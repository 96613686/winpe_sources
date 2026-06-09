# MapHttpStatusToDescription(ushort)

- ea: `0x18001a648`
- end: `0x18001a90b`
- name: `?MapHttpStatusToDescription@@YAPEBDG@Z`
- size: `707`
- prototype: `const char *__fastcall(unsigned __int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014104`

## callees

- `0x18001a648`

## string_xrefs

- `0x18001a6a1`: `Created`
- `0x18001a6b1`: `Switching Protocols`
- `0x18001a711`: `Moved Permanently`
- `0x18001a744`: `Temporary Redirect`
- `0x18001a8a2`: `Request-URI Too Long`
- `0x18001a8f3`: `Service Unavailable`

## pseudocode

```c
const char *__fastcall MapHttpStatusToDescription(unsigned __int16 a1)
{
  if ( a1 <= 0x195u )
  {
    if ( a1 == 405 )
      return "Method Not Allowed";
    if ( a1 > 0x12Du )
    {
      if ( a1 > 0x134u )
      {
        switch ( a1 )
        {
          case 0x190u:
            return "Bad Request";
          case 0x191u:
            return "Unauthorized";
          case 0x192u:
            return "Payment Required";
          case 0x193u:
            return "Forbidden";
          case 0x194u:
            return "Not Found";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0x134u:
            return "Permanent Redirect";
          case 0x12Eu:
            return "Found";
          case 0x12Fu:
            return "See Other";
          case 0x130u:
            return "Not Modified";
          case 0x131u:
            return "Use Proxy";
          case 0x133u:
            return "Temporary Redirect";
        }
      }
    }
    else
    {
      if ( a1 == 301 )
        return "Moved Permanently";
      if ( a1 > 0xCBu )
      {
        switch ( a1 )
        {
          case 0xCCu:
            return "No Content";
          case 0xCDu:
            return "Reset Content";
          case 0xCEu:
            return "Partial Content";
          case 0xCFu:
            return "Multi-Status";
          case 0x12Cu:
            return "Multiple Choices";
        }
      }
      else
      {
        switch ( a1 )
        {
          case 0xCBu:
            return "Non-Authoritative Information";
          case 0x64u:
            return "Continue";
          case 0x65u:
            return "Switching Protocols";
          case 0xC8u:
            return "OK";
          case 0xC9u:
            return "Created";
          case 0xCAu:
            return "Accepted";
        }
      }
    }
    return "Unknown";
  }
  if ( a1 <= 0x1F4u )
  {
    if ( a1 == 500 )
      return "Internal Server Error";
    if ( a1 > 0x19Du )
    {
      switch ( a1 )
      {
        case 0x19Eu:
          return "Request-URI Too Long";
        case 0x19Fu:
          return "Unsupported Media Type";
        case 0x1A0u:
          return "Requested Range Not Satisfiable";
        case 0x1A1u:
          return "Expectation Failed";
        case 0x1A6u:
          return "Unprocessable Entity";
        case 0x1A7u:
          return "Locked";
        case 0x1A8u:
          return "Failed Dependency";
      }
    }
    else
    {
      switch ( a1 )
      {
        case 0x19Du:
          return "Request Entity Too Large";
        case 0x196u:
          return "Not Acceptable";
        case 0x197u:
          return "Proxy Authentication Required";
        case 0x198u:
          return "Request Timeout";
        case 0x199u:
          return "Conflict";
        case 0x19Au:
          return "Gone";
        case 0x19Bu:
          return "Length Required";
        case 0x19Cu:
          return "Precondition Failed";
      }
    }
    return "Unknown";
  }
  switch ( a1 )
  {
    case 0x1F5u:
      return "Not Implemented";
    case 0x1F6u:
      return "Bad Gateway";
    case 0x1F7u:
      return "Service Unavailable";
    case 0x1F8u:
      return "Gateway Timeout";
    case 0x1F9u:
      return "HTTP Version Not Supported";
  }
  if ( a1 != 507 )
    return "Unknown";
  return "Insufficient Storage";
}

```

## disassembly

