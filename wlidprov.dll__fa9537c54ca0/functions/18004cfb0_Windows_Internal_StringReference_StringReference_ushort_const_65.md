# Windows::Internal::StringReference::StringReference(ushort const (&)[65])

- ea: `0x18004cfb0`
- end: `0x18004cff4`
- name: `??$?0$0EB@@StringReference@Internal@Windows@@QEAA@AEAY0EB@$$CBG@Z`
- size: `68`
- prototype: `__int64 __fastcall(HSTRING *string, const unsigned __int16 (*)[65])`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004d588`
- `0x18004d77c`

## callees

- `0x18004cfb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004cfe5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004cfe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cfcc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004cfcc`

## string_xrefs

- `0x18004cfc5`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
HSTRING *__fastcall Windows::Internal::StringReference::StringReference(
        HSTRING *string,
        const unsigned __int16 (*a2)[65])
{
  if ( WindowsCreateStringReference(
         L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
         0x40u,
         (HSTRING_HEADER *)(string + 1),
         string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  return string;
}

```

## disassembly

```asm
0x18004cfb0  push    rbx
0x18004cfb2  sub     rsp, 20h
0x18004cfb6  mov     rbx, rcx
0x18004cfb9  lea     r8, [rcx+8]; hstringHeader
0x18004cfbd  mov     r9, rcx; string
0x18004cfc0  mov     edx, 40h ; '@'; length
0x18004cfc5  lea     rcx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18004cfcc  call    cs:__imp_WindowsCreateStringReference
0x18004cfd2  test    eax, eax
0x18004cfd4  jns     short loc_18004CFEB
0x18004cfd6  xor     r9d, r9d; lpArguments
0x18004cfd9  xor     r8d, r8d; nNumberOfArguments
0x18004cfdc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004cfe1  lea     edx, [r9+1]; dwExceptionFlags
0x18004cfe5  call    cs:__imp_RaiseException
0x18004cfeb  mov     rax, rbx
0x18004cfee  add     rsp, 20h
0x18004cff2  pop     rbx
0x18004cff3  retn
```
