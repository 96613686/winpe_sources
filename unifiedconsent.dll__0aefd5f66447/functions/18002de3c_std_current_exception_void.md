# std::current_exception(void)

- ea: `0x18002de3c`
- end: `0x18002de6c`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180030878`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002de54`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18002de54`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002de5d`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18002de5d`

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
0x18002de3c  push    rbx
0x18002de3e  sub     rsp, 20h
0x18002de42  mov     rbx, rcx
0x18002de45  mov     qword ptr [rcx], 0
0x18002de4c  mov     qword ptr [rcx+8], 0
0x18002de54  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18002de5a  mov     rcx, rbx
0x18002de5d  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18002de63  mov     rax, rbx
0x18002de66  add     rsp, 20h
0x18002de6a  pop     rbx
0x18002de6b  retn
```
