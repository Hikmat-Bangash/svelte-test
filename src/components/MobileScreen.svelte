<script>
  import EventTable from "./EventTable.svelte";
  import home from "../assets/home.png"
  import Footer from '../components/MobileScreenFooter.svelte'
  import addbtn from "../assets/add-01.png"
  import MobileScreenTable from "./MobileScreenTable.svelte";
import Thumbnail from "../assets/thumbnail/Thumbnail.png";
import notification from "../assets/notification-02.png";
import SearchVector from "../assets/Vector.png";

</script>

<section class=" w-full h-screen  py-4 flex flex-col gap-3 ">
<!-- navbar -->
<nav class="w-full flex justify-between items-center py-3 h-[4rem] bg-white border-b border-gray-400">
 <!-- left side -->
 <div class="Left ml-1 flex gap-2 items-center justify-center">
  <img src={Thumbnail} alt="" class="w-[3rem] h-[3rem] rounded-full">
  <div class="name flex flex-col gap-0.5">
<h4 class="text-[1.2rem] font-bold">Hi Jese Leos!</h4>
<p  class="text-[0.8rem] text-gray-400">Good Morning</p>
  </div>
 </div>
 <!-- right -->
 <div class="right flex items-center justify-center gap-3 mr-2">
    <img src={notification} alt="">
    <img src={SearchVector} alt="">
 </div>
</nav>

    <div class="createBTN w-full flex justify-end scroll ">
       <button class="button mr-3 w-[50%] p-2 rounded-md bg-[#1C64F2] text-white text-[0.9rem] mt-3 flex items-end gap-2 ">
        <img src={addbtn} alt="">
        <span>Create event</span></button>
</div>
    <div class="eventable rounded-lg bg-white mb-[10rem] h-[30rem] border">
        <!-- upcomoing events -->
     <div class="events px-4  mt-2 flex justify-between items-center">
        <h1 class="font-medium text-[1.2rem]">Upcoming Events</h1>
        <!-- create events -->
     </div>
    <MobileScreenTable/>
    </div>

    <Footer/>
</section>