# _anonymous_namespace_::GetPathFromFullName

- ea: `0x140073388`
- end: `0x14007394c`
- name: `_anonymous_namespace_::GetPathFromFullName`
- size: `1476`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x140072ab0`

## callees

- `0x140005530`
- `0x140006338`
- `0x14000ccac`
- `0x14000d018`
- `0x14001c804`
- `0x14001f6b4`
- `0x140045250`
- `0x14005ff2c`
- `0x140060564`
- `0x140060e60`
- `0x140060f58`
- `0x14006d2c0`
- `0x14006fb70`
- `0x140072794`
- `0x140073388`
- `0x140081af0`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!GetPackagePath` at `0x140073467`
- `KERNEL32!GetPackagePath` at `0x1400734e7`
- `KERNEL32!GetPackagePath` at `0x140073467`
- `KERNEL32!GetPackagePath` at `0x1400734e7`
- `KERNEL32!PackageIdFromFullName` at `0x1400733ea`
- `KERNEL32!PackageIdFromFullName` at `0x14007342e`
- `KERNEL32!PackageIdFromFullName` at `0x1400733ea`
- `KERNEL32!PackageIdFromFullName` at `0x14007342e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400735ab`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400735ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140073593`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140073593`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall anonymous_namespace_::GetPathFromFullName(__int64 a1, __int64 a2)
{
  _QWORD *v4; // r14
  const WCHAR *v5; // rcx
  LONG v6; // eax
  unsigned int v7; // edi
  const WCHAR *v8; // rcx
  LONG v9; // eax
  signed int v10; // edi
  const PACKAGE_ID *v11; // r12
  LONG PackagePath; // eax
  unsigned int v13; // edi
  WCHAR *v14; // r9
  int v15; // edi
  bool v16; // sf
  __int64 result; // rax
  int v18; // edi
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64 *); // r14
  const WCHAR *v21; // rcx
  const WCHAR *v22; // rdi
  _QWORD *v23; // rax
  int v24; // esi
  __int64 FullNameAndPath; // rax
  _OWORD *v26; // rdi
  __int64 v27; // rcx
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // r10
  int v31; // eax
  __int64 v32; // r10
  int v33; // eax
  __int64 v34; // r10
  int v35; // eax
  __int64 v36; // r10
  int v37; // eax
  __int64 v38; // r10
  UINT32 bufferLength; // [rsp+30h] [rbp-1E8h] BYREF
  UINT32 pathLength; // [rsp+34h] [rbp-1E4h] BYREF
  __int64 v41; // [rsp+38h] [rbp-1E0h] BYREF
  __int64 v42; // [rsp+40h] [rbp-1D8h] BYREF
  const WCHAR *v43; // [rsp+48h] [rbp-1D0h] BYREF
  const WCHAR *v44; // [rsp+50h] [rbp-1C8h]
  _QWORD *v45; // [rsp+60h] [rbp-1B8h]
  _OWORD *v46; // [rsp+68h] [rbp-1B0h]
  _OWORD v47[2]; // [rsp+70h] [rbp-1A8h] BYREF
  BYTE *buffer[3]; // [rsp+90h] [rbp-188h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+A8h] [rbp-170h] BYREF
  _BYTE v50[40]; // [rsp+D0h] [rbp-148h] BYREF
  _BYTE v51[40]; // [rsp+F8h] [rbp-120h] BYREF
  _BYTE v52[40]; // [rsp+120h] [rbp-F8h] BYREF
  _BYTE v53[40]; // [rsp+148h] [rbp-D0h] BYREF
  _BYTE v54[48]; // [rsp+170h] [rbp-A8h] BYREF
  PWSTR path[2]; // [rsp+1A0h] [rbp-78h] BYREF
  __m128i si128; // [rsp+1B0h] [rbp-68h]
  char *v57; // [rsp+1C0h] [rbp-58h] BYREF

  v43 = (const WCHAR *)a2;
  v46 = (_OWORD *)a1;
  v44 = (const WCHAR *)a2;
  bufferLength = 0;
  v4 = (_QWORD *)(a2 + 24);
  v45 = (_QWORD *)(a2 + 24);
  if ( *(_QWORD *)(a2 + 24) <= 7u )
    v5 = (const WCHAR *)a2;
  else
    v5 = *(const WCHAR **)a2;
  v6 = PackageIdFromFullName(v5, 0, &bufferLength, 0);
  try
  {
    v7 = v6;
    if ( v6 && v6 != 122 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v29 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v30 + 16), 17, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v29, v7);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, v7);
      throw (ErrorCodeException *)pExceptionObject;
    }
    std::vector<unsigned char>::vector<unsigned char>(buffer, bufferLength);
    if ( *v4 <= 7u )
      v8 = (const WCHAR *)a2;
    else
      v8 = *(const WCHAR **)a2;
    v9 = PackageIdFromFullName(v8, 0, &bufferLength, buffer[0]);
    v10 = v9;
    if ( v9 > 0 )
      v10 = (unsigned __int16)v9 | 0x80070000;
    if ( v10 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v31 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v32 + 16), 18, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v31, v10);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v50, v10);
      throw (ErrorCodeException *)v50;
    }
    v11 = (const PACKAGE_ID *)buffer[0];
    pathLength = 0;
    PackagePath = GetPackagePath((const PACKAGE_ID *)buffer[0], 0, &pathLength, 0);
    v13 = PackagePath;
    if ( PackagePath && PackagePath != 122 )
    {
      if ( PackagePath > 0 )
        v13 = (unsigned __int16)PackagePath | 0x80070000;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v33 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v34 + 16), 19, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v33, v13);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v51, v13);
      throw (ErrorCodeException *)v51;
    }
    *(_OWORD *)path = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(path[0]) = 0;
    *(_QWORD *)&v47[0] = path;
    BYTE8(v47[0]) = 1;
    std::wstring::resize(path);
    v14 = (WCHAR *)path;
    if ( si128.m128i_i64[1] > 7uLL )
      v14 = path[0];
    v15 = GetPackagePath(v11, 0, &pathLength, v14);
    Private::Buffer<unsigned short>::~Buffer<unsigned short>(v47);
    v16 = v15 < 0;
    if ( v15 > 0 )
    {
      v15 = (unsigned __int16)v15 | 0x80070000;
      v16 = v15 < 0;
    }
    if ( v16 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v35 = std::wstring::c_str(a2);
        WPP_SF_Sd(*(_QWORD *)(v36 + 16), 20, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v35, v15);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v52, v15);
      throw (ErrorCodeException *)v52;
    }
    v47[0] = *(_OWORD *)path;
    v47[1] = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(path[0]) = 0;
    IO::Path::Path(a1, (__int64)v47);
    std::wstring::~wstring((char **)path);
    std::vector<char>::~vector<char>(buffer);
    result = a1;
  }
  catch ( std::exception )
  {
    v42 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Management.Deployment.PackageManager",
           0x2Cu,
           (HSTRING_HEADER *)&path[1],
           (HSTRING *)path) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v18 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
            (__int64)path[0],
            &v42);
    if ( v18 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          21,
          WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids,
          (unsigned int)v18);
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v53, v18);
      throw (ErrorCodeException *)v53;
    }
    v41 = 0;
    v19 = v42;
    v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 136LL);
    if ( *v45 <= 7u )
    {
      v22 = v44;
      v21 = v44;
    }
    else
    {
      v21 = *(const WCHAR **)v43;
      v22 = v43;
    }
    v43 = v21;
    v23 = (_QWORD *)Windows::Internal::StringReference::StringReference((__int64)path, &v43);
    v24 = v20(v19, *v23, &v41);
    if ( v24 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v37 = std::wstring::c_str(v22);
        WPP_SF_Sd(*(_QWORD *)(v38 + 16), 22, (unsigned int)WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids, v37, v24);
      }
      ErrorCodeException::ErrorCodeException((ErrorCodeException *)v54, v24);
      throw (ErrorCodeException *)v54;
    }
    FullNameAndPath = anonymous_namespace_::GetFullNameAndPath(path, v41);
    v26 = v46;
    *v46 = 0;
    *((_QWORD *)v26 + 2) = 0;
    *((_QWORD *)v26 + 3) = 0;
    *v26 = *(_OWORD *)(FullNameAndPath + 32);
    v26[1] = *(_OWORD *)(FullNameAndPath + 48);
    *(_QWORD *)(FullNameAndPath + 48) = 0;
    *(_QWORD *)(FullNameAndPath + 56) = 7;
    *(_WORD *)(FullNameAndPath + 32) = 0;
    std::wstring::~wstring(&v57);
    std::wstring::~wstring((char **)path);
    v27 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v28 = v42;
    if ( v42 )
    {
      v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    }
    return (__int64)v26;
  }
  return result;
}

