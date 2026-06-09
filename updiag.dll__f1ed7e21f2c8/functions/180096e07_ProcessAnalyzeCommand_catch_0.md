# ProcessAnalyzeCommand$catch$0

- ea: `0x180096e07`
- end: `0x180096e4d`
- name: `ProcessAnalyzeCommand$catch$0`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008ebc`

## string_xrefs

- `0x180096e28`: `C:\__w\1\s\src\Calliope\dll\Module.cpp`
- `0x180096e21`: `Error processing UpdateCli command line: %ws`

## pseudocode

```c
__int64 __fastcall ProcessAnalyzeCommand_catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtExceptionMsg(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x1B,
                           (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\dll\\Module.cpp",
                           "Error processing UpdateCli command line: %ws",
                           *(const char **)(a2 + 64));
  return 0;
}

```

## disassembly

```asm
0x180096e07  mov     [rsp+arg_8], rdx
0x180096e0c  push    rbp
0x180096e0d  sub     rsp, 30h
0x180096e11  mov     rbp, rdx
0x180096e14  mov     rcx, [rbp+38h]; this
0x180096e18  mov     rax, [rbp+40h]
0x180096e1c  mov     [rsp+38h+var_18], rax; char *
0x180096e21  lea     r9, aErrorProcessin; "Error processing UpdateCli command line"...
0x180096e28  lea     r8, aCW1SSrcCalliop_9; "C:\\__w\\1\\s\\src\\Calliope\\dll\\Modu"...
0x180096e2f  mov     edx, 1Bh; void *
0x180096e34  call    ?Return_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180096e39  mov     [rbp+40h], eax
0x180096e3c  mov     rax, 0
0x180096e46  add     rsp, 30h
0x180096e4a  pop     rbp
0x180096e4b  retn
```
