# std::current_exception(void)

- ea: `0x18007e5e0`
- end: `0x18007e61d`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18007e820`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007e5f8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007e5f8`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007e607`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007e607`

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
0x18007e5e0  push    rbx
0x18007e5e2  sub     rsp, 20h
0x18007e5e6  mov     rbx, rcx
0x18007e5e9  mov     qword ptr [rcx], 0
0x18007e5f0  mov     qword ptr [rcx+8], 0
0x18007e5f8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007e5ff  nop     dword ptr [rax+rax+00h]
0x18007e604  mov     rcx, rbx
0x18007e607  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18007e60e  nop     dword ptr [rax+rax+00h]
0x18007e613  mov     rax, rbx
0x18007e616  add     rsp, 20h
0x18007e61a  pop     rbx
0x18007e61b  retn
```
