# GetLastErrorHRESULT(void)

- ea: `0x180003b90`
- end: `0x180003bab`
- name: `?GetLastErrorHRESULT@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x1800053f0`
- `0x1800060fc`
- `0x180006374`
- `0x18000d070`
- `0x18000d858`
- `0x18000e140`
- `0x18000e8bc`
- `0x18000f010`
- `0x18000fa80`
- `0x18000fba4`
- `0x18000fd80`
- `0x18000ff64`
- `0x180010130`
- `0x1800102e0`
- `0x180010400`
- `0x1800105c0`
- `0x180010ff4`
- `0x180011664`
- `0x180011e28`
- `0x180012044`
- `0x1800123e0`
- `0x18001250c`

## callees

- `0x180003b90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b94`

## pseudocode

```c
signed int GetLastErrorHRESULT(void)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180003b90  sub     rsp, 28h
0x180003b94  call    cs:__imp_GetLastError
0x180003b9a  test    eax, eax
0x180003b9c  jle     short loc_180003BA6
0x180003b9e  movzx   eax, ax
0x180003ba1  or      eax, 80070000h
0x180003ba6  add     rsp, 28h
0x180003baa  retn
```
