# Enumerator::GetNamedItem<IDiagnosticMetadata>(tagVARIANT,long (IDiagnosticMetadata::*)(ushort * *),IDiagnosticMetadata * *)

- ea: `0x1800043a8`
- end: `0x1800044e0`
- name: `??$GetNamedItem@UIDiagnosticMetadata@@@Enumerator@@QEAAJUtagVARIANT@@P8IDiagnosticMetadata@@EAAJPEAPEAG@ZPEAPEAU2@@Z`
- size: `312`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800042c4`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x18000401c`
- `0x1800043a8`
- `0x180019010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180004447`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180004447`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800044cb`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800044cb`

## pseudocode

```c
__int64 __fastcall Enumerator::GetNamedItem<IDiagnosticMetadata>(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
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
  v10 = Enumerator::GetIndex<IDiagnosticMetadata>((char *)a1, &v15, v8, &v17);
  if ( v10 >= 0 )
  {
    v10 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 72), &ppvData);
    if ( v10 >= 0 )
    {
      v11 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)ppvData + 3 * v17 + 1);
      v10 = (**v11)(v11, &GUID_140bfe8b_54ec_11dc_b924_001438c29fab, a4);
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
0x1800043a8  mov     rax, rsp
0x1800043ab  mov     [rax+10h], rbx
0x1800043af  mov     [rax+18h], r8
0x1800043b3  push    rbp
0x1800043b4  push    rsi
0x1800043b5  push    rdi
0x1800043b6  sub     rsp, 40h
0x1800043ba  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800043c1  mov     rbp, r9
0x1800043c4  mov     rbx, rdx
0x1800043c7  mov     dword ptr [rax+18h], 0
0x1800043ce  mov     rdi, rcx
0x1800043d1  mov     qword ptr [rax+8], 0
0x1800043d9  jge     short loc_1800043EE
0x1800043db  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800043e2  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800043e9  call    McTemplateU0s_EventWriteTransfer
0x1800043ee  lea     rcx, [rdi+8]; this
0x1800043f2  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x1800043f7  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800043fe  jge     short loc_180004413
0x180004400  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x180004407  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x18000440e  call    McTemplateU0s_EventWriteTransfer
0x180004413  movaps  xmm0, xmmword ptr [rbx]
0x180004416  lea     r9, [rsp+58h+arg_10]
0x18000441b  movsd   xmm1, qword ptr [rbx+10h]
0x180004420  lea     rdx, [rsp+58h+var_38]
0x180004425  mov     rcx, rdi
0x180004428  movaps  [rsp+58h+var_38], xmm0
0x18000442d  movsd   [rsp+58h+var_28], xmm1
0x180004433  call    ??$GetIndex@UIDiagnosticMetadata@@@Enumerator@@IEAAJUtagVARIANT@@P8IDiagnosticMetadata@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IDiagnosticMetadata>(tagVARIANT,long (IDiagnosticMetadata::*)(ushort * *),ulong *)
0x180004438  mov     ebx, eax
0x18000443a  test    eax, eax
0x18000443c  js      short loc_18000447C
0x18000443e  mov     rcx, [rdi+48h]; psa
0x180004442  lea     rdx, [rsp+58h+ppvData]; ppvData
0x180004447  call    cs:__imp_SafeArrayAccessData
0x18000444d  mov     ebx, eax
0x18000444f  test    eax, eax
0x180004451  js      short loc_18000447C
0x180004453  mov     eax, [rsp+58h+arg_10]
0x180004457  mov     r8, rbp
0x18000445a  lea     rdx, [rax+rax*2]
0x18000445e  mov     rax, [rsp+58h+ppvData]
0x180004463  mov     rcx, [rax+rdx*8+8]
0x180004468  lea     rdx, _GUID_140bfe8b_54ec_11dc_b924_001438c29fab
0x18000446f  mov     rax, [rcx]
0x180004472  mov     rax, [rax]
0x180004475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000447a  mov     ebx, eax
0x18000447c  lea     rcx, [rdi+8]; this
0x180004480  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180004485  test    ebx, ebx
0x180004487  jz      short loc_1800044A3
0x180004489  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180004490  jz      short loc_1800044BF
0x180004492  mov     r9d, ebx
0x180004495  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x18000449c  call    McTemplateU0sq_EventWriteTransfer
0x1800044a1  jmp     short loc_1800044BF
0x1800044a3  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800044aa  jz      short loc_1800044BF
0x1800044ac  lea     r8, aEnumeratorGetn; "Enumerator::GetNamedItem"
0x1800044b3  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800044ba  call    McTemplateU0s_EventWriteTransfer
0x1800044bf  cmp     [rsp+58h+ppvData], 0
0x1800044c5  jz      short loc_1800044D1
0x1800044c7  mov     rcx, [rdi+48h]; psa
0x1800044cb  call    cs:__imp_SafeArrayUnaccessData
0x1800044d1  mov     eax, ebx
0x1800044d3  mov     rbx, [rsp+58h+arg_8]
0x1800044d8  add     rsp, 40h
0x1800044dc  pop     rdi
0x1800044dd  pop     rsi
0x1800044de  pop     rbp
0x1800044df  retn
```
