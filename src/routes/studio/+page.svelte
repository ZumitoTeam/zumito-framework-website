<script>
    import welcomePng from '$lib/assets/welcome.png';
    import dbExplorerPng from '$lib/assets/dbExplorer.png';
    import moduleSettingsPng from '$lib/assets/moduleSettings.png';
    import moduleMarketplacePng from '$lib/assets/ModuleMarketplace.png';
    import botSettingsPng from '$lib/assets/botSettings.png';

    const features = [
        { title: 'Visual Bot Config', desc: 'Point-and-click database driver setup, module management, and web server config.', img: botSettingsPng, alt: 'Bot configuration editor' },
        { title: 'Database Explorer', desc: 'Browse collections, filter with visual query builder, and edit records inline. TingoDB, SQLite, MongoDB.', img: dbExplorerPng, alt: 'Database explorer' },
        { title: 'Module Marketplace', desc: 'Browse and install community modules directly from the IDE. One-click install from the Zumito registry.', img: moduleMarketplacePng, alt: 'Module marketplace' },
        { title: 'Module Settings', desc: 'Configure installed modules visually. Auto-detects schema from TypeScript types.', img: moduleSettingsPng, alt: 'Module settings' },
    ];

    const commands = [
        { cmd: 'create project', label: 'Scaffold a new bot' },
        { cmd: 'create module', label: 'Generate modules with commands + events' },
        { cmd: 'create command', label: 'Prefix, slash, or hybrid commands' },
        { cmd: 'create embed', label: 'Visual embed builder with preview' },
        { cmd: 'inject service', label: 'Auto-wire DI with code actions' },
        { cmd: 'modules configure', label: 'Manage installed modules' },
        { cmd: 'modules install', label: 'Install from registry' },
        { cmd: 'run dev', label: 'Hot-reload dev server' },
        { cmd: 'run debug', label: 'Debug with breakpoints' },
        { cmd: 'discord portal', label: 'Invite URL + dev portal' },
        { cmd: 'db explorer', label: 'Visual database browser' },
        { cmd: 'config editor', label: 'Visual zumito.config.ts' },
    ];

    const specs = [
        { key: 'Architecture', val: 'Electron 39 + Eclipse Theia 1.73' },
        { key: 'Languages', val: 'TypeScript · JavaScript · JSON · CSS · HTML' },
        { key: 'Database drivers', val: 'TingoDB · SQLite · MongoDB · Memory' },
        { key: 'Integrated CLI', val: 'zumito-cli · Project scaffolding · Code generation' },
        { key: 'Module system', val: 'Community registry · One-click install · Auto-config' },
        { key: 'Extension support', val: 'VS Code extension compatible · Open VSX' },
        { key: 'License', val: 'MIT — Open source, free forever' },
    ];
</script>

<svelte:head>
    <title>Zumito Studio — IDE for Discord Bot Engineering</title>
</svelte:head>

<!-- Hero -->
<div class="relative overflow-hidden bg-white">
    <div class="absolute inset-0 opacity-30">
        <div class="absolute -top-24 right-0 h-96 w-96 rounded-full bg-gradient-to-br from-rose-400 to-purple-400 blur-[128px]" />
        <div class="absolute bottom-0 left-0 h-64 w-64 rounded-full bg-gradient-to-tr from-pink-300 to-rose-300 blur-[96px]" />
    </div>
    <div class="mx-auto max-w-7xl px-6 md:px-12 xl:px-6">
        <div class="relative ml-auto pt-36 pb-20">
            <div class="mx-auto text-center lg:w-2/3">
                <span class="rounded-full bg-rose-100 px-3 py-1 text-sm font-semibold text-rose-600">BETA</span>
                <h1 class="mt-4 text-4xl font-bold text-gray-900 md:text-5xl xl:text-6xl">
                    Zumito <span class="text-rose-600">Studio</span>
                </h1>
                <p class="mt-6 text-lg text-gray-600">
                    The dedicated IDE for engineering Discord bots with the Zumito Framework.
                    Built on Eclipse Theia. Forged for speed.
                </p>

                <div class="mt-10 flex flex-wrap justify-center gap-x-6 gap-y-4">
                    <a href="https://github.com/ZumitoTeam/zumito-studio/releases" data-cursor="block" class="relative flex h-11 w-full items-center justify-center px-6 before:absolute before:inset-0 before:rounded-full before:bg-rose-600 before:transition before:duration-300 hover:before:scale-105 active:before:scale-95 sm:w-max">
                        <span class="relative text-base font-semibold text-white">Download Beta</span>
                    </a>
                    <a href="https://github.com/ZumitoTeam/zumito-studio" data-cursor="block" class="relative flex h-11 w-full items-center justify-center px-6 before:absolute before:inset-0 before:rounded-full before:border before:border-transparent before:bg-rose-600/10 before:bg-gradient-to-b before:transition before:duration-300 hover:before:scale-105 active:before:scale-95 sm:w-max">
                        <span class="relative text-base font-semibold text-rose-600">Source Code</span>
                    </a>
                </div>

                <div class="mt-8 flex justify-center gap-8 text-sm text-gray-400">
                    <span>macOS</span><span class="text-gray-300">·</span>
                    <span>Windows</span><span class="text-gray-300">·</span>
                    <span>Linux</span>
                </div>
            </div>
        </div>
    </div>
