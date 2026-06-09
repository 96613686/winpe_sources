# CLocalContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata(IDiagnosticMetadataCollection *,CDiagnosticCollection *)

- ea: `0x1800087e0`
- end: `0x180008cd5`
- name: `?FindDiagnosticsBySearchMetadata@CLocalContentDiagnosticProviderImpl@@UEAAJPEAUIDiagnosticMetadataCollection@@PEAVCDiagnosticCollection@@@Z`
- size: `1269`
- prototype: `__int64 __fastcall(CLocalContentDiagnosticProviderImpl *__hidden this, struct IDiagnosticMetadataCollection *, struct CDiagnosticCollection *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180002ac4`
- `0x1800034e4`
- `0x180008508`
- `0x1800087e0`
- `0x180008cdc`
- `0x180008f00`
- `0x180009948`
- `0x180011c80`
- `0x1800125e8`
- `0x1800180be`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008923`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180008923`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008ca3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008cbc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008911`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008c95`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008cae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008a51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180008a47`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180008a47`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c1e`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c1e`

## string_xrefs

- `0x1800089a5`: `LocalContentProviderConfiguration::CreateInstance`
- `0x1800089bc`: `LocalContentProviderConfiguration::CreateInstance`
- `0x1800089e0`: `LocalContentProviderConfiguration::CreateInstance`
- `0x1800089fe`: `LocalContentProviderConfiguration::CreateInstance`
- `0x180008ade`: `LocalContentProviderConfiguration::GetPathToLocalSystemIndex`
- `0x180008b34`: `LocalContentProviderConfiguration::GetPathToLocalSystemIndex`
- `0x180008b58`: `LocalContentProviderConfiguration::GetPathToLocalSystemIndex`
- `0x180008b7a`: `LocalContentProviderConfiguration::GetPathToLocalSystemIndex`

## pseudocode

