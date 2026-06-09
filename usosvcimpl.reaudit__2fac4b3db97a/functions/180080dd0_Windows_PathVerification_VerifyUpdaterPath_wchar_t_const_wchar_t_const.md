# Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)

- ea: `0x180080dd0`
- end: `0x18008138d`
- name: `?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z`
- size: `1469`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800728a0`

## callees

- `0x18000f83c`
- `0x1800108b4`
- `0x180010f24`
- `0x1800112d0`
- `0x180011680`
- `0x18002feb0`
- `0x180036f98`
- `0x1800616ac`
- `0x180080dd0`
- `0x180081394`
- `0x180081458`
- `0x180081858`
- `0x1800dd744`
- `0x1800dd930`
- `0x1800e46b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008122e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008122e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080e1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180080e1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081330`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180080fbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180081330`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180080e64`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180080e64`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180081266`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180081266`

## string_xrefs

- `0x1800810ff`: `%ProgramData%\USOPrivate\Providers\Registered`
- `0x180081165`: `%ProgramData%\USOPrivate\Providers\Windows`
- `0x1800812e8`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`
- `0x180081366`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`
- `0x180081378`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`
- `0x180080f06`: `%CommonProgramFiles%`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Windows::PathVerification::VerifyUpdaterPath(_QWORD *a1, const char *a2, __int64 a3)
{
  __int64 v6; // r14
  const char *v7; // r9
  __int64 v8; // r8
  __m128i *v9; // rdx
  __int64 v10; // r8
  __m128i *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  __m128i *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r8
  __m128i *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  HRESULT v25; // eax
  __int64 v26; // rbx
  __int64 v27; // rsi
  char v28; // di
  const wchar_t *v29; // rcx
  int v31; // [rsp+20h] [rbp-E0h]
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  LPVOID v34; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR pszPathIn[3]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v37[32]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v38; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B8h] [rbp-48h]
  wchar_t pszPathOut[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+528h] [rbp+428h]

  pv = a1;
  EnterCriticalSection(&stru_1801508E0);
  pszPathIn[2] = (PCWSTR)&stru_1801508E0;
  v6 = -1;
  if ( qword_180150DE0 == qword_180150DD8 )
  {
    memset(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x14,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
        v7);
    v38 = 0;
    v39 = 0;
    v32 = 0;
    si128 = 0;
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    std::wstring::_Construct<1,wchar_t const *>(&v32, Buffer, v8);
    v9 = (__m128i *)*((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
    }
    else
    {
      **((_OWORD **)&v38 + 1) = v32;
      v9[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v32) = 0;
      *((_QWORD *)&v38 + 1) += 32LL;
    }
    std::wstring::~wstring(&v32);
    v34 = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      &v34,
      L"%CommonProgramFiles%");
    v32 = 0;
    si128 = 0;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v34 + v10) );
    std::wstring::_Construct<1,wchar_t const *>(&v32, v34, v10);
    v11 = (__m128i *)*((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
    }
    else
    {
      **((_OWORD **)&v38 + 1) = v32;
      v11[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v32) = 0;
      *((_QWORD *)&v38 + 1) += 32LL;
    }
    std::wstring::~wstring(&v32);
    v12 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%ProgramFiles%\\Microsoft");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &v34,
      v12);
    if ( pv )
      CoTaskMemFree(pv);
    v32 = 0;
    si128 = 0;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v34 + v13) );
    std::wstring::_Construct<1,wchar_t const *>(&v32, v34, v13);
    v14 = (__m128i *)*((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
    }
    else
    {
      **((_OWORD **)&v38 + 1) = v32;
      v14[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v32) = 0;
      *((_QWORD *)&v38 + 1) += 32LL;
    }
    std::wstring::~wstring(&v32);
    v15 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%ProgramFiles(x86)%\\Microsoft");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &v34,
      v15);
    if ( pv )
      CoTaskMemFree(pv);
    v32 = 0;
    si128 = 0;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v34 + v16) );
    std::wstring::_Construct<1,wchar_t const *>(&v32, v34, v16);
    v17 = (__m128i *)*((_QWORD *)&v38 + 1);
    if ( *((_QWORD *)&v38 + 1) == v39 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), &v32);
    }
    else
    {
      **((_OWORD **)&v38 + 1) = v32;
      v17[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v32) = 0;
      *((_QWORD *)&v38 + 1) += 32LL;
    }
    std::wstring::~wstring(&v32);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      v18 = wil::ExpandEnvironmentStringsW<std::wstring,256>(&v32, L"%ProgramData%\\USOPrivate\\Providers\\Registered");
      v19 = *((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) == v39 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), v18);
      }
      else
      {
        **((_OWORD **)&v38 + 1) = 0;
        *(_QWORD *)(v19 + 16) = 0;
        *(_QWORD *)(v19 + 24) = 0;
        *(_OWORD *)v19 = *(_OWORD *)v18;
        *(_OWORD *)(v19 + 16) = *(_OWORD *)(v18 + 16);
        *(_WORD *)v18 = 0;
        *(_QWORD *)(v18 + 16) = 0;
        *(_QWORD *)(v18 + 24) = 7;
        *((_QWORD *)&v38 + 1) += 32LL;
      }
      std::wstring::~wstring(&v32);
      v20 = wil::ExpandEnvironmentStringsW<std::wstring,256>(v37, L"%ProgramData%\\USOPrivate\\Providers\\Windows");
      v21 = *((_QWORD *)&v38 + 1);
      if ( *((_QWORD *)&v38 + 1) == v39 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v38, *((_QWORD *)&v38 + 1), v20);
      }
      else
      {
        **((_OWORD **)&v38 + 1) = 0;
        *(_QWORD *)(v21 + 16) = 0;
        *(_QWORD *)(v21 + 24) = 0;
        *(_OWORD *)v21 = *(_OWORD *)v20;
        *(_OWORD *)(v21 + 16) = *(_OWORD *)(v20 + 16);
        *(_WORD *)v20 = 0;
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 7;
        *((_QWORD *)&v38 + 1) += 32LL;
      }
      std::wstring::~wstring(v37);
    }
    v22 = qword_180150DD8;
    qword_180150DD8 = v38;
    *(_QWORD *)&v38 = v22;
    v23 = qword_180150DE0;
    qword_180150DE0 = *((_QWORD *)&v38 + 1);
    *((_QWORD *)&v38 + 1) = v23;
    v24 = qword_180150DE8;
    qword_180150DE8 = v39;
    v39 = v24;
    if ( v34 )
      CoTaskMemFree(v34);
    std::vector<std::wstring>::_Tidy(&v38);
  }
  if ( &stru_1801508E0 )
    LeaveCriticalSection(&stru_1801508E0);
  pszPathIn[0] = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    pszPathIn,
    a3);
  memset(pszPathOut, 0, 0x208u);
  v25 = PathCchCanonicalize(pszPathOut, 0x104u, pszPathIn[0]);
  if ( v25 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
      (const char *)(unsigned int)v25,
      v31);
  v26 = qword_180150DD8;
  v27 = qword_180150DE0;
  v28 = 1;
  while ( v26 != v27 )
  {
    v29 = (const wchar_t *)v26;
    if ( *(_QWORD *)(v26 + 24) > 7u )
      v29 = *(const wchar_t **)v26;
    if ( !wcsnicmp(v29, pszPathOut, *(_QWORD *)(v26 + 16)) )
    {
      v28 = 0;
      break;
    }
    v26 += 32;
  }
  LOBYTE(v31) = v28;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x3D,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
    (const char *)0x80070057LL,
    v31,
    (bool)"Caller: %ws Cmdline: %ws",
    a2,
    pszPathOut,
    (_QWORD)v32);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  do
    ++v6;
  while ( pszPathOut[v6] );
  std::wstring::_Construct<1,wchar_t const *>(a1, pszPathOut, v6);
  if ( pszPathIn[0] )
    CoTaskMemFree((LPVOID)pszPathIn[0]);
  return a1;
}

```

