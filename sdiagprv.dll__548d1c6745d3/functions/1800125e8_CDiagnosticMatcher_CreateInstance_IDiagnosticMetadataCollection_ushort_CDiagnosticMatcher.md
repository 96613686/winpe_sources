# CDiagnosticMatcher::CreateInstance(IDiagnosticMetadataCollection *,ushort *,CDiagnosticMatcher * *)

- ea: `0x1800125e8`
- end: `0x180012aa5`
- name: `?CreateInstance@CDiagnosticMatcher@@SAJPEAUIDiagnosticMetadataCollection@@PEAGPEAPEAV1@@Z`
- size: `1213`
- prototype: `__int64 __fastcall(struct IDiagnosticMetadataCollection *, unsigned __int16 *, struct CDiagnosticMatcher **)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800087e0`

## callees

- `0x180001074`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800032ec`
- `0x18000331c`
- `0x180009604`
- `0x1800125e8`
- `0x180019010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18001284f`
- `msvcrt!_wcsnicmp` at `0x18001284f`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800126bd`
- `api-ms-win-core-localization-l1-2-0!LocaleNameToLCID` at `0x1800126bd`
- `OLEAUT32!__imp_SysStringLen` at `0x180012801`
- `OLEAUT32!__imp_SysStringLen` at `0x180012894`
- `OLEAUT32!__imp_SysStringLen` at `0x180012801`
- `OLEAUT32!__imp_SysStringLen` at `0x180012894`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180012734`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180012734`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800129a1`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800129a1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001274d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18001274d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800128f4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001298b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800128f4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001298b`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180012919`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180012919`

## string_xrefs

- `0x18001294f`: `CDiagnosticMatcher::CreateInstance`
- `0x180012a0c`: `CDiagnosticMatcher::CreateInstance`
- `0x180012a94`: `CDiagnosticMatcher::CreateInstance`

## pseudocode

