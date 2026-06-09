# Smb2ExecuteDirectPlacementWrite

- ea: `0x140091888`
- end: `0x140091b1c`
- name: `Smb2ExecuteDirectPlacementWrite`
- size: `660`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14006c240`
- `0x14007e340`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x140091888`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400919ed`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a49`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400919ed`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a49`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400919b1`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400919b1`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091946`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091999`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091946`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091999`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400918da`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14009195d`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400918da`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14009195d`
- `srvnet!SrvNetReadDirectData` at `0x140091b02`
- `srvnet!SrvNetReadDirectData` at `0x140091b02`

## string_xrefs

- `0x1400918fb`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140091a78`: `Smb2ExecuteDirectPlacementWrite`

## pseudocode

```c
__int64 __fastcall Smb2ExecuteDirectPlacementWrite(__int64 a1)
{
  __int64 v1; // rdi
  ULONG v3; // ebx
  __int64 v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 result; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rbp
  __int64 v12; // r15
  __int64 v13; // rax
  struct _MDL *v14; // r14
  void *v15; // r15
  void *v16; // r8
  struct _MDL *v17; // rcx
  __int64 BufferNoTransportHeader; // rax
  void *v19; // r14
  struct _MDL *v20; // r15
  __int64 v21; // rcx
  PVOID v22; // rax
  PVOID v23; // rax
  bool v24; // cf
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-48h]

  v1 = *(_QWORD *)(a1 + 560);
  v3 = *(_DWORD *)(v1 + 252);
  if ( v3 >= 0x1000
    || (*(_DWORD *)(*(_QWORD *)(v1 + 88) + 80LL) & 0x40) != 0
    || (v4 = *(unsigned int *)(*(_QWORD *)(v1 + 96) + 152LL), (unsigned int)v4 < 2) )
  {
    BufferNoTransportHeader = SrvNetAllocateBufferNoTransportHeader(*(unsigned int *)(v1 + 252));
    *(_QWORD *)(v1 + 160) = BufferNoTransportHeader;
    if ( !BufferNoTransportHeader )
    {
      v7 = 1676;
      goto LABEL_6;
    }
    v11 = *(_QWORD *)(BufferNoTransportHeader + 80);
    v19 = *(void **)(BufferNoTransportHeader + 24);
    v20 = *(struct _MDL **)(BufferNoTransportHeader + 56);
    if ( (*(_BYTE *)(v11 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v11 + 24), *(PMDL *)(BufferNoTransportHeader + 80));
    v16 = v19;
    v17 = v20;
  }
  else
  {
    v5 = SrvNetAllocateBufferNoTransportHeader((unsigned int)v4 + v3);
    *(_QWORD *)(v1 + 160) = v5;
    v6 = v5;
    if ( !v5 )
    {
      v7 = 1659;
LABEL_6:
      Smb2SetError(a1, 3221225989LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v7);
      result = Srv2CompleteWorkItem(a1, 0);
      v10 = 0;
      goto LABEL_21;
    }
    v11 = *(_QWORD *)(v5 + 80);
    v12 = *(_QWORD *)(v5 + 24) + v4 - 1;
    v13 = -(int)v4;
    v14 = *(struct _MDL **)(v6 + 56);
    v15 = (void *)(v13 & v12);
    if ( (*(_BYTE *)(v11 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v11 + 24), *(PMDL *)(v6 + 80));
    v16 = v15;
    v17 = v14;
  }
  IoBuildPartialMdl(v17, (PMDL)v11, v16, v3);
  v21 = *(_QWORD *)(*(_QWORD *)(v1 + 160) + 80LL);
  if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
    v22 = *(PVOID *)(v21 + 24);
  else
    v22 = MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v22 )
  {
    v7 = 1689;
    goto LABEL_6;
  }
  result = *(_QWORD *)(v1 + 160);
  v10 = *(_QWORD *)(result + 80);
LABEL_21:
  *(_QWORD *)(v1 + 200) = v10;
  if ( v10 )
  {
    if ( (*(_BYTE *)(v10 + 10) & 5) != 0 )
      v23 = *(PVOID *)(v10 + 24);
    else
      v23 = MmMapLockedPagesSpecifyCache((PMDL)v10, 0, MmCached, 0, 0, 0x40000010u);
    *(_QWORD *)(v1 + 208) = v23;
    *(_QWORD *)(a1 + 152) = a1;
    *(_QWORD *)(a1 + 144) = Srv2PostAfterReceivePrivateBuffer;
    *(_DWORD *)(a1 + 132) = 0;
    LOBYTE(v9) = 6;
    v24 = *(_QWORD *)(v1 + 216) != 0;
    LOBYTE(BugCheckOnFailure) = 1;
    *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 120);
    *(_DWORD *)(a1 + 176) = v24 ? 0x200 : 0;
    *(_DWORD *)(a1 + 128) = *(_DWORD *)(v1 + 252);
    *(_QWORD *)(a1 + 136) = *(_QWORD *)(v1 + 200);
    *(_QWORD *)(a1 + 48) = Smb2ContinueDirectPlacementWrite;
    SRV2_PERF_ENTER_EX(a1 + 584, v9, 2276, "Smb2ExecuteDirectPlacementWrite", BugCheckOnFailure);
    return SrvNetReadDirectData(
             *(_QWORD *)(*(_QWORD *)(a1 + 96) + 480LL),
             *(_QWORD *)(v1 + 216),
             *(unsigned int *)(v1 + 264),
             a1 + 128);
  }
  return result;
}

