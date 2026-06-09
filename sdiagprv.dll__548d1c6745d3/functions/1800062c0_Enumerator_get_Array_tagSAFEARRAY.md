# Enumerator::get_Array(tagSAFEARRAY * *)

- ea: `0x1800062c0`
- end: `0x1800063f4`
- name: `?get_Array@Enumerator@@QEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(Enumerator *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180005ce0`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x1800062c0`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800063d8`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800063d8`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180006337`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x180006337`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000635c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x18000635c`

## pseudocode

```c
__int64 __fastcall Enumerator::get_Array(Enumerator *this, struct tagSAFEARRAY **a2)
{
  __int64 v4; // rcx
  SAFEARRAY *v5; // rcx
  HRESULT v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 *v9; // rdx
  SAFEARRAY *ppsaOut; // [rsp+40h] [rbp+8h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+50h] [rbp+18h] BYREF

  ppsaOut = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::get_Array");
  SDiagPrvSyncObject::Lock((Enumerator *)((char *)this + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v4, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::get_Array");
  v5 = (SAFEARRAY *)*((_QWORD *)this + 9);
  if ( v5 )
  {
    v6 = SafeArrayCopy(v5, &ppsaOut);
    if ( v6 >= 0 )
    {
      psaboundNew.cElements = *((_DWORD *)this + 21);
      psaboundNew.lLbound = 0;
      v6 = SafeArrayRedim(ppsaOut, &psaboundNew);
      if ( v6 >= 0 )
      {
        *a2 = ppsaOut;
        ppsaOut = 0;
      }
    }
  }
  else
  {
    v6 = -2147020590;
  }
  SDiagPrvSyncObject::Unlock((Enumerator *)((char *)this + 8));
  if ( v6 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_19;
    v9 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_18;
  }
  if ( !v6 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_19;
    v9 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_18:
    McTemplateU0s_EventWriteTransfer(v8, v9, "Enumerator::get_Array");
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v8, v7, "Enumerator::get_Array", (unsigned int)v6);
LABEL_19:
  if ( ppsaOut )
    SafeArrayDestroy(ppsaOut);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800062c0  mov     [rsp+arg_8], rbx
0x1800062c5  mov     [rsp+arg_18], rsi
0x1800062ca  push    rdi
0x1800062cb  push    r14
0x1800062cd  push    r15
0x1800062cf  sub     rsp, 20h
0x1800062d3  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800062da  lea     r15, aEnumeratorGetA; "Enumerator::get_Array"
0x1800062e1  mov     r14, rdx
0x1800062e4  mov     [rsp+38h+ppsaOut], 0
0x1800062ed  mov     rdi, rcx
0x1800062f0  jge     short loc_180006301
0x1800062f2  mov     r8, r15
0x1800062f5  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800062fc  call    McTemplateU0s_EventWriteTransfer
0x180006301  lea     rcx, [rdi+8]; this
0x180006305  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x18000630a  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180006311  jge     short loc_180006322
0x180006313  mov     r8, r15
0x180006316  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x18000631d  call    McTemplateU0s_EventWriteTransfer
0x180006322  mov     rcx, [rdi+48h]; psa
0x180006326  test    rcx, rcx
0x180006329  jnz     short loc_180006332
0x18000632b  mov     ebx, 800710D2h
0x180006330  jmp     short loc_180006379
0x180006332  lea     rdx, [rsp+38h+ppsaOut]; ppsaOut
0x180006337  call    cs:__imp_SafeArrayCopy
0x18000633d  mov     ebx, eax
0x18000633f  test    eax, eax
0x180006341  js      short loc_180006379
0x180006343  mov     eax, [rdi+54h]
0x180006346  lea     rdx, [rsp+38h+psaboundNew]; psaboundNew
0x18000634b  mov     rcx, [rsp+38h+ppsaOut]; psa
0x180006350  mov     [rsp+38h+psaboundNew.cElements], eax
0x180006354  mov     [rsp+38h+psaboundNew.lLbound], 0
0x18000635c  call    cs:__imp_SafeArrayRedim
0x180006362  mov     ebx, eax
0x180006364  test    eax, eax
0x180006366  js      short loc_180006379
0x180006368  mov     rax, [rsp+38h+ppsaOut]
0x18000636d  mov     [r14], rax
0x180006370  mov     [rsp+38h+ppsaOut], 0
0x180006379  lea     rcx, [rdi+8]; this
0x18000637d  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180006382  cmp     ebx, 8007000Eh
0x180006388  jz      short loc_1800063B6
0x18000638a  test    ebx, ebx
0x18000638c  jz      short loc_1800063A4
0x18000638e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006395  jz      short loc_1800063CE
0x180006397  mov     r9d, ebx
0x18000639a  mov     r8, r15
0x18000639d  call    McTemplateU0sq_EventWriteTransfer
0x1800063a2  jmp     short loc_1800063CE
0x1800063a4  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800063ab  jz      short loc_1800063CE
0x1800063ad  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800063b4  jmp     short loc_1800063C6
0x1800063b6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800063bd  jz      short loc_1800063CE
0x1800063bf  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x1800063c6  mov     r8, r15
0x1800063c9  call    McTemplateU0s_EventWriteTransfer
0x1800063ce  mov     rcx, [rsp+38h+ppsaOut]; psa
0x1800063d3  test    rcx, rcx
0x1800063d6  jz      short loc_1800063DE
0x1800063d8  call    cs:__imp_SafeArrayDestroy
0x1800063de  mov     rsi, [rsp+38h+arg_18]
0x1800063e3  mov     eax, ebx
0x1800063e5  mov     rbx, [rsp+38h+arg_8]
0x1800063ea  add     rsp, 20h
0x1800063ee  pop     r15
0x1800063f0  pop     r14
0x1800063f2  pop     rdi
0x1800063f3  retn
```
