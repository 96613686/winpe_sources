# SC_PACKET::Copy(SC_PACKET *,ulong,ulong)

- ea: `0x14001a410`
- end: `0x14001a700`
- name: `?Copy@SC_PACKET@@QEAAJPEAV1@KK@Z`
- size: `752`
- prototype: `int(SC_PACKET *__hidden this, struct SC_PACKET *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x140007010`

## callees

- `0x14001a410`
- `0x1400681c0`
- `0x1400684c0`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001a4b1`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14001a4b1`
- `ntoskrnl!IoAllocateMdl` at `0x14001a495`
- `ntoskrnl!IoAllocateMdl` at `0x14001a495`
- `ntoskrnl!ExAllocatePool2` at `0x14001a46a`
- `ntoskrnl!ExAllocatePool2` at `0x14001a46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006abcd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006abcd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a6ef`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001a6ef`
- `ntoskrnl!MmMdlPageContentsState` at `0x14001a4c6`
- `ntoskrnl!MmMdlPageContentsState` at `0x14001a4c6`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a5f1`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14001a5f1`
- `ntoskrnl!MmMapMdl` at `0x14001a523`
- `ntoskrnl!MmMapMdl` at `0x14001a523`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a580`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a66b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a694`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a580`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a66b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001a694`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a5be`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14001a5be`

## pseudocode

```c
__int64 __fastcall SC_PACKET::Copy(SC_PACKET *this, struct SC_PACKET *a2, unsigned int a3, unsigned int a4)
{
  size_t v5; // rsi
  __int64 v7; // r14
  unsigned int v8; // r15d
  void *Pool2; // rdi
  struct _MDL *Mdl; // rax
  __int64 v11; // rcx
  PVOID v12; // rax
  __int64 v13; // rcx
  __int64 result; // rax
  int v15; // ecx
  int v16; // r13d
  unsigned int v17; // edi
  PVOID v18; // rax
  __int64 v19; // rcx
  char *v20; // rdi
  __int64 v21; // rcx
  PVOID v22; // rax
  __int128 v23; // [rsp+30h] [rbp-48h] BYREF
  __int64 v24; // [rsp+40h] [rbp-38h]

  v5 = a4;
  v7 = a3;
  if ( a4 == *((_DWORD *)a2 + 36) )
    *((_DWORD *)this + 19) |= *((_DWORD *)a2 + 19) & 4;
  v8 = 0xFFFF;
  if ( a4 - 4096 <= 0x3F000 )
  {
    _BitScanReverse((unsigned int *)&v16, a4);
    if ( 1 << v16 != a4 )
      ++v16;
    v17 = *((_DWORD *)WPP_MAIN_CB.DeviceExtension + 84);
    v8 = v17 * (v16 - 12) + (unsigned __int8)(KeGetCurrentProcessorNumberEx(0) % v17);
    v18 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45)
                                                                   + ((unsigned __int64)v8 << 7)));
    Pool2 = v18;
    if ( !v18 )
      return 3221225626LL;
    memset(v18, 0, v5);
  }
  else
  {
    Pool2 = (void *)ExAllocatePool2(72, a4, 1715630163);
    if ( !Pool2 )
      return 3221225626LL;
  }
  Mdl = IoAllocateMdl(Pool2, v5, 0, 0, 0);
  *((_QWORD *)this + 15) = Mdl;
  if ( !Mdl )
  {
    if ( v8 == 0xFFFF )
      ExFreePoolWithTag(Pool2, 0);
    else
      ExFreeToNPagedLookasideList(
        (PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 45) + ((unsigned __int64)v8 << 7)),
        Pool2);
    return 3221225626LL;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  MmMdlPageContentsState(*((_QWORD *)this + 15), 1);
  *((_DWORD *)this + 28) = 3;
  *((_WORD *)this + 58) = v8;
  v11 = *((_QWORD *)this + 15);
  v23 = 0;
  v24 = 0;
  if ( (*(_BYTE *)(v11 + 10) & 5) != 0 )
    v12 = *(PVOID *)(v11 + 24);
  else
    v12 = MmMapLockedPagesSpecifyCache((PMDL)v11, 0, MmCached, 0, 0, 0x40000020u);
  v13 = *((_QWORD *)a2 + 15);
  *(_QWORD *)&v23 = v12;
  *((_QWORD *)&v23 + 1) = (unsigned int)v7;
  LODWORD(v24) = v5;
  result = MmMapMdl(v13, 4, SC_BUFFER::CopyCallback, &v23);
  if ( (int)result >= 0 )
    goto LABEL_9;
  v19 = *((_QWORD *)a2 + 15);
  if ( (*(_BYTE *)(v19 + 10) & 5) != 0 )
    v20 = *(char **)(v19 + 24);
  else
    v20 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v19, 0, MmCached, 0, 0, 0x40000020u);
  if ( !v20 )
    return 3221225626LL;
  v21 = *((_QWORD *)this + 15);
  if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
    v22 = *(PVOID *)(v21 + 24);
  else
    v22 = MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000020u);
  memmove(v22, &v20[v7], v5);
  result = 0;
