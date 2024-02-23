<script>
  import Avatar from "../assets/Avatar.png";
  import Thumbnail from "../assets/thumbnail/Thumbnail.png";
  import Thumbnail2 from "../assets/thumbnail/thumbnail2.png";
  import Thumbnail3 from "../assets/thumbnail/thumbnail3.png";
  import Thumbnail4 from "../assets/thumbnail/thumbnail4.png";

  import OptionBtn from "../assets/Button.png";
  import Filter from "../assets/filter.png";
  import { Data } from "../constant/constantData";
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
  let searchTerm = "";

  $: filteredItems = Data.filter(
    (item) =>
      item.product_name.toLowerCase().indexOf(searchTerm.toLowerCase()) !== -1
  );

  let average = 10;
</script>

<TableSearch placeholder="Search" hoverable={true} bind:inputValue={searchTerm}>
  <div class="flex space-x-4 absolute top-[1.4rem] left-[23rem]">
    <button
      class=" py-2 px-5 border border-gray-400 rounded-md font-semibold text-blue-500 flex items-center gap-1 hover:bg-slate-100"
    >
      <img src={Filter} alt="" />
      <p>Filters</p>
    </button>
    <button
      class=" py-2 px-5 border border-gray-400 rounded-md font-bold text-[#333B4C] flex gap-1 justify-center items-center hover:bg-slate-100"
    >
      <span>Action</span>
      <svg
        class="w-2.5 h-2.5 ms-3 mt-1"
        aria-hidden="true"
        xmlns="http://www.w3.org/2000/svg"
        fill="none"
        viewBox="0 0 10 6"
      >
        <path
          stroke="currentColor"
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="m1 1 4 4 4-4"
        />
      </svg></button
    >
  </div>
  <TableHead>
    <!-- <TableHeadCell class="p-4">
      <Checkbox />
    </TableHeadCell> -->
    <TableHeadCell>
      <div class="show flex gap-5">
        <Checkbox />
        <span class="text-[#666C79] opacity-70 capitalize">Show</span>
      </div></TableHeadCell
    >

    <TableHeadCell
      ><span class="text-[#666C79] opacity-70 capitalize"> Performers</span>
    </TableHeadCell>
    <TableHeadCell>
      <span class="text-[#666C79] opacity-70 capitalize">Seats</span
      ></TableHeadCell
    >
    <TableHeadCell
      ><span class="text-[#666C79] opacity-70 capitalize">Sale</span>
    </TableHeadCell>
    <TableHeadCell
      ><span class="text-[#666C79] opacity-70 capitalize">Type</span
      ></TableHeadCell
    >
    <TableHeadCell
      ><span class="text-[#666C79] opacity-70 capitalize">Stage</span
      ></TableHeadCell
    >
    <TableHeadCell
      ><span class="text-[#666C79] opacity-70 capitalize">Status</span
      ></TableHeadCell
    >
    <TableHeadCell></TableHeadCell>
  </TableHead>

  <TableBody class="divide-y ">
    {#each filteredItems as item}
      <TableBodyRow gap="3">
        <!-- <TableBodyCell class="!p-4">
        <Checkbox />
      </TableBodyCell> -->
        <TableBodyCell style="width: 20%;">
          <div class="name flex items-center gap-2">
            <Checkbox />
            <div class="date flex flex-col items-center">
              <div class="day text-[#666C79] text-[0.6rem]">FRI</div>
              <div class="day text-[#1C64F2] text-[1.2rem]">23</div>
              <div class="day text-[#666C79] text-[0.6rem]">SEP</div>
            </div>
            <!-- avatar -->
            <img src={item.Thumbnail} alt="" />
            <!-- NAME + TIME -->
            <div class="wrapper flex flex-col gap-1">
              <h4 class="text-[0.8rem]">{item.product_name}</h4>
              <p class="text-[#666C79] text-[0.7rem]">12:30PM PST</p>
            </div>
          </div>
        </TableBodyCell>

        <TableBodyCell style="width: 15%;">
          <div class="avatar flex items-start">
            <img src={Avatar} alt="" />
          </div>
        </TableBodyCell>

        <TableBodyCell style="width: 15%;">
          <div class="w-[90%] range flex flex-col">
            <p class=" text-end text-[#666C79]">{item.Seats}</p>
            <div class="w-full h-2 bg-gray-300 rounded-full overflow-hidden">
              <div
                class={`h-full ${
                  item.average < 20
                    ? "bg-red-600"
                    : item.average >= 20 && item.average < 50
                      ? "bg-orange-500"
                      : "bg-green-500"
                }`}
                style="width: {item.average}%"
              ></div>
            </div>
            <p class="text-[0.7rem] text-gray-400 ml-5">2 in cart</p>
          </div>
        </TableBodyCell>

        <TableBodyCell style="width: 10%;">
          <span class="text-[#15A033]">{item.Sale}</span></TableBodyCell
        >

        <TableBodyCell style="width: 10%;"
          ><div class="type flex flex-col text-[0.7rem] text-[#333B4C]">
            <p>Stand-up</p>
            <p>Concert</p>
          </div></TableBodyCell
        >
        <TableBodyCell style="width: 10%;"
          ><p class="type flex flex-col text-[0.7rem] text-[#333B4C]">
            Main
          </p></TableBodyCell
        >
        <TableBodyCell style="width: 10%;"
          ><div
            class={`status py-1 px-2 inline-flex items-center gap-2 rounded-lg  ${
              item.Status == "On sale"
                ? "bg-[#15A0331A]"
                : item.Status == "draft"
                  ? "bg-[#6C2BD9]/15"
                  : "bg-[#FF922E]/15"
            }`}
          >
            <div
              class={`circle mt-1 h-2 w-2 rounded-full ${
                item.Status == "On sale"
                  ? "bg-green-600"
                  : item.Status == "draft"
                    ? "bg-[#6C2BD9]"
                    : "bg-[#FF922E]"
              } `}
            ></div>
            <h3
              class={` ${
                item.Status == "On sale"
                  ? "text-green-600"
                  : item.Status == "draft"
                    ? "text-[#6C2BD9]"
                    : "text-[#FF922E]"
              } `}
            >
              {item.Status}
            </h3>
          </div></TableBodyCell
        >
        <TableBodyCell style="width: 10%;"
          ><img src={OptionBtn} alt="" /></TableBodyCell
        >
      </TableBodyRow>
    {/each}
  </TableBody>
</TableSearch>
