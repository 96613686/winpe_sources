# CWinRTServerTableEntry::GetIdentifierStringForLogging(HSTRING__ * *)

- ea: `0x180058c10`
- end: `0x180058ef1`
- name: `?GetIdentifierStringForLogging@CWinRTServerTableEntry@@EEAAXPEAPEAUHSTRING__@@@Z`
- size: `737`
- prototype: `void(CWinRTServerTableEntry *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180058c10`
- `0x180091a10`
- `0x1800b7ac0`
- `0x1800b8428`
- `0x1800d67e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058d02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058d39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058dbf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180058ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058c6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180058d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058dd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058cb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058ce5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058d76`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058dd9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058e45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180058eb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058ca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058df1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058ca0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058cce`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180058df1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058ea2`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180058ea2`

## pseudocode

```c
void __fastcall CWinRTServerTableEntry::GetIdentifierStringForLogging(CWinRTServerTableEntry *this, HSTRING *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  HSTRING v7; // rcx
  HSTRING v8; // rcx
  const GUID *v9; // rdi
  __int64 v10; // rax
  HRESULT v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  HRESULT v14; // ebx
  __int64 v15; // rax
  HSTRING v16; // [rsp+20h] [rbp-89h] BYREF
  HSTRING string1; // [rsp+28h] [rbp-81h] BYREF
  HSTRING v18; // [rsp+30h] [rbp-79h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v20; // [rsp+40h] [rbp-69h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-61h] BYREF
  HSTRING string; // [rsp+60h] [rbp-49h] BYREF
  HSTRING_HEADER v23; // [rsp+68h] [rbp-41h] BYREF
  HSTRING string2; // [rsp+80h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-19h] BYREF

  *a2 = 0;
  newString = 0;
  string1 = 0;
  v18 = 0;
  v16 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"!", 1u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    __debugbreak();
  }
  WindowsDeleteString(newString);
  v7 = (HSTRING)*((_QWORD *)this + 24);
  newString = 0;
  WindowsDuplicateString(v7, &newString);
  WindowsDeleteString(string1);
  v8 = (HSTRING)*((_QWORD *)this + 25);
  string1 = 0;
  WindowsDuplicateString(v8, &string1);
  if ( !string1 || (WindowsDeleteString(v18), v18 = 0, WindowsConcatString(string1, string, &v18) >= 0) )
  {
    WindowsDeleteString(v16);
    v16 = 0;
    if ( WindowsConcatString(v18, newString, &v16) >= 0 )
    {
      v9 = (const GUID *)((char *)this + 216);
      v10 = *((_QWORD *)this + 27) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v10 )
        v10 = *((_QWORD *)this + 28) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v10 )
        goto LABEL_12;
      v20 = 0;
      WindowsDeleteString(0);
      v20 = 0;
      string2 = 0;
      v11 = WindowsCreateStringReference(L"#", 1u, &v23, &string2);
      if ( v11 < 0 )
      {
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
        __debugbreak();
      }
      v14 = WindowsConcatString(v16, string2, &v20);
      if ( v14 >= 0 )
      {
        memset_0(sz, 0, 0x4Eu);
        StringFromGUID2(v9, sz, 39);
        WindowsDeleteString(v16);
        v16 = 0;
        v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v23, sz);
        v14 = WindowsConcatString(v20, *(HSTRING *)(v15 + 24), &v16);
      }
      WindowsDeleteString(v20);
      if ( v14 >= 0 )
LABEL_12:
        WindowsDuplicateString(v16, a2);
    }
  }
  string = 0;
  WindowsDeleteString(v16);
  v16 = 0;
  WindowsDeleteString(v18);
  v18 = 0;
  WindowsDeleteString(string1);
  string1 = 0;
  WindowsDeleteString(newString);
}

