# ChCreateGpadlFromBuffer

- ea: `0x14002d744`
- end: `0x14002d832`
- name: `ChCreateGpadlFromBuffer`
- size: `238`
- prototype: `__int64 __fastcall(__int64, void *, ULONG, LOCK_OPERATION, __int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c830`

## callees

- `0x14000f158`
- `0x14002d744`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002d78e`
- `ntoskrnl!IoAllocateMdl` at `0x14002d78e`
- `ntoskrnl!IoFreeMdl` at `0x14002d813`
- `ntoskrnl!IoFreeMdl` at `0x14002d813`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002d7b6`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002d7b6`
- `ntoskrnl!MmUnlockPages` at `0x14002d7fb`
- `ntoskrnl!MmUnlockPages` at `0x14002d7fb`

## pseudocode

```c
__int64 __fastcall ChCreateGpadlFromBuffer(__int64 a1, void *a2, ULONG a3, LOCK_OPERATION a4, __int64 a5, __int64 a6)
{
  __int64 result; // rax
  struct _MDL *Mdl; // rax
  struct _MDL *v10; // rbx
  unsigned int v11; // edi

  if ( *(_BYTE *)(*(_QWORD *)(a1 + 216) + 322LL) )
    return 3221225659LL;
  Mdl = IoAllocateMdl(a2, a3, 0, 0, 0);
  v10 = Mdl;
  if ( !Mdl )
    return 3221225626LL;
  MmProbeAndLockPages(Mdl, 0, a4);
  result = ChpCreateGpadlFromNtmdl(a1, v10, 0, 0, BusChGpadlCreated, a6, 3);
  v11 = result;
  if ( (int)result < 0 )
  {
    MmUnlockPages(v10);
    IoFreeMdl(v10);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x14002d744  mov     [rsp+arg_8], rbx
0x14002d749  mov     [rsp+arg_10], rsi
0x14002d74e  push    rdi
0x14002d74f  sub     rsp, 40h
0x14002d753  mov     edi, r9d
0x14002d756  mov     r10d, r8d
0x14002d759  mov     r11, rdx
0x14002d75c  mov     rsi, rcx
0x14002d75f  mov     rax, [rcx+0D8h]
0x14002d766  cmp     byte ptr [rax+142h], 0
0x14002d76d  jz      short loc_14002D779
0x14002d76f  mov     eax, 0C00000BBh
0x14002d774  jmp     loc_14002D821
0x14002d779  mov     [rsp+48h+Irp], 0; Irp
0x14002d782  xor     r9d, r9d; ChargeQuota
0x14002d785  xor     r8d, r8d; SecondaryBuffer
0x14002d788  mov     edx, r10d; Length
0x14002d78b  mov     rcx, r11; VirtualAddress
0x14002d78e  call    cs:__imp_IoAllocateMdl
0x14002d795  nop     dword ptr [rax+rax+00h]
0x14002d79a  mov     rbx, rax
0x14002d79d  mov     [rsp+48h+arg_0], rax
0x14002d7a2  test    rax, rax
0x14002d7a5  jnz     short loc_14002D7AE
0x14002d7a7  mov     eax, 0C000009Ah
0x14002d7ac  jmp     short loc_14002D821
0x14002d7ae  mov     r8d, edi; Operation
0x14002d7b1  xor     edx, edx; AccessMode
0x14002d7b3  mov     rcx, rbx; MemoryDescriptorList
0x14002d7b6  call    cs:__imp_MmProbeAndLockPages
0x14002d7bd  nop     dword ptr [rax+rax+00h]
0x14002d7c2  nop
0x14002d7c3  mov     [rsp+48h+var_18], 3
0x14002d7cb  mov     rax, [rsp+48h+arg_28]
0x14002d7d0  mov     [rsp+48h+var_20], rax
0x14002d7d5  lea     rax, BusChGpadlCreated
0x14002d7dc  mov     [rsp+48h+Irp], rax
0x14002d7e1  xor     r9d, r9d
0x14002d7e4  xor     r8d, r8d
0x14002d7e7  mov     rdx, rbx
0x14002d7ea  mov     rcx, rsi
0x14002d7ed  call    ChpCreateGpadlFromNtmdl
0x14002d7f2  mov     edi, eax
0x14002d7f4  test    eax, eax
0x14002d7f6  jns     short loc_14002D821
0x14002d7f8  mov     rcx, rbx; MemoryDescriptorList
0x14002d7fb  call    cs:__imp_MmUnlockPages
0x14002d802  nop     dword ptr [rax+rax+00h]
0x14002d807  jmp     short loc_14002D810
0x14002d809  mov     edi, eax
0x14002d80b  mov     rbx, [rsp+48h+arg_0]
0x14002d810  mov     rcx, rbx; Mdl
0x14002d813  call    cs:__imp_IoFreeMdl
0x14002d81a  nop     dword ptr [rax+rax+00h]
0x14002d81f  mov     eax, edi
0x14002d821  mov     rbx, [rsp+48h+arg_8]
0x14002d826  mov     rsi, [rsp+48h+arg_10]
0x14002d82b  add     rsp, 40h
0x14002d82f  pop     rdi
0x14002d830  retn
```
