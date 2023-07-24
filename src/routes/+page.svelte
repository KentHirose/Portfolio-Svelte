<script lang="ts">
    import Background from '$lib/images/3d-line.png';
    import Hirose from '$lib/images/hirose.png';

    import Tab, { Label } from '@smui/tab';
    import TabBar from '@smui/tab-bar';
    import Button from '@smui/button';
    import Accordion, { Panel, Header, Content } from '@smui-extra/accordion';
    import Paper, { Title } from '@smui/paper';
    import Chip, { Set, Text } from '@smui/chips';
    import Card, {PrimaryAction,Media,MediaContent,} from '@smui/card';

    let active = 'Home';
    let panel1Open = false;
    let panel2Open = false;
    let panel3Open = false;
    let panel4Open = false;
</script>

<body 
    class=" h-screen w-screen bg-cover bg-center"
    style="background-image: url('{Background}');"
>

<div class="flex justify-center items-center h-screen w-screen text-sm px-8">
    <div class="
                container max-w-5xl
                aspect-video
                backdrop-blur-md 
                border border-gray-500/50
                shadow-md
                backdrop-brightness-[1.00]
                ">

        <!-- ヘッダー -->
        <div class="flex justify-between p-3">
            <div class="flex justify-start">
                    <TabBar tabs={['Home', 'About', 'Skills', 'Carrer', 'Contact']} let:tab bind:active>
                        <Tab {tab} minWidth>
                            <Label>{tab}</Label>
                        </Tab>
                    </TabBar>
            </div>

            <!-- 右端のホームロゴ的な -->
            <div class="flex justify-end items-center text-sm pr-3 font-extrabold text-xl text-[#717FFF]">
                <h1>
                    &lt; ../ &gt;
                </h1>
            </div>

        </div>

        <div class="text-[#717FFF]" >
            {#if active === 'Home'}
            <div class="flex justify-end pr-8">
            <div class="flex flex-col">
                    <div class="shrink h-48"></div>
                        <div class="text-lg font-bold flex justify-end">
                            Musashino University
                        </div>
                        <div class="text-lg font-bold flex justify-end">
                            Faculty of Data Science</div>
                        <div class="text-3xl font-bold flex justify-end">
                            Entrepreneur & Developer</div>
                        <div class="text-7xl font-bold">
                            Kento Hirose</div>
                        <Button variant="outlined" on:click={() => active = 'Contact'}>
                            <Label>Contact Me</Label>
                        </Button>
                </div>
                </div>
            {/if}

                {#if active === 'About'}
                <div class="flex justify-between">
                    <div class="px-10 text-slate-500 p-10">
                        <h1 class="text-5xl font-bold">廣瀬 研人 (Hirose Kento)</h1>
                        <div class="pt-2">
                            <h1 class="text-2xl">Faculty of Data Science, Musashino University</h1>
                            <h1 class="text-2xl">武蔵野大学 データサイエンス学部 2年</h1>
                        </div>
                        <h1 class="text-xl">株式会社Gaiax 開発インターン中</h1>
                    </div>

                    <img src={Hirose} alt="Hirose" width = "40%" height = "40%" class="justify-end p-10 shrink">
                </div>

                {/if}
                {#if active === 'Skills'}
                <div class="text-slate-500">
                    <h1 class="px-4 text-slate-500 text-3xl font-bold">
                        Skills</h1>
                    <div class="accordion-container p-4">
                        <Accordion>
                        <Panel 
                        square
                        variant="outlined"
                        color="secondary"
                        extend
                        bind:open={panel1Open}>
                            <Header>
                            > Biz
                            <span slot="description">ビジネススキル.</span>
                            </Header>
                            <Content>
                                <Set chips={['Entrepreneurship', 'Customer Development', "Leadership","Problem-Solving","Sales","Networking","PM"]} let:chip>
                                    <Chip
                                    {chip}>
                                        <Text
                                        >{chip}</Text>
                                    </Chip>
                                </Set>
                            </Content>
                        </Panel>
                        <Panel 
                        square
                        variant="outlined"
                        color="secondary"
                        extend
                        bind:open={panel2Open}>
                            <Header>
                            > Dev
                            <span slot="description">開発スキル.</span>
                            </Header>
                            <Content>
                                <Set chips={['Machine Learning', 'Deep Learning', "LLM","Front End","Back End","DataScience","Design","PoC"]} let:chip>
                                    <Chip
                                    {chip}>
                                        <Text
                                        >{chip}</Text>
                                    </Chip>
                                </Set>
                            </Content>
                        </Panel>
                        <Panel 
                        square
                        variant="outlined"
                        color="secondary"
                        extend
                        bind:open={panel3Open}>
                            <Header>
                            > Tech Stack
                            <span slot="description">経験のある言語やフレームワークなど.</span>
                            </Header>
                            <Content>
                                <Set chips={['Japanese', 'Python', "HTML & CSS","JS","TS","Solidity","React","Material UI","FastAPI","ML&DS Libraries","GCP","Docker","Github"]} let:chip>
                                    <Chip
                                    {chip}>
                                        <Text
                                        >{chip}</Text>
                                    </Chip>
                                </Set>
                            </Content>
                        </Panel>
                        <Panel 
                        square
                        variant="outlined"
                        color="secondary"
                        extend
                        bind:open={panel4Open}>
                            <Header>
                            > Domain
                            <span slot="description">経験のある領域や興味のある分野.</span>
                            </Header>
                            <Content>
                                <Set chips={['Startup', 'LLM', "Data Science","Web3","Education (Educational Technology)","Sociology","Structuralism"]} let:chip>
                                    <Chip
                                    {chip}>
                                        <Text
                                        >{chip}</Text>
                                    </Chip>
                                </Set>
                            </Content>
                        </Panel>
                        </Accordion>
                    </div>
                </div>
                {/if}
                {#if active === 'Carrer'}
                    <div class="text-slate-500">
                        <h1 class="px-4 text-slate-500 text-3xl font-bold">
                            Carrer</h1>
                            <div class="px-6 py-2">
                                <!-- 合同会社Surflexi -->
                                <div class="p-1">
                                <Paper color="secondary" variant="outlined" class="p-2">
                                    <Title>合同会社Surflexi CEO</Title>
                                    <Content>2023/08 予定</Content>
                                    <Content>LLMOpsを中心とした教育業界のDXを行っています。</Content>
                                </Paper>
                                </div>

                                <!-- 株式会社Gaiax 開発インターン -->
                                <div class="p-1">
                                <Paper color="secondary" variant="outlined" class="p-2">
                                    <Title>株式会社Gaiax 開発インターン</Title>
                                    <Content>2023/06 ~ now</Content>
                                    <Content>Web3系の開発や、新規事業の企画を行っています。</Content>
                                </Paper>
                                </div>

                                <!-- 株式会社YouTheOwener PoC開発インターン -->
                                <div class="p-1">
                                <Paper color="secondary" variant="outlined" class="p-2">
                                    <Title>株式会社YouTheOwener PoC開発インターン</Title>
                                    <Content>2022/09 ~ now</Content>
                                    <Content>フロントエンドの技術を用いて、PoCの開発を行っています。</Content>
                                </Paper>
                                </div>
                                
                                <!-- 武蔵野大学データサイエンス学部 -->
                                <div class="p-1">
                                <Paper color="secondary" variant="outlined" class="p-2">
                                    <Title>武蔵野大学データサイエンス学部</Title>
                                    <Content>2022/04 ~ 2026/03卒業予定</Content>
                                    <Content>データサイエンス学部に所属しています。LLMを中心に機械学習技術やデータサイエンスの勉強をしています。</Content>
                                </Paper>
                                </div>
                            </div>
                        </div>
                {/if}
                {#if active === 'Contact'}
                    <div class="text-slate-500">
                        <h1 class="px-4 text-slate-500 text-3xl font-bold">
                            Contact</h1>
                    </div>

                    <div class="text-slate-500">
                        <h1 class="px-4  pt-4 text-slate-500 text-xl font-bold">
                            SNS</h1>
                    </div>
                    
                    <div class="grid grid-cols-4 gap-4 px-4">

                        <a href="https://github.com/KentHirose">
                        <!-- Github -->
                        <div class="card-display">
                            <div class="card-container">
                            Github
                            <Card>
                                <Media class="github-image" aspectRatio="16x9">
                                </Media>
                            </Card>
                            </div>
                        </div>
                        </a>

                        <a href="https://twitter.com/Kent080503">
                        <!-- Twitter -->
                        <div class="card-display">
                            <div class="card-container">
                            Twitter
                            <Card>
                                <Media class="twitter-image" aspectRatio="16x9">
                                </Media>
                            </Card>
                            </div>
                        </div>
                        </a>
                        
                        <!-- wantedly -->
                        <a href="https://www.wantedly.com/id/kento_hirose_c">
                        <div class="card-display">
                            <div class="card-container">
                            Wantedly
                            <Card>
                                <Media class="wantedly-image" aspectRatio="16x9">
                                </Media>
                            </Card>
                            </div>
                        </div>
                        </a>
                        
                        <!-- Qiita -->
                        <a href="https://qiita.com/Kent7974">
                        <div class="card-display">
                            <div class="card-container">
                            Qiita
                            <Card>
                                <Media class="qiita-image" aspectRatio="16x9">
                                </Media>
                            </Card>
                            </div>
                        </div>
                        </a>
                        
                    </div>
                    <div class="text-slate-500">
                        <h1 class="px-4 pt-4 text-slate-500 text-xl font-bold">
                            Mail</h1>
                            <div class="px-4 text-[#717FFF]">
                                s2222031[at]stu.musashino-u.ac.jp</div>
                    </div>
                {/if}
        </div>

</body>

<style>
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+JP&display=swap');
    * :global(.github-image) {
    background-image: url($lib/images/github.png);
    }
    * :global(.twitter-image) {
    background-image: url($lib/images/twitter.png);
    }
    * :global(.wantedly-image) {
    background-image: url($lib/images/wantedly.png);
    }
    * :global(.qiita-image) {
    background-image: url($lib/images/qiita.png);
    }
</style>
