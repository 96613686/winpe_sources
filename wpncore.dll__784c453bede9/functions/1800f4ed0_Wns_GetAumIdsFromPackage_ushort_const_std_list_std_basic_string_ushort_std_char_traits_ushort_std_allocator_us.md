# Wns::GetAumIdsFromPackage(ushort const *,std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x1800f4ed0`
- end: `0x1800f53f2`
- name: `?GetAumIdsFromPackage@Wns@@YAJPEBGAEAV?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180069cb8`

## callees

- `0x180004e38`
- `0x180011618`
- `0x1800117c0`
- `0x180014120`
- `0x180024844`
- `0x180069bf4`
- `0x180069c30`
- `0x180069c7c`
- `0x18006a3f0`
- `0x18008778c`
- `0x1800b99f0`
- `0x1800ec0ac`
- `0x1800f4ed0`
- `0x180118010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800f534f`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800f534f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f52bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f5223`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f52bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f5246`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800f5246`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Wns::GetAumIdsFromPackage(__int64 a1, __int64 *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, _QWORD, __int64); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rax
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, __int64 *); // rbx
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  unsigned int i; // esi
  __int64 v23; // rdi
  int (__fastcall *v24)(__int64, _QWORD, __int64 *); // rbx
  __int64 v25; // rdi
  int (__fastcall *v26)(__int64, HSTRING *); // rbx
  PCWSTR StringRawBuffer; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rcx
  __int64 v34; // rcx
  int v35; // [rsp+20h] [rbp-69h]
  __int64 v36; // [rsp+30h] [rbp-59h] BYREF
  int v37[2]; // [rsp+38h] [rbp-51h] BYREF
  __int64 v38; // [rsp+40h] [rbp-49h] BYREF
  __int64 v39; // [rsp+48h] [rbp-41h] BYREF
  unsigned int v40; // [rsp+50h] [rbp-39h] BYREF
  __int64 v41; // [rsp+58h] [rbp-31h] BYREF
  int v42; // [rsp+60h] [rbp-29h] BYREF
  __int64 v43; // [rsp+68h] [rbp-21h] BYREF
  HSTRING string; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF
  __int64 v46; // [rsp+90h] [rbp+7h]
  HSTRING v47[4]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v41 = a1;
  v43 = 0;
  v46 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.StateRepository.Package",
    0x29u,
    0x28u);
  v3 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(
         v46,
         &v43);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v3,
      v35);
LABEL_40:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    return v4;
  }
  *(_QWORD *)v37 = 0;
  v5 = v43;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v43 + 424LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &v41);
  v8 = v6(v5, 0, *(_QWORD *)(v7 + 24), 49);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 133;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)(unsigned int)v8,
      (int)v37);
LABEL_6:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
    goto LABEL_40;
  }
  v42 = 0;
  v8 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v37 + 56LL))(*(_QWORD *)v37, &v42);
  v4 = v8;
  if ( v8 < 0 )
  {
    v9 = 136;
    goto LABEL_5;
  }
  if ( v42 == 1 )
  {
    v36 = 0;
    v10 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64 *))(**(_QWORD **)v37 + 48LL))(*(_QWORD *)v37, 0, &v36);
    v4 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8C,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)(unsigned int)v10,
        (int)v37);
      v12 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      goto LABEL_6;
    }
    v39 = 0;
    v13 = (_QWORD *)Windows::Internal::StringReference::StringReference(v47, (const unsigned __int16 (*)[45])v11);
    v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(
            *v13,
            &v39);
    v4 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)(unsigned int)v14,
        (int)v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v15 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      goto LABEL_6;
    }
    v38 = 0;
    v16 = v39;
    v17 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 144LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    v18 = v17(v16, v36, &v38);
    v4 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x92,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)(unsigned int)v18,
        (int)v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v19 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      goto LABEL_6;
    }
    v40 = 0;
    v20 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 56LL))(v38, &v40);
    v4 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)(unsigned int)v20,
        (int)v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      v21 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      }
      goto LABEL_6;
    }
    if ( !v40 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x97,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)0x8000FFFFLL,
        (int)v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
LABEL_37:
      v32 = v36;
      if ( v36 )
      {
        v36 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
      v4 = -2147418113;
      goto LABEL_40;
    }
    for ( i = 0; i < v40; ++i )
    {
      v41 = 0;
      v23 = v38;
      v24 = *(int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v38 + 48LL);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      if ( v24(v23, i, &v41) >= 0 )
      {
        string = 0;
        v25 = v41;
        v26 = *(int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v41 + 232LL);
        WindowsDeleteString(0);
        string = 0;
        if ( v26(v25, &string) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v28 = std::wstring::wstring(v47, StringRawBuffer);
          if ( a2[1] == 0x555555555555555LL )
            std::_Xlength_error("list too long");
          v29 = *a2;
          std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(
            &hstringHeader,
            a2,
            v28);
          ++a2[1];
          v30 = *(_QWORD **)(v29 + 8);
          **(_QWORD **)&hstringHeader.Reserved.Reserved2[8] = v29;
          *(_QWORD *)(*(_QWORD *)&hstringHeader.Reserved.Reserved2[8] + 8LL) = v30;
          v31 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
          *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
          *(_QWORD *)(v29 + 8) = v31;
          *v30 = v31;
          std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(&hstringHeader);
          std::pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,enum __MIDL___MIDL_itf_wpntypes_0000_0000_0005>(v47);
        }
        WindowsDeleteString(string);
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
    }
    if ( v40 != a2[1] )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
        (const char *)0x8000FFFFLL,
        (int)v37);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
      goto LABEL_37;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v38);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v39);
    v34 = v36;
    if ( v36 )
    {
      v36 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\diagnosis\\platform\\notifications\\platform\\deployment\\registrationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      (int)v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v37);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v43);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x1800f4ed0  mov     [rsp-8+arg_10], rbx
0x1800f4ed5  push    rbp
0x1800f4ed6  push    rsi
0x1800f4ed7  push    rdi
0x1800f4ed8  push    r14
0x1800f4eda  push    r15
0x1800f4edc  lea     rbp, [rsp-37h]
0x1800f4ee1  sub     rsp, 0C0h
0x1800f4ee8  mov     rax, cs:__security_cookie
0x1800f4eef  xor     rax, rsp
0x1800f4ef2  mov     [rbp+57h+var_28], rax
0x1800f4ef6  mov     r14, rdx
0x1800f4ef9  mov     [rbp+57h+var_88], rcx
0x1800f4efd  xor     r15d, r15d
0x1800f4f00  mov     [rbp+57h+var_78], r15
0x1800f4f04  mov     [rbp+57h+var_50], r15
0x1800f4f08  lea     r9d, [r15+28h]; unsigned int
0x1800f4f0c  lea     r8d, [r15+29h]; unsigned int
0x1800f4f10  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x1800f4f17  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1800f4f1b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800f4f20  lea     rdx, [rbp+57h+var_78]
0x1800f4f24  mov     rcx, [rbp+57h+var_50]
0x1800f4f28  call    ??$GetActivationFactory@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackageStatics>>)
0x1800f4f2d  mov     ebx, eax
0x1800f4f2f  test    eax, eax
0x1800f4f31  jns     short loc_1800F4F4F
0x1800f4f33  mov     rcx, [rbp+5Fh]; this
0x1800f4f37  mov     r9d, eax; char *
0x1800f4f3a  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f4f41  lea     edx, [r15+7Eh]; void *
0x1800f4f45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4f4a  jmp     loc_1800F5338
0x1800f4f4f  mov     qword ptr [rbp+57h+var_A8], r15
0x1800f4f53  mov     rdi, [rbp+57h+var_78]
0x1800f4f57  mov     rax, [rdi]
0x1800f4f5a  mov     rbx, [rax+1A8h]
0x1800f4f61  lea     rcx, [rbp+57h+var_A8]
0x1800f4f65  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f4f6a  lea     rdx, [rbp+57h+var_88]
0x1800f4f6e  lea     rcx, [rbp+57h+var_48]
0x1800f4f72  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800f4f77  nop
0x1800f4f78  lea     rcx, [rbp+57h+var_A8]
0x1800f4f7c  mov     qword ptr [rsp+0E0h+var_C0], rcx; int
0x1800f4f81  mov     r9d, 31h ; '1'
0x1800f4f87  mov     r8, [rax+18h]
0x1800f4f8b  xor     edx, edx
0x1800f4f8d  mov     rcx, rdi
0x1800f4f90  mov     rax, rbx
0x1800f4f93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4f98  mov     ebx, eax
0x1800f4f9a  test    eax, eax
0x1800f4f9c  jns     short loc_1800F4FC5
0x1800f4f9e  mov     edx, 85h; void *
0x1800f4fa3  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f4faa  mov     r9d, eax; char *
0x1800f4fad  mov     rcx, [rbp+5Fh]; this
0x1800f4fb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f4fb6  nop
0x1800f4fb7  lea     rcx, [rbp+57h+var_A8]
0x1800f4fbb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f4fc0  jmp     loc_1800F5338
0x1800f4fc5  mov     [rbp+57h+var_80], r15d
0x1800f4fc9  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800f4fcd  mov     rax, [rcx]
0x1800f4fd0  lea     rdx, [rbp+57h+var_80]
0x1800f4fd4  mov     rax, [rax+38h]
0x1800f4fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f4fdd  mov     ebx, eax
0x1800f4fdf  test    eax, eax
0x1800f4fe1  jns     short loc_1800F4FEA
0x1800f4fe3  mov     edx, 88h
0x1800f4fe8  jmp     short loc_1800F4FA3
0x1800f4fea  cmp     [rbp+57h+var_80], 1
0x1800f4fee  jnz     loc_1800F539B
0x1800f4ff4  mov     [rbp+57h+var_B0], r15
0x1800f4ff8  mov     rcx, qword ptr [rbp+57h+var_A8]
0x1800f4ffc  mov     rax, [rcx]
0x1800f4fff  lea     r8, [rbp+57h+var_B0]
0x1800f5003  xor     edx, edx
0x1800f5005  mov     rax, [rax+30h]
0x1800f5009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f500e  mov     ebx, eax
0x1800f5010  test    eax, eax
0x1800f5012  jns     short loc_1800F504C
0x1800f5014  mov     rcx, [rbp+5Fh]; this
0x1800f5018  mov     r9d, eax; char *
0x1800f501b  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5022  mov     edx, 8Ch; void *
0x1800f5027  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f502c  nop
0x1800f502d  mov     rcx, [rbp+57h+var_B0]
0x1800f5031  test    rcx, rcx
0x1800f5034  jz      short loc_1800F5047
0x1800f5036  mov     [rbp+57h+var_B0], r15
0x1800f503a  mov     rax, [rcx]
0x1800f503d  mov     rax, [rax+10h]
0x1800f5041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5046  nop
0x1800f5047  jmp     loc_1800F4FB7
0x1800f504c  mov     [rbp+57h+var_98], r15
0x1800f5050  lea     rcx, [rbp+57h+var_48]; string
0x1800f5054  call    ??$?0$0CN@@StringReference@Internal@Windows@@QEAA@AEAY0CN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[45])
0x1800f5059  lea     rdx, [rbp+57h+var_98]
0x1800f505d  mov     rcx, [rax]
0x1800f5060  call    ??$GetActivationFactory@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIApplicationStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IApplicationStatics>>)
0x1800f5065  mov     ebx, eax
0x1800f5067  test    eax, eax
0x1800f5069  jns     short loc_1800F50AD
0x1800f506b  mov     rcx, [rbp+5Fh]; this
0x1800f506f  mov     r9d, eax; char *
0x1800f5072  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5079  mov     edx, 90h; void *
0x1800f507e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5083  nop
0x1800f5084  lea     rcx, [rbp+57h+var_98]
0x1800f5088  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f508d  nop
0x1800f508e  mov     rcx, [rbp+57h+var_B0]
0x1800f5092  test    rcx, rcx
0x1800f5095  jz      short loc_1800F50A8
0x1800f5097  mov     [rbp+57h+var_B0], r15
0x1800f509b  mov     rax, [rcx]
0x1800f509e  mov     rax, [rax+10h]
0x1800f50a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f50a7  nop
0x1800f50a8  jmp     loc_1800F4FB7
0x1800f50ad  mov     [rbp+57h+var_A0], r15
0x1800f50b1  mov     rdi, [rbp+57h+var_98]
0x1800f50b5  mov     rax, [rdi]
0x1800f50b8  mov     rbx, [rax+90h]
0x1800f50bf  lea     rcx, [rbp+57h+var_A0]
0x1800f50c3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f50c8  lea     r8, [rbp+57h+var_A0]
0x1800f50cc  mov     rdx, [rbp+57h+var_B0]
0x1800f50d0  mov     rcx, rdi
0x1800f50d3  mov     rax, rbx
0x1800f50d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f50db  mov     ebx, eax
0x1800f50dd  test    eax, eax
0x1800f50df  jns     short loc_1800F512D
0x1800f50e1  mov     rcx, [rbp+5Fh]; this
0x1800f50e5  mov     r9d, eax; char *
0x1800f50e8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f50ef  mov     edx, 92h; void *
0x1800f50f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f50f9  nop
0x1800f50fa  lea     rcx, [rbp+57h+var_A0]
0x1800f50fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5103  nop
0x1800f5104  lea     rcx, [rbp+57h+var_98]
0x1800f5108  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f510d  nop
0x1800f510e  mov     rcx, [rbp+57h+var_B0]
0x1800f5112  test    rcx, rcx
0x1800f5115  jz      short loc_1800F5128
0x1800f5117  mov     [rbp+57h+var_B0], r15
0x1800f511b  mov     rax, [rcx]
0x1800f511e  mov     rax, [rax+10h]
0x1800f5122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5127  nop
0x1800f5128  jmp     loc_1800F4FB7
0x1800f512d  mov     [rbp+57h+var_90], r15d
0x1800f5131  mov     rcx, [rbp+57h+var_A0]
0x1800f5135  mov     rax, [rcx]
0x1800f5138  lea     rdx, [rbp+57h+var_90]
0x1800f513c  mov     rax, [rax+38h]
0x1800f5140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5145  mov     ebx, eax
0x1800f5147  test    eax, eax
0x1800f5149  jns     short loc_1800F5197
0x1800f514b  mov     rcx, [rbp+5Fh]; this
0x1800f514f  mov     r9d, eax; char *
0x1800f5152  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f5159  mov     edx, 96h; void *
0x1800f515e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f5163  nop
0x1800f5164  lea     rcx, [rbp+57h+var_A0]
0x1800f5168  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f516d  nop
0x1800f516e  lea     rcx, [rbp+57h+var_98]
0x1800f5172  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5177  nop
0x1800f5178  mov     rcx, [rbp+57h+var_B0]
0x1800f517c  test    rcx, rcx
0x1800f517f  jz      short loc_1800F5192
0x1800f5181  mov     [rbp+57h+var_B0], r15
0x1800f5185  mov     rax, [rcx]
0x1800f5188  mov     rax, [rax+10h]
0x1800f518c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5191  nop
0x1800f5192  jmp     loc_1800F4FB7
0x1800f5197  mov     eax, [rbp+57h+var_90]
0x1800f519a  test    eax, eax
0x1800f519c  jnz     short loc_1800F51D3
0x1800f519e  mov     rcx, [rbp+5Fh]; this
0x1800f51a2  mov     r9d, 8000FFFFh; char *
0x1800f51a8  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f51af  mov     edx, 97h; void *
0x1800f51b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f51b9  nop
0x1800f51ba  lea     rcx, [rbp+57h+var_A0]
0x1800f51be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f51c3  nop
0x1800f51c4  lea     rcx, [rbp+57h+var_98]
0x1800f51c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f51cd  nop
0x1800f51ce  jmp     loc_1800F5310
0x1800f51d3  mov     esi, r15d
0x1800f51d6  test    eax, eax
0x1800f51d8  jz      loc_1800F52DA
0x1800f51de  mov     [rbp+57h+var_88], r15
0x1800f51e2  mov     rdi, [rbp+57h+var_A0]
0x1800f51e6  mov     rax, [rdi]
0x1800f51e9  mov     rbx, [rax+30h]
0x1800f51ed  lea     rcx, [rbp+57h+var_88]
0x1800f51f1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f51f6  lea     r8, [rbp+57h+var_88]
0x1800f51fa  mov     edx, esi
0x1800f51fc  mov     rcx, rdi
0x1800f51ff  mov     rax, rbx
0x1800f5202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5207  test    eax, eax
0x1800f5209  js      loc_1800F52C4
0x1800f520f  mov     [rbp+57h+string], r15
0x1800f5213  mov     rdi, [rbp+57h+var_88]
0x1800f5217  mov     rax, [rdi]
0x1800f521a  mov     rbx, [rax+0E8h]
0x1800f5221  xor     ecx, ecx; string
0x1800f5223  call    cs:__imp_WindowsDeleteString
0x1800f5229  mov     [rbp+57h+string], r15
0x1800f522d  lea     rdx, [rbp+57h+string]
0x1800f5231  mov     rcx, rdi
0x1800f5234  mov     rax, rbx
0x1800f5237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f523c  test    eax, eax
0x1800f523e  js      short loc_1800F52B9
0x1800f5240  xor     edx, edx; length
0x1800f5242  mov     rcx, [rbp+57h+string]; string
0x1800f5246  call    cs:__imp_WindowsGetStringRawBuffer
0x1800f524c  mov     rdx, rax
0x1800f524f  lea     rcx, [rbp+57h+var_48]
0x1800f5253  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800f5258  nop
0x1800f5259  mov     rcx, 555555555555555h
0x1800f5263  cmp     [r14+8], rcx
0x1800f5267  jz      loc_1800F5348
0x1800f526d  mov     rbx, [r14]
0x1800f5270  mov     r8, rax
0x1800f5273  mov     rdx, r14
0x1800f5276  lea     rcx, [rbp+57h+hstringHeader]
0x1800f527a  call    ??$?0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::wstring &&)
0x1800f527f  inc     qword ptr [r14+8]
0x1800f5283  mov     rcx, [rbx+8]
0x1800f5287  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x1800f528b  mov     [rax], rbx
0x1800f528e  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x1800f5292  mov     [rax+8], rcx
0x1800f5296  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x1800f529a  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r15
0x1800f529e  mov     [rbx+8], rax
0x1800f52a2  mov     [rcx], rax
0x1800f52a5  lea     rcx, [rbp+57h+hstringHeader]
0x1800f52a9  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::wstring,void *>>>(void)
0x1800f52ae  nop
0x1800f52af  lea     rcx, [rbp+57h+var_48]; void *
0x1800f52b3  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4__MIDL___MIDL_itf_wpntypes_0000_0000_0005@@@std@@QEAA@XZ; std::pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>::~pair<std::wstring const,__MIDL___MIDL_itf_wpntypes_0000_0000_0005>(void)
0x1800f52b8  nop
0x1800f52b9  mov     rcx, [rbp+57h+string]; string
0x1800f52bd  call    cs:__imp_WindowsDeleteString
0x1800f52c3  nop
0x1800f52c4  lea     rcx, [rbp+57h+var_88]
0x1800f52c8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f52cd  inc     esi
0x1800f52cf  mov     eax, [rbp+57h+var_90]
0x1800f52d2  cmp     esi, eax
0x1800f52d4  jb      loc_1800F51DE
0x1800f52da  cmp     rax, [r14+8]
0x1800f52de  jz      short loc_1800F5356
0x1800f52e0  mov     rcx, [rbp+5Fh]; this
0x1800f52e4  mov     r9d, 8000FFFFh; char *
0x1800f52ea  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\diagnosis\\platform\\"...
0x1800f52f1  mov     edx, 0A6h; void *
0x1800f52f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f52fb  nop
0x1800f52fc  lea     rcx, [rbp+57h+var_A0]
0x1800f5300  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f5305  nop
0x1800f5306  lea     rcx, [rbp+57h+var_98]
0x1800f530a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800f530f  nop
0x1800f5310  mov     rcx, [rbp+57h+var_B0]
0x1800f5314  test    rcx, rcx
0x1800f5317  jz      short loc_1800F532A
0x1800f5319  mov     [rbp+57h+var_B0], r15
0x1800f531d  mov     rax, [rcx]
0x1800f5320  mov     rax, [rax+10h]
0x1800f5324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f5329  nop
  ... truncated ...
```
