# CBWCRequest::CreateInstance(_SYSTEM_CONFIGURATION *,IDiagnosticMetadataCollection *,CBWCRequest * *)

- ea: `0x18000e7f4`
- end: `0x18000edcb`
- name: `?CreateInstance@CBWCRequest@@SAJPEAU_SYSTEM_CONFIGURATION@@PEAUIDiagnosticMetadataCollection@@PEAPEAV1@@Z`
- size: `1495`
- prototype: `__int64 __fastcall(LPCWSTR *, struct IDiagnosticMetadataCollection *, struct CBWCRequest **)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009e60`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800032ec`
- `0x18000331c`
- `0x1800033a4`
- `0x18000348c`
- `0x1800034e4`
- `0x180009b48`
- `0x18000e7f4`
- `0x18000edd4`
- `0x18000f098`
- `0x18000fac8`
- `0x1800180be`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eafd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000eafd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb80`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000eb80`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb72`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eaec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000eb72`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000e8cd`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000e92a`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000e8cd`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x18000e92a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed14`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ed14`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec5b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e9fc`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eb5f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec5b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea3e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ec8b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ea3e`
- `OLEAUT32!__imp_SysStringLen` at `0x18000ec8b`

## string_xrefs

- `0x18000eab2`: `CBWCRequest::CreateInstance`
- `0x18000eb24`: `CBWCRequest::CreateInstance`
- `0x18000edba`: `CBWCRequest::CreateInstance`
- `0x18000ed6e`: `SystemConfiguration`

## pseudocode

