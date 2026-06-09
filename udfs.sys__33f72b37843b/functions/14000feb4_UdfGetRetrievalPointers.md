# UdfGetRetrievalPointers

- ea: `0x14000feb4`
- end: `0x1400103cf`
- name: `UdfGetRetrievalPointers`
- size: `1307`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14004b594`

## callees

- `0x1400030e0`
- `0x1400050d8`
- `0x14000b648`
- `0x14000eb04`
- `0x14000feb4`
- `0x140030738`
- `0x140045f10`
- `0x14004ce50`
- `0x1400543e0`
- `0x140054460`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400101e8`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x1400101e8`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140010388`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14001d7c7`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x140010388`
- `ntoskrnl!FsRtlUninitializeLargeMcb` at `0x14001d7c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400100c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010354`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001036f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d78e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d7ae`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400100c7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010354`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001036f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d78e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001d7ae`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x140010301`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x140010301`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14001014b`
- `ntoskrnl!FsRtlInitializeLargeMcb` at `0x14001014b`
- `ntoskrnl!ProbeForRead` at `0x14000ffe0`
- `ntoskrnl!ProbeForRead` at `0x14000ffe0`
- `ntoskrnl!ProbeForWrite` at `0x14000fffe`
- `ntoskrnl!ProbeForWrite` at `0x14000fffe`

## pseudocode

