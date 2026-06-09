# _CRegistryKey::CRegistryKey_::_1_::dtor$0

- ea: `0x180010888`
- end: `0x180010898`
- name: `_CRegistryKey::CRegistryKey_::_1_::dtor$0`
- size: `16`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a40c`

## pseudocode

```c
__int64 __fastcall CRegistryKey::CRegistryKey_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(*(_QWORD *)(a2 + 64) + 8LL);
}

```

## disassembly

```asm
0x180010888  mov     rcx, [rdx+40h]
0x18001088f  add     rcx, 8
0x180010893  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
