# SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a_

- ea: `0x180353128`
- end: `0x1803535fe`
- name: `SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a___`
- size: `1238`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1803561c4`

## callees

- `0x18003c5e4`
- `0x1800542a8`
- `0x18005f2f8`
- `0x18008943c`
- `0x1801045d4`
- `0x18013d330`
- `0x18013df8c`
- `0x1801b03c8`
- `0x180352484`
- `0x180352870`
- `0x180352ae4`
- `0x180352b00`
- `0x180352bc8`
- `0x180353078`
- `0x180353128`
- `0x180354d34`
- `0x180356520`
- `0x1803566a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180353269`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803532af`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180353269`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1803532af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18035321a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18035343a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803535b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803535cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18035321a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18035343a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353452`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353520`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180353538`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803535b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1803535cc`

## pseudocode

```c
__int64 __fastcall SetProgIdAndHash__lambda_8ae475174ef77ae8879de97baf49958a_(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6)
{
  int v8; // eax
  const unsigned __int16 *v9; // rcx
  unsigned int v10; // r9d
  int AssociationPath; // eax
  int SystemTimeFromRegKey; // ebx
  int MachineID; // eax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  const unsigned __int16 *v18; // rdx
  unsigned int AssociationsHashVersion; // eax
  void *v20; // rbx
  int v21; // edi
  __int64 v22; // rdx
  unsigned __int16 *v23; // rdi
  int v24; // eax
  int v25; // eax
  unsigned int v26; // esi
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  int dwOptionsb; // [rsp+20h] [rbp-E0h]
  REGSAM samDesired[2]; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  PHKEY phkResult; // [rsp+38h] [rbp-C8h]
  LPDWORD lpdwDisposition; // [rsp+40h] [rbp-C0h]
  int wHour; // [rsp+48h] [rbp-B8h]
  int wMinute; // [rsp+50h] [rbp-B0h]
  int wSecond; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v39; // [rsp+80h] [rbp-80h] BYREF
  const unsigned __int16 *v40; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME v41; // [rsp+90h] [rbp-70h] BYREF
  WCHAR SubKey[264]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+1F8h]

  v40 = a3;
  LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_(
    a6,
    L"SetDefault-ProgIdAndHash: Association=%ls, ProgId=%ls",
    a4,
    a5);
  memset_0(SubKey, 0, 0x208u);
  v8 = IsFileExt(a4);
  AssociationPath = _GetAssociationPath(v9, v8 != 0, SubKey, v10);
  SystemTimeFromRegKey = AssociationPath;
  if ( AssociationPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)AssociationPath,
      dwOptions);
    return (unsigned int)SystemTimeFromRegKey;
  }
  pv = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  MachineID = GetMachineID((unsigned __int16 **)&pv);
  SystemTimeFromRegKey = MachineID;
  if ( MachineID < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE2,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)MachineID,
      dwOptions);
    goto LABEL_6;
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  if ( RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x2001Bu, 0, &hKey, 0) == 1021 )
  {
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v15 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 1u, 0x2001Bu, 0, &hKey, 0);
    if ( v15 )
    {
      SystemTimeFromRegKey = wil::details::in1diag3::Return_Win32(
                               retaddr,
                               (void *)0xF9,
                               (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
                               (const char *)v15,
                               dwOptionsa);
LABEL_11:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_6:
      if ( pv )
        CoTaskMemFree(pv);
      return (unsigned int)SystemTimeFromRegKey;
    }
  }
  v16 = SHRegSetString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", &pszDefault);
  if ( (v16 & 0x1FFF0000) == 0x70000 )
    v16 = (unsigned __int16)v16;
  if ( v16 == 1021 )
  {
    SystemTimeFromRegKey = RegSetVolatileString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", &pszDefault);
    if ( SystemTimeFromRegKey < 0 )
    {
      v17 = 256;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)SystemTimeFromRegKey,
        dwOptionsa);
      goto LABEL_11;
    }
    SystemTimeFromRegKey = RegSetVolatileString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", a5);
    if ( SystemTimeFromRegKey < 0 )
    {
      v17 = 257;
      goto LABEL_17;
    }
  }
  else
  {
    SystemTimeFromRegKey = SHRegSetString(hKey, L"UserChoiceLatest\\ProgId", L"ProgId", a5);
    if ( SystemTimeFromRegKey < 0 )
    {
      v17 = 261;
      goto LABEL_17;
    }
  }
  v41 = 0;
  SystemTimeFromRegKey = GetSystemTimeFromRegKey(hKey, v18, &v41);
  if ( SystemTimeFromRegKey < 0 )
  {
    v17 = 266;
    goto LABEL_17;
  }
  v39 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::GetImpl'::`2'::impl) )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v39,
      0);
    AssociationsHashVersion = getAssociationsHashVersion();
    v20 = pv;
    v21 = HashAssociationRotation(AssociationsHashVersion, (const unsigned __int16 *)pv, a3, a4, a5, &v41, &v39);
    if ( v21 < 0 )
    {
      v22 = 271;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
        (const char *)(unsigned int)v21,
        dwOptionsb);
      if ( v39 )
        CoTaskMemFree(v39);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      if ( v20 )
        CoTaskMemFree(v20);
      return (unsigned int)v21;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v39,
      0);
    v20 = pv;
    v21 = HashAssociationRotation(1u, (const unsigned __int16 *)pv, a3, a4, a5, &v41, &v39);
    if ( v21 < 0 )
    {
      v22 = 275;
      goto LABEL_27;
    }
  }
  v23 = v39;
  v24 = SHRegSetString(hKey, L"UserChoiceLatest", L"Hash", v39);
  if ( (v24 & 0x1FFF0000) == 0x70000 )
    v24 = (unsigned __int16)v24;
  if ( v24 == 1021 && (v25 = RegSetVolatileString(hKey, L"UserChoiceLatest", L"Hash", v23), v26 = v25, v25 < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"OneCore\\Internal\\Shell\\inc\\userchoicecore.h",
      (const char *)(unsigned int)v25,
      dwOptionsb);
    if ( v23 )
      CoTaskMemFree(v23);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v20 )
      CoTaskMemFree(v20);
    return v26;
  }
  else
  {
    wSecond = v41.wSecond;
    wMinute = v41.wMinute;
    wHour = v41.wHour;
    LODWORD(lpdwDisposition) = v41.wDay;
    LODWORD(phkResult) = v41.wDayOfWeek;
    LODWORD(lpSecurityAttributes) = v41.wMonth;
    samDesired[0] = v41.wYear;
    LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_(
      a6,
      L"SetDefault-ProgIdAndHash: UserChoice Association=%ls, ProgId=%ls, U=%ls, T=%02d:%02d:%02d:%02d:%02d:%02d:%02d, H=%ls",
      a4,
      a5,
      v40,
      *(_QWORD *)samDesired,
      lpSecurityAttributes,
      phkResult,
      lpdwDisposition,
      wHour,
      wMinute,
      wSecond,
      v23);
    if ( v23 )
      CoTaskMemFree(v23);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    if ( v20 )
      CoTaskMemFree(v20);
    return 0;
  }
}

