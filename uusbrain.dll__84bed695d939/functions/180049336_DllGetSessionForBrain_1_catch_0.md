# _DllGetSessionForBrain_::_1_::catch$0

- ea: `0x180049336`
- end: `0x180049371`
- name: `_DllGetSessionForBrain_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002572c`
- `0x180025a38`

## string_xrefs

- `0x180049347`: `C:\__w\1\s\src\brain\dll\Module.cpp`

## pseudocode

```c
__int64 __fastcall DllGetSessionForBrain_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil *v5; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x36,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\dll\\Module.cpp",
    a4);
  *(_DWORD *)(a2 + 48) = wil::ResultFromCaughtException(v5);
  return 0;
}

```

## disassembly

```asm
0x180049336  mov     [rsp+arg_8], rdx
0x18004933b  push    rbp
0x18004933c  sub     rsp, 20h
0x180049340  mov     rbp, rdx
0x180049343  mov     rcx, [rbp+28h]; this
0x180049347  lea     r8, aCW1SSrcBrainDl; "C:\\__w\\1\\s\\src\\brain\\dll\\Module."...
0x18004934e  mov     edx, 36h ; '6'; void *
0x180049353  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180049358  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004935d  mov     [rbp+30h], eax
0x180049360  mov     rax, 0
0x18004936a  add     rsp, 20h
0x18004936e  pop     rbp
0x18004936f  retn
```
