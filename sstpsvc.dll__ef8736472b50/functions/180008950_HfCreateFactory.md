# HfCreateFactory

- ea: `0x180008950`
- end: `0x1800089d3`
- name: `HfCreateFactory`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bc0`

## callees

- `0x180007810`
- `0x180008950`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000895d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000895d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008994`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008974`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008974`

## pseudocode

```c
__int64 __fastcall HfCreateFactory(__int64 a1, _QWORD *a2)
{
  HANDLE ProcessHeap; // rax
  LPVOID v4; // rax
  void *v5; // rbx
  HANDLE v6; // rax

  ProcessHeap = GetProcessHeap();
  v4 = HeapAlloc(ProcessHeap, 0, 0x88u);
  v5 = v4;
  if ( !v4 )
    goto LABEL_4;
  if ( (unsigned int)constructHandleFactory(v4) )
  {
    v6 = GetProcessHeap();
    HeapFree(v6, 0, v5);
LABEL_4:
    *a2 = 0;
    return 8;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180008950  mov     [rsp+arg_0], rbx
0x180008955  push    rdi
0x180008956  sub     rsp, 20h
0x18000895a  mov     rdi, rdx
0x18000895d  call    cs:__imp_GetProcessHeap
0x180008964  nop     dword ptr [rax+rax+00h]
0x180008969  xor     edx, edx; dwFlags
0x18000896b  mov     r8d, 88h; dwBytes
0x180008971  mov     rcx, rax; hHeap
0x180008974  call    cs:__imp_HeapAlloc
0x18000897b  nop     dword ptr [rax+rax+00h]
0x180008980  mov     rbx, rax
0x180008983  test    rax, rax
0x180008986  jz      short loc_1800089B4
0x180008988  mov     rcx, rax
0x18000898b  call    constructHandleFactory
0x180008990  test    eax, eax
0x180008992  jz      short loc_1800089CC
0x180008994  call    cs:__imp_GetProcessHeap
0x18000899b  nop     dword ptr [rax+rax+00h]
0x1800089a0  mov     r8, rbx; lpMem
0x1800089a3  xor     edx, edx; dwFlags
0x1800089a5  mov     rcx, rax; hHeap
0x1800089a8  call    cs:__imp_HeapFree
0x1800089af  nop     dword ptr [rax+rax+00h]
0x1800089b4  mov     qword ptr [rdi], 0
0x1800089bb  mov     eax, 8
0x1800089c0  mov     rbx, [rsp+28h+arg_0]
0x1800089c5  add     rsp, 20h
0x1800089c9  pop     rdi
0x1800089ca  retn
0x1800089cc  mov     [rdi], rbx
0x1800089cf  xor     eax, eax
0x1800089d1  jmp     short loc_1800089C0
```