```asm
0x18001a648  movzx   edx, cx
0x18001a64b  mov     eax, 195h
0x18001a650  cmp     edx, eax
0x18001a652  ja      loc_18001A7C4
0x18001a658  jz      loc_18001A7BC
0x18001a65e  mov     eax, 12Dh
0x18001a663  cmp     edx, eax
0x18001a665  ja      loc_18001A719
0x18001a66b  jz      loc_18001A711
0x18001a671  mov     eax, 0CBh
0x18001a676  cmp     edx, eax
0x18001a678  ja      short loc_18001A6C9
0x18001a67a  jz      short loc_18001A6C1
0x18001a67c  sub     edx, 64h ; 'd'
0x18001a67f  jz      short loc_18001A6B9
0x18001a681  sub     edx, 1
0x18001a684  jz      short loc_18001A6B1
0x18001a686  sub     edx, 63h ; 'c'
0x18001a689  jz      short loc_18001A6A9
0x18001a68b  sub     edx, 1
0x18001a68e  jz      short loc_18001A6A1
0x18001a690  cmp     edx, 1
0x18001a693  jnz     loc_18001A8D3
0x18001a699  lea     rax, aAccepted; "Accepted"
0x18001a6a0  retn
0x18001a6a1  lea     rax, aCreated; "Created"
0x18001a6a8  retn
0x18001a6a9  lea     rax, aOk; "OK"
0x18001a6b0  retn
0x18001a6b1  lea     rax, aSwitchingProto; "Switching Protocols"
0x18001a6b8  retn
0x18001a6b9  lea     rax, aContinue; "Continue"
0x18001a6c0  retn
0x18001a6c1  lea     rax, aNonAuthoritati; "Non-Authoritative Information"
0x18001a6c8  retn
0x18001a6c9  sub     edx, 0CCh
0x18001a6cf  jz      short loc_18001A709
0x18001a6d1  sub     edx, 1
0x18001a6d4  jz      short loc_18001A701
0x18001a6d6  sub     edx, 1
0x18001a6d9  jz      short loc_18001A6F9
0x18001a6db  sub     edx, 1
0x18001a6de  jz      short loc_18001A6F1
0x18001a6e0  cmp     edx, 5Dh ; ']'
0x18001a6e3  jnz     loc_18001A8D3
0x18001a6e9  lea     rax, aMultipleChoice; "Multiple Choices"
0x18001a6f0  retn
0x18001a6f1  lea     rax, aMultiStatus; "Multi-Status"
0x18001a6f8  retn
0x18001a6f9  lea     rax, aPartialContent; "Partial Content"
0x18001a700  retn
0x18001a701  lea     rax, aResetContent; "Reset Content"
0x18001a708  retn
0x18001a709  lea     rax, aNoContent; "No Content"
0x18001a710  retn
0x18001a711  lea     rax, aMovedPermanent; "Moved Permanently"
0x18001a718  retn
0x18001a719  mov     eax, 134h
0x18001a71e  cmp     edx, eax
0x18001a720  ja      short loc_18001A774
0x18001a722  jz      short loc_18001A76C
0x18001a724  sub     edx, 12Eh
0x18001a72a  jz      short loc_18001A764
0x18001a72c  sub     edx, 1
0x18001a72f  jz      short loc_18001A75C
0x18001a731  sub     edx, 1
0x18001a734  jz      short loc_18001A754
0x18001a736  sub     edx, 1
0x18001a739  jz      short loc_18001A74C
0x18001a73b  cmp     edx, 2
0x18001a73e  jnz     loc_18001A8D3
0x18001a744  lea     rax, aTemporaryRedir; "Temporary Redirect"
0x18001a74b  retn
0x18001a74c  lea     rax, aUseProxy; "Use Proxy"
0x18001a753  retn
0x18001a754  lea     rax, aNotModified; "Not Modified"
0x18001a75b  retn
0x18001a75c  lea     rax, aSeeOther; "See Other"
0x18001a763  retn
0x18001a764  lea     rax, aFound; "Found"
0x18001a76b  retn
0x18001a76c  lea     rax, aPermanentRedir; "Permanent Redirect"
0x18001a773  retn
0x18001a774  sub     edx, 190h
0x18001a77a  jz      short loc_18001A7B4
0x18001a77c  sub     edx, 1
0x18001a77f  jz      short loc_18001A7AC
0x18001a781  sub     edx, 1
0x18001a784  jz      short loc_18001A7A4
0x18001a786  sub     edx, 1
0x18001a789  jz      short loc_18001A79C
0x18001a78b  cmp     edx, 1
0x18001a78e  jnz     loc_18001A8D3
0x18001a794  lea     rax, aNotFound; "Not Found"
0x18001a79b  retn
0x18001a79c  lea     rax, aForbidden; "Forbidden"
0x18001a7a3  retn
0x18001a7a4  lea     rax, aPaymentRequire; "Payment Required"
0x18001a7ab  retn
0x18001a7ac  lea     rax, aUnauthorized; "Unauthorized"
0x18001a7b3  retn
0x18001a7b4  lea     rax, aBadRequest; "Bad Request"
0x18001a7bb  retn
0x18001a7bc  lea     rax, aMethodNotAllow; "Method Not Allowed"
0x18001a7c3  retn
0x18001a7c4  mov     eax, 1F4h
0x18001a7c9  cmp     edx, eax
0x18001a7cb  ja      loc_18001A8B2
0x18001a7d1  jz      loc_18001A8AA
0x18001a7d7  mov     eax, 19Dh
0x18001a7dc  cmp     edx, eax
0x18001a7de  ja      short loc_18001A84C
0x18001a7e0  jz      short loc_18001A844
0x18001a7e2  sub     edx, 196h
0x18001a7e8  jz      short loc_18001A83C
0x18001a7ea  sub     edx, 1
0x18001a7ed  jz      short loc_18001A834
0x18001a7ef  sub     edx, 1
0x18001a7f2  jz      short loc_18001A82C
0x18001a7f4  sub     edx, 1
0x18001a7f7  jz      short loc_18001A824
0x18001a7f9  sub     edx, 1
0x18001a7fc  jz      short loc_18001A81C
0x18001a7fe  sub     edx, 1
0x18001a801  jz      short loc_18001A814
0x18001a803  cmp     edx, 1
0x18001a806  jnz     loc_18001A8D3
0x18001a80c  lea     rax, aPreconditionFa; "Precondition Failed"
0x18001a813  retn
0x18001a814  lea     rax, aLengthRequired; "Length Required"
0x18001a81b  retn
0x18001a81c  lea     rax, aGone; "Gone"
0x18001a823  retn
0x18001a824  lea     rax, aConflict; "Conflict"
0x18001a82b  retn
0x18001a82c  lea     rax, aRequestTimeout; "Request Timeout"
0x18001a833  retn
0x18001a834  lea     rax, aProxyAuthentic; "Proxy Authentication Required"
0x18001a83b  retn
0x18001a83c  lea     rax, aNotAcceptable; "Not Acceptable"
0x18001a843  retn
0x18001a844  lea     rax, aRequestEntityT; "Request Entity Too Large"
0x18001a84b  retn
0x18001a84c  sub     edx, 19Eh
0x18001a852  jz      short loc_18001A8A2
0x18001a854  sub     edx, 1
0x18001a857  jz      short loc_18001A89A
0x18001a859  sub     edx, 1
0x18001a85c  jz      short loc_18001A892
0x18001a85e  sub     edx, 1
0x18001a861  jz      short loc_18001A88A
0x18001a863  sub     edx, 5
0x18001a866  jz      short loc_18001A882
0x18001a868  sub     edx, 1
0x18001a86b  jz      short loc_18001A87A
0x18001a86d  cmp     edx, 1
0x18001a870  jnz     short loc_18001A8D3
0x18001a872  lea     rax, aFailedDependen; "Failed Dependency"
0x18001a879  retn
0x18001a87a  lea     rax, aLocked; "Locked"
0x18001a881  retn
0x18001a882  lea     rax, aUnprocessableE; "Unprocessable Entity"
0x18001a889  retn
0x18001a88a  lea     rax, aExpectationFai; "Expectation Failed"
0x18001a891  retn
0x18001a892  lea     rax, aRequestedRange; "Requested Range Not Satisfiable"
0x18001a899  retn
0x18001a89a  lea     rax, aUnsupportedMed; "Unsupported Media Type"
0x18001a8a1  retn
0x18001a8a2  lea     rax, aRequestUriTooL; "Request-URI Too Long"
0x18001a8a9  retn
0x18001a8aa  lea     rax, aInternalServer; "Internal Server Error"
0x18001a8b1  retn
0x18001a8b2  sub     edx, 1F5h
0x18001a8b8  jz      short loc_18001A903
0x18001a8ba  sub     edx, 1
0x18001a8bd  jz      short loc_18001A8FB
0x18001a8bf  sub     edx, 1
0x18001a8c2  jz      short loc_18001A8F3
0x18001a8c4  sub     edx, 1
0x18001a8c7  jz      short loc_18001A8EB
0x18001a8c9  sub     edx, 1
0x18001a8cc  jz      short loc_18001A8E3
0x18001a8ce  cmp     edx, 2
0x18001a8d1  jz      short loc_18001A8DB
0x18001a8d3  lea     rax, aUnknown; "Unknown"
0x18001a8da  retn
0x18001a8db  lea     rax, aInsufficientSt; "Insufficient Storage"
0x18001a8e2  retn
0x18001a8e3  lea     rax, aHttpVersionNot; "HTTP Version Not Supported"
0x18001a8ea  retn
0x18001a8eb  lea     rax, aGatewayTimeout; "Gateway Timeout"
0x18001a8f2  retn
0x18001a8f3  lea     rax, aServiceUnavail; "Service Unavailable"
0x18001a8fa  retn
0x18001a8fb  lea     rax, aBadGateway; "Bad Gateway"
0x18001a902  retn
0x18001a903  lea     rax, aNotImplemented; "Not Implemented"
0x18001a90a  retn
```
