# _DllGetSessionForPinky_::_1_::catch$0

- ea: `0x1800492f5`
- end: `0x180049330`
- name: `_DllGetSessionForPinky_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002572c`
- `0x180025a38`

## string_xrefs

- `0x180049306`: `C:\__w\1\s\src\brain\dll\Module.cpp`

## pseudocode

```c
__int64 __fastcall DllGetSessionForPinky_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil *v5; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x29,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\dll\\Module.cpp",
    a4);
  *(_DWORD *)(a2 + 48) = wil::ResultFromCaughtException(v5);
  return 0;
}

```

## disassembly

```asm
0x1800492f5  mov     [rsp+arg_8], rdx
0x1800492fa  push    rbp
0x1800492fb  sub     rsp, 20h
0x1800492ff  mov     rbp, rdx
0x180049302  mov     rcx, [rbp+28h]; this
0x180049306  lea     r8, aCW1SSrcBrainDl; "C:\\__w\\1\\s\\src\\brain\\dll\\Module."...
0x18004930d  mov     edx, 29h ; ')'; void *
0x180049312  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180049317  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004931c  mov     [rbp+30h], eax
0x18004931f  mov     rax, 0
0x180049329  add     rsp, 20h
0x18004932d  pop     rbp
0x18004932e  retn
```
