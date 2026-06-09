# SP<ushort,SP_MEM<ushort>>::Attach(ushort *)

- ea: `0x18001ac00`
- end: `0x18001ac51`
- name: `?Attach@?$SP@GV?$SP_MEM@G@@@@QEAAXPEAG@Z`
- size: `81`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180005b30`
- `0x18000f5a0`
- `0x1800236b4`

## callees

- `0x18001ac00`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001ac1d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001ac31`

## pseudocode

```c
void __fastcall SP<unsigned short,SP_MEM<unsigned short>>::Attach(void **a1, void *a2)
{
  void *v2; // rdi
  HANDLE ProcessHeap; // rax

  v2 = *a1;
  if ( *a1 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v2);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18001ac00  mov     [rsp+arg_0], rbx
0x18001ac05  mov     [rsp+arg_8], rsi
0x18001ac0a  push    rdi
0x18001ac0b  sub     rsp, 20h
0x18001ac0f  mov     rdi, [rcx]
0x18001ac12  mov     rsi, rdx
0x18001ac15  mov     rbx, rcx
0x18001ac18  test    rdi, rdi
0x18001ac1b  jz      short loc_18001AC3D
0x18001ac1d  call    cs:__imp_GetProcessHeap
0x18001ac24  nop     dword ptr [rax+rax+00h]
0x18001ac29  mov     r8, rdi; lpMem
0x18001ac2c  xor     edx, edx; dwFlags
0x18001ac2e  mov     rcx, rax; hHeap
0x18001ac31  call    cs:__imp_HeapFree
0x18001ac38  nop     dword ptr [rax+rax+00h]
0x18001ac3d  mov     [rbx], rsi
0x18001ac40  mov     rbx, [rsp+28h+arg_0]
0x18001ac45  mov     rsi, [rsp+28h+arg_8]
0x18001ac4a  add     rsp, 20h
0x18001ac4e  pop     rdi
0x18001ac4f  retn
```
