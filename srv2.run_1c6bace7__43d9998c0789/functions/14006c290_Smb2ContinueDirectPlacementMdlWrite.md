# Smb2ContinueDirectPlacementMdlWrite

- ea: `0x14006c290`
- end: `0x14006c541`
- name: `Smb2ContinueDirectPlacementMdlWrite`
- size: `689`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14006c548`

## callees

- `0x140005070`
- `0x140007400`
- `0x140008190`
- `0x14006c290`
- `0x1400918d8`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c431`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14006c431`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006c3f5`
- `ntoskrnl!IoBuildPartialMdl` at `0x14006c3f5`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006c3dd`
- `ntoskrnl!MmUnmapLockedPages` at `0x14006c3dd`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c340`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c3a3`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c340`
- `srvnet!SrvNetAllocateBufferNoTransportHeader` at `0x14006c3a3`
- `srvnet!SrvNetReadDirectData` at `0x14006c525`
- `srvnet!SrvNetReadDirectData` at `0x14006c525`

## string_xrefs

- `0x14006c361`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\write.c`
- `0x14006c4a5`: `Smb2ContinueDirectPlacementMdlWrite`

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
0x14006c290  push    rbx
0x14006c292  push    rbp
0x14006c293  push    rsi
0x14006c294  push    rdi
0x14006c295  push    r12
0x14006c297  push    r14
0x14006c299  push    r15
0x14006c29b  sub     rsp, 30h
0x14006c29f  mov     rax, [rcx+78h]
0x14006c2a3  mov     rdi, rcx
0x14006c2a6  mov     rsi, [rcx+230h]
0x14006c2ad  cmp     dword ptr [rax+30h], 0
0x14006c2b1  jge     short loc_14006C2CF
0x14006c2b3  and     byte ptr [rsi+118h], 0FEh
0x14006c2ba  mov     qword ptr [rsi+0C8h], 0
0x14006c2c5  call    Smb2ExecuteDirectPlacementWrite
0x14006c2ca  jmp     loc_14006C531
0x14006c2cf  cmp     qword ptr [rsi+0C8h], 0
0x14006c2d7  mov     qword ptr [rsi+0E8h], 0
0x14006c2e2  jnz     short loc_14006C2F3
0x14006c2e4  mov     rax, [rcx+78h]
0x14006c2e8  mov     rcx, [rax+8]
0x14006c2ec  mov     [rsi+0C8h], rcx
0x14006c2f3  mov     rax, [rdi+78h]
0x14006c2f7  mov     ebx, [rsi+0F8h]
0x14006c2fd  mov     rcx, [rax+38h]
0x14006c301  cmp     rcx, rbx
0x14006c304  jnb     loc_14006C47F
0x14006c30a  mov     rbp, [rdi+230h]
0x14006c311  sub     ebx, ecx
0x14006c313  cmp     ebx, 1000h
0x14006c319  jnb     loc_14006C3A1
0x14006c31f  mov     rax, [rbp+58h]
0x14006c323  mov     ecx, [rax+50h]
0x14006c326  test    cl, 40h
0x14006c329  jnz     short loc_14006C3A1
0x14006c32b  mov     rax, [rbp+60h]
0x14006c32f  mov     r14d, [rax+98h]
0x14006c336  cmp     r14d, 2
0x14006c33a  jb      short loc_14006C3A1
0x14006c33c  lea     ecx, [r14+rbx]
0x14006c340  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14006c347  nop     dword ptr [rax+rax+00h]
0x14006c34c  mov     [rbp+0A0h], rax
0x14006c353  mov     rdx, rax
0x14006c356  test    rax, rax
0x14006c359  jnz     short loc_14006C386
0x14006c35b  mov     r9d, 67Bh
0x14006c361  lea     r8, aOnecoreBaseFsR_1; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006c368  mov     edx, 0C0000205h
0x14006c36d  mov     rcx, rdi
0x14006c370  call    _Smb2SetError
0x14006c375  xor     edx, edx
0x14006c377  mov     rcx, rdi
0x14006c37a  call    Srv2CompleteWorkItem
0x14006c37f  xor     edx, edx
0x14006c381  jmp     loc_14006C458
0x14006c386  mov     r12, [rdx+38h]
0x14006c38a  lea     r15, [r14-1]
0x14006c38e  add     r15, [rax+18h]
0x14006c392  neg     r14d
0x14006c395  movsxd  rax, r14d
0x14006c398  mov     r14, [rdx+50h]
0x14006c39c  and     r15, rax
0x14006c39f  jmp     short loc_14006C3CF
0x14006c3a1  mov     ecx, ebx
0x14006c3a3  call    cs:__imp_SrvNetAllocateBufferNoTransportHeader
0x14006c3aa  nop     dword ptr [rax+rax+00h]
0x14006c3af  mov     [rbp+0A0h], rax
0x14006c3b6  test    rax, rax
0x14006c3b9  jnz     short loc_14006C3C3
0x14006c3bb  mov     r9d, 68Ch
0x14006c3c1  jmp     short loc_14006C361
0x14006c3c3  mov     r15, [rax+18h]
0x14006c3c7  mov     r14, [rax+50h]
0x14006c3cb  mov     r12, [rax+38h]
0x14006c3cf  test    byte ptr [r14+0Ah], 20h
0x14006c3d4  jz      short loc_14006C3E9
0x14006c3d6  mov     rcx, [r14+18h]; BaseAddress
0x14006c3da  mov     rdx, r14; MemoryDescriptorList
0x14006c3dd  call    cs:__imp_MmUnmapLockedPages
0x14006c3e4  nop     dword ptr [rax+rax+00h]
0x14006c3e9  mov     r9d, ebx; Length
0x14006c3ec  mov     r8, r15; VirtualAddress
0x14006c3ef  mov     rdx, r14; TargetMdl
0x14006c3f2  mov     rcx, r12; SourceMdl
0x14006c3f5  call    cs:__imp_IoBuildPartialMdl
0x14006c3fc  nop     dword ptr [rax+rax+00h]
0x14006c401  mov     rax, [rbp+0A0h]
0x14006c408  mov     rcx, [rax+50h]; MemoryDescriptorList
0x14006c40c  test    byte ptr [rcx+0Ah], 5
0x14006c410  jz      short loc_14006C418
0x14006c412  mov     rax, [rcx+18h]
0x14006c416  jmp     short loc_14006C43D
0x14006c418  xor     r9d, r9d; RequestedAddress
0x14006c41b  mov     [rsp+68h+Priority], 40000010h; Priority
0x14006c423  xor     edx, edx; AccessMode
0x14006c425  mov     [rsp+68h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14006c42d  lea     r8d, [r9+1]; CacheType
0x14006c431  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14006c438  nop     dword ptr [rax+rax+00h]
0x14006c43d  test    rax, rax
0x14006c440  jnz     short loc_14006C44D
0x14006c442  mov     r9d, 699h
0x14006c448  jmp     loc_14006C361
0x14006c44d  mov     rax, [rbp+0A0h]
0x14006c454  mov     rdx, [rax+50h]
0x14006c458  mov     r8, [rsi+0C8h]
0x14006c45f  mov     [rsi+0E8h], rdx
0x14006c466  mov     rcx, [r8]
0x14006c469  test    rcx, rcx
0x14006c46c  jz      short loc_14006C47C
0x14006c46e  mov     rax, [rcx]
0x14006c471  mov     r8, rcx
0x14006c474  mov     rcx, rax
0x14006c477  test    rax, rax
0x14006c47a  jnz     short loc_14006C46E
0x14006c47c  mov     [r8], rdx
0x14006c47f  mov     [rdi+98h], rdi
0x14006c486  lea     rax, Srv2PostAfterReceivePrivateBuffer
0x14006c48d  mov     [rdi+90h], rax
0x14006c494  lea     rbx, [rdi+80h]
0x14006c49b  mov     dword ptr [rdi+84h], 0
0x14006c4a5  lea     r9, aSmb2continuedi_0; "Smb2ContinueDirectPlacementMdlWrite"
0x14006c4ac  mov     rax, [rsi+0D8h]
0x14006c4b3  mov     r8d, 9B1h
0x14006c4b9  neg     rax
0x14006c4bc  mov     byte ptr [rsp+68h+BugCheckOnFailure], 1
0x14006c4c1  mov     rax, [rdi+78h]
0x14006c4c5  mov     dl, 5
0x14006c4c7  mov     [rdi+0A8h], rax
0x14006c4ce  sbb     ecx, ecx
0x14006c4d0  and     ecx, 200h
0x14006c4d6  mov     [rdi+0B0h], ecx
0x14006c4dc  lea     rcx, [rdi+248h]
0x14006c4e3  mov     eax, [rsi+0F8h]
0x14006c4e9  mov     [rbx], eax
0x14006c4eb  mov     rax, [rsi+0C8h]
0x14006c4f2  mov     [rdi+88h], rax
0x14006c4f9  lea     rax, Smb2CompleteDirectPlacementMdlWrite
0x14006c500  mov     [rdi+30h], rax
0x14006c504  call    SRV2_PERF_ENTER_EX
0x14006c509  mov     rcx, [rdi+60h]
0x14006c50d  mov     r9, rbx
0x14006c510  mov     r8d, [rsi+108h]
0x14006c517  mov     rdx, [rsi+0D8h]
0x14006c51e  mov     rcx, [rcx+1E0h]
0x14006c525  call    cs:__imp_SrvNetReadDirectData
0x14006c52c  nop     dword ptr [rax+rax+00h]
0x14006c531  add     rsp, 30h
0x14006c535  pop     r15
0x14006c537  pop     r14
0x14006c539  pop     r12
0x14006c53b  pop     rdi
0x14006c53c  pop     rsi
0x14006c53d  pop     rbp
0x14006c53e  pop     rbx
0x14006c53f  retn
```