```

## disassembly

```asm
0x140091888  push    rbx
0x14009188a  push    rbp
0x14009188b  push    rsi
0x14009188c  push    rdi
0x14009188d  push    r14
0x14009188f  push    r15
0x140091891  sub     rsp, 38h
0x140091895  mov     rdi, [rcx+230h]
0x14009189c  mov     rsi, rcx
0x14009189f  mov     ebx, [rdi+0FCh]
0x1400918a5  cmp     ebx, 1000h
0x1400918ab  jnb     loc_14009195A
0x1400918b1  mov     rax, [rdi+58h]
0x1400918b5  mov     edx, [rax+50h]
0x1400918b8  test    dl, 40h
0x1400918bb  jnz     loc_14009195A
0x1400918c1  mov     rax, [rdi+60h]
0x1400918c5  mov     r14d, [rax+98h]
0x1400918cc  cmp     r14d, 2
0x1400918d0  jb      loc_14009195A
0x1400918d6  lea     ecx, [r14+rbx]
0x1400918da  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x1400918e1  nop     dword ptr [rax+rax+00h]
0x1400918e6  mov     [rdi+0A0h], rax
0x1400918ed  mov     rdx, rax
0x1400918f0  test    rax, rax
0x1400918f3  jnz     short loc_140091920
0x1400918f5  mov     r9d, 67Bh
0x1400918fb  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140091902  mov     edx, 0C0000205h
0x140091907  mov     rcx, rsi
0x14009190a  call    _Smb2SetError
0x14009190f  xor     edx, edx
0x140091911  mov     rcx, rsi
0x140091914  call    Srv2CompleteWorkItem
0x140091919  xor     ecx, ecx
0x14009191b  jmp     loc_140091A14
0x140091920  mov     rbp, [rdx+50h]
0x140091924  lea     r15, [r14-1]
0x140091928  add     r15, [rax+18h]
0x14009192c  neg     r14d
0x14009192f  movsxd  rax, r14d
0x140091932  mov     r14, [rdx+38h]
0x140091936  and     r15, rax
0x140091939  test    byte ptr [rbp+0Ah], 20h
0x14009193d  jz      short loc_140091952
0x14009193f  mov     rcx, [rbp+18h]; BaseAddress
0x140091943  mov     rdx, rbp; MemoryDescriptorList
0x140091946  call    cs:__imp_MmUnmapLockedPages
0x14009194d  nop     dword ptr [rax+rax+00h]
0x140091952  mov     r8, r15
0x140091955  mov     rcx, r14
0x140091958  jmp     short loc_1400919AB
0x14009195a  mov     rcx, rbx
0x14009195d  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x140091964  nop     dword ptr [rax+rax+00h]
0x140091969  mov     [rdi+0A0h], rax
0x140091970  test    rax, rax
0x140091973  jnz     short loc_140091980
0x140091975  mov     r9d, 68Ch
0x14009197b  jmp     loc_1400918FB
0x140091980  mov     rbp, [rax+50h]
0x140091984  mov     r14, [rax+18h]
0x140091988  mov     r15, [rax+38h]
0x14009198c  test    byte ptr [rbp+0Ah], 20h
0x140091990  jz      short loc_1400919A5
0x140091992  mov     rcx, [rbp+18h]; BaseAddress
0x140091996  mov     rdx, rbp; MemoryDescriptorList
0x140091999  call    cs:__imp_MmUnmapLockedPages
0x1400919a0  nop     dword ptr [rax+rax+00h]
0x1400919a5  mov     r8, r14; VirtualAddress
0x1400919a8  mov     rcx, r15; SourceMdl
0x1400919ab  mov     r9d, ebx; Length
0x1400919ae  mov     rdx, rbp; TargetMdl
0x1400919b1  call    cs:__imp_IoBuildPartialMdl
0x1400919b8  nop     dword ptr [rax+rax+00h]
0x1400919bd  mov     rax, [rdi+0A0h]
0x1400919c4  mov     rcx, [rax+50h]; MemoryDescriptorList
0x1400919c8  test    byte ptr [rcx+0Ah], 5
0x1400919cc  jz      short loc_1400919D4
0x1400919ce  mov     rax, [rcx+18h]
0x1400919d2  jmp     short loc_1400919F9
0x1400919d4  xor     r9d, r9d; RequestedAddress
0x1400919d7  mov     [rsp+68h+Priority], 40000010h; Priority
0x1400919df  xor     edx, edx; AccessMode
0x1400919e1  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400919e9  lea     r8d, [r9+1]; CacheType
0x1400919ed  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400919f4  nop     dword ptr [rax+rax+00h]
0x1400919f9  test    rax, rax
0x1400919fc  jnz     short loc_140091A09
0x1400919fe  mov     r9d, 699h
0x140091a04  jmp     loc_1400918FB
0x140091a09  mov     rax, [rdi+0A0h]
0x140091a10  mov     rcx, [rax+50h]; MemoryDescriptorList
0x140091a14  mov     [rdi+0C8h], rcx
0x140091a1b  test    rcx, rcx
0x140091a1e  jz      loc_140091B0E
0x140091a24  test    byte ptr [rcx+0Ah], 5
0x140091a28  jz      short loc_140091A30
0x140091a2a  mov     rax, [rcx+18h]
0x140091a2e  jmp     short loc_140091A55
0x140091a30  xor     r9d, r9d; RequestedAddress
0x140091a33  mov     [rsp+68h+Priority], 40000010h; Priority
0x140091a3b  xor     edx, edx; AccessMode
0x140091a3d  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140091a45  lea     r8d, [r9+1]; CacheType
0x140091a49  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140091a50  nop     dword ptr [rax+rax+00h]
0x140091a55  mov     [rdi+0D0h], rax
0x140091a5c  lea     rbx, [rsi+80h]
0x140091a63  mov     [rsi+98h], rsi
0x140091a6a  lea     rax, Srv2PostAfterReceivePrivateBuffer
0x140091a71  mov     [rsi+90h], rax
0x140091a78  lea     r9, aSmb2executedir_0; "Smb2ExecuteDirectPlacementWrite"
0x140091a7f  mov     dword ptr [rsi+84h], 0
0x140091a89  mov     r8d, 8E4h
0x140091a8f  mov     rax, [rdi+0D8h]
0x140091a96  mov     dl, 6
0x140091a98  neg     rax
0x140091a9b  mov     byte ptr [rsp+68h+BugCheckOnFailure], 1
0x140091aa0  mov     rax, [rsi+78h]
0x140091aa4  mov     [rsi+0A8h], rax
0x140091aab  sbb     ecx, ecx
0x140091aad  and     ecx, 200h
0x140091ab3  mov     [rsi+0B0h], ecx
0x140091ab9  lea     rcx, [rsi+248h]
0x140091ac0  mov     eax, [rdi+0FCh]
0x140091ac6  mov     [rbx], eax
0x140091ac8  mov     rax, [rdi+0C8h]
0x140091acf  mov     [rsi+88h], rax
0x140091ad6  lea     rax, Smb2ContinueDirectPlacementWrite
0x140091add  mov     [rsi+30h], rax
0x140091ae1  call    SRV2_PERF_ENTER_EX
0x140091ae6  mov     rcx, [rsi+60h]
0x140091aea  mov     r9, rbx
0x140091aed  mov     r8d, [rdi+108h]
0x140091af4  mov     rdx, [rdi+0D8h]
0x140091afb  mov     rcx, [rcx+1E0h]
0x140091b02  call    cs:__imp_SrvNetReadDirectData
0x140091b09  nop     dword ptr [rax+rax+00h]
0x140091b0e  add     rsp, 38h
0x140091b12  pop     r15
0x140091b14  pop     r14
0x140091b16  pop     rdi
0x140091b17  pop     rsi
0x140091b18  pop     rbp
0x140091b19  pop     rbx
0x140091b1a  retn
```
