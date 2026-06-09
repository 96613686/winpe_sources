# CDescriptionManager::GetContent(_GUID const &,ushort const *,int,long *,ushort * * *,long *,uchar * *)

- ea: `0x180012310`
- end: `0x18001316f`
- name: `?GetContent@CDescriptionManager@@UEAAJAEBU_GUID@@PEBGHPEAJPEAPEAPEAG2PEAPEAE@Z`
- size: `3679`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _GUID *, const unsigned __int16 *, int, int *, unsigned __int16 ***, int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180011bfc`
- `0x180012310`
- `0x180013180`
- `0x18001347c`
- `0x1800134b8`
- `0x180015d90`
- `0x18001a060`
- `0x18001f3f0`
- `0x180020bc0`
- `0x180023790`
- `0x18002ab08`
- `0x180038324`
- `0x180038ce4`
- `0x18003a560`
- `0x18003ae80`
- `0x18003fea4`
- `0x180043124`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012633`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012ec2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012633`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012b66`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180012ec2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800125f2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800125f2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013069`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180013069`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012585`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012426`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800124e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180012585`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001246e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001257c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001291c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012af2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001246e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012535`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001257c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800125d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001291c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012951`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800129d8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800124ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800124ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012693`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012773`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800127a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012850`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012a70`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800130bb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012984`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012996`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800129a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012c95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012d04`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800130bb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012837`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001289a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180012837`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18001289a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b4f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012b3e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180012b3e`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012749`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180012749`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012732`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180012732`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18001303d`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x18001303d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012912`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ba4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800123c8`
- `OLEAUT32!__imp_SysFreeString` at `0x180012912`
- `OLEAUT32!__imp_SysFreeString` at `0x180012ba4`
- `OLEAUT32!__imp_SysStringLen` at `0x18001280c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001280c`

## string_xrefs

- `0x1800127e4`: `Content-Type: text/xml; charset="utf-8"`

## pseudocode

