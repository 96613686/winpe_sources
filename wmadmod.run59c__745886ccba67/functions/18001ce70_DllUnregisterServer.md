# DllUnregisterServer

- ea: `0x18001ce70`
- end: `0x18001ce98`
- name: `DllUnregisterServer`
- size: `40`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ce70`
- `0x180038ddc`
- `0x18008f5c0`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax

  result = sub_180038DDC((IID *)&rclsid, (GUID *)&guidCategory);
  if ( result >= 0 )
    return sub_18008F5C0(0);
  return result;
}

```

## disassembly

```asm
0x18001ce70  sub     rsp, 28h
0x18001ce74  lea     rdx, guidCategory; guidCategory
0x18001ce7b  lea     rcx, rclsid; clsidDMO
0x18001ce82  call    sub_180038DDC
0x18001ce87  test    eax, eax
0x18001ce89  js      short loc_18001CE92
0x18001ce8b  xor     ecx, ecx
0x18001ce8d  call    sub_18008F5C0
0x18001ce92  add     rsp, 28h
0x18001ce96  retn
```
