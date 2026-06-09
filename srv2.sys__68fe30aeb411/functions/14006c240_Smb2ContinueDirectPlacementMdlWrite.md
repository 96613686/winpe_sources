# Smb2ContinueDirectPlacementMdlWrite

- ea: `0x14006c240`
- end: `0x14006c4f1`
- name: `Smb2ContinueDirectPlacementMdlWrite`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14006c4f8`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x14006c240`
- `0x140091888`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c3e1`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c3e1`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006c3a5`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006c3a5`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006c38d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006c38d`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c2f0`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c353`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c2f0`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c353`
- `srvnet!SrvNetReadDirectData` at `0x14006c4d5`
- `srvnet!SrvNetReadDirectData` at `0x14006c4d5`

## string_xrefs

- `0x14006c311`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14006c455`: `Smb2ContinueDirectPlacementMdlWrite`

## pseudocode

```c
__int64 __fastcall Smb2ContinueDirectPlacementMdlWrite(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rsi
  bool v5; // zf
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rcx
  _QWORD *v8; // rbp
  ULONG v9; // ebx
  __int64 v10; // r14
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r9
  struct _MDL *v14; // r12
  __int64 v15; // r15
  __int64 v16; // rax
  __int64 v17; // r14
  void *v18; // r15
  _QWORD *BufferNoTransportHeader; // rax
  __int64 v20; // rcx
  PVOID v21; // rax
  _QWORD **v22; // r8
  _QWORD *i; // rcx
  bool v24; // cf
  ULONG BugCheckOnFailure; // [rsp+20h] [rbp-48h]

  v3 = *(_QWORD *)(a1 + 560);
  if ( *(int *)(*(_QWORD *)(a1 + 120) + 48LL) < 0 )
  {
    *(_BYTE *)(v3 + 280) &= ~1u;
    *(_QWORD *)(v3 + 200) = 0;
    return Smb2ExecuteDirectPlacementWrite(a1);
  }
  v5 = *(_QWORD *)(v3 + 200) == 0;
  *(_QWORD *)(v3 + 232) = 0;
  if ( v5 )
    *(_QWORD *)(v3 + 200) = *(_QWORD *)(*(_QWORD *)(a1 + 120) + 8LL);
  v6 = *(unsigned int *)(v3 + 248);
  v7 = *(_QWORD *)(*(_QWORD *)(a1 + 120) + 56LL);
  if ( v7 < v6 )
  {
    v8 = *(_QWORD **)(a1 + 560);
    v9 = v6 - v7;
    if ( v9 >= 0x1000
      || (*(_DWORD *)(v8[11] + 80LL) & 0x40) != 0
      || (v10 = *(unsigned int *)(v8[12] + 152LL), (unsigned int)v10 < 2) )
    {
      BufferNoTransportHeader = (_QWORD *)SrvNetAllocateBufferNoTransportHeader(v9);
      v8[20] = BufferNoTransportHeader;
      if ( !BufferNoTransportHeader )
      {
        v13 = 1676;
        goto LABEL_11;
      }
      v18 = (void *)BufferNoTransportHeader[3];
      v17 = BufferNoTransportHeader[10];
      v14 = (struct _MDL *)BufferNoTransportHeader[7];
    }
    else
    {
      v11 = SrvNetAllocateBufferNoTransportHeader((unsigned int)v10 + v9);
      v8[20] = v11;
      v12 = v11;
      if ( !v11 )
      {
        v13 = 1659;
        goto LABEL_11;
      }
      v14 = *(struct _MDL **)(v11 + 56);
      v15 = *(_QWORD *)(v11 + 24) + v10 - 1;
      v16 = -(int)v10;
      v17 = *(_QWORD *)(v12 + 80);
      v18 = (void *)(v16 & v15);
    }
    if ( (*(_BYTE *)(v17 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v17 + 24), (PMDL)v17);
    IoBuildPartialMdl(v14, (PMDL)v17, v18, v9);
    v20 = *(_QWORD *)(v8[20] + 80LL);
    if ( (*(_BYTE *)(v20 + 10) & 5) != 0 )
      v21 = *(PVOID *)(v20 + 24);
    else
      v21 = MmMapLockedPagesSpecifyCache((PMDL)v20, 0, MmCached, 0, 0, 0x40000010u);
    if ( v21 )
    {
      a2 = *(_QWORD **)(v8[20] + 80LL);
      goto LABEL_24;
    }
    v13 = 1689;
LABEL_11:
    Smb2SetError(a1, 3221225989LL, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\write.c", v13);
    Srv2CompleteWorkItem(a1, 0);
    a2 = 0;
LABEL_24:
    v22 = *(_QWORD ***)(v3 + 200);
    *(_QWORD *)(v3 + 232) = a2;
    for ( i = *v22; i; i = (_QWORD *)*i )
      v22 = (_QWORD **)i;
    *v22 = a2;
  }
  *(_QWORD *)(a1 + 152) = a1;
  *(_QWORD *)(a1 + 144) = Srv2PostAfterReceivePrivateBuffer;
  *(_DWORD *)(a1 + 132) = 0;
  v24 = *(_QWORD *)(v3 + 216) != 0;
  LOBYTE(BugCheckOnFailure) = 1;
  LOBYTE(a2) = 5;
  *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 120);
  *(_DWORD *)(a1 + 176) = v24 ? 0x200 : 0;
  *(_DWORD *)(a1 + 128) = *(_DWORD *)(v3 + 248);
  *(_QWORD *)(a1 + 136) = *(_QWORD *)(v3 + 200);
  *(_QWORD *)(a1 + 48) = Smb2CompleteDirectPlacementMdlWrite;
  SRV2_PERF_ENTER_EX(a1 + 584, a2, 2481, "Smb2ContinueDirectPlacementMdlWrite", BugCheckOnFailure);
  return SrvNetReadDirectData(
           *(_QWORD *)(*(_QWORD *)(a1 + 96) + 480LL),
           *(_QWORD *)(v3 + 216),
           *(unsigned int *)(v3 + 264),
           a1 + 128);
}

```

