# Smb2ExecuteDirectPlacementWrite

- ea: `0x1400918d8`
- end: `0x140091b6c`
- name: `Smb2ExecuteDirectPlacementWrite`
- size: `660`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14006c290`
- `0x14007e390`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x1400918d8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a3d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a99`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a3d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140091a99`
- `ntoskrnl!IoBuildPartialMdl` at `0x140091a01`
- `ntoskrnl!IoBuildPartialMdl` at `0x140091a01`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091996`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400919e9`
- `ntoskrnl!MmUnmapLockedPages` at `0x140091996`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400919e9`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14009192a`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400919ad`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14009192a`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x1400919ad`
- `srvnet!SrvNetReadDirectData` at `0x140091b52`
- `srvnet!SrvNetReadDirectData` at `0x140091b52`

## string_xrefs

- `0x14009194b`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x140091ac8`: `Smb2ExecuteDirectPlacementWrite`

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
0x1400918d8  push    rbx
0x1400918da  push    rbp
0x1400918db  push    rsi
0x1400918dc  push    rdi
0x1400918dd  push    r14
0x1400918df  push    r15
0x1400918e1  sub     rsp, 38h
0x1400918e5  mov     rdi, [rcx+230h]
0x1400918ec  mov     rsi, rcx
0x1400918ef  mov     ebx, [rdi+0FCh]
0x1400918f5  cmp     ebx, 1000h
0x1400918fb  jnb     loc_1400919AA
0x140091901  mov     rax, [rdi+58h]
0x140091905  mov     edx, [rax+50h]
0x140091908  test    dl, 40h
0x14009190b  jnz     loc_1400919AA
0x140091911  mov     rax, [rdi+60h]
0x140091915  mov     r14d, [rax+98h]
0x14009191c  cmp     r14d, 2
0x140091920  jb      loc_1400919AA
0x140091926  lea     ecx, [r14+rbx]
0x14009192a  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x140091931  nop     dword ptr [rax+rax+00h]
0x140091936  mov     [rdi+0A0h], rax
0x14009193d  mov     rdx, rax
0x140091940  test    rax, rax
0x140091943  jnz     short loc_140091970
0x140091945  mov     r9d, 67Bh
0x14009194b  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x140091952  mov     edx, 0C0000205h
0x140091957  mov     rcx, rsi
0x14009195a  call    _Smb2SetError
0x14009195f  xor     edx, edx
0x140091961  mov     rcx, rsi
0x140091964  call    Srv2CompleteWorkItem
0x140091969  xor     ecx, ecx
0x14009196b  jmp     loc_140091A64
0x140091970  mov     rbp, [rdx+50h]
0x140091974  lea     r15, [r14-1]
0x140091978  add     r15, [rax+18h]
0x14009197c  neg     r14d
0x14009197f  movsxd  rax, r14d
0x140091982  mov     r14, [rdx+38h]
0x140091986  and     r15, rax
0x140091989  test    byte ptr [rbp+0Ah], 20h
0x14009198d  jz      short loc_1400919A2
0x14009198f  mov     rcx, [rbp+18h]; BaseAddress
0x140091993  mov     rdx, rbp; MemoryDescriptorList
0x140091996  call    cs:__imp_MmUnmapLockedPages
0x14009199d  nop     dword ptr [rax+rax+00h]
0x1400919a2  mov     r8, r15
0x1400919a5  mov     rcx, r14
0x1400919a8  jmp     short loc_1400919FB
0x1400919aa  mov     rcx, rbx
0x1400919ad  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x1400919b4  nop     dword ptr [rax+rax+00h]
0x1400919b9  mov     [rdi+0A0h], rax
0x1400919c0  test    rax, rax
0x1400919c3  jnz     short loc_1400919D0
0x1400919c5  mov     r9d, 68Ch
0x1400919cb  jmp     loc_14009194B
0x1400919d0  mov     rbp, [rax+50h]
0x1400919d4  mov     r14, [rax+18h]
0x1400919d8  mov     r15, [rax+38h]
0x1400919dc  test    byte ptr [rbp+0Ah], 20h
0x1400919e0  jz      short loc_1400919F5
0x1400919e2  mov     rcx, [rbp+18h]; BaseAddress
0x1400919e6  mov     rdx, rbp; MemoryDescriptorList
0x1400919e9  call    cs:__imp_MmUnmapLockedPages
0x1400919f0  nop     dword ptr [rax+rax+00h]
0x1400919f5  mov     r8, r14; VirtualAddress
0x1400919f8  mov     rcx, r15; SourceMdl
0x1400919fb  mov     r9d, ebx; Length
0x1400919fe  mov     rdx, rbp; TargetMdl
0x140091a01  call    cs:__imp_IoBuildPartialMdl
0x140091a08  nop     dword ptr [rax+rax+00h]
0x140091a0d  mov     rax, [rdi+0A0h]
0x140091a14  mov     rcx, [rax+50h]; MemoryDescriptorList
0x140091a18  test    byte ptr [rcx+0Ah], 5
0x140091a1c  jz      short loc_140091A24
0x140091a1e  mov     rax, [rcx+18h]
0x140091a22  jmp     short loc_140091A49
0x140091a24  xor     r9d, r9d; RequestedAddress
0x140091a27  mov     [rsp+68h+Priority], 40000010h; Priority
0x140091a2f  xor     edx, edx; AccessMode
0x140091a31  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140091a39  lea     r8d, [r9+1]; CacheType
0x140091a3d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140091a44  nop     dword ptr [rax+rax+00h]
0x140091a49  test    rax, rax
0x140091a4c  jnz     short loc_140091A59
0x140091a4e  mov     r9d, 699h
0x140091a54  jmp     loc_14009194B
0x140091a59  mov     rax, [rdi+0A0h]
0x140091a60  mov     rcx, [rax+50h]; MemoryDescriptorList
0x140091a64  mov     [rdi+0C8h], rcx
0x140091a6b  test    rcx, rcx
0x140091a6e  jz      loc_140091B5E
0x140091a74  test    byte ptr [rcx+0Ah], 5
0x140091a78  jz      short loc_140091A80
0x140091a7a  mov     rax, [rcx+18h]
0x140091a7e  jmp     short loc_140091AA5
0x140091a80  xor     r9d, r9d; RequestedAddress
0x140091a83  mov     [rsp+68h+Priority], 40000010h; Priority
0x140091a8b  xor     edx, edx; AccessMode
0x140091a8d  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140091a95  lea     r8d, [r9+1]; CacheType
0x140091a99  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140091aa0  nop     dword ptr [rax+rax+00h]
0x140091aa5  mov     [rdi+0D0h], rax
0x140091aac  lea     rbx, [rsi+80h]
0x140091ab3  mov     [rsi+98h], rsi
0x140091aba  lea     rax, Srv2PostAfterReceivePrivateBuffer
0x140091ac1  mov     [rsi+90h], rax
0x140091ac8  lea     r9, aSmb2executedir_0; "Smb2ExecuteDirectPlacementWrite"
0x140091acf  mov     dword ptr [rsi+84h], 0
0x140091ad9  mov     r8d, 8E4h
0x140091adf  mov     rax, [rdi+0D8h]
0x140091ae6  mov     dl, 6
0x140091ae8  neg     rax
0x140091aeb  mov     byte ptr [rsp+68h+BugCheckOnFailure], 1
0x140091af0  mov     rax, [rsi+78h]
0x140091af4  mov     [rsi+0A8h], rax
0x140091afb  sbb     ecx, ecx
0x140091afd  and     ecx, 200h
0x140091b03  mov     [rsi+0B0h], ecx
0x140091b09  lea     rcx, [rsi+248h]
0x140091b10  mov     eax, [rdi+0FCh]
0x140091b16  mov     [rbx], eax
0x140091b18  mov     rax, [rdi+0C8h]
0x140091b1f  mov     [rsi+88h], rax
0x140091b26  lea     rax, Smb2ContinueDirectPlacementWrite
0x140091b2d  mov     [rsi+30h], rax
0x140091b31  call    SRV2_PERF_ENTER_EX
0x140091b36  mov     rcx, [rsi+60h]
0x140091b3a  mov     r9, rbx
0x140091b3d  mov     r8d, [rdi+108h]
0x140091b44  mov     rdx, [rdi+0D8h]
0x140091b4b  mov     rcx, [rcx+1E0h]
0x140091b52  call    cs:__imp_SrvNetReadDirectData
0x140091b59  nop     dword ptr [rax+rax+00h]
0x140091b5e  add     rsp, 38h
0x140091b62  pop     r15
0x140091b64  pop     r14
0x140091b66  pop     rdi
0x140091b67  pop     rsi
0x140091b68  pop     rbp
0x140091b69  pop     rbx
0x140091b6a  retn
```
