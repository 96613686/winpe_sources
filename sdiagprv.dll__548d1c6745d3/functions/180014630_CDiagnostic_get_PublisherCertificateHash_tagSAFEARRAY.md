# CDiagnostic::get_PublisherCertificateHash(tagSAFEARRAY * *)

- ea: `0x180014630`
- end: `0x18001474e`
- name: `?get_PublisherCertificateHash@CDiagnostic@@UEAAJPEAPEAUtagSAFEARRAY@@@Z`
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
- `0x180014630`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800146a1`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1800146a1`

## pseudocode

```c
__int64 __fastcall CDiagnostic::get_PublisherCertificateHash(SAFEARRAY **this, struct tagSAFEARRAY **a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  SAFEARRAY *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r9
  __int64 *v10; // rdx

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(
      this,
      SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START,
      "CDiagnostic::get_PublisherCertificateHash");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(this + 1));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(
      v4,
      SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END,
      "CDiagnostic::get_PublisherCertificateHash");
  if ( a2 )
  {
    v5 = 0;
    *a2 = 0;
    v6 = this[16];
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
        McTemplateU0sq_EventWriteTransfer(v8, v7, "CDiagnostic::get_PublisherCertificateHash", v9);
        return v5;
      }
      return v5;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v5;
    v10 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_24:
    McTemplateU0s_EventWriteTransfer(v8, v10, "CDiagnostic::get_PublisherCertificateHash");
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
      (unsigned int)"CDiagnostic::get_PublisherCertificateHash",
      -2147024809,
      (__int64)"PublisherCertificateHash");
  return v5;
}

```

## disassembly

```asm
0x180014630  push    rbx
0x180014632  push    rbp
0x180014633  push    rsi
0x180014634  push    rdi
0x180014635  push    r15
0x180014637  sub     rsp, 30h
0x18001463b  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180014642  lea     r15, aCdiagnosticGet_5; "CDiagnostic::get_PublisherCertificateHa"...
0x180014649  mov     rdi, rdx
0x18001464c  mov     rsi, rcx
0x18001464f  jge     short loc_180014660
0x180014651  mov     r8, r15
0x180014654  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x18001465b  call    McTemplateU0s_EventWriteTransfer
0x180014660  lea     rcx, [rsi+8]; this
0x180014664  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180014669  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180014670  jge     short loc_180014681
0x180014672  mov     r8, r15
0x180014675  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x18001467c  call    McTemplateU0s_EventWriteTransfer
0x180014681  test    rdi, rdi
0x180014684  jnz     short loc_18001468D
0x180014686  mov     ebx, 80070057h
0x18001468b  jmp     short loc_1800146A9
0x18001468d  xor     ebx, ebx
0x18001468f  mov     [rdi], rbx
0x180014692  mov     rcx, [rsi+80h]; psa
0x180014699  test    rcx, rcx
0x18001469c  jz      short loc_1800146A9
0x18001469e  mov     rdx, rdi; ppsaOut
0x1800146a1  call    cs:__imp_SafeArrayCopy
0x1800146a7  mov     ebx, eax
0x1800146a9  lea     rcx, [rsi+8]; this
0x1800146ad  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x1800146b2  cmp     ebx, 8007000Eh
0x1800146b8  jz      short loc_180014729
0x1800146ba  cmp     ebx, 80070057h
0x1800146c0  jz      short loc_1800146EE
0x1800146c2  test    ebx, ebx
0x1800146c4  jz      short loc_1800146DC
0x1800146c6  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800146cd  jz      short loc_180014741
0x1800146cf  mov     r9d, ebx
0x1800146d2  mov     r8, r15
0x1800146d5  call    McTemplateU0sq_EventWriteTransfer
0x1800146da  jmp     short loc_180014741
0x1800146dc  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800146e3  jz      short loc_180014741
0x1800146e5  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800146ec  jmp     short loc_180014739
0x1800146ee  test    rdi, rdi
0x1800146f1  jnz     short loc_180014718
0x1800146f3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800146fa  jz      short loc_180014741
0x1800146fc  lea     rax, aPublishercerti; "PublisherCertificateHash"
0x180014703  mov     r9d, 80070057h
0x180014709  mov     r8, r15
0x18001470c  mov     [rsp+58h+var_38], rax
0x180014711  call    McTemplateU0sqs_EventWriteTransfer
0x180014716  jmp     short loc_180014741
0x180014718  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001471f  jz      short loc_180014741
0x180014721  mov     r9d, 80070057h
0x180014727  jmp     short loc_1800146D2
0x180014729  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180014730  jz      short loc_180014741
0x180014732  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180014739  mov     r8, r15
0x18001473c  call    McTemplateU0s_EventWriteTransfer
0x180014741  mov     eax, ebx
0x180014743  add     rsp, 30h
0x180014747  pop     r15
0x180014749  pop     rdi
0x18001474a  pop     rsi
0x18001474b  pop     rbp
0x18001474c  pop     rbx
0x18001474d  retn
```
