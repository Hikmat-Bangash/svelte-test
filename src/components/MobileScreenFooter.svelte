<script>
    import Home from "../assets/home-02.png"
    import event from "../assets/event.png"
    import sale from "../assets/sale-tag-02.png"
    import Peformance from "../assets/user-love-01.png"
    
   export const FooterTags = [
        {
        image: Home,
        name: "Home",
    },
    
  {
        image: event,
        name: "Events",
    },

    {
        image: sale,
        name: "Sales",
    },
{
        image: Peformance,
        name: "Performers",
    },


    ]
</script>

<footer class="w-full bottom-0 fixed flex justify-around border-t border-gray-400 items-center py-3 h-[5rem] bg-white border-b">
 <!-- left side -->
 {#each FooterTags as Tag}
 <div class="navigationTag flex flex-col items-center gap-1">
 <img src={Tag.image} alt="" class="w-[1.2rem] ">
 <p class={`text-[12px] ${Tag.name == "Events" && "font-bold text-blue-600"}`}>{Tag.name}</p>
 </div>
 {/each}
</footer>