# _GetSession_::_1_::catch$0

- ea: `0x1800492b4`
- end: `0x1800492ef`
- name: `_GetSession_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18002572c`
- `0x180025a38`

## string_xrefs

- `0x1800492c5`: `C:\__w\1\s\src\brain\dll\Module.cpp`

## pseudocode

```c
__int64 __fastcall GetSession_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil *v5; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0x1C,
    (unsigned int)"C:\\__w\\1\\s\\src\\brain\\dll\\Module.cpp",
    a4);
  *(_DWORD *)(a2 + 32) = wil::ResultFromCaughtException(v5);
  return 0;
}

```

## disassembly

```asm
0x1800492b4  mov     [rsp+arg_8], rdx
0x1800492b9  push    rbp
0x1800492ba  sub     rsp, 20h
0x1800492be  mov     rbp, rdx
0x1800492c1  mov     rcx, [rbp+78h]; this
0x1800492c5  lea     r8, aCW1SSrcBrainDl; "C:\\__w\\1\\s\\src\\brain\\dll\\Module."...
0x1800492cc  mov     edx, 1Ch; void *
0x1800492d1  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800492d6  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x1800492db  mov     [rbp+20h], eax
0x1800492de  mov     rax, 0
0x1800492e8  add     rsp, 20h
0x1800492ec  pop     rbp
0x1800492ed  retn
```
