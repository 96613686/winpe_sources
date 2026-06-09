# ConvertStringEnumerableStateToEnumerableState(Windows::Internal::String const &,Windows::Internal::Security::Credentials::WebAccountEnumerableState &)

- ea: `0x180043124`
- end: `0x180043367`
- name: `?ConvertStringEnumerableStateToEnumerableState@@YAJAEBVString@Internal@Windows@@AEAW4WebAccountEnumerableState@Credentials@Security@23@@Z`
- size: `579`
- prototype: `__int64 __fastcall(const struct Windows::Internal::String *, enum Windows::Internal::Security::Credentials::WebAccountEnumerableState *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a790`

## callees

- `0x180043124`
- `0x180043370`
- `0x18008e690`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004333e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043352`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432c0`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432d7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800432ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004333e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180043352`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800431c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004330d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043171`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800431c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043205`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180043245`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004330d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004319d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800431e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180043225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180043265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18004319d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x1800431e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180043225`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x180043265`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043151`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x180043151`

## pseudocode

```c
__int64 __fastcall ConvertStringEnumerableStateToEnumerableState(
        HSTRING *a1,
        enum Windows::Internal::Security::Credentials::WebAccountEnumerableState *a2)
{
  HSTRING v4; // rdx
  HSTRING v5; // rdx
  HSTRING v6; // rdx
  HSTRING v7; // rdx
  INT32 result; // [rsp+20h] [rbp-30h] BYREF
  HSTRING string; // [rsp+28h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-20h] BYREF

  if ( !WindowsIsStringEmpty(*a1) )
  {
    if ( WindowsCreateStringReference(L"EnumerableState_NotDefined", 0x1Au, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v4 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v4, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 0;
      return 0;
    }
    if ( WindowsCreateStringReference(L"EnumerableState_Allowed", 0x17u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v5 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v5, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 1;
      return 0;
    }
    if ( WindowsCreateStringReference(L"EnumerableState_NotAllowed", 0x1Au, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v6, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 2;
      return 0;
    }
    if ( WindowsCreateStringReference(L"EnumerableState_AlwaysAllowed", 0x1Du, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v7 = *a1;
    result = 0;
    WindowsCompareStringOrdinal(string, v7, &result);
    if ( !result )
    {
      *(_DWORD *)a2 = 3;
      return 0;
    }
    if ( WindowsCreateStringReference(L"EnumerableState_AlwaysNotAllowed", 0x20u, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    if ( !(unsigned int)Windows::Internal::StringReference::CompareOrdinal(
                          (Windows::Internal::StringReference *)&string,
                          (const struct Windows::Internal::String *)a1) )
    {
      *(_DWORD *)a2 = 4;
      return 0;
    }
  }
  return 2147942413LL;
}

```

## disassembly

