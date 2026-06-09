# std::current_exception(void)

- ea: `0x1800281c4`
- end: `0x1800281f4`
- name: `?current_exception@std@@YA?AVexception_ptr@1@XZ`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800283ac`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800281e5`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800281e5`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800281dc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800281dc`

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
0x1800281c4  push    rbx
0x1800281c6  sub     rsp, 20h
0x1800281ca  mov     rbx, rcx
0x1800281cd  mov     qword ptr [rcx], 0
0x1800281d4  mov     qword ptr [rcx+8], 0
0x1800281dc  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800281e2  mov     rcx, rbx
0x1800281e5  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800281eb  mov     rax, rbx
0x1800281ee  add     rsp, 20h
0x1800281f2  pop     rbx
0x1800281f3  retn
```
