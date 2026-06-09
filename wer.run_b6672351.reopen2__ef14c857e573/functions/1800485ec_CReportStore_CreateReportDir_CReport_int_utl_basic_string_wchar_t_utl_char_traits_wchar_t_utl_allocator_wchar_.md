# CReportStore::CreateReportDir(CReport *,int,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800485ec`
- end: `0x180048a6e`
- name: `?CreateReportDir@CReportStore@@IEAAJPEAVCReport@@HPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1154`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004f8b8`
- `0x180051144`
- `0x180078ca8`

## callees

- `0x180007fd8`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x18001c368`
- `0x18001d718`
- `0x18001e0a8`
- `0x18001e288`
- `0x1800318c8`
- `0x18003f9a0`
- `0x18003fb94`
- `0x1800479ac`
- `0x1800485ec`
- `0x180048a74`
- `0x180048b34`
- `0x180048ba8`
- `0x180053300`
- `0x180053d3c`
- `0x18005dd11`
- `0x180075254`
- `0x180079fd0`
- `0x1800af010`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800489e2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800489d2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800489d2`

## string_xrefs

- `0x180048644`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x1800486c2`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`
- `0x1800486e9`: `onecore\windows\feedback\core\werdll\lib\reportstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CReportStore::CreateReportDir(__int64 a1, CReport *a2, int a3, LPCWSTR *a4)
{
  unsigned int v7; // ebx
  int v8; // r15d
  int v9; // eax
  __int64 v10; // rdx
  int v11; // eax
  const wchar_t *v12; // rcx
  int NewRestrictedFileOrDirectorySecurityAttributes; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 i; // rbx
  int SignatureParamByIndex; // eax
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  int v20; // r15d
  wchar_t *v21; // r9
  const wchar_t *v22; // rdx
  DWORD LastError; // eax
  int v25; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+44h] [rbp-BCh]
  int v28; // [rsp+48h] [rbp-B8h]
  int v29; // [rsp+4Ch] [rbp-B4h]
  wchar_t *v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  _QWORD v37[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v38[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v39[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE Src[1408]; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v41[352]; // [rsp+690h] [rbp+590h] BYREF
  __int16 v42; // [rsp+C10h] [rbp+B10h] BYREF
  char v43[38]; // [rsp+C12h] [rbp+B12h] BYREF
  int v44; // [rsp+C38h] [rbp+B38h]
  char *v45; // [rsp+C3Ch] [rbp+B3Ch]
  wchar_t v46[264]; // [rsp+1190h] [rbp+1090h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+13E8h] [rbp+12E8h]

  if ( a4 )
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v39);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v37);
    v30 = 0;
    v29 = *((_DWORD *)a2 + 2277);
    v28 = *((_DWORD *)a2 + 2276);
    v27 = *((_DWORD *)a2 + 2275);
    v8 = *((_DWORD *)a2 + 2274);
    v31 = 0;
    v9 = CReportStore::EnsureStoreRootDirectoryPresent(a1, (__int64)&v31);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 858;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v9,
        v25);
LABEL_46:
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v31);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v37);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
      utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v39);
      return v7;
    }
    v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35F,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)(unsigned int)v11,
        v25);
      v42 = 0;
      memset_0(v43, 0, 0x576u);
      memset_0(Src, 0, 0x578u);
      memcpy_0(v41, Src, 0x578u);
      v41[0] = 91751760;
      v41[10] = -1073741820;
      v41[12] = *(_DWORD *)(a1 + 8) == 2;
      v9 = UtilSendMessageToWersvc(v12, (struct _WERSVC_MSG *)v41, (struct _WERSVC_MSG *)&v42, 0);
      v7 = v9;
      if ( v9 < 0 )
      {
        v10 = 874;
        goto LABEL_8;
      }
      if ( v44 != -1073741824 )
      {
        if ( (int)v45 >= 0 )
          v7 = 0;
        else
          v7 = wil::details::in1diag3::Return_NtStatus(
                 retaddr,
                 (void *)0x36E,
                 (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
                 (const char *)(unsigned int)v45,
                 v25);
        goto LABEL_46;
      }
    }
    memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    SecurityAttributes.nLength = 24;
    NewRestrictedFileOrDirectorySecurityAttributes = CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(
                                                       (struct CSecurityAttributes *)&SecurityAttributes,
                                                       *((_DWORD *)a2 + 11657) != 0);
    v7 = NewRestrictedFileOrDirectorySecurityAttributes;
    if ( NewRestrictedFileOrDirectorySecurityAttributes < 0 )
    {
      v14 = 883;
LABEL_15:
      v15 = (unsigned int)NewRestrictedFileOrDirectorySecurityAttributes;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
        (const char *)v15,
        v25);
