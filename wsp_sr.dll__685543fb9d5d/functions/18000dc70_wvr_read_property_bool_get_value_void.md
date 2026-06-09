# wvr::read_property<bool>::get_value(void)

- ea: `0x18000dc70`
- end: `0x18000dc94`
- name: `?get_value@?$read_property@_N@wvr@@QEBA?B_NXZ`
- size: `36`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180008ad4`
- `0x1800137bc`
- `0x180013b60`
- `0x180015c58`
- `0x180015d2c`
- `0x180016684`
- `0x1800191e0`

## callees

- `0x180007168`

## pseudocode

```c
char __fastcall wvr::read_property<bool>::get_value(_QWORD *a1)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  mi::MiInstance::GetElement<bool>(*a1, a1 + 1, &v2);
  return v2;
}

```

## disassembly

```asm
0x18000dc70  sub     rsp, 28h
0x18000dc74  lea     rdx, [rcx+8]
0x18000dc78  mov     [rsp+28h+arg_0], 0
0x18000dc7d  mov     rcx, [rcx]
0x18000dc80  lea     r8, [rsp+28h+arg_0]
0x18000dc85  call    ??$GetElement@_N@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEA_N@Z; mi::MiInstance::GetElement<bool>(std::wstring const &,bool &)
0x18000dc8a  mov     al, [rsp+28h+arg_0]
0x18000dc8e  add     rsp, 28h
0x18000dc92  retn
```
