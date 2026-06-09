# WldpGetApplicationSettingBoolean$catch$4

- ea: `0x18004105f`
- end: `0x18004109b`
- name: `WldpGetApplicationSettingBoolean$catch$4`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x180041073`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall WldpGetApplicationSettingBoolean_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 216) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 184),
                            (void *)0x420,
                            (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18004105f  mov     [rsp+arg_8], rdx
0x180041064  push    rbp
0x180041065  sub     rsp, 30h
0x180041069  mov     rbp, rdx
0x18004106c  mov     rcx, [rbp+0B8h]; this
0x180041073  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x18004107a  mov     edx, 420h; void *
0x18004107f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180041084  mov     [rbp+0D8h], eax
0x18004108a  mov     rax, 0
0x180041094  add     rsp, 30h
0x180041098  pop     rbp
0x180041099  retn
```