```c
__int64 __fastcall CDescriptionManager::GetContent(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        int *a5,
        unsigned __int16 ***a6,
        int *a7,
        unsigned __int8 **a8)
{
  struct _RTL_CRITICAL_SECTION *p_OwningThread; // rbx
  OLECHAR *v13; // r12
  int v14; // r14d
  int IsAllowedCOMCallLocality; // edi
  int i; // eax
  _QWORD *v17; // rdx
  __int64 v18; // rcx
  struct IUPnPDeviceControlHttpHeaders **v19; // rdi
  CDescriptionManager *v20; // rcx
  unsigned __int64 v21; // rax
  const wchar_t **v22; // rax
  int v23; // edx
  __int64 v24; // rsi
  _QWORD *v25; // rcx
  __int64 v26; // rax
  BSTR *v27; // r12
  unsigned __int16 **v28; // r13
  LONG j; // ecx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r9
  __int64 v31; // r8
  unsigned __int64 v32; // rax
  LPCWSTR *v33; // r12
  wchar_t *v34; // rbx
  const wchar_t *v35; // rcx
  size_t v36; // r8
  wchar_t *v37; // r15
  size_t v38; // rdx
  size_t *v39; // r8
  __int64 v40; // rax
  size_t v41; // r15
  const wchar_t *v42; // rax
  size_t v43; // r8
  HRESULT v44; // eax
  size_t v45; // rdx
  wchar_t *v46; // rcx
  size_t *v47; // r8
  const wchar_t *v48; // r9
  HRESULT v49; // r12d
  bool v50; // zf
  unsigned int v51; // r12d
  HANDLE FileW; // r15
  DWORD FileSize; // eax
  void *v54; // r12
  const wchar_t *v55; // rax
  size_t v56; // r8
  size_t v57; // rdx
  wchar_t *v58; // rcx
  size_t *v59; // r8
  STRSAFE_PCNZWCH *v60; // r11
  bool v61; // sf
  UINT v62; // eax
  const WCHAR *v63; // r8
  int v64; // eax
  __int64 v65; // r13
  unsigned int v66; // r15d
  void *v67; // rbx
  bool v69; // sf
  unsigned __int16 ***v70; // rax
  int *v71; // rcx
  _DWORD *v72; // rdx
  _QWORD *v73; // r8
  unsigned int v75; // r15d
  unsigned int k; // ebx
  wchar_t *v77; // rcx
  STRSAFE_PCNZWCH *v78; // rbx
  size_t v79; // rsi
  const wchar_t *v80; // rax
  size_t v81; // rdx
  wchar_t *v82; // rcx
  size_t *v83; // r8
  STRSAFE_PCNZWCH *v84; // r11
  STRSAFE_PCNZWCH v85; // r10
  unsigned int v86; // eax
  DWORD v88; // r12d
  int AdditionalResponseHeadersAndCount; // eax
  signed int LastError; // eax
  STRSAFE_PCNZWCH v91; // rcx
  STRSAFE_PCNZWCH v92; // rcx
  const wchar_t *v93; // r15
  unsigned int v94; // r14d
  wchar_t *v95; // rax
  wchar_t *v96; // rbx
  unsigned __int64 v97; // r13
  unsigned __int16 **v98; // r12
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-E0h]
  DWORD nNumberOfBytesToRead; // [rsp+40h] [rbp-C0h]
  unsigned int v101; // [rsp+44h] [rbp-BCh]
  int v102; // [rsp+48h] [rbp-B8h]
  const wchar_t **cchMax; // [rsp+50h] [rbp-B0h]
  unsigned __int16 **pv; // [rsp+58h] [rbp-A8h]
  int cchWideChar[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v106; // [rsp+68h] [rbp-98h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-90h] BYREF
  LPVOID v108; // [rsp+78h] [rbp-88h]
  unsigned __int16 ***v109; // [rsp+80h] [rbp-80h]
  int *v110; // [rsp+88h] [rbp-78h]
  int *v111; // [rsp+90h] [rbp-70h]
  unsigned __int8 **v112; // [rsp+98h] [rbp-68h]
  int v113; // [rsp+A0h] [rbp-60h]
  LPCWSTR *v114; // [rsp+A8h] [rbp-58h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B0h] [rbp-50h]
  wchar_t pszSrc[18]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR LocaleName[110]; // [rsp+E4h] [rbp-1Ch] BYREF

  p_OwningThread = (struct _RTL_CRITICAL_SECTION *)&this->OwningThread;
  v110 = a5;
  v109 = a6;
  v111 = a7;
  v112 = a8;
  v113 = a4;
  lpCriticalSection = (LPCRITICAL_SECTION)&this->OwningThread;
  ATL::CComSafeDeleteCriticalSection::Lock((ATL::CComSafeDeleteCriticalSection *)&this->OwningThread);
  v13 = 0;
  v14 = (a4 != 0) + 2;
  bstrString = 0;
  v102 = v14;
  v106 = 0;
  if ( !a6 )
  {
    LeaveCriticalSection(p_OwningThread);
    return 2147942487LL;
  }
  IsAllowedCOMCallLocality = HrIsAllowedCOMCallLocality(1);
  if ( IsAllowedCOMCallLocality < 0 )
  {
    SysFreeString(0);
    goto LABEL_4;
  }
  cchMax = 0;
  nNumberOfBytesToRead = 0;
  v108 = 0;
  EnterCriticalSection(this + 14);
  for ( i = 0; ; ++i )
  {
    if ( i >= SLODWORD(this[2].LockSemaphore) )
    {
      LeaveCriticalSection(this + 14);
LABEL_13:
      v102 = v14;
      goto LABEL_14;
    }
    v17 = (char *)this[2].OwningThread + 16 * i;
    v18 = *(_QWORD *)&a2->Data1 - *v17;
    if ( *(_QWORD *)&a2->Data1 == *v17 )
      v18 = *(_QWORD *)a2->Data4 - v17[1];
    if ( !v18 )
      break;
  }
  v19 = (struct IUPnPDeviceControlHttpHeaders **)(this[2].SpinCount + 8LL * i);
  LeaveCriticalSection(this + 14);
  if ( !v19 || !*v19 )
    goto LABEL_13;
  AdditionalResponseHeadersAndCount = CDescriptionManager::HrGetAdditionalResponseHeadersAndCount(
                                        v20,
                                        *v19,
                                        a3,
                                        &bstrString,
                                        &v106);
  v13 = bstrString;
  if ( AdditionalResponseHeadersAndCount >= 0 )
  {
    v14 += v106;
    goto LABEL_13;
  }
LABEL_14:
  if ( v14 < 0 )
  {
    v22 = 0;
LABEL_149:
    IsAllowedCOMCallLocality = -2147024882;
    goto LABEL_150;
  }
  v21 = 8LL * (unsigned int)v14;
  if ( v21 <= 0xFFFFFFFF )
  {
    IsAllowedCOMCallLocality = 0;
    v22 = (const wchar_t **)CoTaskMemAlloc((unsigned int)v21);
    cchMax = v22;
    if ( v22 )
      goto LABEL_17;
    goto LABEL_149;
  }
  v22 = 0;
  IsAllowedCOMCallLocality = -2147024362;
LABEL_150:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
    v22 = cchMax;
  }
LABEL_17:
  if ( IsAllowedCOMCallLocality < 0 )
  {
    v71 = v110;
    v28 = (unsigned __int16 **)v22;
    v70 = v109;
    v72 = v111;
    v73 = v112;
    goto LABEL_75;
  }
  v101 = 0;
  memset_0(cchMax, 0, 8LL * v14);
  EnterCriticalSection(this + 14);
  v23 = 0;
  pv = (unsigned __int16 **)cchMax;
  while ( 1 )
  {
    v24 = -1;
    if ( v23 >= SLODWORD(this[1].SpinCount) )
    {
      LeaveCriticalSection(this + 14);
      goto LABEL_28;
    }
    v25 = (char *)this[1].LockSemaphore + 16 * v23;
    v26 = *(_QWORD *)&a2->Data1 - *v25;
    if ( *(_QWORD *)&a2->Data1 == *v25 )
      v26 = *(_QWORD *)a2->Data4 - v25[1];
    if ( !v26 )
      break;
    ++v23;
  }
  v27 = (BSTR *)((char *)this[2].DebugInfo + 8 * v23);
  LeaveCriticalSection(this + 14);
  if ( v27 )
  {
    v28 = (unsigned __int16 **)cchMax;
    if ( !cchMax )
    {
      IsAllowedCOMCallLocality = -2147467261;
      goto LABEL_113;
    }
    if ( !is_mul_ok(0x28u, 2u) )
    {
      IsAllowedCOMCallLocality = -2147024362;
      pv = (unsigned __int16 **)cchMax;
      v102 = v14;
      goto LABEL_155;
    }
    v55 = (const wchar_t *)CoTaskMemAlloc(0x50u);
    *cchMax = v55;
    pv = (unsigned __int16 **)cchMax;
    v102 = v14;
    if ( v55 )
    {
      IsAllowedCOMCallLocality = StringValidateDestW(*cchMax, 0x28u, v56);
      if ( IsAllowedCOMCallLocality < 0 )
        *v58 = 0;
      else
        IsAllowedCOMCallLocality = StringCopyWorkerW(
                                     v58,
                                     v57,
                                     v59,
                                     L"Content-Type: text/xml; charset=\"utf-8\"",
                                     *(size_t *)dwCreationDisposition);
      v61 = IsAllowedCOMCallLocality < 0;
      if ( !IsAllowedCOMCallLocality )
        goto LABEL_62;
      v91 = WPP_GLOBAL_Control;
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
LABEL_155:
      v91 = WPP_GLOBAL_Control;
      v60 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
          (unsigned int)IsAllowedCOMCallLocality);
        v91 = WPP_GLOBAL_Control;
        v60 = &WPP_GLOBAL_Control;
      }
    }
    if ( v91 != (STRSAFE_PCNZWCH)v60 && (v91[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)v91 + 2),
        12,
        WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    v61 = IsAllowedCOMCallLocality < 0;
LABEL_62:
    if ( v61 )
      goto LABEL_113;
    v101 = 1;
    v62 = SysStringLen(*v27);
    v63 = *v27;
    cchWideChar[0] = v62;
    v64 = WideCharToMultiByte(0xFDE9u, 0, v63, v62, 0, 0, 0, 0);
    v65 = v64;
    v66 = v64 + 1;
    if ( v64 + 1 >= 0 && (v67 = CoTaskMemAlloc(v66)) != 0 )
    {
      IsAllowedCOMCallLocality = 0;
      if ( !WideCharToMultiByte(0xFDE9u, 0, *v27, cchWideChar[0], (LPSTR)v67, v66, 0, 0) )
      {
        IsAllowedCOMCallLocality = HrFromLastWin32Error();
        if ( IsAllowedCOMCallLocality < 0 )
        {
          CoTaskMemFree(v67);
          v28 = pv;
          k = 0;
          v75 = 1;
          goto LABEL_82;
        }
      }
      v108 = v67;
      v88 = v65;
      nNumberOfBytesToRead = v65;
      *((_BYTE *)v67 + v65) = 0;
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, 2147942414LL);
      v88 = 0;
    }
    v28 = pv;
    goto LABEL_70;
  }
LABEL_28:
  EnterCriticalSection(this + 14);
  for ( j = 0; ; ++j )
  {
    if ( j >= this[4].LockCount )
    {
      LeaveCriticalSection(this + 14);
      goto LABEL_79;
    }
    DebugInfo = this[4].DebugInfo;
    v31 = 16LL * j;
    v32 = *(_QWORD *)&a2->Data1 - *(_QWORD *)((char *)&DebugInfo->Type + v31);
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)((char *)&DebugInfo->Type + v31) )
      v32 = *(_QWORD *)a2->Data4 - *(unsigned __int64 *)((char *)&DebugInfo->CriticalSection + v31);
    if ( !v32 )
      break;
  }
  v114 = (LPCWSTR *)((char *)this[4].OwningThread + v31);
  v33 = v114;
  LeaveCriticalSection(this + 14);
  if ( !v33 )
  {
LABEL_79:
    v28 = (unsigned __int16 **)cchMax;
    IsAllowedCOMCallLocality = 1;
    goto LABEL_80;
  }
  v34 = 0;
  *(_QWORD *)cchWideChar = 0;
  v37 = (wchar_t *)malloc(0x1Cu);
  if ( !v37 )
  {
    IsAllowedCOMCallLocality = -2147024882;
    goto LABEL_124;
  }
  IsAllowedCOMCallLocality = StringValidateDestW(v35, 0xEu, v36);
  if ( IsAllowedCOMCallLocality < 0 )
  {
    *v37 = 0;
    goto LABEL_169;
  }
  IsAllowedCOMCallLocality = StringCopyWorkerW(v37, v38, v39, L"content-type:", *(size_t *)dwCreationDisposition);
  if ( IsAllowedCOMCallLocality < 0 )
  {
LABEL_169:
    free(v37);
    goto LABEL_124;
  }
  free(0);
  v34 = v37;
  *(_QWORD *)cchWideChar = v37;
  if ( !IsAllowedCOMCallLocality )
    goto LABEL_38;
LABEL_124:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  if ( IsAllowedCOMCallLocality < 0 )
  {
    v28 = (unsigned __int16 **)cchMax;
    goto LABEL_112;
  }
LABEL_38:
  v28 = (unsigned __int16 **)cchMax;
  IsAllowedCOMCallLocality = CUString::HrAppend((CUString *)cchWideChar, v33[1]);
  v34 = *(wchar_t **)cchWideChar;
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_112;
  if ( !cchMax )
  {
    IsAllowedCOMCallLocality = -2147467261;
    goto LABEL_112;
  }
  if ( *(_QWORD *)cchWideChar )
  {
    v40 = -1;
    do
      ++v40;
    while ( *(_WORD *)(*(_QWORD *)cchWideChar + 2 * v40) );
  }
  else
  {
    v40 = 0;
  }
  v41 = v40 + 1;
  v42 = (const wchar_t *)CoTaskMemAlloc(2 * (v40 + 1));
  *cchMax = v42;
  if ( !v42 )
  {
    IsAllowedCOMCallLocality = -2147024882;
LABEL_118:
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    goto LABEL_48;
  }
  v44 = StringValidateDestW(v42, v41, v43);
  IsAllowedCOMCallLocality = v44;
  if ( v44 >= 0 )
  {
    v49 = StringCopyWorkerW(v46, v45, v47, v48, *(size_t *)dwCreationDisposition);
    goto LABEL_46;
  }
  v49 = v44;
  if ( v41 )
  {
    *v46 = 0;
LABEL_173:
    CoTaskMemFree((LPVOID)*cchMax);
    v50 = v49 == 0;
    *cchMax = 0;
  }
  else
  {
LABEL_46:
    IsAllowedCOMCallLocality = v49;
    v50 = v49 == 0;
    if ( v49 < 0 )
      goto LABEL_173;
  }
  if ( !v50 )
    goto LABEL_118;
LABEL_48:
  if ( IsAllowedCOMCallLocality < 0 )
    goto LABEL_112;
  v101 = 1;
  v51 = DwDHFileSizeLimit();
  if ( !*v114 )
  {
    IsAllowedCOMCallLocality = -2147467261;
    goto LABEL_112;
  }
  FileW = CreateFileW(*v114, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    IsAllowedCOMCallLocality = HrFromLastWin32Error();
    if ( IsAllowedCOMCallLocality )
    {
      v92 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_3fd7421b52d5331ae331e419ccb3b71c_Traceguids,
          (unsigned int)IsAllowedCOMCallLocality);
        v92 = WPP_GLOBAL_Control;
      }
      if ( IsAllowedCOMCallLocality < 0 )
      {
LABEL_186:
        nNumberOfBytesToRead = 0;
        v108 = 0;
        goto LABEL_188;
      }
    }
  }
  FileSize = GetFileSize(FileW, 0);
  nNumberOfBytesToRead = FileSize;
  if ( FileSize == -1 )
  {
    IsAllowedCOMCallLocality = HrFromLastWin32Error();
  }
  else if ( FileSize > v51 )
  {
    IsAllowedCOMCallLocality = -2147024882;
  }
  else if ( (FileSize & 0x80000000) == 0 && (v54 = CoTaskMemAlloc(FileSize), (v108 = v54) != 0) )
  {
    IsAllowedCOMCallLocality = 0;
    cchWideChar[0] = 0;
    if ( !ReadFile(FileW, v54, nNumberOfBytesToRead, (LPDWORD)cchWideChar, 0) )
    {
      IsAllowedCOMCallLocality = HrFromLastWin32Error();
      if ( IsAllowedCOMCallLocality < 0 )
        CoTaskMemFree(v54);
    }
  }
  else
  {
    IsAllowedCOMCallLocality = -2147024882;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, 2147942414LL);
  }
  CloseHandle(FileW);
  if ( IsAllowedCOMCallLocality < 0 )
  {
    v92 = WPP_GLOBAL_Control;
    goto LABEL_186;
  }
  if ( !IsAllowedCOMCallLocality )
    goto LABEL_112;
  v92 = WPP_GLOBAL_Control;
LABEL_188:
  if ( v92 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v92[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)v92 + 2),
      11,
      WPP_3fd7421b52d5331ae331e419ccb3b71c_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
LABEL_112:
  free(v34);
LABEL_113:
  v88 = nNumberOfBytesToRead;
LABEL_70:
  v69 = IsAllowedCOMCallLocality < 0;
  if ( !IsAllowedCOMCallLocality )
  {
    if ( v113 )
    {
      memset_0(pszSrc, 0, 0xD0u);
      IsAllowedCOMCallLocality = StringCchCopyW(pszSrc, 0x68u, L"Content-Language: ");
      if ( IsAllowedCOMCallLocality )
        goto LABEL_137;
      if ( !GetSystemDefaultLocaleName(LocaleName, 85) )
      {
        LastError = GetLastError();
        IsAllowedCOMCallLocality = LastError;
        if ( LastError > 0 )
          IsAllowedCOMCallLocality = (unsigned __int16)LastError | 0x80070000;
        v69 = IsAllowedCOMCallLocality < 0;
        if ( IsAllowedCOMCallLocality )
          goto LABEL_71;
      }
      if ( v101 < v14 - 1 )
      {
        IsAllowedCOMCallLocality = HrCoTaskMemAllocString(pszSrc, &v28[v101]);
        if ( IsAllowedCOMCallLocality )
          goto LABEL_137;
        ++v101;
      }
    }
    if ( v106 > 0 )
    {
      v93 = bstrString;
      v94 = v101;
      do
      {
        v95 = wcsstr(v93, L"\r\n");
        v96 = v95;
        if ( v95 )
        {
          v97 = v95 - v93;
          v98 = &pv[v94];
          IsAllowedCOMCallLocality = HrCoTaskMemAllocString(v97 + 1, v98);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = StringCchCopyNW(*v98, v97 + 1, v93, v97);
            if ( IsAllowedCOMCallLocality < 0 )
              CoTaskMemFree(*v98);
            else
              ++v94;
          }
          v96 += 2;
        }
        if ( !v96 )
          break;
        if ( !*v96 )
          break;
        v93 = v96;
      }
      while ( IsAllowedCOMCallLocality >= 0 );
      v28 = pv;
      v24 = -1;
      v101 = v94;
      v14 = v102;
      v69 = IsAllowedCOMCallLocality < 0;
      if ( IsAllowedCOMCallLocality )
        goto LABEL_71;
      v88 = nNumberOfBytesToRead;
    }
    IsAllowedCOMCallLocality = StringCbPrintfW(pszSrc, 0x100u, L"Content-Length: %d", v88);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_80;
    if ( v101 >= v14 )
    {
LABEL_72:
      if ( IsAllowedCOMCallLocality == 1 )
        goto LABEL_80;
      v70 = v109;
      v71 = v110;
      v72 = v111;
      v73 = v112;
      goto LABEL_74;
    }
    v78 = (STRSAFE_PCNZWCH *)&v28[v101];
    if ( !v78 )
    {
      IsAllowedCOMCallLocality = -2147467261;
      goto LABEL_80;
    }
    do
      ++v24;
    while ( pszSrc[v24] );
    v79 = v24 + 1;
    if ( v79 )
    {
      v114 = 0;
      if ( is_mul_ok(v79, 2u) )
      {
        v80 = (const wchar_t *)CoTaskMemAlloc(2 * v79);
        *v78 = v80;
        if ( v80 )
        {
          IsAllowedCOMCallLocality = StringValidateDestW(*v78, v79, (const size_t)cchMax);
          if ( IsAllowedCOMCallLocality < 0 )
            *v82 = 0;
          else
            IsAllowedCOMCallLocality = StringCopyWorkerW(v82, v81, v83, pszSrc, *(size_t *)dwCreationDisposition);
          v85 = WPP_GLOBAL_Control;
          v86 = IsAllowedCOMCallLocality;
          if ( !IsAllowedCOMCallLocality )
            goto LABEL_103;
          goto LABEL_134;
        }
        IsAllowedCOMCallLocality = -2147024882;
      }
      else
      {
        IsAllowedCOMCallLocality = -2147024362;
      }
    }
    else
    {
      IsAllowedCOMCallLocality = -2147024882;
    }
    v85 = WPP_GLOBAL_Control;
    v84 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
      v85 = WPP_GLOBAL_Control;
      v84 = &WPP_GLOBAL_Control;
    }
    v86 = IsAllowedCOMCallLocality;
LABEL_134:
    if ( v85 != (STRSAFE_PCNZWCH)v84 && (v85[14] & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v85 + 2), 12, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, v86);
      goto LABEL_137;
    }
LABEL_103:
    IsAllowedCOMCallLocality = v86;
    if ( !v86 )
    {
      v13 = bstrString;
      v70 = v109;
      v71 = v110;
      v72 = v111;
      v73 = v112;
      goto LABEL_76;
    }
LABEL_137:
    v69 = IsAllowedCOMCallLocality < 0;
  }
LABEL_71:
  if ( !v69 )
    goto LABEL_72;
LABEL_80:
  if ( v28 )
  {
    v75 = v101;
    for ( k = 0; k < v75; ++k )
    {
LABEL_82:
      v77 = (wchar_t *)cchMax[k];
      if ( v77 )
        CoTaskMemFree(v77);
    }
    CoTaskMemFree(v28);
  }
  if ( v108 )
    CoTaskMemFree(v108);
  v71 = v110;
  v70 = v109;
  v72 = v111;
  v73 = v112;
  *v110 = 0;
  *v70 = 0;
  *v72 = 0;
  *v73 = 0;
LABEL_74:
  v13 = bstrString;
LABEL_75:
  if ( !IsAllowedCOMCallLocality )
  {
LABEL_76:
    *v71 = v14;
    *v70 = v28;
    *v72 = nNumberOfBytesToRead;
    *v73 = v108;
    SysFreeString(v13);
    goto LABEL_77;
  }
  SysFreeString(v13);
LABEL_4:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
LABEL_77:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x180012310  mov     [rsp-8+arg_8], rbx
0x180012315  push    rbp
0x180012316  push    rsi
0x180012317  push    rdi
0x180012318  push    r12
0x18001231a  push    r13
0x18001231c  push    r14
0x18001231e  push    r15
0x180012320  lea     rbp, [rsp-0D0h]
0x180012328  sub     rsp, 1D0h
0x18001232f  mov     rax, cs:__security_cookie
0x180012336  xor     rax, rsp
0x180012339  mov     [rbp+100h+var_40], rax
0x180012340  mov     rax, [rbp+100h+arg_20]
0x180012347  lea     rbx, [rcx+10h]
0x18001234b  mov     [rbp+100h+var_178], rax
0x18001234f  mov     r15, rcx
0x180012352  mov     rax, [rbp+100h+arg_28]
0x180012359  mov     rcx, rbx; this
0x18001235c  mov     [rbp+100h+var_180], rax
0x180012360  mov     edi, r9d
0x180012363  mov     rax, [rbp+100h+arg_30]
0x18001236a  mov     rsi, r8
0x18001236d  mov     [rbp+100h+var_170], rax
0x180012371  mov     r13, rdx
0x180012374  mov     rax, [rbp+100h+arg_38]
0x18001237b  mov     [rbp+100h+var_168], rax
0x18001237f  mov     [rbp+100h+var_160], r9d
0x180012383  mov     [rbp+100h+lpCriticalSection], rbx
0x180012387  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x18001238c  xor     r14d, r14d
0x18001238f  test    edi, edi
0x180012391  setnz   r14b
0x180012395  xor     r12d, r12d
0x180012398  add     r14d, 2
0x18001239c  mov     [rsp+200h+bstrString], r12
0x1800123a1  mov     [rsp+200h+var_1B8], r14d
0x1800123a6  mov     [rsp+200h+var_198], r12d
0x1800123ab  cmp     [rbp+100h+var_180], r12
0x1800123af  jz      loc_180012AEF
0x1800123b5  mov     ecx, 1
0x1800123ba  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x1800123bf  mov     edi, eax
0x1800123c1  test    eax, eax
0x1800123c3  jns     short loc_18001240C
0x1800123c5  mov     ecx, r12d; bstrString
0x1800123c8  call    cs:__imp_SysFreeString
0x1800123ce  lea     rsi, WPP_GLOBAL_Control
0x1800123d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123dc  cmp     rcx, rsi
0x1800123df  jz      loc_180012918
0x1800123e5  test    byte ptr [rcx+1Ch], 1
0x1800123e9  jz      loc_180012918
0x1800123ef  mov     rcx, [rcx+10h]
0x1800123f3  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800123fa  mov     edx, 0Ah
0x1800123ff  mov     r9d, edi
0x180012402  call    WPP_SF_d
0x180012407  jmp     loc_180012918
0x18001240c  xor     edi, edi
0x18001240e  lea     rbx, [r15+230h]
0x180012415  mov     rcx, rbx; lpCriticalSection
0x180012418  mov     [rsp+200h+cchMax], rdi
0x18001241d  mov     [rsp+200h+nNumberOfBytesToRead], edi
0x180012421  mov     [rsp+200h+var_188], rdi
0x180012426  call    cs:__imp_EnterCriticalSection
0x18001242c  mov     r8d, [r15+68h]
0x180012430  mov     eax, edi
0x180012432  cmp     eax, r8d
0x180012435  jge     loc_1800129D5
0x18001243b  mov     rcx, [r13+0]
0x18001243f  movsxd  r9, eax
0x180012442  mov     rdx, r9
0x180012445  shl     rdx, 4
0x180012449  add     rdx, [r15+60h]
0x18001244d  sub     rcx, [rdx]
0x180012450  jnz     short loc_18001245A
0x180012452  mov     rcx, [r13+8]
0x180012456  sub     rcx, [rdx+8]
0x18001245a  test    rcx, rcx
0x18001245d  jnz     loc_1800129CE
0x180012463  mov     rax, [r15+70h]
0x180012467  mov     rcx, rbx; lpCriticalSection
0x18001246a  lea     rdi, [rax+r9*8]
0x18001246e  call    cs:__imp_LeaveCriticalSection
0x180012474  test    rdi, rdi
0x180012477  jnz     loc_180012BF2
0x18001247d  mov     [rsp+200h+var_1B8], r14d
0x180012482  lea     rsi, WPP_GLOBAL_Control
0x180012489  test    r14d, r14d
0x18001248c  js      loc_180012D8D
0x180012492  mov     eax, r14d
0x180012495  mov     edx, 0FFFFFFFFh
0x18001249a  shl     rax, 3
0x18001249e  cmp     rax, rdx
0x1800124a1  ja      loc_180012B02
0x1800124a7  mov     ecx, eax; cb
0x1800124a9  xor     edi, edi
0x1800124ab  call    cs:__imp_CoTaskMemAlloc
0x1800124b1  mov     [rsp+200h+cchMax], rax
0x1800124b6  test    rax, rax
0x1800124b9  jz      loc_180012D92
0x1800124bf  test    edi, edi
0x1800124c1  js      loc_180012B80
0x1800124c7  mov     rdi, [rsp+200h+cchMax]
0x1800124cc  xor     edx, edx; Val
0x1800124ce  movsxd  r8, r14d
0x1800124d1  mov     rcx, rdi; void *
0x1800124d4  shl     r8, 3; Size
0x1800124d8  mov     [rsp+200h+var_1BC], 0
0x1800124e0  call    memset_0
0x1800124e5  mov     rcx, rbx; lpCriticalSection
0x1800124e8  call    cs:__imp_EnterCriticalSection
0x1800124ee  xor     edx, edx
0x1800124f0  mov     [rsp+200h+pv], rdi
0x1800124f5  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800124fc  cmp     edx, [r15+48h]
0x180012500  jge     short loc_180012579
0x180012502  mov     rax, [r13+0]
0x180012506  movsxd  r8, edx
0x180012509  mov     rcx, r8
0x18001250c  shl     rcx, 4
0x180012510  add     rcx, [r15+40h]
0x180012514  sub     rax, [rcx]
0x180012517  jnz     short loc_180012521
0x180012519  mov     rax, [r13+8]
0x18001251d  sub     rax, [rcx+8]
0x180012521  test    rax, rax
0x180012524  jnz     loc_18001279C
0x18001252a  mov     rax, [r15+50h]
0x18001252e  mov     rcx, rbx; lpCriticalSection
0x180012531  lea     r12, [rax+r8*8]
0x180012535  call    cs:__imp_LeaveCriticalSection
0x18001253b  test    r12, r12
0x18001253e  jz      short loc_180012582
0x180012540  mov     r13, rdi
0x180012543  test    rdi, rdi
0x180012546  jz      loc_180012DD3
0x18001254c  mov     eax, 2
0x180012551  mov     r15d, 28h ; '('
0x180012557  mul     r15
0x18001255a  xor     ebx, ebx
0x18001255c  test    rdx, rdx
0x18001255f  jz      loc_1800127A3
0x180012565  mov     edi, 80070216h
0x18001256a  mov     [rsp+200h+pv], r13
0x18001256f  mov     [rsp+200h+var_1B8], r14d
0x180012574  jmp     loc_180012DE2
0x180012579  mov     rcx, rbx; lpCriticalSection
0x18001257c  call    cs:__imp_LeaveCriticalSection
0x180012582  mov     rcx, rbx; lpCriticalSection
0x180012585  call    cs:__imp_EnterCriticalSection
0x18001258b  mov     edx, [r15+0A8h]
0x180012592  xor     ecx, ecx
0x180012594  cmp     ecx, edx
0x180012596  jge     loc_18001294E
0x18001259c  mov     r9, [r15+0A0h]
0x1800125a3  mov     rax, [r13+0]
0x1800125a7  movsxd  r8, ecx
0x1800125aa  shl     r8, 4
0x1800125ae  sub     rax, [r9+r8]
0x1800125b2  jnz     short loc_1800125BD
0x1800125b4  mov     rax, [r13+8]
0x1800125b8  sub     rax, [r9+r8+8]
0x1800125bd  test    rax, rax
0x1800125c0  jnz     loc_180012795
0x1800125c6  mov     r12, [r15+0B0h]
0x1800125cd  mov     rcx, rbx; lpCriticalSection
0x1800125d0  add     r12, r8
0x1800125d3  mov     [rbp+100h+var_158], r12
0x1800125d7  call    cs:__imp_LeaveCriticalSection
0x1800125dd  test    r12, r12
0x1800125e0  jz      loc_180012957
0x1800125e6  xor     ebx, ebx
0x1800125e8  mov     ecx, 1Ch; Size
0x1800125ed  mov     qword ptr [rsp+200h+cchWideChar], rbx
0x1800125f2  call    cs:__imp_malloc
0x1800125f8  mov     r15, rax
0x1800125fb  test    rax, rax
0x1800125fe  jz      loc_180012EAF
0x180012604  mov     edx, 0Eh; cchDest
0x180012609  call    StringValidateDestW
0x18001260e  mov     edi, eax
0x180012610  test    eax, eax
0x180012612  js      loc_180012EB9
0x180012618  lea     r9, aContentType_0; "content-type:"
0x18001261f  mov     rcx, r15; pszDest
0x180012622  call    StringCopyWorkerW
0x180012627  mov     edi, eax
0x180012629  test    eax, eax
0x18001262b  js      loc_180012EBF
0x180012631  xor     ecx, ecx; Block
0x180012633  call    cs:__imp_free
0x180012639  mov     rbx, r15
0x18001263c  mov     qword ptr [rsp+200h+cchWideChar], rbx
0x180012641  test    edi, edi
0x180012643  jnz     loc_180012C2C
0x180012649  mov     rdx, [r12+8]; unsigned __int16 *
0x18001264e  lea     rcx, [rsp+200h+cchWideChar]; this
0x180012653  call    ?HrAppend@CUString@@QEAAJPEBG@Z; CUString::HrAppend(ushort const *)
0x180012658  mov     r13, [rsp+200h+pv]
0x18001265d  mov     edi, eax
0x18001265f  mov     rbx, qword ptr [rsp+200h+cchWideChar]
0x180012664  test    eax, eax
0x180012666  js      loc_180012B63
0x18001266c  test    r13, r13
0x18001266f  jz      loc_180012ECD
0x180012675  test    rbx, rbx
0x180012678  jz      loc_180012C6F
0x18001267e  mov     rax, rsi
0x180012681  inc     rax
0x180012684  cmp     word ptr [rbx+rax*2], 0
0x180012689  jnz     short loc_180012681
0x18001268b  lea     r15, [rax+1]
0x18001268f  lea     rcx, [r15+r15]; cb
0x180012693  call    cs:__imp_CoTaskMemAlloc
0x180012699  mov     [r13+0], rax
0x18001269d  mov     rcx, rax; pszDest
0x1800126a0  test    rax, rax
0x1800126a3  jz      loc_180012BAF
0x1800126a9  test    rbx, rbx
0x1800126ac  lea     r9, dword_180060F84
0x1800126b3  mov     rdx, r15; cchDest
0x1800126b6  cmovnz  r9, rbx
0x1800126ba  call    StringValidateDestW
0x1800126bf  mov     edi, eax
0x1800126c1  test    eax, eax
0x1800126c3  js      loc_180012ED7
0x1800126c9  call    StringCopyWorkerW
0x1800126ce  mov     r12d, eax
0x1800126d1  mov     edi, r12d
0x1800126d4  test    r12d, r12d
0x1800126d7  js      loc_180012EE8
0x1800126dd  jnz     loc_180012BB4
0x1800126e3  test    edi, edi
0x1800126e5  js      loc_180012B63
0x1800126eb  mov     [rsp+200h+var_1BC], 1
0x1800126f3  call    ?DwDHFileSizeLimit@@YAKXZ; DwDHFileSizeLimit(void)
0x1800126f8  mov     rcx, [rbp+100h+var_158]
0x1800126fc  mov     r12d, eax
0x1800126ff  mov     rcx, [rcx]; lpFileName
0x180012702  test    rcx, rcx
0x180012705  jz      loc_180012F02
0x18001270b  mov     [rsp+200h+hTemplateFile], 0; hTemplateFile
0x180012714  xor     r9d, r9d; lpSecurityAttributes
0x180012717  mov     [rsp+200h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001271f  mov     edx, 80000000h; dwDesiredAccess
0x180012724  mov     r8d, 1; dwShareMode
0x18001272a  mov     [rsp+200h+dwCreationDisposition], 3; dwCreationDisposition
0x180012732  call    cs:__imp_CreateFileW
0x180012738  mov     r15, rax
0x18001273b  cmp     rax, rsi
0x18001273e  jz      loc_180012F0C
0x180012744  xor     edx, edx; lpFileSizeHigh
0x180012746  mov     rcx, r15; hFile
0x180012749  call    cs:__imp_GetFileSize
0x18001274f  mov     ecx, 0FFFFFFFFh
0x180012754  mov     [rsp+200h+nNumberOfBytesToRead], eax
0x180012758  cmp     eax, ecx
0x18001275a  jz      loc_180012B98
0x180012760  cmp     eax, r12d
0x180012763  ja      loc_180012FA8
0x180012769  test    eax, eax
0x18001276b  js      loc_180012F5C
0x180012771  mov     ecx, eax; cb
0x180012773  call    cs:__imp_CoTaskMemAlloc
0x180012779  mov     r12, rax
0x18001277c  mov     [rsp+200h+var_188], rax
0x180012781  test    rax, rax
0x180012784  mov     eax, [rsp+200h+nNumberOfBytesToRead]
0x180012788  jz      loc_180012F61
0x18001278e  xor     edi, edi
0x180012790  jmp     loc_180012B1F
0x180012795  inc     ecx
0x180012797  jmp     loc_180012594
0x18001279c  inc     edx
0x18001279e  jmp     loc_1800124F5
0x1800127a3  mov     rcx, rax; cb
0x1800127a6  call    cs:__imp_CoTaskMemAlloc
0x1800127ac  mov     [rdi], rax
0x1800127af  mov     [rsp+200h+pv], r13
0x1800127b4  mov     [rsp+200h+var_1B8], r14d
0x1800127b9  test    rax, rax
0x1800127bc  jz      loc_180012DDD
0x1800127c2  mov     [rsp+200h+cchMax], rdi
0x1800127c7  lea     r11, WPP_GLOBAL_Control
0x1800127ce  mov     rcx, [r13+0]; pszDest
0x1800127d2  mov     rdx, r15; cchDest
0x1800127d5  call    StringValidateDestW
0x1800127da  mov     edi, eax
0x1800127dc  test    eax, eax
0x1800127de  js      loc_180012E33
0x1800127e4  lea     r9, aContentTypeTex; "Content-Type: text/xml; charset=\"utf-8"...
0x1800127eb  call    StringCopyWorkerW
0x1800127f0  mov     edi, eax
0x1800127f2  test    edi, edi
0x1800127f4  jnz     loc_180012E3B
0x1800127fa  js      loc_180012B6C
0x180012800  mov     rcx, [r12]; pbstr
0x180012804  mov     [rsp+200h+var_1BC], 1
  ... truncated ...
```
