# sub_18007ACDC

- ea: `0x18007acdc`
- end: `0x18007ad10`
- name: `sub_18007ACDC`
- size: `52`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180079330`
- `0x180079a0c`
- `0x18007a100`
- `0x18007ab88`
- `0x18007ad18`
- `0x18007ae90`
- `0x180081864`

## callees

- `0x18007acdc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007acfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007acfd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ace9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18007ace9`

## pseudocode

```c
void __fastcall sub_18007ACDC(LPVOID lpMem)
{
  HANDLE ProcessHeap; // rax

  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, lpMem);
  }
}

```

## disassembly

```asm
0x18007acdc  test    rcx, rcx
0x18007acdf  jz      short locret_18007AD0E
0x18007ace1  push    rbx
0x18007ace2  sub     rsp, 20h
0x18007ace6  mov     rbx, rcx
0x18007ace9  call    cs:GetProcessHeap
0x18007acf0  nop     dword ptr [rax+rax+00h]
0x18007acf5  mov     r8, rbx; lpMem
0x18007acf8  xor     edx, edx; dwFlags
0x18007acfa  mov     rcx, rax; hHeap
0x18007acfd  call    cs:HeapFree
0x18007ad04  nop     dword ptr [rax+rax+00h]
0x18007ad09  add     rsp, 20h
0x18007ad0d  pop     rbx
0x18007ad0e  retn
```
