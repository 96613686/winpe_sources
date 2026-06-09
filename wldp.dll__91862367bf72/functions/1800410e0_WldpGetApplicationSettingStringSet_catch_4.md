# WldpGetApplicationSettingStringSet$catch$4

- ea: `0x1800410e0`
- end: `0x180041119`
- name: `WldpGetApplicationSettingStringSet$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x1800410f4`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall WldpGetApplicationSettingStringSet_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x4D5,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800410e0  mov     [rsp+arg_8], rdx
0x1800410e5  push    rbp
0x1800410e6  sub     rsp, 30h
0x1800410ea  mov     rbp, rdx
0x1800410ed  mov     rcx, [rbp+0D8h]; this
0x1800410f4  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800410fb  mov     edx, 4D5h; void *
0x180041100  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180041105  mov     [rbp+38h], eax
0x180041108  mov     rax, 0
0x180041112  add     rsp, 30h
0x180041116  pop     rbp
0x180041117  retn
```
