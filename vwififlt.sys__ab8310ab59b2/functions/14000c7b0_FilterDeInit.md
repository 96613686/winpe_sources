# FilterDeInit

- ea: `0x14000c7b0`
- end: `0x14000c9e0`
- name: `FilterDeInit`
- size: `560`
- prototype: `__int64 __fastcall(PVOID VirtualAddress)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400027d0`
- `0x14000443c`

## callees

- `0x14000c7b0`
- `0x14000cd98`
- `0x14000d8ec`
- `0x14000d91c`
- `0x14000f500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c863`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87d`
- `NDIS!NdisFreeMemory` at `0x14000c89a`
- `NDIS!NdisFreeMemory` at `0x14000c8b7`
- `NDIS!NdisFreeMemory` at `0x14000c8d4`
- `NDIS!NdisFreeMemory` at `0x14000c8fc`
- `NDIS!NdisFreeMemory` at `0x14000c972`
- `NDIS!NdisFreeMemory` at `0x14000c991`
- `NDIS!NdisFreeMemory` at `0x14000c89a`
- `NDIS!NdisFreeMemory` at `0x14000c8b7`
- `NDIS!NdisFreeMemory` at `0x14000c8d4`
- `NDIS!NdisFreeMemory` at `0x14000c8fc`
- `NDIS!NdisFreeMemory` at `0x14000c972`
- `NDIS!NdisFreeMemory` at `0x14000c991`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000c91f`
- `NDIS!NdisFreeNetBufferListPool` at `0x14000c91f`

## pseudocode

```c
void __fastcall FilterDeInit(PVOID **VirtualAddress)
{
  PVOID *v2; // rax
  PVOID *v3; // rcx
  PVOID *v4; // rcx
  PVOID *v5; // rcx
  PVOID *v6; // rcx
  PVOID *v7; // rcx
  PVOID *v8; // rcx
  PVOID *v9; // rcx
  PVOID *v10; // rcx
  PVOID *v11; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x7Fu,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids);
  if ( *((_DWORD *)VirtualAddress + 4) )
    TraceAssert((int)"pFilter->RefCount == 0", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c", 2151);
  if ( *((_DWORD *)VirtualAddress + 30) != 6 )
    TraceAssert((int)"pFilter->State == FilterDetaching", (__int64)"onecoreuap\\net\\vwifi\\filter\\filter.c", 2153);
  v2 = *VirtualAddress;
  if ( (*VirtualAddress)[1] != VirtualAddress || (v3 = VirtualAddress[1], *v3 != VirtualAddress) )
    __fastfail(3u);
  *v3 = v2;
  v2[1] = v3;
  v4 = VirtualAddress[315];
  if ( v4 )
    ExFreePoolWithTag(v4, 0x46465756u);
  v5 = VirtualAddress[317];
  if ( v5 )
    ExFreePoolWithTag(v5, 0x46465756u);
  v6 = VirtualAddress[312];
  if ( v6 )
    NdisFreeMemory(v6, 0, 0);
  v7 = VirtualAddress[307];
  if ( v7 )
    NdisFreeMemory(v7, 0, 0);
  v8 = VirtualAddress[338];
  if ( v8 )
  {
    NdisFreeMemory(v8, 0, 0);
    VirtualAddress[338] = 0;
  }
  v9 = VirtualAddress[337];
  if ( v9 )
  {
    NdisFreeMemory(v9, 0, 0);
    VirtualAddress[337] = 0;
  }
  v10 = VirtualAddress[321];
  if ( v10 )
    NdisFreeNetBufferListPool(v10);
  if ( VirtualAddress[331] )
    VirtualAddress[331] = 0;
  memset(VirtualAddress + 3, 0, 0x60u);
  *((_DWORD *)VirtualAddress + 24) = 2199;
  VirtualAddress[11] = (PVOID *)"FilterDeInit";
  v11 = VirtualAddress[390];
  if ( v11 )
    NdisFreeMemory(v11, 0, 0);
  VirtualAddress[390] = 0;
  NdisFreeMemory(VirtualAddress, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x80u,
      (__int64)WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids,
      0);
}

```

## disassembly

