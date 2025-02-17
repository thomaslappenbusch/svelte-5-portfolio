<script lang="ts">
	import Introduction from './Introduction.svelte';
	import Experience from './Experience.svelte';
	import Education from './Education.svelte';
	import Skills from './Skills.svelte';
	import PersonalProjects from './PersonalProjects.svelte';
	import Gallery from './Gallery.svelte';
    import Button1 from "$lib/components/Button1.svelte";

    const portfolioContent: any = {
        introduction: {
            name: "Jonathan Smith",
            occupation: "Startup Founder @ Resend",
            description: "A software engineer from Dallas Texas. Have experience using React, Tailwind, Svelte and more. Looking for new and exciting projects in the software space. Let's connect!",
            avatar: "https://avatars.githubusercontent.com/u/04?v=4",
            socials: {
                x: "https://x.com/test",
                email: "mailto:hello@test.com",
                linkedin: "https://www.linkedin.com/in/test"
            }
        },
        experiences: [
            {
                company: "Apple",
                role: "Software Engineer II",
                duration: "Present",
                image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTA5r0_FrSjm2OgttQLwh_CnVCnzbJ7dLv6oA&s"
            },
            {
                company: "Meta",
                role: "Senior Frontend Developer",
                duration: "Jan. 2023 to Nov. 2024",
                image: "https://pbs.twimg.com/profile_images/1455242126275526659/zNCAAELg_400x400.png"
            },
            {
                company: "Google",
                role: "Frontend Developer",
                duration: "Jan. 2020 to Dec. 2022",
                image: "https://images.ctfassets.net/y2vv62dcl0ut/4cecci3Vom9aGlDCMwLm0g/cc93483ede67e93325719a423254bf1d/square.jpg"
            }
        ],
        education: {
            image: "https://admission.stanford.edu/assets/cardinal/images/stanford_block_s_logo2.jpg",
            school: "Stanford University",
            degree: "Bachelor of Science in Computer Science",
            graduationYear: "2022"
        },
        skills: [
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M19.8 3.77a6.25 6.25 0 0 0-8.63-1.913L6.11 5.081a6.25 6.25 0 0 0-1.973 8.532a6.25 6.25 0 0 0 8.693 8.53l5.06-3.224a6.25 6.25 0 0 0 1.974-8.532A6.25 6.25 0 0 0 19.8 3.77m-1.352 5.004A6.26 6.26 0 0 0 15.65 7.5a1 1 0 0 0-1.525-1.003L9.066 9.72a1 1 0 1 0 1.075 1.686l2.109-1.343a4.25 4.25 0 1 1 4.567 7.17l-5.06 3.223a4.25 4.25 0 0 1-6.203-5.23A6.25 6.25 0 0 0 8.35 16.5a1 1 0 0 0 1.525 1.003l5.06-3.224a1 1 0 0 0-1.074-1.687l-2.109 1.344a4.25 4.25 0 0 1-4.567-7.17l5.06-3.223a4.25 4.25 0 0 1 6.203 5.23"/></svg>`,
                text: "Svelte"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33s1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2"/></svg>`,
                text: "Github"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24"><path fill="currentColor" d="M12 10.11c1.03 0 1.87.84 1.87 1.89c0 1-.84 1.85-1.87 1.85S10.13 13 10.13 12c0-1.05.84-1.89 1.87-1.89M7.37 20c.63.38 2.01-.2 3.6-1.7c-.52-.59-1.03-1.23-1.51-1.9a23 23 0 0 1-2.4-.36c-.51 2.14-.32 3.61.31 3.96m.71-5.74l-.29-.51c-.11.29-.22.58-.29.86c.27.06.57.11.88.16zm6.54-.76l.81-1.5l-.81-1.5c-.3-.53-.62-1-.91-1.47C13.17 9 12.6 9 12 9s-1.17 0-1.71.03c-.29.47-.61.94-.91 1.47L8.57 12l.81 1.5c.3.53.62 1 .91 1.47c.54.03 1.11.03 1.71.03s1.17 0 1.71-.03c.29-.47.61-.94.91-1.47M12 6.78c-.19.22-.39.45-.59.72h1.18c-.2-.27-.4-.5-.59-.72m0 10.44c.19-.22.39-.45.59-.72h-1.18c.2.27.4.5.59.72M16.62 4c-.62-.38-2 .2-3.59 1.7c.52.59 1.03 1.23 1.51 1.9c.82.08 1.63.2 2.4.36c.51-2.14.32-3.61-.32-3.96m-.7 5.74l.29.51c.11-.29.22-.58.29-.86c-.27-.06-.57-.11-.88-.16zm1.45-7.05c1.47.84 1.63 3.05 1.01 5.63c2.54.75 4.37 1.99 4.37 3.68s-1.83 2.93-4.37 3.68c.62 2.58.46 4.79-1.01 5.63c-1.46.84-3.45-.12-5.37-1.95c-1.92 1.83-3.91 2.79-5.38 1.95c-1.46-.84-1.62-3.05-1-5.63c-2.54-.75-4.37-1.99-4.37-3.68s1.83-2.93 4.37-3.68c-.62-2.58-.46-4.79 1-5.63c1.47-.84 3.46.12 5.38 1.95c1.92-1.83 3.91-2.79 5.37-1.95M17.08 12c.34.75.64 1.5.89 2.26c2.1-.63 3.28-1.53 3.28-2.26s-1.18-1.63-3.28-2.26c-.25.76-.55 1.51-.89 2.26M6.92 12c-.34-.75-.64-1.5-.89-2.26c-2.1.63-3.28 1.53-3.28 2.26s1.18 1.63 3.28 2.26c.25-.76.55-1.51.89-2.26m9 2.26l-.3.51c.31-.05.61-.1.88-.16c-.07-.28-.18-.57-.29-.86zm-2.89 4.04c1.59 1.5 2.97 2.08 3.59 1.7c.64-.35.83-1.82.32-3.96c-.77.16-1.58.28-2.4.36c-.48.67-.99 1.31-1.51 1.9M8.08 9.74l.3-.51c-.31.05-.61.1-.88.16c.07.28.18.57.29.86zm2.89-4.04C9.38 4.2 8 3.62 7.37 4c-.63.35-.82 1.82-.31 3.96a23 23 0 0 1 2.4-.36c.48-.67.99-1.31 1.51-1.9"/></svg>`,
                text: "React"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32"><path fill="currentColor" d="M16 3.936L4.361 8.168L6.45 23.84L16 29.145l9.55-5.307l2.089-15.67zm0 2.128l9.443 3.434l-1.744 13.08L16 26.855l-7.7-4.277l-1.743-13.08zM16 8l-6 14h2l1.29-3h5.42L20 22h2zm0 4.55l.02.06l.7 1.75L17.85 17h-3.7l1.13-2.64l.7-1.75z"/></svg>`,
                text: "Angular"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M3 3v18h18V3zm9.813 14.023c0 1.77-1.045 2.584-2.555 2.584c-1.335 0-2.12-.697-2.526-1.568l1.394-.871c.232.493.493.87 1.103.87c.58 0 .9-.203.9-1.073v-5.69h1.684zm4.006 2.584c-1.567 0-2.583-.784-3.106-1.713l1.394-.813c.377.58.87 1.016 1.683 1.016c.697 0 1.133-.32 1.133-.871c0-.58-.436-.784-1.22-1.133l-.406-.174c-1.22-.493-2.033-1.19-2.033-2.584c0-1.277.93-2.206 2.468-2.206c1.075 0 1.83.378 2.38 1.364l-1.305.871c-.29-.493-.581-.725-1.104-.725c-.493 0-.813.32-.813.726c0 .493.32.696 1.017 1.016l.406.174c1.422.61 2.264 1.22 2.264 2.67c.03 1.54-1.16 2.381-2.758 2.381"/></svg>`,
                text: "JavaScript"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M19.131 3H4.869c-.955 0-1.73.787-1.73 1.758v14.484c0 .97.775 1.758 1.73 1.758h14.262c.956 0 1.73-.787 1.73-1.758V4.758c0-.97-.774-1.758-1.73-1.758m-5.712 9.984h-2.215v6.434H9.439v-6.434H7.223v-1.441h6.196zm5.712 5.277c-.139.317-.377.552-.658.739a3 3 0 0 1-.969.386a5.6 5.6 0 0 1-1.177.12a6.5 6.5 0 0 1-1.211-.11a3.7 3.7 0 0 1-1.004-.33v-1.689l-.066-.053l.066-.015v.068q.441.357.972.545c.347.133.727.2 1.108.2c.242 0 .426-.021.589-.06a1.4 1.4 0 0 0 .415-.168a.7.7 0 0 0 .246-.253a.7.7 0 0 0-.052-.738a1.3 1.3 0 0 0-.346-.335a3 3 0 0 0-.52-.295c-.207-.095-.418-.194-.657-.292c-.589-.281-1.053-.562-1.35-.95c-.301-.35-.45-.808-.45-1.335c0-.422.08-.76.242-1.055c.173-.316.377-.548.658-.738c.277-.193.588-.334.969-.422c.38-.088.762-.133 1.177-.133s.762.024 1.073.073c.311.05.602.127.865.229v1.652a2.3 2.3 0 0 0-.415-.242a3.8 3.8 0 0 0-.97-.275a3 3 0 0 0-.45-.033a2.4 2.4 0 0 0-.553.057a1.3 1.3 0 0 0-.416.161a.8.8 0 0 0-.26.25a.6.6 0 0 0-.093.327q0 .194.104.351q.103.152.295.296c.114.091.27.183.45.274c.207.091.394.183.623.278c.311.133.588.281.83.422c.243.14.447.305.623.492c.187.175.322.387.416.633s.142.523.142.843c0 .457-.108.809-.246 1.125"/></svg>`,
                text: "TypeScript"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M23 21.648H1L12 2.352z"/></svg>`,
                text: "Vercel"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M3.084 15.25c-1.664 0-2.6-1.912-1.58-3.226L10.21.806C10.794.054 12 .466 12 1.42v7.33h8.916c1.663 0 2.6 1.912 1.58 3.226L13.79 23.194c-.584.752-1.79.34-1.79-.613V15.25z"/></svg>`,
                text: "Supabase"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M12 22C6.477 22 2 17.523 2 12S6.477 2 12 2s10 4.477 10 10s-4.477 10-10 10m4-14h-1.35v4H16zM9.346 9.71l6.059 7.828l1.054-.809L9.683 8H8v7.997h1.346z"/></svg>`,
                text: "Next.js"
            },
            {
                icon: `<svg class="h-4 w-4 text-primary" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill="currentColor" d="M19.14 7.5A2.86 2.86 0 0 1 22 10.36v3.78A2.86 2.86 0 0 1 19.14 17H12c0 .39.32.96.71.96H17v1.68a2.86 2.86 0 0 1-2.86 2.86H9.86A2.86 2.86 0 0 1 7 19.64v-3.75a2.85 2.85 0 0 1 2.86-2.85h5.25a2.85 2.85 0 0 0 2.85-2.86V7.5zm-4.28 11.79c-.4 0-.72.3-.72.89s.32.71.72.71a.71.71 0 0 0 .71-.71c0-.59-.32-.89-.71-.89m-10-1.79A2.86 2.86 0 0 1 2 14.64v-3.78A2.86 2.86 0 0 1 4.86 8H12c0-.39-.32-.96-.71-.96H7V5.36A2.86 2.86 0 0 1 9.86 2.5h4.28A2.86 2.86 0 0 1 17 5.36v3.75a2.85 2.85 0 0 1-2.86 2.85H8.89a2.85 2.85 0 0 0-2.85 2.86v2.68zM9.14 5.71c.4 0 .72-.3.72-.89s-.32-.71-.72-.71c-.39 0-.71.12-.71.71s.32.89.71.89"/></svg>`,
                text: "Python"
            }
        ],
        projects: [
            {
                name: "Clutch Maps",
                technology: "Svelte",
                description: "Clutch Maps is a map based web app for finding fun driving routes near you. Built mainly using Svelte and the Mapbox API.",
                image: "Basic.png",
                link: "https://clutchmaps.com"
            },
            {
                name: "Coastal UI",
                technology: "Svelte",
                description: "A Svelte 5 Component library which uses Tailwind 4 and Lucide Icons. Useful copy-paste components, for free.",
                image: "coastal2.png",
                link: "https://coastalui.com"
            }
        ],
        gallery: [
            {
                image: "seattle1.jpg",
                text: "Show your hometown!"
            },
            {
                image: "seattle2.jpg",
                text: "My office."
            },
            {
                component: Button1,
                text: "You can even show off components!"
            }
        ]
    }

