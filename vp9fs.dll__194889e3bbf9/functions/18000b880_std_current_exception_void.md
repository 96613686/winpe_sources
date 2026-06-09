# std::current_exception(void)

- ea: `0x18000b880`
- end: `0x18000b8b0`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c950`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18000b8a1`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x18000b8a1`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000b898`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x18000b898`

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
0x18000b880  push    rbx
0x18000b882  sub     rsp, 20h
0x18000b886  mov     rbx, rcx
0x18000b889  mov     qword ptr [rcx], 0
0x18000b890  mov     qword ptr [rcx+8], 0
0x18000b898  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18000b89e  mov     rcx, rbx
0x18000b8a1  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x18000b8a7  mov     rax, rbx
0x18000b8aa  add     rsp, 20h
0x18000b8ae  pop     rbx
0x18000b8af  retn
```
