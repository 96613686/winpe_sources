# Enumerator::GetNamedItem<IDiagnostic>(tagVARIANT,long (IDiagnostic::*)(ushort * *),IDiagnostic * *)

- ea: `0x180010634`
- end: `0x18001076c`
- name: `??$GetNamedItem@UIDiagnostic@@@Enumerator@@QEAAJUtagVARIANT@@P8IDiagnostic@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010550`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x1800102a8`
- `0x180010634`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800106d3`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800106d3`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010757`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180010757`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<IDiagnostic>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rcx
  __int64 v8; // r8
  IRecordInfo *v9; // xmm1_8
  int v10; // ebx
  __int64 (__fastcall ***v11)(_QWORD, GUID *, __int64); // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  VARIANTARG v15; // [rsp+20h] [rbp-38h] BYREF
  void *ppvData; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v17; // [rsp+70h] [rbp+18h] BYREF
  int v18; // [rsp+74h] [rbp+1Ch]

  v18 = HIDWORD(a3);
  v17 = 0;
  ppvData = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::GetNamedItem");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(a1 + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v7, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::GetNamedItem");
  v9 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v15.vt = *(_OWORD *)a2;
  v15.pRecInfo = v9;
  v10 = Enumerator::GetIndex<IDiagnostic>((char *)a1, &v15, v8, &v17);
  if ( v10 >= 0 )
  {
    v10 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 72), &ppvData);
    if ( v10 >= 0 )
    {
      v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * v17 + 1);
      v10 = (**v11)(v11, &GUID_140bfe8d_54ec_11dc_b924_001438c29fab, a4);
    }
  }
  SDiagPrvSyncObject::Unlock((SDiagPrvSyncObject *)(a1 + 8));
  if ( v10 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v13, v12, "Enumerator::GetNamedItem", (unsigned int)v10);
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(v13, SDIAGPRV_EVENT_DEBUG_SUCCESS, "Enumerator::GetNamedItem");
  }
  if ( ppvData )
    SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 72));
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180010634  mov     rax, rsp
0x180010637  mov     [rax+10h], rbx
0x18001063b  mov     [rax+18h], r8
0x18001063f  push    rbp
0x180010640  push    rsi
0x180010641  push    rdi
0x180010642  sub     rsp, 40h
0x180010646  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x18001064d  mov     rbp, r9
0x180010650  mov     rbx, rdx
0x180010653  mov     dword ptr [rax+18h], 0
0x18001065a  mov     rdi, rcx
0x18001065d  mov     qword ptr [rax+8], 0
0x180010665  jge     short loc_18001067A
0x180010667  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x18001066e  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x180010675  call    McTemplateU0s_EventWriteTransfer
0x18001067a  lea     rcx, [rdi+8]; this
0x18001067e  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180010683  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x18001068a  jge     short loc_18001069F
0x18001068c  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180010693  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x18001069a  call    McTemplateU0s_EventWriteTransfer
0x18001069f  movaps  xmm0, xmmword ptr [rbx]
0x1800106a2  lea     r9, [rsp+58h+arg_10]
0x1800106a7  movsd   xmm1, qword ptr [rbx+10h]
0x1800106ac  lea     rdx, [rsp+58h+var_38]
0x1800106b1  mov     rcx, rdi
0x1800106b4  movaps  [rsp+58h+var_38], xmm0
0x1800106b9  movsd   [rsp+58h+var_28], xmm1
0x1800106bf  call    ??$GetIndex@UIDiagnostic@@@Enumerator@@IEAAJUtagVARIANT@@P8IDiagnostic@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDiagnostic>(tagVARIANT,long (IDiagnostic::*)(ushort * *),ulong *)
0x1800106c4  mov     ebx, eax
0x1800106c6  test    eax, eax
0x1800106c8  js      short loc_180010708
0x1800106ca  mov     rcx, [rdi+48h]; psa
0x1800106ce  lea     rdx, [rsp+58h+ppvData]; ppvData
0x1800106d3  call    cs:__imp_SafeArrayAccessData
0x1800106d9  mov     ebx, eax
0x1800106db  test    eax, eax
0x1800106dd  js      short loc_180010708
0x1800106df  mov     eax, [rsp+58h+arg_10]
0x1800106e3  mov     r8, rbp
0x1800106e6  lea     rdx, [rax+rax*2]
0x1800106ea  mov     rax, [rsp+58h+ppvData]
0x1800106ef  mov     rcx, [rax+rdx*8+8]
0x1800106f4  lea     rdx, _GUID_140bfe8d_54ec_11dc_b924_001438c29fab
0x1800106fb  mov     rax, [rcx]
0x1800106fe  mov     rax, [rax]
0x180010701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010706  mov     ebx, eax
0x180010708  lea     rcx, [rdi+8]; this
0x18001070c  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180010711  test    ebx, ebx
0x180010713  jz      short loc_18001072F
0x180010715  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x18001071c  jz      short loc_18001074B
0x18001071e  mov     r9d, ebx
0x180010721  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180010728  call    McTemplateU0sq_EventWriteTransfer
0x18001072d  jmp     short loc_18001074B
0x18001072f  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180010736  jz      short loc_18001074B
0x180010738  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x18001073f  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180010746  call    McTemplateU0s_EventWriteTransfer
0x18001074b  cmp     [rsp+58h+ppvData], 0
0x180010751  jz      short loc_18001075D
0x180010753  mov     rcx, [rdi+48h]; psa
0x180010757  call    cs:__imp_SafeArrayUnaccessData
0x18001075d  mov     eax, ebx
0x18001075f  mov     rbx, [rsp+58h+arg_8]
0x180010764  add     rsp, 40h
0x180010768  pop     rdi
0x180010769  pop     rsi
0x18001076a  pop     rbp
0x18001076b  retn
```