```c
__int64 __fastcall CLocalContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata(
        CLocalContentDiagnosticProviderImpl *this,
        struct IDiagnosticMetadataCollection *a2,
        struct CDiagnosticCollection *a3)
{
  unsigned __int16 *v3; // r12
  LocalContentProviderConfiguration *v4; // r14
  void *v5; // r15
  WCHAR *v6; // r13
  struct CDiagnosticCollection *v7; // rsi
  struct IDiagnosticMetadataCollection *v8; // rax
  CLocalContentDiagnosticProviderImpl *v9; // rdi
  int PreferredUILanguage; // ebx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  CResourceLoader *v12; // rcx
  __int64 v13; // rcx
  HANDLE ProcessHeap; // rax
  WCHAR *v15; // rax
  LocalContentProviderConfiguration *v16; // rsi
  signed int LastError; // eax
  __int64 v18; // r9
  const unsigned __int16 *v19; // rcx
  unsigned int v20; // eax
  int v21; // eax
  const char *v22; // rax
  __int64 v23; // rcx
  CResourceLoader *v24; // rcx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  HANDLE v26; // rax
  HANDLE v27; // rax
  SIZE_T dwBytes; // [rsp+80h] [rbp+48h] BYREF
  struct IDiagnosticMetadataCollection *v30; // [rsp+88h] [rbp+50h]
  struct CDiagnosticCollection *v31; // [rsp+90h] [rbp+58h]
  unsigned __int16 *v32; // [rsp+98h] [rbp+60h] BYREF

  v31 = a3;
  v30 = a2;
  v3 = 0;
  v4 = 0;
  v5 = 0;
  v32 = 0;
  v6 = 0;
  dwBytes = 0;
  v7 = a3;
  v8 = a2;
  v9 = this;
  PreferredUILanguage = -2147024809;
  if ( a2 && a3 )
  {
    PreferredUILanguage = 0;
    this = 0;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)v9 + 12, 0, 1) )
    {
LABEL_43:
      v8 = v30;
      goto LABEL_44;
    }
    PreferredUILanguage = CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage(0, &v32);
    if ( PreferredUILanguage < 0 )
    {
      v3 = v32;
      goto LABEL_43;
    }
    v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v9 + 3);
    if ( v11 )
    {
      (**v11)(v11, 1);
      *((_QWORD *)v9 + 3) = 0;
    }
    v3 = v32;
    PreferredUILanguage = CDiagnosticMatcher::CreateInstance(v30, v32, (struct CDiagnosticMatcher **)v9 + 3);
    if ( PreferredUILanguage < 0 )
      goto LABEL_43;
    v12 = (CResourceLoader *)*((_QWORD *)v9 + 2);
    if ( v12 )
    {
      CResourceLoader::`scalar deleting destructor'(v12, (unsigned int)a2);
      *((_QWORD *)v9 + 2) = 0;
    }
    PreferredUILanguage = CResourceLoader::CreateInstance((struct CResourceLoader **)v9 + 2, (int)a2);
    if ( PreferredUILanguage < 0 )
      goto LABEL_43;
    this = 0;
    if ( _InterlockedCompareExchange((volatile signed __int32 *)v9 + 12, 0, 1) )
      goto LABEL_43;
    v13 = *((_QWORD *)v9 + 1);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    *((_QWORD *)v9 + 1) = v7;
    (*(void (__fastcall **)(struct CDiagnosticCollection *))(*(_QWORD *)v7 + 8LL))(v7);
    PreferredUILanguage = ULongLongMult(0x104u, 2u, &dwBytes);
    if ( PreferredUILanguage < 0 )
      goto LABEL_43;
    ProcessHeap = GetProcessHeap();
    v15 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, dwBytes);
    v6 = v15;
    if ( !v15 )
    {
      PreferredUILanguage = -2147024882;
      goto LABEL_43;
    }
    memset_0(v15, 0, dwBytes);
    v16 = (LocalContentProviderConfiguration *)operator new(0x10u);
    if ( v16 )
    {
      *((_QWORD *)v16 + 1) = 0;
      *(_QWORD *)v16 = &LocalContentProviderConfiguration::`vftable';
      PreferredUILanguage = LocalContentProviderConfiguration::Initialize(v16);
      if ( PreferredUILanguage != -2147024882 )
      {
        v4 = v16;
        if ( PreferredUILanguage < 0 )
          v4 = 0;
        if ( PreferredUILanguage == -2147024809 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
            McTemplateU0sq_EventWriteTransfer(
              this,
              a2,
              "LocalContentProviderConfiguration::CreateInstance",
              2147942487LL);
LABEL_34:
          (**(void (__fastcall ***)(LocalContentProviderConfiguration *, __int64))v16)(v16, 1);
LABEL_35:
          if ( PreferredUILanguage < 0 )
            goto LABEL_42;
          goto LABEL_36;
        }
        if ( !PreferredUILanguage )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
            goto LABEL_35;
          McTemplateU0s_EventWriteTransfer(
            this,
            SDIAGPRV_EVENT_DEBUG_SUCCESS,
            "LocalContentProviderConfiguration::CreateInstance");
          goto LABEL_36;
        }
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
          McTemplateU0sq_EventWriteTransfer(
            this,
            a2,
            "LocalContentProviderConfiguration::CreateInstance",
            (unsigned int)PreferredUILanguage);
LABEL_32:
        if ( PreferredUILanguage < 0 )
        {
LABEL_33:
          if ( !v16 )
            goto LABEL_35;
          goto LABEL_34;
        }
LABEL_36:
        this = 0;
        if ( !_InterlockedCompareExchange((volatile signed __int32 *)v9 + 12, 0, 1) )
        {
          if ( !GetSystemWindowsDirectoryW(v6, 0x104u) )
          {
            LastError = GetLastError();
            PreferredUILanguage = LastError;
            if ( LastError > 0 )
              PreferredUILanguage = (unsigned __int16)LastError | 0x80070000;
            if ( PreferredUILanguage >= 0 )
              PreferredUILanguage = -2147467259;
            goto LABEL_42;
          }
          v19 = (const unsigned __int16 *)*((_QWORD *)v4 + 1);
          dwBytes = 0;
          v20 = SDiagPrviCopyPWSTR(v19, (unsigned __int16 **)&dwBytes);
          PreferredUILanguage = v20;
          switch ( v20 )
          {
            case 0x8007000E:
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
              {
                McTemplateU0s_EventWriteTransfer(
                  this,
                  SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
                  "LocalContentProviderConfiguration::GetPathToLocalSystemIndex");
                goto LABEL_61;
              }
              break;
            case 0x80070057:
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                McTemplateU0sq_EventWriteTransfer(
                  this,
                  a2,
                  "LocalContentProviderConfiguration::GetPathToLocalSystemIndex",
                  2147942487LL);
              goto LABEL_61;
            case 0u:
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
                McTemplateU0s_EventWriteTransfer(
                  this,
                  SDIAGPRV_EVENT_DEBUG_SUCCESS,
                  "LocalContentProviderConfiguration::GetPathToLocalSystemIndex");
LABEL_54:
              this = 0;
              if ( !_InterlockedCompareExchange((volatile signed __int32 *)v9 + 12, 0, 1) )
              {
                v5 = (void *)dwBytes;
                v21 = CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath(
                        v9,
                        v6,
                        (const unsigned __int16 *)dwBytes);
                v7 = v31;
                PreferredUILanguage = v21;
                if ( v21 >= 0 )
                {
                  this = 0;
                  _InterlockedCompareExchange((volatile signed __int32 *)v9 + 12, 0, 1);
                }
                goto LABEL_43;
              }
              goto LABEL_61;
            default:
              if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
                McTemplateU0sq_EventWriteTransfer(
                  this,
                  a2,
                  "LocalContentProviderConfiguration::GetPathToLocalSystemIndex",
                  v20);
              break;
          }
          if ( PreferredUILanguage >= 0 )
            goto LABEL_54;
LABEL_61:
          v5 = (void *)dwBytes;
        }
LABEL_42:
        v7 = v31;
        goto LABEL_43;
      }
    }
    else
    {
      PreferredUILanguage = -2147024882;
      v16 = 0;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_33;
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY,
      "LocalContentProviderConfiguration::CreateInstance");
    goto LABEL_32;
  }
LABEL_44:
  *((_QWORD *)v9 + 5) = -1;
  if ( PreferredUILanguage == -2147024809 )
  {
    if ( v8 )
    {
      if ( v7 )
      {
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_77;
        v18 = 2147942487LL;
        goto LABEL_76;
      }
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_77;
      v22 = "DiagnosticCollection";
    }
    else
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_77;
      v22 = "DiagnosticMetadataCollection";
    }
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CLocalContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata",
      -2147024809,
      (__int64)v22);
    goto LABEL_77;
  }
  if ( PreferredUILanguage )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_77;
    v18 = (unsigned int)PreferredUILanguage;
LABEL_76:
    McTemplateU0sq_EventWriteTransfer(
      this,
      a2,
      "CLocalContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata",
      v18);
    goto LABEL_77;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_DEBUG_SUCCESS,
      "CLocalContentDiagnosticProviderImpl::FindDiagnosticsBySearchMetadata");
LABEL_77:
  if ( v3 )
    SysFreeString(v3);
  v23 = *((_QWORD *)v9 + 1);
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    *((_QWORD *)v9 + 1) = 0;
  }
  v24 = (CResourceLoader *)*((_QWORD *)v9 + 2);
  if ( v24 )
  {
    CResourceLoader::`scalar deleting destructor'(v24, (unsigned int)a2);
    *((_QWORD *)v9 + 2) = 0;
  }
  v25 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v9 + 3);
  if ( v25 )
  {
    (**v25)(v25, 1);
    *((_QWORD *)v9 + 3) = 0;
  }
  if ( v4 )
    (**(void (__fastcall ***)(LocalContentProviderConfiguration *, __int64))v4)(v4, 1);
  if ( v5 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v5);
  }
  if ( v6 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v6);
  }
  return (unsigned int)PreferredUILanguage;
}

