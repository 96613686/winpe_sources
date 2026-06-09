# CDecoder::CDecoder(CHeap *,CEngine *)

- ea: `0x1800649bc`
- end: `0x1800651af`
- name: `??0CDecoder@@QEAA@PEAVCHeap@@PEAVCEngine@@@Z`
- size: `2035`
- prototype: `CDecoder *__fastcall(CDecoder *this, struct CHeap *, struct CEngine *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b04a4`

## callees

- `0x1800035b0`
- `0x180064974`
- `0x1800649bc`
- `0x1800651b8`
- `0x180081534`
- `0x1800815c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800650f6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065103`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800650f6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180065103`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006516a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18006516a`

## pseudocode

```c
CDecoder *__fastcall CDecoder::CDecoder(CDecoder *this, struct CHeap *a2, struct CEngine *a3)
{
  __int64 i; // rax
  __int64 j; // rbx
  cfData *v8; // rax
  __int64 v9; // rcx
  __int64 k; // rax
  _BYTE v12[232]; // [rsp+30h] [rbp-E8h] BYREF

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_DWORD *)this + 10) = 0;
  NGTreeProbCacheSize<64>::NGTreeProbCacheSize<64>((char *)this + 680);
  *((_QWORD *)this + 292) = a2;
  *((_QWORD *)this + 293) = 0;
  *((_QWORD *)this + 294) = 0;
  *((_QWORD *)this + 295) = a2;
  *((_QWORD *)this + 296) = 0;
  *((_QWORD *)this + 297) = 0;
  *((_QWORD *)this + 299) = a2;
  *((_QWORD *)this + 300) = 0;
  *((_QWORD *)this + 301) = 0;
  *((_QWORD *)this + 304) = a2;
  *((_QWORD *)this + 305) = 0;
  *((_QWORD *)this + 306) = 0;
  *((_QWORD *)this + 308) = a2;
  *((_QWORD *)this + 309) = 0;
  *((_QWORD *)this + 310) = 0;
  *((_QWORD *)this + 311) = a2;
  *((_QWORD *)this + 312) = 0;
  *((_QWORD *)this + 313) = 0;
  *((_QWORD *)this + 315) = a2;
  *((_QWORD *)this + 316) = 0;
  *((_QWORD *)this + 317) = 0;
  `eh vector constructor iterator'(
    (char *)this + 3568,
    0xB0u,
    0x10u,
    (void (*)(void *))cfData::cfData,
    (void (*)(void *))cfData::~cfData);
  RCDFanoutCache::RCDFanoutCache((CDecoder *)((char *)this + 6432), a2);
  *((_QWORD *)this + 813) = &g_heap;
  *((_QWORD *)this + 814) = 0;
  *((_QWORD *)this + 815) = 0;
  *((_QWORD *)this + 817) = &g_heap;
  *((_QWORD *)this + 818) = 0;
  *((_QWORD *)this + 819) = 0;
  *((_QWORD *)this + 821) = &g_heap;
  *((_QWORD *)this + 822) = 0;
  *((_QWORD *)this + 823) = 0;
  *((_QWORD *)this + 904) = a2;
  *((_QWORD *)this + 905) = 0;
  *((_QWORD *)this + 906) = 0;
  *((_QWORD *)this + 907) = a2;
  *((_QWORD *)this + 908) = 0;
  *((_QWORD *)this + 909) = 0;
  *((_QWORD *)this + 910) = 0;
  *((_QWORD *)this + 911) = 0;
  *((_QWORD *)this + 912) = 0;
  *((_QWORD *)this + 913) = 0;
  *((_DWORD *)this + 1828) = 0;
  *((_QWORD *)this + 918) = a2;
  *((_QWORD *)this + 919) = 0;
  *((_QWORD *)this + 920) = 0;
  `eh vector constructor iterator'(
    (char *)this + 7376,
    0x108u,
    1u,
    (void (*)(void *))CChannelPartition::CChannelPartition,
    (void (*)(void *))CChannelPartition::~CChannelPartition);
  *((_QWORD *)this + 921) = 0;
  *((_DWORD *)this + 134) = 0;
  *((_BYTE *)this + 540) = 0;
  *((_DWORD *)this + 136) = 0;
  *((_QWORD *)this + 9) = a2;
  *((_QWORD *)this + 10) = a3;
  *((_QWORD *)this + 288) = 0;
  *((_QWORD *)this + 289) = 0;
  *((_QWORD *)this + 286) = 0;
  *((_QWORD *)this + 287) = 0;
  *(_OWORD *)((char *)this + 6872) = 0;
  *((_QWORD *)this + 861) = 0;
  *((_DWORD *)this + 1722) = -1;
  *(_QWORD *)((char *)this + 7220) = 0;
  *((_DWORD *)this + 580) = 0;
  *((_DWORD *)this + 581) = 0x10000;
  *((_DWORD *)this + 582) = 0x10000;
  *((_DWORD *)this + 596) = 0;
  *((_DWORD *)this + 628) = 0;
  *((_DWORD *)this + 614) = 0;
  *((_DWORD *)this + 604) = 0;
  *((_DWORD *)this + 605) = -536870912;
  *((_DWORD *)this + 606) = -2;
  *((_QWORD *)this + 915) = 0;
  *((_QWORD *)this + 916) = 0;
  *((_DWORD *)this + 1834) = 0;
  *((_QWORD *)this + 320) = 0;
  *((_QWORD *)this + 323) = 0;
  *((_DWORD *)this + 1804) = 0;
  *((_DWORD *)this + 648) = 1;
  *((_BYTE *)this + 3024) = 0;
  *((_DWORD *)this + 636) = 0;
  *((_QWORD *)this + 357) = 0;
  *((_QWORD *)this + 358) = 0;
  for ( i = 0; i != 16; ++i )
  {
    *((_QWORD *)this + i + 830) = 0;
    *((_QWORD *)this + i + 341) = 0;
    *((_QWORD *)this + i + 862) = 0;
    *((_QWORD *)this + i + 878) = 0;
    *((_QWORD *)this + i + 325) = 0;
  }
  *((_QWORD *)this + 855) = 0;
  *((_BYTE *)this + 6832) = 0;
  *((_DWORD *)this + 1712) = 0;
  *((_QWORD *)this + 857) = 0;
  *((_BYTE *)this + 6864) = 0;
  *((_DWORD *)this + 1717) = -600809;
  *((_QWORD *)this + 359) = 0;
  *((_QWORD *)this + 361) = 0;
  *((_QWORD *)this + 360) = 0;
  *((_DWORD *)this + 743) = -2;
  *((_DWORD *)this + 724) = -2;
  *((_BYTE *)this + 2904) = 0;
  *((_BYTE *)this + 2976) = 1;
  for ( j = 0; j != 16; ++j )
  {
    *((_DWORD *)this + j + 727) = -2;
    v8 = cfData::cfData((cfData *)v12, a2);
    v9 = 176 * j;
    *(_OWORD *)((char *)this + v9 + 3568) = *(_OWORD *)v8;
    *(_OWORD *)((char *)this + v9 + 3584) = *((_OWORD *)v8 + 1);
    *(_OWORD *)((char *)this + v9 + 3600) = *((_OWORD *)v8 + 2);
    *(_OWORD *)((char *)this + v9 + 3616) = *((_OWORD *)v8 + 3);
    *(_OWORD *)((char *)this + v9 + 3632) = *((_OWORD *)v8 + 4);
    *(_OWORD *)((char *)this + v9 + 3648) = *((_OWORD *)v8 + 5);
    *(_OWORD *)((char *)this + v9 + 3664) = *((_OWORD *)v8 + 6);
    *(_OWORD *)((char *)this + v9 + 3680) = *((_OWORD *)v8 + 7);
    *(_OWORD *)((char *)this + v9 + 3696) = *((_OWORD *)v8 + 8);
    *(_OWORD *)((char *)this + v9 + 3712) = *((_OWORD *)v8 + 9);
    *(_OWORD *)((char *)this + v9 + 3728) = *((_OWORD *)v8 + 10);
    cfData::~cfData((cfData *)v12);
  }
  *((_BYTE *)this + 2977) = 0;
  *((_BYTE *)this + 2979) = 0;
  *((_DWORD *)this + 745) = 0;
  *((_WORD *)this + 1492) = 0;
  *((_BYTE *)this + 2987) = 0;
  *((_BYTE *)this + 2568) = 0;
  *((_QWORD *)this + 374) = 0;
  *(_QWORD *)((char *)this + 3028) = 0;
  *((_DWORD *)this + 1601) = 0;
  *((_QWORD *)this + 801) = 0;
  *((_QWORD *)this + 802) = 0;
  *((_DWORD *)this + 891) = 0;
  *((_DWORD *)this + 750) = 0;
  *((_WORD *)this + 278) = 0;
  *((_DWORD *)this + 751) = 1;
  *((_DWORD *)this + 752) = 2;
  *((_DWORD *)this + 1794) = 2;
  *((_DWORD *)this + 753) = 2;
  *((_DWORD *)this + 754) = 1065353216;
  *((_QWORD *)this + 901) = 0;
  *((_DWORD *)this + 761) = 0;
  *((_DWORD *)this + 1793) = 0;
  *(_QWORD *)((char *)this + 3052) = CAccuracyBeams::Beams50;
  *((_BYTE *)this + 70) = 0;
  *((_DWORD *)this + 12) = -1;
  *((_DWORD *)this + 13) = 100;
  *((_BYTE *)this + 56) = 0;
  *((_DWORD *)this + 15) = -1;
  *((_DWORD *)this + 16) = 1;
  *((_BYTE *)this + 518) = 0;
  *((_DWORD *)this + 759) = xmmword_1801509F8;
  *((_DWORD *)this + 760) = HIDWORD(CAccuracyBeams::Beams50);
  *((_QWORD *)this + 284) = *(_QWORD *)((char *)&xmmword_1801509F8 + 4);
  *((_OWORD *)this + 192) = CAccuracyBeams::Beams50;
  *((_OWORD *)this + 193) = xmmword_1801509F8;
  *(_OWORD *)((char *)this + 3100) = *(__int128 *)((char *)&xmmword_1801509F8 + 12);
  *(_OWORD *)((char *)this + 3116) = CAccuracyBeams::Beams100;
  *(_OWORD *)((char *)this + 3132) = xmmword_180150A28;
  *(_OWORD *)((char *)this + 3144) = *(__int128 *)((char *)&xmmword_180150A28 + 12);
  *((_BYTE *)this + 3252) = 0;
  *((_QWORD *)this + 409) = 0;
  *((_QWORD *)this + 408) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_DWORD *)this + 124) = 0;
  *((_DWORD *)this + 820) = 0;
  *((_DWORD *)this + 821) = 1065353216;
  *((_DWORD *)this + 823) = 1056964608;
  *((_DWORD *)this + 825) = dword_180150A08;
  *((_DWORD *)this + 826) = dword_180150A0C;
  *((_WORD *)this + 1716) = 0;
  *((_BYTE *)this + 3434) = 0;
  *((_DWORD *)this + 859) = 0;
  *((_QWORD *)this + 430) = 0;
  *((_QWORD *)this + 431) = 0;
  *((_QWORD *)this + 900) = 0;
  *((_QWORD *)this + 825) = 0;
  *((_OWORD *)this + 413) = 0;
  *((_OWORD *)this + 414) = 0;
  *((_QWORD *)this + 437) = 0;
  *((_QWORD *)this + 438) = 0;
  *((_BYTE *)this + 3512) = 0;
  *((_QWORD *)this + 441) = 0;
  *((_QWORD *)this + 442) = 0;
  *((_QWORD *)this + 443) = 0;
  *((_QWORD *)this + 440) = 0;
  *((_WORD *)this + 1776) = 0;
  *((_WORD *)this + 1648) = 0;
  *((_BYTE *)this + 7168) = 1;
  *((_DWORD *)this + 889) = 1;
  *((_DWORD *)this + 890) = 2;
  *((_DWORD *)this + 1598) = 25;
  *((_DWORD *)this + 1599) = 5;
  *((_BYTE *)this + 2978) = 0;
  *((_BYTE *)this + 3456) = -1;
  *((_BYTE *)this + 6400) = 0;
  *((_DWORD *)this + 873) = 0;
  *((_DWORD *)this + 870) = 276324;
  *((_DWORD *)this + 871) = -536870912;
  *((_DWORD *)this + 872) = -536870912;
  *((_QWORD *)this + 12) = 0;
  *((_DWORD *)this + 1911) = 70;
  *((_DWORD *)this + 1912) = 30;
  *((_DWORD *)this + 1913) = 20;
  *((_DWORD *)this + 1914) = -1082130432;
  *((_DWORD *)this + 1915) = -1082130432;
  *((_DWORD *)this + 1916) = 1112014848;
  *((_DWORD *)this + 1917) = 1112014848;
  for ( k = 0; k != 16; ++k )
  {
    *((_QWORD *)this + k + 13) = 0;
    *((_QWORD *)this + k + 29) = 0;
    *((_QWORD *)this + k + 45) = 0;
  }
  *((_QWORD *)this + 65) = 0;
  *((_QWORD *)this + 66) = 0;
  CoCreateGuid((GUID *)this + 35);
  CoCreateGuid((GUID *)this + 36);
  *((_QWORD *)this + 407) = 0;
  *((_WORD *)this + 256) = 0;
  *((_WORD *)this + 257) = 0;
  *((_WORD *)this + 258) = 0;
  *((_BYTE *)this + 6388) = 0;
  *((_DWORD *)this + 1596) = 0;
  *((_DWORD *)this + 148) = 0;
  *((_DWORD *)this + 637) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_BYTE *)this + 2256) = 0;
  *((_DWORD *)this + 565) = 1;
  *((_QWORD *)this + 283) = 1;
  *((_WORD *)this + 1276) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 15);
  *((_QWORD *)this + 959) = 0;
  *((_DWORD *)this + 1920) = 0;
  *((_WORD *)this + 3842) = 0;
  *((_DWORD *)this + 1922) = 20;
  *((_DWORD *)this + 1632) = 0;
  *((_DWORD *)this + 1640) = 0;
  *((_DWORD *)this + 1648) = 0;
  return this;
}

```

