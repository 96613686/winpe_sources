# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180012c34`
- end: `0x180012c62`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: `__int64 __fastcall(std::exception_ptr *__hidden this, const struct std::exception_ptr *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18007ee3c`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180012c4c`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180012c4c`

## pseudocode

```c
std::exception_ptr *__fastcall std::exception_ptr::exception_ptr(
        std::exception_ptr *this,
        const struct std::exception_ptr *a2)
{
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  __ExceptionPtrCopy(this, a2);
  return this;
}

```

## disassembly

```asm
0x180012c34  push    rbx
0x180012c36  sub     rsp, 20h
0x180012c3a  mov     rbx, rcx
0x180012c3d  mov     qword ptr [rcx], 0
0x180012c44  mov     qword ptr [rcx+8], 0
0x180012c4c  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180012c53  nop     dword ptr [rax+rax+00h]
0x180012c58  mov     rax, rbx
0x180012c5b  add     rsp, 20h
0x180012c5f  pop     rbx
0x180012c60  retn
```
