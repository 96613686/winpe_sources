# CWinRTServerTableEntry::GetIdentifierStringForLogging(HSTRING__ * *)

- ea: `0x180052bc0`
- end: `0x180052e38`
- name: `?GetIdentifierStringForLogging@CWinRTServerTableEntry@@EEAAXPEAPEAUHSTRING__@@@Z`
- size: `632`
- prototype: `void(CWinRTServerTableEntry *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180052bc0`
- `0x1800b27e0`
- `0x1800b3128`
- `0x1800cffd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052dc5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052dd8`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052dc5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180052dd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052e2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052c8e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052cb9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052d2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180052e2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052c1d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180052d12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052cf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052c77`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052ca1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052cf0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d41`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d62`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052d8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180052e06`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052d53`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052c66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180052d53`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052dfb`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180052dfb`

## pseudocode

```c
void __fastcall CWinRTServerTableEntry::GetIdentifierStringForLogging(CWinRTServerTableEntry *this, HSTRING *a2)
{
  HRESULT v4; // eax
  HSTRING v5; // rcx
  HSTRING v6; // rcx
  const GUID *v7; // rdi
  __int64 v8; // rax
  HRESULT v9; // eax
  HRESULT v10; // ebx
  __int64 v11; // rax
  HSTRING v12; // [rsp+20h] [rbp-89h] BYREF
  HSTRING string1; // [rsp+28h] [rbp-81h] BYREF
  HSTRING v14; // [rsp+30h] [rbp-79h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-71h] BYREF
  HSTRING v16; // [rsp+40h] [rbp-69h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-61h] BYREF
  HSTRING string; // [rsp+60h] [rbp-49h] BYREF
  HSTRING_HEADER v19; // [rsp+68h] [rbp-41h] BYREF
  HSTRING string2; // [rsp+80h] [rbp-29h] BYREF
  OLECHAR sz[40]; // [rsp+90h] [rbp-19h] BYREF

  *a2 = 0;
  newString = 0;
  string1 = 0;
  v14 = 0;
  v12 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"!", 1u, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    RaiseException(v4, 1u, 0, 0);
    __debugbreak();
  }
  WindowsDeleteString(newString);
  v5 = (HSTRING)*((_QWORD *)this + 24);
  newString = 0;
  WindowsDuplicateString(v5, &newString);
  WindowsDeleteString(string1);
  v6 = (HSTRING)*((_QWORD *)this + 25);
  string1 = 0;
  WindowsDuplicateString(v6, &string1);
  if ( !string1 || (WindowsDeleteString(v14), v14 = 0, WindowsConcatString(string1, string, &v14) >= 0) )
  {
    WindowsDeleteString(v12);
    v12 = 0;
    if ( WindowsConcatString(v14, newString, &v12) >= 0 )
    {
      v7 = (const GUID *)((char *)this + 216);
      v8 = *((_QWORD *)this + 27) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v8 )
        v8 = *((_QWORD *)this + 28) - *(_QWORD *)GUID_NULL.Data4;
      if ( !v8 )
        goto LABEL_12;
      v16 = 0;
      WindowsDeleteString(0);
      v16 = 0;
      string2 = 0;
      v9 = WindowsCreateStringReference(L"#", 1u, &v19, &string2);
      if ( v9 < 0 )
      {
        RaiseException(v9, 1u, 0, 0);
        __debugbreak();
      }
      v10 = WindowsConcatString(v12, string2, &v16);
      if ( v10 >= 0 )
      {
        memset_0(sz, 0, 0x4Eu);
        StringFromGUID2(v7, sz, 39);
        WindowsDeleteString(v12);
        v12 = 0;
        v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v19, sz);
        v10 = WindowsConcatString(v16, *(HSTRING *)(v11 + 24), &v12);
      }
      WindowsDeleteString(v16);
      if ( v10 >= 0 )
LABEL_12:
        WindowsDuplicateString(v12, a2);
    }
  }
  string = 0;
  WindowsDeleteString(v12);
  v12 = 0;
  WindowsDeleteString(v14);
  v14 = 0;
  WindowsDeleteString(string1);
  string1 = 0;
  WindowsDeleteString(newString);
}

```

## disassembly

