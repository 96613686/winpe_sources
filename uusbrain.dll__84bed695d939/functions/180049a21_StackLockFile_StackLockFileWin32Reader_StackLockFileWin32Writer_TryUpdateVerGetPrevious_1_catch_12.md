# __StackLockFile_StackLockFileWin32Reader_StackLockFileWin32Writer_::TryUpdateVerGetPrevious_::_1_::catch$12

- ea: `0x180049a21`
- end: `0x180049a66`
- name: `__StackLockFile_StackLockFileWin32Reader_StackLockFileWin32Writer_::TryUpdateVerGetPrevious_::_1_::catch$12`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x180026924`

## string_xrefs

- `0x180049a35`: `Unable to read previous file contents.`

## pseudocode

```c
__int64 __fastcall _StackLockFile_StackLockFileWin32Reader_StackLockFileWin32Writer_::TryUpdateVerGetPrevious_::_1_::catch_12(
        __int64 a1,
        __int64 a2)
{
  const char *v4; // [rsp+20h] [rbp-8h]

  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 136),
    (void *)0x141,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\lib\\StackLockFile.hpp",
    "Unable to read previous file contents.",
    v4);
  *(_BYTE *)(*(_QWORD *)(a2 + 48) + 8LL) = 0;
  return 0;
}

```

## disassembly

```asm
0x180049a21  mov     [rsp+arg_8], rdx
0x180049a26  push    rbp; char *
0x180049a27  sub     rsp, 20h
0x180049a2b  mov     rbp, rdx
0x180049a2e  mov     rcx, [rbp+88h]; this
0x180049a35  lea     r9, aUnableToReadPr; "Unable to read previous file contents."
0x180049a3c  lea     r8, aCW1SSrcBrainLi_3; "C:\\__w\\1\\s\\src\\brain\\lib\\StackLo"...
0x180049a43  mov     edx, 141h; void *
0x180049a48  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180049a4d  mov     rax, [rbp+30h]
0x180049a51  mov     byte ptr [rax+8], 0
0x180049a55  mov     rax, 0
0x180049a5f  add     rsp, 20h
0x180049a63  pop     rbp
0x180049a64  retn
```
