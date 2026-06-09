# _SETUPCLN_ENUM_PATH_STATE::~_SETUPCLN_ENUM_PATH_STATE(void)

- ea: `0x180003ea8`
- end: `0x180003eb1`
- name: `??1_SETUPCLN_ENUM_PATH_STATE@@QEAA@XZ`
- size: `9`
- prototype: `void __fastcall(_SETUPCLN_ENUM_PATH_STATE *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013714`

## callees

- `0x180003c54`

## pseudocode

```c
void __fastcall _SETUPCLN_ENUM_PATH_STATE::~_SETUPCLN_ENUM_PATH_STATE(_SETUPCLN_ENUM_PATH_STATE *this)
{
  std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>((_QWORD *)this + 12);
}

```

## disassembly

```asm
0x180003ea8  add     rcx, 60h ; '`'
0x180003eac  jmp     ??1?$_Hash@V?$_Uset_traits@_KV?$_Uhash_compare@_KU?$hash@_K@std@@U?$equal_to@_K@2@@std@@V?$allocator@_K@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<std::_Uset_traits<unsigned __int64,std::_Uhash_compare<unsigned __int64,std::hash<unsigned __int64>,std::equal_to<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
```
