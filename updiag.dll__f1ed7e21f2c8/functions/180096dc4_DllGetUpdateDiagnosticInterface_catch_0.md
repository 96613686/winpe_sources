# DllGetUpdateDiagnosticInterface$catch$0

- ea: `0x180096dc4`
- end: `0x180096e01`
- name: `DllGetUpdateDiagnosticInterface$catch$0`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180008ebc`

## string_xrefs

- `0x180096ddc`: `C:\__w\1\s\src\Calliope\dll\Module.cpp`
- `0x180096dd5`: `Error getting UpdateDiagnostics interface`

## pseudocode

```c
__int64 __fastcall DllGetUpdateDiagnosticInterface_catch_0(__int64 a1, __int64 a2)
{
  const char *v3; // [rsp+20h] [rbp-8h]

  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtExceptionMsg(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x13,
                           (unsigned int)"C:\\__w\\1\\s\\src\\Calliope\\dll\\Module.cpp",
                           "Error getting UpdateDiagnostics interface",
                           v3);
  return 0;
}

```

## disassembly

```asm
0x180096dc4  mov     [rsp+arg_8], rdx
0x180096dc9  push    rbp; char *
0x180096dca  sub     rsp, 20h
0x180096dce  mov     rbp, rdx
0x180096dd1  mov     rcx, [rbp+28h]; this
0x180096dd5  lea     r9, aErrorGettingUp; "Error getting UpdateDiagnostics interfa"...
0x180096ddc  lea     r8, aCW1SSrcCalliop_9; "C:\\__w\\1\\s\\src\\Calliope\\dll\\Modu"...
0x180096de3  mov     edx, 13h; void *
0x180096de8  call    ?Return_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180096ded  mov     [rbp+30h], eax
0x180096df0  mov     rax, 0
0x180096dfa  add     rsp, 20h
0x180096dfe  pop     rbp
0x180096dff  retn
```
