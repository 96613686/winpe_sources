# Enumerator::GetItem<IDiagnosticMetadata>(tagVARIANT,IDiagnosticMetadata * *)

- ea: `0x1800042c4`
- end: `0x1800043a1`
- name: `??$GetItem@UIDiagnosticMetadata@@@Enumerator@@QEAAJUtagVARIANT@@PEAPEAUIDiagnosticMetadata@@@Z`
- size: `221`
- prototype: `__int64 __fastcall(__int64, __int128 *, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800046b0`
- `0x180005040`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x1800042c4`
- `0x1800043a8`

## pseudocode

```c
__int64 __fastcall Enumerator::GetItem<IDiagnosticMetadata>(__int64 a1, __int128 *a2, __int64 a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // xmm1_8
  unsigned int v9; // eax
  SDiagPrvSyncObject *v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 *v14; // rdx
  __int128 v16; // [rsp+20h] [rbp-48h] BYREF
  __int64 v17; // [rsp+30h] [rbp-38h]

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::GetItem");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(a1 + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v6, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::GetItem");
  v8 = *((_QWORD *)a2 + 2);
  v16 = *a2;
  v17 = v8;
  v9 = ((__int64 (__fastcall *)(__int64, __int128 *, __int64, __int64))Enumerator::GetNamedItem<IDiagnosticMetadata>)(
         a1,
         &v16,
         v7,
         a3);
  v10 = (SDiagPrvSyncObject *)(a1 + 8);
  v11 = v9;
  SDiagPrvSyncObject::Unlock(v10);
  if ( v11 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v11;
    v14 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_13;
  }
  if ( !v11 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v11;
    v14 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_13:
    McTemplateU0s_EventWriteTransfer(v13, v14, "Enumerator::GetItem");
    return v11;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v13, v12, "Enumerator::GetItem", v11);
  return v11;
}

```

## disassembly

```asm
0x1800042c4  push    rbx
0x1800042c6  push    rbp
0x1800042c7  push    rsi
0x1800042c8  push    rdi
0x1800042c9  push    r14
0x1800042cb  sub     rsp, 40h
0x1800042cf  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800042d6  lea     r14, aEnumeratorGeti; "Enumerator::GetItem"
0x1800042dd  mov     rbp, r8
0x1800042e0  mov     rsi, rdx
0x1800042e3  mov     rbx, rcx
0x1800042e6  jge     short loc_1800042F7
0x1800042e8  mov     r8, r14
0x1800042eb  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800042f2  call    McTemplateU0s_EventWriteTransfer
0x1800042f7  lea     rdi, [rbx+8]
0x1800042fb  mov     rcx, rdi; this
0x1800042fe  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180004303  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x18000430a  jge     short loc_18000431B
0x18000430c  mov     r8, r14
0x18000430f  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x180004316  call    McTemplateU0s_EventWriteTransfer
0x18000431b  movaps  xmm0, xmmword ptr [rsi]
0x18000431e  lea     rdx, [rsp+68h+var_48]
0x180004323  movsd   xmm1, qword ptr [rsi+10h]
0x180004328  mov     r9, rbp
0x18000432b  mov     rcx, rbx
0x18000432e  movaps  [rsp+68h+var_48], xmm0
0x180004333  movsd   [rsp+68h+var_38], xmm1
0x180004339  call    ??$GetNamedItem@UIDiagnosticMetadata@@@Enumerator@@QEAAJUtagVARIANT@@P8IDiagnosticMetadata@@EAAJPEAPEAG@ZPEAPEAU2@@Z; Enumerator::GetNamedItem<IDiagnosticMetadata>(tagVARIANT,long (IDiagnosticMetadata::*)(ushort * *),IDiagnosticMetadata * *)
0x18000433e  mov     rcx, rdi; this
0x180004341  mov     ebx, eax
0x180004343  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180004348  cmp     ebx, 8007000Eh
0x18000434e  jz      short loc_18000437C
0x180004350  test    ebx, ebx
0x180004352  jz      short loc_18000436A
0x180004354  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000435b  jz      short loc_180004394
0x18000435d  mov     r9d, ebx
0x180004360  mov     r8, r14
0x180004363  call    McTemplateU0sq_EventWriteTransfer
0x180004368  jmp     short loc_180004394
0x18000436a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180004371  jz      short loc_180004394
0x180004373  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x18000437a  jmp     short loc_18000438C
0x18000437c  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180004383  jz      short loc_180004394
0x180004385  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x18000438c  mov     r8, r14
0x18000438f  call    McTemplateU0s_EventWriteTransfer
0x180004394  mov     eax, ebx
0x180004396  add     rsp, 40h
0x18000439a  pop     r14
0x18000439c  pop     rdi
0x18000439d  pop     rsi
0x18000439e  pop     rbp
0x18000439f  pop     rbx
0x1800043a0  retn
```
