# CActivatableClassData::GetIdentifierStringForLogging(HSTRING__ * *)

- ea: `0x18006b430`
- end: `0x18006b571`
- name: `?GetIdentifierStringForLogging@CActivatableClassData@@UEAAXPEAPEAUHSTRING__@@@Z`
- size: `321`
- prototype: `void(CActivatableClassData *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18006b430`
- `0x1800b27e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b56a`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18006b56a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006b4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006b4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006b4c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18006b4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18006b489`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b4a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b53a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b4a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b4d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b510`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b522`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b532`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006b53a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006b4fe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18006b4fe`

## pseudocode

```c
void __fastcall CActivatableClassData::GetIdentifierStringForLogging(CActivatableClassData *this, HSTRING *a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rcx
  HSTRING v6; // rdx
  HSTRING v7; // [rsp+20h] [rbp-40h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF

  *a2 = 0;
  newString = 0;
  v7 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"!", 1u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    JUMPOUT(0x18006B570LL);
  }
  if ( !*((_QWORD *)this + 25)
    || (WindowsDeleteString(newString),
        v5 = (HSTRING)*((_QWORD *)this + 25),
        newString = 0,
        WindowsConcatString(v5, string, &newString) >= 0) )
  {
    WindowsDeleteString(v7);
    v6 = (HSTRING)*((_QWORD *)this + 24);
    v7 = 0;
    if ( WindowsConcatString(newString, v6, &v7) >= 0 )
      WindowsDuplicateString(v7, a2);
  }
  string = 0;
  WindowsDeleteString(v7);
  v7 = 0;
  WindowsDeleteString(newString);
  newString = 0;
  WindowsDeleteString(0);
  WindowsDeleteString(0);
}

```

## disassembly

```asm
0x18006b430  mov     [rsp-8+arg_10], rbx
0x18006b435  mov     [rsp-8+arg_18], rdi
0x18006b43a  push    rbp
0x18006b43b  mov     rbp, rsp
0x18006b43e  sub     rsp, 60h
0x18006b442  mov     rax, cs:__security_cookie
0x18006b449  xor     rax, rsp
0x18006b44c  mov     [rbp+var_10], rax
0x18006b450  mov     rdi, rdx
0x18006b453  mov     qword ptr [rdx], 0
0x18006b45a  mov     rbx, rcx
0x18006b45d  mov     [rbp+newString], 0
0x18006b465  mov     edx, 1; length
0x18006b46a  mov     [rbp+var_40], 0
0x18006b472  lea     rcx, sourceString; "!"
0x18006b479  mov     [rbp+string], 0
0x18006b481  lea     r9, [rbp+string]; string
0x18006b485  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18006b489  call    cs:__imp_WindowsCreateStringReference
0x18006b48f  test    eax, eax
0x18006b491  js      loc_18006B55E
0x18006b497  cmp     qword ptr [rbx+0C8h], 0
0x18006b49f  jz      short loc_18006B4CC
0x18006b4a1  mov     rcx, [rbp+newString]; string
0x18006b4a5  call    cs:__imp_WindowsDeleteString
0x18006b4ab  mov     rdx, [rbp+string]; string2
0x18006b4af  lea     r8, [rbp+newString]; newString
0x18006b4b3  mov     rcx, [rbx+0C8h]; string1
0x18006b4ba  mov     [rbp+newString], 0
0x18006b4c2  call    cs:__imp_WindowsConcatString
0x18006b4c8  test    eax, eax
0x18006b4ca  js      short loc_18006B504
0x18006b4cc  mov     rcx, [rbp+var_40]; string
0x18006b4d0  call    cs:__imp_WindowsDeleteString
0x18006b4d6  mov     rdx, [rbx+0C0h]; string2
0x18006b4dd  lea     r8, [rbp+var_40]; newString
0x18006b4e1  mov     rcx, [rbp+newString]; string1
0x18006b4e5  mov     [rbp+var_40], 0
0x18006b4ed  call    cs:__imp_WindowsConcatString
0x18006b4f3  test    eax, eax
0x18006b4f5  js      short loc_18006B504
0x18006b4f7  mov     rcx, [rbp+var_40]; string
0x18006b4fb  mov     rdx, rdi; newString
0x18006b4fe  call    cs:__imp_WindowsDuplicateString
0x18006b504  mov     rcx, [rbp+var_40]; string
0x18006b508  mov     [rbp+string], 0
0x18006b510  call    cs:__imp_WindowsDeleteString
0x18006b516  mov     rcx, [rbp+newString]; string
0x18006b51a  mov     [rbp+var_40], 0
0x18006b522  call    cs:__imp_WindowsDeleteString
0x18006b528  xor     ecx, ecx; string
0x18006b52a  mov     [rbp+newString], 0
0x18006b532  call    cs:__imp_WindowsDeleteString
0x18006b538  xor     ecx, ecx; string
0x18006b53a  call    cs:__imp_WindowsDeleteString
0x18006b540  mov     rcx, [rbp+var_10]
0x18006b544  xor     rcx, rsp; StackCookie
0x18006b547  call    __security_check_cookie
0x18006b54c  lea     r11, [rsp+60h+var_s0]
0x18006b551  mov     rbx, [r11+20h]
0x18006b555  mov     rdi, [r11+28h]
0x18006b559  mov     rsp, r11
0x18006b55c  pop     rbp
0x18006b55d  retn
0x18006b55e  xor     r9d, r9d; lpArguments
0x18006b561  xor     r8d, r8d; nNumberOfArguments
0x18006b564  mov     ecx, eax; dwExceptionCode
0x18006b566  lea     edx, [r9+1]; dwExceptionFlags
0x18006b56a  call    cs:__imp_RaiseException
```
