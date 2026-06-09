# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x18000c1b0`
- end: `0x18000c1c4`
- name: `?_EqualKeys@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000c1b4`
- `msvcrt!_wcsicmp` at `0x18000c1b4`

## pseudocode

```c
bool __fastcall CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_EqualKeys(
        const wchar_t *a1,
        const wchar_t *a2)
{
  return _wcsicmp(a1, a2) == 0;
}

```

## disassembly

```asm
0x18000c1b0  sub     rsp, 28h
0x18000c1b4  call    cs:__imp__wcsicmp
0x18000c1ba  test    eax, eax
0x18000c1bc  setz    al
0x18000c1bf  add     rsp, 28h
0x18000c1c3  retn
```