LABEL_17:
      CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityAttributes);
      goto LABEL_46;
    }
    NewRestrictedFileOrDirectorySecurityAttributes = CReport::GetSignatureParamsHash(a2, v38);
    v7 = NewRestrictedFileOrDirectorySecurityAttributes;
    if ( NewRestrictedFileOrDirectorySecurityAttributes < 0 )
    {
      v14 = 885;
      goto LABEL_15;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v37,
                             L"Report") )
    {
      v7 = -2147024882;
      v15 = 2147942414LL;
      v14 = 887;
      goto LABEL_16;
    }
    for ( i = 0; i != 6; ++i )
    {
      if ( LODWORD(qword_1800B5210[2 * i]) == *((_DWORD *)a2 + 1468) )
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          v37,
          (void *)qword_1800B5210[2 * i + 1]);
    }
    v46[0] = 0;
    SignatureParamByIndex = CReport::GetSignatureParamByIndex(a2, 0, 0, (const wchar_t **)&v30);
    v18 = retaddr;
    if ( SignatureParamByIndex >= 0 )
    {
      if ( !v30 )
        goto LABEL_33;
      SignatureParamByIndex = StringCchCopyW(v46, 0x104u, v30);
      v18 = retaddr;
      if ( SignatureParamByIndex >= 0 )
      {
        UtilSanitizeFileNameComponent(v46);
LABEL_33:
        NewRestrictedFileOrDirectorySecurityAttributes = CReport::GetUniqueIdentifier(a2, v39);
        v7 = NewRestrictedFileOrDirectorySecurityAttributes;
        if ( NewRestrictedFileOrDirectorySecurityAttributes >= 0 )
        {
          v20 = v29 ^ v28 ^ v27 ^ v8;
          v21 = v46;
          if ( !v46[0] )
            v21 = (wchar_t *)L"0";
          v22 = L"%s\\%s_%.16s_%s_%08x_cab_%s";
          if ( !a3 )
            v22 = L"%s\\%s_%.16s_%s_%08x_%s";
          NewRestrictedFileOrDirectorySecurityAttributes = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                                                             a4,
                                                             v22,
                                                             *(_QWORD *)(a1 + 16),
                                                             v37[0],
                                                             v21,
                                                             v38[0],
                                                             v20,
                                                             v39[0]);
          v7 = NewRestrictedFileOrDirectorySecurityAttributes;
          if ( NewRestrictedFileOrDirectorySecurityAttributes >= 0 )
          {
            if ( CreateDirectoryW(*a4, &SecurityAttributes) || (LastError = GetLastError()) == 0 )
            {
              CSecurityAttributes::~CSecurityAttributes((CSecurityAttributes *)&SecurityAttributes);
              v7 = 0;
              goto LABEL_46;
            }
            NewRestrictedFileOrDirectorySecurityAttributes = ERROR_HR_FROM_WIN32(LastError);
            v7 = NewRestrictedFileOrDirectorySecurityAttributes;
            if ( NewRestrictedFileOrDirectorySecurityAttributes >= 0 )
              goto LABEL_17;
            v14 = 941;
          }
          else
          {
            v14 = 927;
          }
        }
        else
        {
          v14 = 910;
        }
        goto LABEL_15;
      }
      v19 = 904;
    }
    else
    {
      v19 = 899;
    }
    wil::details::in1diag3::_Log_Hr(
      v18,
      (void *)v19,
      (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
      (const char *)(unsigned int)SignatureParamByIndex,
      v25);
    goto LABEL_33;
  }
  v7 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x342,
    (unsigned int)"onecore\\windows\\feedback\\core\\werdll\\lib\\reportstore.cpp",
    (const char *)0x80070057LL,
    v25);
  return v7;
}

