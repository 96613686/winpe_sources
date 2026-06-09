# CreateHandleTable

- ea: `0x18003e0b8`
- end: `0x18003e154`
- name: `CreateHandleTable`
- size: `156`
- prototype: `char *()`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d6d0`

## callees

- `0x18003e0b8`
- `0x18003e220`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18003e12b`
- `KERNEL32!DeleteCriticalSection` at `0x18003e12b`
- `KERNEL32!HeapAlloc` at `0x18003e0da`
- `KERNEL32!HeapAlloc` at `0x18003e0da`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003e115`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x18003e115`
- `KERNEL32!HeapFree` at `0x18003e139`
- `KERNEL32!HeapFree` at `0x18003e139`

## pseudocode

```c
char *CreateHandleTable()
{
  HANDLE v0; // rdi
  char *v1; // rax
  char *v2; // rbx

  v0 = ghTapisrvHeap;
  v1 = (char *)HeapAlloc(ghTapisrvHeap, 8u, 0x58u);
  v2 = v1;
  if ( !v1 )
    return 0;
  *(_QWORD *)v1 = v0;
  *((_DWORD *)v1 + 5) = 0x10000;
  *((_QWORD *)v1 + 5) = FreeContextCallback;
  *((_QWORD *)v1 + 4) = v1 + 24;
  *((_QWORD *)v1 + 3) = v1 + 24;
  InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(v1 + 48), 0x80001000);
  if ( !(unsigned int)GrowTable(v2) )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)(v2 + 48));
    HeapFree(v0, 0, v2);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18003e0b8  mov     [rsp+arg_0], rbx
0x18003e0bd  mov     [rsp+arg_8], rsi
0x18003e0c2  push    rdi
0x18003e0c3  sub     rsp, 20h
0x18003e0c7  mov     rdi, cs:ghTapisrvHeap
0x18003e0ce  mov     edx, 8; dwFlags
0x18003e0d3  mov     rcx, rdi; hHeap
0x18003e0d6  lea     r8d, [rdx+50h]; dwBytes
0x18003e0da  call    cs:__imp_HeapAlloc
0x18003e0e0  mov     rbx, rax
0x18003e0e3  test    rax, rax
0x18003e0e6  jnz     short loc_18003E0EC
0x18003e0e8  xor     eax, eax
0x18003e0ea  jmp     short loc_18003E144
0x18003e0ec  mov     [rax], rdi
0x18003e0ef  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003e0f3  mov     dword ptr [rax+14h], 10000h
0x18003e0fa  mov     edx, 80001000h; dwSpinCount
0x18003e0ff  lea     rax, FreeContextCallback
0x18003e106  mov     [rbx+28h], rax
0x18003e10a  lea     rax, [rbx+18h]
0x18003e10e  mov     [rbx+20h], rax
0x18003e112  mov     [rax], rax
0x18003e115  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003e11b  mov     rcx, rbx
0x18003e11e  call    GrowTable
0x18003e123  test    eax, eax
0x18003e125  jnz     short loc_18003E141
0x18003e127  lea     rcx, [rbx+30h]; lpCriticalSection
0x18003e12b  call    cs:__imp_DeleteCriticalSection
0x18003e131  mov     r8, rbx; lpMem
0x18003e134  xor     edx, edx; dwFlags
0x18003e136  mov     rcx, rdi; hHeap
0x18003e139  call    cs:__imp_HeapFree
0x18003e13f  jmp     short loc_18003E0E8
0x18003e141  mov     rax, rbx
0x18003e144  mov     rbx, [rsp+28h+arg_0]
0x18003e149  mov     rsi, [rsp+28h+arg_8]
0x18003e14e  add     rsp, 20h
0x18003e152  pop     rdi
0x18003e153  retn
```
