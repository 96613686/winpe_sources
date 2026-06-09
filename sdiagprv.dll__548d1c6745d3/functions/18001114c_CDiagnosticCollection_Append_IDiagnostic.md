# CDiagnosticCollection::Append(IDiagnostic *)

- ea: `0x18001114c`
- end: `0x18001139a`
- name: `?Append@CDiagnosticCollection@@QEAAJPEAUIDiagnostic@@@Z`
- size: `590`
- prototype: `__int64 __fastcall(Enumerator **this, struct IDiagnostic *)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18000855c`
- `0x18000daa0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800032ec`
- `0x18000331c`
- `0x1800037fc`
- `0x180003908`
- `0x180005af8`
- `0x18001114c`
- `0x180011aa8`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011345`
- `OLEAUT32!__imp_SysFreeString` at `0x180011358`
- `OLEAUT32!__imp_SysFreeString` at `0x18001136b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001137e`
- `OLEAUT32!__imp_SysFreeString` at `0x180011345`
- `OLEAUT32!__imp_SysFreeString` at `0x180011358`
- `OLEAUT32!__imp_SysFreeString` at `0x18001136b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001137e`

## pseudocode

```c
__int64 __fastcall CDiagnosticCollection::Append(Enumerator **this, struct IDiagnostic *a2)
{
  __int64 v4; // rcx
  int v5; // ebx
  int *v6; // r8
  Enumerator *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  BSTR v11; // [rsp+30h] [rbp-20h] BYREF
  struct tagVARIANT v12; // [rsp+38h] [rbp-18h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp+30h] BYREF
  BSTR v14; // [rsp+90h] [rbp+40h] BYREF
  BSTR v15; // [rsp+98h] [rbp+48h] BYREF

  bstrString = 0;
  v14 = 0;
  v15 = 0;
  v11 = 0;
  memset(&v12, 0, sizeof(v12));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "CDiagnosticCollection::Append");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(this + 1));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v4, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "CDiagnosticCollection::Append");
  v5 = SDiagPrviVariantInit(&v12);
  if ( v5 >= 0 )
  {
    if ( !a2 )
    {
      v5 = -2147024809;
      goto LABEL_20;
    }
    if ( !this[9] )
      goto LABEL_9;
    v5 = (*(__int64 (__fastcall **)(struct IDiagnostic *, BSTR *))(*(_QWORD *)a2 + 72LL))(a2, &bstrString);
    if ( v5 >= 0 )
    {
      if ( !bstrString )
        goto LABEL_9;
      v5 = (*(__int64 (__fastcall **)(struct IDiagnostic *, BSTR *))(*(_QWORD *)a2 + 88LL))(a2, &v14);
      if ( v5 < 0 )
        goto LABEL_20;
      if ( !v14 )
        goto LABEL_9;
      v5 = (*(__int64 (__fastcall **)(struct IDiagnostic *, BSTR *))(*(_QWORD *)a2 + 64LL))(a2, &v15);
      if ( v5 < 0 )
        goto LABEL_20;
      if ( !v15 )
        goto LABEL_9;
      v5 = (*(__int64 (__fastcall **)(struct IDiagnostic *, BSTR *))(*(_QWORD *)a2 + 40LL))(a2, &v11);
      if ( v5 < 0 )
        goto LABEL_20;
      if ( !v11 )
      {
LABEL_9:
        v5 = -2147467259;
        goto LABEL_20;
      }
      v5 = (**(__int64 (__fastcall ***)(struct IDiagnostic *, GUID *, ULONG *))a2)(
             a2,
             &IID_IUnknown,
             (ULONG *)&v12.cyVal);
      if ( v5 >= 0 )
      {
        v7 = this[9];
        v12.vt = 13;
        v5 = Enumerator::Add(v7, &v12, v6);
      }
    }
  }
