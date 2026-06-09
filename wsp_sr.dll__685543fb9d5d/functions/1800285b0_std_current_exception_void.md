# std::current_exception(void)

- ea: `0x1800285b0`
- end: `0x1800285ed`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `61`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800287d8`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800285d7`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800285d7`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800285c8`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800285c8`

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
0x1800285b0  push    rbx
0x1800285b2  sub     rsp, 20h
0x1800285b6  mov     rbx, rcx
0x1800285b9  mov     qword ptr [rcx], 0
0x1800285c0  mov     qword ptr [rcx+8], 0
0x1800285c8  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800285cf  nop     dword ptr [rax+rax+00h]
0x1800285d4  mov     rcx, rbx
0x1800285d7  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800285de  nop     dword ptr [rax+rax+00h]
0x1800285e3  mov     rax, rbx
0x1800285e6  add     rsp, 20h
0x1800285ea  pop     rbx
0x1800285eb  retn
```