```c
__int64 __fastcall CDiagnosticMatcher::CreateInstance(
        struct IDiagnosticMetadataCollection *a1,
        unsigned __int16 *a2,
        struct CDiagnosticMatcher **a3)
{
  struct IDiagnosticMetadataCollection *v3; // r15
  _DWORD *v4; // rdi
  SAFEARRAY *v7; // rsi
  const wchar_t *v8; // rdx
  OLECHAR *v9; // rcx
  HRESULT v10; // ebx
  _DWORD *v11; // rax
  LCID v12; // eax
  __int64 v13; // r9
  SAFEARRAY *v14; // rax
  __int64 v15; // r14
  unsigned int i; // eax
  __int64 (__fastcall *v17)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *); // rax
  OLECHAR *v18; // rcx
  __int64 *v19; // rdx
  const char *v21; // rax
  __int64 v22; // [rsp+30h] [rbp-39h] BYREF
  void *ppvData; // [rsp+38h] [rbp-31h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-29h] BYREF
  int v25; // [rsp+48h] [rbp-21h] BYREF
  struct tagVARIANT v26; // [rsp+50h] [rbp-19h] BYREF
  _DWORD *v27; // [rsp+68h] [rbp-1h]
  struct tagVARIANT v28; // [rsp+70h] [rbp+7h] BYREF
  ULONG v30; // [rsp+E8h] [rbp+7Fh] BYREF

  v25 = -1;
  v3 = a1;
  v4 = 0;
  rgsabound = 0;
  v30 = 0;
  v22 = 0;
  memset(&v26, 0, sizeof(v26));
  ppvData = 0;
  v7 = 0;
  v10 = SDiagPrviVariantInit(&v26);
  if ( v10 < 0 )
    goto LABEL_65;
  if ( !v3 )
  {
    v10 = -2147024809;
LABEL_74:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_54;
    v21 = "DiagnosticMetadataCollection";
LABEL_82:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)v9,
      (_DWORD)v8,
      (unsigned int)"CDiagnosticMatcher::CreateInstance",
      -2147024809,
      (__int64)v21);
    goto LABEL_54;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
    goto LABEL_77;
  }
  if ( !a3 )
  {
    v10 = -2147024809;
    goto LABEL_80;
  }
  *a3 = 0;
  v11 = operator new(0x28u);
  v27 = v11;
  v4 = v11;
  if ( !v11 )
  {
    v4 = 0;
LABEL_50:
    v10 = -2147024882;
LABEL_51:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_54;
    v19 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_53;
  }
  v11[2] = 0;
  *(_QWORD *)v11 = &CDiagnosticMatcher::`vftable';
  *((_QWORD *)v11 + 2) = 0;
  *((_QWORD *)v11 + 3) = 0;
  v11[8] = 0;
  v12 = LocaleNameToLCID(a2, 0);
  if ( !v12 )
  {
    v10 = -2147024809;
    goto LABEL_11;
  }
  v4[2] = v12;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
    McTemplateU0qz_EventWriteTransfer(v9, SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER, 0, a2);
  v10 = (*(__int64 (__fastcall **)(struct IDiagnosticMetadataCollection *, ULONG *))(*(_QWORD *)v3 + 24LL))(v3, &v30);
  if ( v10 < 0 )
    goto LABEL_65;
  rgsabound.lLbound = 0;
  rgsabound.cElements = v30;
  v14 = SafeArrayCreate(8u, 1u, &rgsabound);
  v7 = v14;
  if ( !v14 )
    goto LABEL_50;
  v10 = SafeArrayAccessData(v14, &ppvData);
  if ( v10 < 0 )
    goto LABEL_65;
  v15 = 0;
  v26.vt = 19;
  for ( i = 0; ; i = v26.lVal + 1 )
  {
    v26.lVal = i;
    if ( i >= v30 )
      break;
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      v22 = 0;
    }
    v17 = *(__int64 (__fastcall **)(struct IDiagnosticMetadataCollection *, struct tagVARIANT *, __int64 *))(*(_QWORD *)v3 + 32LL);
    v28 = v26;
    v10 = v17(v3, &v28, &v22);
    if ( v10 < 0 )
      goto LABEL_65;
    v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 24LL))(v22, &v25);
    if ( v10 < 0 )
      goto LABEL_65;
    if ( !v25 )
    {
      v9 = (OLECHAR *)*((_QWORD *)v4 + 2);
      if ( (!v9 || !SysStringLen(v9)) && !(_DWORD)v15 )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v22 + 32LL))(v22, v4 + 4);
        if ( v10 < 0 )
        {
LABEL_64:
          v3 = a1;
          goto LABEL_65;
        }
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
          McTemplateU0qz_EventWriteTransfer(
            v9,
            SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER,
            1,
            *((_QWORD *)v4 + 2));
      }
      goto LABEL_41;
    }
    if ( v25 == 2 )
    {
      v18 = (OLECHAR *)*((_QWORD *)v4 + 2);
      if ( !v18 || !SysStringLen(v18) )
      {
        v10 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v22 + 32LL))(v22, (char *)ppvData + 8 * v15);
        if ( v10 < 0 )
          goto LABEL_64;
        v8 = (const wchar_t *)*((_QWORD *)ppvData + v15);
        if ( v8 )
        {
          if ( !_wcsnicmp(L"__ALL__", v8, 7u) )
            v4[8] = 1;
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x20) != 0 )
            McTemplateU0qz_EventWriteTransfer(
              v9,
              SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER,
              3,
              *((_QWORD *)ppvData + v15));
          v15 = (unsigned int)(v15 + 1);
        }
LABEL_41:
        v3 = a1;
        continue;
      }
    }
  }
  if ( ppvData )
    SafeArrayUnaccessData(v7);
  ppvData = 0;
  if ( (_DWORD)v15 )
  {
    rgsabound.lLbound = 0;
    rgsabound.cElements = v15;
    v10 = SafeArrayRedim(v7, &rgsabound);
    if ( v10 < 0 )
      goto LABEL_65;
    *((_QWORD *)v4 + 3) = v7;
    v7 = 0;
  }
  *a3 = (struct CDiagnosticMatcher *)v4;
