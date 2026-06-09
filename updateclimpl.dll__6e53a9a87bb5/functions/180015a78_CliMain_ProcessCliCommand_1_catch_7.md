# _CliMain::ProcessCliCommand_::_1_::catch$7

- ea: `0x180015a78`
- end: `0x180015aae`
- name: `_CliMain::ProcessCliCommand_::_1_::catch$7`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000bf94`

## string_xrefs

- `0x180015a89`: `C:\__w\1\s\src\updatecli\libs\main\CliMain.cpp`

## pseudocode

```c
__int64 __fastcall CliMain::ProcessCliCommand_::_1_::catch_7(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 36) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 104),
                           (void *)0xC,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CliMain.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180015a78  mov     [rsp+arg_8], rdx
0x180015a7d  push    rbp
0x180015a7e  sub     rsp, 20h
0x180015a82  mov     rbp, rdx
0x180015a85  mov     rcx, [rbp+68h]; this
0x180015a89  lea     r8, aCW1SSrcUpdatec; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180015a90  mov     edx, 0Ch; void *
0x180015a95  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180015a9a  mov     [rbp+24h], eax
0x180015a9d  mov     rax, 0
0x180015aa7  add     rsp, 20h
0x180015aab  pop     rbp
0x180015aac  retn
```
