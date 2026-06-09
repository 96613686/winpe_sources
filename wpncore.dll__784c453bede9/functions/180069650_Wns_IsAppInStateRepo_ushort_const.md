# Wns::IsAppInStateRepo(ushort const *)

- ea: `0x180069650`
- end: `0x180069bee`
- name: `?IsAppInStateRepo@Wns@@YA_NPEBG@Z`
- size: `1438`
- prototype: `bool __fastcall(Wns *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180069404`

## callees

- `0x180004e38`
- `0x18000de40`
- `0x18000e5f4`
- `0x180024614`
- `0x180069650`
- `0x180069bf4`
- `0x180069c30`
- `0x180069c7c`
- `0x1800b99f0`
- `0x180118010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006994b`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006994b`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180069684`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180069684`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069749`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069bd4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069be7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069749`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069bd4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180069be7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069ba3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069a0b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180069ba3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800696e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800696e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180069794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006995d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069918`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006995d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180069a3f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006993f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18006993f`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
char __fastcall Wns::IsAppInStateRepo(const wchar_t *this, const unsigned __int16 *a2)
{
  wchar_t *v3; // rax
  int v4; // eax
  wil::details::in1diag3 *v5; // rcx
  HRESULT v6; // eax
  int v7; // eax
  _QWORD *v8; // rdi
  __int64 v9; // r14
  WCHAR *v10; // rsi
  unsigned __int64 v11; // rbx
  unsigned int v12; // eax
  UINT32 v13; // edx
  HRESULT v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  const unsigned __int16 *v18; // rdx
  _QWORD *v19; // rax
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, __int64, __int64 *); // rbx
  int v23; // eax
  int v24; // eax
  unsigned int v25; // edx
  unsigned int i; // r14d
  __int64 v27; // rdi
  int (__fastcall *v28)(__int64, _QWORD, __int64 *); // rbx
  __int64 v29; // rdi
  int (__fastcall *v30)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v32; // rcx
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  _QWORD *v37; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  _QWORD *v44; // rcx
  int v45; // [rsp+20h] [rbp-69h]
  __int64 v46; // [rsp+30h] [rbp-59h] BYREF
  int v47[2]; // [rsp+38h] [rbp-51h] BYREF
  unsigned int v48; // [rsp+40h] [rbp-49h] BYREF
  __int64 v49; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v50; // [rsp+50h] [rbp-39h] BYREF
  __int64 v51; // [rsp+58h] [rbp-31h] BYREF
  __int64 v52; // [rsp+60h] [rbp-29h] BYREF
  _QWORD *v53; // [rsp+68h] [rbp-21h] BYREF
  int v54; // [rsp+70h] [rbp-19h] BYREF
  PCWSTR sourceString[3]; // [rsp+78h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp+7h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v3 = wcschr(this, 0x21u);
  if ( !v3 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x44,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)0x80070490LL,
      v45);
  memset(sourceString, 0, sizeof(sourceString));
  v4 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
         sourceString,
         this,
         v3 - this);
  v5 = retaddr;
  if ( v4 < 0 )
LABEL_9:
    wil::details::in1diag3::Throw_Hr(
      v5,
      (void *)0x46,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v4,
      v45);
  v53 = 0;
  string = 0;
  v6 = WindowsCreateStringReference(L"Windows.Internal.StateRepository.Package", 0x28u, &hstringHeader, &string);
  if ( v6 < 0 )
  {
    RaiseException(v6, 1u, 0, 0);
    goto LABEL_69;
  }
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         string,
         &v53);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v7,
      v45);
  *(_QWORD *)v47 = 0;
  v8 = v53;
  v9 = *v53;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v47);
  string = 0;
  v10 = (WCHAR *)sourceString[0];
  v11 = -1;
  do
    ++v11;
  while ( sourceString[0][v11] );
  if ( v11 > 0xFFFFFFFF )
  {
    RaiseException(0x80070216, 1u, 0, 0);
    goto LABEL_9;
  }
  v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
  v13 = v12 - 1;
  if ( (unsigned int)v11 < v12 )
    v13 = v11;
  v14 = WindowsCreateStringReference(v10, v13, &hstringHeader, &string);
  if ( v14 < 0 )
  {
LABEL_69:
    RaiseException(v14, 1u, 0, 0);
    JUMPOUT(0x180069BEDLL);
  }
  v15 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, HSTRING, __int64))(v9 + 424))(v8, 0, string, 49);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x50,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v15,
      (int)v47);
  v54 = 0;
  v16 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v47 + 56LL))(*(_QWORD *)v47, &v54);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v16,
      (int)v47);
  if ( v54 != 1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x54,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)v47);
  v52 = 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v47 + 48LL))(*(_QWORD *)v47, 0, &v52);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v17,
      (int)v47);
  v51 = 0;
  v19 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                    (HSTRING *)&hstringHeader,
                    (const unsigned __int16 (*)[45])v18);
  v20 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
          *v19,
          &v51);
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v20,
      (int)v47);
  v46 = 0;
  v21 = v51;
  v22 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v51 + 144LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v46);
  v23 = v22(v21, v52, &v46);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v23,
      (int)v47);
  v48 = 0;
  v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v46 + 56LL))(v46, &v48);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v24,
      (int)v47);
  v25 = v48;
  if ( !v48 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)v47);
  for ( i = 0; i < v25; ++i )
  {
    v49 = 0;
    v27 = v46;
    v28 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v46 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    if ( v28(v27, i, &v49) >= 0 )
    {
      v50 = 0;
      v29 = v49;
      v30 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v49 + 232LL);
      WindowsDeleteString(0);
      v50 = 0;
      if ( v30(v29, &v50) >= 0 )
      {
        StringRawBuffer = WindowsGetStringRawBuffer(v50, 0);
        if ( !(unsigned int)_o__wcsicmp(StringRawBuffer, this) )
        {
          WindowsDeleteString(v50);
          v50 = 0;
          v32 = v49;
          if ( v49 )
          {
            v49 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
          }
          v33 = v46;
          if ( v46 )
          {
            v46 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          v34 = v51;
          if ( v51 )
          {
            v51 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
          v35 = v52;
          if ( v52 )
          {
            v52 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = *(_QWORD *)v47;
          if ( *(_QWORD *)v47 )
          {
            *(_QWORD *)v47 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
          v37 = v53;
          if ( v53 )
          {
            v53 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v37 + 16LL))(v37);
          }
          if ( v10 )
            CoTaskMemFree(v10);
          return 1;
        }
      }
      WindowsDeleteString(v50);
    }
    v39 = v49;
    if ( v49 )
    {
      v49 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
    v25 = v48;
  }
  v40 = v46;
  if ( v46 )
  {
    v46 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  }
  v41 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  }
  v42 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  }
  v43 = *(_QWORD *)v47;
  if ( *(_QWORD *)v47 )
  {
    *(_QWORD *)v47 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
  v44 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v44 + 16LL))(v44);
  }
  if ( v10 )
    CoTaskMemFree(v10);
  return 0;
}

```

