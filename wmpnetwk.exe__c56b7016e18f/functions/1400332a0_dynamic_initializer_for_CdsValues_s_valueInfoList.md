# _dynamic_initializer_for__CdsValues::s_valueInfoList__

- ea: `0x1400332a0`
- end: `0x1400346f5`
- name: `_dynamic_initializer_for__CdsValues::s_valueInfoList__`
- size: `5205`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14003ddb0`
- `0x14004627c`

## string_xrefs

- `0x140033c0b`: `upnp:createClass`
- `0x14003413d`: `microsoft:authorComposer`
- `0x1400343c9`: `upnp:albumArtURI@dlna:profileID`
- `0x140034053`: `microsoft:serviceProvider`
- `0x140034229`: `microsoft:folderPath`
- `0x1400341b1`: `microsoft:authorWriter`
- `0x140034387`: `upnp:albumArtURI`
- `0x140033ef6`: `upnp:scheduledStartTime`
- `0x14003378d`: `upnp:writeStatus`
- `0x1400334ee`: `res@protocolInfo`
- `0x140034440`: `res@dlna:ifoFileURI`

## pseudocode

```c
int dynamic_initializer_for__CdsValues::s_valueInfoList__()
{
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0438,
    byte_1400A4F8D);
  dword_1400C044C[0] = -1;
  dword_1400C0440 = 0;
  word_1400C0444 = 0;
  dword_1400C0448 = 0;
  dword_1400C0458 = 1;
  dword_1400C0450 = -1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0460,
    "@id");
  word_1400C046C = 0;
  dword_1400C0468 = 2;
  dword_1400C0480 = 2;
  qword_1400C0470 = 0;
  dword_1400C0478 = 1;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0488,
    "@refID");
  dword_1400C0490 = 2;
  dword_1400C04A0 = 4;
  dword_1400C04A8 = 3;
  word_1400C0494 = 0;
  qword_1400C0498 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C04B0,
    "dc:title");
  dword_1400C04B8 = 2;
  word_1400C04BC = 0;
  dword_1400C04C0 = 0;
  qword_1400C04C4 = 1;
  dword_1400C04D0 = 4;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C04D8,
    "dc:creator");
  dword_1400C04E0 = 2;
  dword_1400C04F8 = 5;
  word_1400C04E4 = 0;
  dword_1400C04E8 = 0;
  qword_1400C04EC = 2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0500,
    "res");
  dword_1400C0508 = 2;
  word_1400C050C = 1;
  dword_1400C0510 = 0;
  qword_1400C0514 = 3;
  dword_1400C0520 = 6;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0528,
    "res@size");
  dword_1400C0530 = 4;
  word_1400C0534 = 0;
  dword_1400C0540 = 7;
  dword_1400C0548 = 7;
  dword_1400C0538 = 0;
  dword_1400C053C = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0550,
    "res@duration");
  dword_1400C0558 = 2;
  dword_1400C0568 = 8;
  dword_1400C0570 = 8;
  word_1400C055C = 0;
  dword_1400C0560 = 0;
  dword_1400C0564 = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0578,
    "res@bitrate");
  dword_1400C0580 = 3;
  word_1400C0584 = 0;
  dword_1400C0588 = 0;
  dword_1400C0590 = 9;
  dword_1400C0598 = 9;
  dword_1400C058C = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C05A0,
    "res@resolution");
  dword_1400C05A8 = 2;
  dword_1400C05B8 = 10;
  dword_1400C05C0 = 10;
  word_1400C05AC = 0;
  dword_1400C05B0 = 0;
  dword_1400C05B4 = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C05C8,
    "res@protocolInfo");
  word_1400C05D4 = 0;
  dword_1400C05D8 = 0;
  dword_1400C05D0 = 2;
  dword_1400C05E0 = 11;
  dword_1400C05E8 = 11;
  dword_1400C05DC = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C05F0,
    "res@protection");
  dword_1400C05F8 = 2;
  dword_1400C0608 = 12;
  word_1400C05FC = 0;
  dword_1400C0600 = 0;
  dword_1400C0610 = 12;
  dword_1400C0604 = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0618,
    "res@sampleFrequency");
  dword_1400C0620 = 3;
  dword_1400C0630 = 13;
  dword_1400C0638 = 13;
  word_1400C0624 = 0;
  dword_1400C0628 = 0;
  dword_1400C062C = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0640,
    "res@bitsPerSample");
  dword_1400C0648 = 3;
  dword_1400C0658 = 14;
  dword_1400C0660 = 14;
  word_1400C064C = 0;
  dword_1400C0650 = 0;
  dword_1400C0654 = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0668,
    "res@nrAudioChannels");
  word_1400C0674 = 0;
  dword_1400C0678 = 0;
  dword_1400C0670 = 3;
  dword_1400C0680 = 15;
  dword_1400C0688 = 15;
  dword_1400C067C = 3;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0690,
    "res@colorDepth");
  dword_1400C0698 = 3;
  dword_1400C06A4 = 3;
  word_1400C069C = 0;
  dword_1400C06A0 = 0;
  dword_1400C06A8 = 16;
  dword_1400C06B0 = 16;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C06B8,
    "res@microsoft:codec");
  dword_1400C06C0 = 2;
  dword_1400C06CC = 3;
  word_1400C06C4 = 0;
  dword_1400C06C8 = 0;
  dword_1400C06D0 = 18;
  dword_1400C06D8 = 17;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C06E0,
    "upnp:class");
  dword_1400C06E8 = 2;
  word_1400C06EC = 0;
  dword_1400C06F0 = 0;
  qword_1400C06F4 = 4;
  dword_1400C0700 = 18;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0708,
    "upnp:class@name");
  dword_1400C0710 = 2;
  word_1400C0714 = 0;
  dword_1400C0718 = 0;
  dword_1400C071C = 4;
  dword_1400C0720 = 20;
  dword_1400C0728 = 19;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0730,
    "@restricted");
  dword_1400C0738 = 1;
  word_1400C073C = 0;
  qword_1400C0740 = 0;
  dword_1400C0748 = 5;
  dword_1400C0750 = 20;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0758,
    "upnp:writeStatus");
  qword_1400C076C = 5;
  word_1400C0764 = 0;
  dword_1400C0768 = 0;
  dword_1400C0778 = 21;
  dword_1400C0760 = 2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0780,
    "@parentID");
  dword_1400C0788 = 2;
  word_1400C078C = 0;
  qword_1400C0790 = 0;
  dword_1400C0798 = 3;
  dword_1400C07A0 = 22;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C07A8,
    "upnp:genre");
  dword_1400C07B0 = 2;
  dword_1400C07B8 = 0;
  word_1400C07B4 = 1;
  qword_1400C07BC = 6;
  dword_1400C07C8 = 23;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C07D0,
    "dc:publisher");
  dword_1400C07D8 = 2;
  dword_1400C07E0 = 0;
  word_1400C07DC = 1;
  qword_1400C07E4 = 7;
  dword_1400C07F0 = 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C07F8,
    "dc:language");
  qword_1400C080C = 8;
  word_1400C0804 = 0;
  dword_1400C0808 = 0;
  dword_1400C0800 = 2;
  dword_1400C0818 = 25;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0820,
    "dc:rights");
  qword_1400C0834 = 9;
  dword_1400C0830 = 0;
  dword_1400C0828 = 2;
  word_1400C082C = 1;
  dword_1400C0840 = 26;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0848,
    "upnp:artist");
  dword_1400C0850 = 2;
  word_1400C0854 = 1;
  dword_1400C0858 = 0;
  qword_1400C085C = 10;
  dword_1400C0868 = 27;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0870,
    "upnp:artist@role");
  dword_1400C0878 = 2;
  word_1400C087C = 0;
  dword_1400C0880 = 0;
  dword_1400C0884 = 10;
  dword_1400C0888 = 21;
  dword_1400C0890 = 28;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0898,
    "upnp:author");
  dword_1400C08A0 = 2;
  word_1400C08A4 = 1;
  dword_1400C08A8 = 0;
  qword_1400C08AC = 11;
  dword_1400C08B8 = 29;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C08C0,
    "upnp:author@role");
  dword_1400C08C8 = 2;
  word_1400C08CC = 0;
  dword_1400C08D0 = 0;
  dword_1400C08D4 = 11;
  dword_1400C08D8 = 21;
  dword_1400C08E0 = 30;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C08E8,
    "upnp:album");
  dword_1400C08F0 = 2;
  word_1400C08F4 = 1;
  dword_1400C08F8 = 0;
  qword_1400C08FC = 12;
  dword_1400C0908 = 31;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0910,
    "upnp:originalTrackNumber");
  word_1400C091C = 0;
  dword_1400C0918 = 3;
  dword_1400C0920 = 0;
  qword_1400C0924 = 13;
  dword_1400C0930 = 32;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0938,
    "dc:date");
  dword_1400C0940 = 2;
  word_1400C0944 = 0;
  dword_1400C0948 = 0;
  qword_1400C094C = 14;
  dword_1400C0958 = 33;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0960,
    "upnp:producer");
  dword_1400C0968 = 2;
  word_1400C096C = 1;
  dword_1400C0970 = 0;
  qword_1400C0974 = 15;
  dword_1400C0980 = 34;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0988,
    "upnp:rating");
  qword_1400C099C = 16;
  dword_1400C0990 = 2;
  word_1400C0994 = 0;
  dword_1400C0998 = 0;
  dword_1400C09A8 = 35;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C09B0,
    "upnp:actor");
  dword_1400C09B8 = 2;
  qword_1400C09C4 = 17;
  word_1400C09BC = 1;
  dword_1400C09C0 = 0;
  dword_1400C09D0 = 36;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C09D8,
    "upnp:actor@role");
  dword_1400C09E0 = 2;
  word_1400C09E4 = 0;
  dword_1400C09F0 = 21;
  dword_1400C09E8 = 0;
  dword_1400C09EC = 17;
  dword_1400C09F8 = 37;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0A00,
    "upnp:director");
  dword_1400C0A08 = 2;
  word_1400C0A0C = 1;
  dword_1400C0A10 = 0;
  qword_1400C0A14 = 18;
  dword_1400C0A20 = 38;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0A28,
    "@childCount");
  dword_1400C0A30 = 3;
  word_1400C0A34 = 0;
  qword_1400C0A38 = 0;
  dword_1400C0A40 = 6;
  dword_1400C0A48 = 39;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0A50,
    "upnp:createClass");
  dword_1400C0A58 = 2;
  word_1400C0A5C = 1;
  dword_1400C0A60 = 0;
  qword_1400C0A64 = 19;
  dword_1400C0A70 = 40;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0A78,
    "upnp:searchClass");
  dword_1400C0A80 = 2;
  qword_1400C0A8C = 20;
  word_1400C0A84 = 1;
  dword_1400C0A88 = 0;
  dword_1400C0A98 = 41;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0AA0,
    "upnp:searchClass@includeDerived");
  dword_1400C0AA8 = 1;
  dword_1400C0AB8 = 22;
  word_1400C0AAC = 0;
  dword_1400C0AB0 = 0;
  dword_1400C0AB4 = 20;
  dword_1400C0AC0 = 42;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0AC8,
    "upnp:searchClass@name");
  dword_1400C0AD0 = 2;
  dword_1400C0AE8 = 43;
  word_1400C0AD4 = 0;
  dword_1400C0AD8 = 0;
  dword_1400C0ADC = 20;
  dword_1400C0AE0 = 20;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0AF0,
    "@searchable");
  dword_1400C0AF8 = 1;
  dword_1400C0B10 = 44;
  word_1400C0AFC = 0;
  qword_1400C0B00 = 0;
  dword_1400C0B08 = 2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0B18,
    "upnp:storageTotal");
  word_1400C0B24 = 0;
  dword_1400C0B20 = 4;
  dword_1400C0B28 = 0;
  qword_1400C0B2C = 21;
  dword_1400C0B38 = 45;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0B40,
    "upnp:storageUsed");
  dword_1400C0B48 = 4;
  word_1400C0B4C = 0;
  dword_1400C0B50 = 0;
  qword_1400C0B54 = 22;
  dword_1400C0B60 = 46;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0B68,
    "upnp:storageFree");
  dword_1400C0B70 = 4;
  dword_1400C0B88 = 47;
  word_1400C0B74 = 0;
  dword_1400C0B78 = 0;
  qword_1400C0B7C = 23;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0B90,
    "upnp:storageMaxPartition");
  dword_1400C0B98 = 4;
  dword_1400C0BB0 = 48;
  word_1400C0B9C = 0;
  dword_1400C0BA0 = 0;
  qword_1400C0BA4 = 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0BB8,
    "upnp:storageMedium");
  dword_1400C0BC0 = 2;
  dword_1400C0BD8 = 49;
  word_1400C0BC4 = 0;
  dword_1400C0BC8 = 0;
  qword_1400C0BCC = 25;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0BE0,
    "upnp:toc");
  dword_1400C0BE8 = 2;
  dword_1400C0C00 = 50;
  word_1400C0BEC = 0;
  dword_1400C0BF0 = 0;
  qword_1400C0BF4 = 26;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0C08,
    "upnp:channelName");
  qword_1400C0C1C = 43;
  dword_1400C0C10 = 2;
  dword_1400C0C28 = 51;
  word_1400C0C14 = 0;
  dword_1400C0C18 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0C30,
    "upnp:scheduledStartTime");
  qword_1400C0C44 = 44;
  dword_1400C0C38 = 2;
  dword_1400C0C50 = 52;
  word_1400C0C3C = 1;
  dword_1400C0C40 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0C58,
    "microsoft:year");
  dword_1400C0C60 = 3;
  qword_1400C0C6C = 48;
  word_1400C0C64 = 0;
  dword_1400C0C78 = 53;
  dword_1400C0C68 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0C80,
    "microsoft:userRatingInStars");
  qword_1400C0C94 = 49;
  dword_1400C0C88 = 2;
  dword_1400C0CA0 = 54;
  word_1400C0C8C = 0;
  dword_1400C0C90 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0CA8,
    "microsoft:userEffectiveRatingInStars");
  qword_1400C0CBC = 50;
  dword_1400C0CB0 = 2;
  dword_1400C0CC8 = 55;
  word_1400C0CB4 = 0;
  dword_1400C0CB8 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0CD0,
    "microsoft:userRating");
  qword_1400C0CE4 = 51;
  dword_1400C0CD8 = 2;
  dword_1400C0CF0 = 56;
  word_1400C0CDC = 0;
  dword_1400C0CE0 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0CF8,
    "microsoft:userEffectiveRating");
  qword_1400C0D0C = 52;
  dword_1400C0D00 = 2;
  dword_1400C0D18 = 57;
  word_1400C0D04 = 0;
  dword_1400C0D08 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0D20,
    "microsoft:serviceProvider");
  qword_1400C0D34 = 53;
  dword_1400C0D28 = 2;
  dword_1400C0D40 = 58;
  word_1400C0D2C = 0;
  dword_1400C0D30 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0D48,
    "microsoft:artistAlbumArtist");
  word_1400C0D54 = 0;
  dword_1400C0D58 = 0;
  dword_1400C0D50 = 2;
  dword_1400C0D68 = 59;
  qword_1400C0D5C = 54;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0D70,
    "microsoft:artistPerformer");
  qword_1400C0D84 = 55;
  dword_1400C0D78 = 2;
  word_1400C0D7C = 0;
  dword_1400C0D90 = 60;
  dword_1400C0D80 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0D98,
    "microsoft:artistConductor");
  dword_1400C0DA0 = 2;
  word_1400C0DA4 = 0;
  dword_1400C0DB8 = 61;
  dword_1400C0DA8 = 0;
  qword_1400C0DAC = 56;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0DC0,
    "microsoft:authorComposer");
  qword_1400C0DD4 = 57;
  dword_1400C0DC8 = 2;
  dword_1400C0DE0 = 62;
  word_1400C0DCC = 0;
  dword_1400C0DD0 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0DE8,
    "microsoft:authorOriginalLyricist");
  word_1400C0DF4 = 0;
  dword_1400C0DF8 = 0;
  dword_1400C0DF0 = 2;
  dword_1400C0E08 = 63;
  qword_1400C0DFC = 58;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0E10,
    "microsoft:authorWriter");
  dword_1400C0E18 = 2;
  qword_1400C0E24 = 59;
  word_1400C0E1C = 0;
  dword_1400C0E20 = 0;
  dword_1400C0E30 = 64;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0E38,
    "microsoft:sourceUrl");
  word_1400C0E44 = 0;
  dword_1400C0E48 = 0;
  qword_1400C0E4C = 47;
  dword_1400C0E58 = 65;
  dword_1400C0E40 = 2;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0E60,
    "microsoft:folderPath");
  dword_1400C0E68 = 2;
  word_1400C0E6C = 0;
  dword_1400C0E70 = 0;
  qword_1400C0E74 = 60;
  dword_1400C0E80 = 66;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0E88,
    "microsoft:playOrder");
  dword_1400C0E90 = 2;
  word_1400C0E94 = 0;
  dword_1400C0E98 = 0;
  qword_1400C0E9C = 63;
  dword_1400C0EA8 = 67;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0EB0,
    "microsoft:fileIdentifier");
  dword_1400C0EB8 = 2;
  word_1400C0EBC = 0;
  dword_1400C0EC0 = 0;
  qword_1400C0EC4 = 64;
  dword_1400C0ED0 = 68;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0ED8,
    "dc:description");
  dword_1400C0EE0 = 2;
  word_1400C0EE4 = 0;
  dword_1400C0EE8 = 0;
  qword_1400C0EEC = 27;
  dword_1400C0EF8 = 69;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0F00,
    "upnp:longDescription");
  dword_1400C0F08 = 2;
  word_1400C0F0C = 0;
  dword_1400C0F10 = 0;
  qword_1400C0F14 = 28;
  dword_1400C0F20 = 70;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0F28,
    "dc:contributor");
  dword_1400C0F30 = 2;
  word_1400C0F34 = 1;
  dword_1400C0F38 = 0;
  qword_1400C0F3C = 32;
  dword_1400C0F48 = 71;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0F50,
    "upnp:albumArtURI");
  dword_1400C0F58 = 2;
  qword_1400C0F64 = 29;
  word_1400C0F5C = 1;
  dword_1400C0F60 = 0;
  dword_1400C0F70 = 72;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0F78,
    "upnp:albumArtURI@dlna:profileID");
  dword_1400C0F80 = 2;
  word_1400C0F84 = 0;
  dword_1400C0F88 = 0;
  dword_1400C0F8C = 29;
  dword_1400C0F90 = 25;
  dword_1400C0F98 = 73;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0FA0,
    "upnp:userAnnotation");
  dword_1400C0FA8 = 2;
  word_1400C0FAC = 1;
  dword_1400C0FB0 = 0;
  qword_1400C0FB4 = 30;
  dword_1400C0FC0 = 74;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0FC8,
    "res@dlna:ifoFileURI");
  dword_1400C0FD0 = 2;
  dword_1400C0FDC = 3;
  word_1400C0FD4 = 0;
  dword_1400C0FD8 = 0;
  dword_1400C0FE0 = 26;
  dword_1400C0FE8 = 75;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C0FF0,
    "upnp:seriesTitle");
  dword_1400C0FF8 = 2;
  word_1400C0FFC = 0;
  dword_1400C1000 = 0;
  qword_1400C1004 = 61;
  dword_1400C1010 = 76;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1018,
    "upnp:programTitle");
  dword_1400C1020 = 2;
  word_1400C1024 = 0;
  dword_1400C1028 = 0;
  qword_1400C102C = 62;
  dword_1400C1038 = 77;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1040,
    "upnp:episodeNumber");
  dword_1400C1048 = 3;
  word_1400C104C = 0;
  dword_1400C1050 = 0;
  qword_1400C1054 = 65;
  dword_1400C1060 = 78;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1068,
    "desc");
  dword_1400C1070 = 2;
  qword_1400C107C = 31;
  word_1400C1074 = 1;
  dword_1400C1078 = 0;
  dword_1400C1088 = 79;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1090,
    "desc@id");
  dword_1400C1098 = 2;
  word_1400C109C = 0;
  dword_1400C10A0 = 0;
  dword_1400C10A4 = 31;
  dword_1400C10A8 = 1;
  dword_1400C10B0 = 80;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C10B8,
    "desc@type");
  dword_1400C10C0 = 2;
  word_1400C10C4 = 0;
  dword_1400C10C8 = 0;
  dword_1400C10CC = 31;
  dword_1400C10D0 = 24;
  dword_1400C10D8 = 81;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C10E0,
    "res@av:imageConvertBGColor");
  dword_1400C10E8 = 2;
  dword_1400C10F4 = -1;
  dword_1400C10F8 = -1;
  word_1400C10EC = 0;
  dword_1400C10F0 = 0;
  dword_1400C1100 = 82;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1108,
    "res@av:imageConvertMode");
  dword_1400C1110 = 2;
  word_1400C1114 = 0;
  dword_1400C1118 = 0;
  dword_1400C111C = -1;
  dword_1400C1120 = -1;
  dword_1400C1128 = 83;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(
    &qword_1400C1130,
    "res@av:pixelAspectRatio");
  dword_1400C1138 = 2;
  word_1400C113C = 0;
  dword_1400C1140 = 0;
  dword_1400C1144 = -1;
  dword_1400C1148 = -1;
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__CdsValues::s_valueInfoList__);
}

