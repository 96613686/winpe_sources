# Enumerator::RemoveNamed<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *))

- ea: `0x1800057b4`
- end: `0x18000591b`
- name: `??$RemoveNamed@UIUnknown@@@Enumerator@@QEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@Z@Z`
- size: `359`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180006088`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x18000550c`
- `0x1800057b4`
- `0x1800180b2`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18000586c`
- `OLEAUT32!__imp_VariantClear` at `0x18000586c`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005851`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005851`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005902`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005902`

## string_xrefs

- `0x1800057ea`: `Enumerator::RemoveNamed`
- `0x18000580f`: `Enumerator::RemoveNamed`
- `0x1800058cd`: `Enumerator::RemoveNamed`
- `0x1800058e4`: `Enumerator::RemoveNamed`

## pseudocode

```c
__int64 __fastcall Enumerator::RemoveNamed<IUnknown>(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  IRecordInfo *v7; // xmm1_8
  int v8; // esi
  unsigned int v9; // ebx
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rcx
  VARIANTARG v14; // [rsp+20h] [rbp-20h] BYREF
  void *ppvData; // [rsp+70h] [rbp+30h] BYREF
  unsigned int v16; // [rsp+80h] [rbp+40h] BYREF
  int v17; // [rsp+84h] [rbp+44h]

  v17 = HIDWORD(a3);
  v16 = 0;
  ppvData = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(a1, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::RemoveNamed");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(a1 + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::RemoveNamed");
  v7 = *(IRecordInfo **)(a2 + 16);
  *(_OWORD *)&v14.vt = *(_OWORD *)a2;
  v14.pRecInfo = v7;
  v8 = Enumerator::GetIndex<IUnknown>((char *)a1, &v14, v6, &v16);
  if ( v8 >= 0 )
  {
    v8 = SafeArrayAccessData(*(SAFEARRAY **)(a1 + 72), &ppvData);
    if ( v8 >= 0 )
    {
      v9 = v16;
      v10 = 3LL * v16;
      VariantClear((VARIANTARG *)ppvData + v16);
      memmove_0((char *)ppvData + 8 * v10, (char *)ppvData + 24 * v9 + 24, 24LL * (*(_DWORD *)(a1 + 84) - v9 - 1));
      *((_WORD *)ppvData + 12 * (unsigned int)--*(_DWORD *)(a1 + 84)) = 0;
    }
  }
  SDiagPrvSyncObject::Unlock((SDiagPrvSyncObject *)(a1 + 8));
  if ( v8 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v12, v11, "Enumerator::RemoveNamed", (unsigned int)v8);
  }
  else if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
  {
    McTemplateU0s_EventWriteTransfer(v12, SDIAGPRV_EVENT_DEBUG_SUCCESS, "Enumerator::RemoveNamed");
  }
  if ( ppvData )
    SafeArrayUnaccessData(*(SAFEARRAY **)(a1 + 72));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800057b4  mov     [rsp-28h+arg_8], rbx
