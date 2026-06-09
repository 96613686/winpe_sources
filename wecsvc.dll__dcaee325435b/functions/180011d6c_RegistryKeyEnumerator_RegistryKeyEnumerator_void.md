# RegistryKeyEnumerator::~RegistryKeyEnumerator(void)

- ea: `0x180011d6c`
- end: `0x180011d91`
- name: `??1RegistryKeyEnumerator@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `14`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180003c10`
- `0x18000d15c`
- `0x1800155e8`
- `0x180015f78`
- `0x18001764c`
- `0x18001ab58`
- `0x18001b998`
- `0x180021702`
- `0x1800222e4`
- `0x1800223c8`
- `0x18002244e`
- `0x1800224cc`
- `0x1800225b2`
- `0x1800226c5`

## callees

- `0x180006334`
- `0x180011d6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011d7d`

## pseudocode

```c
void __fastcall RegistryKeyEnumerator::~RegistryKeyEnumerator(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
    RegCloseKey(v2);
  std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>((__int64)(this + 2));
}

```

## disassembly

```asm
0x180011d6c  push    rbx
0x180011d6e  sub     rsp, 20h
0x180011d72  mov     rbx, rcx
0x180011d75  mov     rcx, [rcx]; hKey
0x180011d78  test    rcx, rcx
0x180011d7b  jz      short loc_180011D83
0x180011d7d  call    cs:__imp_RegCloseKey
0x180011d83  lea     rcx, [rbx+10h]
0x180011d87  add     rsp, 20h
0x180011d8b  pop     rbx
0x180011d8c  jmp     ??1?$vector@U_WSMAN_OPTION@@V?$allocator@U_WSMAN_OPTION@@@std@@@std@@QEAA@XZ; std::vector<_WSMAN_OPTION>::~vector<_WSMAN_OPTION>(void)
```
