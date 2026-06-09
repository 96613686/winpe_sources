# VsmmpHypercopyBackedSubranges

- ea: `0x14002a3a0`
- end: `0x14002a5c1`
- name: `VsmmpHypercopyBackedSubranges`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001d040`

## callees

- `0x140012bc0`
- `0x140015bfc`
- `0x140015cf4`
- `0x140022340`
- `0x14002a3a0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a470`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a470`
- `ntoskrnl!IoFreeMdl` at `0x14002a50e`
- `ntoskrnl!IoFreeMdl` at `0x14002a5a2`
- `ntoskrnl!IoFreeMdl` at `0x14002a50e`
- `ntoskrnl!IoFreeMdl` at `0x14002a5a2`
- `ntoskrnl!IoAllocateMdl` at `0x14002a40a`
- `ntoskrnl!IoAllocateMdl` at `0x14002a40a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a43b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a43b`
- `ntoskrnl!MmUnlockPages` at `0x14002a4ff`
- `ntoskrnl!MmUnlockPages` at `0x14002a58e`
- `ntoskrnl!MmUnlockPages` at `0x14002a4ff`
- `ntoskrnl!MmUnlockPages` at `0x14002a58e`

## pseudocode

```c
__int64 __fastcall VsmmpHypercopyBackedSubranges(char *a1, __int64 a2, __int64 a3, unsigned __int64 a4, char a5)
{
  unsigned __int64 v5; // rax
  char v7; // bl
  unsigned __int64 i; // r14
  __int64 v9; // rsi
  struct _MDL *Mdl; // rax
  struct _MDL *v11; // rdi
  unsigned int v12; // ebx
  char *MappedSystemVa; // rax
  char *v14; // r12
  char *v15; // r13
  unsigned int v16; // eax
  unsigned int v17; // ebx
  __int64 v19; // [rsp+88h] [rbp+10h]
  unsigned int v20; // [rsp+90h] [rbp+18h]

  v19 = a2;
  v5 = a4;
  v7 = a5;
  for ( i = 0; i < v5; i += 0x200000LL )
  {
    v9 = v5 - i;
    if ( v5 - i > 0x200000 )
      v9 = 0x200000;
    Mdl = IoAllocateMdl((PVOID)(i + a2), v9, 0, 0, 0);
    v11 = Mdl;
    if ( !Mdl )
    {
      v12 = -1073741670;
      goto LABEL_23;
    }
    MmProbeAndLockPages(Mdl, 1, (LOCK_OPERATION)(v7 == 0));
    if ( (v11->MdlFlags & 5) != 0 )
      MappedSystemVa = (char *)v11->MappedSystemVa;
    else
      MappedSystemVa = (char *)MmMapLockedPagesSpecifyCache(v11, 0, MmCached, 0, 0, 0x40000010u);
    if ( !MappedSystemVa )
    {
      v12 = -1073741670;
      goto LABEL_23;
    }
    v14 = MappedSystemVa;
    if ( !v7 )
      v14 = a1;
    v15 = a1;
    if ( !v7 )
      v15 = MappedSystemVa;
    v16 = 0;
    v20 = 0;
    if ( (_DWORD)v9 )
    {
      do
      {
        v17 = v9 - v16;
        if ( (unsigned int)v9 - v16 > 0x100000 )
          v17 = 0x100000;
        HviEnterKernelAperture();
        memmove(&v15[v20], &v14[v20], v17);
        HviLeaveKernelAperture();
        v16 = v20 + 0x100000;
        v20 = v16;
      }
      while ( v16 < (unsigned int)v9 );
      v7 = a5;
    }
    a1 += v9;
    MmUnlockPages(v11);
    IoFreeMdl(v11);
    v5 = a4;
    a2 = v19;
  }
  v12 = 0;
  v11 = 0;
LABEL_23:
  if ( v11 )
    IoFreeMdl(v11);
  return v12;
}

```

## disassembly

