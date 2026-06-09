# CClassFactory::CreateInstance(IUnknown *,_GUID const &,void * *)

- ea: `0x180002240`
- end: `0x1800023a4`
- name: `?CreateInstance@CClassFactory@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `356`
- prototype: `__int64 __fastcall(CClassFactory *__hidden this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002240`
- `0x1800024d4`
- `0x180002550`
- `0x1800025ec`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022f0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800022d7`

## string_xrefs

- `0x180002278`: `CClassFactory::CreateInstance`
- `0x180002309`: `CClassFactory::CreateInstance`
- `0x180002353`: `CClassFactory::CreateInstance`
- `0x180002379`: `CClassFactory::CreateInstance`

## pseudocode

```c
__int64 __fastcall CClassFactory::CreateInstance(
        CClassFactory *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  __int64 v5; // rdi
  CClassFactory *v7; // r9
  unsigned int v8; // ebx
  struct _SDIAGPRV_OBJECT near **i; // rbx
  __int64 v10; // rax
  unsigned int v11; // eax

  v5 = 0;
  v7 = this;
  if ( a4 )
  {
    *a4 = 0;
    if ( a2 )
    {
      v8 = -2147221232;
LABEL_23:
      if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
        McTemplateU0sq_EventWriteTransfer(this, a2, "CClassFactory::CreateInstance", v8);
      goto LABEL_25;
    }
    for ( i = &g_SDiagPrvObjects; ; i += 3 )
    {
      if ( !i[2] )
      {
        v8 = -2147467262;
        goto LABEL_23;
      }
      this = *i;
      v10 = *(_QWORD *)((char *)v7 + 12) - *(_QWORD *)*i;
      if ( !v10 )
        v10 = *(_QWORD *)((char *)v7 + 20) - *((_QWORD *)this + 1);
      if ( !v10 )
        break;
    }
    EnterCriticalSection(&g_cs);
    v5 = ((__int64 (*)(void))i[2])();
    LeaveCriticalSection(&g_cs);
    if ( v5 )
    {
      v11 = (**(__int64 (__fastcall ***)(__int64, const struct _GUID *, void **))v5)(v5, a3, a4);
      v8 = v11;
      if ( v11 != -2147024882 )
      {
        if ( v11 == -2147024809 )
          goto LABEL_3;
        if ( !v11 )
        {
          if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x100) != 0 )
            McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_SUCCESS, "CClassFactory::CreateInstance");
          goto LABEL_26;
        }
        goto LABEL_23;
      }
    }
    else
    {
      v8 = -2147024882;
    }
    if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
      McTemplateU0s_EventWriteTransfer(this, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY, "CClassFactory::CreateInstance");
    goto LABEL_25;
  }
  v8 = -2147024809;
LABEL_3:
  if ( (Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits & 0x200) != 0 )
    McTemplateU0sqs_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)"CClassFactory::CreateInstance",
      -2147024809,
      (__int64)"ppv");
LABEL_25:
  if ( v5 )
LABEL_26:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v8;
}

```

## disassembly

```asm
0x180002240  push    rbx
0x180002242  push    rbp
0x180002243  push    rsi
0x180002244  push    rdi
0x180002245  sub     rsp, 38h
0x180002249  mov     rsi, r9
0x18000224c  xor     edi, edi
0x18000224e  mov     rbp, r8
0x180002251  mov     r9, rcx
0x180002254  test    rsi, rsi
0x180002257  jnz     short loc_18000228E
0x180002259  mov     ebx, 80070057h
0x18000225e  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180002265  jz      loc_180002385
0x18000226b  lea     rax, aPpv; "ppv"
0x180002272  mov     r9d, 80070057h
0x180002278  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x18000227f  mov     [rsp+58h+var_38], rax
0x180002284  call    McTemplateU0sqs_EventWriteTransfer
0x180002289  jmp     loc_180002385
0x18000228e  mov     [rsi], rdi
0x180002291  test    rdx, rdx
0x180002294  jz      short loc_1800022A0
0x180002296  mov     ebx, 80040110h
0x18000229b  jmp     loc_18000236D
0x1800022a0  lea     rbx, ?g_SDiagPrvObjects@@3PAU_SDIAGPRV_OBJECT@@A; _SDIAGPRV_OBJECT near * g_SDiagPrvObjects
0x1800022a7  cmp     [rbx+10h], rdi
0x1800022ab  jz      loc_180002368
0x1800022b1  mov     rcx, [rbx]
0x1800022b4  mov     rax, [r9+0Ch]
0x1800022b8  sub     rax, [rcx]
0x1800022bb  jnz     short loc_1800022C5
0x1800022bd  mov     rax, [r9+14h]
0x1800022c1  sub     rax, [rcx+8]
0x1800022c5  test    rax, rax
0x1800022c8  jz      short loc_1800022D0
0x1800022ca  add     rbx, 18h
0x1800022ce  jmp     short loc_1800022A7
0x1800022d0  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800022d7  call    cs:__imp_EnterCriticalSection
0x1800022dd  mov     rax, [rbx+10h]
0x1800022e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800022e6  lea     rcx, ?g_cs@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800022ed  mov     rdi, rax
0x1800022f0  call    cs:__imp_LeaveCriticalSection
0x1800022f6  test    rdi, rdi
0x1800022f9  jnz     short loc_18000231E
0x1800022fb  mov     ebx, 8007000Eh
0x180002300  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180002307  jz      short loc_180002385
0x180002309  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x180002310  lea     rdx, SDIAGPRV_EVENT_DEBUG_OUTOFMEMORY
0x180002317  call    McTemplateU0s_EventWriteTransfer
0x18000231c  jmp     short loc_180002385
0x18000231e  mov     rax, [rdi]
0x180002321  mov     r8, rsi
0x180002324  mov     rdx, rbp
0x180002327  mov     rcx, rdi
0x18000232a  mov     rax, [rax]
0x18000232d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002332  mov     ebx, eax
0x180002334  cmp     eax, 8007000Eh
0x180002339  jz      short loc_180002300
0x18000233b  cmp     eax, 80070057h
0x180002340  jz      loc_18000225E
0x180002346  test    eax, eax
0x180002348  jnz     short loc_18000236D
0x18000234a  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 1
0x180002351  jz      short loc_18000238A
0x180002353  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x18000235a  lea     rdx, SDIAGPRV_EVENT_DEBUG_SUCCESS
0x180002361  call    McTemplateU0s_EventWriteTransfer
0x180002366  jmp     short loc_18000238A
0x180002368  mov     ebx, 80004002h
0x18000236d  test    byte ptr cs:Microsoft_Windows_Diagnosis_ScriptedDiagnosticsProviderEnableBits+1, 2
0x180002374  jz      short loc_180002385
0x180002376  mov     r9d, ebx
0x180002379  lea     r8, aCclassfactoryC; "CClassFactory::CreateInstance"
0x180002380  call    McTemplateU0sq_EventWriteTransfer
0x180002385  test    rdi, rdi
0x180002388  jz      short loc_180002399
0x18000238a  mov     rax, [rdi]
0x18000238d  mov     rcx, rdi
0x180002390  mov     rax, [rax+10h]
0x180002394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002399  mov     eax, ebx
0x18000239b  add     rsp, 38h
0x18000239f  pop     rdi
0x1800023a0  pop     rsi
0x1800023a1  pop     rbp
0x1800023a2  pop     rbx
0x1800023a3  retn
```
