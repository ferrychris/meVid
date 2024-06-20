<script>
      const featuresLink = "/features";
</script>

<div class="flex ml-[65px] mt-6">
    <div>
       <h2 class="text-2xl text-primary font-bold cursor-pointer ">Me<span class="text-green-500 cursor-pointer">Vid</span></h2> 
    </div>
    
    <nav class="hidden md:flex space-x-9 ml-[690px] d-flex">
        <ul class="flex space-x-3 mt-3">
            <a href={featuresLink}>
                <li
                    class="text-1xl font-bold hover:text-[#FF0000] cursor-pointer"
                >
                    FEATURES
                </li></a
            >
            <a href="#s"
                ><li
                    class="text-1xl font-bold hover:text-[#FF0000] cursor-pointer"
                >
                    PRICING
                </li></a
            >
        </ul>
        <div class="space-x-4 ml-9">
            <a href="#e"
                ><button class="bg-primary border-0 px-3 py-2 rounded"
                    >Login</button
                ></a
            >
            <a href="#e"
                ><button class="px-6 py-2 rounded bg-green-500 text-black font-bold"
                    >Register</button
                ></a
            >
        </div>
    </nav>
</div>