LABEL_65:
  switch ( v10 )
  {
    case -2147024882:
      goto LABEL_51;
    case -2147024809:
      if ( !v3 )
        goto LABEL_74;
      if ( !a2 )
      {
LABEL_77:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_54;
        v21 = "Culture";
        goto LABEL_82;
      }
      if ( !a3 )
      {
LABEL_80:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_54;
        v21 = "DiagnosticMatcher";
        goto LABEL_82;
      }
LABEL_11:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v13 = 2147942487LL;
        goto LABEL_70;
      }
      goto LABEL_54;
    case 0:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
        goto LABEL_54;
      v19 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_53:
      McTemplateU0s_EventWriteTransfer(v9, v19, "CDiagnosticMatcher::CreateInstance");
      goto LABEL_54;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v13 = (unsigned int)v10;
LABEL_70:
    McTemplateU0sq_EventWriteTransfer(v9, v8, "CDiagnosticMatcher::CreateInstance", v13);
  }
LABEL_54:
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  SDiagPrviVariantClear(&v26);
  if ( ppvData )
  {
    SafeArrayUnaccessData(v7);
    ppvData = 0;
  }
  if ( v7 )
    SafeArrayDestroy(v7);
  if ( v10 < 0 && v4 )
    (**(void (__fastcall ***)(_DWORD *, __int64))v4)(v4, 1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800125e8  mov     [rsp-8+arg_8], rbx
0x1800125ed  mov     [rsp-8+arg_0], rcx
0x1800125f2  push    rbp
0x1800125f3  push    rsi
0x1800125f4  push    rdi
0x1800125f5  push    r12
0x1800125f7  push    r13
0x1800125f9  push    r14
0x1800125fb  push    r15
0x1800125fd  lea     rbp, [rsp-27h]
0x180012602  sub     rsp, 90h
0x180012609  xor     eax, eax
0x18001260b  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x180012612  mov     r15, rcx
0x180012615  mov     qword ptr [rbp+57h+var_70+10h], rax
0x180012619  xor     edi, edi
0x18001261b  mov     qword ptr [rbp+57h+rgsabound.cElements], rax
0x18001261f  xorps   xmm0, xmm0
0x180012622  mov     [rbp+57h+arg_18], edi
0x180012625  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x180012629  mov     [rbp+57h+var_90], rdi
0x18001262d  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180012631  mov     [rbp+57h+ppvData], rax
0x180012635  mov     r12, r8
0x180012638  mov     r13, rdx
0x18001263b  xor     esi, esi
0x18001263d  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x180012642  mov     ebx, eax
0x180012644  test    eax, eax
0x180012646  js      loc_1800129E4
0x18001264c  test    r15, r15
0x18001264f  jnz     short loc_18001265B
0x180012651  mov     ebx, 80070057h
0x180012656  jmp     loc_180012A3B
0x18001265b  test    r13, r13
0x18001265e  jnz     short loc_18001266A
0x180012660  mov     ebx, 80070057h
0x180012665  jmp     loc_180012A56
0x18001266a  test    r12, r12
0x18001266d  jnz     short loc_180012679
0x18001266f  mov     ebx, 80070057h
0x180012674  jmp     loc_180012A75
0x180012679  mov     ecx, 28h ; '('; Size
0x18001267e  mov     [r12], rsi
0x180012682  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012687  mov     [rbp+57h+var_58], rax
0x18001268b  mov     rdi, rax
0x18001268e  test    rax, rax
0x180012691  jz      loc_180012938
0x180012697  mov     [rdi+8], esi
0x18001269a  lea     rax, ??_7CDiagnosticMatcher@@6B@; const CDiagnosticMatcher::`vftable'
0x1800126a1  mov     [rdi], rax
0x1800126a4  mov     [rdi+10h], rsi
0x1800126a8  mov     [rdi+18h], rsi
0x1800126ac  mov     [rdi+20h], esi
0x1800126af  test    rdi, rdi
0x1800126b2  jz      loc_18001293A
0x1800126b8  xor     edx, edx; dwFlags
0x1800126ba  mov     rcx, r13; lpName
0x1800126bd  call    cs:__imp_LocaleNameToLCID
0x1800126c3  test    eax, eax
0x1800126c5  jnz     short loc_1800126E4
0x1800126c7  mov     ebx, 80070057h
0x1800126cc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800126d3  jz      loc_18001295B
0x1800126d9  mov     r9d, 80070057h
0x1800126df  jmp     loc_180012A0C
0x1800126e4  mov     [rdi+8], eax
0x1800126e7  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x1800126ee  jz      short loc_180012702
0x1800126f0  mov     r9, r13
0x1800126f3  lea     rdx, SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER
0x1800126fa  xor     r8d, r8d
0x1800126fd  call    McTemplateU0qz_EventWriteTransfer
0x180012702  mov     rax, [r15]
0x180012705  lea     rdx, [rbp+57h+arg_18]
0x180012709  mov     rcx, r15
0x18001270c  mov     rax, [rax+18h]
0x180012710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012715  mov     ebx, eax
0x180012717  test    eax, eax
0x180012719  js      loc_1800129E4
0x18001271f  mov     eax, [rbp+57h+arg_18]
0x180012722  lea     r8, [rbp+57h+rgsabound]; rgsabound
0x180012726  mov     ecx, 8; vt
0x18001272b  mov     [rbp+57h+rgsabound.lLbound], esi
0x18001272e  mov     [rbp+57h+rgsabound.cElements], eax
0x180012731  lea     edx, [rcx-7]; cDims
0x180012734  call    cs:__imp_SafeArrayCreate
0x18001273a  mov     rsi, rax
0x18001273d  test    rax, rax
0x180012740  jz      loc_18001293A
0x180012746  lea     rdx, [rbp+57h+ppvData]; ppvData
0x18001274a  mov     rcx, rax; psa
0x18001274d  call    cs:__imp_SafeArrayAccessData
0x180012753  mov     ebx, eax
0x180012755  test    eax, eax
0x180012757  js      loc_1800129E4
0x18001275d  xor     r14d, r14d
0x180012760  lea     eax, [r14+13h]
0x180012764  mov     word ptr [rbp+57h+var_70], ax
0x180012768  xor     eax, eax
0x18001276a  mov     dword ptr [rbp+57h+var_70+8], eax
0x18001276d  cmp     eax, [rbp+57h+arg_18]
0x180012770  jnb     loc_1800128EA
0x180012776  mov     rcx, [rbp+57h+var_90]
0x18001277a  test    rcx, rcx
0x18001277d  jz      short loc_180012793
0x18001277f  mov     rax, [rcx]
0x180012782  mov     rax, [rax+10h]
0x180012786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001278b  mov     [rbp+57h+var_90], 0
0x180012793  mov     rax, [r15]
0x180012796  lea     r8, [rbp+57h+var_90]
0x18001279a  movups  xmm0, xmmword ptr [rbp+57h+var_70]
0x18001279e  lea     rdx, [rbp+57h+var_50]
0x1800127a2  mov     rcx, r15
0x1800127a5  movsd   xmm1, qword ptr [rbp+57h+var_70+10h]
0x1800127aa  mov     rax, [rax+20h]
0x1800127ae  movaps  [rbp+57h+var_50], xmm0
0x1800127b2  movsd   [rbp+57h+var_40], xmm1
0x1800127b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127bc  mov     ebx, eax
0x1800127be  test    eax, eax
0x1800127c0  js      loc_1800129E4
0x1800127c6  mov     rcx, [rbp+57h+var_90]
0x1800127ca  lea     rdx, [rbp+57h+var_78]
0x1800127ce  mov     rax, [rcx]
0x1800127d1  mov     rax, [rax+18h]
0x1800127d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127da  mov     ebx, eax
0x1800127dc  test    eax, eax
0x1800127de  js      loc_1800129E4
0x1800127e4  mov     eax, [rbp+57h+var_78]
0x1800127e7  test    eax, eax
0x1800127e9  jz      loc_180012888
0x1800127ef  cmp     eax, 2
0x1800127f2  jnz     loc_1800128E0
0x1800127f8  mov     rcx, [rdi+10h]; pbstr
0x1800127fc  test    rcx, rcx
0x1800127ff  jz      short loc_18001280F
0x180012801  call    cs:__imp_SysStringLen
0x180012807  test    eax, eax
0x180012809  jnz     loc_1800128E0
0x18001280f  mov     rax, [rbp+57h+ppvData]
0x180012813  mov     rcx, [rbp+57h+var_90]
0x180012817  lea     rdx, [rax+r14*8]
0x18001281b  mov     r8, [rcx]
0x18001281e  mov     rax, [r8+20h]
0x180012822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012827  mov     ebx, eax
0x180012829  test    eax, eax
0x18001282b  js      loc_1800129E0
0x180012831  mov     rax, [rbp+57h+ppvData]
0x180012835  mov     rdx, [rax+r14*8]; String2
0x180012839  test    rdx, rdx
0x18001283c  jz      loc_1800128DC
0x180012842  mov     r8d, 7; MaxCount
0x180012848  lea     rcx, aAll; "__ALL__"
0x18001284f  call    cs:__imp__wcsnicmp
0x180012855  test    eax, eax
0x180012857  jnz     short loc_180012860
0x180012859  mov     dword ptr [rdi+20h], 1
0x180012860  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x180012867  jz      short loc_180012883
0x180012869  mov     r9, [rbp+57h+ppvData]
0x18001286d  lea     rdx, SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER
0x180012874  mov     r8d, 3
0x18001287a  mov     r9, [r9+r14*8]
0x18001287e  call    McTemplateU0qz_EventWriteTransfer
0x180012883  inc     r14d
0x180012886  jmp     short loc_1800128DC
0x180012888  lea     r15, [rdi+10h]
0x18001288c  mov     rcx, [r15]; pbstr
0x18001288f  test    rcx, rcx
0x180012892  jz      short loc_18001289E
0x180012894  call    cs:__imp_SysStringLen
0x18001289a  test    eax, eax
0x18001289c  jnz     short loc_1800128DC
0x18001289e  test    r14d, r14d
0x1800128a1  jnz     short loc_1800128DC
0x1800128a3  mov     rcx, [rbp+57h+var_90]
0x1800128a7  mov     rdx, r15
0x1800128aa  mov     rax, [rcx]
0x1800128ad  mov     rax, [rax+20h]
0x1800128b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800128b6  mov     ebx, eax
0x1800128b8  test    eax, eax
0x1800128ba  js      loc_1800129E0
0x1800128c0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 20h
0x1800128c7  jz      short loc_1800128DC
0x1800128c9  mov     r9, [r15]
0x1800128cc  lea     r8d, [r14+1]
0x1800128d0  lea     rdx, SDIAGPRV_EVENT_DEBUG_LOCAL_CONTENT_SEARCH_QUERY_PARAMETER
0x1800128d7  call    McTemplateU0qz_EventWriteTransfer
0x1800128dc  mov     r15, [rbp+57h+arg_0]
0x1800128e0  mov     eax, dword ptr [rbp+57h+var_70+8]
0x1800128e3  inc     eax
0x1800128e5  jmp     loc_18001276A
0x1800128ea  cmp     [rbp+57h+ppvData], 0
0x1800128ef  jz      short loc_1800128FA
0x1800128f1  mov     rcx, rsi; psa
0x1800128f4  call    cs:__imp_SafeArrayUnaccessData
0x1800128fa  mov     [rbp+57h+ppvData], 0
0x180012902  test    r14d, r14d
0x180012905  jz      short loc_18001292F
0x180012907  lea     rdx, [rbp+57h+rgsabound]; psaboundNew
0x18001290b  mov     [rbp+57h+rgsabound.lLbound], 0
0x180012912  mov     rcx, rsi; psa
0x180012915  mov     [rbp+57h+rgsabound.cElements], r14d
0x180012919  call    cs:__imp_SafeArrayRedim
0x18001291f  mov     ebx, eax
0x180012921  test    eax, eax
0x180012923  js      loc_1800129E4
0x180012929  mov     [rdi+18h], rsi
0x18001292d  xor     esi, esi
0x18001292f  mov     [r12], rdi
0x180012933  jmp     loc_1800129E4
0x180012938  xor     edi, edi
0x18001293a  mov     ebx, 8007000Eh
0x18001293f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012946  jz      short loc_18001295B
0x180012948  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18001294f  lea     r8, aCdiagnosticmat_3; "CDiagnosticMatcher::CreateInstance"
0x180012956  call    McTemplateU0s_EventWriteTransfer
0x18001295b  mov     rcx, [rbp+57h+var_90]
0x18001295f  test    rcx, rcx
0x180012962  jz      short loc_180012978
0x180012964  mov     rax, [rcx]
0x180012967  mov     rax, [rax+10h]
0x18001296b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012970  mov     [rbp+57h+var_90], 0
0x180012978  lea     rcx, [rbp+57h+var_70]; struct tagVARIANT *
0x18001297c  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x180012981  cmp     [rbp+57h+ppvData], 0
0x180012986  jz      short loc_180012999
0x180012988  mov     rcx, rsi; psa
0x18001298b  call    cs:__imp_SafeArrayUnaccessData
0x180012991  mov     [rbp+57h+ppvData], 0
0x180012999  test    rsi, rsi
0x18001299c  jz      short loc_1800129A7
0x18001299e  mov     rcx, rsi; psa
0x1800129a1  call    cs:__imp_SafeArrayDestroy
0x1800129a7  test    ebx, ebx
0x1800129a9  jns     short loc_1800129C3
0x1800129ab  test    rdi, rdi
0x1800129ae  jz      short loc_1800129C3
0x1800129b0  mov     rax, [rdi]
0x1800129b3  mov     edx, 1
0x1800129b8  mov     rcx, rdi
0x1800129bb  mov     rax, [rax]
0x1800129be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129c3  mov     eax, ebx
0x1800129c5  mov     rbx, [rsp+0C0h+arg_8]
0x1800129cd  add     rsp, 90h
0x1800129d4  pop     r15
0x1800129d6  pop     r14
0x1800129d8  pop     r13
0x1800129da  pop     r12
0x1800129dc  pop     rdi
0x1800129dd  pop     rsi
0x1800129de  pop     rbp
0x1800129df  retn
0x1800129e0  mov     r15, [rbp+57h+arg_0]
0x1800129e4  cmp     ebx, 8007000Eh
0x1800129ea  jz      loc_18001293F
0x1800129f0  cmp     ebx, 80070057h
0x1800129f6  jz      short loc_180012A36
0x1800129f8  test    ebx, ebx
0x1800129fa  jz      short loc_180012A1D
0x1800129fc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012a03  jz      loc_18001295B
0x180012a09  mov     r9d, ebx
0x180012a0c  lea     r8, aCdiagnosticmat_3; "CDiagnosticMatcher::CreateInstance"
0x180012a13  call    McTemplateU0sq_EventWriteTransfer
0x180012a18  jmp     loc_18001295B
0x180012a1d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180012a24  jz      loc_18001295B
0x180012a2a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180012a31  jmp     loc_18001294F
0x180012a36  test    r15, r15
0x180012a39  jnz     short loc_180012A51
0x180012a3b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012a42  jz      loc_18001295B
0x180012a48  lea     rax, aDiagnosticmeta_0; "DiagnosticMetadataCollection"
0x180012a4f  jmp     short loc_180012A89
0x180012a51  test    r13, r13
0x180012a54  jnz     short loc_180012A6C
0x180012a56  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012a5d  jz      loc_18001295B
0x180012a63  lea     rax, aCulture; "Culture"
0x180012a6a  jmp     short loc_180012A89
0x180012a6c  test    r12, r12
0x180012a6f  jnz     loc_1800126CC
0x180012a75  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180012a7c  jz      loc_18001295B
0x180012a82  lea     rax, aDiagnosticmatc; "DiagnosticMatcher"
0x180012a89  mov     r9d, 80070057h
0x180012a8f  mov     [rsp+0C0h+var_A0], rax
0x180012a94  lea     r8, aCdiagnosticmat_3; "CDiagnosticMatcher::CreateInstance"
  ... truncated ...
```