```

## disassembly

```asm
0x1400332a0  push    rbx
0x1400332a2  push    rbp
0x1400332a3  push    rsi
0x1400332a4  push    rdi
0x1400332a5  push    r12
0x1400332a7  push    r13
0x1400332a9  push    r14
0x1400332ab  push    r15
0x1400332ad  sub     rsp, 28h
0x1400332b1  lea     rdx, byte_1400A4F8D
0x1400332b8  lea     rcx, qword_1400C0438
0x1400332bf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400332c4  or      eax, 0FFFFFFFFh
0x1400332c7  lea     rdx, aId_1; "@id"
0x1400332ce  xor     r13d, r13d
0x1400332d1  mov     cs:dword_1400C044C, eax
0x1400332d7  lea     rcx, qword_1400C0460
0x1400332de  mov     cs:dword_1400C0440, r13d
0x1400332e5  mov     cs:word_1400C0444, r13w
0x1400332ed  lea     esi, [rax+2]
0x1400332f0  mov     cs:dword_1400C0448, r13d
0x1400332f7  mov     cs:dword_1400C0458, esi
0x1400332fd  mov     cs:dword_1400C0450, eax
0x140033303  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033308  lea     r12d, [r13+2]
0x14003330c  mov     cs:word_1400C046C, r13w
0x140033314  lea     rdx, aRefid; "@refID"
0x14003331b  mov     cs:dword_1400C0468, r12d
0x140033322  lea     rcx, qword_1400C0488
0x140033329  mov     cs:dword_1400C0480, r12d
0x140033330  mov     cs:qword_1400C0470, r13
0x140033337  mov     cs:dword_1400C0478, esi
0x14003333d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033342  lea     edi, [rsi+3]
0x140033345  mov     cs:dword_1400C0490, r12d
0x14003334c  lea     r15d, [r13+3]
0x140033350  mov     cs:dword_1400C04A0, edi
0x140033356  lea     rdx, aDcTitle; "dc:title"
0x14003335d  mov     cs:dword_1400C04A8, r15d
0x140033364  lea     rcx, qword_1400C04B0
0x14003336b  mov     cs:word_1400C0494, r13w
0x140033373  mov     cs:qword_1400C0498, r13
0x14003337a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14003337f  lea     rdx, aDcCreator; "dc:creator"
0x140033386  mov     cs:dword_1400C04B8, r12d
0x14003338d  lea     rcx, qword_1400C04D8
0x140033394  mov     cs:word_1400C04BC, r13w
0x14003339c  mov     cs:dword_1400C04C0, r13d
0x1400333a3  mov     cs:qword_1400C04C4, rsi
0x1400333aa  mov     cs:dword_1400C04D0, edi
0x1400333b0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400333b5  lea     ebx, [rsi+4]
0x1400333b8  mov     cs:dword_1400C04E0, r12d
0x1400333bf  lea     rdx, aRes; "res"
0x1400333c6  mov     cs:dword_1400C04F8, ebx
0x1400333cc  lea     rcx, qword_1400C0500
0x1400333d3  mov     cs:word_1400C04E4, r13w
0x1400333db  mov     cs:dword_1400C04E8, r13d
0x1400333e2  mov     cs:qword_1400C04EC, r12
0x1400333e9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400333ee  lea     rdx, aResSize; "res@size"
0x1400333f5  mov     cs:dword_1400C0508, r12d
0x1400333fc  lea     rcx, qword_1400C0528
0x140033403  mov     cs:word_1400C050C, si
0x14003340a  mov     cs:dword_1400C0510, r13d
0x140033411  mov     cs:qword_1400C0514, r15
0x140033418  mov     cs:dword_1400C0520, 6
0x140033422  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033427  mov     cs:dword_1400C0530, edi
0x14003342d  lea     rdx, aResDuration; "res@duration"
0x140033434  lea     edi, [rsi+6]
0x140033437  mov     cs:word_1400C0534, r13w
0x14003343f  lea     rcx, qword_1400C0550
0x140033446  mov     cs:dword_1400C0540, edi
0x14003344c  mov     cs:dword_1400C0548, edi
0x140033452  mov     cs:dword_1400C0538, r13d
0x140033459  mov     cs:dword_1400C053C, r15d
0x140033460  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033465  lea     esi, [rbx+3]
0x140033468  mov     cs:dword_1400C0558, r12d
0x14003346f  lea     rdx, aResBitrate; "res@bitrate"
0x140033476  mov     cs:dword_1400C0568, esi
0x14003347c  lea     rcx, qword_1400C0578
0x140033483  mov     cs:dword_1400C0570, esi
0x140033489  mov     cs:word_1400C055C, r13w
0x140033491  mov     cs:dword_1400C0560, r13d
0x140033498  mov     cs:dword_1400C0564, r15d
0x14003349f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400334a4  mov     cs:dword_1400C0580, r15d
0x1400334ab  mov     cs:word_1400C0584, r13w
0x1400334b3  lea     ebp, [rbx+4]
0x1400334b6  mov     cs:dword_1400C0588, r13d
0x1400334bd  lea     rdx, aResResolution; "res@resolution"
0x1400334c4  mov     cs:dword_1400C0590, ebp
0x1400334ca  lea     rcx, qword_1400C05A0
0x1400334d1  mov     cs:dword_1400C0598, ebp
0x1400334d7  mov     cs:dword_1400C058C, r15d
0x1400334de  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400334e3  lea     r14d, [r13+0Ah]
0x1400334e7  mov     cs:dword_1400C05A8, r12d
0x1400334ee  lea     rdx, aResProtocolinf; "res@protocolInfo"
0x1400334f5  mov     cs:dword_1400C05B8, r14d
0x1400334fc  lea     rcx, qword_1400C05C8
0x140033503  mov     cs:dword_1400C05C0, r14d
0x14003350a  mov     cs:word_1400C05AC, r13w
0x140033512  mov     cs:dword_1400C05B0, r13d
0x140033519  mov     cs:dword_1400C05B4, r15d
0x140033520  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033525  mov     cs:word_1400C05D4, r13w
0x14003352d  lea     rdx, aResProtection; "res@protection"
0x140033534  mov     cs:dword_1400C05D8, r13d
0x14003353b  lea     rcx, qword_1400C05F0
0x140033542  lea     r13d, [r12+9]
0x140033547  mov     cs:dword_1400C05D0, r12d
0x14003354e  mov     cs:dword_1400C05E0, r13d
0x140033555  mov     cs:dword_1400C05E8, r13d
0x14003355c  mov     cs:dword_1400C05DC, r15d
0x140033563  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033568  lea     eax, [rbx+7]
0x14003356b  mov     cs:dword_1400C05F8, r12d
0x140033572  xor     r12d, r12d
0x140033575  mov     cs:dword_1400C0608, eax
0x14003357b  lea     rdx, aResSamplefrequ; "res@sampleFrequency"
0x140033582  mov     cs:word_1400C05FC, r12w
0x14003358a  lea     rcx, qword_1400C0618
0x140033591  mov     cs:dword_1400C0600, r12d
0x140033598  mov     cs:dword_1400C0610, eax
0x14003359e  mov     cs:dword_1400C0604, r15d
0x1400335a5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400335aa  lea     eax, [rbx+8]
0x1400335ad  mov     cs:dword_1400C0620, r15d
0x1400335b4  lea     rdx, aResBitspersamp; "res@bitsPerSample"
0x1400335bb  mov     cs:dword_1400C0630, eax
0x1400335c1  lea     rcx, qword_1400C0640
0x1400335c8  mov     cs:dword_1400C0638, eax
0x1400335ce  mov     cs:word_1400C0624, r12w
0x1400335d6  mov     cs:dword_1400C0628, r12d
0x1400335dd  mov     cs:dword_1400C062C, r15d
0x1400335e4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400335e9  lea     eax, [rbx+9]
0x1400335ec  mov     cs:dword_1400C0648, r15d
0x1400335f3  lea     rdx, aResNraudiochan; "res@nrAudioChannels"
0x1400335fa  mov     cs:dword_1400C0658, eax
0x140033600  lea     rcx, qword_1400C0668
0x140033607  mov     cs:dword_1400C0660, eax
0x14003360d  mov     cs:word_1400C064C, r12w
0x140033615  mov     cs:dword_1400C0650, r12d
0x14003361c  mov     cs:dword_1400C0654, r15d
0x140033623  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033628  mov     cs:word_1400C0674, r12w
0x140033630  lea     rdx, aResColordepth; "res@colorDepth"
0x140033637  mov     cs:dword_1400C0678, r12d
0x14003363e  lea     rcx, qword_1400C0690
0x140033645  lea     r12d, [r15+0Ch]
0x140033649  mov     cs:dword_1400C0670, r15d
0x140033650  mov     cs:dword_1400C0680, r12d
0x140033657  mov     cs:dword_1400C0688, r12d
0x14003365e  mov     cs:dword_1400C067C, r15d
0x140033665  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14003366a  xor     eax, eax
0x14003366c  mov     cs:dword_1400C0698, r15d
0x140033673  mov     cs:dword_1400C06A4, r15d
0x14003367a  lea     rdx, aResMicrosoftCo; "res@microsoft:codec"
0x140033681  lea     r15d, [rbx+0Bh]
0x140033685  mov     cs:word_1400C069C, ax
0x14003368c  lea     rcx, qword_1400C06B8
0x140033693  mov     cs:dword_1400C06A0, eax
0x140033699  mov     cs:dword_1400C06A8, r15d
0x1400336a0  mov     cs:dword_1400C06B0, r15d
0x1400336a7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400336ac  mov     cs:dword_1400C06C0, 2
0x1400336b6  xor     eax, eax
0x1400336b8  mov     cs:dword_1400C06CC, 3
0x1400336c2  lea     rdx, aUpnpClass; "upnp:class"
0x1400336c9  mov     cs:word_1400C06C4, ax
0x1400336d0  lea     rcx, qword_1400C06E0
0x1400336d7  mov     cs:dword_1400C06C8, eax
0x1400336dd  mov     cs:dword_1400C06D0, 12h
0x1400336e7  mov     cs:dword_1400C06D8, 11h
0x1400336f1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400336f6  xor     eax, eax
0x1400336f8  mov     cs:dword_1400C06E8, 2
0x140033702  lea     rdx, aUpnpClassName; "upnp:class@name"
0x140033709  mov     cs:word_1400C06EC, ax
0x140033710  lea     rcx, qword_1400C0708
0x140033717  mov     cs:dword_1400C06F0, eax
0x14003371d  mov     cs:qword_1400C06F4, 4
0x140033728  mov     cs:dword_1400C0700, 12h
0x140033732  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033737  xor     eax, eax
0x140033739  mov     cs:dword_1400C0710, 2
0x140033743  lea     rdx, aRestricted; "@restricted"
0x14003374a  mov     cs:word_1400C0714, ax
0x140033751  lea     rcx, qword_1400C0730
0x140033758  mov     cs:dword_1400C0718, eax
0x14003375e  mov     cs:dword_1400C071C, 4
0x140033768  mov     cs:dword_1400C0720, 14h
0x140033772  mov     cs:dword_1400C0728, 13h
0x14003377c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033781  xor     eax, eax
0x140033783  mov     cs:dword_1400C0738, 1
0x14003378d  lea     rdx, aUpnpWritestatu; "upnp:writeStatus"
0x140033794  mov     cs:word_1400C073C, ax
0x14003379b  lea     rcx, qword_1400C0758
0x1400337a2  mov     cs:qword_1400C0740, rax
0x1400337a9  mov     cs:dword_1400C0748, ebx
0x1400337af  mov     cs:dword_1400C0750, 14h
0x1400337b9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400337be  xor     eax, eax
0x1400337c0  mov     cs:qword_1400C076C, rbx
0x1400337c7  lea     ebx, [rdi+0Eh]
0x1400337ca  mov     cs:word_1400C0764, ax
0x1400337d1  lea     rdx, aParentid_0; "@parentID"
0x1400337d8  mov     cs:dword_1400C0768, eax
0x1400337de  lea     rcx, qword_1400C0780
0x1400337e5  mov     cs:dword_1400C0778, ebx
0x1400337eb  mov     cs:dword_1400C0760, 2
0x1400337f5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400337fa  xor     eax, eax
0x1400337fc  mov     cs:dword_1400C0788, 2
0x140033806  lea     rdx, aUpnpGenre; "upnp:genre"
0x14003380d  mov     cs:word_1400C078C, ax
0x140033814  lea     rcx, qword_1400C07A8
0x14003381b  mov     cs:qword_1400C0790, rax
0x140033822  mov     cs:dword_1400C0798, 3
0x14003382c  mov     cs:dword_1400C07A0, 16h
0x140033836  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14003383b  xor     eax, eax
0x14003383d  mov     cs:dword_1400C07B0, 2
0x140033847  lea     rdx, aDcPublisher; "dc:publisher"
0x14003384e  mov     cs:dword_1400C07B8, eax
0x140033854  lea     rcx, qword_1400C07D0
0x14003385b  mov     cs:word_1400C07B4, 1
0x140033864  mov     cs:qword_1400C07BC, 6
0x14003386f  mov     cs:dword_1400C07C8, 17h
0x140033879  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14003387e  xor     eax, eax
0x140033880  mov     cs:dword_1400C07D8, 2
0x14003388a  lea     rdx, aDcLanguage; "dc:language"
0x140033891  mov     cs:dword_1400C07E0, eax
0x140033897  lea     rcx, qword_1400C07F8
0x14003389e  mov     cs:word_1400C07DC, 1
0x1400338a7  mov     cs:qword_1400C07E4, rdi
0x1400338ae  mov     cs:dword_1400C07F0, 18h
0x1400338b8  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400338bd  xor     eax, eax
0x1400338bf  mov     cs:qword_1400C080C, rsi
0x1400338c6  lea     edi, [rsi-6]
0x1400338c9  mov     cs:word_1400C0804, ax
0x1400338d0  mov     cs:dword_1400C0808, eax
0x1400338d6  mov     cs:dword_1400C0800, edi
0x1400338dc  mov     cs:dword_1400C0818, 19h
0x1400338e6  lea     rdx, aDcRights; "dc:rights"
0x1400338ed  lea     rcx, qword_1400C0820
0x1400338f4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400338f9  xor     eax, eax
0x1400338fb  mov     cs:qword_1400C0834, rbp
0x140033902  lea     rdx, aUpnpArtist; "upnp:artist"
0x140033909  mov     cs:dword_1400C0830, eax
0x14003390f  lea     rcx, qword_1400C0848
0x140033916  mov     cs:dword_1400C0828, edi
0x14003391c  mov     cs:word_1400C082C, 1
0x140033925  xor     ebp, ebp
0x140033927  mov     cs:dword_1400C0840, 1Ah
0x140033931  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033936  lea     rdx, aUpnpArtistRole; "upnp:artist@role"
0x14003393d  mov     cs:dword_1400C0850, edi
0x140033943  lea     rcx, qword_1400C0870
0x14003394a  mov     cs:word_1400C0854, 1
0x140033953  mov     cs:dword_1400C0858, ebp
0x140033959  mov     cs:qword_1400C085C, r14
0x140033960  mov     cs:dword_1400C0868, 1Bh
0x14003396a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x14003396f  lea     rdx, aUpnpAuthor; "upnp:author"
0x140033976  mov     cs:dword_1400C0878, edi
0x14003397c  lea     rcx, qword_1400C0898
0x140033983  mov     cs:word_1400C087C, bp
0x14003398a  mov     cs:dword_1400C0880, ebp
0x140033990  mov     cs:dword_1400C0884, r14d
0x140033997  mov     cs:dword_1400C0888, ebx
0x14003399d  mov     cs:dword_1400C0890, 1Ch
0x1400339a7  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400339ac  lea     rdx, aUpnpAuthorRole; "upnp:author@role"
0x1400339b3  mov     cs:dword_1400C08A0, edi
0x1400339b9  lea     rcx, qword_1400C08C0
0x1400339c0  mov     cs:word_1400C08A4, 1
0x1400339c9  mov     cs:dword_1400C08A8, ebp
0x1400339cf  mov     cs:qword_1400C08AC, r13
0x1400339d6  mov     cs:dword_1400C08B8, 1Dh
0x1400339e0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x1400339e5  lea     rdx, aUpnpAlbum; "upnp:album"
0x1400339ec  mov     cs:dword_1400C08C8, edi
0x1400339f2  lea     rcx, qword_1400C08E8
0x1400339f9  mov     cs:word_1400C08CC, bp
0x140033a00  mov     cs:dword_1400C08D0, ebp
0x140033a06  mov     cs:dword_1400C08D4, r13d
0x140033a0d  mov     cs:dword_1400C08D8, ebx
0x140033a13  mov     cs:dword_1400C08E0, 1Eh
0x140033a1d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(char const *)
0x140033a22  lea     rdx, aUpnpOriginaltr; "upnp:originalTrackNumber"
  ... truncated ...
```
