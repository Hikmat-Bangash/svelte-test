<script>
  import Avatar from "../assets/Avatar.png";
  import Thumbnail from "../assets/thumbnail/Thumbnail.png";
  import { Data } from "../constant/constantData";

  import OptionBtn from "../assets/Button.png";
  import Filter from "../assets/filter.png";
  import {
    Table,
    TableBody,
    TableBodyCell,
    TableBodyRow,
    TableHead,
    TableHeadCell,
    Checkbox,
    TableSearch,
  } from "flowbite-svelte";
</script>

<section class="w-full h-screen flex flex-col gap-2 mt-3">
     {#each Data as item}
  <!-- row1 -->
  <div class="row1 px-2 w-full flex justify-between items-center ">
    <div class="left flex gap-3">
      <div class="name flex items-center">
        <div class="date font-semibold flex flex-col items-center">
          <div class="day text-[#666C79] text-[0.6rem]">FRI</div>
          <div class="day font-bold text-[#1C64F2] text-[1.2rem]">23</div>
          <div class="day text-[#666C79] text-[0.6rem]">SEP</div>
        </div>
        <!-- avatar -->
        <img src={Thumbnail} alt="" class="w-[2.5rem] h-[2.5rem] rounded-lg" />
      </div>
      <!-- NAME + TIME -->
      <div class="wrapper flex flex-col">
        <h4 class="text-[0.8rem] font-semibold">Jetpack Comedy</h4>

        <!-- img and status -->
        <div class="imgStatus flex relative w-[8rem]">
        <img src={Avatar} alt="" class="w-[6rem]" />
        <!-- status -->
        <div class="circle flex items-center justify-center gap-1 absolute top-2 left-14">
          <div
            class={`circle mt-1 h-2 w-2 rounded-full bg-green-600
                  `}
          ></div>
          <h3 class="text-green-600 font-bold text-[13px]">On sale</h3>
        </div>
        </div>
      </div>
    </div>
    <!-- right -->
    <div class="right flex flex-col">
<p class="text-[#666C79] text-[0.7rem] font-semibold">Sold : 240/500</p>
<h1 class="text-[#15A033] text-[1rem]">$1482</h1>

    </div>
  </div>
  {/each}
</section>