```c
__int64 __fastcall UdfGetRetrievalPointers(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  unsigned int v5; // esi
  unsigned int v6; // r14d
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // esi
  char v10; // r12
  __int64 v11; // r14
  unsigned __int64 v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  BOOLEAN NextLargeMcbEntry; // dl
  int v16; // r8d
  __int64 v17; // rbx
  unsigned int v18; // r9d
  unsigned int v19; // ecx
  _QWORD *v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  _QWORD *v23; // r8
  char v25; // [rsp+41h] [rbp-C7h]
  unsigned int v26; // [rsp+4Ch] [rbp-BCh]
  unsigned int v27; // [rsp+50h] [rbp-B8h]
  __int64 v28; // [rsp+60h] [rbp-A8h] BYREF
  __int64 StartingLbn; // [rsp+68h] [rbp-A0h] BYREF
  unsigned __int64 v30; // [rsp+70h] [rbp-98h] BYREF
  __int64 v31; // [rsp+78h] [rbp-90h]
  __int64 SectorCount; // [rsp+80h] [rbp-88h] BYREF
  __int64 Vbn; // [rsp+88h] [rbp-80h] BYREF
  volatile void *Address; // [rsp+90h] [rbp-78h]
  __int64 Lbn; // [rsp+98h] [rbp-70h] BYREF
  LARGE_MCB Mcb; // [rsp+A0h] [rbp-68h] BYREF
  unsigned int v37; // [rsp+C0h] [rbp-48h]
  ULONG Index; // [rsp+120h] [rbp+18h] BYREF
  SIZE_T Length; // [rsp+128h] [rbp+20h] BYREF

  Index = 0;
  v28 = 0;
  v30 = 0;
  Lbn = 0;
  Vbn = 0;
  StartingLbn = 0;
  SectorCount = 0;
  memset(&Mcb, 0, sizeof(Mcb));
  v31 = *(_QWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 28) |= 4u;
  v4 = *(_QWORD *)(a2 + 184);
  v5 = *(_DWORD *)(v4 + 16);
  LODWORD(Length) = v5;
  v6 = *(_DWORD *)(v4 + 8);
  v26 = v6;
  Address = (volatile void *)UdfMapUserBuffer(a1, a2);
  if ( (unsigned int)UdfDecodeFileObject(*(_QWORD *)(v4 + 48), &v28, &v30) - 3 > 1 || v5 < 8 )
  {
    v8 = -1073741811;
    v7 = a1;
    goto LABEL_32;
  }
  v7 = a1;
  if ( v6 < 0x20 )
  {
    v8 = -1073741789;
LABEL_32:
    UdfCompleteRequest(v7, a2, v8);
    return v8;
  }
  v9 = 0;
  v25 = 0;
  v10 = 0;
  v27 = 0;
  v11 = v28;
  UdfAcquireResource(a1, *(_QWORD *)(*(_QWORD *)(v28 + 136) + 80LL) + 8LL, 0, 1);
  UdfVerifyScbOperation(a1, v11, v30);
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(*(volatile void **)(v4 + 32), (unsigned int)Length, 1u);
    ProbeForWrite(Address, v26, 1u);
  }
  v12 = **(_QWORD **)(v4 + 32);
  v30 = v12;
  if ( v12 >= (unsigned int)(*(_QWORD *)(v11 + 24) >> *(_DWORD *)(v31 + 72))
    || (*(_DWORD *)(v11 + 212) & 2) != 0
    || !*(_QWORD *)(v11 + 24) )
  {
    goto LABEL_25;
  }
  UdfAcquireResource(a1, *(_QWORD *)(v11 + 16), 0, 1);
  v25 = 1;
  if ( (*(_DWORD *)(v11 + 212) & 0x2000) == 0
    && (*(_BYTE *)(*(_QWORD *)(v31 + 16) + 6LL) & 2) == 0
    && (*(_DWORD *)(v31 + 48) & 0x20000000) == 0
    && *(_QWORD *)(v11 + 312) != *(_QWORD *)(v11 + 32) )
  {
    LODWORD(Length) = 0;
    ExReleaseResourceLite(*(PERESOURCE *)(v11 + 16));
    UdfAcquireResource(a1, *(_QWORD *)(v11 + 16), 0, 0);
    UdfGetBlocksNeeded(v31, v11, v11 + 32, (unsigned int)&Length, 0, 0, 0, 0);
    if ( (_DWORD)Length )
    {
      UdfAllocateAtFileTail(a1, v11, (unsigned int)Length, v11 + 32);
      UdfUpdateAdsFromScb(a1, v11, 0, 0xFFFFFFFFLL);
    }
  }
  FsRtlInitializeLargeMcb(&Mcb, PagedPool);
  v10 = 1;
  UdfCopyMoveMcbAllocation(v13, v11 + 232, &Mcb, 0);
  if ( (*(_DWORD *)(v11 + 212) & 0x4000) != 0 )
    UdfCopyMoveMcbAllocation(v14, v11 + 264, &Mcb, 0);
  NextLargeMcbEntry = FsRtlLookupLargeMcbEntry(&Mcb, v12, &Lbn, 0, &StartingLbn, &SectorCount, &Index);
  if ( NextLargeMcbEntry )
  {
    v16 = StartingLbn;
    v17 = StartingLbn - Lbn + v12;
    v30 = v17;
    Vbn = v17;
    while ( 1 )
    {
      v18 = v27;
      v19 = v27 + 2;
      if ( !NextLargeMcbEntry )
        break;
      if ( v26 < 16 * v19 )
      {
        v9 = -2147483643;
        break;
      }
      v21 = 2LL * v27;
      v22 = (unsigned int)(v16
                         - *(_DWORD *)(((*(_DWORD *)(v11 + 212) & 0x8000000) != 0 ? 0xC8 : 0)
                                     + *(_QWORD *)(a1 + 16)
                                     + 656LL));
      v23 = Address;
      *((_QWORD *)Address + v21 + 3) = v22;
      v23[v21 + 2] = Vbn + SectorCount;
      ++v27;
      v37 = v18 + 1;
      NextLargeMcbEntry = FsRtlGetNextLargeMcbEntry(&Mcb, ++Index, &Vbn, &StartingLbn, &SectorCount);
      v16 = StartingLbn;
    }
    v20 = Address;
    *(_DWORD *)Address = v27;
    v20[1] = v17;
    *(_QWORD *)(a2 + 56) = (int)(16 * v19);
  }
  else
  {
LABEL_25:
    v9 = -1073741807;
  }
  if ( v25 )
    ExReleaseResourceLite(*(PERESOURCE *)(v11 + 16));
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(v11 + 136) + 80LL) + 8LL));
  if ( v10 )
    FsRtlUninitializeLargeMcb(&Mcb);
  UdfCompleteRequest(a1, a2, v9);
  return v9;
}

```

## disassembly

