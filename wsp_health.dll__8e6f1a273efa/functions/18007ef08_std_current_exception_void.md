# std::current_exception(void)

- ea: `0x18007ef08`
- end: `0x18007ef45`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18007f148`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007ef2f`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18007ef2f`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007ef20`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18007ef20`

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
0x18007ef08  push    rbx
0x18007ef0a  sub     rsp, 20h
0x18007ef0e  mov     rbx, rcx
0x18007ef11  mov     qword ptr [rcx], 0
0x18007ef18  mov     qword ptr [rcx+8], 0
0x18007ef20  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18007ef27  nop     dword ptr [rax+rax+00h]
0x18007ef2c  mov     rcx, rbx
0x18007ef2f  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18007ef36  nop     dword ptr [rax+rax+00h]
0x18007ef3b  mov     rax, rbx
0x18007ef3e  add     rsp, 20h
0x18007ef42  pop     rbx
0x18007ef43  retn
```