```asm
0x14002a3a0  mov     [rsp+arg_18], r9
0x14002a3a5  mov     byte ptr [rsp+arg_10], r8b
0x14002a3aa  mov     [rsp+arg_8], rdx
0x14002a3af  push    rbx
0x14002a3b0  push    rsi
0x14002a3b1  push    rdi
0x14002a3b2  push    r12
0x14002a3b4  push    r13
0x14002a3b6  push    r14
0x14002a3b8  push    r15
0x14002a3ba  sub     rsp, 40h
0x14002a3be  mov     rax, r9
0x14002a3c1  mov     r15, rcx
0x14002a3c4  mov     bl, [rsp+78h+arg_20]
0x14002a3cb  mov     ecx, 200000h
0x14002a3d0  mov     [rsp+78h+arg_0], 0
0x14002a3dc  xor     r14d, r14d
0x14002a3df  cmp     r14, rax
0x14002a3e2  jnb     loc_14002A580
0x14002a3e8  mov     rsi, rax
0x14002a3eb  sub     rsi, r14
0x14002a3ee  cmp     rcx, rsi
0x14002a3f1  cmovb   rsi, rcx
0x14002a3f5  lea     rcx, [r14+rdx]; VirtualAddress
0x14002a3f9  mov     [rsp+78h+Irp], 0; Irp
0x14002a402  xor     r9d, r9d; ChargeQuota
0x14002a405  xor     r8d, r8d; SecondaryBuffer
0x14002a408  mov     edx, esi; Length
0x14002a40a  call    cs:__imp_IoAllocateMdl
0x14002a411  nop     dword ptr [rax+rax+00h]
0x14002a416  mov     rdi, rax
0x14002a419  mov     [rsp+78h+var_48], rax
0x14002a41e  test    rax, rax
0x14002a421  jnz     short loc_14002A42D
0x14002a423  mov     ebx, 0C000009Ah
0x14002a428  jmp     loc_14002A586
0x14002a42d  xor     r8d, r8d
0x14002a430  test    bl, bl
0x14002a432  setz    r8b; Operation
0x14002a436  mov     dl, 1; AccessMode
0x14002a438  mov     rcx, rdi; MemoryDescriptorList
0x14002a43b  call    cs:__imp_MmProbeAndLockPages
0x14002a442  nop     dword ptr [rax+rax+00h]
0x14002a447  nop
0x14002a448  test    byte ptr [rdi+0Ah], 5
0x14002a44c  jz      short loc_14002A454
0x14002a44e  mov     rax, [rdi+18h]
0x14002a452  jmp     short loc_14002A47C
0x14002a454  mov     [rsp+78h+Priority], 40000010h; Priority
0x14002a45c  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x14002a464  xor     r9d, r9d; RequestedAddress
0x14002a467  xor     edx, edx; AccessMode
0x14002a469  lea     r8d, [r9+1]; CacheType
0x14002a46d  mov     rcx, rdi; MemoryDescriptorList
0x14002a470  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002a477  nop     dword ptr [rax+rax+00h]
0x14002a47c  test    rax, rax
0x14002a47f  jnz     short loc_14002A48B
0x14002a481  mov     ebx, 0C000009Ah
0x14002a486  jmp     loc_14002A586
0x14002a48b  mov     r12, rax
0x14002a48e  test    bl, bl
0x14002a490  cmovz   r12, r15
0x14002a494  mov     r13, r15
0x14002a497  cmovz   r13, rax
0x14002a49b  xor     eax, eax
0x14002a49d  mov     [rsp+78h+arg_10], eax
0x14002a4a4  test    esi, esi
0x14002a4a6  jz      short loc_14002A4F9
0x14002a4a8  mov     ebx, esi
0x14002a4aa  sub     ebx, eax
0x14002a4ac  mov     eax, 100000h
0x14002a4b1  cmp     ebx, eax
0x14002a4b3  cmova   ebx, eax
0x14002a4b6  call    HviEnterKernelAperture
0x14002a4bb  mov     eax, [rsp+78h+arg_10]
0x14002a4c2  mov     r8d, ebx; Size
0x14002a4c5  lea     rdx, [rax+r12]; Src
0x14002a4c9  lea     rcx, [rax+r13]; void *
0x14002a4cd  call    memmove
0x14002a4d2  call    HviLeaveKernelAperture
0x14002a4d7  mov     eax, [rsp+78h+arg_10]
0x14002a4de  mov     r8d, 100000h
0x14002a4e4  add     eax, r8d
0x14002a4e7  mov     [rsp+78h+arg_10], eax
0x14002a4ee  cmp     eax, esi
0x14002a4f0  jb      short loc_14002A4A8
0x14002a4f2  mov     bl, [rsp+78h+arg_20]
0x14002a4f9  add     r15, rsi
0x14002a4fc  mov     rcx, rdi; MemoryDescriptorList
0x14002a4ff  call    cs:__imp_MmUnlockPages
0x14002a506  nop     dword ptr [rax+rax+00h]
0x14002a50b  mov     rcx, rdi; Mdl
0x14002a50e  call    cs:__imp_IoFreeMdl
0x14002a515  nop     dword ptr [rax+rax+00h]
0x14002a51a  mov     ecx, 200000h
0x14002a51f  add     r14, rcx
0x14002a522  mov     rax, [rsp+78h+arg_18]
0x14002a52a  mov     rdx, [rsp+78h+arg_8]
0x14002a532  jmp     loc_14002A3DF
0x14002a537  mov     ebx, eax
0x14002a539  lea     rax, WPP_GLOBAL_Control
0x14002a540  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a547  cmp     rcx, rax
0x14002a54a  jz      short loc_14002A571
0x14002a54c  mov     eax, [rcx+2Ch]
0x14002a54f  test    al, 2
0x14002a551  jz      short loc_14002A571
0x14002a553  cmp     byte ptr [rcx+29h], 2
0x14002a557  jb      short loc_14002A571
0x14002a559  mov     edx, 0Dh
0x14002a55e  mov     r9d, ebx
0x14002a561  lea     r8, WPP_249c70fdd68d3ef0b70098d2ebbbf01f_Traceguids
0x14002a568  mov     rcx, [rcx+18h]
0x14002a56c  call    WPP_SF_d
0x14002a571  mov     rax, [rsp+78h+arg_0]
0x14002a579  mov     rdi, [rsp+78h+var_48]
0x14002a57e  jmp     short loc_14002A586
0x14002a580  xor     ebx, ebx
0x14002a582  xor     eax, eax
0x14002a584  xor     edi, edi
0x14002a586  test    rax, rax
0x14002a589  jz      short loc_14002A59A
0x14002a58b  mov     rcx, rdi; MemoryDescriptorList
0x14002a58e  call    cs:__imp_MmUnlockPages
0x14002a595  nop     dword ptr [rax+rax+00h]
0x14002a59a  test    rdi, rdi
0x14002a59d  jz      short loc_14002A5AE
0x14002a59f  mov     rcx, rdi; Mdl
0x14002a5a2  call    cs:__imp_IoFreeMdl
0x14002a5a9  nop     dword ptr [rax+rax+00h]
0x14002a5ae  mov     eax, ebx
0x14002a5b0  add     rsp, 40h
0x14002a5b4  pop     r15
0x14002a5b6  pop     r14
0x14002a5b8  pop     r13
0x14002a5ba  pop     r12
0x14002a5bc  pop     rdi
0x14002a5bd  pop     rsi
0x14002a5be  pop     rbx
0x14002a5bf  retn
```