```

## disassembly

```asm
0x180353128  mov     [rsp-8+arg_0], rbx
0x18035312d  push    rbp
0x18035312e  push    rsi
0x18035312f  push    rdi
0x180353130  push    r12
0x180353132  push    r13
0x180353134  push    r14
0x180353136  push    r15
0x180353138  lea     rbp, [rsp-1C0h]
0x180353140  sub     rsp, 2C0h
0x180353147  mov     rax, cs:__security_cookie
0x18035314e  xor     rax, rsp
0x180353151  mov     [rbp+1F0h+var_40], rax
0x180353158  mov     r12, [rbp+1F0h+arg_20]
0x18035315f  lea     rdx, aSetdefaultProg; "SetDefault-ProgIdAndHash: Association=%"...
0x180353166  mov     rcx, [rbp+1F0h+arg_28]
0x18035316d  mov     r13, r9
0x180353170  mov     rdi, r8
0x180353173  mov     [rbp+1F0h+var_268], r8
0x180353177  mov     r9, r12
0x18035317a  mov     r8, r13
0x18035317d  call    LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9___; LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_
0x180353182  xor     edx, edx; Val
0x180353184  lea     rcx, [rbp+1F0h+SubKey]; void *
0x180353188  mov     r8d, 208h; Size
0x18035318e  call    memset_0
0x180353193  mov     rcx, r13; unsigned __int16 *
0x180353196  call    ?IsFileExt@@YAHPEBG@Z; IsFileExt(ushort const *)
0x18035319b  xor     r14d, r14d
0x18035319e  lea     r8, [rbp+1F0h+SubKey]; unsigned __int16 *
0x1803531a2  test    eax, eax
0x1803531a4  setnz   dl; bool
0x1803531a7  call    ?_GetAssociationPath@@YAJPEBG_NPEAGI@Z; _GetAssociationPath(ushort const *,bool,ushort *,uint)
0x1803531ac  mov     ebx, eax
0x1803531ae  test    eax, eax
0x1803531b0  jns     short loc_1803531D4
0x1803531b2  mov     rcx, [rbp+1F8h]; this
0x1803531b9  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1803531c0  mov     r9d, eax; char *
0x1803531c3  mov     edx, 0D7h; void *
0x1803531c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1803531cd  mov     eax, ebx
0x1803531cf  jmp     loc_1803535D4
0x1803531d4  xor     edx, edx
0x1803531d6  mov     [rsp+2F0h+pv], r14
0x1803531db  lea     rcx, [rsp+2F0h+pv]
0x1803531e0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1803531e5  lea     rcx, [rsp+2F0h+pv]; unsigned __int16 **
0x1803531ea  call    ?GetMachineID@@YAJPEAPEAG@Z; GetMachineID(ushort * *)
0x1803531ef  mov     ebx, eax
0x1803531f1  test    eax, eax
0x1803531f3  jns     short loc_180353222
0x1803531f5  mov     rcx, [rbp+1F8h]; this
0x1803531fc  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x180353203  mov     r9d, eax; char *
0x180353206  mov     edx, 0E2h; void *
0x18035320b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180353210  mov     rcx, [rsp+2F0h+pv]; pv
0x180353215  test    rcx, rcx
0x180353218  jz      short loc_1803531CD
0x18035321a  call    cs:__imp_CoTaskMemFree
0x180353220  jmp     short loc_1803531CD
0x180353222  xor     edx, edx
0x180353224  mov     [rsp+2F0h+hKey], r14
0x180353229  lea     rcx, [rsp+2F0h+hKey]
0x18035322e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180353233  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x180353238  lea     rax, [rsp+2F0h+hKey]
0x18035323d  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180353242  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180353246  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18035324b  mov     ebx, 2001Bh
0x180353250  mov     rsi, 0FFFFFFFF80000001h
0x180353257  mov     [rsp+2F0h+samDesired], ebx; samDesired
0x18035325b  xor     r9d, r9d; lpClass
0x18035325e  mov     [rsp+2F0h+dwOptions], r14d; int
0x180353263  xor     r8d, r8d; Reserved
0x180353266  mov     rcx, rsi; hKey
0x180353269  call    cs:__imp_RegCreateKeyExW
0x18035326f  cmp     eax, 3FDh
0x180353274  jnz     short loc_1803532E5
0x180353276  xor     edx, edx
0x180353278  lea     rcx, [rsp+2F0h+hKey]
0x18035327d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180353282  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x180353287  lea     rax, [rsp+2F0h+hKey]
0x18035328c  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180353291  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180353295  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18035329a  xor     r9d, r9d; lpClass
0x18035329d  mov     [rsp+2F0h+samDesired], ebx; samDesired
0x1803532a1  xor     r8d, r8d; Reserved
0x1803532a4  mov     rcx, rsi; hKey
0x1803532a7  mov     [rsp+2F0h+dwOptions], 1; unsigned int
0x1803532af  call    cs:__imp_RegCreateKeyExW
0x1803532b5  test    eax, eax
0x1803532b7  jz      short loc_1803532E5
0x1803532b9  mov     rcx, [rbp+1F8h]; this
0x1803532c0  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x1803532c7  mov     r9d, eax; char *
0x1803532ca  mov     edx, 0F9h; void *
0x1803532cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1803532d4  mov     ebx, eax
0x1803532d6  lea     rcx, [rsp+2F0h+hKey]
0x1803532db  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803532e0  jmp     loc_180353210
0x1803532e5  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1803532ea  lea     rsi, aProgid; "ProgId"
0x1803532f1  lea     r15, aUserchoicelate_0; "UserChoiceLatest\\ProgId"
0x1803532f8  mov     r8, rsi; unsigned __int16 *
0x1803532fb  mov     rdx, r15; unsigned __int16 *
0x1803532fe  lea     r9, pszDefault; unsigned __int16 *
0x180353305  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18035330a  mov     ecx, eax
0x18035330c  and     ecx, 1FFF0000h
0x180353312  cmp     ecx, 70000h
0x180353318  jnz     short loc_18035331D
0x18035331a  movzx   eax, ax
0x18035331d  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x180353322  mov     r8, rsi; unsigned __int16 *
0x180353325  mov     rdx, r15; unsigned __int16 *
0x180353328  cmp     eax, 3FDh
0x18035332d  jnz     short loc_180353381
0x18035332f  lea     r9, pszDefault; unsigned __int16 *
0x180353336  call    ?RegSetVolatileString@@YAJPEAUHKEY__@@PEBG11@Z; RegSetVolatileString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x18035333b  mov     ebx, eax
0x18035333d  test    eax, eax
0x18035333f  jns     short loc_180353361
0x180353341  mov     edx, 100h; void *
0x180353346  mov     rcx, [rbp+1F8h]; this
0x18035334d  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x180353354  mov     r9d, ebx; char *
0x180353357  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18035335c  jmp     loc_1803532D6
0x180353361  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x180353366  mov     r9, r12; unsigned __int16 *
0x180353369  mov     r8, rsi; unsigned __int16 *
0x18035336c  mov     rdx, r15; unsigned __int16 *
0x18035336f  call    ?RegSetVolatileString@@YAJPEAUHKEY__@@PEBG11@Z; RegSetVolatileString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180353374  mov     ebx, eax
0x180353376  test    eax, eax
0x180353378  jns     short loc_180353396
0x18035337a  mov     edx, 101h
0x18035337f  jmp     short loc_180353346
0x180353381  mov     r9, r12; unsigned __int16 *
0x180353384  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x180353389  mov     ebx, eax
0x18035338b  test    eax, eax
0x18035338d  jns     short loc_180353396
0x18035338f  mov     edx, 105h
0x180353394  jmp     short loc_180353346
0x180353396  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18035339b  lea     r8, [rbp+1F0h+var_260]; struct _SYSTEMTIME *
0x18035339f  xorps   xmm0, xmm0
0x1803533a2  movups  xmmword ptr [rbp+1F0h+var_260.wYear], xmm0
0x1803533a6  call    ?GetSystemTimeFromRegKey@@YAJPEAUHKEY__@@PEBGPEAU_SYSTEMTIME@@@Z; GetSystemTimeFromRegKey(HKEY__ *,ushort const *,_SYSTEMTIME *)
0x1803533ab  mov     ebx, eax
0x1803533ad  test    eax, eax
0x1803533af  jns     short loc_1803533B8
0x1803533b1  mov     edx, 10Ah
0x1803533b6  jmp     short loc_180353346
0x1803533b8  mov     [rbp+1F0h+var_270], r14
0x1803533bc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2> `wil::Feature<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::GetImpl(void)'::`2'::impl
0x1803533c3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppDefaultHashRotationV1ToV2>::__private_IsEnabled(void)
0x1803533c8  xor     edx, edx
0x1803533ca  lea     rcx, [rbp+1F0h+var_270]
0x1803533ce  test    al, al
0x1803533d0  jz      loc_18035345F
0x1803533d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1803533db  call    ?getAssociationsHashVersion@@YAKXZ; getAssociationsHashVersion(void)
0x1803533e0  mov     rbx, [rsp+2F0h+pv]
0x1803533e5  lea     rcx, [rbp+1F0h+var_270]
0x1803533e9  mov     [rsp+2F0h+lpSecurityAttributes], rcx; unsigned __int16 **
0x1803533ee  mov     r9, r13; unsigned __int16 *
0x1803533f1  lea     rcx, [rbp+1F0h+var_260]
0x1803533f5  mov     r8, rdi; unsigned __int16 *
0x1803533f8  mov     qword ptr [rsp+2F0h+samDesired], rcx; struct _SYSTEMTIME *
0x1803533fd  mov     rdx, rbx; unsigned __int16 *
0x180353400  mov     ecx, eax; unsigned int
0x180353402  mov     qword ptr [rsp+2F0h+dwOptions], r12; int
0x180353407  call    ?HashAssociationRotation@@YAJIPEBG000AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociationRotation(uint,ushort const *,ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x18035340c  mov     edi, eax
0x18035340e  test    eax, eax
0x180353410  jns     loc_1803534A3
0x180353416  mov     edx, 10Fh; void *
0x18035341b  mov     rcx, [rbp+1F8h]; this
0x180353422  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x180353429  mov     r9d, edi; char *
0x18035342c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180353431  mov     rcx, [rbp+1F0h+var_270]; pv
0x180353435  test    rcx, rcx
0x180353438  jz      short loc_180353440
0x18035343a  call    cs:__imp_CoTaskMemFree
0x180353440  lea     rcx, [rsp+2F0h+hKey]
0x180353445  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18035344a  test    rbx, rbx
0x18035344d  jz      short loc_180353458
0x18035344f  mov     rcx, rbx; pv
0x180353452  call    cs:__imp_CoTaskMemFree
0x180353458  mov     eax, edi
0x18035345a  jmp     loc_1803535D4
0x18035345f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180353464  mov     rbx, [rsp+2F0h+pv]
0x180353469  lea     rax, [rbp+1F0h+var_270]
0x18035346d  mov     [rsp+2F0h+lpSecurityAttributes], rax; unsigned __int16 **
0x180353472  mov     r9, r13; unsigned __int16 *
0x180353475  lea     rax, [rbp+1F0h+var_260]
0x180353479  mov     r8, rdi; unsigned __int16 *
0x18035347c  mov     qword ptr [rsp+2F0h+samDesired], rax; struct _SYSTEMTIME *
0x180353481  mov     rdx, rbx; unsigned __int16 *
0x180353484  mov     ecx, 1; unsigned int
0x180353489  mov     qword ptr [rsp+2F0h+dwOptions], r12; unsigned __int16 *
0x18035348e  call    ?HashAssociationRotation@@YAJIPEBG000AEBU_SYSTEMTIME@@PEAPEAG@Z; HashAssociationRotation(uint,ushort const *,ushort const *,ushort const *,ushort const *,_SYSTEMTIME const &,ushort * *)
0x180353493  mov     edi, eax
0x180353495  test    eax, eax
0x180353497  jns     short loc_1803534A3
0x180353499  mov     edx, 113h
0x18035349e  jmp     loc_18035341B
0x1803534a3  mov     rdi, [rbp+1F0h+var_270]
0x1803534a7  lea     r8, aHash; "Hash"
0x1803534ae  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1803534b3  lea     rdx, aUserchoicelate; "UserChoiceLatest"
0x1803534ba  mov     r9, rdi; unsigned __int16 *
0x1803534bd  call    ?SHRegSetString@@YAJPEAUHKEY__@@PEBG11@Z; SHRegSetString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1803534c2  mov     ecx, eax
0x1803534c4  and     ecx, 1FFF0000h
0x1803534ca  cmp     ecx, 70000h
0x1803534d0  jnz     short loc_1803534D5
0x1803534d2  movzx   eax, ax
0x1803534d5  cmp     eax, 3FDh
0x1803534da  jnz     short loc_180353545
0x1803534dc  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1803534e1  lea     r8, aHash; "Hash"
0x1803534e8  mov     r9, rdi; unsigned __int16 *
0x1803534eb  lea     rdx, aUserchoicelate; "UserChoiceLatest"
0x1803534f2  call    ?RegSetVolatileString@@YAJPEAUHKEY__@@PEBG11@Z; RegSetVolatileString(HKEY__ *,ushort const *,ushort const *,ushort const *)
0x1803534f7  mov     esi, eax
0x1803534f9  test    eax, eax
0x1803534fb  jns     short loc_180353545
0x1803534fd  mov     rcx, [rbp+1F8h]; this
0x180353504  lea     r8, aOnecoreInterna; "OneCore\\Internal\\Shell\\inc\\userchoi"...
0x18035350b  mov     r9d, eax; char *
0x18035350e  mov     edx, 11Ah; void *
0x180353513  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180353518  test    rdi, rdi
0x18035351b  jz      short loc_180353526
0x18035351d  mov     rcx, rdi; pv
0x180353520  call    cs:__imp_CoTaskMemFree
0x180353526  lea     rcx, [rsp+2F0h+hKey]
0x18035352b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180353530  test    rbx, rbx
0x180353533  jz      short loc_18035353E
0x180353535  mov     rcx, rbx; pv
0x180353538  call    cs:__imp_CoTaskMemFree
0x18035353e  mov     eax, esi
0x180353540  jmp     loc_1803535D4
0x180353545  movzx   eax, [rbp+1F0h+var_260.wSecond]
0x180353549  mov     r9, r12
0x18035354c  movzx   edx, [rbp+1F0h+var_260.wMinute]
0x180353550  mov     r8, r13
0x180353553  movzx   r10d, [rbp+1F0h+var_260.wHour]
0x180353558  movzx   r11d, [rbp+1F0h+var_260.wDay]
0x18035355d  movzx   esi, [rbp+1F0h+var_260.wDayOfWeek]
0x180353561  movzx   r14d, [rbp+1F0h+var_260.wMonth]
0x180353566  movzx   r15d, [rbp+1F0h+var_260.wYear]
0x18035356b  mov     rcx, [rbp+1F0h+arg_28]
0x180353572  mov     [rsp+2F0h+var_290], rdi
0x180353577  mov     [rsp+2F0h+var_298], eax
0x18035357b  mov     rax, [rbp+1F0h+var_268]
0x18035357f  mov     [rsp+2F0h+var_2A0], edx
0x180353583  lea     rdx, aSetdefaultProg_0; "SetDefault-ProgIdAndHash: UserChoice As"...
0x18035358a  mov     [rsp+2F0h+var_2A8], r10d
0x18035358f  mov     dword ptr [rsp+2F0h+lpdwDisposition], r11d
0x180353594  mov     dword ptr [rsp+2F0h+phkResult], esi
0x180353598  mov     dword ptr [rsp+2F0h+lpSecurityAttributes], r14d
0x18035359d  mov     [rsp+2F0h+samDesired], r15d
0x1803535a2  mov     qword ptr [rsp+2F0h+dwOptions], rax
0x1803535a7  call    LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9___; LogAppDefaultMessage__lambda_baf5d6d1cf956a8c951be3cc9f691ba9_
0x1803535ac  test    rdi, rdi
0x1803535af  jz      short loc_1803535BA
0x1803535b1  mov     rcx, rdi; pv
0x1803535b4  call    cs:__imp_CoTaskMemFree
0x1803535ba  lea     rcx, [rsp+2F0h+hKey]
0x1803535bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1803535c4  test    rbx, rbx
0x1803535c7  jz      short loc_1803535D2
0x1803535c9  mov     rcx, rbx; pv
0x1803535cc  call    cs:__imp_CoTaskMemFree
0x1803535d2  xor     eax, eax
0x1803535d4  mov     rcx, [rbp+1F0h+var_40]
0x1803535db  xor     rcx, rsp; StackCookie
0x1803535de  call    __security_check_cookie
0x1803535e3  mov     rbx, [rsp+2F0h+arg_0]
0x1803535eb  add     rsp, 2C0h
0x1803535f2  pop     r15
0x1803535f4  pop     r14
0x1803535f6  pop     r13
0x1803535f8  pop     r12
0x1803535fa  pop     rdi
0x1803535fb  pop     rsi
  ... truncated ...
```
