<script>
  import EventTable from "./EventTable.svelte";
  import home from "../assets/home.png"
  import addbtn from "../assets/add-01.png"
</script>

<section class="w-full h-screen  p-4 flex flex-col gap-3 ">
    <div class="flex gap-2 items-center ml-1">
     <div class="text-black font-semibold flex gap-2 items-center"> <img src={home} alt="home icon" class="w-3 h-3"> Home</div>
      <span class="text-gray-400 font-semibold"> > Event</span>
    </div>
    <div class="eventable rounded-lg bg-white mb-[10rem]">
        <!-- upcomoing events -->
     <div class="events px-5 mt-2 flex justify-between items-center">
        <h1 class="font-medium text-[1.2rem]">Upcoming Events</h1>
        <!-- create events -->
    <button class="button p-2 rounded-md bg-[#1C64F2] text-white text-[0.9rem] mt-3 flex items-center gap-2 ">
        <img src={addbtn} alt="">
        <span>Create event</span></button>

     </div>
    <EventTable/>
    </div>
</section>