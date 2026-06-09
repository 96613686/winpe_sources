# CDiagnostic::get_Keywords(tagSAFEARRAY * *)

- ea: `0x180014280`
- end: `0x18001439e`
- name: `?get_Keywords@CDiagnostic@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `286`
- prototype: `__int64 __fastcall(SAFEARRAY **this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x1800037fc`
- `0x180003908`
- `0x180014280`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800142f1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800142f1`

## pseudocode

```c
__int64 __fastcall CDiagnostic::get_Keywords(SAFEARRAY **this, struct tagSAFEARRAY **a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  SAFEARRAY *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 *v10; // rdx

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "CDiagnostic::get_Keywords");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(this + 1));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v4, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "CDiagnostic::get_Keywords");
  if ( a2 )
  {
    v5 = 0;
    *a2 = 0;
    v6 = this[20];
    if ( v6 )
      v5 = SafeArrayCopy(v6, a2);
  }
  else
  {
    v5 = -2147024809;
  }
  SDiagPrvSyncObject::Unlock((SDiagPrvSyncObject *)(this + 1));
  if ( v5 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v5;
    v10 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_24;
  }
  if ( v5 != -2147024809 )
  {
    if ( v5 )
    {
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      {
        v9 = v5;
LABEL_14:
        McTemplateU0sq_EventWriteTransfer(v8, v7, "CDiagnostic::get_Keywords", v9);
        return v5;
      }
      return v5;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v5;
    v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_24:
    McTemplateU0s_EventWriteTransfer(v8, v10, "CDiagnostic::get_Keywords");
    return v5;
  }
  if ( a2 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v5;
    v9 = 2147942487LL;
    goto LABEL_14;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      v8,
      v7,
      (unsigned int)"CDiagnostic::get_Keywords",
      -2147024809,
      (__int64)"Keywords");
  return v5;
}

```

## disassembly

```asm
0x180014280  push    rbx
0x180014282  push    rbp
0x180014283  push    rsi
0x180014284  push    rdi
0x180014285  push    r15
0x180014287  sub     rsp, 30h
0x18001428b  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180014292  lea     r15, aCdiagnosticGet_10; "CDiagnostic::get_Keywords"
0x180014299  mov     rdi, rdx
0x18001429c  mov     rsi, rcx
0x18001429f  jge     short loc_1800142B0
0x1800142a1  mov     r8, r15
0x1800142a4  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800142ab  call    McTemplateU0s_EventWriteTransfer
0x1800142b0  lea     rcx, [rsi+8]; this
0x1800142b4  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x1800142b9  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800142c0  jge     short loc_1800142D1
0x1800142c2  mov     r8, r15
0x1800142c5  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x1800142cc  call    McTemplateU0s_EventWriteTransfer
0x1800142d1  test    rdi, rdi
0x1800142d4  jnz     short loc_1800142DD
0x1800142d6  mov     ebx, 80070057h
0x1800142db  jmp     short loc_1800142F9
0x1800142dd  xor     ebx, ebx
0x1800142df  mov     [rdi], rbx
0x1800142e2  mov     rcx, [rsi+0A0h]; psa
0x1800142e9  test    rcx, rcx
0x1800142ec  jz      short loc_1800142F9
0x1800142ee  mov     rdx, rdi; ppsaOut
0x1800142f1  call    cs:__imp_SafeArrayCopy
0x1800142f7  mov     ebx, eax
0x1800142f9  lea     rcx, [rsi+8]; this
0x1800142fd  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180014302  cmp     ebx, 8007000Eh
0x180014308  jz      short loc_180014379
0x18001430a  cmp     ebx, 80070057h
0x180014310  jz      short loc_18001433E
0x180014312  test    ebx, ebx
0x180014314  jz      short loc_18001432C
0x180014316  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001431d  jz      short loc_180014391
0x18001431f  mov     r9d, ebx
0x180014322  mov     r8, r15
0x180014325  call    McTemplateU0sq_EventWriteTransfer
0x18001432a  jmp     short loc_180014391
0x18001432c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180014333  jz      short loc_180014391
0x180014335  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18001433c  jmp     short loc_180014389
0x18001433e  test    rdi, rdi
0x180014341  jnz     short loc_180014368
0x180014343  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001434a  jz      short loc_180014391
0x18001434c  lea     rax, aKeywords; "Keywords"
0x180014353  mov     r9d, 80070057h
0x180014359  mov     r8, r15
0x18001435c  mov     [rsp+58h+var_38], rax
0x180014361  call    McTemplateU0sqs_EventWriteTransfer
0x180014366  jmp     short loc_180014391
0x180014368  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001436f  jz      short loc_180014391
0x180014371  mov     r9d, 80070057h
0x180014377  jmp     short loc_180014322
0x180014379  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180014380  jz      short loc_180014391
0x180014382  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180014389  mov     r8, r15
0x18001438c  call    McTemplateU0s_EventWriteTransfer
0x180014391  mov     eax, ebx
0x180014393  add     rsp, 30h
0x180014397  pop     r15
0x180014399  pop     rdi
0x18001439a  pop     rsi
0x18001439b  pop     rbp
0x18001439c  pop     rbx
0x18001439d  retn
```