```

## disassembly

```asm
0x140073388  mov     [rsp+arg_10], rbx
0x14007338d  push    rsi
0x14007338e  push    rdi
0x14007338f  push    r12
0x140073391  push    r14
0x140073393  push    r15
0x140073395  sub     rsp, 1F0h
0x14007339c  mov     rax, cs:__security_cookie
0x1400733a3  xor     rax, rsp
0x1400733a6  mov     [rsp+218h+var_38], rax
0x1400733ae  mov     rsi, rdx
0x1400733b1  mov     r15, rcx
0x1400733b4  mov     [rsp+218h+var_1D0], rdx
0x1400733b9  mov     [rsp+218h+var_1B0], rcx
0x1400733be  mov     [rsp+218h+var_1C8], rdx
0x1400733c3  xor     ebx, ebx
0x1400733c5  mov     [rsp+218h+bufferLength], ebx
0x1400733c9  lea     r14, [rdx+18h]
0x1400733cd  mov     [rsp+218h+var_1B8], r14
0x1400733d2  cmp     qword ptr [r14], 7
0x1400733d6  jbe     short loc_1400733DD
0x1400733d8  mov     rcx, [rdx]
0x1400733db  jmp     short loc_1400733E0
0x1400733dd  mov     rcx, rsi; packageFullName
0x1400733e0  xor     r9d, r9d; buffer
0x1400733e3  lea     r8, [rsp+218h+bufferLength]; bufferLength
0x1400733e8  xor     edx, edx; flags
0x1400733ea  call    cs:__imp_PackageIdFromFullName
0x1400733f0  mov     edi, eax
0x1400733f2  test    eax, eax
0x1400733f4  jz      short loc_1400733FF
0x1400733f6  cmp     eax, 7Ah ; 'z'
0x1400733f9  jnz     loc_1400736F7
0x1400733ff  mov     edx, [rsp+218h+bufferLength]
0x140073403  lea     rcx, [rsp+218h+buffer]
0x14007340b  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x140073410  nop
0x140073411  cmp     qword ptr [r14], 7
0x140073415  jbe     short loc_14007341C
0x140073417  mov     rcx, [rsi]
0x14007341a  jmp     short loc_14007341F
0x14007341c  mov     rcx, rsi; packageFullName
0x14007341f  mov     r9, [rsp+218h+buffer]; buffer
0x140073427  lea     r8, [rsp+218h+bufferLength]; bufferLength
0x14007342c  xor     edx, edx; flags
0x14007342e  call    cs:__imp_PackageIdFromFullName
0x140073434  mov     edi, eax
0x140073436  mov     r14d, 80070000h
0x14007343c  test    eax, eax
0x14007343e  jle     short loc_140073446
0x140073440  movzx   edi, ax
0x140073443  or      edi, r14d
0x140073446  test    edi, edi
0x140073448  js      loc_140073766
0x14007344e  mov     r12, [rsp+218h+buffer]
0x140073456  mov     [rsp+218h+pathLength], ebx
0x14007345a  xor     r9d, r9d; path
0x14007345d  lea     r8, [rsp+218h+pathLength]; pathLength
0x140073462  xor     edx, edx; reserved
0x140073464  mov     rcx, r12; packageId
0x140073467  call    cs:__imp_GetPackagePath
0x14007346d  mov     edi, eax
0x14007346f  test    eax, eax
0x140073471  jz      short loc_14007347C
0x140073473  cmp     eax, 7Ah ; 'z'
0x140073476  jnz     loc_1400737C7
0x14007347c  xorps   xmm0, xmm0
0x14007347f  movups  xmmword ptr [rsp+218h+path], xmm0
0x140073487  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14007348f  movdqu  [rsp+218h+var_68], xmm1
0x140073498  mov     word ptr [rsp+218h+path], bx
0x1400734a0  lea     rax, [rsp+218h+path]
0x1400734a8  mov     qword ptr [rsp+218h+var_1A8], rax
0x1400734ad  mov     byte ptr [rsp+218h+var_1A8+8], 1
0x1400734b2  mov     edx, [rsp+218h+pathLength]
0x1400734b6  lea     rcx, [rsp+218h+path]; Src
0x1400734be  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1400734c3  lea     r9, [rsp+218h+path]
0x1400734cb  cmp     qword ptr [rsp+218h+var_68+8], 7
0x1400734d4  cmova   r9, [rsp+218h+path]; path
0x1400734dd  lea     r8, [rsp+218h+pathLength]; pathLength
0x1400734e2  xor     edx, edx; reserved
0x1400734e4  mov     rcx, r12; packageId
0x1400734e7  call    cs:__imp_GetPackagePath
0x1400734ed  mov     edi, eax
0x1400734ef  lea     rcx, [rsp+218h+var_1A8]
0x1400734f4  call    ??1?$Buffer@G@Private@@QEAA@XZ; Private::Buffer<ushort>::~Buffer<ushort>(void)
0x1400734f9  test    edi, edi
0x1400734fb  jle     short loc_140073505
0x1400734fd  movzx   edi, di
0x140073500  or      edi, r14d
0x140073503  test    edi, edi
0x140073505  js      loc_140073833
0x14007350b  movups  xmm0, xmmword ptr [rsp+218h+path]
0x140073513  movups  [rsp+218h+var_1A8], xmm0
0x140073518  movups  xmm1, [rsp+218h+var_68]
0x140073520  movups  [rsp+218h+var_198], xmm1
0x140073528  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140073530  movdqu  [rsp+218h+var_68], xmm0
0x140073539  mov     word ptr [rsp+218h+path], bx
0x140073541  lea     rdx, [rsp+218h+var_1A8]
0x140073546  mov     rcx, r15
0x140073549  call    ??0Path@IO@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; IO::Path::Path(std::wstring)
0x14007354e  nop
0x14007354f  lea     rcx, [rsp+218h+path]
0x140073557  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14007355c  nop
0x14007355d  lea     rcx, [rsp+218h+buffer]
0x140073565  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x14007356a  mov     rax, r15
0x14007356d  jmp     loc_1400736CF
0x140073572  xor     ebx, ebx
0x140073574  mov     [rsp+218h+var_1D8], rbx
0x140073579  lea     r9, [rsp+218h+path]; string
0x140073581  lea     r8, [rsp+218h+path+8]; hstringHeader
0x140073589  lea     edx, [rbx+2Ch]; length
0x14007358c  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x140073593  call    cs:__imp_WindowsCreateStringReference
0x140073599  test    eax, eax
0x14007359b  jns     short loc_1400735B1
0x14007359d  xor     r9d, r9d; lpArguments
0x1400735a0  xor     r8d, r8d; nNumberOfArguments
0x1400735a3  lea     edx, [rbx+1]; dwExceptionFlags
0x1400735a6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1400735ab  call    cs:__imp_RaiseException
0x1400735b1  lea     rdx, [rsp+218h+var_1D8]
0x1400735b6  mov     rcx, [rsp+218h+path]
0x1400735be  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x1400735c3  mov     edi, eax
0x1400735c5  test    eax, eax
0x1400735c7  js      loc_140073895
0x1400735cd  mov     [rsp+218h+var_1E0], rbx
0x1400735d2  mov     rsi, [rsp+218h+var_1D8]
0x1400735d7  mov     rax, [rsi]
0x1400735da  mov     r14, [rax+88h]
0x1400735e1  mov     rax, [rsp+218h+var_1B8]
0x1400735e6  cmp     qword ptr [rax], 7
0x1400735ea  jbe     short loc_1400735F9
0x1400735ec  mov     rax, [rsp+218h+var_1D0]
0x1400735f1  mov     rcx, [rax]
0x1400735f4  mov     rdi, rax
0x1400735f7  jmp     short loc_140073601
0x1400735f9  mov     rdi, [rsp+218h+var_1C8]
0x1400735fe  mov     rcx, rdi
0x140073601  mov     [rsp+218h+var_1D0], rcx
0x140073606  lea     rdx, [rsp+218h+var_1D0]
0x14007360b  lea     rcx, [rsp+218h+path]
0x140073613  call    ??$?0PEBG@StringReference@Internal@Windows@@QEAA@AEBQEBGUdummy_t@_StringDetail@12@@Z; Windows::Internal::StringReference::StringReference(ushort const * const &,Windows::Internal::_StringDetail::dummy_t)
0x140073618  lea     r8, [rsp+218h+var_1E0]
0x14007361d  mov     rdx, [rax]
0x140073620  mov     rcx, rsi
0x140073623  mov     rax, r14
0x140073626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007362b  mov     esi, eax
0x14007362d  test    eax, eax
0x14007362f  js      loc_1400738EA
0x140073635  mov     rdx, [rsp+218h+var_1E0]
0x14007363a  lea     rcx, [rsp+218h+path]
0x140073642  call    _anonymous_namespace___GetFullNameAndPath
0x140073647  xorps   xmm0, xmm0
0x14007364a  mov     rdi, [rsp+218h+var_1B0]
0x14007364f  movups  xmmword ptr [rdi], xmm0
0x140073652  mov     [rdi+10h], rbx
0x140073656  mov     [rdi+18h], rbx
0x14007365a  movups  xmm0, xmmword ptr [rax+20h]
0x14007365e  movups  xmmword ptr [rdi], xmm0
0x140073661  movups  xmm1, xmmword ptr [rax+30h]
0x140073665  movups  xmmword ptr [rdi+10h], xmm1
0x140073669  mov     [rax+30h], rbx
0x14007366d  mov     qword ptr [rax+38h], 7
0x140073675  mov     [rax+20h], bx
0x140073679  lea     rcx, [rsp+218h+var_58]
0x140073681  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140073686  lea     rcx, [rsp+218h+path]
0x14007368e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140073693  nop
0x140073694  mov     rcx, [rsp+218h+var_1E0]
0x140073699  test    rcx, rcx
0x14007369c  jz      short loc_1400736B0
0x14007369e  mov     [rsp+218h+var_1E0], rbx
0x1400736a3  mov     rax, [rcx]
0x1400736a6  mov     rax, [rax+10h]
0x1400736aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400736af  nop
0x1400736b0  mov     rcx, [rsp+218h+var_1D8]
0x1400736b5  test    rcx, rcx
0x1400736b8  jz      short loc_1400736CC
0x1400736ba  mov     [rsp+218h+var_1D8], rbx
0x1400736bf  mov     rdx, [rcx]
0x1400736c2  mov     rax, [rdx+10h]
0x1400736c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400736cb  nop
0x1400736cc  mov     rax, rdi
0x1400736cf  mov     rcx, [rsp+218h+var_38]
0x1400736d7  xor     rcx, rsp; StackCookie
0x1400736da  call    __security_check_cookie
0x1400736df  mov     rbx, [rsp+218h+arg_10]
0x1400736e7  add     rsp, 1F0h
0x1400736ee  pop     r15
0x1400736f0  pop     r14
0x1400736f2  pop     r12
0x1400736f4  pop     rdi
0x1400736f5  pop     rsi
0x1400736f6  retn
0x1400736f7  test    eax, eax
0x1400736f9  jle     short loc_140073704
0x1400736fb  movzx   edi, ax
0x1400736fe  or      edi, 80070000h
0x140073704  lea     rax, WPP_GLOBAL_Control
0x14007370b  mov     r10, cs:WPP_GLOBAL_Control
0x140073712  cmp     r10, rax
0x140073715  jz      short loc_140073742
0x140073717  test    byte ptr [r10+1Ch], 1
0x14007371c  jz      short loc_140073742
0x14007371e  mov     rcx, rsi
0x140073721  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140073726  mov     edx, 11h
0x14007372b  mov     [rsp+218h+var_1F8], edi
0x14007372f  mov     r9, rax
0x140073732  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140073739  mov     rcx, [r10+10h]
0x14007373d  call    WPP_SF_Sd
0x140073742  mov     edx, edi; int
0x140073744  lea     rcx, [rsp+218h+pExceptionObject]; this
0x14007374c  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140073751  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140073758  lea     rcx, [rsp+218h+pExceptionObject]; pExceptionObject
0x140073760  call    _CxxThrowException_0
0x140073766  lea     rax, WPP_GLOBAL_Control
0x14007376d  mov     r10, cs:WPP_GLOBAL_Control
0x140073774  cmp     r10, rax
0x140073777  jz      short loc_1400737A4
0x140073779  test    byte ptr [r10+1Ch], 1
0x14007377e  jz      short loc_1400737A4
0x140073780  mov     rcx, rsi
0x140073783  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140073788  mov     edx, 12h
0x14007378d  mov     [rsp+218h+var_1F8], edi
0x140073791  mov     r9, rax
0x140073794  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x14007379b  mov     rcx, [r10+10h]
0x14007379f  call    WPP_SF_Sd
0x1400737a4  mov     edx, edi; int
0x1400737a6  lea     rcx, [rsp+218h+var_148]; this
0x1400737ae  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x1400737b3  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x1400737ba  lea     rcx, [rsp+218h+var_148]; pExceptionObject
0x1400737c2  call    _CxxThrowException_0
0x1400737c7  test    eax, eax
0x1400737c9  jle     short loc_1400737D1
0x1400737cb  movzx   edi, ax
0x1400737ce  or      edi, r14d
0x1400737d1  lea     rax, WPP_GLOBAL_Control
0x1400737d8  mov     r10, cs:WPP_GLOBAL_Control
0x1400737df  cmp     r10, rax
0x1400737e2  jz      short loc_14007380F
0x1400737e4  test    byte ptr [r10+1Ch], 1
0x1400737e9  jz      short loc_14007380F
0x1400737eb  mov     rcx, rsi
0x1400737ee  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1400737f3  mov     edx, 13h
0x1400737f8  mov     [rsp+218h+var_1F8], edi
0x1400737fc  mov     r9, rax
0x1400737ff  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140073806  mov     rcx, [r10+10h]
0x14007380a  call    WPP_SF_Sd
0x14007380f  mov     edx, edi; int
0x140073811  lea     rcx, [rsp+218h+var_120]; this
0x140073819  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x14007381e  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140073825  lea     rcx, [rsp+218h+var_120]; pExceptionObject
0x14007382d  call    _CxxThrowException_0
0x140073833  lea     rax, WPP_GLOBAL_Control
0x14007383a  mov     r10, cs:WPP_GLOBAL_Control
0x140073841  cmp     r10, rax
0x140073844  jz      short loc_140073871
0x140073846  test    byte ptr [r10+1Ch], 1
0x14007384b  jz      short loc_140073871
0x14007384d  mov     rcx, rsi
0x140073850  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x140073855  mov     edx, 14h
0x14007385a  mov     [rsp+218h+var_1F8], edi
0x14007385e  mov     r9, rax
0x140073861  lea     r8, WPP_0847ce96184e3f024f3fa6ccac8aefb7_Traceguids
0x140073868  mov     rcx, [r10+10h]
0x14007386c  call    WPP_SF_Sd
0x140073871  mov     edx, edi; int
0x140073873  lea     rcx, [rsp+218h+var_F8]; this
0x14007387b  call    ??0ErrorCodeException@@QEAA@J@Z; ErrorCodeException::ErrorCodeException(long)
0x140073880  lea     rdx, _TI2?AVErrorCodeException@@; pThrowInfo
0x140073887  lea     rcx, [rsp+218h+var_F8]; pExceptionObject
0x14007388f  call    _CxxThrowException_0
0x140073895  lea     rax, WPP_GLOBAL_Control
0x14007389c  mov     rcx, cs:WPP_GLOBAL_Control
0x1400738a3  cmp     rcx, rax
0x1400738a6  jz      short loc_1400738C6
0x1400738a8  test    byte ptr [rcx+1Ch], 1
0x1400738ac  jz      short loc_1400738C6
0x1400738ae  mov     edx, 15h
0x1400738b3  mov     r9d, edi
  ... truncated ...
```