## disassembly

```asm
0x180080dd0  mov     [rsp-8+arg_18], rbx
0x180080dd5  push    rbp
0x180080dd6  push    rsi
0x180080dd7  push    rdi
0x180080dd8  push    r12
0x180080dda  push    r13
0x180080ddc  push    r14
0x180080dde  push    r15
0x180080de0  lea     rbp, [rsp-3F0h]
0x180080de8  sub     rsp, 4F0h
0x180080def  mov     rax, cs:__security_cookie
0x180080df6  xor     rax, rsp
0x180080df9  mov     [rbp+420h+var_40], rax
0x180080e00  mov     rsi, r8
0x180080e03  mov     r12, rdx
0x180080e06  mov     r15, rcx
0x180080e09  mov     [rsp+520h+pv], rcx
0x180080e0e  xor     r13d, r13d
0x180080e11  lea     rbx, stru_1801508E0
0x180080e18  mov     rcx, rbx; lpCriticalSection
0x180080e1b  call    cs:__imp_EnterCriticalSection
0x180080e21  mov     [rbp+420h+var_4A0], rbx
0x180080e25  mov     rax, cs:qword_180150DE0
0x180080e2c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180080e30  cmp     rax, cs:qword_180150DD8
0x180080e37  jnz     loc_180081226
0x180080e3d  xor     edx, edx; Val
0x180080e3f  mov     r8d, 208h; Size
0x180080e45  lea     rcx, [rbp+420h+Buffer]; void *
0x180080e4c  call    memset
0x180080e51  mov     rdi, [rbp+428h]
0x180080e58  mov     edx, 104h; uSize
0x180080e5d  lea     rcx, [rbp+420h+Buffer]; lpBuffer
0x180080e64  call    cs:__imp_GetSystemDirectoryW
0x180080e6a  test    eax, eax
0x180080e6c  jz      loc_180081378
0x180080e72  xorps   xmm0, xmm0
0x180080e75  xorps   xmm1, xmm1
0x180080e78  movdqu  [rbp+420h+var_478], xmm1
0x180080e7d  mov     [rbp+420h+var_468], r13
0x180080e81  movups  [rsp+520h+var_4E0], xmm0
0x180080e86  movdqu  [rsp+520h+var_4D0], xmm1
0x180080e8c  lea     rax, [rbp+420h+Buffer]
0x180080e93  mov     r8, r14
0x180080e96  inc     r8
0x180080e99  cmp     [rax+r8*2], r13w
0x180080e9e  jnz     short loc_180080E96
0x180080ea0  lea     rdx, [rbp+420h+Buffer]
0x180080ea7  lea     rcx, [rsp+520h+var_4E0]
0x180080eac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180080eb1  nop
0x180080eb2  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x180080eb6  cmp     rdx, [rbp+420h+var_468]
0x180080eba  jz      short loc_180080EE8
0x180080ebc  movups  xmm0, [rsp+520h+var_4E0]
0x180080ec1  movups  xmmword ptr [rdx], xmm0
0x180080ec4  movups  xmm1, [rsp+520h+var_4D0]
0x180080ec9  movups  xmmword ptr [rdx+10h], xmm1
0x180080ecd  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180080ed5  movdqu  [rsp+520h+var_4D0], xmm0
0x180080edb  mov     word ptr [rsp+520h+var_4E0], r13w
0x180080ee1  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x180080ee6  jmp     short loc_180080EF7
0x180080ee8  lea     r8, [rsp+520h+var_4E0]
0x180080eed  lea     rcx, [rbp+420h+var_478]
0x180080ef1  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180080ef6  nop
0x180080ef7  lea     rcx, [rsp+520h+var_4E0]; void *
0x180080efc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080f01  mov     [rsp+520h+var_4C0], r13
0x180080f06  lea     rdx, aCommonprogramf; "%CommonProgramFiles%"
0x180080f0d  lea     rcx, [rsp+520h+var_4C0]
0x180080f12  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180080f17  nop
0x180080f18  xorps   xmm0, xmm0
0x180080f1b  movups  [rsp+520h+var_4E0], xmm0
0x180080f20  xorps   xmm1, xmm1
0x180080f23  movdqu  [rsp+520h+var_4D0], xmm1
0x180080f29  mov     rdx, [rsp+520h+var_4C0]
0x180080f2e  mov     r8, r14
0x180080f31  inc     r8
0x180080f34  cmp     [rdx+r8*2], r13w
0x180080f39  jnz     short loc_180080F31
0x180080f3b  lea     rcx, [rsp+520h+var_4E0]
0x180080f40  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180080f45  nop
0x180080f46  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x180080f4a  cmp     rdx, [rbp+420h+var_468]
0x180080f4e  jz      short loc_180080F7C
0x180080f50  movups  xmm0, [rsp+520h+var_4E0]
0x180080f55  movups  xmmword ptr [rdx], xmm0
0x180080f58  movups  xmm1, [rsp+520h+var_4D0]
0x180080f5d  movups  xmmword ptr [rdx+10h], xmm1
0x180080f61  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180080f69  movdqu  [rsp+520h+var_4D0], xmm0
0x180080f6f  mov     word ptr [rsp+520h+var_4E0], r13w
0x180080f75  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x180080f7a  jmp     short loc_180080F8B
0x180080f7c  lea     r8, [rsp+520h+var_4E0]
0x180080f81  lea     rcx, [rbp+420h+var_478]
0x180080f85  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180080f8a  nop
0x180080f8b  lea     rcx, [rsp+520h+var_4E0]; void *
0x180080f90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180080f95  lea     rdx, aProgramfilesMi; "%ProgramFiles%\\Microsoft"
0x180080f9c  lea     rcx, [rsp+520h+pv]
0x180080fa1  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180080fa6  mov     rdx, rax
0x180080fa9  lea     rcx, [rsp+520h+var_4C0]
0x180080fae  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x180080fb3  mov     rcx, [rsp+520h+pv]; pv
0x180080fb8  test    rcx, rcx
0x180080fbb  jz      short loc_180080FC3
0x180080fbd  call    cs:__imp_CoTaskMemFree
0x180080fc3  xorps   xmm0, xmm0
0x180080fc6  movups  [rsp+520h+var_4E0], xmm0
0x180080fcb  xorps   xmm1, xmm1
0x180080fce  movdqu  [rsp+520h+var_4D0], xmm1
0x180080fd4  mov     rdx, [rsp+520h+var_4C0]
0x180080fd9  mov     r8, r14
0x180080fdc  inc     r8
0x180080fdf  cmp     [rdx+r8*2], r13w
0x180080fe4  jnz     short loc_180080FDC
0x180080fe6  lea     rcx, [rsp+520h+var_4E0]
0x180080feb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180080ff0  nop
0x180080ff1  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x180080ff5  cmp     rdx, [rbp+420h+var_468]
0x180080ff9  jz      short loc_180081027
0x180080ffb  movups  xmm0, [rsp+520h+var_4E0]
0x180081000  movups  xmmword ptr [rdx], xmm0
0x180081003  movups  xmm1, [rsp+520h+var_4D0]
0x180081008  movups  xmmword ptr [rdx+10h], xmm1
0x18008100c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180081014  movdqu  [rsp+520h+var_4D0], xmm0
0x18008101a  mov     word ptr [rsp+520h+var_4E0], r13w
0x180081020  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x180081025  jmp     short loc_180081036
0x180081027  lea     r8, [rsp+520h+var_4E0]
0x18008102c  lea     rcx, [rbp+420h+var_478]
0x180081030  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x180081035  nop
0x180081036  lea     rcx, [rsp+520h+var_4E0]; void *
0x18008103b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081040  lea     rdx, aProgramfilesX8; "%ProgramFiles(x86)%\\Microsoft"
0x180081047  lea     rcx, [rsp+520h+pv]
0x18008104c  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180081051  mov     rdx, rax
0x180081054  lea     rcx, [rsp+520h+var_4C0]
0x180081059  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x18008105e  mov     rcx, [rsp+520h+pv]; pv
0x180081063  test    rcx, rcx
0x180081066  jz      short loc_18008106E
0x180081068  call    cs:__imp_CoTaskMemFree
0x18008106e  xorps   xmm0, xmm0
0x180081071  movups  [rsp+520h+var_4E0], xmm0
0x180081076  xorps   xmm1, xmm1
0x180081079  movdqu  [rsp+520h+var_4D0], xmm1
0x18008107f  mov     rdx, [rsp+520h+var_4C0]
0x180081084  mov     r8, r14
0x180081087  inc     r8
0x18008108a  cmp     [rdx+r8*2], r13w
0x18008108f  jnz     short loc_180081087
0x180081091  lea     rcx, [rsp+520h+var_4E0]
0x180081096  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18008109b  nop
0x18008109c  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x1800810a0  cmp     rdx, [rbp+420h+var_468]
0x1800810a4  jz      short loc_1800810D2
0x1800810a6  movups  xmm0, [rsp+520h+var_4E0]
0x1800810ab  movups  xmmword ptr [rdx], xmm0
0x1800810ae  movups  xmm1, [rsp+520h+var_4D0]
0x1800810b3  movups  xmmword ptr [rdx+10h], xmm1
0x1800810b7  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800810bf  movdqu  [rsp+520h+var_4D0], xmm0
0x1800810c5  mov     word ptr [rsp+520h+var_4E0], r13w
0x1800810cb  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x1800810d0  jmp     short loc_1800810E1
0x1800810d2  lea     r8, [rsp+520h+var_4E0]
0x1800810d7  lea     rcx, [rbp+420h+var_478]
0x1800810db  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800810e0  nop
0x1800810e1  lea     rcx, [rsp+520h+var_4E0]; void *
0x1800810e6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800810eb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x1800810f2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x1800810f7  test    al, al
0x1800810f9  jz      loc_1800811C9
0x1800810ff  lea     rdx, aProgramdataUso; "%ProgramData%\\USOPrivate\\Providers\\R"...
0x180081106  lea     rcx, [rsp+520h+var_4E0]
0x18008110b  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x180081110  nop
0x180081111  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x180081115  cmp     rdx, [rbp+420h+var_468]
0x180081119  jz      short loc_18008114E
0x18008111b  xorps   xmm0, xmm0
0x18008111e  movups  xmmword ptr [rdx], xmm0
0x180081121  mov     [rdx+10h], r13
0x180081125  mov     [rdx+18h], r13
0x180081129  movups  xmm0, xmmword ptr [rax]
0x18008112c  movups  xmmword ptr [rdx], xmm0
0x18008112f  movups  xmm1, xmmword ptr [rax+10h]
0x180081133  movups  xmmword ptr [rdx+10h], xmm1
0x180081137  mov     [rax], r13w
0x18008113b  mov     [rax+10h], r13
0x18008113f  mov     qword ptr [rax+18h], 7
0x180081147  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x18008114c  jmp     short loc_18008115B
0x18008114e  mov     r8, rax
0x180081151  lea     rcx, [rbp+420h+var_478]
0x180081155  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x18008115a  nop
0x18008115b  lea     rcx, [rsp+520h+var_4E0]; void *
0x180081160  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180081165  lea     rdx, aProgramdataUso_9; "%ProgramData%\\USOPrivate\\Providers\\W"...
0x18008116c  lea     rcx, [rbp+420h+var_498]
0x180081170  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x180081175  nop
0x180081176  mov     rdx, qword ptr [rbp+420h+var_478+8]
0x18008117a  cmp     rdx, [rbp+420h+var_468]
0x18008117e  jz      short loc_1800811B3
0x180081180  xorps   xmm0, xmm0
0x180081183  movups  xmmword ptr [rdx], xmm0
0x180081186  mov     [rdx+10h], r13
0x18008118a  mov     [rdx+18h], r13
0x18008118e  movups  xmm0, xmmword ptr [rax]
0x180081191  movups  xmmword ptr [rdx], xmm0
0x180081194  movups  xmm1, xmmword ptr [rax+10h]
0x180081198  movups  xmmword ptr [rdx+10h], xmm1
0x18008119c  mov     [rax], r13w
0x1800811a0  mov     [rax+10h], r13
0x1800811a4  mov     qword ptr [rax+18h], 7
0x1800811ac  add     qword ptr [rbp+420h+var_478+8], 20h ; ' '
0x1800811b1  jmp     short loc_1800811C0
0x1800811b3  mov     r8, rax
0x1800811b6  lea     rcx, [rbp+420h+var_478]
0x1800811ba  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1800811bf  nop
0x1800811c0  lea     rcx, [rbp+420h+var_498]; void *
0x1800811c4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800811c9  mov     rcx, cs:qword_180150DD8
0x1800811d0  mov     rax, qword ptr [rbp+420h+var_478]
0x1800811d4  mov     cs:qword_180150DD8, rax
0x1800811db  mov     qword ptr [rbp+420h+var_478], rcx
0x1800811df  mov     rcx, cs:qword_180150DE0
0x1800811e6  mov     rax, qword ptr [rbp+420h+var_478+8]
0x1800811ea  mov     cs:qword_180150DE0, rax
0x1800811f1  mov     qword ptr [rbp+420h+var_478+8], rcx
0x1800811f5  mov     rcx, cs:qword_180150DE8
0x1800811fc  mov     rax, [rbp+420h+var_468]
0x180081200  mov     cs:qword_180150DE8, rax
0x180081207  mov     [rbp+420h+var_468], rcx
0x18008120b  mov     rcx, [rsp+520h+var_4C0]; pv
0x180081210  test    rcx, rcx
0x180081213  jz      short loc_18008121C
0x180081215  call    cs:__imp_CoTaskMemFree
0x18008121b  nop
0x18008121c  lea     rcx, [rbp+420h+var_478]
0x180081220  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180081225  nop
0x180081226  test    rbx, rbx
0x180081229  jz      short loc_180081234
0x18008122b  mov     rcx, rbx; lpCriticalSection
0x18008122e  call    cs:__imp_LeaveCriticalSection
0x180081234  mov     [rsp+520h+pszPathIn], r13
0x180081239  mov     rdx, rsi
0x18008123c  lea     rcx, [rsp+520h+pszPathIn]
0x180081241  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x180081246  nop
0x180081247  xor     edx, edx; Val
0x180081249  mov     r8d, 208h; Size
0x18008124f  lea     rcx, [rbp+420h+pszPathOut]; void *
0x180081253  call    memset
0x180081258  mov     r8, [rsp+520h+pszPathIn]; pszPathIn
0x18008125d  mov     edx, 104h; cchPathOut
0x180081262  lea     rcx, [rbp+420h+pszPathOut]; pszPathOut
0x180081266  call    cs:__imp_PathCchCanonicalize
0x18008126c  mov     rcx, [rbp+428h]; this
0x180081273  test    eax, eax
0x180081275  js      loc_180081363
0x18008127b  mov     rbx, cs:qword_180150DD8
0x180081282  mov     rsi, cs:qword_180150DE0
0x180081289  mov     edi, 1
0x18008128e  jmp     short loc_1800812B2
0x180081290  mov     rcx, rbx
0x180081293  cmp     qword ptr [rbx+18h], 7
0x180081298  jbe     short loc_18008129D
0x18008129a  mov     rcx, [rbx]; String1
0x18008129d  mov     r8, [rbx+10h]; MaxCount
0x1800812a1  lea     rdx, [rbp+420h+pszPathOut]; String2
0x1800812a5  call    _wcsnicmp
0x1800812aa  test    eax, eax
0x1800812ac  jz      short loc_1800812B9
0x1800812ae  add     rbx, 20h ; ' '
0x1800812b2  cmp     rbx, rsi
0x1800812b5  jnz     short loc_180081290
0x1800812b7  jmp     short loc_1800812BC
0x1800812b9  mov     edi, r13d
0x1800812bc  mov     rcx, [rbp+428h]; this
0x1800812c3  lea     rax, [rbp+420h+pszPathOut]
  ... truncated ...
```
