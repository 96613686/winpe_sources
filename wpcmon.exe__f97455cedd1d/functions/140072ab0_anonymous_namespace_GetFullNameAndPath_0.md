# _anonymous_namespace_::GetFullNameAndPath_0

- ea: `0x140072ab0`
- end: `0x140073358`
- name: `_anonymous_namespace_::GetFullNameAndPath_0`
- size: `2216`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x140072170`

## callees

- `0x140005530`
- `0x1400057f0`
- `0x140006314`
- `0x140006338`
- `0x140009858`
- `0x14000cbd8`
- `0x14000ccac`
- `0x14000d084`
- `0x14001c1c0`
- `0x14001c804`
- `0x14001f654`
- `0x14001f6b4`
- `0x140045250`
- `0x140060e60`
- `0x140060f58`
- `0x14006fb70`
- `0x140070fb4`
- `0x140071080`
- `0x140072794`
- `0x140072ab0`
- `0x140073388`
- `0x140073f34`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetPackagesByPackageFamily` at `0x140072b2b`
- `KERNEL32!GetPackagesByPackageFamily` at `0x140072cb2`
- `KERNEL32!GetPackagesByPackageFamily` at `0x140072b2b`
- `KERNEL32!GetPackagesByPackageFamily` at `0x140072cb2`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140072e9d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140072e9d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140072e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140072e84`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall anonymous_namespace_::GetFullNameAndPath_0(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r12
  const WCHAR *v5; // rcx
  LONG PackagesByPackageFamily; // eax
  unsigned int v7; // ebx
  size_t v8; // r15
  PWSTR *v9; // rax
  WCHAR *v10; // rax
  WCHAR *v11; // rcx
  PWSTR *v12; // rbx
  size_t v13; // r15
  WCHAR *v14; // rax
  void *v15; // rax
  void *v16; // rcx
  WCHAR *v17; // rbx
  const WCHAR *v18; // rcx
  LONG v19; // eax
  signed int v20; // ebx
  _WORD *v21; // rdx
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // r8
  __int64 PathFromFullName; // rcx
  _WORD *v25; // rdx
  __int16 v26; // si
  __int64 v27; // xmm6_8
  int v28; // r15d
  __int16 v29; // r12
  __int64 v30; // r13
  int v32; // ebx
  __int64 v33; // rbx
  __int64 (__fastcall *v34)(__int64, _QWORD, __int64 *); // r15
  const WCHAR *v35; // rax
  _QWORD *v36; // rax
  int v37; // ebx
  int v38; // ebx
  int v39; // ebx
  int v40; // ebx
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v45; // eax
  __int64 v46; // rdx
  int v47; // r8d
  int v48; // eax
  __int64 v49; // r10
  int v50; // eax
  __int64 v51; // r10
  int v52; // eax
  __int64 v53; // r10
  int v54; // eax
  __int64 v55; // r10
  __int64 v56; // rax
  __int64 v57; // r10
  int v58; // eax
  __int64 v59; // r10
  char v60[4]; // [rsp+30h] [rbp-278h] BYREF
  UINT32 count; // [rsp+34h] [rbp-274h] BYREF
  UINT32 bufferLength; // [rsp+38h] [rbp-270h] BYREF
  __int64 v63; // [rsp+40h] [rbp-268h] BYREF
  __int64 v64; // [rsp+48h] [rbp-260h] BYREF
  __int64 v65; // [rsp+50h] [rbp-258h] BYREF
  __int64 v66; // [rsp+58h] [rbp-250h] BYREF
  __int64 v67; // [rsp+60h] [rbp-248h] BYREF
  const WCHAR *v68; // [rsp+68h] [rbp-240h] BYREF
  PWSTR *packageFullNames[2]; // [rsp+70h] [rbp-238h] BYREF
  PWSTR *v70; // [rsp+80h] [rbp-228h]
  WCHAR *buffer[2]; // [rsp+88h] [rbp-220h] BYREF
  WCHAR *v72; // [rsp+98h] [rbp-210h]
  __int64 v73; // [rsp+A8h] [rbp-200h]
  __int64 v74; // [rsp+B0h] [rbp-1F8h]
  _BYTE pExceptionObject[40]; // [rsp+C0h] [rbp-1E8h] BYREF
  _BYTE v76[40]; // [rsp+E8h] [rbp-1C0h] BYREF
  _BYTE v77[40]; // [rsp+110h] [rbp-198h] BYREF
  _BYTE v78[40]; // [rsp+138h] [rbp-170h] BYREF
  _BYTE v79[40]; // [rsp+160h] [rbp-148h] BYREF
  _BYTE v80[40]; // [rsp+188h] [rbp-120h] BYREF
  _BYTE v81[40]; // [rsp+1B0h] [rbp-F8h] BYREF
  _BYTE v82[40]; // [rsp+1D8h] [rbp-D0h] BYREF
  __int64 v83; // [rsp+200h] [rbp-A8h]
  __int128 v84; // [rsp+208h] [rbp-A0h] BYREF
  __int64 v85; // [rsp+218h] [rbp-90h]
  __int64 v86; // [rsp+220h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+228h] [rbp-80h] BYREF
  __int64 v88; // [rsp+240h] [rbp-68h]
  char *v89[4]; // [rsp+248h] [rbp-60h] BYREF

  v74 = a1;
  v68 = (const WCHAR *)a2;
  count = 0;
  bufferLength = 0;
  v4 = (_QWORD *)(a2 + 24);
  v73 = a2 + 24;
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  PackagesByPackageFamily = GetPackagesByPackageFamily(v5, &count, 0, &bufferLength, 0);
  v7 = PackagesByPackageFamily;
  if ( PackagesByPackageFamily && PackagesByPackageFamily != 122 )
  {
    if ( PackagesByPackageFamily > 0 )
      v7 = (unsigned __int16)PackagesByPackageFamily | 0x80070000;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v45 = std::wstring::c_str(a2);
      WPP_SF_Sdd(*(_QWORD *)(v46 + 16), v46, v47, v45, count, v7);
    }
    ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
    throw (ErrorCodeException *)pExceptionObject;
  }
  if ( count )
  {
    *(_OWORD *)packageFullNames = 0;
    v70 = 0;
    v8 = 8LL * count;
    if ( v8 )
    {
      if ( v8 < 0x1000 )
      {
        v9 = (PWSTR *)operator new(8LL * count);
      }
      else
      {
        if ( v8 + 39 < v8 )
          __scrt_throw_std_bad_array_new_length();
        v10 = (WCHAR *)operator new(v8 + 39);
        v11 = v10;
        if ( !v10 )
          __fastfail(5u);
        v9 = (PWSTR *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v11;
      }
    }
    else
    {
      v9 = 0;
    }
    packageFullNames[0] = v9;
    v12 = &v9[v8 / 8];
    v70 = &v9[v8 / 8];
    memset_0(v9, 0, v8);
    packageFullNames[1] = v12;
    v64 = 0;
    std::_Tidy_guard<std::vector<IWaitable const *>>::~_Tidy_guard<std::vector<IWaitable const *>>(&v64);
    *(_OWORD *)buffer = 0;
    v72 = 0;
    if ( bufferLength )
    {
      v13 = 2LL * bufferLength;
      if ( v13 )
      {
        if ( v13 < 0x1000 )
        {
          v14 = (WCHAR *)operator new(2LL * bufferLength);
        }
        else
        {
          if ( v13 + 39 < v13 )
            __scrt_throw_std_bad_array_new_length();
          v15 = operator new(v13 + 39);
          v16 = v15;
          if ( !v15 )
            __fastfail(5u);
          v14 = (WCHAR *)(((unsigned __int64)v15 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
          *((_QWORD *)v14 - 1) = v16;
        }
      }
      else
      {
        v14 = 0;
      }
      buffer[0] = v14;
      v17 = &v14[v13 / 2];
      v72 = &v14[v13 / 2];
      memset_0(v14, 0, v13);
      buffer[1] = v17;
      v64 = 0;
      std::_Tidy_guard<std::vector<unsigned short>>::~_Tidy_guard<std::vector<unsigned short>>(&v64);
    }
    if ( *v4 <= 7u )
      v18 = (const WCHAR *)a2;
    else
      v18 = *(const WCHAR **)a2;
    v19 = GetPackagesByPackageFamily(v18, &count, packageFullNames[0], &bufferLength, buffer[0]);
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v48 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v49 + 16), 24, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v48, v20);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v76, v20);
      throw (ErrorCodeException *)v76;
    }
    v21 = *packageFullNames[0];
    memset(&hstringHeader, 0, sizeof(hstringHeader));
    v88 = 0;
    v22 = -1;
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    std::wstring::_Construct<1,unsigned short const *>((char **)&hstringHeader, v21, v23);
    PathFromFullName = anonymous_namespace_::GetPathFromFullName((__int64)v89, (__int64)&hstringHeader);
    v25 = *packageFullNames[0];
    v83 = (__int64)*packageFullNames[0];
    v84 = 0;
    v26 = *(_WORD *)PathFromFullName;
    LOWORD(v84) = *(_WORD *)PathFromFullName;
    v27 = *(_QWORD *)(PathFromFullName + 2);
    *(_QWORD *)((char *)&v84 + 2) = v27;
    v28 = *(_DWORD *)(PathFromFullName + 10);
    *(_DWORD *)((char *)&v84 + 10) = v28;
    v29 = *(_WORD *)(PathFromFullName + 14);
    HIWORD(v84) = v29;
    v30 = *(_QWORD *)(PathFromFullName + 16);
    v85 = v30;
    v64 = *(_QWORD *)(PathFromFullName + 24);
    v86 = v64;
    *(_QWORD *)(PathFromFullName + 16) = 0;
    *(_QWORD *)(PathFromFullName + 24) = 7;
    *(_WORD *)PathFromFullName = 0;
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    do
      ++v22;
    while ( v25[v22] );
    std::wstring::_Construct<1,unsigned short const *>((char **)a1, v25, v22);
    *(_WORD *)(a1 + 32) = v26;
    *(_QWORD *)(a1 + 34) = v27;
    *(_DWORD *)(a1 + 42) = v28;
    *(_WORD *)(a1 + 46) = v29;
    *(_QWORD *)(a1 + 48) = v30;
    *(_QWORD *)(a1 + 56) = v64;
    v85 = 0;
    v86 = 7;
    LOWORD(v84) = 0;
    std::wstring::~wstring((char **)&v84);
    std::wstring::~wstring(v89);
    std::wstring::~wstring((char **)&hstringHeader);
    std::vector<unsigned short>::~vector<unsigned short>(buffer);
    std::vector<unsigned short *>::~vector<unsigned short *>((char **)packageFullNames);
    return a1;
  }
  else
  {
    v67 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Management.Deployment.PackageManager",
           0x2Cu,
           (HSTRING_HEADER *)&hstringHeader.Reserved.Reserved2[8],
           (HSTRING *)&hstringHeader) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v32 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
            (__int64)hstringHeader.Reserved.Reserved1,
            &v67);
    if ( v32 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          25,
          WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
          (unsigned int)v32);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v77, v32);
      throw (ErrorCodeException *)v77;
    }
    v66 = 0;
    v33 = v67;
    v34 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v67 + 152LL);
    if ( *v4 <= 7u )
      v35 = (const WCHAR *)a2;
    else
      v35 = *(const WCHAR **)a2;
    v68 = v35;
    v36 = (_QWORD *)Windows::Internal::StringReference::StringReference((__int64)v89, &v68);
    v37 = v34(v33, *v36, &v66);
    if ( v37 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v50 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v51 + 16), 26, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v50, v37);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v78, v37);
      throw (ErrorCodeException *)v78;
    }
    v63 = 0;
    v38 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v66 + 48LL))(v66, &v63);
    if ( v38 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v52 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v53 + 16), 27, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v52, v38);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v79, v38);
      throw (ErrorCodeException *)v79;
    }
    v60[0] = 0;
    v39 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v63 + 56LL))(v63, v60);
    if ( v39 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v54 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v55 + 16), 28, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v54, v39);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v80, v39);
      throw (ErrorCodeException *)v80;
    }
    if ( !v60[0] )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v56 = std::wstring::c_str(a2);
        WPP_SF_S(*(_QWORD *)(v57 + 16), 29, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v56);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v81, -2147024809);
      throw (ErrorCodeException *)v81;
    }
    v65 = 0;
    v40 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v63 + 48LL))(v63, &v65);
    if ( v40 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v58 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v59 + 16), 30, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v58, v40);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v82, v40);
      throw (ErrorCodeException *)v82;
    }
    anonymous_namespace_::GetFullNameAndPath(a1, v65);
    v41 = v65;
    if ( v65 )
    {
      v65 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v42 = v63;
    if ( v63 )
    {
      v63 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
    v43 = v66;
    if ( v66 )
    {
      v66 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    }
    v44 = v67;
    if ( v67 )
    {
      v67 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return a1;
  }
}

```