0x1800057b9  mov     [rsp-28h+arg_10], r8
0x1800057be  push    rbp
0x1800057bf  push    rsi
0x1800057c0  push    rdi
0x1800057c1  push    r14
0x1800057c3  push    r15
0x1800057c5  mov     rbp, rsp
0x1800057c8  sub     rsp, 40h
0x1800057cc  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x1800057d3  mov     rbx, rdx
0x1800057d6  mov     r14, rcx
0x1800057d9  mov     dword ptr [rbp+arg_10], 0
0x1800057e0  mov     [rbp+ppvData], 0
0x1800057e8  jge     short loc_1800057FD
0x1800057ea  lea     r8, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x1800057f1  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x1800057f8  call    McTemplateU0s_EventWriteTransfer
0x1800057fd  lea     rcx, [r14+8]; this
0x180005801  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180005806  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x18000580d  jge     short loc_180005822
0x18000580f  lea     r8, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x180005816  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x18000581d  call    McTemplateU0s_EventWriteTransfer
0x180005822  movaps  xmm0, xmmword ptr [rbx]
0x180005825  lea     r9, [rbp+arg_10]
0x180005829  movsd   xmm1, qword ptr [rbx+10h]
0x18000582e  lea     rdx, [rbp+var_20]
0x180005832  mov     rcx, r14
0x180005835  movaps  [rbp+var_20], xmm0
0x180005839  movsd   [rbp+var_10], xmm1
0x18000583e  call    ??$GetIndex@UIUnknown@@@Enumerator@@IEAAJUtagVARIANT@@P8IUnknown@@EAAJPEAPEAG@ZPEAK@Z; Enumerator::GetIndex<IUnknown>(tagVARIANT,long (IUnknown::*)(ushort * *),ulong *)
0x180005843  mov     esi, eax
0x180005845  test    eax, eax
0x180005847  js      short loc_1800058B4
0x180005849  mov     rcx, [r14+48h]; psa
0x18000584d  lea     rdx, [rbp+ppvData]; ppvData
0x180005851  call    cs:__imp_SafeArrayAccessData
0x180005857  mov     esi, eax
0x180005859  test    eax, eax
0x18000585b  js      short loc_1800058B4
0x18000585d  mov     rax, [rbp+ppvData]
0x180005861  mov     ebx, dword ptr [rbp+arg_10]
0x180005864  lea     rdi, [rbx+rbx*2]
0x180005868  lea     rcx, [rax+rdi*8]; pvarg
0x18000586c  call    cs:__imp_VariantClear
0x180005872  mov     eax, [r14+54h]
0x180005876  mov     r8, [rbp+ppvData]
0x18000587a  sub     eax, ebx
0x18000587c  dec     eax
0x18000587e  lea     rcx, [r8+rdi*8]; void *
0x180005882  lea     r9, [rax+rax*2]
0x180005886  shl     r9, 3
0x18000588a  lea     eax, [rbx+1]
0x18000588d  lea     rax, [rax+rax*2]
0x180005891  lea     rdx, [r8+rax*8]; Src
0x180005895  mov     r8, r9; Size
0x180005898  call    memmove_0
0x18000589d  dec     dword ptr [r14+54h]
0x1800058a1  mov     eax, [r14+54h]
0x1800058a5  xor     edx, edx
0x1800058a7  lea     r9, [rax+rax*2]
0x1800058ab  mov     rax, [rbp+ppvData]
0x1800058af  mov     [rax+r9*8], dx
0x1800058b4  lea     rcx, [r14+8]; this
0x1800058b8  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x1800058bd  test    esi, esi
0x1800058bf  jz      short loc_1800058DB
0x1800058c1  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x1800058c8  jz      short loc_1800058F7
0x1800058ca  mov     r9d, esi
0x1800058cd  lea     r8, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x1800058d4  call    McTemplateU0sq_EventWriteTransfer
0x1800058d9  jmp     short loc_1800058F7
0x1800058db  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x1800058e2  jz      short loc_1800058F7
0x1800058e4  lea     r8, aEnumeratorRemo_0; "Enumerator::RemoveNamed"
0x1800058eb  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x1800058f2  call    McTemplateU0s_EventWriteTransfer
0x1800058f7  cmp     [rbp+ppvData], 0
0x1800058fc  jz      short loc_180005908
0x1800058fe  mov     rcx, [r14+48h]; psa
0x180005902  call    cs:__imp_SafeArrayUnaccessData
0x180005908  mov     rbx, [rsp+40h+arg_8]
0x18000590d  mov     eax, esi
0x18000590f  add     rsp, 40h
0x180005913  pop     r15
0x180005915  pop     r14
0x180005917  pop     rdi
0x180005918  pop     rsi
0x180005919  pop     rbp
0x18000591a  retn
```
