# WldpGetApplicationSettingStringList$catch$4

- ea: `0x1800410a1`
- end: `0x1800410da`
- name: `WldpGetApplicationSettingStringList$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting`

## callees

- `0x18002c520`

## string_xrefs

- `0x1800410b5`: `onecore\base\ngscb\wldp\dll\applicationsetting.cpp`

## pseudocode

```c
__int64 __fastcall WldpGetApplicationSettingStringList_catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 216),
                           (void *)0x47A,
                           (unsigned int)"onecore\\base\\ngscb\\wldp\\dll\\applicationsetting.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800410a1  mov     [rsp+arg_8], rdx
0x1800410a6  push    rbp
0x1800410a7  sub     rsp, 30h
0x1800410ab  mov     rbp, rdx
0x1800410ae  mov     rcx, [rbp+0D8h]; this
0x1800410b5  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\wldp\\dll\\applic"...
0x1800410bc  mov     edx, 47Ah; void *
0x1800410c1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800410c6  mov     [rbp+38h], eax
0x1800410c9  mov     rax, 0
0x1800410d3  add     rsp, 30h
0x1800410d7  pop     rbp
0x1800410d8  retn
```