```asm
0x180043124  mov     [rsp-18h+arg_10], rbx
0x180043129  mov     [rsp-18h+arg_18], rdi
0x18004312e  push    rbp
0x18004312f  push    r14
0x180043131  push    r15
0x180043133  mov     rbp, rsp
0x180043136  sub     rsp, 50h
0x18004313a  mov     rax, cs:__security_cookie
0x180043141  xor     rax, rsp
0x180043144  mov     [rbp+var_8], rax
0x180043148  mov     rdi, rcx
0x18004314b  mov     rbx, rdx
0x18004314e  mov     rcx, [rcx]; string
0x180043151  call    cs:__imp_WindowsIsStringEmpty
0x180043157  test    eax, eax
0x180043159  jnz     loc_18004335D
0x18004315f  lea     r9, [rbp+string]; string
0x180043163  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180043167  lea     edx, [rax+1Ah]; length
0x18004316a  lea     rcx, aEnumerablestat_1; "EnumerableState_NotDefined"
0x180043171  call    cs:__imp_WindowsCreateStringReference
0x180043177  mov     r14d, 1
0x18004317d  mov     r15d, 0C000000Dh
0x180043183  test    eax, eax
0x180043185  js      loc_1800432B4
0x18004318b  mov     rdx, [rdi]; string2
0x18004318e  lea     r8, [rbp+result]; result
0x180043192  mov     rcx, [rbp+string]; string1
0x180043196  mov     [rbp+result], 0
0x18004319d  call    cs:__imp_WindowsCompareStringOrdinal
0x1800431a3  cmp     [rbp+result], 0
0x1800431a7  jz      loc_1800432AC
0x1800431ad  lea     r9, [rbp+string]; string
0x1800431b1  mov     edx, 17h; length
0x1800431b6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800431ba  lea     rcx, aEnumerablestat_0; "EnumerableState_Allowed"
0x1800431c1  call    cs:__imp_WindowsCreateStringReference
0x1800431c7  test    eax, eax
0x1800431c9  js      loc_1800432CB
0x1800431cf  mov     rdx, [rdi]; string2
0x1800431d2  lea     r8, [rbp+result]; result
0x1800431d6  mov     rcx, [rbp+string]; string1
0x1800431da  mov     [rbp+result], 0
0x1800431e1  call    cs:__imp_WindowsCompareStringOrdinal
0x1800431e7  cmp     [rbp+result], 0
0x1800431eb  jz      loc_18004327D
0x1800431f1  lea     r9, [rbp+string]; string
0x1800431f5  mov     edx, 1Ah; length
0x1800431fa  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800431fe  lea     rcx, aEnumerablestat_3; "EnumerableState_NotAllowed"
0x180043205  call    cs:__imp_WindowsCreateStringReference
0x18004320b  test    eax, eax
0x18004320d  js      loc_1800432E2
0x180043213  mov     rdx, [rdi]; string2
0x180043216  lea     r8, [rbp+result]; result
0x18004321a  mov     rcx, [rbp+string]; string1
0x18004321e  mov     [rbp+result], 0
0x180043225  call    cs:__imp_WindowsCompareStringOrdinal
0x18004322b  cmp     [rbp+result], 0
0x18004322f  jz      short loc_1800432A4
0x180043231  lea     r9, [rbp+string]; string
0x180043235  mov     edx, 1Dh; length
0x18004323a  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18004323e  lea     rcx, aEnumerablestat; "EnumerableState_AlwaysAllowed"
0x180043245  call    cs:__imp_WindowsCreateStringReference
0x18004324b  test    eax, eax
0x18004324d  js      loc_180043346
0x180043253  mov     rdx, [rdi]; string2
0x180043256  lea     r8, [rbp+result]; result
0x18004325a  mov     rcx, [rbp+string]; string1
0x18004325e  mov     [rbp+result], 0
0x180043265  call    cs:__imp_WindowsCompareStringOrdinal
0x18004326b  cmp     [rbp+result], 0
0x18004326f  jnz     loc_1800432F9
0x180043275  mov     dword ptr [rbx], 3
0x18004327b  jmp     short loc_180043280
0x18004327d  mov     [rbx], r14d
0x180043280  xor     eax, eax
0x180043282  mov     rcx, [rbp+var_8]
0x180043286  xor     rcx, rsp; StackCookie
0x180043289  call    __security_check_cookie
0x18004328e  lea     r11, [rsp+50h+var_s0]
0x180043293  mov     rbx, [r11+30h]
0x180043297  mov     rdi, [r11+38h]
0x18004329b  mov     rsp, r11
0x18004329e  pop     r15
0x1800432a0  pop     r14
0x1800432a2  pop     rbp
0x1800432a3  retn
0x1800432a4  mov     dword ptr [rbx], 2
0x1800432aa  jmp     short loc_180043280
0x1800432ac  mov     dword ptr [rbx], 0
0x1800432b2  jmp     short loc_180043280
0x1800432b4  xor     r9d, r9d; lpArguments
0x1800432b7  xor     r8d, r8d; nNumberOfArguments
0x1800432ba  mov     edx, r14d; dwExceptionFlags
0x1800432bd  mov     ecx, r15d; dwExceptionCode
0x1800432c0  call    cs:__imp_RaiseException
0x1800432c6  jmp     loc_18004318B
0x1800432cb  xor     r9d, r9d; lpArguments
0x1800432ce  xor     r8d, r8d; nNumberOfArguments
0x1800432d1  mov     edx, r14d; dwExceptionFlags
0x1800432d4  mov     ecx, r15d; dwExceptionCode
0x1800432d7  call    cs:__imp_RaiseException
0x1800432dd  jmp     loc_1800431CF
0x1800432e2  xor     r9d, r9d; lpArguments
0x1800432e5  xor     r8d, r8d; nNumberOfArguments
0x1800432e8  mov     edx, r14d; dwExceptionFlags
0x1800432eb  mov     ecx, r15d; dwExceptionCode
0x1800432ee  call    cs:__imp_RaiseException
0x1800432f4  jmp     loc_180043213
0x1800432f9  lea     r9, [rbp+string]; string
0x1800432fd  mov     edx, 20h ; ' '; length
0x180043302  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180043306  lea     rcx, aEnumerablestat_2; "EnumerableState_AlwaysNotAllowed"
0x18004330d  call    cs:__imp_WindowsCreateStringReference
0x180043313  test    eax, eax
0x180043315  js      short loc_180043332
0x180043317  mov     rdx, rdi; struct Windows::Internal::String *
0x18004331a  lea     rcx, [rbp+string]; this
0x18004331e  call    ?CompareOrdinal@StringReference@Internal@Windows@@QEBAHAEBVString@23@@Z; Windows::Internal::StringReference::CompareOrdinal(Windows::Internal::String const &)
0x180043323  test    eax, eax
0x180043325  jnz     short loc_18004335D
0x180043327  mov     dword ptr [rbx], 4
0x18004332d  jmp     loc_180043280
0x180043332  xor     r9d, r9d; lpArguments
0x180043335  xor     r8d, r8d; nNumberOfArguments
0x180043338  mov     edx, r14d; dwExceptionFlags
0x18004333b  mov     ecx, r15d; dwExceptionCode
0x18004333e  call    cs:__imp_RaiseException
0x180043344  jmp     short loc_180043317
0x180043346  xor     r9d, r9d; lpArguments
0x180043349  xor     r8d, r8d; nNumberOfArguments
0x18004334c  mov     edx, r14d; dwExceptionFlags
0x18004334f  mov     ecx, r15d; dwExceptionCode
0x180043352  call    cs:__imp_RaiseException
0x180043358  jmp     loc_180043253
0x18004335d  mov     eax, 8007000Dh
0x180043362  jmp     loc_180043282
```