## disassembly

```asm
0x1800649bc  mov     [rsp+arg_0], rcx
0x1800649c1  push    rbx
0x1800649c2  push    rbp
0x1800649c3  push    rsi
0x1800649c4  push    rdi
0x1800649c5  push    r14
0x1800649c7  push    r15
0x1800649c9  sub     rsp, 0E8h
0x1800649d0  mov     rbx, r8
0x1800649d3  mov     rsi, rdx
0x1800649d6  mov     rdi, rcx
0x1800649d9  xor     ebp, ebp
0x1800649db  mov     [rcx], rbp
0x1800649de  mov     [rcx+8], rbp
0x1800649e2  mov     [rcx+10h], rbp
0x1800649e6  mov     [rcx+18h], rbp
0x1800649ea  mov     [rcx+20h], rbp
0x1800649ee  mov     [rcx+28h], ebp
0x1800649f1  add     rcx, 2A8h
0x1800649f8  call    ??0?$NGTreeProbCacheSize@$0EA@@@QEAA@XZ; NGTreeProbCacheSize<64>::NGTreeProbCacheSize<64>(void)
0x1800649fd  nop
0x1800649fe  mov     [rdi+920h], rsi
0x180064a05  mov     [rdi+928h], rbp
0x180064a0c  mov     [rdi+930h], rbp
0x180064a13  mov     [rdi+938h], rsi
0x180064a1a  mov     [rdi+940h], rbp
0x180064a21  mov     [rdi+948h], rbp
0x180064a28  mov     [rdi+958h], rsi
0x180064a2f  mov     [rdi+960h], rbp
0x180064a36  mov     [rdi+968h], rbp
0x180064a3d  mov     [rdi+980h], rsi
0x180064a44  mov     [rdi+988h], rbp
0x180064a4b  mov     [rdi+990h], rbp
0x180064a52  mov     [rdi+9A0h], rsi
0x180064a59  mov     [rdi+9A8h], rbp
0x180064a60  mov     [rdi+9B0h], rbp
0x180064a67  mov     [rdi+9B8h], rsi
0x180064a6e  mov     [rdi+9C0h], rbp
0x180064a75  mov     [rdi+9C8h], rbp
0x180064a7c  mov     [rdi+9D8h], rsi
0x180064a83  mov     [rdi+9E0h], rbp
0x180064a8a  mov     [rdi+9E8h], rbp
0x180064a91  lea     rcx, [rdi+0DF0h]; void *
0x180064a98  lea     rax, ??1cfData@@QEAA@XZ; cfData::~cfData(void)
0x180064a9f  mov     [rsp+118h+var_F8], rax; void (*)(void *)
0x180064aa4  lea     r9, ??0cfData@@QEAA@XZ; void (*)(void *)
0x180064aab  mov     edx, 0B0h; unsigned __int64
0x180064ab0  lea     r8d, [rbp+10h]; unsigned __int64
0x180064ab4  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180064ab9  nop
0x180064aba  lea     rcx, [rdi+1920h]; this
0x180064ac1  mov     rdx, rsi; struct CHeap *
0x180064ac4  call    ??0RCDFanoutCache@@QEAA@PEAVCHeap@@@Z; RCDFanoutCache::RCDFanoutCache(CHeap *)
0x180064ac9  nop
0x180064aca  lea     rax, ?g_heap@@3VCHeap@@A; CHeap g_heap
0x180064ad1  mov     [rdi+1968h], rax
0x180064ad8  mov     [rdi+1970h], rbp
0x180064adf  mov     [rdi+1978h], rbp
0x180064ae6  mov     [rdi+1988h], rax
0x180064aed  mov     [rdi+1990h], rbp
0x180064af4  mov     [rdi+1998h], rbp
0x180064afb  mov     [rdi+19A8h], rax
0x180064b02  mov     [rdi+19B0h], rbp
0x180064b09  mov     [rdi+19B8h], rbp
0x180064b10  mov     [rdi+1C40h], rsi
0x180064b17  mov     [rdi+1C48h], rbp
0x180064b1e  mov     [rdi+1C50h], rbp
0x180064b25  mov     [rdi+1C58h], rsi
0x180064b2c  mov     [rdi+1C60h], rbp
0x180064b33  mov     [rdi+1C68h], rbp
0x180064b3a  mov     [rdi+1C70h], rbp
0x180064b41  mov     [rdi+1C78h], rbp
0x180064b48  mov     [rdi+1C80h], rbp
0x180064b4f  mov     [rdi+1C88h], rbp
0x180064b56  mov     [rdi+1C90h], ebp
0x180064b5c  mov     [rdi+1CB0h], rsi
0x180064b63  mov     [rdi+1CB8h], rbp
0x180064b6a  mov     [rdi+1CC0h], rbp
0x180064b71  lea     rcx, [rdi+1CD0h]; void *
0x180064b78  lea     rax, ??1CChannelPartition@@QEAA@XZ; CChannelPartition::~CChannelPartition(void)
0x180064b7f  mov     [rsp+118h+var_F8], rax; void (*)(void *)
0x180064b84  lea     r9, ??0CChannelPartition@@QEAA@XZ; void (*)(void *)
0x180064b8b  lea     r14d, [rbp+1]
0x180064b8f  mov     r8d, r14d; unsigned __int64
0x180064b92  mov     edx, 108h; unsigned __int64
0x180064b97  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180064b9c  mov     [rdi+1CC8h], rbp
0x180064ba3  mov     [rdi+218h], ebp
0x180064ba9  mov     [rdi+21Ch], bpl
0x180064bb0  mov     [rdi+220h], ebp
0x180064bb6  mov     [rdi+48h], rsi
0x180064bba  mov     [rdi+50h], rbx
0x180064bbe  mov     [rdi+900h], rbp
0x180064bc5  mov     [rdi+908h], rbp
0x180064bcc  mov     [rdi+8F0h], rbp
0x180064bd3  mov     [rdi+8F8h], rbp
0x180064bda  xorps   xmm0, xmm0
0x180064bdd  xor     eax, eax
0x180064bdf  movups  xmmword ptr [rdi+1AD8h], xmm0
0x180064be6  mov     [rdi+1AE8h], rax
0x180064bed  mov     dword ptr [rdi+1AE8h], 0FFFFFFFFh
0x180064bf7  mov     [rdi+1C34h], rbp
0x180064bfe  mov     [rdi+910h], ebp
0x180064c04  mov     eax, 10000h
0x180064c09  mov     [rdi+914h], eax
0x180064c0f  mov     [rdi+918h], eax
0x180064c15  mov     [rdi+950h], ebp
0x180064c1b  mov     [rdi+9D0h], ebp
0x180064c21  mov     [rdi+998h], ebp
0x180064c27  mov     [rdi+970h], ebp
0x180064c2d  mov     dword ptr [rdi+974h], 0E0000000h
0x180064c37  mov     dword ptr [rdi+978h], 0FFFFFFFEh
0x180064c41  mov     [rdi+1C98h], rbp
0x180064c48  mov     [rdi+1CA0h], rbp
0x180064c4f  mov     [rdi+1CA8h], ebp
0x180064c55  mov     [rdi+0A00h], rbp
0x180064c5c  mov     [rdi+0A18h], rbp
0x180064c63  mov     [rdi+1C30h], ebp
0x180064c69  mov     [rdi+0A20h], r14d
0x180064c70  mov     [rdi+0BD0h], bpl
0x180064c77  mov     [rdi+9F0h], ebp
0x180064c7d  mov     [rdi+0B28h], rbp
0x180064c84  mov     [rdi+0B30h], rbp
0x180064c8b  mov     eax, ebp
0x180064c8d  mov     [rdi+rax*8+19F0h], rbp
0x180064c95  mov     [rdi+rax*8+0AA8h], rbp
0x180064c9d  mov     [rdi+rax*8+1AF0h], rbp
0x180064ca5  mov     [rdi+rax*8+1B70h], rbp
0x180064cad  mov     [rdi+rax*8+0A28h], rbp
0x180064cb5  add     rax, r14
0x180064cb8  cmp     rax, 10h
0x180064cbc  jnz     short loc_180064C8D
0x180064cbe  mov     [rdi+1AB8h], rbp
0x180064cc5  mov     [rdi+1AB0h], bpl
0x180064ccc  mov     [rdi+1AC0h], ebp
0x180064cd2  mov     [rdi+1AC8h], rbp
0x180064cd9  mov     [rdi+1AD0h], bpl
0x180064ce0  mov     eax, cs:dword_18011785C
0x180064ce6  cdq
0x180064ce7  mov     r15d, 2
0x180064ced  idiv    r15d
0x180064cf0  mov     [rdi+1AD4h], eax
0x180064cf6  mov     [rdi+0B38h], rbp
0x180064cfd  mov     [rdi+0B48h], rbp
0x180064d04  mov     [rdi+0B40h], rbp
0x180064d0b  mov     dword ptr [rdi+0B9Ch], 0FFFFFFFEh
0x180064d15  mov     dword ptr [rdi+0B50h], 0FFFFFFFEh
0x180064d1f  mov     [rdi+0B58h], bpl
0x180064d26  mov     [rdi+0BA0h], r14b
0x180064d2d  mov     rbx, rbp
0x180064d30  mov     dword ptr [rdi+rbx*4+0B5Ch], 0FFFFFFFEh
0x180064d3b  mov     rdx, rsi; struct CHeap *
0x180064d3e  lea     rcx, [rsp+118h+var_E8]; this
0x180064d43  call    ??0cfData@@QEAA@PEAVCHeap@@@Z; cfData::cfData(CHeap *)
0x180064d48  imul    rcx, rbx, 0B0h
0x180064d4f  movups  xmm0, xmmword ptr [rax]
0x180064d52  movups  xmmword ptr [rcx+rdi+0DF0h], xmm0
0x180064d5a  movups  xmm1, xmmword ptr [rax+10h]
0x180064d5e  movups  xmmword ptr [rcx+rdi+0E00h], xmm1
0x180064d66  movups  xmm0, xmmword ptr [rax+20h]
0x180064d6a  movups  xmmword ptr [rcx+rdi+0E10h], xmm0
0x180064d72  movups  xmm1, xmmword ptr [rax+30h]
0x180064d76  movups  xmmword ptr [rcx+rdi+0E20h], xmm1
0x180064d7e  movups  xmm0, xmmword ptr [rax+40h]
0x180064d82  movups  xmmword ptr [rcx+rdi+0E30h], xmm0
0x180064d8a  movups  xmm1, xmmword ptr [rax+50h]
0x180064d8e  movups  xmmword ptr [rcx+rdi+0E40h], xmm1
0x180064d96  movups  xmm0, xmmword ptr [rax+60h]
0x180064d9a  movups  xmmword ptr [rcx+rdi+0E50h], xmm0
0x180064da2  movups  xmm1, xmmword ptr [rax+70h]
0x180064da6  movups  xmmword ptr [rcx+rdi+0E60h], xmm1
0x180064dae  movups  xmm0, xmmword ptr [rax+80h]
0x180064db5  movups  xmmword ptr [rcx+rdi+0E70h], xmm0
0x180064dbd  movups  xmm1, xmmword ptr [rax+90h]
0x180064dc4  movups  xmmword ptr [rcx+rdi+0E80h], xmm1
0x180064dcc  movups  xmm0, xmmword ptr [rax+0A0h]
0x180064dd3  movups  xmmword ptr [rcx+rdi+0E90h], xmm0
0x180064ddb  lea     rcx, [rsp+118h+var_E8]; this
0x180064de0  call    ??1cfData@@QEAA@XZ; cfData::~cfData(void)
0x180064de5  add     rbx, r14
0x180064de8  cmp     rbx, 10h
0x180064dec  jnz     loc_180064D30
0x180064df2  mov     [rdi+0BA1h], bpl
0x180064df9  mov     [rdi+0BA3h], bpl
0x180064e00  mov     [rdi+0BA4h], ebp
0x180064e06  mov     [rdi+0BA8h], bp
0x180064e0d  mov     [rdi+0BABh], bpl
0x180064e14  mov     [rdi+0A08h], bpl
0x180064e1b  mov     [rdi+0BB0h], rbp
0x180064e22  mov     [rdi+0BD4h], rbp
0x180064e29  mov     [rdi+1904h], ebp
0x180064e2f  mov     [rdi+1908h], rbp
0x180064e36  mov     [rdi+1910h], rbp
0x180064e3d  mov     [rdi+0DECh], ebp
0x180064e43  mov     [rdi+0BB8h], ebp
0x180064e49  mov     [rdi+22Ch], bp
0x180064e50  mov     [rdi+0BBCh], r14d
0x180064e57  mov     [rdi+0BC0h], r15d
0x180064e5e  mov     [rdi+1C08h], r15d
0x180064e65  mov     [rdi+0BC4h], r15d
0x180064e6c  mov     ecx, 3F800000h
0x180064e71  mov     [rdi+0BC8h], ecx
0x180064e77  mov     [rdi+1C28h], rbp
0x180064e7e  mov     [rdi+0BE4h], ebp
0x180064e84  mov     [rdi+1C04h], ebp
0x180064e8a  mov     eax, dword ptr cs:?Beams50@CAccuracyBeams@@2V1@B+4; CAccuracyBeams const CAccuracyBeams::Beams50
0x180064e90  mov     [rdi+0BF0h], eax
0x180064e96  mov     eax, dword ptr cs:?Beams50@CAccuracyBeams@@2V1@B; CAccuracyBeams const CAccuracyBeams::Beams50
0x180064e9c  mov     [rdi+0BECh], eax
0x180064ea2  mov     [rdi+46h], bpl
0x180064ea6  or      eax, 0FFFFFFFFh
0x180064ea9  mov     [rdi+30h], eax
0x180064eac  mov     dword ptr [rdi+34h], 64h ; 'd'
0x180064eb3  mov     [rdi+38h], bpl
0x180064eb7  mov     [rdi+3Ch], eax
0x180064eba  mov     [rdi+40h], r14d
0x180064ebe  mov     [rdi+206h], bpl
0x180064ec5  mov     eax, dword ptr cs:xmmword_1801509F8
0x180064ecb  mov     [rdi+0BDCh], eax
0x180064ed1  mov     eax, dword ptr cs:?Beams50@CAccuracyBeams@@2V1@B+0Ch; CAccuracyBeams const CAccuracyBeams::Beams50
0x180064ed7  mov     [rdi+0BE0h], eax
0x180064edd  mov     eax, dword ptr cs:xmmword_1801509F8+4
0x180064ee3  mov     [rdi+8E0h], eax
0x180064ee9  mov     eax, dword ptr cs:xmmword_1801509F8+8
0x180064eef  mov     [rdi+8E4h], eax
0x180064ef5  movups  xmm0, cs:?Beams50@CAccuracyBeams@@2V1@B; CAccuracyBeams const CAccuracyBeams::Beams50
0x180064efc  movups  xmmword ptr [rdi+0C00h], xmm0
0x180064f03  movups  xmm1, cs:xmmword_1801509F8
0x180064f0a  movups  xmmword ptr [rdi+0C10h], xmm1
0x180064f11  movups  xmm0, cs:xmmword_1801509F8+0Ch
0x180064f18  movups  xmmword ptr [rdi+0C1Ch], xmm0
0x180064f1f  movups  xmm0, cs:?Beams100@CAccuracyBeams@@2V1@B; CAccuracyBeams const CAccuracyBeams::Beams100
0x180064f26  movups  xmmword ptr [rdi+0C2Ch], xmm0
0x180064f2d  movups  xmm1, cs:xmmword_180150A28
0x180064f34  movups  xmmword ptr [rdi+0C3Ch], xmm1
0x180064f3b  movups  xmm0, cs:xmmword_180150A28+0Ch
0x180064f42  movups  xmmword ptr [rdi+0C48h], xmm0
0x180064f49  mov     [rdi+0CB4h], bpl
0x180064f50  mov     [rdi+0CC8h], rbp
0x180064f57  mov     [rdi+0CC0h], rbp
0x180064f5e  mov     [rdi+1E8h], rbp
0x180064f65  mov     [rdi+1F0h], ebp
0x180064f6b  mov     [rdi+0CD0h], ebp
0x180064f71  mov     [rdi+0CD4h], ecx
0x180064f77  mov     dword ptr [rdi+0CDCh], 3F000000h
0x180064f81  mov     eax, cs:dword_180150A08
0x180064f87  mov     [rdi+0CE4h], eax
0x180064f8d  mov     eax, cs:dword_180150A0C
0x180064f93  mov     [rdi+0CE8h], eax
0x180064f99  mov     [rdi+0D68h], bp
0x180064fa0  mov     [rdi+0D6Ah], bpl
0x180064fa7  mov     [rdi+0D6Ch], ebp
0x180064fad  mov     [rdi+0D70h], rbp
0x180064fb4  mov     [rdi+0D78h], rbp
0x180064fbb  mov     [rdi+1C20h], rbp
0x180064fc2  mov     [rdi+19C8h], rbp
0x180064fc9  xorps   xmm0, xmm0
0x180064fcc  movups  xmmword ptr [rdi+19D0h], xmm0
0x180064fd3  xorps   xmm1, xmm1
0x180064fd6  movups  xmmword ptr [rdi+19E0h], xmm1
0x180064fdd  mov     [rdi+0DA8h], rbp
0x180064fe4  mov     [rdi+0DB0h], rbp
0x180064feb  mov     [rdi+0DB8h], bpl
0x180064ff2  mov     [rdi+0DC8h], rbp
0x180064ff9  mov     [rdi+0DD0h], rbp
0x180065000  mov     [rdi+0DD8h], rbp
0x180065007  mov     [rdi+0DC0h], rbp
0x18006500e  mov     [rdi+0DE0h], bp
0x180065015  mov     [rdi+0CE0h], bp
0x18006501c  mov     [rdi+1C00h], r14b
0x180065023  mov     [rdi+0DE4h], r14d
0x18006502a  mov     [rdi+0DE8h], r15d
0x180065031  mov     dword ptr [rdi+18F8h], 19h
0x18006503b  mov     dword ptr [rdi+18FCh], 5
0x180065045  mov     [rdi+0BA2h], bpl
0x18006504c  mov     byte ptr [rdi+0D80h], 0FFh
0x180065053  mov     [rdi+1900h], bpl
0x18006505a  mov     [rdi+0DA4h], ebp
0x180065060  mov     dword ptr [rdi+0D98h], 43764h
0x18006506a  mov     eax, 0E0000000h
0x18006506f  mov     [rdi+0D9Ch], eax
0x180065075  mov     [rdi+0DA0h], eax
0x18006507b  mov     [rdi+60h], rbp
0x18006507f  mov     dword ptr [rdi+1DDCh], 46h ; 'F'
0x180065089  mov     dword ptr [rdi+1DE0h], 1Eh
0x180065093  mov     ebx, 14h
0x180065098  mov     [rdi+1DE4h], ebx
0x18006509e  mov     eax, 0BF800000h
0x1800650a3  mov     [rdi+1DE8h], eax
0x1800650a9  mov     [rdi+1DECh], eax
0x1800650af  mov     eax, 42480000h
0x1800650b4  mov     [rdi+1DF0h], eax
0x1800650ba  mov     [rdi+1DF4h], eax
0x1800650c0  mov     rax, rbp
0x1800650c3  mov     [rdi+rax*8+68h], rbp
0x1800650c8  mov     [rdi+rax*8+0E8h], rbp
0x1800650d0  mov     [rdi+rax*8+168h], rbp
0x1800650d8  add     rax, r14
0x1800650db  cmp     rax, 10h
0x1800650df  jnz     short loc_1800650C3
  ... truncated ...
```
