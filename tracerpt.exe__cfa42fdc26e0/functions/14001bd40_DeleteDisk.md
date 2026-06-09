# DeleteDisk

- ea: `0x14001bd40`
- end: `0x14001bdd7`
- name: `DeleteDisk`
- size: `151`
- prototype: `char __fastcall(_QWORD *lpMem)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14001c85c`
- `0x14001cb70`
- `0x14001db34`

## callees

- `0x14001bd40`
- `0x14001c85c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001bd99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001bdc6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001bd99`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001bdc6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bd8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bdb8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bd8b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001bdb8`

## pseudocode

```c
char __fastcall DeleteDisk(_QWORD *lpMem)
{
  _QWORD *v3; // rax
  LPVOID *v4; // rcx
  void *v5; // rdi
  HANDLE ProcessHeap; // rax
  struct _PROCESS_RECORD *v7; // rdi
  struct _PROCESS_RECORD *v8; // rcx
  HANDLE v9; // rax

  if ( !lpMem )
    return 0;
  v3 = (_QWORD *)*lpMem;
  if ( *(_QWORD **)(*lpMem + 8LL) != lpMem || (v4 = (LPVOID *)lpMem[1], *v4 != lpMem) )
    __fastfail(3u);
  *v4 = v3;
  v3[1] = v4;
  v5 = (void *)lpMem[3];
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
  v7 = (struct _PROCESS_RECORD *)lpMem[7];
  while ( v7 != (struct _PROCESS_RECORD *)(lpMem + 7) )
  {
    v8 = v7;
    v7 = *(struct _PROCESS_RECORD **)v7;
    DeleteProcess(v8);
  }
  v9 = GetProcessHeap();
  HeapFree(v9, 0, lpMem);
  return 1;
}

```

## disassembly

```asm
0x14001bd40  mov     [rsp+arg_0], rbx
0x14001bd45  mov     [rsp+arg_8], rsi
0x14001bd4a  push    rdi
0x14001bd4b  sub     rsp, 20h
0x14001bd4f  mov     rbx, rcx
0x14001bd52  test    rcx, rcx
0x14001bd55  jnz     short loc_14001BD69
0x14001bd57  xor     al, al
0x14001bd59  mov     rbx, [rsp+28h+arg_0]
0x14001bd5e  mov     rsi, [rsp+28h+arg_8]
0x14001bd63  add     rsp, 20h
0x14001bd67  pop     rdi
0x14001bd68  retn
0x14001bd69  mov     rax, [rcx]
0x14001bd6c  cmp     [rax+8], rbx
0x14001bd70  jnz     short loc_14001BDD0
0x14001bd72  mov     rcx, [rcx+8]
0x14001bd76  cmp     [rcx], rbx
0x14001bd79  jnz     short loc_14001BDD0
0x14001bd7b  mov     [rcx], rax
0x14001bd7e  mov     [rax+8], rcx
0x14001bd82  mov     rdi, [rbx+18h]
0x14001bd86  test    rdi, rdi
0x14001bd89  jz      short loc_14001BD9F
0x14001bd8b  call    cs:__imp_GetProcessHeap
0x14001bd91  mov     r8, rdi; lpMem
0x14001bd94  xor     edx, edx; dwFlags
0x14001bd96  mov     rcx, rax; hHeap
0x14001bd99  call    cs:__imp_HeapFree
0x14001bd9f  lea     rsi, [rbx+38h]
0x14001bda3  mov     rdi, [rsi]
0x14001bda6  jmp     short loc_14001BDB3
0x14001bda8  mov     rcx, rdi; lpMem
0x14001bdab  mov     rdi, [rdi]
0x14001bdae  call    ?DeleteProcess@@YAEPEAU_PROCESS_RECORD@@@Z; DeleteProcess(_PROCESS_RECORD *)
0x14001bdb3  cmp     rdi, rsi
0x14001bdb6  jnz     short loc_14001BDA8
0x14001bdb8  call    cs:__imp_GetProcessHeap
0x14001bdbe  mov     r8, rbx; lpMem
0x14001bdc1  xor     edx, edx; dwFlags
0x14001bdc3  mov     rcx, rax; hHeap
0x14001bdc6  call    cs:__imp_HeapFree
0x14001bdcc  mov     al, 1
0x14001bdce  jmp     short loc_14001BD59
0x14001bdd0  mov     ecx, 3
0x14001bdd5  int     29h; Win8: RtlFailFast(ecx)
```
