# _lambda_ecf613b2a3d6774c3bee26d626498818_::operator()_wpc::UI::Logging::MonitorUILogger::GetAppDisplayName_

- ea: `0x140045940`
- end: `0x140045d88`
- name: `_lambda_ecf613b2a3d6774c3bee26d626498818_::operator()_wpc::UI::Logging::MonitorUILogger::GetAppDisplayName_`
- size: `1096`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14004c4a0`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000b744`
- `0x14000ccac`
- `0x14001f6b4`
- `0x14003c488`
- `0x14003c5d8`
- `0x140045250`
- `0x140045940`
- `0x140060f58`
- `0x140070a9c`
- `0x1400711e8`
- `0x140071418`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140045b6d`
- `KERNEL32!GetLastError` at `0x140045b6d`
- `KERNEL32!SetLastError` at `0x140045b80`
- `KERNEL32!SetLastError` at `0x140045b80`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045af6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140045af6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045b78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045c44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140045c8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140045bd2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140045bd2`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_OWORD *__fastcall lambda_ecf613b2a3d6774c3bee26d626498818_::operator()_wpc::UI::Logging::MonitorUILogger::GetAppDisplayName_(
        _QWORD *a1,
        _OWORD *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rcx
  __int64 v6; // rcx
  char v7; // r8
  __int64 v8; // rax
  __int64 v9; // rax
  HRESULT v10; // eax
  int v11; // ebx
  char **v12; // rax
  const WCHAR *v13; // rax
  LPVOID v14; // r15
  __int64 (__fastcall *v15)(LPVOID, _QWORD, __int64, HSTRING *); // r12
  __int64 v16; // rbx
  _QWORD *v17; // rax
  int v18; // eax
  int v19; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v21; // r8
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  const WCHAR *v25; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+60h] [rbp-A0h]
  __int128 pExceptionObject; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int64 v30; // [rsp+88h] [rbp-78h]
  char v31; // [rsp+90h] [rbp-70h]
  char **v32; // [rsp+98h] [rbp-68h] BYREF
  char *v33[4]; // [rsp+A0h] [rbp-60h] BYREF
  char v34; // [rsp+C0h] [rbp-40h]
  char *v35[4]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v36[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v37; // [rsp+F0h] [rbp-10h]
  void **v38; // [rsp+108h] [rbp+8h] BYREF

  *(_QWORD *)&v26 = a2;
  v4 = (_QWORD *)*a1;
  if ( *(_DWORD *)*a1 )
  {
    ppv = 0;
    v10 = CoCreateInstance(&rclsid, 0, 1u, &GUID_222eb002_1c9e_515d_9965_e5231a6d4574, &ppv);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          10,
          WPP_9b57d64f09ec319e5981f6a81644f01b_Traceguids,
          (unsigned int)v10);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v11);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    string = 0;
    std::wstring::wstring((__int64)&v32, a1[1] + 72LL);
    v12 = (char **)&v32;
    if ( v33[2] > (char *)7 )
      v12 = v32;
    *(_QWORD *)&v26 = v12;
    std::wstring::wstring((__int64)v35, *a1 + 48LL);
    v13 = (const WCHAR *)v35;
    if ( v35[3] > (char *)7 )
      v13 = (const WCHAR *)v35[0];
    v25 = v13;
    v14 = ppv;
    v15 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, HSTRING *))(*(_QWORD *)ppv + 64LL);
    string = 0;
    v16 = *(_QWORD *)Windows::Internal::StringReference::StringReference((__int64)v36, &v25);
    v17 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      (__int64)&pExceptionObject,
                      (const WCHAR **)&v26);
    v18 = v15(v14, *v17, v16, &string);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          11,
          WPP_9b57d64f09ec319e5981f6a81644f01b_Traceguids,
          (unsigned int)v18);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)&pExceptionObject, v19);
      throw (ErrorCodeException *)&pExceptionObject;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v26 = 0;
    v27 = 0u;
    v21 = -1;
    do
      ++v21;
    while ( StringRawBuffer[v21] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&v26, StringRawBuffer, v21);
    if ( (_QWORD)v27 )
    {
      std::wstring::wstring((__int64)a2, (__int64)&v26);
      std::wstring::~wstring((char **)&v26);
      std::wstring::~wstring(v35);
      std::wstring::~wstring((char **)&v32);
      if ( string )
        WindowsDeleteString(string);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    else
    {
      std::wstring::~wstring((char **)&v26);
      std::wstring::~wstring(v35);
      std::wstring::~wstring((char **)&v32);
      if ( string )
        WindowsDeleteString(string);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      std::wstring::wstring((__int64)a2, *a1 + 48LL);
    }
  }
  else
  {
    if ( v4[9] <= 7u )
      v5 = v4 + 6;
    else
      v5 = (_QWORD *)v4[6];
    *(_QWORD *)&v26 = v5;
    *((_QWORD *)&v26 + 1) = v4[8];
    v6 = appids::Private::ParsePlatformIndependentString(&v32, &v26);
    v7 = -1;
    v31 = -1;
    v8 = *(char *)(v6 + 40) + 1LL;
    if ( *(char *)(v6 + 40) != -1 )
    {
      v29 = 0;
      v30 = 0;
      pExceptionObject = 0;
      pExceptionObject = *(_OWORD *)(v6 + 8);
      v29 = *(_QWORD *)(v6 + 24);
      v30 = *(_QWORD *)(v6 + 32);
      *(_QWORD *)(v6 + 24) = 0;
      *(_QWORD *)(v6 + 32) = 7;
      *(_WORD *)(v6 + 8) = 0;
      if ( v8 == 1 )
      {
        v7 = 0;
        v31 = 0;
      }
      else
      {
        v7 = 1;
        v31 = 1;
      }
    }
    if ( v34 != -1 )
    {
      std::wstring::~wstring(v33);
      v7 = v31;
    }
    if ( v7 )
      std::_Throw_bad_variant_access();
    std::wstring::wstring((__int64)&v32, (__int64)&pExceptionObject);
    if ( v31 != -1 )
      std::wstring::~wstring((char **)&pExceptionObject);
    PackageApplication::PackageApplication((PackageApplication *)v36, (const struct appids::PackageFamilyName *)&v32);
    v9 = Lazy__anonymous_namespace_::LazyData_Optional_::operator__(v37 + 96);
    std::wstring::wstring((__int64)&v26, v9 + 32);
    *a2 = v26;
    a2[1] = v27;
    *(_QWORD *)&v27 = 0;
    *((_QWORD *)&v27 + 1) = 7;
    LOWORD(v26) = 0;
    std::wstring::~wstring((char **)&v26);
    PackageApplication::~PackageApplication((PackageApplication *)&v38);
    v38 = &Application::`vftable';
    std::wstring::~wstring((char **)&v32);
  }
  return a2;
}

```

## disassembly

```asm
0x140045940  mov     [rsp-8+arg_10], rbx
0x140045945  push    rbp
0x140045946  push    rsi
0x140045947  push    rdi
0x140045948  push    r12
0x14004594a  push    r13
0x14004594c  push    r14
0x14004594e  push    r15
0x140045950  lea     rbp, [rsp-20h]
0x140045955  sub     rsp, 120h
0x14004595c  mov     rax, cs:__security_cookie
0x140045963  xor     rax, rsp
0x140045966  mov     [rbp+50h+var_40], rax
0x14004596a  mov     rdi, rdx
0x14004596d  mov     rsi, rcx
0x140045970  mov     qword ptr [rsp+150h+var_100], rdx
0x140045975  xor     r13d, r13d
0x140045978  mov     rax, [rcx]
0x14004597b  cmp     [rax], r13d
0x14004597e  jnz     loc_140045AD3
0x140045984  lea     ebx, [r13+7]
0x140045988  cmp     [rax+48h], rbx
0x14004598c  jbe     short loc_140045994
0x14004598e  mov     rcx, [rax+30h]
0x140045992  jmp     short loc_140045998
0x140045994  lea     rcx, [rax+30h]
0x140045998  mov     qword ptr [rsp+150h+var_100], rcx
0x14004599d  mov     rax, [rax+40h]
0x1400459a1  mov     qword ptr [rsp+150h+var_100+8], rax
0x1400459a6  lea     rdx, [rsp+150h+var_100]
0x1400459ab  lea     rcx, [rbp+50h+var_B8]
0x1400459af  call    ?ParsePlatformIndependentString@Private@appids@@YA?AU?$pair@W4RuntimeIdType@appids@@V?$variant@VPackageFamilyName@appids@@VUnsupportedAppId@2@@std@@@std@@V?$basic_string_view@GU?$char_traits@G@std@@@4@@Z; appids::Private::ParsePlatformIndependentString(std::basic_string_view<ushort>)
0x1400459b4  mov     rcx, rax
0x1400459b7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400459bb  mov     [rbp+50h+var_C0], r8b
0x1400459bf  movsx   rax, byte ptr [rax+28h]
0x1400459c4  add     rax, 1
0x1400459c8  jz      short loc_140045A17
0x1400459ca  xorps   xmm0, xmm0
0x1400459cd  mov     [rbp+50h+var_D0], r13
0x1400459d1  mov     [rbp+50h+var_C8], r13
0x1400459d5  movups  [rsp+150h+pExceptionObject], xmm0
0x1400459da  movups  xmm0, xmmword ptr [rcx+8]
0x1400459de  movdqu  [rsp+150h+pExceptionObject], xmm0
0x1400459e4  cmp     rax, 1
0x1400459e8  mov     rax, [rcx+18h]
0x1400459ec  mov     [rbp+50h+var_D0], rax
0x1400459f0  mov     rax, [rcx+20h]
0x1400459f4  mov     [rbp+50h+var_C8], rax
0x1400459f8  mov     [rcx+18h], r13
0x1400459fc  mov     [rcx+20h], rbx
0x140045a00  mov     [rcx+8], r13w
0x140045a05  jz      short loc_140045A10
0x140045a07  mov     r8b, 1
0x140045a0a  mov     [rbp+50h+var_C0], r8b
0x140045a0e  jmp     short loc_140045A17
0x140045a10  mov     r8b, r13b
0x140045a13  mov     [rbp+50h+var_C0], r13b
0x140045a17  movsx   rax, [rbp+50h+var_90]
0x140045a1c  add     rax, 1
0x140045a20  jz      short loc_140045A2F
0x140045a22  lea     rcx, [rbp+50h+var_B0]
0x140045a26  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045a2b  mov     r8b, [rbp+50h+var_C0]
0x140045a2f  test    r8b, r8b
0x140045a32  jnz     loc_140045D33
0x140045a38  lea     rdx, [rsp+150h+pExceptionObject]
0x140045a3d  lea     rcx, [rbp+50h+var_B8]
0x140045a41  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045a46  nop
0x140045a47  movsx   rax, [rbp+50h+var_C0]
0x140045a4c  add     rax, 1
0x140045a50  jz      short loc_140045A5C
0x140045a52  lea     rcx, [rsp+150h+pExceptionObject]
0x140045a57  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045a5c  lea     rdx, [rbp+50h+var_B8]; struct appids::PackageFamilyName *
0x140045a60  lea     rcx, [rbp+50h+var_68]; this
0x140045a64  call    ??0PackageApplication@@QEAA@AEBVPackageFamilyName@appids@@@Z; PackageApplication::PackageApplication(appids::PackageFamilyName const &)
0x140045a69  nop
0x140045a6a  mov     rcx, [rbp+50h+var_60]
0x140045a6e  add     rcx, 60h ; '`'
0x140045a72  call    Lazy__anonymous_namespace___LazyData_Optional___operator__
0x140045a77  lea     rdx, [rax+20h]
0x140045a7b  lea     rcx, [rsp+150h+var_100]
0x140045a80  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045a85  movups  xmm0, [rsp+150h+var_100]
0x140045a8a  movups  xmmword ptr [rdi], xmm0
0x140045a8d  movups  xmm1, [rsp+150h+var_F0]
0x140045a92  movups  xmmword ptr [rdi+10h], xmm1
0x140045a96  mov     qword ptr [rsp+150h+var_F0], r13
0x140045a9b  mov     qword ptr [rsp+150h+var_F0+8], rbx
0x140045aa0  mov     word ptr [rsp+150h+var_100], r13w
0x140045aa6  lea     rcx, [rsp+150h+var_100]
0x140045aab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045ab0  nop
0x140045ab1  lea     rcx, [rbp+50h+var_48]; this
0x140045ab5  call    ??1PackageApplication@@UEAA@XZ; PackageApplication::~PackageApplication(void)
0x140045aba  lea     rax, ??_7Application@@6B@; const Application::`vftable'
0x140045ac1  mov     [rbp+50h+var_48], rax
0x140045ac5  lea     rcx, [rbp+50h+var_B8]
0x140045ac9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045ace  jmp     loc_140045CBA
0x140045ad3  mov     [rsp+150h+var_118], r13
0x140045ad8  lea     rax, [rsp+150h+var_118]
0x140045add  mov     [rsp+150h+ppv], rax; ppv
0x140045ae2  lea     r9, _GUID_222eb002_1c9e_515d_9965_e5231a6d4574; riid
0x140045ae9  xor     edx, edx; pUnkOuter
0x140045aeb  lea     r8d, [rdx+1]; dwClsContext
0x140045aef  lea     rcx, rclsid; rclsid
0x140045af6  call    cs:__imp_CoCreateInstance
0x140045afc  mov     ebx, eax
0x140045afe  test    eax, eax
0x140045b00  js      loc_140045D39
0x140045b06  mov     [rsp+150h+string], r13
0x140045b0b  mov     rdx, [rsi+8]
0x140045b0f  add     rdx, 48h ; 'H'
0x140045b13  lea     rcx, [rbp+50h+var_B8]
0x140045b17  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045b1c  nop
0x140045b1d  lea     rax, [rbp+50h+var_B8]
0x140045b21  mov     ebx, 7
0x140045b26  cmp     [rbp+50h+var_A0], rbx
0x140045b2a  cmova   rax, [rbp+50h+var_B8]
0x140045b2f  mov     qword ptr [rsp+150h+var_100], rax
0x140045b34  mov     rdx, [rsi]
0x140045b37  add     rdx, 30h ; '0'
0x140045b3b  lea     rcx, [rbp+50h+var_88]
0x140045b3f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045b44  nop
0x140045b45  lea     rax, [rbp+50h+var_88]
0x140045b49  cmp     [rbp+50h+var_70], rbx
0x140045b4d  cmova   rax, [rbp+50h+var_88]
0x140045b52  mov     [rsp+150h+var_108], rax
0x140045b57  mov     r15, [rsp+150h+var_118]
0x140045b5c  mov     rax, [r15]
0x140045b5f  mov     r12, [rax+40h]
0x140045b63  mov     r14, [rsp+150h+string]
0x140045b68  test    r14, r14
0x140045b6b  jz      short loc_140045B86
0x140045b6d  call    cs:__imp_GetLastError
0x140045b73  mov     ebx, eax
0x140045b75  mov     rcx, r14; string
0x140045b78  call    cs:__imp_WindowsDeleteString
0x140045b7e  mov     ecx, ebx; dwErrCode
0x140045b80  call    cs:__imp_SetLastError
0x140045b86  mov     [rsp+150h+string], r13
0x140045b8b  lea     rdx, [rsp+150h+var_108]
0x140045b90  lea     rcx, [rbp+50h+var_68]
0x140045b94  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x140045b99  mov     rbx, [rax]
0x140045b9c  lea     rdx, [rsp+150h+var_100]
0x140045ba1  lea     rcx, [rsp+150h+pExceptionObject]
0x140045ba6  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x140045bab  lea     r9, [rsp+150h+string]
0x140045bb0  mov     r8, rbx
0x140045bb3  mov     rdx, [rax]
0x140045bb6  mov     rcx, r15
0x140045bb9  mov     rax, r12
0x140045bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045bc1  mov     ebx, eax
0x140045bc3  test    eax, eax
0x140045bc5  js      loc_140045CE4
0x140045bcb  xor     edx, edx; length
0x140045bcd  mov     rcx, [rsp+150h+string]; string
0x140045bd2  call    cs:__imp_WindowsGetStringRawBuffer
0x140045bd8  xorps   xmm0, xmm0
0x140045bdb  movups  [rsp+150h+var_100], xmm0
0x140045be0  mov     qword ptr [rsp+150h+var_F0], r13
0x140045be5  mov     qword ptr [rsp+150h+var_F0+8], r13
0x140045bea  or      r8, 0FFFFFFFFFFFFFFFFh
0x140045bee  inc     r8
0x140045bf1  cmp     [rax+r8*2], r13w
0x140045bf6  jnz     short loc_140045BEE
0x140045bf8  mov     rdx, rax
0x140045bfb  lea     rcx, [rsp+150h+var_100]
0x140045c00  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140045c05  nop
0x140045c06  cmp     qword ptr [rsp+150h+var_F0], r13
0x140045c0b  jz      short loc_140045C64
0x140045c0d  lea     rdx, [rsp+150h+var_100]
0x140045c12  mov     rcx, rdi
0x140045c15  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045c1a  nop
0x140045c1b  lea     rcx, [rsp+150h+var_100]
0x140045c20  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c25  nop
0x140045c26  lea     rcx, [rbp+50h+var_88]
0x140045c2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c2f  nop
0x140045c30  lea     rcx, [rbp+50h+var_B8]
0x140045c34  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c39  nop
0x140045c3a  mov     rcx, [rsp+150h+string]; string
0x140045c3f  test    rcx, rcx
0x140045c42  jz      short loc_140045C4B
0x140045c44  call    cs:__imp_WindowsDeleteString
0x140045c4a  nop
0x140045c4b  mov     rcx, [rsp+150h+var_118]
0x140045c50  test    rcx, rcx
0x140045c53  jz      short loc_140045C62
0x140045c55  mov     rax, [rcx]
0x140045c58  mov     rax, [rax+10h]
0x140045c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045c61  nop
0x140045c62  jmp     short loc_140045CBA
0x140045c64  lea     rcx, [rsp+150h+var_100]
0x140045c69  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c6e  nop
0x140045c6f  lea     rcx, [rbp+50h+var_88]
0x140045c73  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c78  nop
0x140045c79  lea     rcx, [rbp+50h+var_B8]
0x140045c7d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140045c82  nop
0x140045c83  mov     rcx, [rsp+150h+string]; string
0x140045c88  test    rcx, rcx
0x140045c8b  jz      short loc_140045C94
0x140045c8d  call    cs:__imp_WindowsDeleteString
0x140045c93  nop
0x140045c94  mov     rcx, [rsp+150h+var_118]
0x140045c99  test    rcx, rcx
0x140045c9c  jz      short loc_140045CAB
0x140045c9e  mov     rax, [rcx]
0x140045ca1  mov     rax, [rax+10h]
0x140045ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140045caa  nop
0x140045cab  mov     rdx, [rsi]
0x140045cae  add     rdx, 30h ; '0'
0x140045cb2  mov     rcx, rdi
0x140045cb5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x140045cba  mov     rax, rdi
0x140045cbd  mov     rcx, [rbp+50h+var_40]
0x140045cc1  xor     rcx, rsp; StackCookie
0x140045cc4  call    __security_check_cookie
0x140045cc9  mov     rbx, [rsp+150h+arg_10]
0x140045cd1  add     rsp, 120h
0x140045cd8  pop     r15
0x140045cda  pop     r14
0x140045cdc  pop     r13
0x140045cde  pop     r12
0x140045ce0  pop     rdi
0x140045ce1  pop     rsi
0x140045ce2  pop     rbp
0x140045ce3  retn
0x140045ce4  lea     rdx, WPP_GLOBAL_Control
0x140045ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140045cf2  cmp     rcx, rdx
0x140045cf5  jz      short loc_140045D15
0x140045cf7  test    byte ptr [rcx+1Ch], 1
0x140045cfb  jz      short loc_140045D15
0x140045cfd  mov     edx, 0Bh
0x140045d02  mov     r9d, ebx
0x140045d05  lea     r8, WPP_9b57d64f09ec319e5981f6a81644f01b_Traceguids
0x140045d0c  mov     rcx, [rcx+10h]
0x140045d10  call    WPP_SF_d
0x140045d15  mov     edx, ebx; int
0x140045d17  lea     rcx, [rsp+150h+pExceptionObject]; this
0x140045d1c  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140045d21  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140045d28  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x140045d2d  call    _CxxThrowException_0
0x140045d33  call    ?_Throw_bad_variant_access@std@@YAXXZ; std::_Throw_bad_variant_access(void)
0x140045d39  lea     rdx, WPP_GLOBAL_Control
0x140045d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140045d47  cmp     rcx, rdx
0x140045d4a  jz      short loc_140045D6A
0x140045d4c  test    byte ptr [rcx+1Ch], 1
0x140045d50  jz      short loc_140045D6A
0x140045d52  mov     edx, 0Ah
0x140045d57  mov     r9d, ebx
0x140045d5a  lea     r8, WPP_9b57d64f09ec319e5981f6a81644f01b_Traceguids
0x140045d61  mov     rcx, [rcx+10h]
0x140045d65  call    WPP_SF_d
0x140045d6a  mov     edx, ebx; int
0x140045d6c  lea     rcx, [rsp+150h+pExceptionObject]; this
0x140045d71  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140045d76  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140045d7d  lea     rcx, [rsp+150h+pExceptionObject]; pExceptionObject
0x140045d82  call    _CxxThrowException_0
```
