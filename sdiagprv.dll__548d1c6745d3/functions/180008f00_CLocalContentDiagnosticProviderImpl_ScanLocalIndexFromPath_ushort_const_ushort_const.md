# CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath(ushort const *,ushort const *)

- ea: `0x180008f00`
- end: `0x1800095fe`
- name: `?ScanLocalIndexFromPath@CLocalContentDiagnosticProviderImpl@@AEAAJPEBG0@Z`
- size: `1790`
- prototype: `__int64 __fastcall(CLocalContentDiagnosticProviderImpl *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002bf0`
- `0x1800031d8`
- `0x1800032ec`
- `0x18000331c`
- `0x180003400`
- `0x1800034e4`
- `0x180007ce0`
- `0x1800083ec`
- `0x18000855c`
- `0x180008f00`
- `0x180009604`
- `0x18001374c`
- `0x180014e7c`
- `0x180014f1c`
- `0x1800180be`
- `0x1800180f0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008fea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090a6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008fea`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800090a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009564`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009564`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000952a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009556`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008fd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009093`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000952a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009438`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000954b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000954b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180009069`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x180009069`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800093e7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800093e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180009187`
- `OLEAUT32!__imp_SysAllocString` at `0x180009187`

## string_xrefs

- `0x18000901c`: `*.xml`
- `0x180009420`: `CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath`
- `0x1800094f9`: `CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath`
- `0x180009516`: `CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath`
- `0x1800094d0`: `IndexDirectory`
- `0x1800094e7`: `IndexPath`

## pseudocode

