# CDevNodeCollection::AddDeviceInterface(_GUID const &)

- ea: `0x18000823c`
- end: `0x18000828a`
- name: `?AddDeviceInterface@CDevNodeCollection@@QEAAXAEBU_GUID@@@Z`
- size: `78`
- prototype: `void __fastcall(CDevNodeCollection *__hidden this, const struct _GUID *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cf4`
- `0x18000450c`
- `0x180005314`
- `0x180005a48`
- `0x180005da0`
- `0x1800065f8`

## callees

- `0x180008020`
- `0x18000823c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008272`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008268`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008272`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000825e`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000825e`

## pseudocode

```c
void __fastcall CDevNodeCollection::AddDeviceInterface(CDevNodeCollection *this, const struct _GUID *a2)
{
  DWORD LastError; // eax

  if ( !(unsigned int)DevObjGetClassDevs(*(_QWORD *)this, a2, 0, 16, 0, 0) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      CException::ThrowException(LastError, 0, 0);
    }
  }
}

```

## disassembly

```asm
0x18000823c  sub     rsp, 38h
0x180008240  mov     rcx, [rcx]
0x180008243  mov     r9d, 10h
0x180008249  mov     [rsp+38h+var_10], 0
0x180008252  xor     r8d, r8d
0x180008255  mov     [rsp+38h+var_18], 0
0x18000825e  call    cs:__imp_DevObjGetClassDevs
0x180008264  test    eax, eax
0x180008266  jnz     short loc_180008285
0x180008268  call    cs:__imp_GetLastError
0x18000826e  test    eax, eax
0x180008270  jz      short loc_180008285
0x180008272  call    cs:__imp_GetLastError
0x180008278  xor     r8d, r8d
0x18000827b  xor     edx, edx
0x18000827d  mov     ecx, eax
0x18000827f  call    ?ThrowException@CException@@SAXKW4ErrorCodeType@@PEBGZZ; CException::ThrowException(ulong,ErrorCodeType,ushort const *,...)
0x180008285  add     rsp, 38h
0x180008289  retn
```
