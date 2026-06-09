# CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)

- ea: `0x18000d0a0`
- end: `0x18000d0bb`
- name: `?_EqualKeys@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d0a4`
- `msvcrt!_wcsicmp` at `0x18000d0a4`

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
0x18000d0a0  sub     rsp, 28h
0x18000d0a4  call    cs:__imp__wcsicmp
0x18000d0ab  nop     dword ptr [rax+rax+00h]
0x18000d0b0  test    eax, eax
0x18000d0b2  setz    al
0x18000d0b5  add     rsp, 28h
0x18000d0b9  retn
```
