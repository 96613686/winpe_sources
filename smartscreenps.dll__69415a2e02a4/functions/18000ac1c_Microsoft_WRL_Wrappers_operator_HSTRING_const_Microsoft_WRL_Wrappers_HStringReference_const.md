# Microsoft::WRL::Wrappers::operator==(HSTRING__ * const &,Microsoft::WRL::Wrappers::HStringReference const &)

- ea: `0x18000ac1c`
- end: `0x18000ac87`
- name: `??8Wrappers@WRL@Microsoft@@YA_NAEBQEAUHSTRING__@@AEBVHStringReference@012@@Z`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000ac90`

## callees

- `0x180001590`
- `0x18000ac1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ac7a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ac7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000ac43`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18000ac43`

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
    __debugbreak();
    JUMPOUT(0x18000AC87LL);
  }
  return result == 0;
}

```

## disassembly

```asm
0x18000ac1c  sub     rsp, 38h
0x18000ac20  mov     rax, cs:__security_cookie
0x18000ac27  xor     rax, rsp
0x18000ac2a  mov     [rsp+38h+var_10], rax
0x18000ac2f  mov     rdx, [rdx+18h]; string2
0x18000ac33  lea     r8, [rsp+38h+result]; result
0x18000ac38  mov     rcx, [rcx]; string1
0x18000ac3b  mov     [rsp+38h+result], 0
0x18000ac43  call    cs:__imp_WindowsCompareStringOrdinal
0x18000ac4a  nop     dword ptr [rax+rax+00h]
0x18000ac4f  test    eax, eax
0x18000ac51  js      short loc_18000AC6E
0x18000ac53  cmp     [rsp+38h+result], 0
0x18000ac58  setz    al
0x18000ac5b  mov     rcx, [rsp+38h+var_10]
0x18000ac60  xor     rcx, rsp; StackCookie
0x18000ac63  call    __security_check_cookie
0x18000ac68  add     rsp, 38h
0x18000ac6c  retn
0x18000ac6e  xor     r9d, r9d; lpArguments
0x18000ac71  xor     r8d, r8d; nNumberOfArguments
0x18000ac74  mov     ecx, eax; dwExceptionCode
0x18000ac76  lea     edx, [r9+1]; dwExceptionFlags
0x18000ac7a  call    cs:__imp_RaiseException
0x18000ac81  nop     dword ptr [rax+rax+00h]
0x18000ac86  int     3; Trap to Debugger
```
