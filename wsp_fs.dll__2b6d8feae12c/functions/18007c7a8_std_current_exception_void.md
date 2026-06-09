# std::current_exception(void)

- ea: `0x18007c7a8`
- end: `0x18007c7d8`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18007c9a8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c7c0`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007c7c0`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007c7c9`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007c7c9`

## pseudocode

```c
_QWORD *__fastcall std::current_exception(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  __ExceptionPtrCreate(a1);
  __ExceptionPtrCurrentException(a1);
  return a1;
}

```

## disassembly

```asm
0x18007c7a8  push    rbx
0x18007c7aa  sub     rsp, 20h
0x18007c7ae  mov     rbx, rcx
0x18007c7b1  mov     qword ptr [rcx], 0
0x18007c7b8  mov     qword ptr [rcx+8], 0
0x18007c7c0  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007c7c6  mov     rcx, rbx
0x18007c7c9  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18007c7cf  mov     rax, rbx
0x18007c7d2  add     rsp, 20h
0x18007c7d6  pop     rbx
0x18007c7d7  retn
```
