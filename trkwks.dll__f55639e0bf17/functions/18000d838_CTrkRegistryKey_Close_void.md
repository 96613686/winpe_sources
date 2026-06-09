# CTrkRegistryKey::Close(void)

- ea: `0x18000d838`
- end: `0x18000d85c`
- name: `?Close@CTrkRegistryKey@@AEAAXXZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000d814`

## callees

- `0x18000d838`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d849`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000d849`

## pseudocode

```c
void __fastcall CTrkRegistryKey::Close(HKEY *this)
{
  HKEY v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    RegCloseKey(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000d838  push    rbx
0x18000d83a  sub     rsp, 20h
0x18000d83e  mov     rbx, rcx
0x18000d841  mov     rcx, [rcx]; hKey
0x18000d844  test    rcx, rcx
0x18000d847  jz      short loc_18000D856
0x18000d849  call    cs:__imp_RegCloseKey
0x18000d84f  mov     qword ptr [rbx], 0
0x18000d856  add     rsp, 20h
0x18000d85a  pop     rbx
0x18000d85b  retn
```
