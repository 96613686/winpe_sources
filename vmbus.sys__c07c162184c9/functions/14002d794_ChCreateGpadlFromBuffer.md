# ChCreateGpadlFromBuffer

- ea: `0x14002d794`
- end: `0x14002d882`
- name: `ChCreateGpadlFromBuffer`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14002c880`

## callees

- `0x14000f158`
- `0x14002d794`

## import_xrefs

- `ntoskrnl!IoAllocateMdl` at `0x14002d7de`
- `ntoskrnl!IoAllocateMdl` at `0x14002d7de`
- `ntoskrnl!IoFreeMdl` at `0x14002d863`
- `ntoskrnl!IoFreeMdl` at `0x14002d863`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002d806`
- `ntoskrnl!MmProbeAndLockPages` at `0x14002d806`
- `ntoskrnl!MmUnlockPages` at `0x14002d84b`
- `ntoskrnl!MmUnlockPages` at `0x14002d84b`

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
  result = ChpCreateGpadlFromNtmdl(a1, (__int64)v10, 0, 0, (__int64)BusChGpadlCreated, a6, 3);
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
0x14002d794  mov     [rsp+arg_8], rbx
0x14002d799  mov     [rsp+arg_10], rsi
0x14002d79e  push    rdi
0x14002d79f  sub     rsp, 40h
0x14002d7a3  mov     edi, r9d
0x14002d7a6  mov     r10d, r8d
0x14002d7a9  mov     r11, rdx
0x14002d7ac  mov     rsi, rcx
0x14002d7af  mov     rax, [rcx+0D8h]
0x14002d7b6  cmp     byte ptr [rax+142h], 0
0x14002d7bd  jz      short loc_14002D7C9
0x14002d7bf  mov     eax, 0C00000BBh
0x14002d7c4  jmp     loc_14002D871
0x14002d7c9  mov     [rsp+48h+Irp], 0; Irp
0x14002d7d2  xor     r9d, r9d; ChargeQuota
0x14002d7d5  xor     r8d, r8d; SecondaryBuffer
0x14002d7d8  mov     edx, r10d; Length
0x14002d7db  mov     rcx, r11; VirtualAddress
0x14002d7de  call    cs:__imp_IoAllocateMdl
0x14002d7e5  nop     dword ptr [rax+rax+00h]
0x14002d7ea  mov     rbx, rax
0x14002d7ed  mov     [rsp+48h+arg_0], rax
0x14002d7f2  test    rax, rax
0x14002d7f5  jnz     short loc_14002D7FE
0x14002d7f7  mov     eax, 0C000009Ah
0x14002d7fc  jmp     short loc_14002D871
0x14002d7fe  mov     r8d, edi; Operation
0x14002d801  xor     edx, edx; AccessMode
0x14002d803  mov     rcx, rbx; MemoryDescriptorList
0x14002d806  call    cs:__imp_MmProbeAndLockPages
0x14002d80d  nop     dword ptr [rax+rax+00h]
0x14002d812  nop
0x14002d813  mov     [rsp+48h+var_18], 3
0x14002d81b  mov     rax, [rsp+48h+arg_28]
0x14002d820  mov     [rsp+48h+var_20], rax
0x14002d825  lea     rax, BusChGpadlCreated
0x14002d82c  mov     [rsp+48h+Irp], rax
0x14002d831  xor     r9d, r9d
0x14002d834  xor     r8d, r8d
0x14002d837  mov     rdx, rbx
0x14002d83a  mov     rcx, rsi
0x14002d83d  call    ChpCreateGpadlFromNtmdl
0x14002d842  mov     edi, eax
0x14002d844  test    eax, eax
0x14002d846  jns     short loc_14002D871
0x14002d848  mov     rcx, rbx; MemoryDescriptorList
0x14002d84b  call    cs:__imp_MmUnlockPages
0x14002d852  nop     dword ptr [rax+rax+00h]
0x14002d857  jmp     short loc_14002D860
0x14002d859  mov     edi, eax
0x14002d85b  mov     rbx, [rsp+48h+arg_0]
0x14002d860  mov     rcx, rbx; Mdl
0x14002d863  call    cs:__imp_IoFreeMdl
0x14002d86a  nop     dword ptr [rax+rax+00h]
0x14002d86f  mov     eax, edi
0x14002d871  mov     rbx, [rsp+48h+arg_8]
0x14002d876  mov     rsi, [rsp+48h+arg_10]
0x14002d87b  add     rsp, 40h
0x14002d87f  pop     rdi
0x14002d880  retn
```
