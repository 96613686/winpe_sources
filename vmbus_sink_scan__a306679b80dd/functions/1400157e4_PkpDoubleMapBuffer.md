# PkpDoubleMapBuffer

- ea: `0x1400157e4`
- end: `0x140015905`
- name: `PkpDoubleMapBuffer`
- size: `289`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _MDL **, PVOID *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400155e0`

## callees

- `0x1400157e4`
- `0x140017240`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14001581b`
- `ntoskrnl!IoAllocateMdl` at `0x14001581b`
- `ntoskrnl!IoFreeMdl` at `0x1400158e8`
- `ntoskrnl!IoFreeMdl` at `0x1400158e8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015897`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140015897`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001584a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14001584a`
- `ntoskrnl!MmUnlockPages` at `0x1400158d9`
- `ntoskrnl!MmUnlockPages` at `0x1400158d9`

## pseudocode

```c
__int64 __fastcall PkpDoubleMapBuffer(void *a1, unsigned int a2, struct _MDL **a3, PVOID *a4)
{
  unsigned __int64 v6; // rdi
  char v7; // si
  int v8; // r12d
  PMDL Mdl; // rax
  struct _MDL *v10; // rbx
  unsigned int v11; // edi

  v6 = a2;
  v7 = 0;
  v8 = 2 * a2;
  Mdl = IoAllocateMdl(a1, 2 * a2, 0, 0, 0);
  v10 = Mdl;
  if ( !Mdl )
    goto LABEL_2;
  Mdl->ByteCount = v6;
  MmProbeAndLockPages(Mdl, 0, IoModifyAccess);
  v7 = 1;
  memmove(&v10[1].Next + (v6 >> 12), &v10[1], 8 * (v6 >> 12));
  v10->ByteCount = v8;
  if ( !MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u) )
  {
    v10->ByteCount >>= 1;
LABEL_2:
    v11 = -1073741670;
    goto LABEL_6;
  }
  *a3 = v10;
  *a4 = v10->MappedSystemVa;
  v10 = 0;
  v11 = 0;
LABEL_6:
  if ( v10 )
  {
    if ( v7 )
      MmUnlockPages(v10);
    IoFreeMdl(v10);
  }
  return v11;
}

```

## disassembly

```asm
0x1400157e4  push    rbx
0x1400157e6  push    rsi
0x1400157e7  push    rdi
0x1400157e8  push    r12
0x1400157ea  push    r14
0x1400157ec  push    r15
0x1400157ee  sub     rsp, 48h
0x1400157f2  mov     r14, r9
0x1400157f5  mov     r15, r8
0x1400157f8  mov     edi, edx
0x1400157fa  xor     sil, sil
0x1400157fd  mov     [rsp+78h+arg_8], sil
0x140015805  lea     r12d, [rdi+rdi]
0x140015809  mov     [rsp+78h+Irp], 0; Irp
0x140015812  xor     r9d, r9d; ChargeQuota
0x140015815  xor     r8d, r8d; SecondaryBuffer
0x140015818  mov     edx, r12d; Length
0x14001581b  call    cs:__imp_IoAllocateMdl
0x140015822  nop     dword ptr [rax+rax+00h]
0x140015827  mov     rbx, rax
0x14001582a  mov     [rsp+78h+var_48], rax
0x14001582f  test    rax, rax
0x140015832  jnz     short loc_14001583E
0x140015834  mov     edi, 0C000009Ah
0x140015839  jmp     loc_1400158CC
0x14001583e  mov     [rax+28h], edi
0x140015841  xor     edx, edx; AccessMode
0x140015843  lea     r8d, [rdx+2]; Operation
0x140015847  mov     rcx, rbx; MemoryDescriptorList
0x14001584a  call    cs:__imp_MmProbeAndLockPages
0x140015851  nop     dword ptr [rax+rax+00h]
0x140015856  nop
0x140015857  mov     esi, 1
0x14001585c  lea     rdx, [rbx+30h]; Src
0x140015860  mov     rax, rdi
0x140015863  shr     rax, 0Ch
0x140015867  lea     r8, ds:0[rax*8]; Size
0x14001586f  lea     rcx, [r8+rdx]; void *
0x140015873  call    memmove
0x140015878  mov     [rbx+28h], r12d
0x14001587c  mov     [rsp+78h+Priority], 40000010h; Priority
0x140015884  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x14001588c  xor     r9d, r9d; RequestedAddress
0x14001588f  mov     r8d, esi; CacheType
0x140015892  xor     edx, edx; AccessMode
0x140015894  mov     rcx, rbx; MemoryDescriptorList
0x140015897  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001589e  nop     dword ptr [rax+rax+00h]
0x1400158a3  test    rax, rax
0x1400158a6  jnz     short loc_1400158AD
0x1400158a8  shr     dword ptr [rbx+28h], 1
0x1400158ab  jmp     short loc_140015834
0x1400158ad  mov     [r15], rbx
0x1400158b0  mov     rax, [rbx+18h]
0x1400158b4  mov     [r14], rax
0x1400158b7  xor     ebx, ebx
0x1400158b9  xor     edi, edi
0x1400158bb  jmp     short loc_1400158CC
0x1400158bd  mov     edi, eax
0x1400158bf  mov     rbx, [rsp+78h+var_48]
0x1400158c4  mov     sil, [rsp+78h+arg_8]
0x1400158cc  test    rbx, rbx
0x1400158cf  jz      short loc_1400158F4
0x1400158d1  test    sil, sil
0x1400158d4  jz      short loc_1400158E5
0x1400158d6  mov     rcx, rbx; MemoryDescriptorList
0x1400158d9  call    cs:__imp_MmUnlockPages
0x1400158e0  nop     dword ptr [rax+rax+00h]
0x1400158e5  mov     rcx, rbx; Mdl
0x1400158e8  call    cs:__imp_IoFreeMdl
0x1400158ef  nop     dword ptr [rax+rax+00h]
0x1400158f4  mov     eax, edi
0x1400158f6  add     rsp, 48h
0x1400158fa  pop     r15
0x1400158fc  pop     r14
0x1400158fe  pop     r12
0x140015900  pop     rdi
0x140015901  pop     rsi
0x140015902  pop     rbx
0x140015903  retn
```
