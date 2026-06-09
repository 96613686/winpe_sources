# DllUnregisterServer

- ea: `0x18001ceb0`
- end: `0x18001ced8`
- name: `DllUnregisterServer`
- size: `40`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ceb0`
- `0x180038e1c`
- `0x18008f600`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax

  result = sub_180038E1C((IID *)&rclsid, (GUID *)&guidCategory);
  if ( result >= 0 )
    return sub_18008F600(0);
  return result;
}

```

## disassembly

```asm
0x18001ceb0  sub     rsp, 28h
0x18001ceb4  lea     rdx, guidCategory; guidCategory
0x18001cebb  lea     rcx, rclsid; clsidDMO
0x18001cec2  call    sub_180038E1C
0x18001cec7  test    eax, eax
0x18001cec9  js      short loc_18001CED2
0x18001cecb  xor     ecx, ecx
0x18001cecd  call    sub_18008F600
0x18001ced2  add     rsp, 28h
0x18001ced6  retn
```
