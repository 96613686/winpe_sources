# NotificationParser::ConvertDisplayTimestampToFILETIME(Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *> *)

- ea: `0x18000c7d0`
- end: `0x18000cb62`
- name: `?ConvertDisplayTimestampToFILETIME@NotificationParser@@AEAAXPEAU?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@Z`
- size: `914`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800020d0`

## callees

- `0x180005670`
- `0x18000c7d0`
- `0x1800180cc`
- `0x18001b848`
- `0x18001cc5c`
- `0x18001ff00`
- `0x18002e090`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c8cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c8f8`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c8cc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000c8f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000c8ee`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoui64` at `0x18000c8ee`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c9c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ca82`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cb42`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000c9c6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000ca82`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000cb42`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ca2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c824`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000c9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000ca2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c8db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c8db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000c920`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cac8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000c89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000ca63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000cac8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c951`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000c951`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18000c933`
- `dmiso8601utils!ISO8601StringToSystemTime` at `0x18000c933`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HRESULT __fastcall NotificationParser::ConvertDisplayTimestampToFILETIME(__int64 *a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, HSTRING, __int64 *); // rbx
  HRESULT result; // eax
  __int64 v6; // rcx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, HSTRING *); // rbx
  int v9; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v11; // rcx
  _DWORD *v12; // rax
  PCWSTR v13; // rax
  int v14; // eax
  void *v15; // rdx
  unsigned int v16; // r8d
  const char *v17; // r9
  __int64 v18; // r14
  __int64 (__fastcall *v19)(__int64, HSTRING, __int64 *); // r15
  const WCHAR *p_string; // rdi
  unsigned __int64 v21; // rbx
  int v22; // eax
  __int64 (__fastcall *v23)(__int64, HSTRING, __int64, _BYTE *); // rdi
  __int64 v24; // rbx
  int v25; // eax
  int v26; // [rsp+20h] [rbp-69h]
  _BYTE v27[8]; // [rsp+30h] [rbp-59h] BYREF
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  HSTRING v29; // [rsp+40h] [rbp-49h] BYREF
  int v30; // [rsp+48h] [rbp-41h] BYREF
  struct _FILETIME FileTime; // [rsp+50h] [rbp-39h] BYREF
  _WORD *v32; // [rsp+58h] [rbp-31h] BYREF
  HSTRING string; // [rsp+60h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-21h] BYREF
  SYSTEMTIME SystemTime; // [rsp+80h] [rbp-9h] BYREF
  HSTRING v36; // [rsp+90h] [rbp+7h] BYREF
  HSTRING_HEADER v37; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v28 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)a2 + 48LL);
  if ( WindowsCreateStringReference(L"displayTimestamp", 0x10u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  result = v4(a2, string, &v28);
  if ( result >= 0 )
  {
    v29 = 0;
    v7 = v28;
    v8 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 152LL);
    WindowsDeleteString(0);
    v29 = 0;
    v9 = v8(v7, &v29);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x810,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v9,
        v26);
    FileTime = 0;
    v32 = 0;
    *(_DWORD *)_o__errno(retaddr) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v29, 0);
    FileTime = (struct _FILETIME)_o__wcstoui64(StringRawBuffer, &v32, 10);
    v12 = (_DWORD *)_o__errno(v11);
    if ( (unsigned __int64)(*(_QWORD *)&FileTime - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL && !*v32 && *v12 != 22 && *v12 != 34 )
    {
      WindowsDeleteString(v29);
      v29 = 0;
      return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    }
    v30 = 0;
    SystemTime = 0;
    v13 = WindowsGetStringRawBuffer(v29, 0);
    v14 = ISO8601StringToSystemTime(v13, 0, &SystemTime, &v30);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x827,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v14,
        v26);
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, v15, v16, v17);
    v18 = *a1;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v18 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    ((void (__fastcall *)(_QWORD, _QWORD))std::_Integral_to_string<unsigned short,unsigned __int64>)(&string, FileTime);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] > 7u )
      p_string = (const WCHAR *)string;
    else
      p_string = (const WCHAR *)&string;
    v21 = -1;
    do
      ++v21;
    while ( p_string[v21] );
    if ( v21 > 0xFFFFFFFF )
    {
      LODWORD(v21) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(p_string, v21, &v37, &v36);
    v22 = v19(v18, v36, &v28);
    if ( v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82B,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v22,
        v26);
    if ( *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] > 7u )
      std::_Deallocate<16>(string, 2LL * *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] + 2);
    v27[0] = 0;
    v23 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)a2 + 80LL);
    v24 = v28;
    if ( WindowsCreateStringReference(L"displayTimestamp", 0x10u, &v37, &v36) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v25 = v23(a2, v36, v24, v27);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x82F,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\client\\notificationparser\\src\\notificationparser.cpp",
        (const char *)(unsigned int)v25,
        v26);
    result = WindowsDeleteString(v29);
    v29 = 0;
  }
  v6 = v28;
  if ( v28 )
  {
    v28 = 0;
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return result;
}

```