```

## disassembly

```asm
0x1800087e0  mov     [rsp-40h+arg_10], r8
0x1800087e5  mov     [rsp-40h+arg_8], rdx
0x1800087ea  push    rbp
0x1800087eb  push    rbx
0x1800087ec  push    rsi
0x1800087ed  push    rdi
0x1800087ee  push    r12
0x1800087f0  push    r13
0x1800087f2  push    r14
0x1800087f4  push    r15
0x1800087f6  mov     rbp, rsp
0x1800087f9  sub     rsp, 38h
0x1800087fd  xor     r12d, r12d
0x180008800  xor     r14d, r14d
0x180008803  xor     r15d, r15d
0x180008806  mov     [rbp+arg_18], r12
0x18000880a  xor     r13d, r13d
0x18000880d  mov     [rbp+dwBytes], r12
0x180008811  mov     rsi, r8
0x180008814  mov     rax, rdx
0x180008817  mov     rdi, rcx
0x18000881a  mov     ebx, 80070057h
0x18000881f  test    rdx, rdx
0x180008822  jz      loc_180008A78
0x180008828  test    r8, r8
0x18000882b  jz      loc_180008A78
0x180008831  xor     ebx, ebx
0x180008833  xor     ecx, ecx; this
0x180008835  lea     eax, [rbx+1]
0x180008838  lock cmpxchg [rdi+30h], ecx
0x18000883d  test    eax, eax
0x18000883f  jnz     loc_180008A74
0x180008845  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x180008849  call    ?GetPreferredUILanguage@CLocalContentDiagnosticProviderImpl@@AEAAJPEAPEAG@Z; CLocalContentDiagnosticProviderImpl::GetPreferredUILanguage(ushort * *)
0x18000884e  mov     ebx, eax
0x180008850  test    eax, eax
0x180008852  js      loc_180008B8F
0x180008858  lea     rbx, [rdi+18h]
0x18000885c  mov     rcx, [rbx]
0x18000885f  test    rcx, rcx
0x180008862  jz      short loc_180008877
0x180008864  mov     rax, [rcx]
0x180008867  lea     edx, [r12+1]
0x18000886c  mov     rax, [rax]
0x18000886f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008874  mov     [rbx], r12
0x180008877  mov     r12, [rbp+arg_18]
0x18000887b  mov     r8, rbx; struct CDiagnosticMatcher **
0x18000887e  mov     rcx, [rbp+arg_8]; struct IDiagnosticMetadataCollection *
0x180008882  mov     rdx, r12; unsigned __int16 *
0x180008885  call    ?CreateInstance@CDiagnosticMatcher@@SAJPEAUIDiagnosticMetadataCollection@@PEAGPEAPEAV1@@Z; CDiagnosticMatcher::CreateInstance(IDiagnosticMetadataCollection *,ushort *,CDiagnosticMatcher * *)
0x18000888a  mov     ebx, eax
0x18000888c  test    eax, eax
0x18000888e  js      loc_180008A74
0x180008894  lea     rbx, [rdi+10h]
0x180008898  mov     rcx, [rbx]; this
0x18000889b  test    rcx, rcx
0x18000889e  jz      short loc_1800088A8
0x1800088a0  call    ??_GCResourceLoader@@QEAAPEAXI@Z; CResourceLoader::`scalar deleting destructor'(uint)
0x1800088a5  mov     [rbx], r13
0x1800088a8  mov     rcx, rbx; struct CResourceLoader **
0x1800088ab  call    ?CreateInstance@CResourceLoader@@SAJPEAPEAV1@@Z; CResourceLoader::CreateInstance(CResourceLoader * *)
0x1800088b0  mov     ebx, eax
0x1800088b2  test    eax, eax
0x1800088b4  js      loc_180008A74
0x1800088ba  xor     ecx, ecx
0x1800088bc  lea     eax, [rcx+1]
0x1800088bf  lock cmpxchg [rdi+30h], ecx
0x1800088c4  test    eax, eax
0x1800088c6  jnz     loc_180008A74
0x1800088cc  mov     rcx, [rdi+8]
0x1800088d0  test    rcx, rcx
0x1800088d3  jz      short loc_1800088E1
0x1800088d5  mov     rax, [rcx]
0x1800088d8  mov     rax, [rax+10h]
0x1800088dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e1  mov     [rdi+8], rsi
0x1800088e5  mov     rcx, rsi
0x1800088e8  mov     rax, [rsi]
0x1800088eb  mov     rax, [rax+8]
0x1800088ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088f4  lea     r8, [rbp+dwBytes]; unsigned __int64 *
0x1800088f8  mov     edx, 2; unsigned __int64
0x1800088fd  mov     ecx, 104h; unsigned __int64
0x180008902  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180008907  mov     ebx, eax
0x180008909  test    eax, eax
0x18000890b  js      loc_180008A74
0x180008911  call    cs:__imp_GetProcessHeap
0x180008917  mov     r8, [rbp+dwBytes]; dwBytes
0x18000891b  mov     edx, 8; dwFlags
0x180008920  mov     rcx, rax; hHeap
0x180008923  call    cs:__imp_HeapAlloc
0x180008929  mov     r13, rax
0x18000892c  test    rax, rax
0x18000892f  jnz     short loc_18000893B
0x180008931  mov     ebx, 8007000Eh
0x180008936  jmp     loc_180008A74
0x18000893b  mov     r8, [rbp+dwBytes]; Size
0x18000893f  xor     edx, edx; Val
0x180008941  mov     rcx, r13; void *
0x180008944  call    memset_0
0x180008949  mov     ecx, 10h; Size
0x18000894e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008953  mov     rsi, rax
0x180008956  test    rax, rax
0x180008959  jz      loc_1800089EE
0x18000895f  lea     rax, ??_7LocalContentProviderConfiguration@@6B@; const LocalContentProviderConfiguration::`vftable'
0x180008966  mov     [rsi+8], r14
0x18000896a  mov     rcx, rsi; this
0x18000896d  mov     [rsi], rax
0x180008970  call    ?Initialize@LocalContentProviderConfiguration@@AEAAJXZ; LocalContentProviderConfiguration::Initialize(void)
0x180008975  mov     ebx, eax
0x180008977  test    eax, eax
0x180008979  jns     short loc_180008982
0x18000897b  cmp     eax, 8007000Eh
0x180008980  jz      short loc_1800089F5
0x180008982  xor     eax, eax
0x180008984  mov     r14, rsi
0x180008987  test    ebx, ebx
0x180008989  cmovs   r14, rax
0x18000898d  cmp     ebx, 80070057h
0x180008993  jz      short loc_1800089D1
0x180008995  test    ebx, ebx
0x180008997  jz      short loc_1800089B3
0x180008999  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800089a0  jz      short loc_180008A11
0x1800089a2  mov     r9d, ebx
0x1800089a5  lea     r8, aLocalcontentpr; "LocalContentProviderConfiguration::Crea"...
0x1800089ac  call    McTemplateU0sq_EventWriteTransfer
0x1800089b1  jmp     short loc_180008A11
0x1800089b3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800089ba  jz      short loc_180008A2D
0x1800089bc  lea     r8, aLocalcontentpr; "LocalContentProviderConfiguration::Crea"...
0x1800089c3  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800089ca  call    McTemplateU0s_EventWriteTransfer
0x1800089cf  jmp     short loc_180008A31
0x1800089d1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800089d8  jz      short loc_180008A1A
0x1800089da  mov     r9d, 80070057h
0x1800089e0  lea     r8, aLocalcontentpr; "LocalContentProviderConfiguration::Crea"...
0x1800089e7  call    McTemplateU0sq_EventWriteTransfer
0x1800089ec  jmp     short loc_180008A1A
0x1800089ee  mov     ebx, 8007000Eh
0x1800089f3  xor     esi, esi
0x1800089f5  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800089fc  jz      short loc_180008A15
0x1800089fe  lea     r8, aLocalcontentpr; "LocalContentProviderConfiguration::Crea"...
0x180008a05  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180008a0c  call    McTemplateU0s_EventWriteTransfer
0x180008a11  test    ebx, ebx
0x180008a13  jns     short loc_180008A31
0x180008a15  test    rsi, rsi
0x180008a18  jz      short loc_180008A2D
0x180008a1a  mov     rax, [rsi]
0x180008a1d  mov     edx, 1
0x180008a22  mov     rcx, rsi
0x180008a25  mov     rax, [rax]
0x180008a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a2d  test    ebx, ebx
0x180008a2f  js      short loc_180008A70
0x180008a31  xor     ecx, ecx
0x180008a33  lea     eax, [rcx+1]
0x180008a36  lock cmpxchg [rdi+30h], ecx
0x180008a3b  test    eax, eax
0x180008a3d  jnz     short loc_180008A70
0x180008a3f  mov     edx, 104h; uSize
0x180008a44  mov     rcx, r13; lpBuffer
0x180008a47  call    cs:__imp_GetSystemWindowsDirectoryW
0x180008a4d  test    eax, eax
0x180008a4f  jnz     short loc_180008AA9
0x180008a51  call    cs:__imp_GetLastError
0x180008a57  mov     ebx, eax
0x180008a59  test    eax, eax
0x180008a5b  jle     short loc_180008A66
0x180008a5d  movzx   ebx, ax
0x180008a60  or      ebx, 80070000h
0x180008a66  test    ebx, ebx
0x180008a68  mov     eax, 80004005h
0x180008a6d  cmovns  ebx, eax
0x180008a70  mov     rsi, [rbp+arg_10]
0x180008a74  mov     rax, [rbp+arg_8]
0x180008a78  mov     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180008a80  cmp     ebx, 80070057h
0x180008a86  jz      loc_180008BB6
0x180008a8c  test    ebx, ebx
0x180008a8e  jz      loc_180008B98
0x180008a94  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008a9b  jz      loc_180008C16
0x180008aa1  mov     r9d, ebx
0x180008aa4  jmp     loc_180008C0A
0x180008aa9  mov     rcx, [r14+8]; unsigned __int16 *
0x180008aad  lea     rdx, [rbp+dwBytes]; unsigned __int16 **
0x180008ab1  mov     [rbp+dwBytes], r15
0x180008ab5  call    ?SDiagPrviCopyPWSTR@@YAJPEBGPEAPEAG@Z; SDiagPrviCopyPWSTR(ushort const *,ushort * *)
0x180008aba  mov     ebx, eax
0x180008abc  cmp     eax, 8007000Eh
0x180008ac1  jz      loc_180008B6D
0x180008ac7  cmp     eax, 80070057h
0x180008acc  jz      short loc_180008B49
0x180008ace  test    eax, eax
0x180008ad0  jz      short loc_180008B2B
0x180008ad2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008ad9  jz      short loc_180008AEA
0x180008adb  mov     r9d, eax
0x180008ade  lea     r8, aLocalcontentpr_0; "LocalContentProviderConfiguration::GetP"...
0x180008ae5  call    McTemplateU0sq_EventWriteTransfer
0x180008aea  test    ebx, ebx
0x180008aec  js      short loc_180008B64
0x180008aee  xor     ecx, ecx
0x180008af0  lea     eax, [rcx+1]
0x180008af3  lock cmpxchg [rdi+30h], ecx
0x180008af8  test    eax, eax
0x180008afa  jnz     short loc_180008B64
0x180008afc  mov     r15, [rbp+dwBytes]
0x180008b00  mov     rdx, r13; unsigned __int16 *
0x180008b03  mov     r8, r15; unsigned __int16 *
0x180008b06  mov     rcx, rdi; this
0x180008b09  call    ?ScanLocalIndexFromPath@CLocalContentDiagnosticProviderImpl@@AEAAJPEBG0@Z; CLocalContentDiagnosticProviderImpl::ScanLocalIndexFromPath(ushort const *,ushort const *)
0x180008b0e  mov     rsi, [rbp+arg_10]
0x180008b12  mov     ebx, eax
0x180008b14  test    eax, eax
0x180008b16  js      loc_180008A74
0x180008b1c  xor     ecx, ecx
0x180008b1e  lea     eax, [rcx+1]
0x180008b21  lock cmpxchg [rdi+30h], ecx
0x180008b26  jmp     loc_180008A74
0x180008b2b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180008b32  jz      short loc_180008AEE
0x180008b34  lea     r8, aLocalcontentpr_0; "LocalContentProviderConfiguration::GetP"...
0x180008b3b  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180008b42  call    McTemplateU0s_EventWriteTransfer
0x180008b47  jmp     short loc_180008AEE
0x180008b49  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008b50  jz      short loc_180008B64
0x180008b52  mov     r9d, 80070057h
0x180008b58  lea     r8, aLocalcontentpr_0; "LocalContentProviderConfiguration::GetP"...
0x180008b5f  call    McTemplateU0sq_EventWriteTransfer
0x180008b64  mov     r15, [rbp+dwBytes]
0x180008b68  jmp     loc_180008A70
0x180008b6d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008b74  jz      loc_180008AEA
0x180008b7a  lea     r8, aLocalcontentpr_0; "LocalContentProviderConfiguration::GetP"...
0x180008b81  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180008b88  call    McTemplateU0s_EventWriteTransfer
0x180008b8d  jmp     short loc_180008B64
0x180008b8f  mov     r12, [rbp+arg_18]
0x180008b93  jmp     loc_180008A74
0x180008b98  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180008b9f  jz      short loc_180008C16
0x180008ba1  lea     r8, aClocalcontentd_1; "CLocalContentDiagnosticProviderImpl::Fi"...
0x180008ba8  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180008baf  call    McTemplateU0s_EventWriteTransfer
0x180008bb4  jmp     short loc_180008C16
0x180008bb6  test    rax, rax
0x180008bb9  jnz     short loc_180008BCD
0x180008bbb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008bc2  jz      short loc_180008C16
0x180008bc4  lea     rax, aDiagnosticmeta_0; "DiagnosticMetadataCollection"
0x180008bcb  jmp     short loc_180008BE2
0x180008bcd  test    rsi, rsi
0x180008bd0  jnz     short loc_180008BFB
0x180008bd2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008bd9  jz      short loc_180008C16
0x180008bdb  lea     rax, aDiagnosticcoll; "DiagnosticCollection"
0x180008be2  mov     r9d, 80070057h
0x180008be8  mov     [rsp+38h+var_18], rax
0x180008bed  lea     r8, aClocalcontentd_1; "CLocalContentDiagnosticProviderImpl::Fi"...
0x180008bf4  call    McTemplateU0sqs_EventWriteTransfer
0x180008bf9  jmp     short loc_180008C16
0x180008bfb  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180008c02  jz      short loc_180008C16
0x180008c04  mov     r9d, 80070057h
0x180008c0a  lea     r8, aClocalcontentd_1; "CLocalContentDiagnosticProviderImpl::Fi"...
0x180008c11  call    McTemplateU0sq_EventWriteTransfer
0x180008c16  test    r12, r12
0x180008c19  jz      short loc_180008C24
0x180008c1b  mov     rcx, r12; bstrString
0x180008c1e  call    cs:__imp_SysFreeString
0x180008c24  mov     rcx, [rdi+8]
0x180008c28  test    rcx, rcx
0x180008c2b  jz      short loc_180008C41
0x180008c2d  mov     rax, [rcx]
0x180008c30  mov     rax, [rax+10h]
0x180008c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c39  mov     qword ptr [rdi+8], 0
0x180008c41  mov     rcx, [rdi+10h]; this
0x180008c45  test    rcx, rcx
0x180008c48  jz      short loc_180008C57
0x180008c4a  call    ??_GCResourceLoader@@QEAAPEAXI@Z; CResourceLoader::`scalar deleting destructor'(uint)
0x180008c4f  mov     qword ptr [rdi+10h], 0
0x180008c57  mov     rcx, [rdi+18h]
0x180008c5b  test    rcx, rcx
0x180008c5e  jz      short loc_180008C78
0x180008c60  mov     rax, [rcx]
0x180008c63  mov     edx, 1
0x180008c68  mov     rax, [rax]
0x180008c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c70  mov     qword ptr [rdi+18h], 0
0x180008c78  test    r14, r14
  ... truncated ...
```
