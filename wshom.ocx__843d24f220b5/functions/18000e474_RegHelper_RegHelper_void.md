# RegHelper::~RegHelper(void)

- ea: `0x18000e474`
- end: `0x18000e4a0`
- name: `??1RegHelper@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(RegHelper *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e8b8`
- `0x18000ebac`

## callees

- `0x18000e474`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000e485`
- `ADVAPI32!RegCloseKey` at `0x18000e494`
- `ADVAPI32!RegCloseKey` at `0x18000e485`
- `ADVAPI32!RegCloseKey` at `0x18000e494`

## pseudocode

```c
void __fastcall RegHelper::~RegHelper(HKEY *this)
{
  HKEY v2; // rcx
  HKEY v3; // rcx

  v2 = *this;
  if ( v2 )
    RegCloseKey(v2);
  v3 = this[1];
  if ( v3 )
    RegCloseKey(v3);
}

```

## disassembly

```asm
0x18000e474  push    rbx
0x18000e476  sub     rsp, 20h
0x18000e47a  mov     rbx, rcx
0x18000e47d  mov     rcx, [rcx]; hKey
0x18000e480  test    rcx, rcx
0x18000e483  jz      short loc_18000E48B
0x18000e485  call    cs:__imp_RegCloseKey
0x18000e48b  mov     rcx, [rbx+8]; hKey
0x18000e48f  test    rcx, rcx
0x18000e492  jz      short loc_18000E49A
0x18000e494  call    cs:__imp_RegCloseKey
0x18000e49a  add     rsp, 20h
0x18000e49e  pop     rbx
0x18000e49f  retn
```
