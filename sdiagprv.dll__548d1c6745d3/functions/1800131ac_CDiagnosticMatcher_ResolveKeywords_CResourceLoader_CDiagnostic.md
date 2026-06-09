# CDiagnosticMatcher::ResolveKeywords(CResourceLoader *,CDiagnostic *)

- ea: `0x1800131ac`
- end: `0x1800133a4`
- name: `?ResolveKeywords@CDiagnosticMatcher@@AEBAJPEAVCResourceLoader@@PEAVCDiagnostic@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(CDiagnosticMatcher *__hidden this, struct CResourceLoader *, struct CDiagnostic *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180012aac`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180011d2c`
- `0x1800131ac`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800132c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180013384`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132c0`
- `OLEAUT32!__imp_SysFreeString` at `0x180013384`
- `OLEAUT32!__imp_SysStringLen` at `0x180013284`
- `OLEAUT32!__imp_SysStringLen` at `0x180013284`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180013258`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180013258`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001336e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18001336e`

## pseudocode

```c
__int64 __fastcall CDiagnosticMatcher::ResolveKeywords(
        CDiagnosticMatcher *this,
        struct CResourceLoader *a2,
        struct CDiagnostic *a3)
{
  SAFEARRAY *v3; // rsi
  unsigned __int16 *v4; // rdi
  HRESULT v6; // ebx
  const char *v7; // rax
  __int64 v8; // r14
  unsigned __int16 *v9; // r12
  __int64 v10; // r9
  __int64 *v11; // rdx
  void *ppvData; // [rsp+70h] [rbp+40h] BYREF
  CResourceLoader *v14; // [rsp+78h] [rbp+48h]
  unsigned __int16 *v15; // [rsp+88h] [rbp+58h] BYREF

  v14 = a2;
  v3 = 0;
  v4 = 0;
  ppvData = 0;
  v15 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    {
      v7 = "ResourceLoader";
      goto LABEL_9;
    }
    return (unsigned int)v6;
  }
  if ( !a3 )
  {
    v6 = -2147024809;
    goto LABEL_6;
  }
  v3 = (SAFEARRAY *)*((_QWORD *)a3 + 20);
  v6 = 0;
  if ( !v3 )
  {
LABEL_33:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_36;
    v11 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
    goto LABEL_35;
  }
  v6 = SafeArrayAccessData(*((SAFEARRAY **)a3 + 20), &ppvData);
  if ( v6 < 0 )
    goto LABEL_23;
  v8 = 0;
  if ( !v3->rgsabound[0].cElements )
  {
LABEL_25:
    if ( v6 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_36;
      v10 = (unsigned int)v6;
      goto LABEL_28;
    }
    goto LABEL_33;
  }
  while ( 1 )
  {
    this = (CDiagnosticMatcher *)ppvData;
    v9 = (unsigned __int16 *)*((_QWORD *)ppvData + v8);
    if ( v9 )
    {
      if ( SysStringLen(*((BSTR *)ppvData + v8)) && *v9 == 64 )
        break;
    }
LABEL_20:
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= v3->rgsabound[0].cElements )
      goto LABEL_23;
  }
  v6 = CResourceLoader::LoadLocalizedResource(v14, v9, &v15);
  if ( v6 >= 0 )
  {
    this = (CDiagnosticMatcher *)ppvData;
    if ( *((_QWORD *)ppvData + v8) )
    {
      SysFreeString(*((BSTR *)ppvData + v8));
      *((_QWORD *)ppvData + v8) = 0;
      this = (CDiagnosticMatcher *)ppvData;
    }
    v4 = 0;
    *((_QWORD *)this + v8) = v15;
    v15 = 0;
    goto LABEL_20;
  }
  v4 = v15;
LABEL_23:
  if ( v6 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_36;
    v11 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
LABEL_35:
    McTemplateU0s_EventWriteTransfer(this, v11, "CDiagnosticMatcher::ResolveKeywords");
    goto LABEL_36;
  }
  if ( v6 != -2147024809 )
    goto LABEL_25;
LABEL_6:
  if ( a3 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_36;
    v10 = 2147942487LL;
LABEL_28:
    McTemplateU0sq_EventWriteTransfer(this, a2, "CDiagnosticMatcher::ResolveKeywords", v10);
    goto LABEL_36;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v7 = "Diagnostic";
LABEL_9:
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CDiagnosticMatcher::ResolveKeywords",
      -2147024809,
      (__int64)v7);
  }
LABEL_36:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v3);
    ppvData = 0;
  }
  if ( v4 )
    SysFreeString(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800131ac  mov     [rsp-38h+arg_10], rbx
0x1800131b1  mov     [rsp-38h+arg_8], rdx
0x1800131b6  mov     [rsp-38h+ppvData], rcx
0x1800131bb  push    rbp
0x1800131bc  push    rsi
0x1800131bd  push    rdi
0x1800131be  push    r12
0x1800131c0  push    r13
0x1800131c2  push    r14
0x1800131c4  push    r15
0x1800131c6  mov     rbp, rsp
0x1800131c9  sub     rsp, 30h
0x1800131cd  xor     esi, esi
0x1800131cf  xor     edi, edi
0x1800131d1  mov     [rbp+ppvData], rsi
0x1800131d5  mov     r15, r8
0x1800131d8  mov     [rbp+arg_18], rdi
0x1800131dc  test    rdx, rdx
0x1800131df  jnz     short loc_1800131FC
0x1800131e1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800131e8  mov     ebx, 80070057h
0x1800131ed  jz      loc_18001338A
0x1800131f3  lea     rax, aResourceloader; "ResourceLoader"
0x1800131fa  jmp     short loc_180013223
0x1800131fc  test    r15, r15
0x1800131ff  jnz     short loc_18001323F
0x180013201  mov     ebx, 80070057h
0x180013206  test    r15, r15
0x180013209  jnz     loc_180013325
0x18001320f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180013216  jz      loc_180013364
0x18001321c  lea     rax, aDiagnostic; "Diagnostic"
0x180013223  mov     r9d, 80070057h
0x180013229  mov     [rsp+30h+var_10], rax
0x18001322e  lea     r8, aCdiagnosticmat; "CDiagnosticMatcher::ResolveKeywords"
0x180013235  call    McTemplateU0sqs_EventWriteTransfer
0x18001323a  jmp     loc_180013364
0x18001323f  mov     rsi, [r8+0A0h]
0x180013246  xor     ebx, ebx
0x180013248  test    rsi, rsi
0x18001324b  jz      loc_180013348
0x180013251  lea     rdx, [rbp+ppvData]; ppvData
0x180013255  mov     rcx, rsi; psa
0x180013258  call    cs:__imp_SafeArrayAccessData
0x18001325e  mov     ebx, eax
0x180013260  test    eax, eax
0x180013262  js      loc_1800132F3
0x180013268  xor     r14d, r14d
0x18001326b  cmp     [rsi+18h], edi
0x18001326e  jbe     loc_180013307
0x180013274  mov     rcx, [rbp+ppvData]
0x180013278  mov     r12, [rcx+r14*8]
0x18001327c  test    r12, r12
0x18001327f  jz      short loc_1800132E4
0x180013281  mov     rcx, r12; pbstr
0x180013284  call    cs:__imp_SysStringLen
0x18001328a  test    eax, eax
0x18001328c  jz      short loc_1800132E4
0x18001328e  mov     eax, 40h ; '@'
0x180013293  cmp     ax, [r12]
0x180013298  jnz     short loc_1800132E4
0x18001329a  mov     rcx, [rbp+arg_8]; this
0x18001329e  lea     r8, [rbp+arg_18]; unsigned __int16 **
0x1800132a2  mov     rdx, r12; unsigned __int16 *
0x1800132a5  call    ?LoadLocalizedResource@CResourceLoader@@QEAAJPEAGPEAPEAG@Z; CResourceLoader::LoadLocalizedResource(ushort *,ushort * *)
0x1800132aa  mov     ebx, eax
0x1800132ac  test    eax, eax
0x1800132ae  js      short loc_1800132EF
0x1800132b0  mov     rcx, [rbp+ppvData]
0x1800132b4  mov     rax, [rcx+r14*8]
0x1800132b8  test    rax, rax
0x1800132bb  jz      short loc_1800132D6
0x1800132bd  mov     rcx, rax; bstrString
0x1800132c0  call    cs:__imp_SysFreeString
0x1800132c6  mov     rax, [rbp+ppvData]
0x1800132ca  mov     qword ptr [rax+r14*8], 0
0x1800132d2  mov     rcx, [rbp+ppvData]
0x1800132d6  mov     rax, [rbp+arg_18]
0x1800132da  xor     edi, edi
0x1800132dc  mov     [rcx+r14*8], rax
0x1800132e0  mov     [rbp+arg_18], rdi
0x1800132e4  inc     r14d
0x1800132e7  cmp     r14d, [rsi+18h]
0x1800132eb  jb      short loc_180013274
0x1800132ed  jmp     short loc_1800132F3
0x1800132ef  mov     rdi, [rbp+arg_18]
0x1800132f3  cmp     ebx, 8007000Eh
0x1800132f9  jz      short loc_180013336
0x1800132fb  cmp     ebx, 80070057h
0x180013301  jz      loc_180013206
0x180013307  test    ebx, ebx
0x180013309  jz      short loc_180013348
0x18001330b  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180013312  jz      short loc_180013364
0x180013314  mov     r9d, ebx
0x180013317  lea     r8, aCdiagnosticmat; "CDiagnosticMatcher::ResolveKeywords"
0x18001331e  call    McTemplateU0sq_EventWriteTransfer
0x180013323  jmp     short loc_180013364
0x180013325  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001332c  jz      short loc_180013364
0x18001332e  mov     r9d, 80070057h
0x180013334  jmp     short loc_180013317
0x180013336  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001333d  jz      short loc_180013364
0x18001333f  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180013346  jmp     short loc_180013358
0x180013348  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18001334f  jz      short loc_180013364
0x180013351  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180013358  lea     r8, aCdiagnosticmat; "CDiagnosticMatcher::ResolveKeywords"
0x18001335f  call    McTemplateU0s_EventWriteTransfer
0x180013364  cmp     [rbp+ppvData], 0
0x180013369  jz      short loc_18001337C
0x18001336b  mov     rcx, rsi; psa
0x18001336e  call    cs:__imp_SafeArrayUnaccessData
0x180013374  mov     [rbp+ppvData], 0
0x18001337c  test    rdi, rdi
0x18001337f  jz      short loc_18001338A
0x180013381  mov     rcx, rdi; bstrString
0x180013384  call    cs:__imp_SysFreeString
0x18001338a  mov     eax, ebx
0x18001338c  mov     rbx, [rsp+30h+arg_10]
0x180013394  add     rsp, 30h
0x180013398  pop     r15
0x18001339a  pop     r14
0x18001339c  pop     r13
0x18001339e  pop     r12
0x1800133a0  pop     rdi
0x1800133a1  pop     rsi
0x1800133a2  pop     rbp
0x1800133a3  retn
```
