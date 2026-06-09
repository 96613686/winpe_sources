# EventDumpIterator::CopyFrom(EventDumpIterator const &)

- ea: `0x14000d96c`
- end: `0x14000d9d7`
- name: `?CopyFrom@EventDumpIterator@@AEAAXAEBV1@@Z`
- size: `107`
- prototype: `void __fastcall(EventDumpIterator *__hidden this, const struct EventDumpIterator *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f104`
- `0x14000ffcc`

## callees

- `0x14000d96c`
- `0x1400400be`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d994`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000d994`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d9a5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x14000d9a5`

## pseudocode

```c
void __fastcall EventDumpIterator::CopyFrom(EventDumpIterator *this, const struct EventDumpIterator *a2)
{
  int v4; // eax
  unsigned int v5; // esi
  HANDLE ProcessHeap; // rax
  void *v7; // rax

  *((_QWORD *)this + 2) = *((_QWORD *)a2 + 2);
  v4 = *((_DWORD *)a2 + 3);
  *((_DWORD *)this + 3) = v4;
  v5 = 16 * v4;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, v5);
  *(_QWORD *)this = v7;
  if ( v7 )
  {
    memcpy_0(v7, *(const void **)a2, v5);
    *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  }
}

```

## disassembly

```asm
0x14000d96c  mov     [rsp+arg_0], rbx
0x14000d971  mov     [rsp+arg_8], rsi
0x14000d976  push    rdi
0x14000d977  sub     rsp, 20h
0x14000d97b  mov     rax, [rdx+10h]
0x14000d97f  mov     rbx, rdx
0x14000d982  mov     [rcx+10h], rax
0x14000d986  mov     rdi, rcx
0x14000d989  mov     eax, [rdx+0Ch]
0x14000d98c  mov     [rcx+0Ch], eax
0x14000d98f  shl     eax, 4
0x14000d992  mov     esi, eax
0x14000d994  call    cs:__imp_GetProcessHeap
0x14000d99a  mov     r8d, esi; dwBytes
0x14000d99d  mov     edx, 8; dwFlags
0x14000d9a2  mov     rcx, rax; hHeap
0x14000d9a5  call    cs:__imp_HeapAlloc
0x14000d9ab  mov     [rdi], rax
0x14000d9ae  test    rax, rax
0x14000d9b1  jz      short loc_14000D9C7
0x14000d9b3  mov     rdx, [rbx]; Src
0x14000d9b6  mov     r8d, esi; Size
0x14000d9b9  mov     rcx, rax; void *
0x14000d9bc  call    memcpy_0
0x14000d9c1  mov     eax, [rbx+8]
0x14000d9c4  mov     [rdi+8], eax
0x14000d9c7  mov     rbx, [rsp+28h+arg_0]
0x14000d9cc  mov     rsi, [rsp+28h+arg_8]
0x14000d9d1  add     rsp, 20h
0x14000d9d5  pop     rdi
0x14000d9d6  retn
```