## disassembly

```asm
0x140072ab0  mov     rax, rsp
0x140072ab3  mov     [rax+18h], rbx
0x140072ab7  mov     [rax+20h], rsi
0x140072abb  push    rdi
0x140072abc  push    r12
0x140072abe  push    r13
0x140072ac0  push    r14
0x140072ac2  push    r15
0x140072ac4  sub     rsp, 280h
0x140072acb  movaps  xmmword ptr [rax-38h], xmm6
0x140072acf  mov     rax, cs:__security_cookie
0x140072ad6  xor     rax, rsp
0x140072ad9  mov     [rsp+2A8h+var_40], rax
0x140072ae1  mov     rsi, rdx
0x140072ae4  mov     r14, rcx
0x140072ae7  mov     [rsp+2A8h+var_1F8], rcx
0x140072aef  mov     [rsp+2A8h+var_240], rdx
0x140072af4  xor     edi, edi
0x140072af6  mov     [rsp+2A8h+count], edi
0x140072afa  mov     [rsp+2A8h+bufferLength], edi
0x140072afe  lea     r12, [rdx+18h]
0x140072b02  mov     [rsp+2A8h+var_200], r12
0x140072b0a  cmp     qword ptr [r12], 7
0x140072b0f  jbe     short loc_140072B16
0x140072b11  mov     rcx, [rdx]
0x140072b14  jmp     short loc_140072B19
0x140072b16  mov     rcx, rsi; packageFamilyName
0x140072b19  mov     [rsp+2A8h+buffer], rdi; buffer
0x140072b1e  lea     r9, [rsp+2A8h+bufferLength]; bufferLength
0x140072b23  xor     r8d, r8d; packageFullNames
0x140072b26  lea     rdx, [rsp+2A8h+count]; count
0x140072b2b  call    cs:__imp_GetPackagesByPackageFamily
0x140072b31  mov     ebx, eax
0x140072b33  test    eax, eax
0x140072b35  jz      short loc_140072B40
0x140072b37  cmp     eax, 7Ah ; 'z'
0x140072b3a  jnz     loc_140073043
0x140072b40  cmp     [rsp+2A8h+count], edi
0x140072b44  jbe     loc_140072E4A
0x140072b4a  mov     r15d, [rsp+2A8h+count]
0x140072b4f  xorps   xmm0, xmm0
0x140072b52  movdqu  xmmword ptr [rsp+2A8h+packageFullNames], xmm0
0x140072b58  mov     [rsp+2A8h+var_228], rdi
0x140072b60  test    r15, r15
0x140072b63  jz      short loc_140072BE4
0x140072b65  shl     r15, 3
0x140072b69  test    r15, r15
0x140072b6c  jnz     short loc_140072B73
0x140072b6e  mov     rax, rdi
0x140072b71  jmp     short loc_140072BB1
0x140072b73  cmp     r15, 1000h
0x140072b7a  jb      short loc_140072BA9
0x140072b7c  lea     rcx, [r15+27h]; Size
0x140072b80  cmp     rcx, r15
0x140072b83  jbe     loc_1400730AC
0x140072b89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140072b8e  mov     rcx, rax
0x140072b91  test    rax, rax
0x140072b94  jnz     short loc_140072B9B
0x140072b96  lea     ecx, [rax+5]
0x140072b99  int     29h; Win8: RtlFailFast(ecx)
0x140072b9b  add     rax, 27h ; '''
0x140072b9f  and     rax, 0FFFFFFFFFFFFFFE0h
0x140072ba3  mov     [rax-8], rcx
0x140072ba7  jmp     short loc_140072BB1
0x140072ba9  mov     rcx, r15; Size
0x140072bac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140072bb1  mov     [rsp+2A8h+packageFullNames], rax
0x140072bb6  lea     rbx, [rax+r15]
0x140072bba  mov     [rsp+2A8h+var_228], rbx
0x140072bc2  mov     r8, r15; Size
0x140072bc5  xor     edx, edx; Val
0x140072bc7  mov     rcx, rax; void *
0x140072bca  call    memset_0
0x140072bcf  mov     [rsp+2A8h+packageFullNames+8], rbx
0x140072bd4  mov     [rsp+2A8h+var_260], rdi
0x140072bd9  lea     rcx, [rsp+2A8h+var_260]
0x140072bde  call    ??1?$_Tidy_guard@V?$vector@PEBUIWaitable@@V?$allocator@PEBUIWaitable@@@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<IWaitable const *>>::~_Tidy_guard<std::vector<IWaitable const *>>(void)
0x140072be3  nop
0x140072be4  mov     r15d, [rsp+2A8h+bufferLength]
0x140072be9  xorps   xmm0, xmm0
0x140072bec  movdqu  xmmword ptr [rsp+2A8h+var_220], xmm0
0x140072bf5  mov     [rsp+2A8h+var_210], rdi
0x140072bfd  test    r15, r15
0x140072c00  jz      loc_140072C87
0x140072c06  add     r15, r15
0x140072c09  jnz     short loc_140072C10
0x140072c0b  mov     rax, rdi
0x140072c0e  jmp     short loc_140072C4E
0x140072c10  cmp     r15, 1000h
0x140072c17  jb      short loc_140072C46
0x140072c19  lea     rcx, [r15+27h]; Size
0x140072c1d  cmp     rcx, r15
0x140072c20  jbe     loc_1400730B2
0x140072c26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140072c2b  mov     rcx, rax
0x140072c2e  test    rax, rax
0x140072c31  jnz     short loc_140072C38
0x140072c33  lea     ecx, [rax+5]
0x140072c36  int     29h; Win8: RtlFailFast(ecx)
0x140072c38  add     rax, 27h ; '''
0x140072c3c  and     rax, 0FFFFFFFFFFFFFFE0h
0x140072c40  mov     [rax-8], rcx
0x140072c44  jmp     short loc_140072C4E
0x140072c46  mov     rcx, r15; Size
0x140072c49  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140072c4e  mov     [rsp+2A8h+var_220], rax
0x140072c56  lea     rbx, [rax+r15]
0x140072c5a  mov     [rsp+2A8h+var_210], rbx
0x140072c62  mov     r8, r15; Size
0x140072c65  xor     edx, edx; Val
0x140072c67  mov     rcx, rax; void *
0x140072c6a  call    memset_0
0x140072c6f  mov     [rsp+2A8h+var_220+8], rbx
0x140072c77  mov     [rsp+2A8h+var_260], rdi
0x140072c7c  lea     rcx, [rsp+2A8h+var_260]
0x140072c81  call    ??1?$_Tidy_guard@V?$vector@GV?$allocator@G@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<ushort>>::~_Tidy_guard<std::vector<ushort>>(void)
0x140072c86  nop
0x140072c87  mov     rax, [rsp+2A8h+var_220]
0x140072c8f  cmp     qword ptr [r12], 7
0x140072c94  jbe     short loc_140072C9B
0x140072c96  mov     rcx, [rsi]
0x140072c99  jmp     short loc_140072C9E
0x140072c9b  mov     rcx, rsi; packageFamilyName
0x140072c9e  mov     [rsp+2A8h+buffer], rax; buffer
0x140072ca3  lea     r9, [rsp+2A8h+bufferLength]; bufferLength
0x140072ca8  mov     r8, [rsp+2A8h+packageFullNames]; packageFullNames
0x140072cad  lea     rdx, [rsp+2A8h+count]; count
0x140072cb2  call    cs:__imp_GetPackagesByPackageFamily
0x140072cb8  mov     ebx, eax
0x140072cba  test    eax, eax
0x140072cbc  jle     short loc_140072CC7
0x140072cbe  movzx   ebx, ax
0x140072cc1  or      ebx, 80070000h
0x140072cc7  test    ebx, ebx
0x140072cc9  js      loc_1400730B8
0x140072ccf  mov     rax, [rsp+2A8h+packageFullNames]
0x140072cd4  mov     rdx, [rax]
0x140072cd7  xorps   xmm0, xmm0
0x140072cda  movups  xmmword ptr [rsp+2A8h+hstringHeader.Reserved], xmm0
0x140072ce2  mov     qword ptr [rsp+2A8h+hstringHeader.Reserved+10h], rdi
0x140072cea  mov     [rsp+2A8h+var_68], rdi
0x140072cf2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140072cf6  mov     r8, rbx
0x140072cf9  inc     r8
0x140072cfc  cmp     [rdx+r8*2], di
0x140072d01  jnz     short loc_140072CF9
0x140072d03  lea     rcx, [rsp+2A8h+hstringHeader]
0x140072d0b  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140072d10  nop
0x140072d11  lea     rdx, [rsp+2A8h+hstringHeader]
0x140072d19  lea     rcx, [rsp+2A8h+var_60]
0x140072d21  call    _anonymous_namespace___GetPathFromFullName
0x140072d26  mov     rcx, rax
0x140072d29  mov     rax, [rsp+2A8h+packageFullNames]
0x140072d2e  mov     rdx, [rax]
0x140072d31  mov     [rsp+2A8h+var_A8], rdx
0x140072d39  xorps   xmm0, xmm0
0x140072d3c  movups  [rsp+2A8h+var_A0], xmm0
0x140072d44  movzx   esi, word ptr [rcx]
0x140072d47  mov     word ptr [rsp+2A8h+var_A0], si
0x140072d4f  movsd   xmm6, qword ptr [rcx+2]
0x140072d54  movsd   qword ptr [rsp+2A8h+var_A0+2], xmm6
0x140072d5d  mov     r15d, [rcx+0Ah]
0x140072d61  mov     dword ptr [rsp+2A8h+var_A0+0Ah], r15d
0x140072d69  movzx   r12d, word ptr [rcx+0Eh]
0x140072d6e  mov     word ptr [rsp+2A8h+var_A0+0Eh], r12w
0x140072d77  mov     r13, [rcx+10h]
0x140072d7b  mov     [rsp+2A8h+var_90], r13
0x140072d83  mov     rax, [rcx+18h]
0x140072d87  mov     [rsp+2A8h+var_260], rax
0x140072d8c  mov     [rsp+2A8h+var_88], rax
0x140072d94  mov     [rcx+10h], rdi
0x140072d98  mov     qword ptr [rcx+18h], 7
0x140072da0  mov     [rcx], di
0x140072da3  movups  xmmword ptr [r14], xmm0
0x140072da7  mov     [r14+10h], rdi
0x140072dab  mov     [r14+18h], rdi
0x140072daf  inc     rbx
0x140072db2  cmp     [rdx+rbx*2], di
0x140072db6  jnz     short loc_140072DAF
0x140072db8  mov     r8, rbx
0x140072dbb  mov     rcx, r14
0x140072dbe  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140072dc3  mov     [r14+20h], si
0x140072dc8  movsd   qword ptr [r14+22h], xmm6
0x140072dce  mov     [r14+2Ah], r15d
0x140072dd2  mov     [r14+2Eh], r12w
0x140072dd7  mov     [r14+30h], r13
0x140072ddb  mov     rax, [rsp+2A8h+var_260]
0x140072de0  mov     [r14+38h], rax
0x140072de4  mov     [rsp+2A8h+var_90], rdi
0x140072dec  mov     [rsp+2A8h+var_88], 7
0x140072df8  mov     word ptr [rsp+2A8h+var_A0], di
0x140072e00  lea     rcx, [rsp+2A8h+var_A0]
0x140072e08  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140072e0d  nop
0x140072e0e  lea     rcx, [rsp+2A8h+var_60]
0x140072e16  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140072e1b  nop
0x140072e1c  lea     rcx, [rsp+2A8h+hstringHeader]
0x140072e24  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140072e29  nop
0x140072e2a  lea     rcx, [rsp+2A8h+var_220]
0x140072e32  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x140072e37  nop
0x140072e38  lea     rcx, [rsp+2A8h+packageFullNames]
0x140072e3d  call    ??1?$vector@PEAGV?$allocator@PEAG@std@@@std@@QEAA@XZ; std::vector<ushort *>::~vector<ushort *>(void)
0x140072e42  mov     rax, r14
0x140072e45  jmp     loc_140073011
0x140072e4a  jmp     short loc_140072E63
0x140072e4c  xor     edi, edi
0x140072e4e  mov     r12, [rsp+2A8h+var_200]
0x140072e56  mov     r14, [rsp+2A8h+var_1F8]
0x140072e5e  mov     rsi, [rsp+2A8h+var_240]
0x140072e63  mov     [rsp+2A8h+var_248], rdi
0x140072e68  lea     r9, [rsp+2A8h+hstringHeader]; string
0x140072e70  lea     r8, [rsp+2A8h+hstringHeader.Reserved+8]; hstringHeader
0x140072e78  mov     edx, 2Ch ; ','; length
0x140072e7d  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x140072e84  call    cs:__imp_WindowsCreateStringReference
0x140072e8a  test    eax, eax
0x140072e8c  jns     short loc_140072EA3
0x140072e8e  xor     r9d, r9d; lpArguments
0x140072e91  xor     r8d, r8d; nNumberOfArguments
0x140072e94  lea     edx, [r9+1]; dwExceptionFlags
0x140072e98  mov     ecx, 0C000000Dh; dwExceptionCode
0x140072e9d  call    cs:__imp_RaiseException
0x140072ea3  lea     rdx, [rsp+2A8h+var_248]
0x140072ea8  mov     rcx, qword ptr [rsp+2A8h+hstringHeader.Reserved]
0x140072eb0  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x140072eb5  mov     ebx, eax
0x140072eb7  test    eax, eax
0x140072eb9  js      loc_14007311A
0x140072ebf  mov     [rsp+2A8h+var_250], rdi
0x140072ec4  mov     rbx, [rsp+2A8h+var_248]
0x140072ec9  mov     rax, [rbx]
0x140072ecc  mov     r15, [rax+98h]
0x140072ed3  cmp     qword ptr [r12], 7
0x140072ed8  jbe     short loc_140072EDF
0x140072eda  mov     rax, [rsi]
0x140072edd  jmp     short loc_140072EE2
0x140072edf  mov     rax, rsi
0x140072ee2  mov     [rsp+2A8h+var_240], rax
0x140072ee7  lea     rdx, [rsp+2A8h+var_240]
0x140072eec  lea     rcx, [rsp+2A8h+var_60]
0x140072ef4  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x140072ef9  lea     r8, [rsp+2A8h+var_250]
0x140072efe  mov     rdx, [rax]
0x140072f01  mov     rcx, rbx
0x140072f04  mov     rax, r15
0x140072f07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072f0c  mov     ebx, eax
0x140072f0e  test    eax, eax
0x140072f10  js      loc_14007316F
0x140072f16  mov     [rsp+2A8h+var_268], rdi
0x140072f1b  mov     rcx, [rsp+2A8h+var_250]
0x140072f20  mov     rax, [rcx]
0x140072f23  lea     rdx, [rsp+2A8h+var_268]
0x140072f28  mov     rax, [rax+30h]
0x140072f2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072f31  mov     ebx, eax
0x140072f33  test    eax, eax
0x140072f35  js      loc_1400731D1
0x140072f3b  mov     [rsp+2A8h+var_278], dil
0x140072f40  mov     rcx, [rsp+2A8h+var_268]
0x140072f45  mov     rax, [rcx]
0x140072f48  lea     rdx, [rsp+2A8h+var_278]
0x140072f4d  mov     rax, [rax+38h]
0x140072f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072f56  mov     ebx, eax
0x140072f58  test    eax, eax
0x140072f5a  js      loc_140073233
0x140072f60  cmp     [rsp+2A8h+var_278], dil
0x140072f65  jz      loc_140073295
0x140072f6b  mov     [rsp+2A8h+var_258], rdi
0x140072f70  mov     rcx, [rsp+2A8h+var_268]
0x140072f75  mov     rax, [rcx]
0x140072f78  lea     rdx, [rsp+2A8h+var_258]
0x140072f7d  mov     rax, [rax+30h]
0x140072f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072f86  mov     ebx, eax
0x140072f88  test    eax, eax
0x140072f8a  js      loc_1400732F6
0x140072f90  mov     rdx, [rsp+2A8h+var_258]
0x140072f95  mov     rcx, r14
0x140072f98  call    _anonymous_namespace___GetFullNameAndPath
0x140072f9d  nop
0x140072f9e  mov     rcx, [rsp+2A8h+var_258]
0x140072fa3  test    rcx, rcx
0x140072fa6  jz      short loc_140072FBA
0x140072fa8  mov     [rsp+2A8h+var_258], rdi
0x140072fad  mov     rax, [rcx]
0x140072fb0  mov     rax, [rax+10h]
0x140072fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140072fb9  nop
0x140072fba  mov     rcx, [rsp+2A8h+var_268]
0x140072fbf  test    rcx, rcx
0x140072fc2  jz      short loc_140072FD6
0x140072fc4  mov     [rsp+2A8h+var_268], rdi
  ... truncated ...
```
