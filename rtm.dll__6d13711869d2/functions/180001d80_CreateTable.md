# CreateTable

- ea: `0x180001d80`
- end: `0x180001dcf`
- name: `CreateTable`
- size: `79`
- prototype: `SCODE __stdcall(LPCIID lpInterface, ALLOCATEBUFFER *lpAllocateBuffer, ALLOCATEMORE *lpAllocateMore, FREEBUFFER *lpFreeBuffer, LPVOID lpvReserved, ULONG ulTableType, ULONG ulPropTagIndexColumn, LPSPropTagArray lpSPropTagArrayColumns, LPTABLEDATA *lppTableData)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009118`
- `0x1800094a8`

## callees

- `0x180001d80`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180001daa`
- `KERNEL32!HeapAlloc` at `0x180001daa`
- `KERNEL32!GetProcessHeap` at `0x180001d98`
- `KERNEL32!GetProcessHeap` at `0x180001d98`

## pseudocode

```c
SCODE __stdcall CreateTable(
        LPCIID lpInterface,
        ALLOCATEBUFFER *lpAllocateBuffer,
        ALLOCATEMORE *lpAllocateMore,
        FREEBUFFER *lpFreeBuffer,
        LPVOID lpvReserved,
        ULONG ulTableType,
        ULONG ulPropTagIndexColumn,
        LPSPropTagArray lpSPropTagArrayColumns,
        LPTABLEDATA *lppTableData)
{
  int v10; // ebx
  HANDLE ProcessHeap; // rax
  _DWORD *v13; // rax

  v10 = (int)lpInterface;
  if ( !(_DWORD)lpInterface )
    return 87;
  ProcessHeap = GetProcessHeap();
  v13 = HeapAlloc(ProcessHeap, 8u, 0x10u);
  if ( !v13 )
    return 8;
  v13[2] = v10;
  *(_QWORD *)lpAllocateBuffer = v13;
  return 0;
}

```

## disassembly

```asm
0x180001d80  mov     [rsp+arg_0], rbx
0x180001d85  push    rdi
0x180001d86  sub     rsp, 20h
0x180001d8a  mov     rdi, rdx
0x180001d8d  mov     ebx, ecx
0x180001d8f  test    ecx, ecx
0x180001d91  jnz     short loc_180001D98
0x180001d93  lea     eax, [rcx+57h]
0x180001d96  jmp     short loc_180001DC4
0x180001d98  call    cs:__imp_GetProcessHeap
0x180001d9e  mov     edx, 8; dwFlags
0x180001da3  mov     rcx, rax; hHeap
0x180001da6  lea     r8d, [rdx+8]; dwBytes
0x180001daa  call    cs:__imp_HeapAlloc
0x180001db0  test    rax, rax
0x180001db3  jnz     short loc_180001DBC
0x180001db5  mov     eax, 8
0x180001dba  jmp     short loc_180001DC4
0x180001dbc  mov     [rax+8], ebx
0x180001dbf  mov     [rdi], rax
0x180001dc2  xor     eax, eax
0x180001dc4  mov     rbx, [rsp+28h+arg_0]
0x180001dc9  add     rsp, 20h
0x180001dcd  pop     rdi
0x180001dce  retn
```