## disassembly

```asm
0x18000c7d0  mov     [rsp-8+arg_10], rbx
0x18000c7d5  mov     [rsp-8+arg_18], rsi
0x18000c7da  push    rbp
0x18000c7db  push    rdi
0x18000c7dc  push    r12
0x18000c7de  push    r14
0x18000c7e0  push    r15
0x18000c7e2  lea     rbp, [rsp-37h]
0x18000c7e7  sub     rsp, 0C0h
0x18000c7ee  mov     rax, cs:__security_cookie
0x18000c7f5  xor     rax, rsp
0x18000c7f8  mov     [rbp+57h+var_30], rax
0x18000c7fc  mov     rsi, rdx
0x18000c7ff  mov     r14, rcx
0x18000c802  xor     r12d, r12d
0x18000c805  mov     [rbp+57h+var_A8], r12
0x18000c809  mov     rax, [rdx]
0x18000c80c  mov     rbx, [rax+30h]
0x18000c810  lea     r9, [rbp+57h+string]; string
0x18000c814  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000c818  mov     edx, 10h; length
0x18000c81d  lea     rcx, aDisplaytimesta; "displayTimestamp"
0x18000c824  call    cs:__imp_WindowsCreateStringReference
0x18000c82a  test    eax, eax
0x18000c82c  js      loc_18000CA72
0x18000c832  lea     r8, [rbp+57h+var_A8]
0x18000c836  mov     rdx, [rbp+57h+string]
0x18000c83a  mov     rcx, rsi
0x18000c83d  mov     rax, rbx
0x18000c840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c845  test    eax, eax
0x18000c847  jns     short loc_18000C88B
0x18000c849  mov     rcx, [rbp+57h+var_A8]
0x18000c84d  test    rcx, rcx
0x18000c850  jz      short loc_18000C863
0x18000c852  mov     [rbp+57h+var_A8], r12
0x18000c856  mov     rax, [rcx]
0x18000c859  mov     rax, [rax+10h]
0x18000c85d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c862  nop
0x18000c863  mov     rcx, [rbp+57h+var_30]
0x18000c867  xor     rcx, rsp; StackCookie
0x18000c86a  call    __security_check_cookie
0x18000c86f  lea     r11, [rsp+0E0h+var_20]
0x18000c877  mov     rbx, [r11+40h]
0x18000c87b  mov     rsi, [r11+48h]
0x18000c87f  mov     rsp, r11
0x18000c882  pop     r15
0x18000c884  pop     r14
0x18000c886  pop     r12
0x18000c888  pop     rdi
0x18000c889  pop     rbp
0x18000c88a  retn
0x18000c88b  mov     [rbp+57h+var_A0], r12
0x18000c88f  mov     rdi, [rbp+57h+var_A8]
0x18000c893  mov     rax, [rdi]
0x18000c896  mov     rbx, [rax+98h]
0x18000c89d  xor     ecx, ecx; string
0x18000c89f  call    cs:__imp_WindowsDeleteString
0x18000c8a5  mov     [rbp+57h+var_A0], r12
0x18000c8a9  lea     rdx, [rbp+57h+var_A0]
0x18000c8ad  mov     rcx, rdi
0x18000c8b0  mov     rax, rbx
0x18000c8b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b8  mov     rcx, [rbp+5Fh]; this
0x18000c8bc  test    eax, eax
0x18000c8be  js      loc_18000CA8D
0x18000c8c4  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x18000c8c8  mov     [rbp+57h+var_88], r12
0x18000c8cc  call    cs:__imp__o__errno
0x18000c8d2  mov     [rax], r12d
0x18000c8d5  xor     edx, edx; length
0x18000c8d7  mov     rcx, [rbp+57h+var_A0]; string
0x18000c8db  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c8e1  mov     r8d, 0Ah
0x18000c8e7  lea     rdx, [rbp+57h+var_88]
0x18000c8eb  mov     rcx, rax
0x18000c8ee  call    cs:__imp__o__wcstoui64
0x18000c8f4  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rax
0x18000c8f8  call    cs:__imp__o__errno
0x18000c8fe  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18000c902  dec     rcx
0x18000c905  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c909  jbe     loc_18000CAA2
0x18000c90f  mov     [rbp+57h+var_98], r12d
0x18000c913  xorps   xmm0, xmm0
0x18000c916  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18000c91a  xor     edx, edx; length
0x18000c91c  mov     rcx, [rbp+57h+var_A0]; string
0x18000c920  call    cs:__imp_WindowsGetStringRawBuffer
0x18000c926  lea     r9, [rbp+57h+var_98]
0x18000c92a  lea     r8, [rbp+57h+SystemTime]
0x18000c92e  xor     edx, edx
0x18000c930  mov     rcx, rax
0x18000c933  call    cs:__imp_ISO8601StringToSystemTime
0x18000c939  mov     rcx, [rbp+5Fh]; this
0x18000c93d  test    eax, eax
0x18000c93f  js      loc_18000CAE0
0x18000c945  mov     rbx, [rbp+5Fh]
0x18000c949  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x18000c94d  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18000c951  call    cs:__imp_SystemTimeToFileTime
0x18000c957  test    eax, eax
0x18000c959  jz      loc_18000CAF5
0x18000c95f  mov     r14, [r14]
0x18000c962  mov     rax, [r14]
0x18000c965  mov     r15, [rax+90h]
0x18000c96c  lea     rcx, [rbp+57h+var_A8]
0x18000c970  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000c975  mov     rdx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x18000c979  lea     rcx, [rbp+57h+string]
0x18000c97d  call    ??$_Integral_to_string@G_K@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@_K@Z; std::_Integral_to_string<ushort,unsigned __int64>(unsigned __int64)
0x18000c982  nop
0x18000c983  cmp     qword ptr [rbp+57h+hstringHeader.Reserved+10h], 7
0x18000c988  ja      loc_18000CAFE
0x18000c98e  lea     rdi, [rbp+57h+string]
0x18000c992  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000c999  nop     dword ptr [rax+00000000h]
0x18000c9a0  inc     rbx
0x18000c9a3  cmp     word ptr [rdi+rbx*2], 0
0x18000c9a8  jnz     short loc_18000C9A0
0x18000c9aa  mov     eax, 0FFFFFFFFh
0x18000c9af  cmp     rbx, rax
0x18000c9b2  jbe     short loc_18000C9CC
0x18000c9b4  mov     ebx, eax
0x18000c9b6  xor     r9d, r9d; lpArguments
0x18000c9b9  xor     r8d, r8d; nNumberOfArguments
0x18000c9bc  mov     edx, 1; dwExceptionFlags
0x18000c9c1  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000c9c6  call    cs:__imp_RaiseException
0x18000c9cc  lea     r9, [rbp+57h+var_50]; string
0x18000c9d0  lea     r8, [rbp+57h+var_48]; hstringHeader
0x18000c9d4  mov     edx, ebx; length
0x18000c9d6  mov     rcx, rdi; sourceString
0x18000c9d9  call    cs:__imp_WindowsCreateStringReference
0x18000c9df  lea     r8, [rbp+57h+var_A8]
0x18000c9e3  mov     rdx, [rbp+57h+var_50]
0x18000c9e7  mov     rcx, r14
0x18000c9ea  mov     rax, r15
0x18000c9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f2  mov     rcx, [rbp+5Fh]; this
0x18000c9f6  test    eax, eax
0x18000c9f8  js      loc_18000CB07
0x18000c9fe  mov     rdx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18000ca02  cmp     rdx, 7
0x18000ca06  ja      loc_18000CB1C
0x18000ca0c  mov     [rbp+57h+var_B0], 0
0x18000ca10  mov     rax, [rsi]
0x18000ca13  mov     rdi, [rax+50h]
0x18000ca17  mov     rbx, [rbp+57h+var_A8]
0x18000ca1b  lea     r9, [rbp+57h+var_50]; string
0x18000ca1f  lea     r8, [rbp+57h+var_48]; hstringHeader
0x18000ca23  mov     edx, 10h; length
0x18000ca28  lea     rcx, aDisplaytimesta; "displayTimestamp"
0x18000ca2f  call    cs:__imp_WindowsCreateStringReference
0x18000ca35  test    eax, eax
0x18000ca37  js      loc_18000CB32
0x18000ca3d  lea     r9, [rbp+57h+var_B0]
0x18000ca41  mov     r8, rbx
0x18000ca44  mov     rdx, [rbp+57h+var_50]
0x18000ca48  mov     rcx, rsi
0x18000ca4b  mov     rax, rdi
0x18000ca4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca53  mov     rcx, [rbp+5Fh]; this
0x18000ca57  test    eax, eax
0x18000ca59  js      loc_18000CB4D
0x18000ca5f  mov     rcx, [rbp+57h+var_A0]; string
0x18000ca63  call    cs:__imp_WindowsDeleteString
0x18000ca69  mov     [rbp+57h+var_A0], r12
0x18000ca6d  jmp     loc_18000C849
0x18000ca72  xor     r9d, r9d; lpArguments
0x18000ca75  xor     r8d, r8d; nNumberOfArguments
0x18000ca78  mov     edx, 1; dwExceptionFlags
0x18000ca7d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000ca82  call    cs:__imp_RaiseException
0x18000ca88  jmp     loc_18000C832
0x18000ca8d  mov     r9d, eax; char *
0x18000ca90  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000ca97  mov     edx, 810h; void *
0x18000ca9c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000caa2  mov     rcx, [rbp+57h+var_88]
0x18000caa6  cmp     word ptr [rcx], 0
0x18000caaa  jnz     loc_18000C90F
0x18000cab0  mov     ecx, [rax]
0x18000cab2  cmp     ecx, 16h
0x18000cab5  jz      loc_18000C90F
0x18000cabb  cmp     ecx, 22h ; '"'
0x18000cabe  jz      loc_18000C90F
0x18000cac4  mov     rcx, [rbp+57h+var_A0]; string
0x18000cac8  call    cs:__imp_WindowsDeleteString
0x18000cace  mov     [rbp+57h+var_A0], r12
0x18000cad2  lea     rcx, [rbp+57h+var_A8]
0x18000cad6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000cadb  jmp     loc_18000C863
0x18000cae0  mov     r9d, eax; char *
0x18000cae3  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000caea  mov     edx, 827h; void *
0x18000caef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000caf5  mov     rcx, rbx; this
0x18000caf8  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18000cafe  mov     rdi, [rbp+57h+string]
0x18000cb02  jmp     loc_18000C992
0x18000cb07  mov     r9d, eax; char *
0x18000cb0a  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cb11  mov     edx, 82Bh; void *
0x18000cb16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cb1c  lea     rdx, ds:2[rdx*2]
0x18000cb24  mov     rcx, [rbp+57h+string]
0x18000cb28  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18000cb2d  jmp     loc_18000CA0C
0x18000cb32  xor     r9d, r9d; lpArguments
0x18000cb35  xor     r8d, r8d; nNumberOfArguments
0x18000cb38  mov     edx, 1; dwExceptionFlags
0x18000cb3d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000cb42  call    cs:__imp_RaiseException
0x18000cb48  jmp     loc_18000CA3D
0x18000cb4d  mov     r9d, eax; char *
0x18000cb50  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18000cb57  mov     edx, 82Fh; void *
0x18000cb5c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