```asm
0x14000c7b0  mov     [rsp+arg_0], rbx
0x14000c7b5  mov     [rsp+arg_8], rbp
0x14000c7ba  push    rdi
0x14000c7bb  sub     rsp, 20h
0x14000c7bf  mov     rdi, rcx
0x14000c7c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c7c9  lea     rbp, WPP_GLOBAL_Control
0x14000c7d0  cmp     rcx, rbp
0x14000c7d3  jz      short loc_14000C7F1
0x14000c7d5  mov     eax, [rcx+2Ch]
0x14000c7d8  test    al, 20h
0x14000c7da  jz      short loc_14000C7F1
0x14000c7dc  mov     rcx, [rcx+18h]
0x14000c7e0  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000c7e7  mov     edx, 7Fh
0x14000c7ec  call    WPP_SF_
0x14000c7f1  cmp     dword ptr [rdi+10h], 0
0x14000c7f5  jz      short loc_14000C810
0x14000c7f7  mov     r8d, 867h
0x14000c7fd  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000c804  lea     rcx, aPfilterRefcoun; "pFilter->RefCount == 0"
0x14000c80b  call    TraceAssert
0x14000c810  cmp     dword ptr [rdi+78h], 6
0x14000c814  jz      short loc_14000C82F
0x14000c816  mov     r8d, 869h
0x14000c81c  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000c823  lea     rcx, aPfilterStateFi_0; "pFilter->State == FilterDetaching"
0x14000c82a  call    TraceAssert
0x14000c82f  mov     rax, [rdi]
0x14000c832  cmp     [rax+8], rdi
0x14000c836  jnz     loc_14000C9D9
0x14000c83c  mov     rcx, [rdi+8]
0x14000c840  cmp     [rcx], rdi
0x14000c843  jnz     loc_14000C9D9
0x14000c849  mov     [rcx], rax
0x14000c84c  mov     ebx, 46465756h
0x14000c851  mov     [rax+8], rcx
0x14000c855  mov     rcx, [rdi+9D8h]; P
0x14000c85c  test    rcx, rcx
0x14000c85f  jz      short loc_14000C86F
0x14000c861  mov     edx, ebx; Tag
0x14000c863  call    cs:__imp_ExFreePoolWithTag
0x14000c86a  nop     dword ptr [rax+rax+00h]
0x14000c86f  mov     rcx, [rdi+9E8h]; P
0x14000c876  test    rcx, rcx
0x14000c879  jz      short loc_14000C889
0x14000c87b  mov     edx, ebx; Tag
0x14000c87d  call    cs:__imp_ExFreePoolWithTag
0x14000c884  nop     dword ptr [rax+rax+00h]
0x14000c889  mov     rcx, [rdi+9C0h]; VirtualAddress
0x14000c890  test    rcx, rcx
0x14000c893  jz      short loc_14000C8A6
0x14000c895  xor     r8d, r8d; MemoryFlags
0x14000c898  xor     edx, edx; Length
0x14000c89a  call    cs:__imp_NdisFreeMemory
0x14000c8a1  nop     dword ptr [rax+rax+00h]
0x14000c8a6  mov     rcx, [rdi+998h]; VirtualAddress
0x14000c8ad  test    rcx, rcx
0x14000c8b0  jz      short loc_14000C8C3
0x14000c8b2  xor     r8d, r8d; MemoryFlags
0x14000c8b5  xor     edx, edx; Length
0x14000c8b7  call    cs:__imp_NdisFreeMemory
0x14000c8be  nop     dword ptr [rax+rax+00h]
0x14000c8c3  mov     rcx, [rdi+0A90h]; VirtualAddress
0x14000c8ca  test    rcx, rcx
0x14000c8cd  jz      short loc_14000C8EB
0x14000c8cf  xor     r8d, r8d; MemoryFlags
0x14000c8d2  xor     edx, edx; Length
0x14000c8d4  call    cs:__imp_NdisFreeMemory
0x14000c8db  nop     dword ptr [rax+rax+00h]
0x14000c8e0  mov     qword ptr [rdi+0A90h], 0
0x14000c8eb  mov     rcx, [rdi+0A88h]; VirtualAddress
0x14000c8f2  test    rcx, rcx
0x14000c8f5  jz      short loc_14000C913
0x14000c8f7  xor     r8d, r8d; MemoryFlags
0x14000c8fa  xor     edx, edx; Length
0x14000c8fc  call    cs:__imp_NdisFreeMemory
0x14000c903  nop     dword ptr [rax+rax+00h]
0x14000c908  mov     qword ptr [rdi+0A88h], 0
0x14000c913  mov     rcx, [rdi+0A08h]; PoolHandle
0x14000c91a  test    rcx, rcx
0x14000c91d  jz      short loc_14000C92B
0x14000c91f  call    cs:__imp_NdisFreeNetBufferListPool
0x14000c926  nop     dword ptr [rax+rax+00h]
0x14000c92b  cmp     qword ptr [rdi+0A58h], 0
0x14000c933  jz      short loc_14000C940
0x14000c935  mov     qword ptr [rdi+0A58h], 0
0x14000c940  xor     edx, edx; Val
0x14000c942  lea     rcx, [rdi+18h]; void *
0x14000c946  lea     r8d, [rdx+60h]; Size
0x14000c94a  call    memset
0x14000c94f  lea     rax, aFilterdeinit; "FilterDeInit"
0x14000c956  mov     dword ptr [rdi+60h], 897h
0x14000c95d  mov     [rdi+58h], rax
0x14000c961  mov     rcx, [rdi+0C30h]; VirtualAddress
0x14000c968  test    rcx, rcx
0x14000c96b  jz      short loc_14000C97E
0x14000c96d  xor     r8d, r8d; MemoryFlags
0x14000c970  xor     edx, edx; Length
0x14000c972  call    cs:__imp_NdisFreeMemory
0x14000c979  nop     dword ptr [rax+rax+00h]
0x14000c97e  xor     r8d, r8d; MemoryFlags
0x14000c981  mov     qword ptr [rdi+0C30h], 0
0x14000c98c  xor     edx, edx; Length
0x14000c98e  mov     rcx, rdi; VirtualAddress
0x14000c991  call    cs:__imp_NdisFreeMemory
0x14000c998  nop     dword ptr [rax+rax+00h]
0x14000c99d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c9a4  cmp     rcx, rbp
0x14000c9a7  jz      short loc_14000C9C8
0x14000c9a9  mov     eax, [rcx+2Ch]
0x14000c9ac  test    al, 20h
0x14000c9ae  jz      short loc_14000C9C8
0x14000c9b0  mov     rcx, [rcx+18h]
0x14000c9b4  lea     r8, WPP_577728b1843d38bfcf7aafa5ce158edb_Traceguids
0x14000c9bb  mov     edx, 80h
0x14000c9c0  xor     r9d, r9d
0x14000c9c3  call    WPP_SF_d
0x14000c9c8  mov     rbx, [rsp+28h+arg_0]
0x14000c9cd  mov     rbp, [rsp+28h+arg_8]
0x14000c9d2  add     rsp, 20h
0x14000c9d6  pop     rdi
0x14000c9d7  retn
0x14000c9d9  mov     ecx, 3
0x14000c9de  int     29h; Win8: RtlFailFast(ecx)
```
