# wvr::read_property<uint>::get_value(void)

- ea: `0x18000dcbc`
- end: `0x18000dce2`
- name: `?get_value@?$read_property@I@wvr@@QEBA?BIXZ`
- size: `38`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b48c`
- `0x18000b98c`
- `0x18000cfa4`
- `0x1800126cc`
- `0x180013c50`

## callees

- `0x180006a08`

## pseudocode

```c
__int64 __fastcall wvr::read_property<unsigned int>::get_value(_QWORD *a1)
{
  unsigned int v2; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  mi::MiInstance::GetElement<unsigned int>(*a1, a1 + 1, &v2);
  return v2;
}

```

## disassembly

```asm
0x18000dcbc  sub     rsp, 28h
0x18000dcc0  lea     rdx, [rcx+8]
0x18000dcc4  mov     [rsp+28h+arg_0], 0
0x18000dccc  mov     rcx, [rcx]
0x18000dccf  lea     r8, [rsp+28h+arg_0]
0x18000dcd4  call    ??$GetElement@I@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAI@Z; mi::MiInstance::GetElement<uint>(std::wstring const &,uint &)
0x18000dcd9  mov     eax, [rsp+28h+arg_0]
0x18000dcdd  add     rsp, 28h
0x18000dce1  retn
```