LABEL_9:
  v15 = *((_DWORD *)a2 + 41);
  if ( v15 != -1 )
    *((_DWORD *)this + 41) = v7 + v15;
  return result;
}

```

## disassembly

```asm
0x14001a410  push    rbx
0x14001a412  push    rbp
0x14001a413  push    rsi
0x14001a414  push    r14
0x14001a416  push    r15
0x14001a418  sub     rsp, 50h
0x14001a41c  mov     rbp, rdx
0x14001a41f  mov     esi, r9d
0x14001a422  mov     rbx, rcx
0x14001a425  mov     r14d, r8d
0x14001a428  cmp     r9d, [rdx+90h]
0x14001a42f  jz      loc_14001A6A2
0x14001a435  lea     eax, [rsi-1000h]
0x14001a43b  mov     [rsp+78h+arg_0], rdi
0x14001a443  mov     [rsp+78h+arg_8], r12
0x14001a44b  mov     r15d, 0FFFFh
0x14001a451  cmp     eax, 3F000h
0x14001a456  jbe     loc_14001A591
0x14001a45c  mov     rdx, rsi
0x14001a45f  mov     ecx, 48h ; 'H'
0x14001a464  mov     r8d, 66427053h
0x14001a46a  call    cs:__imp_ExAllocatePool2
0x14001a471  nop     dword ptr [rax+rax+00h]
0x14001a476  mov     rdi, rax
0x14001a479  test    rax, rax
0x14001a47c  jz      loc_14001A611
0x14001a482  xor     r12d, r12d
0x14001a485  xor     r9d, r9d; ChargeQuota
0x14001a488  xor     r8d, r8d; SecondaryBuffer
0x14001a48b  mov     [rsp+78h+Irp], r12; Irp
0x14001a490  mov     edx, esi; Length
0x14001a492  mov     rcx, rdi; VirtualAddress
0x14001a495  call    cs:__imp_IoAllocateMdl
0x14001a49c  nop     dword ptr [rax+rax+00h]
0x14001a4a1  mov     [rbx+78h], rax
0x14001a4a5  test    rax, rax
0x14001a4a8  jz      loc_14001A6CA
0x14001a4ae  mov     rcx, rax; MemoryDescriptorList
0x14001a4b1  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14001a4b8  nop     dword ptr [rax+rax+00h]
0x14001a4bd  mov     rcx, [rbx+78h]
0x14001a4c1  mov     edx, 1
0x14001a4c6  call    cs:__imp_MmMdlPageContentsState
0x14001a4cd  nop     dword ptr [rax+rax+00h]
0x14001a4d2  mov     dword ptr [rbx+70h], 3
0x14001a4d9  xor     eax, eax
0x14001a4db  mov     [rbx+74h], r15w
0x14001a4e0  xorps   xmm0, xmm0
0x14001a4e3  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x14001a4e7  movups  [rsp+78h+var_48], xmm0
0x14001a4ec  mov     [rsp+78h+var_38], rax
0x14001a4f1  test    byte ptr [rcx+0Ah], 5
0x14001a4f5  jz      short loc_14001A568
0x14001a4f7  mov     rax, [rcx+18h]
0x14001a4fb  mov     rcx, [rbp+78h]
0x14001a4ff  lea     r9, [rsp+78h+var_48]
0x14001a504  lea     r8, ?CopyCallback@SC_BUFFER@@SAXPEAXPEAE@Z; SC_BUFFER::CopyCallback(void *,uchar *)
0x14001a50b  mov     qword ptr [rsp+78h+var_48], rax
0x14001a510  mov     edx, 4
0x14001a515  mov     dword ptr [rsp+78h+var_48+8], r14d
0x14001a51a  mov     dword ptr [rsp+78h+var_48+0Ch], r12d
0x14001a51f  mov     dword ptr [rsp+78h+var_38], esi
0x14001a523  call    cs:__imp_MmMapMdl
0x14001a52a  nop     dword ptr [rax+rax+00h]
0x14001a52f  test    eax, eax
0x14001a531  js      loc_14001A61B
0x14001a537  mov     ecx, [rbp+0A4h]
0x14001a53d  cmp     ecx, 0FFFFFFFFh
0x14001a540  jz      short loc_14001A54B
0x14001a542  add     ecx, r14d
0x14001a545  mov     [rbx+0A4h], ecx
0x14001a54b  mov     r12, [rsp+78h+arg_8]
0x14001a553  mov     rdi, [rsp+78h+arg_0]
0x14001a55b  add     rsp, 50h
0x14001a55f  pop     r15
0x14001a561  pop     r14
0x14001a563  pop     rsi
0x14001a564  pop     rbp
0x14001a565  pop     rbx
0x14001a566  retn
0x14001a568  mov     [rsp+78h+Priority], 40000020h; Priority
0x14001a570  xor     r9d, r9d; RequestedAddress
0x14001a573  xor     edx, edx; AccessMode
0x14001a575  mov     dword ptr [rsp+78h+Irp], r12d; BugCheckOnFailure
0x14001a57a  mov     r8d, 1; CacheType
0x14001a580  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001a587  nop     dword ptr [rax+rax+00h]
0x14001a58c  jmp     loc_14001A4FB
0x14001a591  mov     [rsp+78h+arg_10], r13
0x14001a599  mov     eax, 1
0x14001a59e  bsr     r13d, esi
0x14001a5a2  mov     ecx, r13d
0x14001a5a5  shl     eax, cl
0x14001a5a7  cmp     eax, esi
0x14001a5a9  jnz     loc_14001A6B0
0x14001a5af  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14001a5b6  xor     ecx, ecx; ProcNumber
0x14001a5b8  mov     edi, [rax+150h]
0x14001a5be  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14001a5c5  nop     dword ptr [rax+rax+00h]
0x14001a5ca  xor     edx, edx
0x14001a5cc  div     edi
0x14001a5ce  lea     eax, [r13-0Ch]
0x14001a5d2  imul    eax, edi
0x14001a5d5  movzx   r15d, dl
0x14001a5d9  add     r15d, eax
0x14001a5dc  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14001a5e3  mov     ecx, r15d
0x14001a5e6  shl     rcx, 7
0x14001a5ea  add     rcx, [rax+168h]; Lookaside
0x14001a5f1  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14001a5f8  nop     dword ptr [rax+rax+00h]
0x14001a5fd  mov     r13, [rsp+78h+arg_10]
0x14001a605  mov     rdi, rax
0x14001a608  test    rax, rax
0x14001a60b  jnz     loc_14001A6B8
0x14001a611  mov     eax, 0C000009Ah
0x14001a616  jmp     loc_14001A54B
0x14001a61b  mov     rcx, [rbp+78h]; MemoryDescriptorList
0x14001a61f  test    byte ptr [rcx+0Ah], 5
0x14001a623  jz      short loc_14001A653
0x14001a625  mov     rdi, [rcx+18h]
0x14001a629  test    rdi, rdi
0x14001a62c  jz      short loc_14001A611
0x14001a62e  mov     rcx, [rbx+78h]; MemoryDescriptorList
0x14001a632  test    byte ptr [rcx+0Ah], 5
0x14001a636  jz      short loc_14001A67C
0x14001a638  mov     rax, [rcx+18h]
0x14001a63c  mov     r8, rsi; Size
0x14001a63f  lea     rdx, [rdi+r14]; Src
0x14001a643  mov     rcx, rax; void *
0x14001a646  call    memmove
0x14001a64b  mov     eax, r12d
0x14001a64e  jmp     loc_14001A537
0x14001a653  mov     [rsp+78h+Priority], 40000020h; Priority
0x14001a65b  xor     r9d, r9d; RequestedAddress
0x14001a65e  xor     edx, edx; AccessMode
0x14001a660  mov     dword ptr [rsp+78h+Irp], r12d; BugCheckOnFailure
0x14001a665  mov     r8d, 1; CacheType
0x14001a66b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001a672  nop     dword ptr [rax+rax+00h]
0x14001a677  mov     rdi, rax
0x14001a67a  jmp     short loc_14001A629
0x14001a67c  mov     [rsp+78h+Priority], 40000020h; Priority
0x14001a684  xor     r9d, r9d; RequestedAddress
0x14001a687  xor     edx, edx; AccessMode
0x14001a689  mov     dword ptr [rsp+78h+Irp], r12d; BugCheckOnFailure
0x14001a68e  mov     r8d, 1; CacheType
0x14001a694  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001a69b  nop     dword ptr [rax+rax+00h]
0x14001a6a0  jmp     short loc_14001A63C
0x14001a6a2  mov     eax, [rdx+4Ch]
0x14001a6a5  and     eax, 4
0x14001a6a8  or      [rcx+4Ch], eax
0x14001a6ab  jmp     loc_14001A435
0x14001a6b0  inc     r13d
0x14001a6b3  jmp     loc_14001A5AF
0x14001a6b8  mov     r8, rsi; Size
0x14001a6bb  xor     edx, edx; Val
0x14001a6bd  mov     rcx, rax; void *
0x14001a6c0  call    memset
0x14001a6c5  jmp     loc_14001A482
0x14001a6ca  cmp     r15d, 0FFFFh
0x14001a6d1  jz      loc_14006ABC8
0x14001a6d7  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14001a6de  mov     rdx, rdi; Entry
0x14001a6e1  mov     ecx, r15d
0x14001a6e4  shl     rcx, 7
0x14001a6e8  add     rcx, [rax+168h]; Lookaside
0x14001a6ef  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001a6f6  nop     dword ptr [rax+rax+00h]
0x14001a6fb  jmp     loc_14001A611
0x14006abc8  xor     edx, edx; Tag
0x14006abca  mov     rcx, rdi; P
0x14006abcd  call    cs:__imp_ExFreePoolWithTag
0x14006abd4  nop     dword ptr [rax+rax+00h]
0x14006abd9  nop
0x14006abda  jmp     loc_14001A611
```
