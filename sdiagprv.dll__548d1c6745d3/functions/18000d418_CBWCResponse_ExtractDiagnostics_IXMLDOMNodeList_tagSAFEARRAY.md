# CBWCResponse::ExtractDiagnostics(IXMLDOMNodeList *,tagSAFEARRAY * *)

- ea: `0x18000d418`
- end: `0x18000d741`
- name: `?ExtractDiagnostics@CBWCResponse@@CAJPEAUIXMLDOMNodeList@@PEAPEAUtagSAFEARRAY@@@Z`
- size: `809`
- prototype: `__int64 __fastcall(struct IXMLDOMNodeList *, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d244`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800032ec`
- `0x18000331c`
- `0x1800083ec`
- `0x18000d418`
- `0x18001374c`
- `0x180014e7c`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x18000d657`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d657`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d4cb`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x18000d4cb`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d54f`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18000d54f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000d576`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000d576`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d53d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d678`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d53d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000d678`

## pseudocode

```c
__int64 __fastcall CBWCResponse::ExtractDiagnostics(struct IXMLDOMNodeList *a1, struct tagSAFEARRAY **a2)
{
  CDiagnostic *v3; // rsi
  SAFEARRAY *v4; // rdi
  __int64 v6; // rdx
  __int64 v7; // rcx
  HRESULT IsLocal; // ebx
  SAFEARRAY *v9; // rax
  __int64 *v10; // rdx
  signed int i; // r14d
  CDiagnostic *Class; // rax
  __int64 v14; // r9
  const char *v15; // rax
  void *ppvData; // [rsp+30h] [rbp-30h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+38h] [rbp-28h] BYREF
  VARIANTARG pvargSrc; // [rsp+40h] [rbp-20h] BYREF
  signed int v19; // [rsp+B0h] [rbp+50h] BYREF
  struct IXMLDOMNode *v20; // [rsp+B8h] [rbp+58h] BYREF

  v20 = 0;
  v19 = 0;
  memset(&pvargSrc, 0, sizeof(pvargSrc));
  v3 = 0;
  rgsabound = 0;
  v4 = 0;
  ppvData = 0;
  IsLocal = SDiagPrviVariantInit(&pvargSrc);
  if ( IsLocal >= 0 )
  {
    if ( !a1 )
    {
      IsLocal = -2147024809;
LABEL_48:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
        goto LABEL_13;
      v15 = "NodeList";
LABEL_53:
      McTemplateU0sqs_EventWriteTransfer(
        v7,
        v6,
        (unsigned int)"CBWCResponse::ExtractDiagnostics",
        -2147024809,
        (__int64)v15);
      goto LABEL_13;
    }
    if ( !a2 )
    {
      IsLocal = -2147024809;
      goto LABEL_51;
    }
    *a2 = 0;
    IsLocal = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, signed int *))a1->lpVtbl->get_length)(a1, &v19);
    if ( IsLocal >= 0 )
    {
      if ( v19 <= 0 )
      {
LABEL_36:
        *a2 = v4;
        if ( ppvData )
        {
          SafeArrayUnaccessData(v4);
          ppvData = 0;
        }
        v4 = 0;
LABEL_41:
        if ( !IsLocal )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
            goto LABEL_13;
          v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_12:
          McTemplateU0s_EventWriteTransfer(v7, v10, "CBWCResponse::ExtractDiagnostics");
          goto LABEL_13;
        }
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_13;
        v14 = (unsigned int)IsLocal;
LABEL_44:
        McTemplateU0sq_EventWriteTransfer(v7, v6, "CBWCResponse::ExtractDiagnostics", v14);
        goto LABEL_13;
      }
      rgsabound.lLbound = 0;
      rgsabound.cElements = v19;
      v9 = SafeArrayCreate(0xCu, 1u, &rgsabound);
      v4 = v9;
      if ( !v9 )
      {
LABEL_9:
        IsLocal = -2147024882;
LABEL_10:
        if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
          goto LABEL_13;
        v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
        goto LABEL_12;
      }
      IsLocal = SafeArrayAccessData(v9, &ppvData);
      if ( IsLocal >= 0 )
      {
        for ( i = 0; i < v19; ++i )
        {
          if ( v20 )
          {
            ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
            v20 = 0;
          }
          IsLocal = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, struct IXMLDOMNode **))a1->lpVtbl->get_item)(
                      a1,
                      (unsigned int)i,
                      &v20);
          if ( IsLocal < 0 )
            goto LABEL_39;
          if ( v3 )
            (*(void (__fastcall **)(CDiagnostic *))(*(_QWORD *)v3 + 16LL))(v3);
          SDiagPrviVariantClear(&pvargSrc);
          Class = CreateClassObject<CDiagnostic>();
          v3 = Class;
          if ( !Class )
            goto LABEL_9;
          IsLocal = CDiagnostic::Load(Class, v20);
          if ( IsLocal < 0 )
            goto LABEL_39;
          IsLocal = CDiagnostic::put_IsLocal(v3, 0);
          if ( IsLocal < 0 )
            goto LABEL_39;
          IsLocal = (**(__int64 (__fastcall ***)(CDiagnostic *, GUID *, ULONG *))v3)(
                      v3,
                      &IID_IUnknown,
                      (ULONG *)&pvargSrc.cyVal);
          if ( IsLocal < 0 )
            goto LABEL_39;
          pvargSrc.vt = 13;
          IsLocal = VariantCopy((VARIANTARG *)ppvData + i, &pvargSrc);
          if ( IsLocal < 0 )
            goto LABEL_39;
        }
        goto LABEL_36;
      }
    }
  }
LABEL_39:
  if ( IsLocal == -2147024882 )
    goto LABEL_10;
  if ( IsLocal != -2147024809 )
    goto LABEL_41;
  if ( !a1 )
    goto LABEL_48;
  if ( !a2 )
  {
LABEL_51:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_13;
    v15 = "Diagnostics";
    goto LABEL_53;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
  {
    v14 = 2147942487LL;
    goto LABEL_44;
  }
LABEL_13:
  if ( v20 )
  {
    ((void (__fastcall *)(struct IXMLDOMNode *))v20->lpVtbl->Release)(v20);
    v20 = 0;
  }
  if ( v3 )
    (*(void (__fastcall **)(CDiagnostic *))(*(_QWORD *)v3 + 16LL))(v3);
  SDiagPrviVariantClear(&pvargSrc);
  if ( ppvData )
  {
    SafeArrayUnaccessData(v4);
    ppvData = 0;
  }
  if ( v4 )
    SafeArrayDestroy(v4);
  return (unsigned int)IsLocal;
}

```