```

## disassembly

```asm
0x1800485ec  mov     [rsp-8+arg_10], rbx
0x1800485f1  push    rbp
0x1800485f2  push    rsi
0x1800485f3  push    rdi
0x1800485f4  push    r12
0x1800485f6  push    r13
0x1800485f8  push    r14
0x1800485fa  push    r15
0x1800485fc  lea     rbp, [rsp-12B0h]
0x180048604  mov     eax, 13B0h
0x180048609  call    _alloca_probe
0x18004860e  sub     rsp, rax
0x180048611  mov     rax, cs:__security_cookie
0x180048618  xor     rax, rsp
0x18004861b  mov     [rbp+12E0h+var_40], rax
0x180048622  mov     r12, r9
0x180048625  mov     [rsp+13E0h+var_13A0], r8d
0x18004862a  mov     rsi, rdx
0x18004862d  mov     r14, rcx
0x180048630  test    r9, r9
0x180048633  jnz     short loc_18004865A
0x180048635  mov     rcx, [rbp+12E8h]; this
0x18004863c  mov     ebx, 80070057h
0x180048641  mov     r9d, ebx; char *
0x180048644  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x18004864b  mov     edx, 342h; void *
0x180048650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048655  jmp     loc_180048A41
0x18004865a  lea     rcx, [rbp+12E0h+var_12F0]; void *
0x18004865e  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180048663  nop
0x180048664  lea     rcx, [rbp+12E0h+var_1310]; void *
0x180048668  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18004866d  nop
0x18004866e  lea     rcx, [rbp+12E0h+var_1330]; void *
0x180048672  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180048677  nop
0x180048678  mov     [rsp+13E0h+var_1390], 0
0x180048681  mov     eax, [rsi+2394h]
0x180048687  mov     [rsp+13E0h+var_1394], eax
0x18004868b  mov     eax, [rsi+2390h]
0x180048691  mov     [rsp+13E0h+var_1398], eax
0x180048695  mov     eax, [rsi+238Ch]
0x18004869b  mov     [rsp+13E0h+var_139C], eax
0x18004869f  mov     r15d, [rsi+2388h]
0x1800486a6  mov     [rsp+13E0h+var_1388], 0
0x1800486af  lea     rdx, [rsp+13E0h+var_1388]
0x1800486b4  mov     rcx, r14
0x1800486b7  call    ?EnsureStoreRootDirectoryPresent@CReportStore@@IEAAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CReportStore::EnsureStoreRootDirectoryPresent(tlx::unique_any<tlx::file_handle_traits> *)
0x1800486bc  mov     ebx, eax
0x1800486be  test    eax, eax
0x1800486c0  jns     short loc_1800486D3
0x1800486c2  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800486c9  mov     edx, 35Ah
0x1800486ce  jmp     loc_180048793
0x1800486d3  mov     rax, [r14]
0x1800486d6  mov     rcx, r14
0x1800486d9  mov     rax, [rax+8]
0x1800486dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800486e2  mov     rcx, [rbp+12E8h]; this
0x1800486e9  lea     rdi, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werdl"...
0x1800486f0  test    eax, eax
0x1800486f2  jns     loc_1800487E1
0x1800486f8  mov     r9d, eax; char *
0x1800486fb  mov     r8, rdi; unsigned int
0x1800486fe  mov     edx, 35Fh; void *
0x180048703  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180048708  xor     eax, eax
0x18004870a  mov     [rbp+12E0h+var_7D0], ax
0x180048711  xor     edx, edx; Val
0x180048713  mov     r8d, 576h; Size
0x180048719  lea     rcx, [rbp+12E0h+var_7CE]; void *
0x180048720  call    memset_0
0x180048725  mov     ebx, 578h
0x18004872a  mov     r8d, ebx; Size
0x18004872d  xor     edx, edx; Val
0x18004872f  lea     rcx, [rbp+12E0h+Src]; void *
0x180048733  call    memset_0
0x180048738  lea     rcx, [rbp+12E0h+var_D50]; void *
0x18004873f  lea     rdx, [rbp+12E0h+Src]; Src
0x180048743  mov     r8d, ebx; Size
0x180048746  call    memcpy_0
0x18004874b  mov     [rbp+12E0h+var_D50], 5780550h
0x180048755  mov     [rbp+12E0h+var_D28], 0C0000004h
0x18004875f  xor     eax, eax
0x180048761  cmp     dword ptr [r14+8], 2
0x180048766  setz    al
0x180048769  mov     [rbp+12E0h+var_D20], eax
0x18004876f  xor     r9d, r9d; unsigned int
0x180048772  lea     r8, [rbp+12E0h+var_7D0]; struct _WERSVC_MSG *
0x180048779  lea     rdx, [rbp+12E0h+var_D50]; struct _WERSVC_MSG *
0x180048780  call    ?UtilSendMessageToWersvc@@YAJPEB_WPEAU_WERSVC_MSG@@1K@Z; UtilSendMessageToWersvc(wchar_t const *,_WERSVC_MSG *,_WERSVC_MSG *,ulong)
0x180048785  mov     ebx, eax
0x180048787  test    eax, eax
0x180048789  jns     short loc_1800487A7
0x18004878b  mov     r8, rdi; unsigned int
0x18004878e  mov     edx, 36Ah; void *
0x180048793  mov     r9d, eax; char *
0x180048796  mov     rcx, [rbp+12E8h]; this
0x18004879d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800487a2  jmp     loc_180048A19
0x1800487a7  cmp     [rbp+12E0h+var_7A8], 0C0000000h
0x1800487b1  jz      short loc_1800487E1
0x1800487b3  mov     r9d, dword ptr [rbp+12E0h+var_7A4]; char *
0x1800487ba  test    r9d, r9d
0x1800487bd  jns     short loc_1800487DA
0x1800487bf  mov     rcx, [rbp+12E8h]; this
0x1800487c6  mov     r8, rdi; unsigned int
0x1800487c9  mov     edx, 36Eh; void *
0x1800487ce  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800487d3  mov     ebx, eax
0x1800487d5  jmp     loc_180048A19
0x1800487da  xor     ebx, ebx
0x1800487dc  jmp     loc_180048A19
0x1800487e1  xorps   xmm0, xmm0
0x1800487e4  xor     eax, eax
0x1800487e6  movups  xmmword ptr [rsp+13E0h+SecurityAttributes.nLength], xmm0
0x1800487eb  mov     qword ptr [rsp+13E0h+SecurityAttributes.bInheritHandle], rax
0x1800487f0  xorps   xmm1, xmm1
0x1800487f3  movups  [rsp+13E0h+var_1368], xmm1
0x1800487f8  movups  [rbp+12E0h+var_1358], xmm1
0x1800487fc  mov     [rbp+12E0h+var_1348], rax
0x180048800  movdqa  [rbp+12E0h+var_1340], xmm0
0x180048805  mov     [rsp+13E0h+SecurityAttributes.nLength], 18h
0x18004880d  cmp     [rsi+0B624h], eax
0x180048813  setnz   dl; bool
0x180048816  lea     rcx, [rsp+13E0h+SecurityAttributes]; this
0x18004881b  call    ?GetNewRestrictedFileOrDirectorySecurityAttributes@CSecurityAttributes@@SAJAEAV1@_N@Z; CSecurityAttributes::GetNewRestrictedFileOrDirectorySecurityAttributes(CSecurityAttributes &,bool)
0x180048820  mov     ebx, eax
0x180048822  test    eax, eax
0x180048824  jns     short loc_18004884D
0x180048826  mov     edx, 373h; void *
0x18004882b  mov     r9d, eax; char *
0x18004882e  mov     r8, rdi; unsigned int
0x180048831  mov     rcx, [rbp+12E8h]; this
0x180048838  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004883d  nop
0x18004883e  lea     rcx, [rsp+13E0h+SecurityAttributes]; this
0x180048843  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x180048848  jmp     loc_180048A19
0x18004884d  lea     rdx, [rbp+12E0h+var_1310]
0x180048851  mov     rcx, rsi
0x180048854  call    ?GetSignatureParamsHash@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetSignatureParamsHash(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180048859  mov     ebx, eax
0x18004885b  test    eax, eax
0x18004885d  jns     short loc_180048866
0x18004885f  mov     edx, 375h
0x180048864  jmp     short loc_18004882B
0x180048866  lea     rdx, aReport; "Report"
0x18004886d  lea     rcx, [rbp+12E0h+var_1330]
0x180048871  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180048876  test    al, al
0x180048878  jnz     short loc_180048889
0x18004887a  mov     ebx, 8007000Eh
0x18004887f  mov     r9d, ebx
0x180048882  mov     edx, 377h
0x180048887  jmp     short loc_18004882E
0x180048889  xor     ebx, ebx
0x18004888b  lea     r13, qword_1800B5210
0x180048892  mov     rdx, rbx
0x180048895  add     rdx, rdx
0x180048898  mov     eax, [rsi+16F0h]
0x18004889e  cmp     [r13+rdx*8+0], eax
0x1800488a3  jnz     short loc_1800488B3
0x1800488a5  mov     rdx, [r13+rdx*8+8]
0x1800488aa  lea     rcx, [rbp+12E0h+var_1330]
0x1800488ae  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800488b3  inc     rbx
0x1800488b6  cmp     rbx, 6
0x1800488ba  jnz     short loc_180048892
0x1800488bc  xor     eax, eax
0x1800488be  mov     [rbp+12E0h+var_250], ax
0x1800488c5  lea     r9, [rsp+13E0h+var_1390]; wchar_t **
0x1800488ca  xor     r8d, r8d; wchar_t **
0x1800488cd  xor     edx, edx; unsigned int
0x1800488cf  mov     rcx, rsi; this
0x1800488d2  call    ?GetSignatureParamByIndex@CReport@@QEBAJKPEAPEB_W0@Z; CReport::GetSignatureParamByIndex(ulong,wchar_t const * *,wchar_t const * *)
0x1800488d7  mov     rcx, [rbp+12E8h]
0x1800488de  test    eax, eax
0x1800488e0  jns     short loc_1800488E9
0x1800488e2  mov     edx, 383h
0x1800488e7  jmp     short loc_180048914
0x1800488e9  mov     r8, [rsp+13E0h+var_1390]; wchar_t *
0x1800488ee  test    r8, r8
0x1800488f1  jz      short loc_18004892D
0x1800488f3  mov     edx, 104h; unsigned __int64
0x1800488f8  lea     rcx, [rbp+12E0h+var_250]; wchar_t *
0x1800488ff  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180048904  mov     rcx, [rbp+12E8h]; this
0x18004890b  test    eax, eax
0x18004890d  jns     short loc_180048921
0x18004890f  mov     edx, 388h; void *
0x180048914  mov     r8, rdi; unsigned int
0x180048917  mov     r9d, eax; char *
0x18004891a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004891f  jmp     short loc_18004892D
0x180048921  lea     rcx, [rbp+12E0h+var_250]; wchar_t *
0x180048928  call    ?UtilSanitizeFileNameComponent@@YAXPEA_W@Z; UtilSanitizeFileNameComponent(wchar_t *)
0x18004892d  lea     rdx, [rbp+12E0h+var_12F0]
0x180048931  mov     rcx, rsi
0x180048934  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180048939  mov     ebx, eax
0x18004893b  xor     esi, esi
0x18004893d  test    eax, eax
0x18004893f  mov     r13d, [rsp+13E0h+var_13A0]
0x180048944  jns     short loc_180048950
0x180048946  mov     edx, 38Eh
0x18004894b  jmp     loc_18004882B
0x180048950  xor     r15d, [rsp+13E0h+var_139C]
0x180048955  xor     r15d, [rsp+13E0h+var_1398]
0x18004895a  xor     r15d, [rsp+13E0h+var_1394]
0x18004895f  mov     rax, [rbp+12E0h+var_12F0]
0x180048963  mov     rcx, [rbp+12E0h+var_1310]
0x180048967  lea     r9, [rbp+12E0h+var_250]
0x18004896e  lea     rdx, a0; "0"
0x180048975  cmp     [rbp+12E0h+var_250], si
0x18004897c  cmovz   r9, rdx
0x180048980  lea     r8, aSS16sS08xS; "%s\\%s_%.16s_%s_%08x_%s"
0x180048987  lea     rdx, aSS16sS08xCabS; "%s\\%s_%.16s_%s_%08x_cab_%s"
0x18004898e  test    r13d, r13d
0x180048991  cmovz   rdx, r8
0x180048995  mov     [rsp+13E0h+var_13A8], rax
0x18004899a  mov     [rsp+13E0h+var_13B0], r15d
0x18004899f  mov     [rsp+13E0h+var_13B8], rcx
0x1800489a4  mov     [rsp+13E0h+var_13C0], r9
0x1800489a9  mov     r9, [rbp+12E0h+var_1330]
0x1800489ad  mov     r8, [r14+10h]
0x1800489b1  mov     rcx, r12
0x1800489b4  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x1800489b9  mov     ebx, eax
0x1800489bb  test    eax, eax
0x1800489bd  jns     short loc_1800489C9
0x1800489bf  mov     edx, 39Fh
0x1800489c4  jmp     loc_18004882B
0x1800489c9  lea     rdx, [rsp+13E0h+SecurityAttributes]; lpSecurityAttributes
0x1800489ce  mov     rcx, [r12]; lpPathName
0x1800489d2  call    cs:__imp_CreateDirectoryW
0x1800489d9  nop     dword ptr [rax+rax+00h]
0x1800489de  test    eax, eax
0x1800489e0  jnz     short loc_180048A0D
0x1800489e2  call    cs:__imp_GetLastError
0x1800489e9  nop     dword ptr [rax+rax+00h]
0x1800489ee  test    eax, eax
0x1800489f0  jz      short loc_180048A0D
0x1800489f2  mov     ecx, eax; unsigned int
0x1800489f4  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x1800489f9  mov     ebx, eax
0x1800489fb  test    eax, eax
0x1800489fd  jns     loc_18004883E
0x180048a03  mov     edx, 3ADh
0x180048a08  jmp     loc_18004882B
0x180048a0d  lea     rcx, [rsp+13E0h+SecurityAttributes]; this
0x180048a12  call    ??1CSecurityAttributes@@QEAA@XZ; CSecurityAttributes::~CSecurityAttributes(void)
0x180048a17  mov     ebx, esi
0x180048a19  lea     rcx, [rsp+13E0h+var_1388]
0x180048a1e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180048a23  nop
0x180048a24  lea     rcx, [rbp+12E0h+var_1330]; void *
0x180048a28  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180048a2d  nop
0x180048a2e  lea     rcx, [rbp+12E0h+var_1310]; void *
0x180048a32  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180048a37  nop
0x180048a38  lea     rcx, [rbp+12E0h+var_12F0]; void *
0x180048a3c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180048a41  mov     eax, ebx
0x180048a43  mov     rcx, [rbp+12E0h+var_40]
0x180048a4a  xor     rcx, rsp; StackCookie
0x180048a4d  call    __security_check_cookie
0x180048a52  mov     rbx, [rsp+13E0h+arg_10]
0x180048a5a  add     rsp, 13B0h
0x180048a61  pop     r15
0x180048a63  pop     r14
0x180048a65  pop     r13
0x180048a67  pop     r12
0x180048a69  pop     rdi
0x180048a6a  pop     rsi
0x180048a6b  pop     rbp
0x180048a6c  retn
```