## disassembly

```asm
0x180069650  mov     [rsp-8+arg_8], rbx
0x180069655  mov     [rsp-8+arg_10], rsi
0x18006965a  push    rbp
0x18006965b  push    rdi
0x18006965c  push    r12
0x18006965e  push    r14
0x180069660  push    r15
0x180069662  lea     rbp, [rsp-37h]
0x180069667  sub     rsp, 0C0h
0x18006966e  mov     rax, cs:__security_cookie
0x180069675  xor     rax, rsp
0x180069678  mov     [rbp+57h+var_30], rax
0x18006967c  mov     r15, rcx
0x18006967f  mov     edx, 21h ; '!'; Ch
0x180069684  call    cs:__imp_wcschr
0x18006968a  mov     rcx, [rbp+5Fh]; this
0x18006968e  xor     r12d, r12d
0x180069691  test    rax, rax
0x180069694  jz      loc_180069BB0
0x18006969a  mov     [rbp+57h+sourceString], r12
0x18006969e  mov     [rbp+57h+var_60], r12
0x1800696a2  mov     [rbp+57h+var_58], r12
0x1800696a6  sub     rax, r15
0x1800696a9  sar     rax, 1
0x1800696ac  mov     r8, rax
0x1800696af  mov     rdx, r15
0x1800696b2  lea     rcx, [rbp+57h+sourceString]
0x1800696b6  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x1800696bb  mov     rcx, [rbp+5Fh]
0x1800696bf  test    eax, eax
0x1800696c1  js      loc_180069750
0x1800696c7  mov     [rbp+57h+var_78], r12
0x1800696cb  mov     [rbp+57h+string], r12
0x1800696cf  lea     r9, [rbp+57h+string]; string
0x1800696d3  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800696d7  lea     edx, [r12+28h]; length
0x1800696dc  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800696e3  call    cs:__imp_WindowsCreateStringReference
0x1800696e9  test    eax, eax
0x1800696eb  js      loc_180069BC8
0x1800696f1  lea     rdx, [rbp+57h+var_78]
0x1800696f5  mov     rcx, [rbp+57h+string]
0x1800696f9  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800696fe  mov     rcx, [rbp+5Fh]; this
0x180069702  test    eax, eax
0x180069704  js      short loc_180069765
0x180069706  mov     qword ptr [rbp+57h+var_A8], r12
0x18006970a  mov     rdi, [rbp+57h+var_78]
0x18006970e  mov     r14, [rdi]
0x180069711  lea     rcx, [rbp+57h+var_A8]
0x180069715  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006971a  mov     [rbp+57h+string], r12
0x18006971e  mov     rsi, [rbp+57h+sourceString]
0x180069722  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180069726  inc     rbx
0x180069729  cmp     [rsi+rbx*2], r12w
0x18006972e  jnz     short loc_180069726
0x180069730  mov     eax, 0FFFFFFFFh
0x180069735  cmp     rbx, rax
0x180069738  jbe     short loc_18006977A
0x18006973a  xor     r9d, r9d; lpArguments
0x18006973d  xor     r8d, r8d; nNumberOfArguments
0x180069740  lea     edx, [r9+1]; dwExceptionFlags
0x180069744  mov     ecx, 80070216h; dwExceptionCode
0x180069749  call    cs:__imp_RaiseException
0x18006974f  nop
0x180069750  mov     r9d, eax; char *
0x180069753  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006975a  mov     edx, 46h ; 'F'; void *
0x18006975f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069765  mov     r9d, eax; char *
0x180069768  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x18006976f  mov     edx, 49h ; 'I'; void *
0x180069774  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006977a  mov     ecx, ebx; unsigned int
0x18006977c  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180069781  lea     edx, [rax-1]
0x180069784  cmp     ebx, eax
0x180069786  cmovb   edx, ebx; length
0x180069789  lea     r9, [rbp+57h+string]; string
0x18006978d  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180069791  mov     rcx, rsi; sourceString
0x180069794  call    cs:__imp_WindowsCreateStringReference
0x18006979a  test    eax, eax
0x18006979c  js      loc_180069BDB
0x1800697a2  lea     rax, [rbp+57h+var_A8]
0x1800697a6  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1800697ab  mov     r9d, 31h ; '1'
0x1800697b1  mov     r8, [rbp+57h+string]
0x1800697b5  xor     edx, edx
0x1800697b7  mov     rcx, rdi
0x1800697ba  mov     rax, [r14+1A8h]
0x1800697c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697c6  mov     rcx, [rbp+5Fh]; this
0x1800697ca  test    eax, eax
0x1800697cc  js      loc_180069A9B
0x1800697d2  mov     [rbp+57h+var_70], r12d
0x1800697d6  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800697da  mov     rax, [rcx]
0x1800697dd  lea     rdx, [rbp+57h+var_70]
0x1800697e1  mov     rax, [rax+38h]
0x1800697e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800697ea  mov     rcx, [rbp+5Fh]; this
0x1800697ee  test    eax, eax
0x1800697f0  js      loc_180069AB0
0x1800697f6  cmp     [rbp+57h+var_70], 1
0x1800697fa  setz    al
0x1800697fd  mov     rcx, [rbp+5Fh]; this
0x180069801  test    al, al
0x180069803  jz      loc_180069A83
0x180069809  mov     [rbp+57h+var_80], r12
0x18006980d  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180069811  mov     rax, [rcx]
0x180069814  lea     r8, [rbp+57h+var_80]
0x180069818  xor     edx, edx
0x18006981a  mov     rax, [rax+30h]
0x18006981e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069823  mov     rcx, [rbp+5Fh]; this
0x180069827  test    eax, eax
0x180069829  js      loc_180069AC5
0x18006982f  mov     [rbp+57h+var_88], r12
0x180069833  lea     rcx, [rbp+57h+hstringHeader]; string
0x180069837  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x18006983c  lea     rdx, [rbp+57h+var_88]
0x180069840  mov     rcx, [rax]
0x180069843  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x180069848  mov     rcx, [rbp+5Fh]; this
0x18006984c  test    eax, eax
0x18006984e  js      loc_180069ADA
0x180069854  mov     [rbp+57h+var_B0], r12
0x180069858  mov     rdi, [rbp+57h+var_88]
0x18006985c  mov     rax, [rdi]
0x18006985f  mov     rbx, [rax+90h]
0x180069866  lea     rcx, [rbp+57h+var_B0]
0x18006986a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006986f  lea     r8, [rbp+57h+var_B0]
0x180069873  mov     rdx, [rbp+57h+var_80]
0x180069877  mov     rcx, rdi
0x18006987a  mov     rax, rbx
0x18006987d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069882  mov     rcx, [rbp+5Fh]; this
0x180069886  test    eax, eax
0x180069888  js      loc_180069AEF
0x18006988e  mov     [rbp+57h+var_A0], r12d
0x180069892  mov     rcx, [rbp+57h+var_B0]
0x180069896  mov     rax, [rcx]
0x180069899  lea     rdx, [rbp+57h+var_A0]
0x18006989d  mov     rax, [rax+38h]
0x1800698a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698a6  mov     rcx, [rbp+5Fh]; this
0x1800698aa  test    eax, eax
0x1800698ac  js      loc_180069B04
0x1800698b2  mov     edx, [rbp+57h+var_A0]
0x1800698b5  test    edx, edx
0x1800698b7  setz    al
0x1800698ba  mov     rcx, [rbp+5Fh]; this
0x1800698be  test    al, al
0x1800698c0  jnz     loc_180069A6B
0x1800698c6  mov     r14d, r12d
0x1800698c9  cmp     r14d, edx
0x1800698cc  jnb     loc_180069B19
0x1800698d2  mov     [rbp+57h+var_98], r12
0x1800698d6  mov     rdi, [rbp+57h+var_B0]
0x1800698da  mov     rax, [rdi]
0x1800698dd  mov     rbx, [rax+30h]
0x1800698e1  lea     rcx, [rbp+57h+var_98]
0x1800698e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800698ea  lea     r8, [rbp+57h+var_98]
0x1800698ee  mov     edx, r14d
0x1800698f1  mov     rcx, rdi
0x1800698f4  mov     rax, rbx
0x1800698f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800698fc  test    eax, eax
0x1800698fe  js      loc_180069A46
0x180069904  mov     [rbp+57h+var_90], r12
0x180069908  mov     rdi, [rbp+57h+var_98]
0x18006990c  mov     rax, [rdi]
0x18006990f  mov     rbx, [rax+0E8h]
0x180069916  xor     ecx, ecx; string
0x180069918  call    cs:__imp_WindowsDeleteString
0x18006991e  mov     [rbp+57h+var_90], r12
0x180069922  lea     rdx, [rbp+57h+var_90]
0x180069926  mov     rcx, rdi
0x180069929  mov     rax, rbx
0x18006992c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069931  test    eax, eax
0x180069933  js      loc_180069A3B
0x180069939  xor     edx, edx; length
0x18006993b  mov     rcx, [rbp+57h+var_90]; string
0x18006993f  call    cs:__imp_WindowsGetStringRawBuffer
0x180069945  mov     rdx, r15
0x180069948  mov     rcx, rax
0x18006994b  call    cs:__imp__o__wcsicmp
0x180069951  test    eax, eax
0x180069953  jnz     loc_180069A3B
0x180069959  mov     rcx, [rbp+57h+var_90]; string
0x18006995d  call    cs:__imp_WindowsDeleteString
0x180069963  mov     [rbp+57h+var_90], r12
0x180069967  mov     rcx, [rbp+57h+var_98]
0x18006996b  test    rcx, rcx
0x18006996e  jz      short loc_180069981
0x180069970  mov     [rbp+57h+var_98], r12
0x180069974  mov     rax, [rcx]
0x180069977  mov     rax, [rax+10h]
0x18006997b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069980  nop
0x180069981  mov     rcx, [rbp+57h+var_B0]
0x180069985  test    rcx, rcx
0x180069988  jz      short loc_18006999B
0x18006998a  mov     [rbp+57h+var_B0], r12
0x18006998e  mov     rax, [rcx]
0x180069991  mov     rax, [rax+10h]
0x180069995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006999a  nop
0x18006999b  mov     rcx, [rbp+57h+var_88]
0x18006999f  test    rcx, rcx
0x1800699a2  jz      short loc_1800699B5
0x1800699a4  mov     [rbp+57h+var_88], r12
0x1800699a8  mov     rax, [rcx]
0x1800699ab  mov     rax, [rax+10h]
0x1800699af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699b4  nop
0x1800699b5  mov     rcx, [rbp+57h+var_80]
0x1800699b9  test    rcx, rcx
0x1800699bc  jz      short loc_1800699CF
0x1800699be  mov     [rbp+57h+var_80], r12
0x1800699c2  mov     rax, [rcx]
0x1800699c5  mov     rax, [rax+10h]
0x1800699c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699ce  nop
0x1800699cf  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800699d3  test    rcx, rcx
0x1800699d6  jz      short loc_1800699E9
0x1800699d8  mov     qword ptr [rbp+57h+var_A8], r12
0x1800699dc  mov     rax, [rcx]
0x1800699df  mov     rax, [rax+10h]
0x1800699e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699e8  nop
0x1800699e9  mov     rcx, [rbp+57h+var_78]
0x1800699ed  test    rcx, rcx
0x1800699f0  jz      short loc_180069A03
0x1800699f2  mov     [rbp+57h+var_78], r12
0x1800699f6  mov     rax, [rcx]
0x1800699f9  mov     rax, [rax+10h]
0x1800699fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a02  nop
0x180069a03  test    rsi, rsi
0x180069a06  jz      short loc_180069A11
0x180069a08  mov     rcx, rsi; pv
0x180069a0b  call    cs:__imp_CoTaskMemFree
0x180069a11  mov     al, 1
0x180069a13  mov     rcx, [rbp+57h+var_30]
0x180069a17  xor     rcx, rsp; StackCookie
0x180069a1a  call    __security_check_cookie
0x180069a1f  lea     r11, [rsp+0E0h+var_20]
0x180069a27  mov     rbx, [r11+38h]
0x180069a2b  mov     rsi, [r11+40h]
0x180069a2f  mov     rsp, r11
0x180069a32  pop     r15
0x180069a34  pop     r14
0x180069a36  pop     r12
0x180069a38  pop     rdi
0x180069a39  pop     rbp
0x180069a3a  retn
0x180069a3b  mov     rcx, [rbp+57h+var_90]; string
0x180069a3f  call    cs:__imp_WindowsDeleteString
0x180069a45  nop
0x180069a46  mov     rcx, [rbp+57h+var_98]
0x180069a4a  test    rcx, rcx
0x180069a4d  jz      short loc_180069A60
0x180069a4f  mov     [rbp+57h+var_98], r12
0x180069a53  mov     rax, [rcx]
0x180069a56  mov     rax, [rax+10h]
0x180069a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a5f  nop
0x180069a60  inc     r14d
0x180069a63  mov     edx, [rbp+57h+var_A0]
0x180069a66  jmp     loc_1800698C9
0x180069a6b  mov     r9d, 8000FFFFh; char *
0x180069a71  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180069a78  mov     edx, 62h ; 'b'; void *
0x180069a7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069a83  mov     r9d, 8000FFFFh; char *
0x180069a89  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180069a90  mov     edx, 54h ; 'T'; void *
0x180069a95  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069a9b  mov     r9d, eax; char *
0x180069a9e  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180069aa5  mov     edx, 50h ; 'P'; void *
0x180069aaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069ab0  mov     r9d, eax; char *
0x180069ab3  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180069aba  mov     edx, 53h ; 'S'; void *
0x180069abf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069ac5  mov     r9d, eax; char *
0x180069ac8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180069acf  mov     edx, 57h ; 'W'; void *
0x180069ad4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180069ada  mov     r9d, eax; char *
0x180069add  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
  ... truncated ...
```
