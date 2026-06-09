# PkpDoubleMapBuffer

- ea: `0x140011ba4`
- end: `0x140011cc5`
- name: `PkpDoubleMapBuffer`
- size: `289`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140011a4c`

## callees

- `0x140011ba4`
- `0x140011f80`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x140011bdb`
- `ntoskrnl!IoAllocateMdl` at `0x140011bdb`
- `ntoskrnl!IoFreeMdl` at `0x140011ca8`
- `ntoskrnl!IoFreeMdl` at `0x140011ca8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011c57`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140011c57`
- `ntoskrnl!MmUnlockPages` at `0x140011c99`
- `ntoskrnl!MmUnlockPages` at `0x140011c99`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011c0a`
- `ntoskrnl!MmProbeAndLockPages` at `0x140011c0a`

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
0x140011ba4  push    rbx
0x140011ba6  push    rsi
0x140011ba7  push    rdi
0x140011ba8  push    r12
0x140011baa  push    r14
0x140011bac  push    r15
0x140011bae  sub     rsp, 48h
0x140011bb2  mov     r14, r9
0x140011bb5  mov     r15, r8
0x140011bb8  mov     edi, edx
0x140011bba  xor     sil, sil
0x140011bbd  mov     [rsp+78h+arg_8], sil
0x140011bc5  lea     r12d, [rdi+rdi]
0x140011bc9  mov     [rsp+78h+Irp], 0; Irp
0x140011bd2  xor     r9d, r9d; ChargeQuota
0x140011bd5  xor     r8d, r8d; SecondaryBuffer
0x140011bd8  mov     edx, r12d; Length
0x140011bdb  call    cs:__imp_IoAllocateMdl
0x140011be2  nop     dword ptr [rax+rax+00h]
0x140011be7  mov     rbx, rax
0x140011bea  mov     [rsp+78h+var_48], rax
0x140011bef  test    rax, rax
0x140011bf2  jnz     short loc_140011BFE
0x140011bf4  mov     edi, 0C000009Ah
0x140011bf9  jmp     loc_140011C8C
0x140011bfe  mov     [rax+28h], edi
0x140011c01  xor     edx, edx; AccessMode
0x140011c03  lea     r8d, [rdx+2]; Operation
0x140011c07  mov     rcx, rbx; MemoryDescriptorList
0x140011c0a  call    cs:__imp_MmProbeAndLockPages
0x140011c11  nop     dword ptr [rax+rax+00h]
0x140011c16  nop
0x140011c17  mov     esi, 1
0x140011c1c  lea     rdx, [rbx+30h]; Src
0x140011c20  mov     rax, rdi
0x140011c23  shr     rax, 0Ch
0x140011c27  lea     r8, ds:0[rax*8]; Size
0x140011c2f  lea     rcx, [r8+rdx]; void *
0x140011c33  call    memmove
0x140011c38  mov     [rbx+28h], r12d
0x140011c3c  mov     [rsp+78h+Priority], 40000010h; Priority
0x140011c44  mov     dword ptr [rsp+78h+Irp], 0; BugCheckOnFailure
0x140011c4c  xor     r9d, r9d; RequestedAddress
0x140011c4f  mov     r8d, esi; CacheType
0x140011c52  xor     edx, edx; AccessMode
0x140011c54  mov     rcx, rbx; MemoryDescriptorList
0x140011c57  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140011c5e  nop     dword ptr [rax+rax+00h]
0x140011c63  test    rax, rax
0x140011c66  jnz     short loc_140011C6D
0x140011c68  shr     dword ptr [rbx+28h], 1
0x140011c6b  jmp     short loc_140011BF4
0x140011c6d  mov     [r15], rbx
0x140011c70  mov     rax, [rbx+18h]
0x140011c74  mov     [r14], rax
0x140011c77  xor     ebx, ebx
0x140011c79  xor     edi, edi
0x140011c7b  jmp     short loc_140011C8C
0x140011c7d  mov     edi, eax
0x140011c7f  mov     rbx, [rsp+78h+var_48]
0x140011c84  mov     sil, [rsp+78h+arg_8]
0x140011c8c  test    rbx, rbx
0x140011c8f  jz      short loc_140011CB4
0x140011c91  test    sil, sil
0x140011c94  jz      short loc_140011CA5
0x140011c96  mov     rcx, rbx; MemoryDescriptorList
0x140011c99  call    cs:__imp_MmUnlockPages
0x140011ca0  nop     dword ptr [rax+rax+00h]
0x140011ca5  mov     rcx, rbx; Mdl
0x140011ca8  call    cs:__imp_IoFreeMdl
0x140011caf  nop     dword ptr [rax+rax+00h]
0x140011cb4  mov     eax, edi
0x140011cb6  add     rsp, 48h
0x140011cba  pop     r15
0x140011cbc  pop     r14
0x140011cbe  pop     r12
0x140011cc0  pop     rdi
0x140011cc1  pop     rsi
0x140011cc2  pop     rbx
0x140011cc3  retn
```