LABEL_20:
  SDiagPrvSyncObject::Unlock((SDiagPrvSyncObject *)(this + 1));
  if ( v5 == -2147024809 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sqs_EventWriteTransfer(
        v9,
        v8,
        (unsigned int)"CDiagnosticCollection::Append",
        -2147024809,
        (__int64)"Diagnostic");
  }
  else if ( v5 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v9, v8, "CDiagnosticCollection::Append", (unsigned int)v5);
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
  {
    McTemplateU0zzzz_EventWriteTransfer(v9, v8, (_DWORD)bstrString, (_DWORD)v14, (__int64)v15, (__int64)v11);
  }
  SDiagPrviVariantClear(&v12);
  if ( bstrString )
  {
    SysFreeString(bstrString);
    bstrString = 0;
  }
  if ( v14 )
  {
    SysFreeString(v14);
    v14 = 0;
  }
  if ( v15 )
  {
    SysFreeString(v15);
    v15 = 0;
  }
  if ( v11 )
    SysFreeString(v11);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18001114c  mov     [rsp-28h+arg_8], rbx
0x180011151  push    rbp
0x180011152  push    rsi
0x180011153  push    rdi
0x180011154  push    r14
0x180011156  push    r15
0x180011158  mov     rbp, rsp
0x18001115b  sub     rsp, 50h
0x18001115f  xor     r15d, r15d
0x180011162  xor     eax, eax
0x180011164  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r15b
0x18001116b  xorps   xmm0, xmm0
0x18001116e  mov     rdi, rdx
0x180011171  mov     [rbp+bstrString], r15
0x180011175  mov     rsi, rcx
0x180011178  mov     [rbp+arg_10], r15
0x18001117c  mov     [rbp+arg_18], r15
0x180011180  mov     [rbp+var_20], r15
0x180011184  movups  xmmword ptr [rbp+var_18], xmm0
0x180011188  mov     qword ptr [rbp+var_18+10h], rax
0x18001118c  jge     short loc_1800111A1
0x18001118e  lea     r8, aCdiagnosticcol_0; "CDiagnosticCollection::Append"
0x180011195  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x18001119c  call    McTemplateU0s_EventWriteTransfer
0x1800111a1  lea     rcx, [rsi+8]; this
0x1800111a5  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x1800111aa  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r15b
0x1800111b1  jge     short loc_1800111C6
0x1800111b3  lea     r8, aCdiagnosticcol_0; "CDiagnosticCollection::Append"
0x1800111ba  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x1800111c1  call    McTemplateU0s_EventWriteTransfer
0x1800111c6  lea     rcx, [rbp+var_18]; struct tagVARIANT *
0x1800111ca  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x1800111cf  mov     ebx, eax
0x1800111d1  test    eax, eax
0x1800111d3  js      loc_1800112B3
0x1800111d9  test    rdi, rdi
0x1800111dc  jnz     short loc_1800111E8
0x1800111de  mov     ebx, 80070057h
0x1800111e3  jmp     loc_1800112B3
0x1800111e8  cmp     [rsi+48h], r15
0x1800111ec  jnz     short loc_1800111F8
0x1800111ee  mov     ebx, 80004005h
0x1800111f3  jmp     loc_1800112B3
0x1800111f8  mov     rax, [rdi]
0x1800111fb  lea     rdx, [rbp+bstrString]
0x1800111ff  mov     rcx, rdi
0x180011202  mov     rax, [rax+48h]
0x180011206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001120b  mov     ebx, eax
0x18001120d  test    eax, eax
0x18001120f  js      loc_1800112B3
0x180011215  cmp     [rbp+bstrString], r15
0x180011219  jz      short loc_1800111EE
0x18001121b  mov     rax, [rdi]
0x18001121e  lea     rdx, [rbp+arg_10]
0x180011222  mov     rcx, rdi
0x180011225  mov     rax, [rax+58h]
0x180011229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001122e  mov     ebx, eax
0x180011230  test    eax, eax
0x180011232  js      short loc_1800112B3
0x180011234  cmp     [rbp+arg_10], r15
0x180011238  jz      short loc_1800111EE
0x18001123a  mov     rax, [rdi]
0x18001123d  lea     rdx, [rbp+arg_18]
0x180011241  mov     rcx, rdi
0x180011244  mov     rax, [rax+40h]
0x180011248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001124d  mov     ebx, eax
0x18001124f  test    eax, eax
0x180011251  js      short loc_1800112B3
0x180011253  cmp     [rbp+arg_18], r15
0x180011257  jz      short loc_1800111EE
0x180011259  mov     rax, [rdi]
0x18001125c  lea     rdx, [rbp+var_20]
0x180011260  mov     rcx, rdi
0x180011263  mov     rax, [rax+28h]
0x180011267  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001126c  mov     ebx, eax
0x18001126e  test    eax, eax
0x180011270  js      short loc_1800112B3
0x180011272  cmp     [rbp+var_20], r15
0x180011276  jz      loc_1800111EE
0x18001127c  mov     rax, [rdi]
0x18001127f  lea     r8, [rbp+var_18+8]
0x180011283  lea     rdx, IID_IUnknown
0x18001128a  mov     rcx, rdi
0x18001128d  mov     rax, [rax]
0x180011290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011295  mov     ebx, eax
0x180011297  test    eax, eax
0x180011299  js      short loc_1800112B3
0x18001129b  mov     rcx, [rsi+48h]; this
0x18001129f  lea     rdx, [rbp+var_18]; struct tagVARIANT *
0x1800112a3  mov     eax, 0Dh
0x1800112a8  mov     word ptr [rbp+var_18], ax
0x1800112ac  call    ?Add@Enumerator@@QEAAJPEAUtagVARIANT@@PEAJ@Z; Enumerator::Add(tagVARIANT *,long *)
0x1800112b1  mov     ebx, eax
0x1800112b3  lea     rcx, [rsi+8]; this
0x1800112b7  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x1800112bc  cmp     ebx, 80070057h
0x1800112c2  jz      short loc_18001130C
0x1800112c4  test    ebx, ebx
0x1800112c6  jz      short loc_1800112E2
0x1800112c8  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800112cf  jz      short loc_180011333
0x1800112d1  mov     r9d, ebx
0x1800112d4  lea     r8, aCdiagnosticcol_0; "CDiagnosticCollection::Append"
0x1800112db  call    McTemplateU0sq_EventWriteTransfer
0x1800112e0  jmp     short loc_180011333
0x1800112e2  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, r15b
0x1800112e9  jge     short loc_180011333
0x1800112eb  mov     rax, [rbp+var_20]
0x1800112ef  mov     r9, [rbp+arg_10]
0x1800112f3  mov     r8, [rbp+bstrString]
0x1800112f7  mov     [rsp+50h+var_28], rax
0x1800112fc  mov     rax, [rbp+arg_18]
0x180011300  mov     [rsp+50h+var_30], rax
0x180011305  call    McTemplateU0zzzz_EventWriteTransfer
0x18001130a  jmp     short loc_180011333
0x18001130c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180011313  jz      short loc_180011333
0x180011315  lea     rax, aDiagnostic; "Diagnostic"
0x18001131c  mov     r9d, 80070057h
0x180011322  lea     r8, aCdiagnosticcol_0; "CDiagnosticCollection::Append"
0x180011329  mov     [rsp+50h+var_30], rax
0x18001132e  call    McTemplateU0sqs_EventWriteTransfer
0x180011333  lea     rcx, [rbp+var_18]; struct tagVARIANT *
0x180011337  call    ?SDiagPrviVariantClear@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantClear(tagVARIANT *)
0x18001133c  mov     rcx, [rbp+bstrString]; bstrString
0x180011340  test    rcx, rcx
0x180011343  jz      short loc_18001134F
0x180011345  call    cs:__imp_SysFreeString
0x18001134b  mov     [rbp+bstrString], r15
0x18001134f  mov     rcx, [rbp+arg_10]; bstrString
0x180011353  test    rcx, rcx
0x180011356  jz      short loc_180011362
0x180011358  call    cs:__imp_SysFreeString
0x18001135e  mov     [rbp+arg_10], r15
0x180011362  mov     rcx, [rbp+arg_18]; bstrString
0x180011366  test    rcx, rcx
0x180011369  jz      short loc_180011375
0x18001136b  call    cs:__imp_SysFreeString
0x180011371  mov     [rbp+arg_18], r15
0x180011375  mov     rcx, [rbp+var_20]; bstrString
0x180011379  test    rcx, rcx
0x18001137c  jz      short loc_180011384
0x18001137e  call    cs:__imp_SysFreeString
0x180011384  mov     eax, ebx
0x180011386  mov     rbx, [rsp+50h+arg_8]
0x18001138e  add     rsp, 50h
0x180011392  pop     r15
0x180011394  pop     r14
0x180011396  pop     rdi
0x180011397  pop     rsi
0x180011398  pop     rbp
0x180011399  retn
```
