<script lang="ts">
  import { enhance } from "$app/forms";
  import type { SubmitFunction } from "@sveltejs/kit";
  import type { ActionData } from "./$types";
  import { disableScrollHandling } from "$app/navigation";

  export let form: ActionData

  let formData = {
    description: '',
    file: ''
  }

    const handleSubmitPost: SubmitFunction = ({ data, cancel, formData}) => {
        const { description, file } = Object.entries(data)

        console.log(description)
    } 

    const showMenu = () => {
        const menu = document.querySelector(".menu")
        menu?.classList.toggle("hidden")
    }

    const handleFileSubmit = (event: Event) => {
        const fileInput = event.target.value

        console.log(fileInput);
        
        if(fileInput.length < 1 && !fileInput){
            console.log("no podés hacer eso")
        }
    }
</script>
<main class="bg-white-100 dark:bg-gray-800 relative h-screen overflow-hidden relative">
    <div class="flex items-start justify-between">
      <div class="menu h-screen hidden lg:block my-4 ml-4 shadow-lg relative w-80">
        <div class="bg-white h-full rounded-2xl dark:bg-gray-700">
          <div class="flex items-center justify-center pt-6">
            <svg width="35" height="30" viewBox="0 0 256 366" version="1.1" preserveAspectRatio="xMidYMid">
              <defs>
                <linearGradient x1="12.5189534%" y1="85.2128611%" x2="88.2282959%" y2="10.0225497%" id="linearGradient-1">
                  <stop stop-color="#FF0057" stop-opacity="0.16" offset="0%"></stop>
                  <stop stop-color="#FF0057" offset="86.1354%"></stop>
                </linearGradient>
              </defs>
              <g>
                <path
                  d="M0,60.8538006 C0,27.245261 27.245304,0 60.8542121,0 L117.027019,0 L255.996549,0 L255.996549,86.5999776 C255.996549,103.404155 242.374096,117.027222 225.569919,117.027222 L145.80812,117.027222 C130.003299,117.277829 117.242615,130.060011 117.027019,145.872817 L117.027019,335.28252 C117.027019,352.087312 103.404567,365.709764 86.5997749,365.709764 L0,365.709764 L0,117.027222 L0,60.8538006 Z"
                  fill="#001B38"
                ></path>
                <circle fill="url(#linearGradient-1)" transform="translate(147.013244, 147.014675) rotate(90.000000) translate(-147.013244, -147.014675) " cx="147.013244" cy="147.014675" r="78.9933938"></circle>
                <circle fill="url(#linearGradient-1)" opacity="0.5" transform="translate(147.013244, 147.014675) rotate(90.000000) translate(-147.013244, -147.014675) " cx="147.013244" cy="147.014675" r="78.9933938"></circle>
              </g>
            </svg>
          </div>
          <nav class="mt-6">
            <div>
              <a
                class="w-full font-thin uppercase text-blue-500 flex items-center p-4 my-2 transition-colors duration-200 justify-start bg-gradient-to-r from-white to-blue-100 border-r-4 border-blue-500 dark:from-gray-700 dark:to-gray-800 border-r-4 border-blue-500"
                href="#"
              >
                <span class="text-left">
                  <svg width="20" height="20" fill="currentColor" viewBox="0 0 2048 1792" xmlns="http://www.w3.org/2000/svg">
                    <path d="M1070 1178l306-564h-654l-306 564h654zm722-282q0 182-71 348t-191 286-286 191-348 71-348-71-286-191-191-286-71-348 71-348 191-286 286-191 348-71 348 71 286 191 191 286 71 348z"></path>
                  </svg>
                </span>
                <span class="mx-4 text-sm font-normal">
                  Inicio
                </span>
              </a>
              <a class="w-full font-thin uppercase text-gray-500 dark:text-gray-200 flex items-center p-4 my-2 transition-colors duration-200 justify-start hover:text-blue-500" href="#">
                <span class="text-left">
                  <svg width="20" height="20" fill="currentColor" class="m-auto" viewBox="0 0 2048 1792" xmlns="http://www.w3.org/2000/svg">
                    <path
                      d="M1024 1131q0-64-9-117.5t-29.5-103-60.5-78-97-28.5q-6 4-30 18t-37.5 21.5-35.5 17.5-43 14.5-42 4.5-42-4.5-43-14.5-35.5-17.5-37.5-21.5-30-18q-57 0-97 28.5t-60.5 78-29.5 103-9 117.5 37 106.5 91 42.5h512q54 0 91-42.5t37-106.5zm-157-520q0-94-66.5-160.5t-160.5-66.5-160.5 66.5-66.5 160.5 66.5 160.5 160.5 66.5 160.5-66.5 66.5-160.5zm925 509v-64q0-14-9-23t-23-9h-576q-14 0-23 9t-9 23v64q0 14 9 23t23 9h576q14 0 23-9t9-23zm0-260v-56q0-15-10.5-25.5t-25.5-10.5h-568q-15 0-25.5 10.5t-10.5 25.5v56q0 15 10.5 25.5t25.5 10.5h568q15 0 25.5-10.5t10.5-25.5zm0-252v-64q0-14-9-23t-23-9h-576q-14 0-23 9t-9 23v64q0 14 9 23t23 9h576q14 0 23-9t9-23zm256-320v1216q0 66-47 113t-113 47h-352v-96q0-14-9-23t-23-9h-64q-14 0-23 9t-9 23v96h-768v-96q0-14-9-23t-23-9h-64q-14 0-23 9t-9 23v96h-352q-66 0-113-47t-47-113v-1216q0-66 47-113t113-47h1728q66 0 113 47t47 113z"
                    ></path>
                  </svg>
                </span>
                <span class="mx-4 text-sm font-normal">
                  Proyectos
                </span>
              </a>
              <a class="w-full font-thin uppercase text-gray-500 dark:text-gray-200 flex items-center p-4 my-2 transition-colors duration-200 justify-start hover:text-blue-500" href="#">
                <span class="text-left">
                  <svg width="20" height="20" fill="currentColor" class="m-auto" viewBox="0 0 2048 1792" xmlns="http://www.w3.org/2000/svg">
                    <path
                      d="M1024 1131q0-64-9-117.5t-29.5-103-60.5-78-97-28.5q-6 4-30 18t-37.5 21.5-35.5 17.5-43 14.5-42 4.5-42-4.5-43-14.5-35.5-17.5-37.5-21.5-30-18q-57 0-97 28.5t-60.5 78-29.5 103-9 117.5 37 106.5 91 42.5h512q54 0 91-42.5t37-106.5zm-157-520q0-94-66.5-160.5t-160.5-66.5-160.5 66.5-66.5 160.5 66.5 160.5 160.5 66.5 160.5-66.5 66.5-160.5zm925 509v-64q0-14-9-23t-23-9h-576q-14 0-23 9t-9 23v64q0 14 9 23t23 9h576q14 0 23-9t9-23zm0-260v-56q0-15-10.5-25.5t-25.5-10.5h-568q-15 0-25.5 10.5t-10.5 25.5v56q0 15 10.5 25.5t25.5 10.5h568q15 0 25.5-10.5t10.5-25.5zm0-252v-64q0-14-9-23t-23-9h-576q-14 0-23 9t-9 23v64q0 14 9 23t23 9h576q14 0 23-9t9-23zm256-320v1216q0 66-47 113t-113 47h-352v-96q0-14-9-23t-23-9h-64q-14 0-23 9t-9 23v96h-768v-96q0-14-9-23t-23-9h-64q-14 0-23 9t-9 23v96h-352q-66 0-113-47t-47-113v-1216q0-66 47-113t113-47h1728q66 0 113 47t47 113z"
                    ></path>
                  </svg>
                </span>
                <span class="mx-4 text-sm font-normal">
                  Reportes
                </span>
              </a>

              <a class="w-full font-thin uppercase text-gray-500 dark:text-gray-200 flex items-center p-4 my-2 transition-colors duration-200 justify-start hover:text-blue-500" href="#">
                <span class="text-left">
                  <svg width="20" fill="currentColor" height="20" class="h-5 w-5" viewBox="0 0 1792 1792" xmlns="http://www.w3.org/2000/svg">
                    <path
                      d="M1088 1256v240q0 16-12 28t-28 12h-240q-16 0-28-12t-12-28v-240q0-16 12-28t28-12h240q16 0 28 12t12 28zm316-600q0 54-15.5 101t-35 76.5-55 59.5-57.5 43.5-61 35.5q-41 23-68.5 65t-27.5 67q0 17-12 32.5t-28 15.5h-240q-15 0-25.5-18.5t-10.5-37.5v-45q0-83 65-156.5t143-108.5q59-27 84-56t25-76q0-42-46.5-74t-107.5-32q-65 0-108 29-35 25-107 115-13 16-31 16-12 0-25-8l-164-125q-13-10-15.5-25t5.5-28q160-266 464-266 80 0 161 31t146 83 106 127.5 41 158.5z"
                    ></path>
                  </svg>
                </span>
                <span class="mx-4 text-sm font-normal">
                  Ajustes
                </span>
              </a>
            </div>
          </nav>
        </div>
      </div>

      <!-- navbar -->
      <div class="flex flex-col w-full pl-0 md:p-4 md:space-y-4">
        <header class="w-full shadow-lg bg-white dark:bg-gray-700 items-center h-16 rounded-2xl z-40">
          <div class="relative z-20 flex flex-col justify-center h-full px-3 mx-auto flex-center">
            <div class="relative items-center pl-1 flex w-full lg:max-w-68 sm:pr-2 sm:ml-0">
              <div class="container relative left-0 z-50 flex w-3/4 h-auto h-full">
                <div class="relative flex items-center w-full lg:w-64 h-full group">
                <button class="hidden flex px-3 py-2 bg-blue-400 mr-1 text-white font-semibold rounded">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M3 12l2-2m0 0l7-7 7 7M5 10v10a1 1 0 001 1h3m10-11l2 2m-2-2v10a1 1 0 01-1 1h-3m-6 0a1 1 0 001-1v-4a1 1 0 011-1h2a1 1 0 011 1v4a1 1 0 001 1m-6 0h6" />
                    </svg>
                    <span class="ml-1">Menú</span>
                </button>

                <!-- show menu -->
                <button 
                    class="xl:hidden flex px-3 py-2 bg-blue-400 mr-1 text-white font-semibold rounded"
                    on:click={showMenu}
                    >
                    <span class="ml-1">Menú</span>
                </button>

                <!-- search -->
                  <input
                    type="text"
                    class="block w-full py-1.5 pl-10 pr-4 leading-normal rounded-2xl focus:border-transparent focus:outline-none focus:ring-2 focus:ring-blue-500 ring-opacity-90 bg-gray-100 dark:bg-gray-800 text-gray-400 aa-input"
                    placeholder="Búsqueda..."
                  />
                </div>
              </div>
              <div class="relative p-1 flex items-center justify-end w-1/4 ml-5 mr-4 sm:mr-0 sm:right-auto">
                <a href="#" class="block relative">
                  <img
                    alt="profil"
                    src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=880&q=80"
                    class="mx-auto object-cover rounded-full h-10 w-10"
                  />
                </a>
              </div>
            </div>
          </div>
        </header>

        <!-- Post Content Section -->
        <div class="grid content-start mt-5 p-10">
            <div class="max-w-md w-full bg-white p-8 rounded-lg shadow-md">
                <form action="?/submitFile" method="post" use:enhance={handleSubmitPost}>
                    <div class="mb-6">
                        <label for="postContent" class="block text-gray-700 text-sm font-bold mb-2">Descripción :</label>
                        <textarea
                            id="postContent"
                            name="postContent"
                            rows="4"
                            class="w-full border-2 rounded-md px-4 py-2 leading-5 transition duration-150 ease-in-out sm:text-sm sm:leading-5 resize-none focus:outline-none focus:border-blue-500"
                            placeholder="¿Qué estás pensando?"
                            maxlength="360"
                            bind:value={formData.description}
                        ></textarea>
                    </div>
                    <!-- File Attachment Section -->
                    <div class="mb-6">
                        <label for="fileAttachment" class="block text-gray-700 text-sm font-bold mb-2">Ingresa archivo :</label>
                        <div class="relative border-2 rounded-md px-4 py-3 bg-white flex items-center justify-between hover:border-blue-500 transition duration-150 ease-in-out">
                            <input 
                                type="file" 
                                id="fileAttachment" 
                                name="fileAttachment" 
                                class="absolute inset-0 w-full h-full opacity-0 cursor-pointer" 
                                bind:value={formData.file}
                                on:change={handleFileSubmit}
                                />
                            <div class="flex items-center">
                                <svg class="w-6 h-6 text-gray-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
                                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6v6m0 0v6m0-6h6m-6 0H6"></path>
                                </svg>
                                <span class="ml-2 text-sm text-gray-600">Arrastra aquí</span>
                            </div>
                            <span class="text-sm text-gray-500">Max file size: 10MB</span>
                        </div>
                    </div>

                    <div class="flex items-center justify-between">
                        <button 
                            type="submit" 
                            class="flex justify-center items-center bg-blue-500 hover:bg-blue-600 focus:outline-none focus:shadow-outline-blue text-white py-2 px-4 rounded-md transition duration-300 gap-2"
                            >
                            Publicar
                            <svg xmlns="http://www.w3.org/2000/svg" width="19" height="19" viewBox="0 0 24 24" id="send" fill="#fff">
                                <path fill="none" d="M0 0h24v24H0V0z"></path>
                                <path d="M3.4 20.4l17.45-7.48c.81-.35.81-1.49 0-1.84L3.4 3.6c-.66-.29-1.39.2-1.39.91L2 9.12c0 .5.37.93.87.99L17 12 2.87 13.88c-.5.07-.87.5-.87 1l.01 4.61c0 .71.73 1.2 1.39.91z"></path>
                            </svg>
                        </button>
                        <span class="text-gray-500 text-sm">Máximo 360 carácteres</span>
                    </div>
                </form>
            </div>
        </div>
  </main>  