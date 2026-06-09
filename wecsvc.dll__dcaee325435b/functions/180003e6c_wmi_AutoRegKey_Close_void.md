# wmi::AutoRegKey::Close(void)

- ea: `0x180003e6c`
- end: `0x180003e90`
- name: `?Close@AutoRegKey@wmi@@QEAAXXZ`
- size: `36`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `25`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180003b68`
- `0x180003be8`
- `0x180003f08`
- `0x180004b80`
- `0x1800052cc`
- `0x180007c00`
- `0x1800081e4`
- `0x18000d15c`
- `0x18000e134`
- `0x18000e2f8`
- `0x18000f1f8`
- `0x18000f3d0`
- `0x18000f8bc`
- `0x18000fd88`
- `0x1800103b8`
- `0x1800155e8`
- `0x180015844`
- `0x180015dd4`
- `0x180015f78`
- `0x18001718c`
- `0x18001764c`
- `0x18001780c`
- `0x1800178f0`
- `0x18001ab58`
- `0x18001b998`

## callees

- `0x180003e6c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e7d`

## pseudocode

```c
void __fastcall wmi::AutoRegKey::Close(HKEY *this)
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
0x180003e6c  push    rbx
0x180003e6e  sub     rsp, 20h
0x180003e72  mov     rbx, rcx
0x180003e75  mov     rcx, [rcx]; hKey
0x180003e78  test    rcx, rcx
0x180003e7b  jz      short loc_180003E8A
0x180003e7d  call    cs:__imp_RegCloseKey
0x180003e83  mov     qword ptr [rbx], 0
0x180003e8a  add     rsp, 20h
0x180003e8e  pop     rbx
0x180003e8f  retn
```