```c
__int64 __fastcall CBWCRequest::CreateInstance(
        LPCWSTR *a1,
        struct IDiagnosticMetadataCollection *a2,
        struct CBWCRequest **a3)
{
  _QWORD *v4; // rdi
  struct CBWCRequest **v5; // r14
  unsigned __int16 *v7; // rsi
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  int Instance; // ebx
  _QWORD *v11; // rax
  int v12; // edx
  LCID v13; // eax
  __int64 v14; // r9
  __int64 v15; // r11
  int v16; // r15d
  unsigned int v17; // eax
  unsigned __int64 v18; // r14
  __int64 (__fastcall *v19)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *); // rax
  UINT v20; // eax
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v22; // rax
  __int64 *v23; // rdx
  unsigned int v24; // edx
  HANDLE v25; // rax
  unsigned int i; // eax
  __int64 (__fastcall *v28)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *); // rax
  size_t v29; // r9
  size_t cchToCopy; // r15
  size_t *v31; // r8
  BSTR v32; // rax
  const char *v33; // rax
  __int64 v34; // [rsp+30h] [rbp-39h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+40h] [rbp-29h] BYREF
  size_t pcchDestLength; // [rsp+48h] [rbp-21h] BYREF
  struct tagVARIANT v38; // [rsp+50h] [rbp-19h] BYREF
  SIZE_T dwBytes; // [rsp+68h] [rbp-1h] BYREF
  struct tagVARIANT v40[3]; // [rsp+70h] [rbp+7h] BYREF
  int v42; // [rsp+E8h] [rbp+7Fh] BYREF

  v42 = -1;
  v4 = 0;
  bstrString = 0;
  v36 = 0;
  v34 = 0;
  memset(&v38, 0, sizeof(v38));
  dwBytes = 0;
  v5 = a3;
  pcchDestLength = 0;
  v7 = 0;
  Instance = SDiagPrviVariantInit(&v38);
  if ( Instance >= 0 )
  {
    if ( !a1 )
    {
      Instance = -2147024809;
LABEL_85:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_52;
      v33 = "SystemConfiguration";
      goto LABEL_93;
    }
    if ( !a2 )
    {
      Instance = -2147024809;
      goto LABEL_88;
    }
    if ( !v5 )
    {
      Instance = -2147024809;
      goto LABEL_91;
    }
    *v5 = 0;
    v11 = operator new(0x28u);
    v4 = v11;
    if ( !v11 )
    {
      Instance = -2147024882;
      v4 = 0;
      goto LABEL_49;
    }
    *v11 = 0;
    v11[1] = 0;
    v11[2] = 0;
    v11[3] = 0;
    v11[4] = 0;
    Instance = BWCContentProviderConfiguration::CreateInstance((struct BWCContentProviderConfiguration **)v11, v12);
    if ( Instance >= 0 )
    {
      v13 = LocaleNameToLCID(a1[3], 0);
      if ( !v13 )
      {
LABEL_11:
        Instance = -2147024809;
LABEL_12:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_52;
        v14 = 2147942487LL;
LABEL_43:
        McTemplateU0sq_EventWriteTransfer(v9, v8, "CBWCRequest::CreateInstance", v14);
        goto LABEL_52;
      }
      *((_DWORD *)v4 + 4) = v13;
      if ( *((_DWORD *)a1 + 8) > 1u )
      {
        Instance = StringCchLengthW(a1[3], 0x55u, &pcchDestLength);
        if ( Instance < 0 )
          goto LABEL_38;
        v13 = LocaleNameToLCID((LPCWSTR)(v15 + 2 * (pcchDestLength + 1)), 0);
        if ( !v13 )
          goto LABEL_11;
      }
      *((_DWORD *)v4 + 5) = v13;
      Instance = (*(__int64 (__fastcall **)(struct IDiagnosticMetadataCollection *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
                   a2,
                   &v36);
      if ( Instance >= 0 )
      {
        v38.vt = 19;
        v16 = 1;
        v17 = 0;
        v18 = 1;
        while ( 1 )
        {
          v38.lVal = v17;
          if ( v17 >= v36 )
            break;
          if ( v34 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
            v34 = 0;
          }
          v19 = *(__int64 (__fastcall **)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *))(*(_QWORD *)a2 + 32LL);
          v40[0] = v38;
          Instance = v19(a2, v40, &v34);
          if ( Instance < 0 )
            goto LABEL_37;
          Instance = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 24LL))(v34, &v42);
          if ( Instance < 0 )
            goto LABEL_37;
          if ( !v42 && v16 )
          {
            Instance = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v34 + 32LL))(v34, v4 + 3);
            if ( Instance < 0 )
            {
LABEL_37:
              v5 = a3;
              goto LABEL_38;
            }
            goto LABEL_80;
          }
          if ( v42 == 2 )
          {
            if ( bstrString )
            {
              SysFreeString(bstrString);
              bstrString = 0;
            }
            Instance = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 32LL))(v34, &bstrString);
            if ( Instance < 0 )
              goto LABEL_37;
            if ( v18 > 1 )
            {
              if ( v18 + 1 < v18 )
                goto LABEL_44;
              ++v18;
            }
            v20 = SysStringLen(bstrString);
            v9 = v18 + v20;
            if ( v9 < v18 )
            {
LABEL_44:
              Instance = -2147024362;
              goto LABEL_41;
            }
            v16 = 0;
            v18 += v20;
            Instance = 0;
          }
          v17 = v38.lVal + 1;
        }
        if ( !v16 && v18 > 1 )
        {
          Instance = ULongLongMult(v18, 2u, &dwBytes);
          ProcessHeap = GetProcessHeap();
          v22 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, dwBytes);
          v7 = v22;
          if ( !v22 )
            goto LABEL_48;
          memset_0(v22, 0, dwBytes);
          v38.vt = 19;
          for ( i = 0; ; i = v38.lVal + 1 )
          {
            v38.lVal = i;
            if ( i >= v36 )
              break;
            if ( v34 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
              v34 = 0;
            }
            v28 = *(__int64 (__fastcall **)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *))(*(_QWORD *)a2 + 32LL);
            v40[0] = v38;
            Instance = v28(a2, v40, &v34);
            if ( Instance < 0 )
              goto LABEL_37;
            Instance = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 24LL))(v34, &v42);
            if ( Instance < 0 )
              goto LABEL_37;
            if ( v42 == 2 )
            {
              if ( bstrString )
              {
                SysFreeString(bstrString);
                bstrString = 0;
              }
              Instance = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v34 + 32LL))(v34, &bstrString);
              if ( Instance < 0 )
                goto LABEL_37;
              cchToCopy = SysStringLen(bstrString);
              if ( *v7 )
              {
                Instance = StringCchCatW(v7, v18, L" ");
                if ( Instance < 0 )
                  goto LABEL_37;
              }
              pcchDestLength = 0;
              Instance = StringValidateDestAndLengthW(v7, v18, &pcchDestLength, v29);
              if ( Instance >= 0 )
              {
                if ( (unsigned int)cchToCopy > 0x7FFFFFFE )
                  goto LABEL_11;
                Instance = StringCopyWorkerW(&v7[pcchDestLength], v18 - pcchDestLength, v31, bstrString, cchToCopy);
              }
              if ( Instance < 0 )
                goto LABEL_37;
            }
          }
          v32 = SysAllocString(v7);
          v4[4] = v32;
          if ( !v32 )
          {
LABEL_48:
            Instance = -2147024882;
            goto LABEL_49;
          }
        }
LABEL_80:
        v5 = a3;
        v4[1] = a1;
        *a3 = (struct CBWCRequest *)v4;
      }
    }
  }
LABEL_38:
  if ( Instance == -2147024882 )
  {
LABEL_49:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_52;
    v23 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_51;
  }
  if ( Instance != -2147024809 )
  {
    if ( Instance )
    {
LABEL_41:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_52;
      v14 = (unsigned int)Instance;
      goto LABEL_43;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_52;
    v23 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_51:
    McTemplateU0s_EventWriteTransfer(v9, v23, "CBWCRequest::CreateInstance");
    goto LABEL_52;
  }
  if ( !a1 )
    goto LABEL_85;
  if ( !a2 )
  {
LABEL_88:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_52;
    v33 = "DiagnosticMetadataCollection";
    goto LABEL_93;
  }
  if ( v5 )
    goto LABEL_12;
LABEL_91:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
    goto LABEL_52;
  v33 = "BWCRequest";
LABEL_93:
  McTemplateU0sqs_EventWriteTransfer(v9, v8, (unsigned int)"CBWCRequest::CreateInstance", -2147024809, (__int64)v33);
LABEL_52:
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  SDiagPrviVariantClear(&v38);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v7 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v7);
  }
  if ( Instance < 0 && v4 )
    CBWCRequest::`scalar deleting destructor'((CBWCRequest *)v4, v24);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000e7f4  mov     [rsp-8+arg_0], rbx
