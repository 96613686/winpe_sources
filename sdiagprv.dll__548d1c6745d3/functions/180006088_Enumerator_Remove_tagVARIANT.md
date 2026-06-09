# Enumerator::Remove(tagVARIANT)

- ea: `0x180006088`
- end: `0x18000615b`
- name: `?Remove@Enumerator@@QEAAJUtagVARIANT@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(Enumerator *__hidden this, struct tagVARIANT *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180010938`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x1800057b4`
- `0x180006088`

## string_xrefs

- `0x180006098`: `Enumerator::Remove`

## pseudocode

```c
__int64 __fastcall Enumerator::Remove(Enumerator *this, struct tagVARIANT *a2)
{
  SDiagPrvSyncObject *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // r8
  IRecordInfo *pRecInfo; // xmm1_8
  unsigned int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 *v11; // rdx
  __int128 v13; // [rsp+20h] [rbp-48h] BYREF
  IRecordInfo *v14; // [rsp+30h] [rbp-38h]

  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::Remove");
  v4 = (Enumerator *)((char *)this + 8);
  SDiagPrvSyncObject::Lock((Enumerator *)((char *)this + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::Remove");
  pRecInfo = a2->pRecInfo;
  v13 = *(_OWORD *)&a2->vt;
  v14 = pRecInfo;
  v8 = Enumerator::RemoveNamed<IUnknown>((__int64)this, (__int64)&v13, v6);
  SDiagPrvSyncObject::Unlock(v4);
  if ( v8 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      return v8;
    v11 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_13;
  }
  if ( !v8 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      return v8;
    v11 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_13:
    McTemplateU0s_EventWriteTransfer(v10, v11, "Enumerator::Remove");
    return v8;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v10, v9, "Enumerator::Remove", v8);
  return v8;
}

```

## disassembly

```asm
0x180006088  push    rbx
0x18000608a  push    rbp
0x18000608b  push    rsi
0x18000608c  push    rdi
0x18000608d  sub     rsp, 48h
0x180006091  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180006098  lea     rbp, aEnumeratorRemo; "Enumerator::Remove"
0x18000609f  mov     rsi, rdx
0x1800060a2  mov     rbx, rcx
0x1800060a5  jge     short loc_1800060B6
0x1800060a7  mov     r8, rbp
0x1800060aa  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800060b1  call    McTemplateU0s_EventWriteTransfer
0x1800060b6  lea     rdi, [rbx+8]
0x1800060ba  mov     rcx, rdi; this
0x1800060bd  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x1800060c2  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800060c9  jge     short loc_1800060DA
0x1800060cb  mov     r8, rbp
0x1800060ce  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x1800060d5  call    McTemplateU0s_EventWriteTransfer
0x1800060da  movaps  xmm0, xmmword ptr [rsi]
0x1800060dd  lea     rdx, [rsp+68h+var_48]
0x1800060e2  movsd   xmm1, qword ptr [rsi+10h]
0x1800060e7  mov     rcx, rbx
0x1800060ea  movaps  [rsp+68h+var_48], xmm0
0x1800060ef  movsd   [rsp+68h+var_38], xmm1
0x1800060f5  call    ??$RemoveNamed@UIUnknown@@@Enumerator@@QEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@Z@Z; Enumerator::RemoveNamed<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *))
0x1800060fa  mov     ebx, eax
0x1800060fc  mov     rcx, rdi; this
0x1800060ff  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180006104  cmp     ebx, 8007000Eh
0x18000610a  jz      short loc_180006138
0x18000610c  test    ebx, ebx
0x18000610e  jz      short loc_180006126
0x180006110  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180006117  jz      short loc_180006150
0x180006119  mov     r9d, ebx
0x18000611c  mov     r8, rbp
0x18000611f  call    McTemplateU0sq_EventWriteTransfer
0x180006124  jmp     short loc_180006150
0x180006126  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x18000612d  jz      short loc_180006150
0x18000612f  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180006136  jmp     short loc_180006148
0x180006138  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18000613f  jz      short loc_180006150
0x180006141  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180006148  mov     r8, rbp
0x18000614b  call    McTemplateU0s_EventWriteTransfer
0x180006150  mov     eax, ebx
0x180006152  add     rsp, 48h
0x180006156  pop     rdi
0x180006157  pop     rsi
0x180006158  pop     rbp
0x180006159  pop     rbx
0x18000615a  retn
```