</div>

<!-- Main screenshot -->
<div class="mx-auto max-w-6xl px-6 -mt-8">
    <img src={welcomePng} alt="Zumito Studio welcome screen" class="w-full" />
</div>

<!-- Features grid -->
<div class="mx-auto max-w-7xl bg-white px-5 py-20">
    <h2 class="text-center text-2xl font-bold text-gray-800 md:text-4xl" data-cursor="text">What's <span class="text-rose-600">inside</span></h2>
    <p class="mt-4 text-center text-gray-500">Everything you need to build, configure, and deploy your bot — all in one place.</p>

    <div class="mt-10 grid grid-cols-1 gap-8 lg:grid-cols-2">
        {#each features as f}
            <div class="overflow-hidden rounded-2xl bg-gradient-to-br from-rose-50 to-pink-50 p-6 shadow-lg transition-all duration-300 hover:shadow-xl lg:p-8">
                <h3 class="text-xl font-semibold text-gray-800">{f.title}</h3>
                <p class="mt-2 text-gray-500">{f.desc}</p>
                <img src={f.img} alt={f.alt} class="mt-6 w-full rounded-xl border border-gray-100 shadow-md" loading="lazy" />
            </div>
        {/each}
    </div>
</div>

<!-- Command matrix -->
<div class="mx-auto max-w-7xl bg-white px-5 py-10">
    <h2 class="text-center text-2xl font-bold text-gray-800 md:text-4xl" data-cursor="text">Built-in <span class="text-rose-600">Commands</span></h2>
    <p class="mt-4 text-center text-gray-500">13 CLI commands integrated into the IDE ribbon and command palette.</p>

    <div class="mt-8 grid grid-cols-2 gap-2 md:grid-cols-3 lg:grid-cols-4">
        {#each commands as c}
            <div class="rounded-xl border border-gray-100 bg-gray-50 px-4 py-3 transition-colors hover:border-rose-200 hover:bg-rose-50">
                <code class="text-sm font-semibold text-rose-600">zumito-cli {c.cmd}</code>
                <p class="mt-1 text-xs text-gray-400">{c.label}</p>
            </div>
        {/each}
    </div>
</div>

<!-- Specs -->
<div class="mx-auto max-w-7xl bg-white px-5 py-10">
    <h2 class="text-center text-2xl font-bold text-gray-800 md:text-4xl" data-cursor="text">Technical <span class="text-rose-600">Specs</span></h2>

    <div class="mx-auto mt-8 max-w-2xl divide-y divide-gray-100 rounded-2xl border border-gray-200 bg-white">
        {#each specs as s}
            <div class="flex justify-between px-6 py-4">
                <span class="text-sm font-medium text-gray-500">{s.key}</span>
                <span class="text-sm text-gray-800">{s.val}</span>
            </div>
        {/each}
    </div>
</div>

<!-- CTA -->
<div class="mx-auto max-w-7xl px-5 py-16">
    <div class="rounded-3xl bg-gradient-to-r from-rose-600 to-purple-600 p-12 text-center text-white shadow-2xl">
        <h2 class="text-3xl font-bold md:text-4xl" data-cursor="text">Ready to build?</h2>
        <p class="mt-4 text-lg text-rose-100">Download the beta and start engineering your bot with precision.</p>
        <div class="mt-8 flex flex-wrap justify-center gap-4">
            <a href="https://github.com/ZumitoTeam/zumito-studio/releases" class="rounded-full bg-white px-8 py-4 font-semibold text-rose-600 shadow-lg transition-all duration-300 hover:scale-105 hover:shadow-xl" data-cursor="block">
                Download — macOS / Windows / Linux
            </a>
        </div>
        <p class="mt-6 text-sm text-rose-200">Status: Beta · Compatible with Zumito Framework 1.x</p>
    </div>
</div>

<!-- Footer links -->
<div class="mx-auto max-w-7xl px-5 pb-10 text-center">
    <div class="flex justify-center gap-6 text-sm text-gray-400">
        <a href="https://github.com/ZumitoTeam/zumito-studio" class="hover:text-rose-600 transition-colors">GitHub</a>
        <a href="https://discord.gg/zumito" class="hover:text-rose-600 transition-colors">Discord</a>
        <a href="https://github.com/ZumitoTeam/zumito-framework" class="hover:text-rose-600 transition-colors">Framework</a>
        <a href="https://modules.zumito.dev" class="hover:text-rose-600 transition-colors">Modules</a>
    </div>
</div>
