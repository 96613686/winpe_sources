# Enumerator::Next(ulong,tagVARIANT *,ulong *)

- ea: `0x180005e30`
- end: `0x180005f8c`
- name: `?Next@Enumerator@@UEAAJKPEAUtagVARIANT@@PEAK@Z`
- size: `348`
- prototype: `__int64 __fastcall(SAFEARRAY **this, unsigned int, struct tagVARIANT *, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x18000331c`
- `0x1800037fc`
- `0x180003908`
- `0x180005e30`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180005f22`
- `OLEAUT32!__imp_VariantCopy` at `0x180005f22`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005ee6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005ee6`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005ec2`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005ec2`

## pseudocode

```c
__int64 __fastcall Enumerator::Next(SAFEARRAY **this, unsigned int a2, struct tagVARIANT *a3, unsigned int *a4)
{
  __int64 v4; // rsi
  __int64 v9; // rcx
  SAFEARRAY *v10; // rcx
  HRESULT v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // rcx
  bool v14; // zf
  void *ppvData; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  ppvData = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::Next");
  SDiagPrvSyncObject::Lock((SDiagPrvSyncObject *)(this + 1));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v9, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::Next");
  v10 = this[9];
  if ( v10 )
  {
    v11 = SafeArrayAccessData(v10, &ppvData);
    if ( v11 < 0 )
      goto LABEL_9;
    while ( *((_DWORD *)this + 20) < *((_DWORD *)this + 21) && (unsigned int)v4 < a2 )
    {
      SDiagPrviVariantInit(&a3[v4]);
      v11 = VariantCopy(&a3[v4], (const VARIANTARG *)ppvData + *((unsigned int *)this + 20));
      if ( v11 < 0 )
        goto LABEL_9;
      ++*((_DWORD *)this + 20);
      v4 = (unsigned int)(v4 + 1);
    }
  }
  else
  {
    v11 = 0;
  }
  if ( a4 )
    *a4 = v4;
LABEL_9:
  SDiagPrvSyncObject::Unlock((SDiagPrvSyncObject *)(this + 1));
  if ( ppvData )
  {
    SafeArrayUnaccessData(this[9]);
    ppvData = 0;
  }
  v14 = v11 == 0;
  if ( v11 >= 0 )
  {
    if ( a2 > (unsigned int)v4 )
    {
      v11 = 1;
      goto LABEL_21;
    }
    v14 = v11 == 0;
  }
  if ( !v14 )
  {
LABEL_21:
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0sq_EventWriteTransfer(v13, v12, "Enumerator::Next", (unsigned int)v11);
    return (unsigned int)v11;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
    McTemplateU0s_EventWriteTransfer(v13, SDIAGPRV_EVENT_DEBUG_SUCCESS, "Enumerator::Next");
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180005e30  mov     [rsp+arg_8], rbx
0x180005e35  mov     [rsp+arg_10], rbp
0x180005e3a  push    rsi
0x180005e3b  push    rdi
0x180005e3c  push    r12
0x180005e3e  push    r14
0x180005e40  push    r15
0x180005e42  sub     rsp, 20h
0x180005e46  xor     esi, esi
0x180005e48  mov     r14, r9
0x180005e4b  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, sil
0x180005e52  mov     r12, r8
0x180005e55  mov     r15d, edx
0x180005e58  mov     [rsp+48h+ppvData], rsi
0x180005e5d  mov     rdi, rcx
0x180005e60  jge     short loc_180005E75
0x180005e62  lea     r8, aEnumeratorNext; "Enumerator::Next"
0x180005e69  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x180005e70  call    McTemplateU0s_EventWriteTransfer
0x180005e75  lea     rcx, [rdi+8]; this
0x180005e79  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180005e7e  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, sil
0x180005e85  jge     short loc_180005E9A
0x180005e87  lea     r8, aEnumeratorNext; "Enumerator::Next"
0x180005e8e  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x180005e95  call    McTemplateU0s_EventWriteTransfer
0x180005e9a  mov     rcx, [rdi+48h]; psa
0x180005e9e  test    rcx, rcx
0x180005ea1  jnz     short loc_180005EE1
0x180005ea3  xor     ebx, ebx
0x180005ea5  test    r14, r14
0x180005ea8  jz      short loc_180005EAD
0x180005eaa  mov     [r14], esi
0x180005ead  lea     rcx, [rdi+8]; this
0x180005eb1  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180005eb6  cmp     [rsp+48h+ppvData], 0
0x180005ebc  jz      short loc_180005ED1
0x180005ebe  mov     rcx, [rdi+48h]; psa
0x180005ec2  call    cs:__imp_SafeArrayUnaccessData
0x180005ec8  mov     [rsp+48h+ppvData], 0
0x180005ed1  test    ebx, ebx
0x180005ed3  js      short loc_180005F3B
0x180005ed5  cmp     r15d, esi
0x180005ed8  jbe     short loc_180005F39
0x180005eda  mov     ebx, 1
0x180005edf  jmp     short loc_180005F3D
0x180005ee1  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180005ee6  call    cs:__imp_SafeArrayAccessData
0x180005eec  mov     ebx, eax
0x180005eee  test    eax, eax
0x180005ef0  js      short loc_180005EAD
0x180005ef2  mov     ecx, [rdi+54h]
0x180005ef5  cmp     [rdi+50h], ecx
0x180005ef8  jnb     short loc_180005EA5
0x180005efa  cmp     esi, r15d
0x180005efd  jnb     short loc_180005EA5
0x180005eff  lea     rcx, [rsi+rsi*2]
0x180005f03  lea     rbx, [r12+rcx*8]
0x180005f07  mov     rcx, rbx; struct tagVARIANT *
0x180005f0a  call    ?SDiagPrviVariantInit@@YAJPEAUtagVARIANT@@@Z; SDiagPrviVariantInit(tagVARIANT *)
0x180005f0f  mov     eax, [rdi+50h]
0x180005f12  mov     rcx, rbx; pvargDest
0x180005f15  lea     rdx, [rax+rax*2]
0x180005f19  mov     rax, [rsp+48h+ppvData]
0x180005f1e  lea     rdx, [rax+rdx*8]; pvargSrc
0x180005f22  call    cs:__imp_VariantCopy
0x180005f28  mov     ebx, eax
0x180005f2a  test    eax, eax
0x180005f2c  js      loc_180005EAD
0x180005f32  inc     dword ptr [rdi+50h]
0x180005f35  inc     esi
0x180005f37  jmp     short loc_180005EF2
0x180005f39  test    ebx, ebx
0x180005f3b  jz      short loc_180005F57
0x180005f3d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180005f44  jz      short loc_180005F73
0x180005f46  mov     r9d, ebx
0x180005f49  lea     r8, aEnumeratorNext; "Enumerator::Next"
0x180005f50  call    McTemplateU0sq_EventWriteTransfer
0x180005f55  jmp     short loc_180005F73
0x180005f57  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180005f5e  jz      short loc_180005F73
0x180005f60  lea     r8, aEnumeratorNext; "Enumerator::Next"
0x180005f67  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180005f6e  call    McTemplateU0s_EventWriteTransfer
0x180005f73  mov     rbp, [rsp+48h+arg_10]
0x180005f78  mov     eax, ebx
0x180005f7a  mov     rbx, [rsp+48h+arg_8]
0x180005f7f  add     rsp, 20h
0x180005f83  pop     r15
0x180005f85  pop     r14
0x180005f87  pop     r12
0x180005f89  pop     rdi
0x180005f8a  pop     rsi
0x180005f8b  retn
```