```

## disassembly

```asm
0x180058c10  mov     [rsp-8+arg_10], rbx
0x180058c15  mov     [rsp-8+arg_18], rsi
0x180058c1a  push    rbp
0x180058c1b  push    rdi
0x180058c1c  push    r14
0x180058c1e  lea     rbp, [rsp-47h]
0x180058c23  sub     rsp, 0F0h
0x180058c2a  mov     rax, cs:__security_cookie
0x180058c31  xor     rax, rsp
0x180058c34  mov     [rbp+57h+var_20], rax
0x180058c38  xor     r14d, r14d
0x180058c3b  lea     r9, [rbp+57h+string]; string
0x180058c3f  mov     rsi, rdx
0x180058c42  mov     [rdx], r14
0x180058c45  mov     rbx, rcx
0x180058c48  mov     [rbp+57h+newString], r14
0x180058c4c  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180058c50  mov     [rsp+100h+string1], r14
0x180058c55  lea     edx, [r14+1]; length
0x180058c59  mov     [rbp+57h+var_D0], r14
0x180058c5d  lea     rcx, sourceString; "!"
0x180058c64  mov     [rsp+100h+var_E0], r14
0x180058c69  mov     [rbp+57h+string], r14
0x180058c6d  call    cs:__imp_WindowsCreateStringReference
0x180058c74  nop     dword ptr [rax+rax+00h]
0x180058c79  test    eax, eax
0x180058c7b  js      loc_180058E76
0x180058c81  mov     rcx, [rbp+57h+newString]; string
0x180058c85  call    cs:__imp_WindowsDeleteString
0x180058c8c  nop     dword ptr [rax+rax+00h]
0x180058c91  mov     rcx, [rbx+0C0h]; string
0x180058c98  lea     rdx, [rbp+57h+newString]; newString
0x180058c9c  mov     [rbp+57h+newString], r14
0x180058ca0  call    cs:__imp_WindowsDuplicateString
0x180058ca7  nop     dword ptr [rax+rax+00h]
0x180058cac  mov     rcx, [rsp+100h+string1]; string
0x180058cb1  call    cs:__imp_WindowsDeleteString
0x180058cb8  nop     dword ptr [rax+rax+00h]
0x180058cbd  mov     rcx, [rbx+0C8h]; string
0x180058cc4  lea     rdx, [rsp+100h+string1]; newString
0x180058cc9  mov     [rsp+100h+string1], r14
0x180058cce  call    cs:__imp_WindowsDuplicateString
0x180058cd5  nop     dword ptr [rax+rax+00h]
0x180058cda  cmp     [rsp+100h+string1], r14
0x180058cdf  jz      short loc_180058D16
0x180058ce1  mov     rcx, [rbp+57h+var_D0]; string
0x180058ce5  call    cs:__imp_WindowsDeleteString
0x180058cec  nop     dword ptr [rax+rax+00h]
0x180058cf1  mov     rdx, [rbp+57h+string]; string2
0x180058cf5  lea     r8, [rbp+57h+var_D0]; newString
0x180058cf9  mov     rcx, [rsp+100h+string1]; string1
0x180058cfe  mov     [rbp+57h+var_D0], r14
0x180058d02  call    cs:__imp_WindowsConcatString
0x180058d09  nop     dword ptr [rax+rax+00h]
0x180058d0e  test    eax, eax
0x180058d10  js      loc_180058DFD
0x180058d16  mov     rcx, [rsp+100h+var_E0]; string
0x180058d1b  call    cs:__imp_WindowsDeleteString
0x180058d22  nop     dword ptr [rax+rax+00h]
0x180058d27  mov     rdx, [rbp+57h+newString]; string2
0x180058d2b  lea     r8, [rsp+100h+var_E0]; newString
0x180058d30  mov     rcx, [rbp+57h+var_D0]; string1
0x180058d34  mov     [rsp+100h+var_E0], r14
0x180058d39  call    cs:__imp_WindowsConcatString
0x180058d40  nop     dword ptr [rax+rax+00h]
0x180058d45  test    eax, eax
0x180058d47  js      loc_180058DFD
0x180058d4d  lea     rdi, [rbx+0D8h]
0x180058d54  mov     rax, [rdi]
0x180058d57  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180058d5e  jnz     short loc_180058D6B
0x180058d60  mov     rax, [rdi+8]
0x180058d64  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180058d6b  test    rax, rax
0x180058d6e  jz      short loc_180058DE9
0x180058d70  xor     ecx, ecx; string
0x180058d72  mov     [rbp+57h+var_C0], r14
0x180058d76  call    cs:__imp_WindowsDeleteString
0x180058d7d  nop     dword ptr [rax+rax+00h]
0x180058d82  lea     r9, [rbp+57h+string2]; string
0x180058d86  mov     [rbp+57h+var_C0], r14
0x180058d8a  lea     r8, [rbp+57h+var_98]; hstringHeader
0x180058d8e  mov     [rbp+57h+string2], r14
0x180058d92  mov     edx, 1; length
0x180058d97  lea     rcx, asc_180123890; "#"
0x180058d9e  call    cs:__imp_WindowsCreateStringReference
0x180058da5  nop     dword ptr [rax+rax+00h]
0x180058daa  test    eax, eax
0x180058dac  js      loc_180058E7E
0x180058db2  mov     rdx, [rbp+57h+string2]; string2
0x180058db6  lea     r8, [rbp+57h+var_C0]; newString
0x180058dba  mov     rcx, [rsp+100h+var_E0]; string1
0x180058dbf  call    cs:__imp_WindowsConcatString
0x180058dc6  nop     dword ptr [rax+rax+00h]
0x180058dcb  mov     ebx, eax
0x180058dcd  test    eax, eax
0x180058dcf  jns     loc_180058E86
0x180058dd5  mov     rcx, [rbp+57h+var_C0]; string
0x180058dd9  call    cs:__imp_WindowsDeleteString
0x180058de0  nop     dword ptr [rax+rax+00h]
0x180058de5  test    ebx, ebx
0x180058de7  js      short loc_180058DFD
0x180058de9  mov     rcx, [rsp+100h+var_E0]; string
0x180058dee  mov     rdx, rsi; newString
0x180058df1  call    cs:__imp_WindowsDuplicateString
0x180058df8  nop     dword ptr [rax+rax+00h]
0x180058dfd  mov     rcx, [rsp+100h+var_E0]; string
0x180058e02  mov     [rbp+57h+string], r14
0x180058e06  call    cs:__imp_WindowsDeleteString
0x180058e0d  nop     dword ptr [rax+rax+00h]
0x180058e12  mov     rcx, [rbp+57h+var_D0]; string
0x180058e16  mov     [rsp+100h+var_E0], r14
0x180058e1b  call    cs:__imp_WindowsDeleteString
0x180058e22  nop     dword ptr [rax+rax+00h]
0x180058e27  mov     rcx, [rsp+100h+string1]; string
0x180058e2c  mov     [rbp+57h+var_D0], r14
0x180058e30  call    cs:__imp_WindowsDeleteString
0x180058e37  nop     dword ptr [rax+rax+00h]
0x180058e3c  mov     rcx, [rbp+57h+newString]; string
0x180058e40  mov     [rsp+100h+string1], r14
0x180058e45  call    cs:__imp_WindowsDeleteString
0x180058e4c  nop     dword ptr [rax+rax+00h]
0x180058e51  mov     rcx, [rbp+57h+var_20]
0x180058e55  xor     rcx, rsp; StackCookie
0x180058e58  call    __security_check_cookie
0x180058e5d  lea     r11, [rsp+100h+var_10]
0x180058e65  mov     rbx, [r11+30h]
0x180058e69  mov     rsi, [r11+38h]
0x180058e6d  mov     rsp, r11
0x180058e70  pop     r14
0x180058e72  pop     rdi
0x180058e73  pop     rbp
0x180058e74  retn
0x180058e76  mov     ecx, eax; this
0x180058e78  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180058e7d  int     3; Trap to Debugger
0x180058e7e  mov     ecx, eax; this
0x180058e80  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180058e85  int     3; Trap to Debugger
0x180058e86  xor     edx, edx; Val
0x180058e88  lea     rcx, [rbp+57h+sz]; void *
0x180058e8c  lea     r8d, [rdx+4Eh]; Size
0x180058e90  call    memset_0
0x180058e95  mov     r8d, 27h ; '''; cchMax
0x180058e9b  lea     rdx, [rbp+57h+sz]; lpsz
0x180058e9f  mov     rcx, rdi; rguid
0x180058ea2  call    cs:__imp_StringFromGUID2
0x180058ea9  nop     dword ptr [rax+rax+00h]
0x180058eae  mov     rcx, [rsp+100h+var_E0]; string
0x180058eb3  call    cs:__imp_WindowsDeleteString
0x180058eba  nop     dword ptr [rax+rax+00h]
0x180058ebf  lea     rdx, [rbp+57h+sz]; sourceString
0x180058ec3  mov     [rsp+100h+var_E0], r14
0x180058ec8  lea     rcx, [rbp+57h+var_98]; hstringHeader
0x180058ecc  call    ??$?0$0CH@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CH@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[39])
0x180058ed1  mov     rcx, [rbp+57h+var_C0]; string1
0x180058ed5  lea     r8, [rsp+100h+var_E0]; newString
0x180058eda  mov     rdx, [rax+18h]; string2
0x180058ede  call    cs:__imp_WindowsConcatString
0x180058ee5  nop     dword ptr [rax+rax+00h]
0x180058eea  mov     ebx, eax
0x180058eec  jmp     loc_180058DD5
```
