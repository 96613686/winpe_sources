# std::exception_ptr::exception_ptr(std::exception_ptr const &)

- ea: `0x180005dd0`
- end: `0x180005df7`
- name: `??0exception_ptr@std@@QEAA@AEBV01@@Z`
- size: `39`
- prototype: `__int64 __fastcall(std::exception_ptr *__hidden this, const struct std::exception_ptr *)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e5a0`
- `0x18000e930`
- `0x18000ec20`
- `0x18000ef00`
- `0x18000f2d0`
- `0x18000f950`
- `0x180010160`
- `0x180010d90`
- `0x180012700`
- `0x1800133e0`
- `0x180015ad0`
- `0x180016b50`
- `0x180017090`
- `0x180017570`
- `0x1800183c0`
- `0x180020600`
- `0x1800221d0`
- `0x180027950`
- `0x18002b190`

## import_xrefs

- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180005de8`
- `msvcp_win!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180005de8`

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
0x180005dd0  push    rbx
0x180005dd2  sub     rsp, 20h
0x180005dd6  mov     rbx, rcx
0x180005dd9  mov     qword ptr [rcx], 0
0x180005de0  mov     qword ptr [rcx+8], 0
0x180005de8  call    cs:__imp_?__ExceptionPtrCopy@@YAXPEAXPEBX@Z; __ExceptionPtrCopy(void *,void const *)
0x180005dee  mov     rax, rbx
0x180005df1  add     rsp, 20h
0x180005df5  pop     rbx
0x180005df6  retn
```