## disassembly

```asm
0x14006c240  push    rbx
0x14006c242  push    rbp
0x14006c243  push    rsi
0x14006c244  push    rdi
0x14006c245  push    r12
0x14006c247  push    r14
0x14006c249  push    r15
0x14006c24b  sub     rsp, 30h
0x14006c24f  mov     rax, [rcx+78h]
0x14006c253  mov     rdi, rcx
0x14006c256  mov     rsi, [rcx+230h]
0x14006c25d  cmp     dword ptr [rax+30h], 0
0x14006c261  jge     short loc_14006C27F
0x14006c263  and     byte ptr [rsi+118h], 0FEh
0x14006c26a  mov     qword ptr [rsi+0C8h], 0
0x14006c275  call    Smb2ExecuteDirectPlacementWrite
0x14006c27a  jmp     loc_14006C4E1
0x14006c27f  cmp     qword ptr [rsi+0C8h], 0
0x14006c287  mov     qword ptr [rsi+0E8h], 0
0x14006c292  jnz     short loc_14006C2A3
0x14006c294  mov     rax, [rcx+78h]
0x14006c298  mov     rcx, [rax+8]
0x14006c29c  mov     [rsi+0C8h], rcx
0x14006c2a3  mov     rax, [rdi+78h]
0x14006c2a7  mov     ebx, [rsi+0F8h]
0x14006c2ad  mov     rcx, [rax+38h]
0x14006c2b1  cmp     rcx, rbx
0x14006c2b4  jnb     loc_14006C42F
0x14006c2ba  mov     rbp, [rdi+230h]
0x14006c2c1  sub     ebx, ecx
0x14006c2c3  cmp     ebx, 1000h
0x14006c2c9  jnb     loc_14006C351
0x14006c2cf  mov     rax, [rbp+58h]
0x14006c2d3  mov     ecx, [rax+50h]
0x14006c2d6  test    cl, 40h
0x14006c2d9  jnz     short loc_14006C351
0x14006c2db  mov     rax, [rbp+60h]
0x14006c2df  mov     r14d, [rax+98h]
0x14006c2e6  cmp     r14d, 2
0x14006c2ea  jb      short loc_14006C351
0x14006c2ec  lea     ecx, [r14+rbx]
0x14006c2f0  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14006c2f7  nop     dword ptr [rax+rax+00h]
0x14006c2fc  mov     [rbp+0A0h], rax
0x14006c303  mov     rdx, rax
0x14006c306  test    rax, rax
0x14006c309  jnz     short loc_14006C336
0x14006c30b  mov     r9d, 67Bh
0x14006c311  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006c318  mov     edx, 0C0000205h
0x14006c31d  mov     rcx, rdi
0x14006c320  call    _Smb2SetError
0x14006c325  xor     edx, edx
0x14006c327  mov     rcx, rdi
0x14006c32a  call    Srv2CompleteWorkItem
0x14006c32f  xor     edx, edx
0x14006c331  jmp     loc_14006C408
0x14006c336  mov     r12, [rdx+38h]
0x14006c33a  lea     r15, [r14-1]
0x14006c33e  add     r15, [rax+18h]
0x14006c342  neg     r14d
0x14006c345  movsxd  rax, r14d
0x14006c348  mov     r14, [rdx+50h]
0x14006c34c  and     r15, rax
0x14006c34f  jmp     short loc_14006C37F
0x14006c351  mov     ecx, ebx
0x14006c353  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14006c35a  nop     dword ptr [rax+rax+00h]
0x14006c35f  mov     [rbp+0A0h], rax
0x14006c366  test    rax, rax
0x14006c369  jnz     short loc_14006C373
0x14006c36b  mov     r9d, 68Ch
0x14006c371  jmp     short loc_14006C311
0x14006c373  mov     r15, [rax+18h]
0x14006c377  mov     r14, [rax+50h]
0x14006c37b  mov     r12, [rax+38h]
0x14006c37f  test    byte ptr [r14+0Ah], 20h
0x14006c384  jz      short loc_14006C399
0x14006c386  mov     rcx, [r14+18h]; BaseAddress
0x14006c38a  mov     rdx, r14; MemoryDescriptorList
0x14006c38d  call    cs:__imp_MmUnmapLockedPages
0x14006c394  nop     dword ptr [rax+rax+00h]
0x14006c399  mov     r9d, ebx; Length
0x14006c39c  mov     r8, r15; VirtualAddress
0x14006c39f  mov     rdx, r14; TargetMdl
0x14006c3a2  mov     rcx, r12; SourceMdl
0x14006c3a5  call    cs:__imp_IoBuildPartialMdl
0x14006c3ac  nop     dword ptr [rax+rax+00h]
0x14006c3b1  mov     rax, [rbp+0A0h]
0x14006c3b8  mov     rcx, [rax+50h]; MemoryDescriptorList
0x14006c3bc  test    byte ptr [rcx+0Ah], 5
0x14006c3c0  jz      short loc_14006C3C8
0x14006c3c2  mov     rax, [rcx+18h]
0x14006c3c6  jmp     short loc_14006C3ED
0x14006c3c8  xor     r9d, r9d; RequestedAddress
0x14006c3cb  mov     [rsp+68h+Priority], 40000010h; Priority
0x14006c3d3  xor     edx, edx; AccessMode
0x14006c3d5  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006c3dd  lea     r8d, [r9+1]; CacheType
0x14006c3e1  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c3e8  nop     dword ptr [rax+rax+00h]
0x14006c3ed  test    rax, rax
0x14006c3f0  jnz     short loc_14006C3FD
0x14006c3f2  mov     r9d, 699h
0x14006c3f8  jmp     loc_14006C311
0x14006c3fd  mov     rax, [rbp+0A0h]
0x14006c404  mov     rdx, [rax+50h]
0x14006c408  mov     r8, [rsi+0C8h]
0x14006c40f  mov     [rsi+0E8h], rdx
0x14006c416  mov     rcx, [r8]
0x14006c419  test    rcx, rcx
0x14006c41c  jz      short loc_14006C42C
0x14006c41e  mov     rax, [rcx]
0x14006c421  mov     r8, rcx
0x14006c424  mov     rcx, rax
0x14006c427  test    rax, rax
0x14006c42a  jnz     short loc_14006C41E
0x14006c42c  mov     [r8], rdx
0x14006c42f  mov     [rdi+98h], rdi
0x14006c436  lea     rax, Srv2PostAfterReceivePrivateBuffer
0x14006c43d  mov     [rdi+90h], rax
0x14006c444  lea     rbx, [rdi+80h]
0x14006c44b  mov     dword ptr [rdi+84h], 0
0x14006c455  lea     r9, aSmb2continuedi_0; "Smb2ContinueDirectPlacementMdlWrite"
0x14006c45c  mov     rax, [rsi+0D8h]
0x14006c463  mov     r8d, 9B1h
0x14006c469  neg     rax
0x14006c46c  mov     byte ptr [rsp+68h+BugCheckOnFailure], 1
0x14006c471  mov     rax, [rdi+78h]
0x14006c475  mov     dl, 5
0x14006c477  mov     [rdi+0A8h], rax
0x14006c47e  sbb     ecx, ecx
0x14006c480  and     ecx, 200h
0x14006c486  mov     [rdi+0B0h], ecx
0x14006c48c  lea     rcx, [rdi+248h]
0x14006c493  mov     eax, [rsi+0F8h]
0x14006c499  mov     [rbx], eax
0x14006c49b  mov     rax, [rsi+0C8h]
0x14006c4a2  mov     [rdi+88h], rax
0x14006c4a9  lea     rax, Smb2CompleteDirectPlacementMdlWrite
0x14006c4b0  mov     [rdi+30h], rax
0x14006c4b4  call    SRV2_PERF_ENTER_EX
0x14006c4b9  mov     rcx, [rdi+60h]
0x14006c4bd  mov     r9, rbx
0x14006c4c0  mov     r8d, [rsi+108h]
0x14006c4c7  mov     rdx, [rsi+0D8h]
0x14006c4ce  mov     rcx, [rcx+1E0h]
0x14006c4d5  call    cs:__imp_SrvNetReadDirectData
0x14006c4dc  nop     dword ptr [rax+rax+00h]
0x14006c4e1  add     rsp, 30h
0x14006c4e5  pop     r15
0x14006c4e7  pop     r14
0x14006c4e9  pop     r12
0x14006c4eb  pop     rdi
0x14006c4ec  pop     rsi
0x14006c4ed  pop     rbp
0x14006c4ee  pop     rbx
0x14006c4ef  retn
```
