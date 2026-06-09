# _RemoveUnusedPackages_::_1_::catch$0

- ea: `0x180049377`
- end: `0x1800493b2`
- name: `_RemoveUnusedPackages_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002572c`
- `0x180025a38`

## string_xrefs

- `0x180049388`: `C:\__w\1\s\src\brain\dll\Module.cpp`

## pseudocode

```c
__int64 __fastcall RemoveUnusedPackages_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil *v5; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 40),
    (void *)0x42,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\dll\\Module.cpp",
    a4);
  *(_DWORD *)(a2 + 56) = wil::ResultFromCaughtException(v5);
  return 0;
}

```

## disassembly

```asm
0x180049377  mov     [rsp+arg_8], rdx
0x18004937c  push    rbp
0x18004937d  sub     rsp, 20h
0x180049381  mov     rbp, rdx
0x180049384  mov     rcx, [rbp+28h]; this
0x180049388  lea     r8, aCW1SSrcBrainDl; "C:\\__w\\1\\s\\src\\brain\\dll\\Module."...
0x18004938f  mov     edx, 42h ; 'B'; void *
0x180049394  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180049399  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18004939e  mov     [rbp+38h], eax
0x1800493a1  mov     rax, 0
0x1800493ab  add     rsp, 20h
0x1800493af  pop     rbp
0x1800493b0  retn
```
