# _PluginManagerSingleton::InvokePluginAction_::_1_::catch$24

- ea: `0x180027805`
- end: `0x180027842`
- name: `_PluginManagerSingleton::InvokePluginAction_::_1_::catch$24`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180009044`

## string_xrefs

- `0x18002781f`: `pcshell\base\whesvc\lib\pluginmanager.cpp`

## pseudocode

```c
__int64 __fastcall PluginManagerSingleton::InvokePluginAction_::_1_::catch_24(__int64 a1, __int64 a2)
{
  wil::details::in1diag3::Return_Hr(
    *(wil::details::in1diag3 **)(a2 + 184),
    (void *)0x4D,
    (int)"pcshell\\base\\whesvc\\lib\\pluginmanager.cpp",
    (const char *)0x80004005LL);
  return 0;
}

```

## disassembly

```asm
0x180027805  mov     [rsp+arg_8], rdx
0x18002780a  push    rbp; int
0x18002780b  sub     rsp, 20h
0x18002780f  mov     rbp, rdx
0x180027812  mov     rcx, [rbp+0B8h]; this
0x180027819  mov     r9d, 80004005h; char *
0x18002781f  lea     r8, aPcshellBaseWhe_3; "pcshell\\base\\whesvc\\lib\\pluginmanag"...
0x180027826  mov     edx, 4Dh ; 'M'; void *
0x18002782b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027830  nop
0x180027831  mov     rax, 0
0x18002783b  add     rsp, 20h
0x18002783f  pop     rbp
0x180027840  retn
```
