# Enumerator::Add(tagVARIANT *,long *)

- ea: `0x180005af8`
- end: `0x180005c74`
- name: `?Add@Enumerator@@QEAAJPEAUtagVARIANT@@PEAJ@Z`
- size: `380`
- prototype: `__int64 __fastcall(Enumerator *this, struct tagVARIANT *, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800046b0`
- `0x180010938`
- `0x18001114c`

## callees

- `0x1800024d4`
- `0x180002550`
- `0x1800037fc`
- `0x180003908`
- `0x180005af8`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180005bc6`
- `OLEAUT32!__imp_VariantCopy` at `0x180005bc6`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005c0d`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180005c0d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005ba7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x180005ba7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005c5b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x180005c5b`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180005b8c`
- `OLEAUT32!__imp_SafeArrayRedim` at `0x180005b8c`

## pseudocode

```c
__int64 __fastcall Enumerator::Add(Enumerator *this, struct tagVARIANT *a2, int *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  SAFEARRAY **v7; // rbx
  SAFEARRAY *v8; // rcx
  HRESULT v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  SAFEARRAY *v12; // rax
  __int64 *v13; // rdx
  void *ppvData; // [rsp+50h] [rbp+8h] BYREF
  SAFEARRAYBOUND psaboundNew; // [rsp+60h] [rbp+18h] BYREF

  ppvData = 0;
  psaboundNew = 0;
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START, "Enumerator::Add");
  SDiagPrvSyncObject::Lock((Enumerator *)((char *)this + 8));
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(v5, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END, "Enumerator::Add");
  v6 = *((_DWORD *)this + 22);
  v7 = (SAFEARRAY **)((char *)this + 72);
  if ( *((_DWORD *)this + 21) >= v6 )
  {
    v8 = *v7;
    psaboundNew.lLbound = 0;
    psaboundNew.cElements = v6 + 32;
    if ( v8 )
    {
      v9 = SafeArrayRedim(v8, &psaboundNew);
      if ( v9 < 0 )
        goto LABEL_12;
    }
    else
    {
      v12 = SafeArrayCreate(0xCu, 1u, &psaboundNew);
      *v7 = v12;
      if ( !v12 )
      {
        v9 = -2147024882;
        goto LABEL_12;
      }
    }
    *((_DWORD *)this + 22) = psaboundNew.cElements;
  }
  v9 = SafeArrayAccessData(*v7, &ppvData);
  if ( v9 >= 0 )
  {
    v9 = VariantCopy((VARIANTARG *)ppvData + *((unsigned int *)this + 21), a2);
    if ( v9 >= 0 )
      ++*((_DWORD *)this + 21);
  }
LABEL_12:
  SDiagPrvSyncObject::Unlock((Enumerator *)((char *)this + 8));
  if ( v9 == -2147024882 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) == 0 )
      goto LABEL_23;
    v13 = SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY;
    goto LABEL_22;
  }
  if ( !v9 )
  {
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) == 0 )
      goto LABEL_23;
    v13 = SDIAGPRV_EVENT_DEBUG_SUCCESS;
LABEL_22:
    McTemplateU0s_EventWriteTransfer(v11, v13, "Enumerator::Add");
    goto LABEL_23;
  }
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sq_EventWriteTransfer(v11, v10, "Enumerator::Add", (unsigned int)v9);
LABEL_23:
  if ( ppvData )
    SafeArrayUnaccessData(*v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180005af8  mov     rax, rsp
0x180005afb  mov     [rax+10h], rbx
0x180005aff  mov     [rax+18h], r8
0x180005b03  push    rbp
0x180005b04  push    rsi
0x180005b05  push    rdi
0x180005b06  push    r12
0x180005b08  push    r14
0x180005b0a  sub     rsp, 20h
0x180005b0e  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180005b15  lea     r12, aEnumeratorAdd; "Enumerator::Add"
0x180005b1c  mov     r14, rdx
0x180005b1f  mov     qword ptr [rax+8], 0
0x180005b27  mov     rsi, rcx
0x180005b2a  mov     qword ptr [rax+18h], 0
0x180005b32  jge     short loc_180005B43
0x180005b34  mov     r8, r12
0x180005b37  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_START
0x180005b3e  call    McTemplateU0s_EventWriteTransfer
0x180005b43  lea     rcx, [rsi+8]; this
0x180005b47  call    ?Lock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Lock(void)
0x180005b4c  cmp     byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits, 0
0x180005b53  jge     short loc_180005B64
0x180005b55  mov     r8, r12
0x180005b58  lea     rdx, SDIAGPRV_EVENT_PERF_ACQUIRE_LOCK_END
0x180005b5f  call    McTemplateU0s_EventWriteTransfer
0x180005b64  mov     eax, [rsi+58h]
0x180005b67  lea     rbx, [rsi+48h]
0x180005b6b  cmp     [rsi+54h], eax
0x180005b6e  jb      short loc_180005B9F
0x180005b70  mov     rcx, [rbx]; psa
0x180005b73  add     eax, 20h ; ' '
0x180005b76  mov     [rsp+48h+psaboundNew.lLbound], 0
0x180005b7e  mov     [rsp+48h+psaboundNew.cElements], eax
0x180005b82  test    rcx, rcx
0x180005b85  jz      short loc_180005C00
0x180005b87  lea     rdx, [rsp+48h+psaboundNew]; psaboundNew
0x180005b8c  call    cs:__imp_SafeArrayRedim
0x180005b92  mov     edi, eax
0x180005b94  test    eax, eax
0x180005b96  js      short loc_180005BD5
0x180005b98  mov     eax, [rsp+48h+psaboundNew.cElements]
0x180005b9c  mov     [rsi+58h], eax
0x180005b9f  mov     rcx, [rbx]; psa
0x180005ba2  lea     rdx, [rsp+48h+ppvData]; ppvData
0x180005ba7  call    cs:__imp_SafeArrayAccessData
0x180005bad  mov     edi, eax
0x180005baf  test    eax, eax
0x180005bb1  js      short loc_180005BD5
0x180005bb3  mov     eax, [rsi+54h]
0x180005bb6  mov     rdx, r14; pvargSrc
0x180005bb9  lea     rcx, [rax+rax*2]
0x180005bbd  mov     rax, [rsp+48h+ppvData]
0x180005bc2  lea     rcx, [rax+rcx*8]; pvargDest
0x180005bc6  call    cs:__imp_VariantCopy
0x180005bcc  mov     edi, eax
0x180005bce  test    eax, eax
0x180005bd0  js      short loc_180005BD5
0x180005bd2  inc     dword ptr [rsi+54h]
0x180005bd5  lea     rcx, [rsi+8]; this
0x180005bd9  call    ?Unlock@SDiagPrvSyncObject@@IEAAXXZ; SDiagPrvSyncObject::Unlock(void)
0x180005bde  cmp     edi, 8007000Eh
0x180005be4  jz      short loc_180005C38
0x180005be6  test    edi, edi
0x180005be8  jz      short loc_180005C26
0x180005bea  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180005bf1  jz      short loc_180005C50
0x180005bf3  mov     r9d, edi
0x180005bf6  mov     r8, r12
0x180005bf9  call    McTemplateU0sq_EventWriteTransfer
0x180005bfe  jmp     short loc_180005C50
0x180005c00  mov     ecx, 0Ch; vt
0x180005c05  lea     r8, [rsp+48h+psaboundNew]; rgsabound
0x180005c0a  lea     edx, [rcx-0Bh]; cDims
0x180005c0d  call    cs:__imp_SafeArrayCreate
0x180005c13  mov     [rbx], rax
0x180005c16  test    rax, rax
0x180005c19  jnz     loc_180005B98
0x180005c1f  mov     edi, 8007000Eh
0x180005c24  jmp     short loc_180005BD5
0x180005c26  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180005c2d  jz      short loc_180005C50
0x180005c2f  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180005c36  jmp     short loc_180005C48
0x180005c38  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180005c3f  jz      short loc_180005C50
0x180005c41  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180005c48  mov     r8, r12
0x180005c4b  call    McTemplateU0s_EventWriteTransfer
0x180005c50  cmp     [rsp+48h+ppvData], 0
0x180005c56  jz      short loc_180005C61
0x180005c58  mov     rcx, [rbx]; psa
0x180005c5b  call    cs:__imp_SafeArrayUnaccessData
0x180005c61  mov     rbx, [rsp+48h+arg_8]
0x180005c66  mov     eax, edi
0x180005c68  add     rsp, 20h
0x180005c6c  pop     r14
0x180005c6e  pop     r12
0x180005c70  pop     rdi
0x180005c71  pop     rsi
0x180005c72  pop     rbp
0x180005c73  retn
```
