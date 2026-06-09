# DeleteTracerptString(_TRACERPT_STRING *)

- ea: `0x1400328a4`
- end: `0x140032903`
- name: `?DeleteTracerptString@@YAXPEAU_TRACERPT_STRING@@@Z`
- size: `95`
- prototype: `void __fastcall(struct _TRACERPT_STRING *Block)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14003252c`
- `0x140038330`

## callees

- `0x1400020f0`
- `0x1400328a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400328cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400328ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400328cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400328ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400328bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400328dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400328bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400328dc`

## pseudocode

```c
void __fastcall DeleteTracerptString(struct _TRACERPT_STRING *Block)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax

  if ( Block )
  {
    v1 = (void *)*((_QWORD *)Block + 9);
    if ( v1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v1);
    }
    v4 = (void *)*((_QWORD *)Block + 4);
    if ( v4 )
    {
      v5 = GetProcessHeap();
      HeapFree(v5, 0, v4);
    }
    operator delete(Block);
  }
}

```

## disassembly

```asm
0x1400328a4  test    rcx, rcx
0x1400328a7  jz      short locret_140032902
0x1400328a9  mov     [rsp+arg_0], rbx
0x1400328ae  push    rdi
0x1400328af  sub     rsp, 20h
0x1400328b3  mov     rdi, [rcx+48h]
0x1400328b7  mov     rbx, rcx
0x1400328ba  test    rdi, rdi
0x1400328bd  jz      short loc_1400328D3
0x1400328bf  call    cs:__imp_GetProcessHeap
0x1400328c5  mov     r8, rdi; lpMem
0x1400328c8  xor     edx, edx; dwFlags
0x1400328ca  mov     rcx, rax; hHeap
0x1400328cd  call    cs:__imp_HeapFree
0x1400328d3  mov     rdi, [rbx+20h]
0x1400328d7  test    rdi, rdi
0x1400328da  jz      short loc_1400328F0
0x1400328dc  call    cs:__imp_GetProcessHeap
0x1400328e2  mov     r8, rdi; lpMem
0x1400328e5  xor     edx, edx; dwFlags
0x1400328e7  mov     rcx, rax; hHeap
0x1400328ea  call    cs:__imp_HeapFree
0x1400328f0  mov     rcx, rbx; Block
0x1400328f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400328f8  mov     rbx, [rsp+28h+arg_0]
0x1400328fd  add     rsp, 20h
0x140032901  pop     rdi
0x140032902  retn
```
