# ATL::CRegKey::~CRegKey(void)

- ea: `0x18000230c`
- end: `0x180002330`
- name: `??1CRegKey@ATL@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800050c4`
- `0x1800050d6`

## callees

- `0x18000230c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000231d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000231d`

## pseudocode

```c
void __fastcall ATL::CRegKey::~CRegKey(HKEY *this)
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
0x18000230c  push    rbx
0x18000230e  sub     rsp, 20h
0x180002312  mov     rbx, rcx
0x180002315  mov     rcx, [rcx]; hKey
0x180002318  test    rcx, rcx
0x18000231b  jz      short loc_18000232A
0x18000231d  call    cs:__imp_RegCloseKey
0x180002323  mov     qword ptr [rbx], 0
0x18000232a  add     rsp, 20h
0x18000232e  pop     rbx
0x18000232f  retn
```