```c
__int64 __fastcall CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath(
        CLocalContentDiagnosticProviderImpl *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *v3; // r12
  unsigned __int16 *v5; // rsi
  __int64 FirstFile; // r15
  void *v7; // r14
  CDiagnostic *v8; // rdi
  int v9; // eax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r9
  signed int LastError; // ebx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v15; // rax
  int v16; // r12d
  HANDLE v17; // rax
  void *v18; // rax
  BSTR v19; // rax
  struct IXMLDOMDocumentVtbl *lpVtbl; // rax
  __int64 v21; // r8
  __int64 *v22; // rdx
  CDiagnostic *Class; // rax
  int v24; // eax
  char v25; // al
  bool v26; // zf
  bool v27; // sf
  __int64 v28; // r9
  const char *v29; // rax
  HANDLE v30; // rax
  HANDLE v31; // rax
  __int16 v33; // [rsp+30h] [rbp-308h] BYREF
  struct IXMLDOMDocument *v34; // [rsp+38h] [rbp-300h] BYREF
  const unsigned __int16 *v35; // [rsp+40h] [rbp-2F8h]
  SIZE_T dwBytes; // [rsp+48h] [rbp-2F0h] BYREF
  __int64 v37; // [rsp+50h] [rbp-2E8h] BYREF
  struct IXMLDOMNode *v38; // [rsp+58h] [rbp-2E0h] BYREF
  const unsigned __int16 *v39; // [rsp+60h] [rbp-2D8h]
  struct tagVARIANT v40; // [rsp+68h] [rbp-2D0h] BYREF
  struct tagVARIANT v41; // [rsp+80h] [rbp-2B8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-298h] BYREF

  v3 = a3;
  v39 = a3;
  v35 = a2;
  dwBytes = 0;
  v5 = 0;
  FirstFile = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v33 = -1;
  v34 = 0;
  memset(&v40, 0, sizeof(v40));
  v7 = 0;
  v37 = 0;
  v38 = 0;
  v8 = 0;
  v9 = SDiagPrviVariantInit(&v40);
  v12 = v35;
  LastError = v9;
  if ( v9 >= 0 )
  {
    if ( !v35 )
    {
      LastError = -2147024809;
LABEL_79:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_88;
      v29 = "IndexDirectory";
LABEL_84:
      McTemplateU0sqs_EventWriteTransfer(
        v11,
        (_DWORD)v10,
        (unsigned int)"CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath",
        -2147024809,
        (__int64)v29);
      goto LABEL_88;
    }
    if ( !v3 )
    {
      LastError = -2147024809;
      goto LABEL_82;
    }
    LastError = ULongLongMult(0x104u, 2u, &dwBytes);
    if ( LastError >= 0 )
    {
      ProcessHeap = GetProcessHeap();
      v15 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
      v5 = v15;
      if ( !v15 )
      {
        LastError = -2147024882;
LABEL_76:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_88;
        v28 = (unsigned int)LastError;
        goto LABEL_87;
      }
      v16 = 1;
      memset_0(v15, 0, dwBytes);
      LastError = StringCchPrintfW(v5, 0x104u, L"%s\\%s\\%s", v35, v39, L"*.xml");
      if ( LastError < 0 )
        goto LABEL_68;
      FirstFile = (__int64)FindFirstFileExW(v5, FindExInfoStandard, &FindFileData, FindExSearchNameMatch, 0, 0);
      if ( (unsigned __int64)(FirstFile - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        if ( LastError == 2 || LastError == 3 )
          goto LABEL_57;
        v26 = LastError == 53;
LABEL_63:
        if ( v26 )
        {
LABEL_57:
          LastError = 0;
LABEL_58:
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(
              v11,
              SDIAGPRV_EVENT_DEBUG_SUCCESS,
              "CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath");
          goto LABEL_88;
        }
        v27 = LastError < 0;
        if ( LastError > 0 )
        {
          LastError = (unsigned __int16)LastError | 0x80070000;
LABEL_66:
          v27 = LastError < 0;
        }
        if ( !v27 )
          goto LABEL_70;
        goto LABEL_68;
      }
      v11 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) )
        goto LABEL_75;
      v17 = GetProcessHeap();
      v18 = HeapAlloc(v17, 8u, dwBytes);
      v7 = v18;
      if ( !v18 )
      {
LABEL_13:
        LastError = -2147024882;
        goto LABEL_68;
      }
      memset_0(v18, 0, dwBytes);
      LastError = SDiagPrviCreateXmlDocument(&v34);
      if ( LastError < 0 || (LastError = SDiagPrviSetDOMProperties(v34, v10), LastError < 0) )
      {
LABEL_68:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 2) != 0 )
          McTemplateU0qz_EventWriteTransfer(
            v11,
            SDIAGPRV_EVENT_LOCAL_CONTENT_DIAGNOSTIC_PROVIDER_SCAN_INDEX_FAIL,
            (unsigned int)LastError,
            v5);
LABEL_70:
        if ( !v16 )
        {
LABEL_71:
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            McTemplateU0z_EventWriteTransfer(v11, SDIAGPRV_EVENT_PERF_SCAN_INDEX_END, v40.llVal);
        }
        v12 = v35;
        v3 = v39;
        goto LABEL_74;
      }
      while ( 1 )
      {
        v11 = 0;
        v16 = 1;
        if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) )
          goto LABEL_66;
        memset_0(v7, 0, dwBytes);
        LastError = StringCchPrintfW((unsigned __int16 *)v7, 0x104u, L"%s\\%s\\%s", v35, v39, FindFileData.cFileName);
        if ( LastError < 0 )
          goto LABEL_68;
        SDiagPrviVariantClear(&v40);
        v40.vt = 8;
        v19 = SysAllocString((const OLECHAR *)v7);
        v40.llVal = (LONGLONG)v19;
        if ( !v19 )
          goto LABEL_13;
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
          McTemplateU0z_EventWriteTransfer(v11, SDIAGPRV_EVENT_PERF_SCAN_INDEX_START, v19);
        v16 = 0;
        lpVtbl = v34->lpVtbl;
        v41 = v40;
        LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, struct tagVARIANT *, __int16 *))lpVtbl->load)(
                      v34,
                      &v41,
                      &v33);
        if ( LastError < 0 )
          goto LABEL_68;
        if ( v33 )
        {
          v11 = 0;
          if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) )
            goto LABEL_71;
          if ( v37 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v37 = 0;
          }
          LastError = ((__int64 (__fastcall *)(struct IXMLDOMDocument *, __int64 *))v34->lpVtbl->get_documentElement)(
                        v34,
                        &v37);
          if ( LastError < 0 )
            goto LABEL_68;
          if ( v38 )
          {
            ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
            v38 = 0;
          }
          LastError = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IXMLDOMNode **))v37)(
                        v37,
                        &IID_IXMLDOMNode,
                        &v38);
          if ( LastError < 0 )
            goto LABEL_68;
          if ( v8 )
            (*(void (__fastcall **)(CDiagnostic *))(*(_QWORD *)v8 + 16LL))(v8);
          Class = CreateClassObject<CDiagnostic>();
          v8 = Class;
          if ( !Class )
            goto LABEL_13;
          v24 = CDiagnostic::Load(Class, v38);
          LastError = v24;
          if ( v24 >= 0 )
          {
            v11 = 0;
            if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) )
              goto LABEL_71;
            LastError = CDiagnostic::put_IsLocal(v8, -1);
            if ( LastError < 0 )
              goto LABEL_68;
            LastError = CDiagnostic::put_Url(v8, v40.bstrVal);
            if ( LastError < 0 )
              goto LABEL_68;
            v11 = 0;
            if ( _InterlockedCompareExchange((volatile signed __int32 *)this + 12, 0, 1) )
              goto LABEL_71;
            LastError = CLocalContentDiagnosticProviderImpl::AddDiagnosticToResult(this, v8);
            if ( LastError < 0 )
              goto LABEL_68;
            v25 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
            if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            {
              McTemplateU0z_EventWriteTransfer(v11, SDIAGPRV_EVENT_PERF_SCAN_INDEX_END, v40.llVal);
              v25 = Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits;
            }
            if ( (v25 & 1) != 0 )
              McTemplateU0z_EventWriteTransfer(
                v11,
                SDIAGPRV_EVENT_LOCAL_CONTENT_DIAGNOSTIC_PROVIDER_SCAN_INDEX,
                v40.llVal);
            v16 = 1;
            if ( *((_DWORD *)this + 8) )
              goto LABEL_75;
            goto LABEL_52;
          }
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x800) != 0 )
          {
            v21 = (unsigned int)v24;
            v22 = SDIAGPRV_EVENT_DEBUG_DESERIALIZE_DIAGNOSTIC_FAIL;
            goto LABEL_25;
          }
        }
        else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x800) != 0 )
        {
          v21 = (unsigned int)LastError;
          v22 = SDIAGPRV_EVENT_DEBUG_DESERIALIZE_DIAGNOSTIC_INVALID_XML;
LABEL_25:
          McTemplateU0qz_EventWriteTransfer(v11, v22, v21, v40.llVal);
        }
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
          McTemplateU0z_EventWriteTransfer(v11, SDIAGPRV_EVENT_PERF_SCAN_INDEX_END, v40.llVal);
        LastError = 0;
        v16 = 1;
LABEL_52:
        if ( !FindNextFileW((HANDLE)FirstFile, &FindFileData) )
        {
          LastError = GetLastError();
          if ( LastError != 2 && LastError != 3 && LastError != 18 )
          {
            v26 = LastError == 53;
            goto LABEL_63;
          }
          goto LABEL_57;
        }
      }
    }
  }
LABEL_74:
  if ( LastError != -2147024809 )
  {
LABEL_75:
    if ( LastError )
      goto LABEL_76;
    goto LABEL_58;
  }
  if ( !v12 )
    goto LABEL_79;
  if ( !v3 )
  {
LABEL_82:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_88;
    v29 = "IndexPath";
    goto LABEL_84;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v28 = 2147942487LL;
LABEL_87:
    McTemplateU0sq_EventWriteTransfer(v11, v10, "CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath", v28);
  }
LABEL_88:
  if ( v5 )
  {
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v5);
  }
  if ( (unsigned __int64)(FirstFile - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFile);
  if ( v7 )
  {
    v31 = GetProcessHeap();
    HeapFree(v31, 0, v7);
  }
  SDiagPrviVariantClear(&v40);
  if ( v34 )
  {
    ((void (__fastcall *)(struct IXMLDOMDocument *))v34->lpVtbl->Release)(v34);
    v34 = 0;
  }
  if ( v37 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    v37 = 0;
  }
  if ( v38 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v38->lpVtbl->Release)(v38);
    v38 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(CDiagnostic *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180008f00  push    rbx
0x180008f02  push    rsi
0x180008f03  push    rdi
0x180008f04  push    r12
0x180008f06  push    r13
0x180008f08  push    r14
0x180008f0a  push    r15
0x180008f0c  sub     rsp, 300h
0x180008f13  mov     rax, cs:__security_cookie
0x180008f1a  xor     rax, rsp
0x180008f1d  mov     [rsp+338h+var_48], rax
0x180008f25  mov     r12, r8
0x180008f28  mov     [rsp+338h+var_2D8], r8
0x180008f2d  mov     [rsp+338h+var_2F8], rdx
0x180008f32  mov     r13, rcx
0x180008f35  xor     ebx, ebx
0x180008f37  lea     rcx, [rsp+338h+FindFileData]; void *
0x180008f3f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008f43  mov     [rsp+338h+dwBytes], rbx
0x180008f48  xor     edx, edx; Val
0x180008f4a  mov     r8d, 250h; Size
0x180008f50  mov     esi, ebx
0x180008f52  mov     r15, rdi
0x180008f55  call    memset_0
0x180008f5a  xorps   xmm0, xmm0
0x180008f5d  mov     [rsp+338h+var_308], di
0x180008f62  xor     eax, eax
0x180008f64  mov     [rsp+338h+var_300], rbx
0x180008f69  lea     rcx, [rsp+338h+var_2D0]; struct tagVARIANT *
0x180008f6e  mov     qword ptr [rsp+338h+var_2D0+10h], rax
0x180008f73  movups  xmmword ptr [rsp+338h+var_2D0], xmm0
0x180008f78  mov     r14d, ebx
0x180008f7b  mov     [rsp+338h+var_2E8], rbx
0x180008f80  mov     [rsp+338h+var_2E0], rbx
0x180008f85  mov     edi, ebx
0x180008f87  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x180008f8c  mov     r9, [rsp+338h+var_2F8]
0x180008f91  mov     ebx, eax
0x180008f93  test    eax, eax
0x180008f95  js      loc_1800094A4
0x180008f9b  test    r9, r9
0x180008f9e  jnz     short loc_180008FAA
0x180008fa0  mov     ebx, 80070057h
0x180008fa5  jmp     loc_1800094C7
0x180008faa  test    r12, r12
0x180008fad  jnz     short loc_180008FB9
0x180008faf  mov     ebx, 80070057h
0x180008fb4  jmp     loc_1800094DE
0x180008fb9  lea     r8, [rsp+338h+dwBytes]; unsigned __int64 *
0x180008fbe  mov     edx, 2; unsigned __int64
0x180008fc3  mov     ecx, 104h; unsigned __int64
0x180008fc8  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180008fcd  mov     ebx, eax
0x180008fcf  test    eax, eax
0x180008fd1  js      loc_1800094A4
0x180008fd7  call    cs:__imp_GetProcessHeap
0x180008fdd  mov     r8, [rsp+338h+dwBytes]; dwBytes
0x180008fe2  mov     edx, 8; dwFlags
0x180008fe7  mov     rcx, rax; hHeap
0x180008fea  call    cs:__imp_HeapAlloc
0x180008ff0  mov     rsi, rax
0x180008ff3  test    rax, rax
0x180008ff6  jnz     short loc_180009002
0x180008ff8  mov     ebx, 8007000Eh
0x180008ffd  jmp     loc_1800094B4
0x180009002  mov     r8, [rsp+338h+dwBytes]; Size
0x180009007  xor     edx, edx; Val
0x180009009  mov     rcx, rsi; void *
0x18000900c  mov     r12d, 1
0x180009012  call    memset_0
0x180009017  mov     r9, [rsp+338h+var_2F8]
0x18000901c  lea     rax, aXml; "*.xml"
0x180009023  mov     qword ptr [rsp+338h+dwAdditionalFlags], rax
0x180009028  lea     r8, aSSS; "%s\\%s\\%s"
0x18000902f  mov     rax, [rsp+338h+var_2D8]
0x180009034  mov     edx, 104h; unsigned __int64
0x180009039  mov     rcx, rsi; unsigned __int16 *
0x18000903c  mov     [rsp+338h+lpSearchFilter], rax
0x180009041  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009046  mov     ebx, eax
0x180009048  test    eax, eax
0x18000904a  js      loc_180009460
0x180009050  mov     [rsp+338h+dwAdditionalFlags], edi; dwAdditionalFlags
0x180009054  lea     r8, [rsp+338h+FindFileData]; lpFindFileData
0x18000905c  xor     r9d, r9d; fSearchOp
0x18000905f  mov     [rsp+338h+lpSearchFilter], rdi; lpSearchFilter
0x180009064  xor     edx, edx; fInfoLevelId
0x180009066  mov     rcx, rsi; lpFileName
0x180009069  call    cs:__imp_FindFirstFileExW
0x18000906f  mov     r15, rax
0x180009072  lea     rcx, [rax-1]
0x180009076  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000907a  ja      loc_180009438
0x180009080  xor     ecx, ecx
0x180009082  mov     eax, r12d
0x180009085  lock cmpxchg [r13+30h], ecx
0x18000908b  test    eax, eax
0x18000908d  jnz     loc_1800094AC
0x180009093  call    cs:__imp_GetProcessHeap
0x180009099  mov     r8, [rsp+338h+dwBytes]; dwBytes
0x18000909e  lea     edx, [r12+7]; dwFlags
0x1800090a3  mov     rcx, rax; hHeap
0x1800090a6  call    cs:__imp_HeapAlloc
0x1800090ac  mov     r14, rax
0x1800090af  test    rax, rax
0x1800090b2  jnz     short loc_1800090BE
0x1800090b4  mov     ebx, 8007000Eh
0x1800090b9  jmp     loc_180009460
0x1800090be  mov     r8, [rsp+338h+dwBytes]; Size
0x1800090c3  xor     edx, edx; Val
0x1800090c5  mov     rcx, r14; void *
0x1800090c8  call    memset_0
0x1800090cd  mov     rcx, [rsp+338h+var_300]
0x1800090d2  test    rcx, rcx
0x1800090d5  jz      short loc_1800090E8
0x1800090d7  mov     rax, [rcx]
0x1800090da  mov     rax, [rax+10h]
0x1800090de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090e3  mov     [rsp+338h+var_300], rdi
0x1800090e8  lea     rcx, [rsp+338h+var_300]; struct IXMLDOMDocument **
0x1800090ed  call    ?SDiagPrviCreateXmlDocument@@YAJPEAPEAUIXMLDOMDocument@@@Z; SDiagPrviCreateXmlDocument(IXMLDOMDocument * *)
0x1800090f2  mov     ebx, eax
0x1800090f4  test    eax, eax
0x1800090f6  js      loc_180009460
0x1800090fc  mov     rcx, [rsp+338h+var_300]; struct IXMLDOMDocument *
0x180009101  call    ?SDiagPrviSetDOMProperties@@YAJPEAUIXMLDOMDocument@@PEBG@Z; SDiagPrviSetDOMProperties(IXMLDOMDocument *,ushort const *)
0x180009106  mov     ebx, eax
0x180009108  test    eax, eax
0x18000910a  js      loc_180009460
0x180009110  xor     ecx, ecx
0x180009112  lea     r12d, [rcx+1]
0x180009116  mov     eax, r12d
0x180009119  lock cmpxchg [r13+30h], ecx
0x18000911f  test    eax, eax
0x180009121  jnz     loc_18000945C
0x180009127  mov     r8, [rsp+338h+dwBytes]; Size
0x18000912c  xor     edx, edx; Val
0x18000912e  mov     rcx, r14; void *
0x180009131  call    memset_0
0x180009136  mov     r9, [rsp+338h+var_2F8]
0x18000913b  lea     rax, [rsp+338h+var_26C]
0x180009143  mov     qword ptr [rsp+338h+dwAdditionalFlags], rax
0x180009148  lea     r8, aSSS; "%s\\%s\\%s"
0x18000914f  mov     rax, [rsp+338h+var_2D8]
0x180009154  mov     edx, 104h; unsigned __int64
0x180009159  mov     rcx, r14; unsigned __int16 *
0x18000915c  mov     [rsp+338h+lpSearchFilter], rax
0x180009161  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009166  mov     ebx, eax
0x180009168  test    eax, eax
0x18000916a  js      loc_180009460
0x180009170  lea     rcx, [rsp+338h+var_2D0]; struct tagVARIANT *
0x180009175  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18000917a  lea     eax, [r12+7]
0x18000917f  mov     rcx, r14; psz
0x180009182  mov     word ptr [rsp+338h+var_2D0], ax
0x180009187  call    cs:__imp_SysAllocString
0x18000918d  mov     qword ptr [rsp+338h+var_2D0+8], rax
0x180009192  test    rax, rax
0x180009195  jz      loc_1800090B4
0x18000919b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x1800091a2  jz      short loc_1800091B3
0x1800091a4  mov     r8, rax
0x1800091a7  lea     rdx, SDIAGPRV_EVENT_PERF_SCAN_INDEX_START
0x1800091ae  call    McTemplateU0z_EventWriteTransfer
0x1800091b3  mov     rcx, [rsp+338h+var_300]
0x1800091b8  lea     r8, [rsp+338h+var_308]
0x1800091bd  movups  xmm0, xmmword ptr [rsp+338h+var_2D0]
0x1800091c2  lea     rdx, [rsp+338h+var_2B8]
0x1800091ca  xor     r12d, r12d
0x1800091cd  movsd   xmm1, qword ptr [rsp+338h+var_2D0+10h]
0x1800091d3  mov     rax, [rcx]
0x1800091d6  movaps  [rsp+338h+var_2B8], xmm0
0x1800091de  movsd   [rsp+338h+var_2A8], xmm1
0x1800091e7  mov     rax, [rax+1D0h]
0x1800091ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f3  mov     ebx, eax
0x1800091f5  test    eax, eax
0x1800091f7  js      loc_180009460
0x1800091fd  xor     eax, eax
0x1800091ff  cmp     ax, [rsp+338h+var_308]
0x180009204  jnz     short loc_180009248
0x180009206  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 8
0x18000920d  jz      short loc_180009223
0x18000920f  mov     r8d, ebx
0x180009212  lea     rdx, SDIAGPRV_EVENT_DEBUG_DESERIALIZE_DIAGNOSTIC_INVALID_XML
0x180009219  mov     r9, qword ptr [rsp+338h+var_2D0+8]
0x18000921e  call    McTemplateU0qz_EventWriteTransfer
0x180009223  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x18000922a  jz      short loc_18000923D
0x18000922c  mov     r8, qword ptr [rsp+338h+var_2D0+8]
0x180009231  lea     rdx, SDIAGPRV_EVENT_PERF_SCAN_INDEX_END
0x180009238  call    McTemplateU0z_EventWriteTransfer
0x18000923d  xor     ebx, ebx
0x18000923f  lea     r12d, [rbx+1]
0x180009243  jmp     loc_1800093DC
0x180009248  xor     ecx, ecx
0x18000924a  lea     eax, [rcx+1]
0x18000924d  lock cmpxchg [r13+30h], ecx
0x180009253  test    eax, eax
0x180009255  jnz     loc_180009480
0x18000925b  mov     rcx, [rsp+338h+var_2E8]
0x180009260  test    rcx, rcx
0x180009263  jz      short loc_180009276
0x180009265  mov     rax, [rcx]
0x180009268  mov     rax, [rax+10h]
0x18000926c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009271  mov     [rsp+338h+var_2E8], r12
0x180009276  mov     rcx, [rsp+338h+var_300]
0x18000927b  lea     rdx, [rsp+338h+var_2E8]
0x180009280  mov     rax, [rcx]
0x180009283  mov     rax, [rax+168h]
0x18000928a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000928f  mov     ebx, eax
0x180009291  test    eax, eax
0x180009293  js      loc_180009460
0x180009299  mov     rcx, [rsp+338h+var_2E0]
0x18000929e  test    rcx, rcx
0x1800092a1  jz      short loc_1800092B4
0x1800092a3  mov     rax, [rcx]
0x1800092a6  mov     rax, [rax+10h]
0x1800092aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092af  mov     [rsp+338h+var_2E0], r12
0x1800092b4  mov     rcx, [rsp+338h+var_2E8]
0x1800092b9  lea     r8, [rsp+338h+var_2E0]
0x1800092be  lea     rdx, IID_IXMLDOMNode
0x1800092c5  mov     rax, [rcx]
0x1800092c8  mov     rax, [rax]
0x1800092cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092d0  mov     ebx, eax
0x1800092d2  test    eax, eax
0x1800092d4  js      loc_180009460
0x1800092da  test    rdi, rdi
0x1800092dd  jz      short loc_1800092EE
0x1800092df  mov     rax, [rdi]
0x1800092e2  mov     rcx, rdi
0x1800092e5  mov     rax, [rax+10h]
0x1800092e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092ee  call    ??$CreateClassObject@VCDiagnostic@@@@YAPEAVCDiagnostic@@XZ; CreateClassObject<CDiagnostic>(void)
0x1800092f3  mov     rdi, rax
0x1800092f6  test    rax, rax
0x1800092f9  jz      loc_1800090B4
0x1800092ff  mov     rdx, [rsp+338h+var_2E0]; struct IXMLDOMNode *
0x180009304  mov     rcx, rax; this
0x180009307  call    ?Load@CDiagnostic@@QEAAJPEAUIXMLDOMNode@@@Z; CDiagnostic::Load(IXMLDOMNode *)
0x18000930c  mov     ebx, eax
0x18000930e  test    eax, eax
0x180009310  jns     short loc_18000932E
0x180009312  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 8
0x180009319  jz      loc_180009223
0x18000931f  mov     r8d, eax
0x180009322  lea     rdx, SDIAGPRV_EVENT_DEBUG_DESERIALIZE_DIAGNOSTIC_FAIL
0x180009329  jmp     loc_180009219
0x18000932e  xor     ecx, ecx
0x180009330  lea     eax, [rcx+1]
0x180009333  lock cmpxchg [r13+30h], ecx
0x180009339  test    eax, eax
0x18000933b  jnz     loc_180009480
0x180009341  or      edx, 0FFFFFFFFh; __int16
0x180009344  mov     rcx, rdi; this
0x180009347  call    ?put_IsLocal@CDiagnostic@@QEAAJF@Z; CDiagnostic::put_IsLocal(short)
0x18000934c  mov     ebx, eax
0x18000934e  test    eax, eax
0x180009350  js      loc_180009460
0x180009356  mov     rdx, qword ptr [rsp+338h+var_2D0+8]; unsigned __int16 *
0x18000935b  mov     rcx, rdi; this
0x18000935e  call    ?put_Url@CDiagnostic@@QEAAJPEAG@Z; CDiagnostic::put_Url(ushort *)
0x180009363  mov     ebx, eax
0x180009365  test    eax, eax
0x180009367  js      loc_180009460
0x18000936d  xor     ecx, ecx
0x18000936f  lea     eax, [rcx+1]
0x180009372  lock cmpxchg [r13+30h], ecx
0x180009378  test    eax, eax
0x18000937a  jnz     loc_180009480
0x180009380  mov     rdx, rdi; struct CDiagnostic *
0x180009383  mov     rcx, r13; this
0x180009386  call    ?AddDiagnosticToResult@CLocalContentDiagnosticProviderImpl@@AEAAJPEAVCDiagnostic@@@Z; CLocalContentDiagnosticProviderImpl::AddDiagnosticToResult(CDiagnostic *)
0x18000938b  mov     ebx, eax
0x18000938d  test    eax, eax
0x18000938f  js      loc_180009460
0x180009395  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits
0x18000939b  test    al, 20h
0x18000939d  jz      short loc_1800093B6
0x18000939f  mov     r8, qword ptr [rsp+338h+var_2D0+8]
0x1800093a4  lea     rdx, SDIAGPRV_EVENT_PERF_SCAN_INDEX_END
0x1800093ab  call    McTemplateU0z_EventWriteTransfer
0x1800093b0  mov     eax, cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits
0x1800093b6  test    al, 1
0x1800093b8  jz      short loc_1800093CB
0x1800093ba  mov     r8, qword ptr [rsp+338h+var_2D0+8]
0x1800093bf  lea     rdx, SDIAGPRV_EVENT_LOCAL_CONTENT_DIAGNOSTIC_PROVIDER_SCAN_INDEX
0x1800093c6  call    McTemplateU0z_EventWriteTransfer
0x1800093cb  cmp     dword ptr [r13+20h], 0
0x1800093d0  mov     r12d, 1
0x1800093d6  jnz     loc_1800094AC
0x1800093dc  lea     rdx, [rsp+338h+FindFileData]; lpFindFileData
0x1800093e4  mov     rcx, r15; hFindFile
0x1800093e7  call    cs:__imp_FindNextFileW
0x1800093ed  test    eax, eax
  ... truncated ...
```
