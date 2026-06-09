# CDescriptionManager::GetContent(_GUID const &,ushort const *,int,long *,ushort * * *,long *,uchar * *)

- ea: `0x1800062c0`
- end: `0x1800071b6`
- name: `?GetContent@CDescriptionManager@@UEAAJAEBU_GUID@@PEBGHPEAJPEAPEAPEAG2PEAPEAE@Z`
- size: `3830`
- prototype: `int(CDescriptionManager *__hidden this, const struct _GUID *, const unsigned __int16 *, int, int *, unsigned __int16 ***, int *, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180005b24`
- `0x1800062c0`
- `0x1800071c0`
- `0x1800074dc`
- `0x180007520`
- `0x18000a060`
- `0x18000ecf0`
- `0x180014550`
- `0x18001be90`
- `0x1800244b0`
- `0x18002bed8`
- `0x18002c364`
- `0x18003a798`
- `0x18003b1cc`
- `0x18003cb60`
- `0x18003d4b0`
- `0x180042774`
- `0x180045b90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800067f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800069ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006f25`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800067f5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800069ac`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180006f25`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800067ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800067ae`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800070a4`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800070a4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006734`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800063e3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006734`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006432`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ba5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006432`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006516`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800066e2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006725`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000678d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800069ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006a85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180006ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000660c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006475`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006550`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000660c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006b21`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a36`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006a4f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006cf0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006d65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800070fc`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800065ed`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000665c`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800065ed`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18000665c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000698f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000698f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006978`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006978`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006918`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x180006918`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800068fb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800068fb`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x180007073`
- `api-ms-win-core-localization-l1-2-2!GetSystemDefaultLocaleName` at `0x180007073`
- `OLEAUT32!__imp_SysFreeString` at `0x180006383`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c04`
- `OLEAUT32!__imp_SysFreeString` at `0x180006383`
- `OLEAUT32!__imp_SysFreeString` at `0x1800066d2`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c04`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065bc`
- `OLEAUT32!__imp_SysStringLen` at `0x1800065bc`

## string_xrefs

- `0x180006594`: `Content-Type: text/xml; charset="utf-8"`

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
  struct _RTL_CRITICAL_SECTION *p_OwningThread; // rdi
  const struct _GUID *v12; // r12
  int v13; // r14d
  int IsAllowedCOMCallLocality; // edi
  unsigned __int16 **v15; // r13
  int i; // eax
  _QWORD *v17; // rdx
  __int64 v18; // rcx
  struct IUPnPDeviceControlHttpHeaders **v19; // rdi
  CDescriptionManager *v20; // rcx
  unsigned __int64 v21; // rax
  int v22; // edx
  __int64 v23; // rsi
  _QWORD *v24; // rcx
  __int64 v25; // rax
  BSTR *v26; // r12
  LPVOID v27; // rax
  size_t v28; // r8
  size_t v29; // rdx
  wchar_t *v30; // rcx
  size_t *v31; // r8
  STRSAFE_PCNZWCH *v32; // r11
  bool v33; // sf
  UINT v34; // eax
  const WCHAR *v35; // r8
  int v36; // eax
  __int64 v37; // r13
  unsigned int cbMultiByte; // r15d
  void *v39; // rbx
  bool v41; // sf
  unsigned __int16 ***v42; // rax
  int *v43; // rcx
  _DWORD *v44; // rdx
  unsigned __int8 **v45; // r8
  OLECHAR *v46; // rcx
  LONG j; // ecx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // r9
  __int64 v50; // r8
  unsigned __int64 v51; // rax
  LPCWSTR *v52; // r12
  struct _GUID *v53; // rbx
  const wchar_t *v54; // rcx
  size_t v55; // r8
  wchar_t *v56; // r15
  size_t v57; // rdx
  size_t *v58; // r8
  int v59; // eax
  __int64 v60; // rax
  size_t v61; // r15
  const wchar_t *v62; // rax
  size_t v63; // r8
  HRESULT v64; // eax
  size_t v65; // rdx
  wchar_t *v66; // rcx
  size_t *v67; // r8
  const wchar_t *v68; // r9
  HRESULT v69; // r12d
  bool v70; // zf
  DWORD v71; // r12d
  HANDLE FileW; // r15
  DWORD FileSize; // eax
  int v74; // eax
  void *v75; // r12
  unsigned int v76; // r15d
  unsigned int v77; // ebx
  void *v78; // rcx
  STRSAFE_PCNZWCH *v79; // rbx
  size_t v80; // rsi
  const wchar_t *v81; // rax
  size_t v82; // rdx
  wchar_t *v83; // rcx
  size_t *v84; // r8
  STRSAFE_PCNZWCH *v85; // r11
  STRSAFE_PCNZWCH v86; // r10
  unsigned int v87; // eax
  unsigned __int8 *v88; // r12
  signed int LastError; // eax
  STRSAFE_PCNZWCH v90; // rcx
  STRSAFE_PCNZWCH v91; // rcx
  const wchar_t *v92; // r15
  char *v93; // rsi
  unsigned int v94; // r14d
  wchar_t *v95; // rax
  wchar_t *v96; // rbx
  unsigned __int64 v97; // r13
  unsigned __int16 **v98; // r12
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  unsigned int v100; // [rsp+40h] [rbp-C0h]
  int v101; // [rsp+44h] [rbp-BCh]
  DWORD nNumberOfBytesToRead; // [rsp+48h] [rbp-B8h]
  LPVOID *cchMax; // [rsp+50h] [rbp-B0h]
  int cchWideChar[2]; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID v105; // [rsp+60h] [rbp-A0h]
  LPVOID pv; // [rsp+68h] [rbp-98h]
  int v107; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 ***v108; // [rsp+78h] [rbp-88h]
  int *v109; // [rsp+80h] [rbp-80h]
  int *v110; // [rsp+88h] [rbp-78h]
  unsigned __int8 **v111; // [rsp+90h] [rbp-70h]
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  int v113; // [rsp+A0h] [rbp-60h]
  LPVOID lpBuffer; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR *v115; // [rsp+B0h] [rbp-50h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+B8h] [rbp-48h]
  wchar_t pszSrc[18]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR LocaleName[110]; // [rsp+E4h] [rbp-1Ch] BYREF

  p_OwningThread = (struct _RTL_CRITICAL_SECTION *)&this->OwningThread;
  v109 = a5;
  v110 = a7;
  v12 = a2;
  v111 = a8;
  v113 = a4;
  *(_QWORD *)cchWideChar = a2;
  v108 = a6;
  lpCriticalSection = (LPCRITICAL_SECTION)&this->OwningThread;
  ATL::CComSafeDeleteCriticalSection::Lock((ATL::CComSafeDeleteCriticalSection *)&this->OwningThread);
  v13 = (a4 != 0) + 2;
  v105 = 0;
  v101 = v13;
  lpBuffer = 0;
  bstrString = 0;
  v107 = 0;
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
  nNumberOfBytesToRead = 0;
  v15 = 0;
  cchMax = 0;
  EnterCriticalSection(this + 14);
  for ( i = 0; ; ++i )
  {
    if ( i >= SLODWORD(this[2].LockSemaphore) )
    {
      LeaveCriticalSection(this + 14);
LABEL_13:
      v101 = v13;
      goto LABEL_14;
    }
    v17 = (char *)this[2].OwningThread + 16 * i;
    v18 = *(_QWORD *)&v12->Data1 - *v17;
    if ( *(_QWORD *)&v12->Data1 == *v17 )
      v18 = *(_QWORD *)v12->Data4 - v17[1];
    if ( !v18 )
      break;
  }
  v19 = (struct IUPnPDeviceControlHttpHeaders **)(this[2].SpinCount + 8LL * i);
  LeaveCriticalSection(this + 14);
  if ( !v19 || !*v19 )
    goto LABEL_13;
  if ( CDescriptionManager::HrGetAdditionalResponseHeadersAndCount(v20, *v19, a3, &bstrString, &v107) >= 0 )
  {
    v13 += v107;
    goto LABEL_13;
  }
LABEL_14:
  if ( v13 < 0 )
    goto LABEL_146;
  v21 = 8LL * (unsigned int)v13;
  if ( v21 > 0xFFFFFFFF )
  {
    IsAllowedCOMCallLocality = -2147024362;
LABEL_147:
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
    goto LABEL_17;
  }
  IsAllowedCOMCallLocality = 0;
  cchMax = (LPVOID *)CoTaskMemAlloc((unsigned int)v21);
  v15 = (unsigned __int16 **)cchMax;
  if ( !cchMax )
  {
LABEL_146:
    IsAllowedCOMCallLocality = -2147024882;
    goto LABEL_147;
  }
LABEL_17:
  if ( IsAllowedCOMCallLocality < 0 )
  {
    v88 = (unsigned __int8 *)v105;
    v42 = v108;
    v43 = v109;
    v44 = v110;
    v45 = v111;
    goto LABEL_42;
  }
  v100 = 0;
  memset_0(cchMax, 0, 8LL * v13);
  EnterCriticalSection(this + 14);
  v22 = 0;
  pv = cchMax;
  v15 = (unsigned __int16 **)cchMax;
  while ( 1 )
  {
    v23 = -1;
    if ( v22 >= SLODWORD(this[1].SpinCount) )
    {
      LeaveCriticalSection(this + 14);
      goto LABEL_47;
    }
    v24 = (char *)this[1].LockSemaphore + 16 * v22;
    v25 = *(_QWORD *)&v12->Data1 - *v24;
    if ( *(_QWORD *)&v12->Data1 == *v24 )
      v25 = *(_QWORD *)v12->Data4 - v24[1];
    if ( !v25 )
      break;
    ++v22;
  }
  v26 = (BSTR *)((char *)this[2].DebugInfo + 8 * v22);
  LeaveCriticalSection(this + 14);
  if ( !v26 )
  {
    v12 = *(const struct _GUID **)cchWideChar;
LABEL_47:
    EnterCriticalSection(this + 14);
    for ( j = 0; ; ++j )
    {
      if ( j >= this[4].LockCount )
      {
        LeaveCriticalSection(this + 14);
        goto LABEL_82;
      }
      DebugInfo = this[4].DebugInfo;
      v50 = 16LL * j;
      v51 = *(_QWORD *)&v12->Data1 - *(_QWORD *)((char *)&DebugInfo->Type + v50);
      if ( *(_QWORD *)&v12->Data1 == *(_QWORD *)((char *)&DebugInfo->Type + v50) )
        v51 = *(_QWORD *)v12->Data4 - *(unsigned __int64 *)((char *)&DebugInfo->CriticalSection + v50);
      if ( !v51 )
        break;
    }
    v115 = (LPCWSTR *)((char *)this[4].OwningThread + v50);
    v52 = v115;
    LeaveCriticalSection(this + 14);
    if ( v52 )
    {
      v53 = 0;
      *(_QWORD *)cchWideChar = 0;
      v56 = (wchar_t *)malloc(0x1Cu);
      if ( !v56 )
      {
        IsAllowedCOMCallLocality = -2147024882;
        goto LABEL_121;
      }
      IsAllowedCOMCallLocality = StringValidateDestW(v54, 0xEu, v55);
      if ( IsAllowedCOMCallLocality < 0 )
      {
        *v56 = 0;
      }
      else
      {
        IsAllowedCOMCallLocality = StringCopyWorkerW(v56, v57, v58, L"content-type:", (size_t)lpMultiByteStr);
        if ( IsAllowedCOMCallLocality >= 0 )
        {
          free(0);
          v53 = (struct _GUID *)v56;
          *(_QWORD *)cchWideChar = v56;
          if ( !IsAllowedCOMCallLocality )
            goto LABEL_57;
LABEL_121:
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              10,
              WPP_bbadc92b44a9335df55a63a23abb1016_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          if ( IsAllowedCOMCallLocality < 0 )
          {
LABEL_76:
            free(v53);
            goto LABEL_77;
          }
LABEL_57:
          v59 = CUString::HrAppend((CUString *)cchWideChar, v52[1]);
          v53 = *(struct _GUID **)cchWideChar;
          IsAllowedCOMCallLocality = v59;
          if ( v59 < 0 )
            goto LABEL_76;
          if ( !cchMax )
          {
            IsAllowedCOMCallLocality = -2147467261;
            goto LABEL_76;
          }
          if ( *(_QWORD *)cchWideChar )
          {
            v60 = -1;
            do
              ++v60;
            while ( *(_WORD *)(*(_QWORD *)cchWideChar + 2 * v60) );
          }
          else
          {
            v60 = 0;
          }
          v61 = v60 + 1;
          v62 = (const wchar_t *)CoTaskMemAlloc(2 * (v60 + 1));
          *cchMax = (LPVOID)v62;
          if ( v62 )
          {
            v64 = StringValidateDestW(v62, v61, v63);
            IsAllowedCOMCallLocality = v64;
            if ( v64 >= 0 )
            {
              v69 = StringCopyWorkerW(v66, v65, v67, v68, (size_t)lpMultiByteStr);
              goto LABEL_65;
            }
            v69 = v64;
            if ( v61 )
            {
              *v66 = 0;
LABEL_170:
              CoTaskMemFree(*cchMax);
              v70 = v69 == 0;
              *cchMax = 0;
            }
            else
            {
LABEL_65:
              IsAllowedCOMCallLocality = v69;
              v70 = v69 == 0;
              if ( v69 < 0 )
                goto LABEL_170;
            }
            if ( v70 )
            {
LABEL_67:
              if ( IsAllowedCOMCallLocality < 0 )
                goto LABEL_76;
              v100 = 1;
              v71 = DwDHFileSizeLimit();
              if ( !*v115 )
              {
                IsAllowedCOMCallLocality = -2147467261;
                goto LABEL_76;
              }
              FileW = CreateFileW(*v115, 0x80000000, 1u, 0, 3u, 0x80u, 0);
              if ( FileW != (HANDLE)-1LL )
                goto LABEL_70;
              IsAllowedCOMCallLocality = HrFromLastWin32Error();
              if ( !IsAllowedCOMCallLocality )
                goto LABEL_70;
              v91 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  10,
                  WPP_3fd7421b52d5331ae331e419ccb3b71c_Traceguids,
                  (unsigned int)IsAllowedCOMCallLocality);
                v91 = WPP_GLOBAL_Control;
              }
              if ( IsAllowedCOMCallLocality >= 0 )
              {
LABEL_70:
                FileSize = GetFileSize(FileW, 0);
                nNumberOfBytesToRead = FileSize;
                if ( FileSize == -1 )
                {
                  IsAllowedCOMCallLocality = HrFromLastWin32Error();
                }
                else if ( FileSize > v71 )
                {
                  IsAllowedCOMCallLocality = -2147024882;
                }
                else
                {
                  v74 = HrCoTaskMemAllocArray(FileSize, 1, &lpBuffer);
                  v75 = lpBuffer;
                  IsAllowedCOMCallLocality = v74;
                  v105 = lpBuffer;
                  if ( v74 >= 0 )
                  {
                    cchWideChar[0] = 0;
                    if ( !ReadFile(FileW, lpBuffer, nNumberOfBytesToRead, (LPDWORD)cchWideChar, 0) )
                    {
                      IsAllowedCOMCallLocality = HrFromLastWin32Error();
                      if ( IsAllowedCOMCallLocality < 0 )
                      {
                        if ( v75 )
                          CoTaskMemFree(v75);
                      }
                    }
                  }
                }
                CloseHandle(FileW);
                if ( IsAllowedCOMCallLocality >= 0 )
                {
                  if ( !IsAllowedCOMCallLocality )
                    goto LABEL_76;
                  v91 = WPP_GLOBAL_Control;
LABEL_182:
                  if ( v91 != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (v91[14] & 1) != 0 )
                    WPP_SF_d(
                      *((_QWORD *)v91 + 2),
                      11,
                      WPP_3fd7421b52d5331ae331e419ccb3b71c_Traceguids,
                      (unsigned int)IsAllowedCOMCallLocality);
                  goto LABEL_76;
                }
                v91 = WPP_GLOBAL_Control;
              }
              nNumberOfBytesToRead = 0;
              v105 = 0;
              goto LABEL_182;
            }
          }
          else
          {
            IsAllowedCOMCallLocality = -2147024882;
          }
          if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              11,
              WPP_a0ae7d175179382b7ee5ae7e1ec9cc2a_Traceguids,
              (unsigned int)IsAllowedCOMCallLocality);
          goto LABEL_67;
        }
      }
      free(v56);
      goto LABEL_121;
    }
LABEL_82:
    IsAllowedCOMCallLocality = 1;
    goto LABEL_83;
  }
  if ( !cchMax )
  {
    IsAllowedCOMCallLocality = -2147467261;
LABEL_77:
    v88 = (unsigned __int8 *)v105;
    goto LABEL_38;
  }
  if ( !is_mul_ok(0x28u, 2u) )
  {
    IsAllowedCOMCallLocality = -2147024362;
    pv = cchMax;
    v101 = v13;
LABEL_152:
    v90 = WPP_GLOBAL_Control;
    v32 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
      v90 = WPP_GLOBAL_Control;
      v32 = &WPP_GLOBAL_Control;
    }
    goto LABEL_157;
  }
  v27 = CoTaskMemAlloc(0x50u);
  *cchMax = v27;
  pv = cchMax;
  v101 = v13;
  if ( !v27 )
  {
    IsAllowedCOMCallLocality = -2147024882;
    goto LABEL_152;
  }
  IsAllowedCOMCallLocality = StringValidateDestW((STRSAFE_PCNZWCH)*cchMax, 0x28u, v28);
  if ( IsAllowedCOMCallLocality < 0 )
    *v30 = 0;
  else
    IsAllowedCOMCallLocality = StringCopyWorkerW(
                                 v30,
                                 v29,
                                 v31,
                                 L"Content-Type: text/xml; charset=\"utf-8\"",
                                 (size_t)lpMultiByteStr);
  v33 = IsAllowedCOMCallLocality < 0;
  if ( !IsAllowedCOMCallLocality )
    goto LABEL_30;
  v90 = WPP_GLOBAL_Control;
LABEL_157:
  if ( v90 != (STRSAFE_PCNZWCH)v32 && (v90[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)v90 + 2),
      12,
      WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
  v33 = IsAllowedCOMCallLocality < 0;
LABEL_30:
  if ( v33 )
    goto LABEL_77;
  v100 = 1;
  v34 = SysStringLen(*v26);
  v35 = *v26;
  cchWideChar[0] = v34;
  v36 = WideCharToMultiByte(0xFDE9u, 0, v35, v34, 0, 0, 0, 0);
  v37 = v36;
  cbMultiByte = v36 + 1;
  if ( v36 + 1 >= 0 && (v39 = CoTaskMemAlloc(cbMultiByte)) != 0 )
  {
    IsAllowedCOMCallLocality = 0;
    if ( !WideCharToMultiByte(0xFDE9u, 0, *v26, cchWideChar[0], (LPSTR)v39, cbMultiByte, 0, 0) )
    {
      IsAllowedCOMCallLocality = HrFromLastWin32Error();
      if ( IsAllowedCOMCallLocality < 0 )
      {
        CoTaskMemFree(v39);
        v15 = (unsigned __int16 **)pv;
        v77 = 0;
        v76 = 1;
        do
        {
LABEL_85:
          v78 = cchMax[v77];
          if ( v78 )
            CoTaskMemFree(v78);
          ++v77;
        }
        while ( v77 < v76 );
        goto LABEL_88;
      }
    }
    v88 = (unsigned __int8 *)v39;
    v105 = v39;
    nNumberOfBytesToRead = v37;
    *((_BYTE *)v39 + v37) = 0;
  }
  else
  {
    IsAllowedCOMCallLocality = -2147024882;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, 2147942414LL);
    v88 = (unsigned __int8 *)v105;
  }
  v15 = (unsigned __int16 **)pv;
LABEL_38:
  v41 = IsAllowedCOMCallLocality < 0;
  if ( !IsAllowedCOMCallLocality )
  {
    if ( v113 )
    {
      memset_0(pszSrc, 0, 0xD0u);
      IsAllowedCOMCallLocality = StringCchCopyW(pszSrc, 0x68u, L"Content-Language: ");
      if ( IsAllowedCOMCallLocality )
        goto LABEL_134;
      if ( !GetSystemDefaultLocaleName(LocaleName, 85) )
      {
        LastError = GetLastError();
        IsAllowedCOMCallLocality = LastError;
        if ( LastError > 0 )
          IsAllowedCOMCallLocality = (unsigned __int16)LastError | 0x80070000;
        v41 = IsAllowedCOMCallLocality < 0;
        if ( IsAllowedCOMCallLocality )
          goto LABEL_39;
      }
      if ( v100 < v13 - 1 )
      {
        IsAllowedCOMCallLocality = HrCoTaskMemAllocString(pszSrc, &v15[v100]);
        if ( IsAllowedCOMCallLocality )
          goto LABEL_134;
        ++v100;
      }
    }
    if ( v107 > 0 )
    {
      v92 = bstrString;
      v93 = (char *)pv;
      v94 = v100;
      do
      {
        v95 = wcsstr(v92, L"\r\n");
        v96 = v95;
        if ( v95 )
        {
          v97 = v95 - v92;
          v98 = (unsigned __int16 **)&v93[8 * v94];
          IsAllowedCOMCallLocality = HrCoTaskMemAllocString(v97 + 1, v98);
          if ( IsAllowedCOMCallLocality >= 0 )
          {
            IsAllowedCOMCallLocality = StringCchCopyNW(*v98, v97 + 1, v92, v97);
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
        v92 = v96;
      }
      while ( IsAllowedCOMCallLocality >= 0 );
      v15 = (unsigned __int16 **)pv;
      v23 = -1;
      v88 = (unsigned __int8 *)v105;
      v100 = v94;
      v13 = v101;
      v41 = IsAllowedCOMCallLocality < 0;
      if ( IsAllowedCOMCallLocality )
        goto LABEL_39;
    }
    IsAllowedCOMCallLocality = StringCbPrintfW(pszSrc, 0x100u, L"Content-Length: %d", nNumberOfBytesToRead);
    if ( IsAllowedCOMCallLocality < 0 )
      goto LABEL_83;
    if ( v100 >= v13 )
      goto LABEL_40;
    v79 = (STRSAFE_PCNZWCH *)&v15[v100];
    if ( !v79 )
    {
      IsAllowedCOMCallLocality = -2147467261;
      goto LABEL_83;
    }
    do
      ++v23;
    while ( pszSrc[v23] );
    v80 = v23 + 1;
    if ( v80 )
    {
      v115 = 0;
      if ( is_mul_ok(v80, 2u) )
      {
        v81 = (const wchar_t *)CoTaskMemAlloc(2 * v80);
        *v79 = v81;
        if ( v81 )
        {
          IsAllowedCOMCallLocality = StringValidateDestW(*v79, v80, (const size_t)cchMax);
          if ( IsAllowedCOMCallLocality < 0 )
            *v83 = 0;
          else
            IsAllowedCOMCallLocality = StringCopyWorkerW(v83, v82, v84, pszSrc, (size_t)lpMultiByteStr);
          v86 = WPP_GLOBAL_Control;
          v87 = IsAllowedCOMCallLocality;
          if ( !IsAllowedCOMCallLocality )
          {
LABEL_106:
            IsAllowedCOMCallLocality = v87;
            if ( !v87 )
            {
              v42 = v108;
              v43 = v109;
              v44 = v110;
              v45 = v111;
              goto LABEL_43;
            }
            goto LABEL_134;
          }
          goto LABEL_131;
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
    v86 = WPP_GLOBAL_Control;
    v85 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_75c351f6869f3647f61a30e7f530184a_Traceguids,
        (unsigned int)IsAllowedCOMCallLocality);
      v86 = WPP_GLOBAL_Control;
      v85 = &WPP_GLOBAL_Control;
    }
    v87 = IsAllowedCOMCallLocality;
LABEL_131:
    if ( v86 == (STRSAFE_PCNZWCH)v85 || (v86[14] & 1) == 0 )
      goto LABEL_106;
    WPP_SF_d(*((_QWORD *)v86 + 2), 12, WPP_75c351f6869f3647f61a30e7f530184a_Traceguids, v87);
LABEL_134:
    v41 = IsAllowedCOMCallLocality < 0;
  }
LABEL_39:
  if ( !v41 )
  {
LABEL_40:
    if ( IsAllowedCOMCallLocality != 1 )
    {
      v42 = v108;
      v43 = v109;
      v44 = v110;
      v45 = v111;
      goto LABEL_42;
    }
  }
LABEL_83:
  if ( !v15 )
    goto LABEL_89;
  v76 = v100;
  v77 = 0;
  if ( v100 )
    goto LABEL_85;
LABEL_88:
  CoTaskMemFree(v15);
LABEL_89:
  v88 = (unsigned __int8 *)v105;
  if ( v105 )
    CoTaskMemFree(v105);
  v43 = v109;
  v42 = v108;
  v44 = v110;
  v45 = v111;
  *v109 = 0;
  *v42 = 0;
  *v44 = 0;
  *v45 = 0;
LABEL_42:
  if ( !IsAllowedCOMCallLocality )
  {
LABEL_43:
    *v43 = v13;
    v46 = bstrString;
    *v42 = v15;
    *v44 = nNumberOfBytesToRead;
    *v45 = v88;
    SysFreeString(v46);
    goto LABEL_44;
  }
  SysFreeString(bstrString);
LABEL_4:
  if ( WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids,
      (unsigned int)IsAllowedCOMCallLocality);
LABEL_44:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)IsAllowedCOMCallLocality;
}

```

