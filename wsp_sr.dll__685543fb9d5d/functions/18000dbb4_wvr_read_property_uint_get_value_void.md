# wvr::read_property<uint>::get_value(void)

- ea: `0x18000dbb4`
- end: `0x18000dbdb`
- name: `?get_value@?$read_property@I@wvr@@QEBA?BIXZ`
- size: `39`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b5f8`
- `0x18000bab8`
- `0x18000cec8`
- `0x180012594`
- `0x180013b60`

## callees

- `0x180006ac0`

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
0x18000dbb4  sub     rsp, 28h
0x18000dbb8  lea     rdx, [rcx+8]
0x18000dbbc  mov     [rsp+28h+arg_0], 0
0x18000dbc4  mov     rcx, [rcx]
0x18000dbc7  lea     r8, [rsp+28h+arg_0]
0x18000dbcc  call    ??$GetElement@I@MiInstance@mi@@QEBAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAI@Z; mi::MiInstance::GetElement<uint>(std::wstring const &,uint &)
0x18000dbd1  mov     eax, [rsp+28h+arg_0]
0x18000dbd5  add     rsp, 28h
0x18000dbd9  retn
```
