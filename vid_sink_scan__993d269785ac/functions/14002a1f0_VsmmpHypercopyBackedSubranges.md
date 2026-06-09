# VsmmpHypercopyBackedSubranges

- ea: `0x14002a1f0`
- end: `0x14002a411`
- name: `VsmmpHypercopyBackedSubranges`
- size: `545`
- prototype: `__int64 __fastcall(char *, __int64, __int64, unsigned __int64, char)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14001a960`

## callees

- `0x140012b3c`
- `0x140015d4c`
- `0x140015e44`
- `0x140021d40`
- `0x14002a1f0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a2c0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002a2c0`
- `ntoskrnl!IoFreeMdl` at `0x14002a35e`
- `ntoskrnl!IoFreeMdl` at `0x14002a3f2`
- `ntoskrnl!IoFreeMdl` at `0x14002a35e`
- `ntoskrnl!IoFreeMdl` at `0x14002a3f2`
- `ntoskrnl!IoAllocateMdl` at `0x14002a25a`
- `ntoskrnl!IoAllocateMdl` at `0x14002a25a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a28b`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002a28b`
- `ntoskrnl!MmUnlockPages` at `0x14002a34f`
- `ntoskrnl!MmUnlockPages` at `0x14002a3de`
- `ntoskrnl!MmUnlockPages` at `0x14002a34f`
- `ntoskrnl!MmUnlockPages` at `0x14002a3de`

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
0x14002a1f0  mov     [rsp+arg_18], r9
0x14002a1f5  mov     byte ptr [rsp+arg_10], r8b
0x14002a1fa  mov     [rsp+arg_8], rdx
0x14002a1ff  push    rbx
0x14002a200  push    rsi
0x14002a201  push    rdi
0x14002a202  push    r12
0x14002a204  push    r13
0x14002a206  push    r14
0x14002a208  push    r15
0x14002a20a  sub     rsp, 40h
0x14002a20e  mov     rax, r9
0x14002a211  mov     r15, rcx
0x14002a214  mov     bl, [rsp+78h+arg_20]
0x14002a21b  mov     ecx, 200000h
0x14002a220  mov     [rsp+78h+arg_0], 0
0x14002a22c  xor     r14d, r14d
0x14002a22f  cmp     r14, rax
0x14002a232  jnb     loc_14002A3D0
0x14002a238  mov     rsi, rax
0x14002a23b  sub     rsi, r14
0x14002a23e  cmp     rcx, rsi
0x14002a241  cmovb   rsi, rcx
0x14002a245  lea     rcx, [r14+rdx]; VirtualAddress
0x14002a249  mov     [rsp+78h+Irp], 0; Irp
0x14002a252  xor     r9d, r9d; ChargeQuota
0x14002a255  xor     r8d, r8d; SecondaryBuffer
0x14002a258  mov     edx, esi; Length
0x14002a25a  call    cs:__imp_IoAllocateMdl
0x14002a261  nop     dword ptr [rax+rax+00h]
0x14002a266  mov     rdi, rax
0x14002a269  mov     [rsp+78h+var_48], rax
0x14002a26e  test    rax, rax
0x14002a271  jnz     short loc_14002A27D
0x14002a273  mov     ebx, 0C000009Ah
0x14002a278  jmp     loc_14002A3D6
0x14002a27d  xor     r8d, r8d
0x14002a280  test    bl, bl
0x14002a282  setz    r8b; Operation
0x14002a286  mov     dl, 1; AccessMode
0x14002a288  mov     rcx, rdi; MemoryDescriptorList
0x14002a28b  call    cs:__imp_MmProbeAndLockPages
0x14002a292  nop     dword ptr [rax+rax+00h]
0x14002a297  nop
0x14002a298  test    byte ptr [rdi+0Ah], 5
0x14002a29c  jz      short loc_14002A2A4
0x14002a29e  mov     rax, [rdi+18h]
0x14002a2a2  jmp     short loc_14002A2CC
0x14002a2a4  mov     [rsp+78h+Priority], 40000010h; Priority
0x14002a2ac  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x14002a2b4  xor     r9d, r9d; RequestedAddress
0x14002a2b7  xor     edx, edx; AccessMode
0x14002a2b9  lea     r8d, [r9+1]; CacheType
0x14002a2bd  mov     rcx, rdi; MemoryDescriptorList
0x14002a2c0  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002a2c7  nop     dword ptr [rax+rax+00h]
0x14002a2cc  test    rax, rax
0x14002a2cf  jnz     short loc_14002A2DB
0x14002a2d1  mov     ebx, 0C000009Ah
0x14002a2d6  jmp     loc_14002A3D6
0x14002a2db  mov     r12, rax
0x14002a2de  test    bl, bl
0x14002a2e0  cmovz   r12, r15
0x14002a2e4  mov     r13, r15
0x14002a2e7  cmovz   r13, rax
0x14002a2eb  xor     eax, eax
0x14002a2ed  mov     [rsp+78h+arg_10], eax
0x14002a2f4  test    esi, esi
0x14002a2f6  jz      short loc_14002A349
0x14002a2f8  mov     ebx, esi
0x14002a2fa  sub     ebx, eax
0x14002a2fc  mov     eax, 100000h
0x14002a301  cmp     ebx, eax
0x14002a303  cmova   ebx, eax
0x14002a306  call    HviEnterKernelAperture
0x14002a30b  mov     eax, [rsp+78h+arg_10]
0x14002a312  mov     r8d, ebx; Size
0x14002a315  lea     rdx, [rax+r12]; Src
0x14002a319  lea     rcx, [rax+r13]; void *
0x14002a31d  call    memmove
0x14002a322  call    HviLeaveKernelAperture
0x14002a327  mov     eax, [rsp+78h+arg_10]
0x14002a32e  mov     r8d, 100000h
0x14002a334  add     eax, r8d
0x14002a337  mov     [rsp+78h+arg_10], eax
0x14002a33e  cmp     eax, esi
0x14002a340  jb      short loc_14002A2F8
0x14002a342  mov     bl, [rsp+78h+arg_20]
0x14002a349  add     r15, rsi
0x14002a34c  mov     rcx, rdi; MemoryDescriptorList
0x14002a34f  call    cs:__imp_MmUnlockPages
0x14002a356  nop     dword ptr [rax+rax+00h]
0x14002a35b  mov     rcx, rdi; Mdl
0x14002a35e  call    cs:__imp_IoFreeMdl
0x14002a365  nop     dword ptr [rax+rax+00h]
0x14002a36a  mov     ecx, 200000h
0x14002a36f  add     r14, rcx
0x14002a372  mov     rax, [rsp+78h+arg_18]
0x14002a37a  mov     rdx, [rsp+78h+arg_8]
0x14002a382  jmp     loc_14002A22F
0x14002a387  mov     ebx, eax
0x14002a389  lea     rax, WPP_GLOBAL_Control
0x14002a390  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a397  cmp     rcx, rax
0x14002a39a  jz      short loc_14002A3C1
0x14002a39c  mov     eax, [rcx+2Ch]
0x14002a39f  test    al, 2
0x14002a3a1  jz      short loc_14002A3C1
0x14002a3a3  cmp     byte ptr [rcx+29h], 2
0x14002a3a7  jb      short loc_14002A3C1
0x14002a3a9  mov     edx, 0Dh
0x14002a3ae  mov     r9d, ebx
0x14002a3b1  lea     r8, WPP_249c70fdd68d3ef0b70098d2ebbbf01f_Traceguids
0x14002a3b8  mov     rcx, [rcx+18h]
0x14002a3bc  call    WPP_SF_d
0x14002a3c1  mov     rax, [rsp+78h+arg_0]
0x14002a3c9  mov     rdi, [rsp+78h+var_48]
0x14002a3ce  jmp     short loc_14002A3D6
0x14002a3d0  xor     ebx, ebx
0x14002a3d2  xor     eax, eax
0x14002a3d4  xor     edi, edi
0x14002a3d6  test    rax, rax
0x14002a3d9  jz      short loc_14002A3EA
0x14002a3db  mov     rcx, rdi; MemoryDescriptorList
0x14002a3de  call    cs:__imp_MmUnlockPages
0x14002a3e5  nop     dword ptr [rax+rax+00h]
0x14002a3ea  test    rdi, rdi
0x14002a3ed  jz      short loc_14002A3FE
0x14002a3ef  mov     rcx, rdi; Mdl
0x14002a3f2  call    cs:__imp_IoFreeMdl
0x14002a3f9  nop     dword ptr [rax+rax+00h]
0x14002a3fe  mov     eax, ebx
0x14002a400  add     rsp, 40h
0x14002a404  pop     r15
0x14002a406  pop     r14
0x14002a408  pop     r13
0x14002a40a  pop     r12
0x14002a40c  pop     rdi
0x14002a40d  pop     rsi
0x14002a40e  pop     rbx
0x14002a40f  retn
```