## disassembly

```asm
0x1800062c0  mov     [rsp-8+arg_8], rbx
0x1800062c5  push    rbp
0x1800062c6  push    rsi
0x1800062c7  push    rdi
0x1800062c8  push    r12
0x1800062ca  push    r13
0x1800062cc  push    r14
0x1800062ce  push    r15
0x1800062d0  lea     rbp, [rsp-0D0h]
0x1800062d8  sub     rsp, 1D0h
0x1800062df  mov     rax, cs:__security_cookie
0x1800062e6  xor     rax, rsp
0x1800062e9  mov     [rbp+100h+var_40], rax
0x1800062f0  mov     rax, [rbp+100h+arg_20]
0x1800062f7  lea     rdi, [rcx+10h]
0x1800062fb  mov     r13, [rbp+100h+arg_28]
0x180006302  mov     ebx, r9d
0x180006305  mov     [rbp+100h+var_180], rax
0x180006309  mov     r15, rcx
0x18000630c  mov     rax, [rbp+100h+arg_30]
0x180006313  mov     rcx, rdi; this
0x180006316  mov     [rbp+100h+var_178], rax
0x18000631a  mov     rsi, r8
0x18000631d  mov     rax, [rbp+100h+arg_38]
0x180006324  mov     r12, rdx
0x180006327  mov     [rbp+100h+var_170], rax
0x18000632b  mov     [rbp+100h+var_160], ebx
0x18000632e  mov     qword ptr [rsp+200h+cchWideChar], rdx
0x180006333  mov     [rsp+200h+var_188], r13
0x180006338  mov     [rbp+100h+lpCriticalSection], rdi
0x18000633c  call    ?Lock@CComSafeDeleteCriticalSection@ATL@@QEAAJXZ; ATL::CComSafeDeleteCriticalSection::Lock(void)
0x180006341  xor     r14d, r14d
0x180006344  test    ebx, ebx
0x180006346  setnz   r14b
0x18000634a  xor     eax, eax
0x18000634c  add     r14d, 2
0x180006350  mov     [rsp+200h+var_1A0], rax
0x180006355  xor     ebx, ebx
0x180006357  mov     [rsp+200h+var_1BC], r14d
0x18000635c  mov     [rbp+100h+lpBuffer], rax
0x180006360  mov     [rbp+100h+bstrString], rbx
0x180006364  mov     [rsp+200h+var_190], eax
0x180006368  test    r13, r13
0x18000636b  jz      loc_180006BA2
0x180006371  mov     ecx, 1
0x180006376  call    ?HrIsAllowedCOMCallLocality@@YAJW4CALL_LOCALITY@@@Z; HrIsAllowedCOMCallLocality(CALL_LOCALITY)
0x18000637b  mov     edi, eax
0x18000637d  test    eax, eax
0x18000637f  jns     short loc_1800063CD
0x180006381  mov     ecx, ebx; bstrString
0x180006383  call    cs:__imp_SysFreeString
0x18000638a  nop     dword ptr [rax+rax+00h]
0x18000638f  lea     rsi, WPP_GLOBAL_Control
0x180006396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000639d  cmp     rcx, rsi
0x1800063a0  jz      loc_1800066DE
0x1800063a6  test    byte ptr [rcx+1Ch], 1
0x1800063aa  jz      loc_1800066DE
0x1800063b0  mov     rcx, [rcx+10h]
0x1800063b4  lea     r8, WPP_d1632e28abac3523b7923f2ce652edb2_Traceguids
0x1800063bb  mov     edx, 0Ah
0x1800063c0  mov     r9d, edi
0x1800063c3  call    WPP_SF_d
0x1800063c8  jmp     loc_1800066DE
0x1800063cd  mov     [rsp+200h+nNumberOfBytesToRead], ebx
0x1800063d1  xor     r13d, r13d
0x1800063d4  lea     rbx, [r15+230h]
0x1800063db  mov     [rsp+200h+cchMax], r13
0x1800063e0  mov     rcx, rbx; lpCriticalSection
0x1800063e3  call    cs:__imp_EnterCriticalSection
0x1800063ea  nop     dword ptr [rax+rax+00h]
0x1800063ef  mov     r8d, [r15+68h]
0x1800063f3  xor     eax, eax
0x1800063f5  cmp     eax, r8d
0x1800063f8  jge     loc_180006A82
0x1800063fe  mov     rcx, [r12]
0x180006402  movsxd  r9, eax
0x180006405  mov     rdx, r9
0x180006408  shl     rdx, 4
0x18000640c  add     rdx, [r15+60h]
0x180006410  sub     rcx, [rdx]
0x180006413  jnz     short loc_18000641E
0x180006415  mov     rcx, [r12+8]
0x18000641a  sub     rcx, [rdx+8]
0x18000641e  test    rcx, rcx
0x180006421  jnz     loc_180006A7B
0x180006427  mov     rax, [r15+70h]
0x18000642b  mov     rcx, rbx; lpCriticalSection
0x18000642e  lea     rdi, [rax+r9*8]
0x180006432  call    cs:__imp_LeaveCriticalSection
0x180006439  nop     dword ptr [rax+rax+00h]
0x18000643e  test    rdi, rdi
0x180006441  jnz     loc_180006C58
0x180006447  mov     [rsp+200h+var_1BC], r14d
0x18000644c  lea     rsi, WPP_GLOBAL_Control
0x180006453  test    r14d, r14d
0x180006456  js      loc_180006DFA
0x18000645c  mov     eax, r14d
0x18000645f  mov     edx, 0FFFFFFFFh
0x180006464  shl     rax, 3
0x180006468  cmp     rax, rdx
0x18000646b  ja      loc_180006BBB
0x180006471  mov     ecx, eax; cb
0x180006473  xor     edi, edi
0x180006475  call    cs:__imp_CoTaskMemAlloc
0x18000647c  nop     dword ptr [rax+rax+00h]
0x180006481  mov     [rsp+200h+cchMax], rax
0x180006486  mov     r13, rax
0x180006489  test    rax, rax
0x18000648c  jz      loc_180006DFA
0x180006492  test    edi, edi
0x180006494  js      loc_180006BD9
0x18000649a  mov     rdi, [rsp+200h+cchMax]
0x18000649f  xor     edx, edx; Val
0x1800064a1  movsxd  r8, r14d
0x1800064a4  mov     rcx, rdi; void *
0x1800064a7  shl     r8, 3; Size
0x1800064ab  mov     [rsp+200h+var_1C0], 0
0x1800064b3  call    memset_0
0x1800064b8  mov     rcx, rbx; lpCriticalSection
0x1800064bb  call    cs:__imp_EnterCriticalSection
0x1800064c2  nop     dword ptr [rax+rax+00h]
0x1800064c7  xor     edx, edx
0x1800064c9  mov     [rsp+200h+pv], rdi
0x1800064ce  mov     r13, rdi
0x1800064d1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800064d8  cmp     edx, [r15+48h]
0x1800064dc  jge     loc_180006722
0x1800064e2  mov     rax, [r12]
0x1800064e6  movsxd  r8, edx
0x1800064e9  mov     rcx, r8
0x1800064ec  shl     rcx, 4
0x1800064f0  add     rcx, [r15+40h]
0x1800064f4  sub     rax, [rcx]
0x1800064f7  jnz     short loc_180006502
0x1800064f9  mov     rax, [r12+8]
0x1800064fe  sub     rax, [rcx+8]
0x180006502  test    rax, rax
0x180006505  jnz     loc_18000671B
0x18000650b  mov     rax, [r15+50h]
0x18000650f  mov     rcx, rbx; lpCriticalSection
0x180006512  lea     r12, [rax+r8*8]
0x180006516  call    cs:__imp_LeaveCriticalSection
0x18000651d  nop     dword ptr [rax+rax+00h]
0x180006522  test    r12, r12
0x180006525  jz      loc_1800069C9
0x18000652b  test    r13, r13
0x18000652e  jz      loc_180006E36
0x180006534  mov     eax, 2
0x180006539  mov     r15d, 28h ; '('
0x18000653f  mul     r15
0x180006542  xor     ebx, ebx
0x180006544  test    rdx, rdx
0x180006547  jnz     loc_1800069D3
0x18000654d  mov     rcx, rax; cb
0x180006550  call    cs:__imp_CoTaskMemAlloc
0x180006557  nop     dword ptr [rax+rax+00h]
0x18000655c  mov     [rdi], rax
0x18000655f  mov     [rsp+200h+pv], r13
0x180006564  mov     [rsp+200h+var_1BC], r14d
0x180006569  test    rax, rax
0x18000656c  jz      loc_180006E40
0x180006572  mov     [rsp+200h+cchMax], rdi
0x180006577  lea     r11, WPP_GLOBAL_Control
0x18000657e  mov     rcx, [r13+0]; pszDest
0x180006582  mov     rdx, r15; cchDest
0x180006585  call    StringValidateDestW
0x18000658a  mov     edi, eax
0x18000658c  test    eax, eax
0x18000658e  js      loc_180006E96
0x180006594  lea     r9, aContentTypeTex; "Content-Type: text/xml; charset=\"utf-8"...
0x18000659b  call    StringCopyWorkerW
0x1800065a0  mov     edi, eax
0x1800065a2  test    edi, edi
0x1800065a4  jnz     loc_180006E9E
0x1800065aa  js      loc_1800069B8
0x1800065b0  mov     rcx, [r12]; pbstr
0x1800065b4  mov     [rsp+200h+var_1C0], 1
0x1800065bc  call    cs:__imp_SysStringLen
0x1800065c3  nop     dword ptr [rax+rax+00h]
0x1800065c8  mov     r8, [r12]; lpWideCharStr
0x1800065cc  xor     edx, edx; dwFlags
0x1800065ce  mov     [rsp+200h+lpUsedDefaultChar], rbx; lpUsedDefaultChar
0x1800065d3  mov     r9d, eax; cchWideChar
0x1800065d6  mov     [rsp+200h+lpDefaultChar], rbx; lpDefaultChar
0x1800065db  mov     ecx, 0FDE9h; CodePage
0x1800065e0  mov     [rsp+200h+cbMultiByte], ebx; cbMultiByte
0x1800065e4  mov     [rsp+200h+lpMultiByteStr], rbx; lpMultiByteStr
0x1800065e9  mov     [rsp+200h+cchWideChar], eax
0x1800065ed  call    cs:__imp_WideCharToMultiByte
0x1800065f4  nop     dword ptr [rax+rax+00h]
0x1800065f9  movsxd  r13, eax
0x1800065fc  lea     r15d, [r13+1]
0x180006600  test    r15d, r15d
0x180006603  js      loc_180006ECF
0x180006609  mov     ecx, r15d; cb
0x18000660c  call    cs:__imp_CoTaskMemAlloc
0x180006613  nop     dword ptr [rax+rax+00h]
0x180006618  mov     rbx, rax
0x18000661b  test    rax, rax
0x18000661e  jz      loc_180006ECF
0x180006624  xor     edi, edi
0x180006626  jmp     short loc_180006630
0x180006628  test    edi, edi
0x18000662a  js      loc_180006BCF
0x180006630  mov     r9d, [rsp+200h+cchWideChar]; cchWideChar
0x180006635  xor     edx, edx; dwFlags
0x180006637  mov     r8, [r12]; lpWideCharStr
0x18000663b  mov     ecx, 0FDE9h; CodePage
0x180006640  mov     [rsp+200h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180006649  mov     [rsp+200h+lpDefaultChar], 0; lpDefaultChar
0x180006652  mov     [rsp+200h+cbMultiByte], r15d; cbMultiByte
0x180006657  mov     [rsp+200h+lpMultiByteStr], rbx; cchToCopy
0x18000665c  call    cs:__imp_WideCharToMultiByte
0x180006663  nop     dword ptr [rax+rax+00h]
0x180006668  test    eax, eax
0x18000666a  jz      loc_180006CDE
0x180006670  mov     r12, rbx
0x180006673  mov     [rsp+200h+var_1A0], rbx
0x180006678  mov     [rsp+200h+nNumberOfBytesToRead], r13d
0x18000667d  mov     byte ptr [r13+rbx+0], 0
0x180006683  mov     r13, [rsp+200h+pv]
0x180006688  test    edi, edi
0x18000668a  jz      loc_180006A96
0x180006690  js      loc_1800069FB
0x180006696  cmp     edi, 1
0x180006699  jz      loc_1800069FB
0x18000669f  mov     rax, [rsp+200h+var_188]
0x1800066a4  mov     rcx, [rbp+100h+var_180]
0x1800066a8  mov     rdx, [rbp+100h+var_178]
0x1800066ac  mov     r8, [rbp+100h+var_170]
0x1800066b0  lea     rsi, WPP_GLOBAL_Control
0x1800066b7  test    edi, edi
0x1800066b9  jnz     loc_180006C00
0x1800066bf  mov     [rcx], r14d
0x1800066c2  mov     rcx, [rbp+100h+bstrString]; bstrString
0x1800066c6  mov     [rax], r13
0x1800066c9  mov     eax, [rsp+200h+nNumberOfBytesToRead]
0x1800066cd  mov     [rdx], eax
0x1800066cf  mov     [r8], r12
0x1800066d2  call    cs:__imp_SysFreeString
0x1800066d9  nop     dword ptr [rax+rax+00h]
0x1800066de  mov     rcx, [rbp+100h+lpCriticalSection]; lpCriticalSection
0x1800066e2  call    cs:__imp_LeaveCriticalSection
0x1800066e9  nop     dword ptr [rax+rax+00h]
0x1800066ee  mov     eax, edi
0x1800066f0  mov     rcx, [rbp+100h+var_40]
0x1800066f7  xor     rcx, rsp; StackCookie
0x1800066fa  call    __security_check_cookie
0x1800066ff  mov     rbx, [rsp+200h+arg_8]
0x180006707  add     rsp, 1D0h
0x18000670e  pop     r15
0x180006710  pop     r14
0x180006712  pop     r13
0x180006714  pop     r12
0x180006716  pop     rdi
0x180006717  pop     rsi
0x180006718  pop     rbp
0x180006719  retn
0x18000671b  inc     edx
0x18000671d  jmp     loc_1800064D1
0x180006722  mov     rcx, rbx; lpCriticalSection
0x180006725  call    cs:__imp_LeaveCriticalSection
0x18000672c  nop     dword ptr [rax+rax+00h]
0x180006731  mov     rcx, rbx; lpCriticalSection
0x180006734  call    cs:__imp_EnterCriticalSection
0x18000673b  nop     dword ptr [rax+rax+00h]
0x180006740  mov     edx, [r15+0A8h]
0x180006747  xor     ecx, ecx
0x180006749  cmp     ecx, edx
0x18000674b  jge     loc_1800069E7
0x180006751  mov     r9, [r15+0A0h]
0x180006758  mov     rax, [r12]
0x18000675c  movsxd  r8, ecx
0x18000675f  shl     r8, 4
0x180006763  sub     rax, [r9+r8]
0x180006767  jnz     short loc_180006773
0x180006769  mov     rax, [r12+8]
0x18000676e  sub     rax, [r9+r8+8]
0x180006773  test    rax, rax
0x180006776  jnz     loc_1800069C2
0x18000677c  mov     r12, [r15+0B0h]
0x180006783  mov     rcx, rbx; lpCriticalSection
0x180006786  add     r12, r8
0x180006789  mov     [rbp+100h+var_150], r12
0x18000678d  call    cs:__imp_LeaveCriticalSection
0x180006794  nop     dword ptr [rax+rax+00h]
0x180006799  test    r12, r12
0x18000679c  jz      loc_1800069F6
0x1800067a2  xor     ebx, ebx
0x1800067a4  mov     ecx, 1Ch; Size
0x1800067a9  mov     qword ptr [rsp+200h+cchWideChar], rbx
0x1800067ae  call    cs:__imp_malloc
0x1800067b5  nop     dword ptr [rax+rax+00h]
0x1800067ba  mov     r15, rax
0x1800067bd  test    rax, rax
0x1800067c0  jz      loc_180006F12
0x1800067c6  mov     edx, 0Eh; cchDest
0x1800067cb  call    StringValidateDestW
0x1800067d0  mov     edi, eax
  ... truncated ...
```
