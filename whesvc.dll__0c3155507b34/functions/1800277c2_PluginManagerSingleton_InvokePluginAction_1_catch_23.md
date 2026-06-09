# _PluginManagerSingleton::InvokePluginAction_::_1_::catch$23

- ea: `0x1800277c2`
- end: `0x1800277ff`
- name: `_PluginManagerSingleton::InvokePluginAction_::_1_::catch$23`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009044`

## string_xrefs

- `0x1800277dc`: `pcshell\base\whesvc\lib\pluginmanager.cpp`

## pseudocode

```c
__int64 __fastcall PluginManagerSingleton::InvokePluginAction_::_1_::catch_23(__int64 a1, __int64 a2)
{
  wil::details::in1diag3::Return_Hr(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x49,
    (int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
    (const char *)0x8007000ELL);
  return 0;
}

```

## disassembly

```asm
0x1800277c2  mov     [rsp+arg_8], rdx
0x1800277c7  push    rbp; int
0x1800277c8  sub     rsp, 20h
0x1800277cc  mov     rbp, rdx
0x1800277cf  mov     rcx, [rbp+0B8h]; this
0x1800277d6  mov     r9d, 8007000Eh; char *
0x1800277dc  lea     r8, aPcshellBaseWhe_3; "pcshell\\base\\whesvc\\lib\\pluginmanag"...
0x1800277e3  mov     edx, 49h ; 'I'; void *
0x1800277e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277ed  nop
0x1800277ee  mov     rax, 0
0x1800277f8  add     rsp, 20h
0x1800277fc  pop     rbp
0x1800277fd  retn
```