```asm
0x14000feb4  mov     rax, rsp
0x14000feb7  mov     [rax+10h], rdx
0x14000febb  mov     [rax+8], rcx
0x14000febf  push    rbx
0x14000fec0  push    rsi
0x14000fec1  push    rdi
0x14000fec2  push    r12
0x14000fec4  push    r13
0x14000fec6  push    r14
0x14000fec8  push    r15
0x14000feca  sub     rsp, 0D0h
0x14000fed1  mov     r13, rdx
0x14000fed4  mov     r15, rcx
0x14000fed7  xor     edi, edi
0x14000fed9  mov     [rsp+108h+var_C0], edi
0x14000fedd  mov     [rax+18h], edi
0x14000fee0  mov     [rsp+108h+var_A8], rdi
0x14000fee5  mov     [rsp+108h+var_98], rdi
0x14000feea  mov     [rax-70h], rdi
0x14000feee  mov     [rax-80h], rdi
0x14000fef2  mov     [rsp+108h+var_A0], rdi
0x14000fef7  mov     [rax-88h], rdi
0x14000fefe  xorps   xmm0, xmm0
0x14000ff01  movups  xmmword ptr [rax-68h], xmm0
0x14000ff05  movups  xmmword ptr [rax-58h], xmm0
0x14000ff09  mov     rax, [rcx+10h]
0x14000ff0d  mov     [rsp+108h+var_90], rax
0x14000ff12  or      dword ptr [rcx+1Ch], 4
0x14000ff16  mov     rbx, [rdx+0B8h]
0x14000ff1d  mov     esi, [rbx+10h]
0x14000ff20  mov     dword ptr [rsp+108h+Length], esi
0x14000ff27  mov     r14d, [rbx+8]
0x14000ff2b  mov     dword ptr [rsp+108h+var_BC], r14d
0x14000ff30  call    UdfMapUserBuffer
0x14000ff35  mov     [rsp+108h+Address], rax
0x14000ff3d  lea     r8, [rsp+108h+var_98]
0x14000ff42  lea     rdx, [rsp+108h+var_A8]
0x14000ff47  mov     rcx, [rbx+30h]
0x14000ff4b  call    UdfDecodeFileObject
0x14000ff50  add     eax, 0FFFFFFFDh
0x14000ff53  cmp     eax, 1
0x14000ff56  ja      loc_1400103A6
0x14000ff5c  cmp     esi, 8
0x14000ff5f  jb      loc_1400103A6
0x14000ff65  mov     rcx, r15
0x14000ff68  cmp     r14d, 20h ; ' '
0x14000ff6c  jnb     short loc_14000FF78
0x14000ff6e  mov     ebx, 0C0000023h
0x14000ff73  jmp     loc_1400103AE
0x14000ff78  mov     esi, edi
0x14000ff7a  mov     [rsp+108h+var_C8], dil
0x14000ff7f  mov     [rsp+108h+var_C7], dil
0x14000ff84  mov     r12b, dil
0x14000ff87  mov     [rsp+108h+var_C6], dil
0x14000ff8c  mov     dword ptr [rsp+108h+var_BC+4], edi
0x14000ff90  mov     r14, [rsp+108h+var_A8]
0x14000ff95  mov     rax, [r14+88h]
0x14000ff9c  mov     rdx, [rax+50h]
0x14000ffa0  add     rdx, 8
0x14000ffa4  mov     r9d, 1
0x14000ffaa  xor     r8d, r8d
0x14000ffad  call    UdfAcquireResource
0x14000ffb2  nop
0x14000ffb3  mov     r8, [rsp+108h+var_98]
0x14000ffb8  mov     rdx, r14
0x14000ffbb  mov     rcx, r15
0x14000ffbe  call    UdfVerifyScbOperation
0x14000ffc3  nop
0x14000ffc4  mov     [rsp+108h+var_C8], 1
0x14000ffc9  cmp     [r13+40h], dil
0x14000ffcd  jz      short loc_14001000A
0x14000ffcf  mov     edx, dword ptr [rsp+108h+Length]; Length
0x14000ffd6  mov     r8d, 1; Alignment
0x14000ffdc  mov     rcx, [rbx+20h]; Address
0x14000ffe0  call    cs:__imp_ProbeForRead
0x14000ffe7  nop     dword ptr [rax+rax+00h]
0x14000ffec  mov     edx, dword ptr [rsp+108h+var_BC]; Length
0x14000fff0  mov     r8d, 1; Alignment
0x14000fff6  mov     rcx, [rsp+108h+Address]; Address
0x14000fffe  call    cs:__imp_ProbeForWrite
0x140010005  nop     dword ptr [rax+rax+00h]
0x14001000a  mov     rbx, [rbx+20h]
0x14001000e  mov     rbx, [rbx]
0x140010011  mov     [rsp+108h+var_98], rbx
0x140010016  mov     [rsp+108h+var_C8], dil
0x14001001b  mov     rax, rbx
0x14001001e  shr     rax, 20h
0x140010022  test    eax, eax
0x140010024  jnz     loc_140010319
0x14001002a  mov     rdx, [r14+18h]
0x14001002e  mov     rax, rdx
0x140010031  mov     rcx, [rsp+108h+var_90]
0x140010036  mov     ecx, [rcx+48h]
0x140010039  shr     rax, cl
0x14001003c  cmp     ebx, eax
0x14001003e  jnb     loc_140010319
0x140010044  mov     eax, [r14+0D4h]
0x14001004b  test    al, 2
0x14001004d  jnz     loc_140010319
0x140010053  test    rdx, rdx
0x140010056  jz      loc_140010319
0x14001005c  mov     r9d, 1
0x140010062  xor     r8d, r8d
0x140010065  mov     rdx, [r14+10h]
0x140010069  mov     rcx, r15
0x14001006c  call    UdfAcquireResource
0x140010071  mov     [rsp+108h+var_C7], 1
0x140010076  test    dword ptr [r14+0D4h], 2000h
0x140010081  jnz     loc_14001013E
0x140010087  mov     rdx, [rsp+108h+var_90]
0x14001008c  mov     rax, [rdx+10h]
0x140010090  test    byte ptr [rax+6], 2
0x140010094  jnz     loc_14001013E
0x14001009a  test    dword ptr [rdx+30h], 20000000h
0x1400100a1  jnz     loc_14001013E
0x1400100a7  lea     r12, [r14+20h]
0x1400100ab  mov     rax, [r12]
0x1400100af  cmp     [r14+138h], rax
0x1400100b6  jz      loc_14001013E
0x1400100bc  mov     dword ptr [rsp+108h+Length], edi
0x1400100c3  mov     rcx, [r14+10h]; Resource
0x1400100c7  call    cs:__imp_ExReleaseResourceLite
0x1400100ce  nop     dword ptr [rax+rax+00h]
0x1400100d3  xor     r9d, r9d
0x1400100d6  xor     r8d, r8d
0x1400100d9  mov     rdx, [r14+10h]
0x1400100dd  mov     rcx, r15
0x1400100e0  call    UdfAcquireResource
0x1400100e5  mov     [rsp+108h+var_D0], rdi
0x1400100ea  mov     [rsp+108h+Index], rdi
0x1400100ef  mov     [rsp+108h+SectorCountFromStartingLbn], rdi
0x1400100f4  mov     [rsp+108h+StartingLbn], rdi
0x1400100f9  lea     r9, [rsp+108h+Length]
0x140010101  mov     r8, r12
0x140010104  mov     rdx, r14
0x140010107  mov     rcx, [rsp+108h+var_90]
0x14001010c  call    UdfGetBlocksNeeded
0x140010111  mov     r8d, dword ptr [rsp+108h+Length]
0x140010119  test    r8d, r8d
0x14001011c  jz      short loc_14001013E
0x14001011e  mov     r9, r12
0x140010121  mov     rdx, r14
0x140010124  mov     rcx, r15
0x140010127  call    UdfAllocateAtFileTail
0x14001012c  or      r9d, 0FFFFFFFFh
0x140010130  xor     r8d, r8d
0x140010133  mov     rdx, r14
0x140010136  mov     rcx, r15
0x140010139  call    UdfUpdateAdsFromScb
0x14001013e  mov     edx, 1; PoolType
0x140010143  lea     rcx, [rsp+108h+Mcb]; Mcb
0x14001014b  call    cs:__imp_FsRtlInitializeLargeMcb
0x140010152  nop     dword ptr [rax+rax+00h]
0x140010157  mov     r12b, 1
0x14001015a  mov     [rsp+108h+var_C6], r12b
0x14001015f  lea     rdx, [r14+0E8h]
0x140010166  lea     rax, [rsp+108h+var_C0]
0x14001016b  mov     [rsp+108h+SectorCountFromStartingLbn], rax
0x140010170  xor     r9d, r9d
0x140010173  lea     r8, [rsp+108h+Mcb]
0x14001017b  call    UdfCopyMoveMcbAllocation
0x140010180  test    dword ptr [r14+0D4h], 4000h
0x14001018b  jz      short loc_1400101AE
0x14001018d  lea     rdx, [r14+108h]
0x140010194  lea     rax, [rsp+108h+var_C0]
0x140010199  mov     [rsp+108h+SectorCountFromStartingLbn], rax
0x14001019e  xor     r9d, r9d
0x1400101a1  lea     r8, [rsp+108h+Mcb]
0x1400101a9  call    UdfCopyMoveMcbAllocation
0x1400101ae  lea     rax, [rsp+108h+arg_10]
0x1400101b6  mov     [rsp+108h+Index], rax; Index
0x1400101bb  lea     rax, [rsp+108h+SectorCount]
0x1400101c3  mov     [rsp+108h+SectorCountFromStartingLbn], rax; SectorCountFromStartingLbn
0x1400101c8  lea     rax, [rsp+108h+var_A0]
0x1400101cd  mov     [rsp+108h+StartingLbn], rax; StartingLbn
0x1400101d2  xor     r9d, r9d; SectorCountFromLbn
0x1400101d5  lea     r8, [rsp+108h+Lbn]; Lbn
0x1400101dd  mov     rdx, rbx; Vbn
0x1400101e0  lea     rcx, [rsp+108h+Mcb]; Mcb
0x1400101e8  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x1400101ef  nop     dword ptr [rax+rax+00h]
0x1400101f4  mov     dl, al
0x1400101f6  test    al, al
0x1400101f8  jz      loc_140010319
0x1400101fe  mov     r8, [rsp+108h+var_A0]
0x140010203  mov     rax, r8
0x140010206  sub     rax, [rsp+108h+Lbn]
0x14001020e  add     rbx, rax
0x140010211  mov     [rsp+108h+var_98], rbx
0x140010216  mov     [rsp+108h+Vbn], rbx
0x14001021e  mov     r9d, dword ptr [rsp+108h+var_BC+4]
0x140010223  lea     ecx, [r9+2]
0x140010227  test    dl, dl
0x140010229  jz      short loc_14001023F
0x14001022b  mov     eax, ecx
0x14001022d  shl     eax, 4
0x140010230  cmp     dword ptr [rsp+108h+var_BC], eax
0x140010234  jnb     short loc_140010267
0x140010236  mov     esi, 80000005h
0x14001023b  mov     [rsp+108h+var_C4], esi
0x14001023f  mov     [rsp+108h+var_C8], r12b
0x140010244  mov     rax, [rsp+108h+Address]
0x14001024c  mov     [rax], r9d
0x14001024f  mov     [rax+8], rbx
0x140010253  mov     [rsp+108h+var_C8], dil
0x140010258  shl     ecx, 4
0x14001025b  movsxd  rax, ecx
0x14001025e  mov     [r13+38h], rax
0x140010262  jmp     loc_140010322
0x140010267  mov     [rsp+108h+var_C8], r12b
0x14001026c  mov     rdx, r9
0x14001026f  add     rdx, rdx
0x140010272  mov     eax, [r14+0D4h]
0x140010279  and     eax, 8000000h
0x14001027e  neg     eax
0x140010280  sbb     rcx, rcx
0x140010283  and     ecx, 0C8h
0x140010289  mov     rax, [r15+10h]
0x14001028d  sub     r8d, [rcx+rax+290h]
0x140010295  mov     eax, r8d
0x140010298  mov     r8, [rsp+108h+Address]
0x1400102a0  mov     [r8+rdx*8+18h], rax
0x1400102a5  mov     rcx, [rsp+108h+SectorCount]
0x1400102ad  add     rcx, [rsp+108h+Vbn]
0x1400102b5  mov     [r8+rdx*8+10h], rcx
0x1400102ba  mov     [rsp+108h+var_C8], dil
0x1400102bf  inc     r9d
0x1400102c2  mov     dword ptr [rsp+108h+var_BC+4], r9d
0x1400102c7  mov     [rsp+108h+var_48], r9d
0x1400102cf  mov     edx, [rsp+108h+arg_10]
0x1400102d6  inc     edx; RunIndex
0x1400102d8  mov     [rsp+108h+arg_10], edx
0x1400102df  lea     rax, [rsp+108h+SectorCount]
0x1400102e7  mov     [rsp+108h+StartingLbn], rax; SectorCount
0x1400102ec  lea     r9, [rsp+108h+var_A0]; Lbn
0x1400102f1  lea     r8, [rsp+108h+Vbn]; Vbn
0x1400102f9  lea     rcx, [rsp+108h+Mcb]; Mcb
0x140010301  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x140010308  nop     dword ptr [rax+rax+00h]
0x14001030d  mov     dl, al
0x14001030f  mov     r8, [rsp+108h+var_A0]
0x140010314  jmp     loc_14001021E
0x140010319  mov     esi, 0C0000011h
0x14001031e  mov     [rsp+108h+var_C4], esi
0x140010322  jmp     short loc_140010349
0x140010324  mov     esi, 0C00000E8h
0x140010329  mov     [rsp+108h+var_C4], esi
0x14001032d  xor     edi, edi
0x14001032f  mov     r13, [rsp+108h+arg_8]
0x140010337  mov     r15, [rsp+108h+arg_0]
0x14001033f  mov     r14, [rsp+108h+var_A8]
0x140010344  mov     r12b, [rsp+108h+var_C6]
0x140010349  cmp     [rsp+108h+var_C7], dil
0x14001034e  jz      short loc_140010360
0x140010350  mov     rcx, [r14+10h]; Resource
0x140010354  call    cs:__imp_ExReleaseResourceLite
0x14001035b  nop     dword ptr [rax+rax+00h]
0x140010360  mov     rax, [r14+88h]
0x140010367  mov     rcx, [rax+50h]
0x14001036b  add     rcx, 8; Resource
0x14001036f  call    cs:__imp_ExReleaseResourceLite
0x140010376  nop     dword ptr [rax+rax+00h]
0x14001037b  test    r12b, r12b
0x14001037e  jz      short loc_140010394
0x140010380  lea     rcx, [rsp+108h+Mcb]; Mcb
0x140010388  call    cs:__imp_FsRtlUninitializeLargeMcb
0x14001038f  nop     dword ptr [rax+rax+00h]
0x140010394  mov     r8d, esi
0x140010397  mov     rdx, r13
0x14001039a  mov     rcx, r15
0x14001039d  call    UdfCompleteRequest
0x1400103a2  mov     eax, esi
0x1400103a4  jmp     short loc_1400103BB
0x1400103a6  mov     ebx, 0C000000Dh
0x1400103ab  mov     rcx, r15
0x1400103ae  mov     r8d, ebx
0x1400103b1  mov     rdx, r13
0x1400103b4  call    UdfCompleteRequest
0x1400103b9  mov     eax, ebx
0x1400103bb  add     rsp, 0D0h
0x1400103c2  pop     r15
0x1400103c4  pop     r14
0x1400103c6  pop     r13
0x1400103c8  pop     r12
0x1400103ca  pop     rdi
0x1400103cb  pop     rsi
0x1400103cc  pop     rbx
0x1400103cd  retn
0x14001d72f  push    rbp
0x14001d731  sub     rsp, 40h
0x14001d735  mov     rbp, rdx
0x14001d738  mov     rax, [rcx]
0x14001d73b  mov     ecx, [rax]
0x14001d73d  mov     [rbp+58h], ecx
0x14001d740  cmp     byte ptr [rbp+40h], 0
0x14001d744  jz      short loc_14001D761
0x14001d746  mov     eax, [rbp+58h]
0x14001d749  cmp     eax, 80000002h
0x14001d74e  jz      short loc_14001D75A
0x14001d750  mov     eax, [rbp+58h]
  ... truncated ...
```