```asm
0x180052bc0  mov     [rsp-8+arg_10], rbx
0x180052bc5  mov     [rsp-8+arg_18], rsi
0x180052bca  push    rbp
0x180052bcb  push    rdi
0x180052bcc  push    r14
0x180052bce  lea     rbp, [rsp-47h]
0x180052bd3  sub     rsp, 0F0h
0x180052bda  mov     rax, cs:__security_cookie
0x180052be1  xor     rax, rsp
0x180052be4  mov     [rbp+57h+var_20], rax
0x180052be8  xor     r14d, r14d
0x180052beb  lea     r9, [rbp+57h+string]; string
0x180052bef  mov     rsi, rdx
0x180052bf2  mov     [rdx], r14
0x180052bf5  mov     rbx, rcx
0x180052bf8  mov     [rbp+57h+newString], r14
0x180052bfc  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180052c00  mov     [rsp+100h+string1], r14
0x180052c05  lea     edx, [r14+1]; length
0x180052c09  mov     [rbp+57h+var_D0], r14
0x180052c0d  lea     rcx, sourceString; "!"
0x180052c14  mov     [rsp+100h+var_E0], r14
0x180052c19  mov     [rbp+57h+string], r14
0x180052c1d  call    cs:__imp_WindowsCreateStringReference
0x180052c23  test    eax, eax
0x180052c25  js      loc_180052DB9
0x180052c2b  mov     rcx, [rbp+57h+newString]; string
0x180052c2f  call    cs:__imp_WindowsDeleteString
0x180052c35  mov     rcx, [rbx+0C0h]; string
0x180052c3c  lea     rdx, [rbp+57h+newString]; newString
0x180052c40  mov     [rbp+57h+newString], r14
0x180052c44  call    cs:__imp_WindowsDuplicateString
0x180052c4a  mov     rcx, [rsp+100h+string1]; string
0x180052c4f  call    cs:__imp_WindowsDeleteString
0x180052c55  mov     rcx, [rbx+0C8h]; string
0x180052c5c  lea     rdx, [rsp+100h+string1]; newString
0x180052c61  mov     [rsp+100h+string1], r14
0x180052c66  call    cs:__imp_WindowsDuplicateString
0x180052c6c  cmp     [rsp+100h+string1], r14
0x180052c71  jz      short loc_180052C9C
0x180052c73  mov     rcx, [rbp+57h+var_D0]; string
0x180052c77  call    cs:__imp_WindowsDeleteString
0x180052c7d  mov     rdx, [rbp+57h+string]; string2
0x180052c81  lea     r8, [rbp+57h+var_D0]; newString
0x180052c85  mov     rcx, [rsp+100h+string1]; string1
0x180052c8a  mov     [rbp+57h+var_D0], r14
0x180052c8e  call    cs:__imp_WindowsConcatString
0x180052c94  test    eax, eax
0x180052c96  js      loc_180052D59
0x180052c9c  mov     rcx, [rsp+100h+var_E0]; string
0x180052ca1  call    cs:__imp_WindowsDeleteString
0x180052ca7  mov     rdx, [rbp+57h+newString]; string2
0x180052cab  lea     r8, [rsp+100h+var_E0]; newString
0x180052cb0  mov     rcx, [rbp+57h+var_D0]; string1
0x180052cb4  mov     [rsp+100h+var_E0], r14
0x180052cb9  call    cs:__imp_WindowsConcatString
0x180052cbf  test    eax, eax
0x180052cc1  js      loc_180052D59
0x180052cc7  lea     rdi, [rbx+0D8h]
0x180052cce  mov     rax, [rdi]
0x180052cd1  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180052cd8  jnz     short loc_180052CE5
0x180052cda  mov     rax, [rdi+8]
0x180052cde  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180052ce5  test    rax, rax
0x180052ce8  jz      short loc_180052D4B
0x180052cea  xor     ecx, ecx; string
0x180052cec  mov     [rbp+57h+var_C0], r14
0x180052cf0  call    cs:__imp_WindowsDeleteString
0x180052cf6  lea     r9, [rbp+57h+string2]; string
0x180052cfa  mov     [rbp+57h+var_C0], r14
0x180052cfe  lea     r8, [rbp+57h+var_98]; hstringHeader
0x180052d02  mov     [rbp+57h+string2], r14
0x180052d06  mov     edx, 1; length
0x180052d0b  lea     rcx, asc_18011A788; "#"
0x180052d12  call    cs:__imp_WindowsCreateStringReference
0x180052d18  test    eax, eax
0x180052d1a  js      loc_180052DCC
0x180052d20  mov     rdx, [rbp+57h+string2]; string2
0x180052d24  lea     r8, [rbp+57h+var_C0]; newString
0x180052d28  mov     rcx, [rsp+100h+var_E0]; string1
0x180052d2d  call    cs:__imp_WindowsConcatString
0x180052d33  mov     ebx, eax
0x180052d35  test    eax, eax
0x180052d37  jns     loc_180052DDF
0x180052d3d  mov     rcx, [rbp+57h+var_C0]; string
0x180052d41  call    cs:__imp_WindowsDeleteString
0x180052d47  test    ebx, ebx
0x180052d49  js      short loc_180052D59
0x180052d4b  mov     rcx, [rsp+100h+var_E0]; string
0x180052d50  mov     rdx, rsi; newString
0x180052d53  call    cs:__imp_WindowsDuplicateString
0x180052d59  mov     rcx, [rsp+100h+var_E0]; string
0x180052d5e  mov     [rbp+57h+string], r14
0x180052d62  call    cs:__imp_WindowsDeleteString
0x180052d68  mov     rcx, [rbp+57h+var_D0]; string
0x180052d6c  mov     [rsp+100h+var_E0], r14
0x180052d71  call    cs:__imp_WindowsDeleteString
0x180052d77  mov     rcx, [rsp+100h+string1]; string
0x180052d7c  mov     [rbp+57h+var_D0], r14
0x180052d80  call    cs:__imp_WindowsDeleteString
0x180052d86  mov     rcx, [rbp+57h+newString]; string
0x180052d8a  mov     [rsp+100h+string1], r14
0x180052d8f  call    cs:__imp_WindowsDeleteString
0x180052d95  mov     rcx, [rbp+57h+var_20]
0x180052d99  xor     rcx, rsp; StackCookie
0x180052d9c  call    __security_check_cookie
0x180052da1  lea     r11, [rsp+100h+var_10]
0x180052da9  mov     rbx, [r11+30h]
0x180052dad  mov     rsi, [r11+38h]
0x180052db1  mov     rsp, r11
0x180052db4  pop     r14
0x180052db6  pop     rdi
0x180052db7  pop     rbp
0x180052db8  retn
0x180052db9  xor     r9d, r9d; lpArguments
0x180052dbc  xor     r8d, r8d; nNumberOfArguments
0x180052dbf  mov     ecx, eax; dwExceptionCode
0x180052dc1  lea     edx, [r9+1]; dwExceptionFlags
0x180052dc5  call    cs:__imp_RaiseException
0x180052dcb  int     3; Trap to Debugger
0x180052dcc  xor     r9d, r9d; lpArguments
0x180052dcf  xor     r8d, r8d; nNumberOfArguments
0x180052dd2  mov     ecx, eax; dwExceptionCode
0x180052dd4  lea     edx, [r9+1]; dwExceptionFlags
0x180052dd8  call    cs:__imp_RaiseException
0x180052dde  int     3; Trap to Debugger
0x180052ddf  xor     edx, edx; Val
0x180052de1  lea     rcx, [rbp+57h+sz]; void *
0x180052de5  lea     r8d, [rdx+4Eh]; Size
0x180052de9  call    memset_0
0x180052dee  mov     r8d, 27h ; '''; cchMax
0x180052df4  lea     rdx, [rbp+57h+sz]; lpsz
0x180052df8  mov     rcx, rdi; rguid
0x180052dfb  call    cs:__imp_StringFromGUID2
0x180052e01  mov     rcx, [rsp+100h+var_E0]; string
0x180052e06  call    cs:__imp_WindowsDeleteString
0x180052e0c  lea     rdx, [rbp+57h+sz]; sourceString
0x180052e10  mov     [rsp+100h+var_E0], r14
0x180052e15  lea     rcx, [rbp+57h+var_98]; hstringHeader
0x180052e19  call    ??$?0$0CH@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0CH@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[39])
0x180052e1e  mov     rcx, [rbp+57h+var_C0]; string1
0x180052e22  lea     r8, [rsp+100h+var_E0]; newString
0x180052e27  mov     rdx, [rax+18h]; string2
0x180052e2b  call    cs:__imp_WindowsConcatString
0x180052e31  mov     ebx, eax
0x180052e33  jmp     loc_180052D3D
```
