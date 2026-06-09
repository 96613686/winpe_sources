# Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)

- ea: `0x18000a99c`
- end: `0x18000a9fa`
- name: `??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z`
- size: `94`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000aa00`

## callees

- `0x180001590`
- `0x18000a99c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a9f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000a9f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000a9c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000a9c3`

## pseudocode

```c
bool __fastcall Microsoft::WRL::Wrappers::operator==(HSTRING *a1, __int64 a2)
{
  HSTRING v2; // rdx
  HSTRING v3; // rcx
  HRESULT v4; // eax
  INT32 result; // [rsp+20h] [rbp-18h] BYREF

  v2 = *(HSTRING *)(a2 + 24);
  v3 = *a1;
  result = 0;
  v4 = WindowsCompareStringOrdinal(v3, v2, &result);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    JUMPOUT(0x18000A9F9LL);
  }
  return result == 0;
}

```

## disassembly

```asm
0x18000a99c  sub     rsp, 38h
0x18000a9a0  mov     rax, cs:__security_cookie
0x18000a9a7  xor     rax, rsp
0x18000a9aa  mov     [rsp+38h+var_10], rax
0x18000a9af  mov     rdx, [rdx+18h]; string2
0x18000a9b3  lea     r8, [rsp+38h+result]; result
0x18000a9b8  mov     rcx, [rcx]; string1
0x18000a9bb  mov     [rsp+38h+result], 0
0x18000a9c3  call    cs:__imp_WindowsCompareStringOrdinal
0x18000a9c9  test    eax, eax
0x18000a9cb  js      short loc_18000A9E7
0x18000a9cd  cmp     [rsp+38h+result], 0
0x18000a9d2  setz    al
0x18000a9d5  mov     rcx, [rsp+38h+var_10]
0x18000a9da  xor     rcx, rsp; StackCookie
0x18000a9dd  call    __security_check_cookie
0x18000a9e2  add     rsp, 38h
0x18000a9e6  retn
0x18000a9e7  xor     r9d, r9d; lpArguments
0x18000a9ea  xor     r8d, r8d; nNumberOfArguments
0x18000a9ed  mov     ecx, eax; dwExceptionCode
0x18000a9ef  lea     edx, [r9+1]; dwExceptionFlags
0x18000a9f3  call    cs:__imp_RaiseException
```