0x18000e7f9  mov     [rsp-8+arg_10], r8
0x18000e7fe  push    rbp
0x18000e7ff  push    rsi
0x18000e800  push    rdi
0x18000e801  push    r12
0x18000e803  push    r13
0x18000e805  push    r14
0x18000e807  push    r15
0x18000e809  lea     rbp, [rsp-27h]
0x18000e80e  sub     rsp, 90h
0x18000e815  xor     eax, eax
0x18000e817  mov     [rbp+57h+arg_18], 0FFFFFFFFh
0x18000e81e  mov     r13, rcx
0x18000e821  mov     qword ptr [rbp+57h+var_70+10h], rax
0x18000e825  xor     edi, edi
0x18000e827  mov     [rbp+57h+bstrString], rax
0x18000e82b  xorps   xmm0, xmm0
0x18000e82e  mov     [rbp+57h+var_80], edi
0x18000e831  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x18000e835  mov     [rbp+57h+var_90], rdi
0x18000e839  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x18000e83d  mov     [rbp+57h+dwBytes], rax
0x18000e841  mov     r14, r8
0x18000e844  mov     [rbp+57h+pcchDestLength], rax
0x18000e848  mov     r12, rdx
0x18000e84b  xor     esi, esi
0x18000e84d  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x18000e852  mov     ebx, eax
0x18000e854  test    eax, eax
0x18000e856  js      loc_18000EA82
0x18000e85c  test    r13, r13
0x18000e85f  jnz     short loc_18000E86B
0x18000e861  mov     ebx, 80070057h
0x18000e866  jmp     loc_18000ED61
0x18000e86b  test    r12, r12
0x18000e86e  jnz     short loc_18000E87A
0x18000e870  mov     ebx, 80070057h
0x18000e875  jmp     loc_18000ED7C
0x18000e87a  test    r14, r14
0x18000e87d  jnz     short loc_18000E889
0x18000e87f  mov     ebx, 80070057h
0x18000e884  jmp     loc_18000ED9B
0x18000e889  mov     ecx, 28h ; '('; Size
0x18000e88e  mov     [r14], rsi
0x18000e891  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e896  mov     rdi, rax
0x18000e899  test    rax, rax
0x18000e89c  jz      loc_18000ED37
0x18000e8a2  mov     rcx, rax; struct BWCContentProviderConfiguration **
0x18000e8a5  mov     [rax], rsi
0x18000e8a8  mov     [rax+8], rsi
0x18000e8ac  mov     [rax+10h], rsi
0x18000e8b0  mov     [rax+18h], rsi
0x18000e8b4  mov     [rax+20h], rsi
0x18000e8b8  call    ?CreateInstance@BWCContentProviderConfiguration@@SAJPEAPEAV1@@Z; BWCContentProviderConfiguration::CreateInstance(BWCContentProviderConfiguration * *)
0x18000e8bd  mov     ebx, eax
0x18000e8bf  test    eax, eax
0x18000e8c1  js      loc_18000EA82
0x18000e8c7  mov     rcx, [r13+18h]; lpName
0x18000e8cb  xor     edx, edx; dwFlags
0x18000e8cd  call    cs:__imp_LocaleNameToLCID
0x18000e8d3  test    eax, eax
0x18000e8d5  jnz     short loc_18000E8F4
0x18000e8d7  mov     ebx, 80070057h
0x18000e8dc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000e8e3  jz      loc_18000EB30
0x18000e8e9  mov     r9d, 80070057h
0x18000e8ef  jmp     loc_18000EAB2
0x18000e8f4  mov     [rdi+10h], eax
0x18000e8f7  cmp     dword ptr [r13+20h], 1
0x18000e8fc  jbe     short loc_18000E934
0x18000e8fe  mov     r11, [r13+18h]
0x18000e902  lea     r8, [rbp+57h+pcchDestLength]; unsigned __int64 *
0x18000e906  mov     rcx, r11; unsigned __int16 *
0x18000e909  mov     edx, 55h ; 'U'; unsigned __int64
0x18000e90e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000e913  mov     ebx, eax
0x18000e915  test    eax, eax
0x18000e917  js      loc_18000EA82
0x18000e91d  mov     rax, [rbp+57h+pcchDestLength]
0x18000e921  xor     edx, edx; dwFlags
0x18000e923  inc     rax
0x18000e926  lea     rcx, [r11+rax*2]; lpName
0x18000e92a  call    cs:__imp_LocaleNameToLCID
0x18000e930  test    eax, eax
0x18000e932  jz      short loc_18000E8D7
0x18000e934  mov     [rdi+14h], eax
0x18000e937  lea     rdx, [rbp+57h+var_80]
0x18000e93b  mov     rax, [r12]
0x18000e93f  mov     rcx, r12
0x18000e942  mov     rax, [rax+18h]
0x18000e946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e94b  mov     ebx, eax
0x18000e94d  test    eax, eax
0x18000e94f  js      loc_18000EA82
0x18000e955  mov     eax, 13h
0x18000e95a  mov     word ptr [rbp+57h+var_70], ax
0x18000e95e  lea     r15d, [rax-12h]
0x18000e962  xor     eax, eax
0x18000e964  mov     r14d, r15d
0x18000e967  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000e96a  cmp     eax, [rbp+57h+var_80]
0x18000e96d  jnb     loc_18000EAC7
0x18000e973  mov     rcx, [rbp+57h+var_90]
0x18000e977  test    rcx, rcx
0x18000e97a  jz      short loc_18000E990
0x18000e97c  mov     rax, [rcx]
0x18000e97f  mov     rax, [rax+10h]
0x18000e983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e988  mov     [rbp+57h+var_90], 0
0x18000e990  mov     rax, [r12]
0x18000e994  lea     r8, [rbp+57h+var_90]
0x18000e998  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18000e99c  lea     rdx, [rbp+57h+var_50]
0x18000e9a0  mov     rcx, r12
0x18000e9a3  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18000e9a8  mov     rax, [rax+20h]
0x18000e9ac  movaps  [rbp+57h+var_50], xmm0
0x18000e9b0  movsd   [rbp+57h+var_40], xmm1
0x18000e9b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9ba  mov     ebx, eax
0x18000e9bc  test    eax, eax
0x18000e9be  js      loc_18000EA7E
0x18000e9c4  mov     rcx, [rbp+57h+var_90]
0x18000e9c8  lea     rdx, [rbp+57h+arg_18]
0x18000e9cc  mov     rax, [rcx]
0x18000e9cf  mov     rax, [rax+18h]
0x18000e9d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9d8  mov     ebx, eax
0x18000e9da  test    eax, eax
0x18000e9dc  js      loc_18000EA7E
0x18000e9e2  mov     eax, [rbp+57h+arg_18]
0x18000e9e5  test    eax, eax
0x18000e9e7  jnz     short loc_18000E9EE
0x18000e9e9  test    r15d, r15d
0x18000e9ec  jnz     short loc_18000EA60
0x18000e9ee  cmp     eax, 2
0x18000e9f1  jnz     short loc_18000EA56
0x18000e9f3  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000e9f7  test    rcx, rcx
0x18000e9fa  jz      short loc_18000EA0A
0x18000e9fc  call    cs:__imp_SysFreeString
0x18000ea02  mov     [rbp+57h+bstrString], 0
0x18000ea0a  mov     rcx, [rbp+57h+var_90]
0x18000ea0e  lea     rdx, [rbp+57h+bstrString]
0x18000ea12  mov     rax, [rcx]
0x18000ea15  mov     rax, [rax+20h]
0x18000ea19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea1e  mov     ebx, eax
0x18000ea20  test    eax, eax
0x18000ea22  js      short loc_18000EA7E
0x18000ea24  cmp     r14, 1
0x18000ea28  jbe     short loc_18000EA3A
0x18000ea2a  lea     rax, [r14+1]
0x18000ea2e  cmp     rax, r14
0x18000ea31  jb      loc_18000EAC0
0x18000ea37  mov     r14, rax
0x18000ea3a  mov     rcx, [rbp+57h+bstrString]; pbstr
0x18000ea3e  call    cs:__imp_SysStringLen
0x18000ea44  mov     ecx, eax
0x18000ea46  add     rcx, r14
0x18000ea49  cmp     rcx, r14
0x18000ea4c  jb      short loc_18000EAC0
0x18000ea4e  xor     r15d, r15d
0x18000ea51  mov     r14, rcx
0x18000ea54  xor     ebx, ebx
0x18000ea56  mov     eax, dword ptr [rbp+57h+var_70+8]
0x18000ea59  inc     eax
0x18000ea5b  jmp     loc_18000E967
0x18000ea60  mov     rcx, [rbp+57h+var_90]
0x18000ea64  lea     rdx, [rdi+18h]
0x18000ea68  mov     rax, [rcx]
0x18000ea6b  mov     rax, [rax+20h]
0x18000ea6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea74  mov     ebx, eax
0x18000ea76  test    eax, eax
0x18000ea78  jns     loc_18000ED27
0x18000ea7e  mov     r14, [rbp+57h+arg_10]
0x18000ea82  cmp     ebx, 8007000Eh
0x18000ea88  jz      loc_18000EB14
0x18000ea8e  cmp     ebx, 80070057h
0x18000ea94  jz      loc_18000ED5C
0x18000ea9a  test    ebx, ebx
0x18000ea9c  jz      loc_18000ED43
0x18000eaa2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000eaa9  jz      loc_18000EB30
0x18000eaaf  mov     r9d, ebx
0x18000eab2  lea     r8, aCbwcrequestCre; "CBWCRequest::CreateInstance"
0x18000eab9  call    McTemplateU0sq_EventWriteTransfer
0x18000eabe  jmp     short loc_18000EB30
0x18000eac0  mov     ebx, 80070216h
0x18000eac5  jmp     short loc_18000EAA2
0x18000eac7  test    r15d, r15d
0x18000eaca  jnz     loc_18000ED27
0x18000ead0  cmp     r14, 1
0x18000ead4  jbe     loc_18000ED27
0x18000eada  lea     r8, [rbp+57h+dwBytes]; unsigned __int64 *
0x18000eade  mov     rcx, r14; unsigned __int64
0x18000eae1  lea     edx, [r15+2]; unsigned __int64
0x18000eae5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000eaea  mov     ebx, eax
0x18000eaec  call    cs:__imp_GetProcessHeap
0x18000eaf2  mov     r8, [rbp+57h+dwBytes]; dwBytes
0x18000eaf6  lea     edx, [r15+8]; dwFlags
0x18000eafa  mov     rcx, rax; hHeap
0x18000eafd  call    cs:__imp_HeapAlloc
0x18000eb03  mov     rsi, rax
0x18000eb06  test    rax, rax
0x18000eb09  jnz     loc_18000EBB4
0x18000eb0f  mov     ebx, 8007000Eh
0x18000eb14  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000eb1b  jz      short loc_18000EB30
0x18000eb1d  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000eb24  lea     r8, aCbwcrequestCre; "CBWCRequest::CreateInstance"
0x18000eb2b  call    McTemplateU0s_EventWriteTransfer
0x18000eb30  mov     rcx, [rbp+57h+var_90]
0x18000eb34  test    rcx, rcx
0x18000eb37  jz      short loc_18000EB4D
0x18000eb39  mov     rax, [rcx]
0x18000eb3c  mov     rax, [rax+10h]
0x18000eb40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb45  mov     [rbp+57h+var_90], 0
0x18000eb4d  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x18000eb51  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18000eb56  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000eb5a  test    rcx, rcx
0x18000eb5d  jz      short loc_18000EB6D
0x18000eb5f  call    cs:__imp_SysFreeString
0x18000eb65  mov     [rbp+57h+bstrString], 0
0x18000eb6d  test    rsi, rsi
0x18000eb70  jz      short loc_18000EB86
0x18000eb72  call    cs:__imp_GetProcessHeap
0x18000eb78  mov     r8, rsi; lpMem
0x18000eb7b  xor     edx, edx; dwFlags
0x18000eb7d  mov     rcx, rax; hHeap
0x18000eb80  call    cs:__imp_HeapFree
0x18000eb86  test    ebx, ebx
0x18000eb88  jns     short loc_18000EB97
0x18000eb8a  test    rdi, rdi
0x18000eb8d  jz      short loc_18000EB97
0x18000eb8f  mov     rcx, rdi; this
0x18000eb92  call    ??_GCBWCRequest@@QEAAPEAXI@Z; CBWCRequest::`scalar deleting destructor'(uint)
0x18000eb97  mov     eax, ebx
0x18000eb99  mov     rbx, [rsp+0C0h+arg_0]
0x18000eba1  add     rsp, 90h
0x18000eba8  pop     r15
0x18000ebaa  pop     r14
0x18000ebac  pop     r13
0x18000ebae  pop     r12
0x18000ebb0  pop     rdi
0x18000ebb1  pop     rsi
0x18000ebb2  pop     rbp
0x18000ebb3  retn
0x18000ebb4  mov     r8, [rbp+57h+dwBytes]; Size
0x18000ebb8  xor     edx, edx; Val
0x18000ebba  mov     rcx, rsi; void *
0x18000ebbd  call    memset_0
0x18000ebc2  mov     eax, 13h
0x18000ebc7  mov     word ptr [rbp+57h+var_70], ax
0x18000ebcb  xor     eax, eax
0x18000ebcd  mov     dword ptr [rbp+57h+var_70+8], eax
0x18000ebd0  cmp     eax, [rbp+57h+var_80]
0x18000ebd3  jnb     loc_18000ED11
0x18000ebd9  mov     rcx, [rbp+57h+var_90]
0x18000ebdd  test    rcx, rcx
0x18000ebe0  jz      short loc_18000EBF6
0x18000ebe2  mov     rax, [rcx]
0x18000ebe5  mov     rax, [rax+10h]
0x18000ebe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebee  mov     [rbp+57h+var_90], 0
0x18000ebf6  mov     rax, [r12]
0x18000ebfa  lea     r8, [rbp+57h+var_90]
0x18000ebfe  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18000ec02  lea     rdx, [rbp+57h+var_50]
0x18000ec06  mov     rcx, r12
0x18000ec09  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x18000ec0e  mov     rax, [rax+20h]
0x18000ec12  movaps  [rbp+57h+var_50], xmm0
0x18000ec16  movsd   [rbp+57h+var_40], xmm1
0x18000ec1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec20  mov     ebx, eax
0x18000ec22  test    eax, eax
0x18000ec24  js      loc_18000EA7E
0x18000ec2a  mov     rcx, [rbp+57h+var_90]
0x18000ec2e  lea     rdx, [rbp+57h+arg_18]
0x18000ec32  mov     rax, [rcx]
0x18000ec35  mov     rax, [rax+18h]
0x18000ec39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec3e  mov     ebx, eax
0x18000ec40  test    eax, eax
0x18000ec42  js      loc_18000EA7E
0x18000ec48  cmp     [rbp+57h+arg_18], 2
0x18000ec4c  jnz     loc_18000ED07
0x18000ec52  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18000ec56  test    rcx, rcx
0x18000ec59  jz      short loc_18000EC69
0x18000ec5b  call    cs:__imp_SysFreeString
0x18000ec61  mov     [rbp+57h+bstrString], 0
0x18000ec69  mov     rcx, [rbp+57h+var_90]
  ... truncated ...
```
