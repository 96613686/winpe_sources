# std::current_exception(void)

- ea: `0x18007cc4c`
- end: `0x18007cc7c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18007ce4c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007cc6d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007cc6d`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007cc64`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007cc64`

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
0x18007cc4c  push    rbx
0x18007cc4e  sub     rsp, 20h
0x18007cc52  mov     rbx, rcx
0x18007cc55  mov     qword ptr [rcx], 0
0x18007cc5c  mov     qword ptr [rcx+8], 0
0x18007cc64  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007cc6a  mov     rcx, rbx
0x18007cc6d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18007cc73  mov     rax, rbx
0x18007cc76  add     rsp, 20h
0x18007cc7a  pop     rbx
0x18007cc7b  retn
```