## disassembly

```asm
0x18000d418  mov     [rsp-38h+arg_0], rbx
0x18000d41d  push    rbp
0x18000d41e  push    rsi
0x18000d41f  push    rdi
0x18000d420  push    r12
0x18000d422  push    r13
0x18000d424  push    r14
0x18000d426  push    r15
0x18000d428  mov     rbp, rsp
0x18000d42b  sub     rsp, 60h
0x18000d42f  xor     r13d, r13d
0x18000d432  mov     r15, rcx
0x18000d435  xorps   xmm0, xmm0
0x18000d438  mov     [rbp+arg_18], r13
0x18000d43c  xor     eax, eax
0x18000d43e  mov     [rbp+arg_10], r13d
0x18000d442  lea     rcx, [rbp+pvargSrc]; struct tagVARIANT *
0x18000d446  mov     qword ptr [rbp+pvargSrc+10h], rax
0x18000d44a  movups  xmmword ptr [rbp+pvargSrc], xmm0
0x18000d44e  mov     esi, r13d
0x18000d451  mov     qword ptr [rbp+rgsabound.cElements], r13
0x18000d455  mov     edi, r13d
0x18000d458  mov     [rbp+ppvData], r13
0x18000d45c  mov     r12, rdx
0x18000d45f  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x18000d464  mov     ebx, eax
0x18000d466  test    eax, eax
0x18000d468  js      loc_18000D687
0x18000d46e  test    r15, r15
0x18000d471  jnz     short loc_18000D47D
0x18000d473  mov     ebx, 80070057h
0x18000d478  jmp     loc_18000D6DE
0x18000d47d  test    r12, r12
0x18000d480  jnz     short loc_18000D48C
0x18000d482  mov     ebx, 80070057h
0x18000d487  jmp     loc_18000D6F9
0x18000d48c  mov     [r12], r13
0x18000d490  lea     rdx, [rbp+arg_10]
0x18000d494  mov     rax, [r15]
0x18000d497  mov     rcx, r15
0x18000d49a  mov     rax, [rax+40h]
0x18000d49e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4a3  mov     ebx, eax
0x18000d4a5  test    eax, eax
0x18000d4a7  js      loc_18000D687
0x18000d4ad  mov     eax, [rbp+arg_10]
0x18000d4b0  test    eax, eax
0x18000d4b2  jle     loc_18000D66B
0x18000d4b8  mov     ecx, 0Ch; vt
0x18000d4bd  mov     [rbp+rgsabound.lLbound], r13d
0x18000d4c1  lea     r8, [rbp+rgsabound]; rgsabound
0x18000d4c5  mov     [rbp+rgsabound.cElements], eax
0x18000d4c8  lea     edx, [rcx-0Bh]; cDims
0x18000d4cb  call    cs:__imp_SafeArrayCreate
0x18000d4d1  mov     rdi, rax
0x18000d4d4  test    rax, rax
0x18000d4d7  jnz     loc_18000D56F
0x18000d4dd  mov     ebx, 8007000Eh
0x18000d4e2  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d4e9  jz      short loc_18000D4FE
0x18000d4eb  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000d4f2  lea     r8, aCbwcresponseEx; "CBWCResponse::ExtractDiagnostics"
0x18000d4f9  call    McTemplateU0s_EventWriteTransfer
0x18000d4fe  mov     rcx, [rbp+arg_18]
0x18000d502  test    rcx, rcx
0x18000d505  jz      short loc_18000D517
0x18000d507  mov     rax, [rcx]
0x18000d50a  mov     rax, [rax+10h]
0x18000d50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d513  mov     [rbp+arg_18], r13
0x18000d517  test    rsi, rsi
0x18000d51a  jz      short loc_18000D52B
0x18000d51c  mov     rax, [rsi]
0x18000d51f  mov     rcx, rsi
0x18000d522  mov     rax, [rax+10h]
0x18000d526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d52b  lea     rcx, [rbp+pvargSrc]; struct tagVARIANT *
0x18000d52f  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18000d534  cmp     [rbp+ppvData], r13
0x18000d538  jz      short loc_18000D547
0x18000d53a  mov     rcx, rdi; psa
0x18000d53d  call    cs:__imp_SafeArrayUnaccessData
0x18000d543  mov     [rbp+ppvData], r13
0x18000d547  test    rdi, rdi
0x18000d54a  jz      short loc_18000D555
0x18000d54c  mov     rcx, rdi; psa
0x18000d54f  call    cs:__imp_SafeArrayDestroy
0x18000d555  mov     eax, ebx
0x18000d557  mov     rbx, [rsp+60h+arg_0]
0x18000d55f  add     rsp, 60h
0x18000d563  pop     r15
0x18000d565  pop     r14
0x18000d567  pop     r13
0x18000d569  pop     r12
0x18000d56b  pop     rdi
0x18000d56c  pop     rsi
0x18000d56d  pop     rbp
0x18000d56e  retn
0x18000d56f  lea     rdx, [rbp+ppvData]; ppvData
0x18000d573  mov     rcx, rax; psa
0x18000d576  call    cs:__imp_SafeArrayAccessData
0x18000d57c  mov     ebx, eax
0x18000d57e  test    eax, eax
0x18000d580  js      loc_18000D687
0x18000d586  mov     r14d, r13d
0x18000d589  cmp     r14d, [rbp+arg_10]
0x18000d58d  jge     loc_18000D66B
0x18000d593  mov     rcx, [rbp+arg_18]
0x18000d597  test    rcx, rcx
0x18000d59a  jz      short loc_18000D5AC
0x18000d59c  mov     rax, [rcx]
0x18000d59f  mov     rax, [rax+10h]
0x18000d5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5a8  mov     [rbp+arg_18], r13
0x18000d5ac  mov     rax, [r15]
0x18000d5af  lea     r8, [rbp+arg_18]
0x18000d5b3  mov     edx, r14d
0x18000d5b6  mov     rcx, r15
0x18000d5b9  mov     rax, [rax+38h]
0x18000d5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5c2  mov     ebx, eax
0x18000d5c4  test    eax, eax
0x18000d5c6  js      loc_18000D687
0x18000d5cc  test    rsi, rsi
0x18000d5cf  jz      short loc_18000D5E0
0x18000d5d1  mov     rax, [rsi]
0x18000d5d4  mov     rcx, rsi
0x18000d5d7  mov     rax, [rax+10h]
0x18000d5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5e0  lea     rcx, [rbp+pvargSrc]; struct tagVARIANT *
0x18000d5e4  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18000d5e9  call    ??$CreateClassObject@VCDiagnostic@@@@YAPEAVCDiagnostic@@XZ; CreateClassObject<CDiagnostic>(void)
0x18000d5ee  mov     rsi, rax
0x18000d5f1  test    rax, rax
0x18000d5f4  jz      loc_18000D4DD
0x18000d5fa  mov     rdx, [rbp+arg_18]; struct IXMLDOMNode *
0x18000d5fe  mov     rcx, rax; this
0x18000d601  call    ?Load@CDiagnostic@@QEAAJPEAUIXMLDOMNode@@@Z; CDiagnostic::Load(IXMLDOMNode *)
0x18000d606  mov     ebx, eax
0x18000d608  test    eax, eax
0x18000d60a  js      short loc_18000D687
0x18000d60c  xor     edx, edx; __int16
0x18000d60e  mov     rcx, rsi; this
0x18000d611  call    ?put_IsLocal@CDiagnostic@@QEAAJF@Z; CDiagnostic::put_IsLocal(short)
0x18000d616  mov     ebx, eax
0x18000d618  test    eax, eax
0x18000d61a  js      short loc_18000D687
0x18000d61c  mov     rax, [rsi]
0x18000d61f  lea     r8, [rbp+pvargSrc+8]
0x18000d623  lea     rdx, IID_IUnknown
0x18000d62a  mov     rcx, rsi
0x18000d62d  mov     rax, [rax]
0x18000d630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d635  mov     ebx, eax
0x18000d637  test    eax, eax
0x18000d639  js      short loc_18000D687
0x18000d63b  mov     eax, 0Dh
0x18000d640  lea     rdx, [rbp+pvargSrc]; pvargSrc
0x18000d644  mov     word ptr [rbp+pvargSrc], ax
0x18000d648  movsxd  rax, r14d
0x18000d64b  lea     rcx, [rax+rax*2]
0x18000d64f  mov     rax, [rbp+ppvData]
0x18000d653  lea     rcx, [rax+rcx*8]; pvargDest
0x18000d657  call    cs:__imp_VariantCopy
0x18000d65d  mov     ebx, eax
0x18000d65f  test    eax, eax
0x18000d661  js      short loc_18000D687
0x18000d663  inc     r14d
0x18000d666  jmp     loc_18000D589
0x18000d66b  mov     [r12], rdi
0x18000d66f  cmp     [rbp+ppvData], r13
0x18000d673  jz      short loc_18000D682
0x18000d675  mov     rcx, rdi; psa
0x18000d678  call    cs:__imp_SafeArrayUnaccessData
0x18000d67e  mov     [rbp+ppvData], r13
0x18000d682  mov     rdi, r13
0x18000d685  jmp     short loc_18000D69B
0x18000d687  cmp     ebx, 8007000Eh
0x18000d68d  jz      loc_18000D4E2
0x18000d693  cmp     ebx, 80070057h
0x18000d699  jz      short loc_18000D6D9
0x18000d69b  test    ebx, ebx
0x18000d69d  jz      short loc_18000D6C0
0x18000d69f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d6a6  jz      loc_18000D4FE
0x18000d6ac  mov     r9d, ebx
0x18000d6af  lea     r8, aCbwcresponseEx; "CBWCResponse::ExtractDiagnostics"
0x18000d6b6  call    McTemplateU0sq_EventWriteTransfer
0x18000d6bb  jmp     loc_18000D4FE
0x18000d6c0  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000d6c7  jz      loc_18000D4FE
0x18000d6cd  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000d6d4  jmp     loc_18000D4F2
0x18000d6d9  test    r15, r15
0x18000d6dc  jnz     short loc_18000D6F4
0x18000d6de  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d6e5  jz      loc_18000D4FE
0x18000d6eb  lea     rax, aNodelist; "NodeList"
0x18000d6f2  jmp     short loc_18000D70D
0x18000d6f4  test    r12, r12
0x18000d6f7  jnz     short loc_18000D729
0x18000d6f9  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d700  jz      loc_18000D4FE
0x18000d706  lea     rax, aDiagnostics; "Diagnostics"
0x18000d70d  mov     r9d, 80070057h
0x18000d713  mov     [rsp+60h+var_40], rax
0x18000d718  lea     r8, aCbwcresponseEx; "CBWCResponse::ExtractDiagnostics"
0x18000d71f  call    McTemplateU0sqs_EventWriteTransfer
0x18000d724  jmp     loc_18000D4FE
0x18000d729  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000d730  jz      loc_18000D4FE
0x18000d736  mov     r9d, 80070057h
0x18000d73c  jmp     loc_18000D6AF
```