</script>

<div class="overflow-x-hidden bg-background flex flex-col justify-center items-center relative">
    <div class="w-full max-w-[680px] flex flex-col my-24 lg:px-0 px-5 mb-[100px] sm:mb-[200px]">
        
        <Introduction data={portfolioContent.introduction}/>
        <Experience data={portfolioContent.experiences}/>
        <Education data={portfolioContent.education}/>
        <Skills data={portfolioContent.skills}/>
        <div class="w-full h-[1px] bg-gradient-to-r from-zinc-900 to-zinc-900 via-zinc-800 my-12 mb-16"></div>
        <div class="mb-4 flex flex-col items-center">
            <div class="text-3xl text-primary font-bold">My Work</div>
            <div class="text-faint font-thin mt-1">Collected across various projects.</div>
        </div>
        <PersonalProjects data={portfolioContent.projects}/>
        <Gallery data={portfolioContent.gallery}/>
    </div>
    <div class="bg-gradient-to-b from-background to-background-secondary bg-background h-[200px] w-full">
    </div>
    <button onclick={() => window.open("https://www.coastalui.com/", "_blank")} class="absolute bottom-3 left-1/2 -translate-x-1/2 text-faint text-sm flex items-center cursor-pointer">
        <svg class="text-tertiary mr-1" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24">
            <path fill="currentColor" d="M23 18H1l7.25-9.67l2 2.67L14 6zm-11.5-5.33L14 16h5l-5-6.67zM5 16h6.5l-3.25-4.33z" />
        </svg>
        Coastal UI Homepage
    </button>
</div>