# CWmiEventSinkAvFw::Indicate(long,IWbemClassObject * *)

- ea: `0x180038b20`
- end: `0x180039411`
- name: `?Indicate@CWmiEventSinkAvFw@@UEAAJJPEAPEAUIWbemClassObject@@@Z`
- size: `2289`
- prototype: `__int64 __fastcall(CWmiEventSinkAvFw *__hidden this, int, struct IWbemClassObject **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180002e30`
- `0x180018b60`
- `0x18001c6dc`
- `0x18001fdd8`
- `0x18001fe40`
- `0x180020018`
- `0x1800281c4`
- `0x1800371ec`
- `0x180038b20`
- `0x18003fbfe`
- `0x180042010`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x180038cf8`
- `ntdll!EtwEventWrite` at `0x180038dbc`
- `ntdll!EtwEventWrite` at `0x180038e74`
- `ntdll!EtwEventWrite` at `0x180038f4b`
- `ntdll!EtwEventWrite` at `0x180039000`
- `ntdll!EtwEventWrite` at `0x1800390b8`
- `ntdll!EtwEventWrite` at `0x18003918f`
- `ntdll!EtwEventWrite` at `0x180039244`
- `ntdll!EtwEventWrite` at `0x1800392fc`
- `ntdll!EtwEventWrite` at `0x180038cf8`
- `ntdll!EtwEventWrite` at `0x180038dbc`
- `ntdll!EtwEventWrite` at `0x180038e74`
- `ntdll!EtwEventWrite` at `0x180038f4b`
- `ntdll!EtwEventWrite` at `0x180039000`
- `ntdll!EtwEventWrite` at `0x1800390b8`
- `ntdll!EtwEventWrite` at `0x18003918f`
- `ntdll!EtwEventWrite` at `0x180039244`
- `ntdll!EtwEventWrite` at `0x1800392fc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800393ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800393ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038bb2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038bb2`
- `OLEAUT32!__imp_VariantInit` at `0x180038b56`
- `OLEAUT32!__imp_VariantInit` at `0x180038b79`
- `OLEAUT32!__imp_VariantInit` at `0x180038b9c`
- `OLEAUT32!__imp_VariantInit` at `0x180038b56`
- `OLEAUT32!__imp_VariantInit` at `0x180038b79`
- `OLEAUT32!__imp_VariantInit` at `0x180038b9c`
- `OLEAUT32!__imp_VariantClear` at `0x180039388`
- `OLEAUT32!__imp_VariantClear` at `0x1800393c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800393d1`
- `OLEAUT32!__imp_VariantClear` at `0x180039388`
- `OLEAUT32!__imp_VariantClear` at `0x1800393c3`
- `OLEAUT32!__imp_VariantClear` at `0x1800393d1`

## pseudocode

```c
__int64 __fastcall CWmiEventSinkAvFw::Indicate(CWmiEventSinkAvFw *this, int a2, struct IWbemClassObject **a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  int v7; // r14d
  const wchar_t *bstrVal; // rdi
  const wchar_t *v9; // rdi
  struct _RTL_CRITICAL_SECTION *v10; // rdi
  int IsAlerted; // eax
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  int v13; // eax
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  int v15; // eax
  const wchar_t *v16; // rdi
  struct _RTL_CRITICAL_SECTION *v17; // rdi
  int v18; // eax
  struct _RTL_CRITICAL_SECTION *v19; // rdi
  int v20; // eax
  struct _RTL_CRITICAL_SECTION *v21; // rdi
  int v22; // eax
  const wchar_t *v23; // rdi
  struct _RTL_CRITICAL_SECTION *v24; // rdi
  int v25; // eax
  struct _RTL_CRITICAL_SECTION *v26; // rdi
  int v27; // eax
  struct _RTL_CRITICAL_SECTION *v28; // rdi
  int v29; // eax
  struct CExternalBase *v31; // [rsp+40h] [rbp-B8h] BYREF
  struct CExternalBase *v32; // [rsp+48h] [rbp-B0h] BYREF
  struct CExternalBase *v33; // [rsp+50h] [rbp-A8h] BYREF
  struct CExternalBase *v34; // [rsp+58h] [rbp-A0h] BYREF
  struct CExternalBase *v35; // [rsp+60h] [rbp-98h] BYREF
  struct CExternalBase *v36; // [rsp+68h] [rbp-90h] BYREF
  struct CExternalBase *v37; // [rsp+70h] [rbp-88h] BYREF
  struct CExternalBase *v38; // [rsp+78h] [rbp-80h] BYREF
  VARIANTARG v39; // [rsp+80h] [rbp-78h] BYREF
  struct _RTL_CRITICAL_SECTION *v40; // [rsp+98h] [rbp-60h]
  VARIANTARG pvarg; // [rsp+A0h] [rbp-58h] BYREF
  VARIANTARG v42; // [rsp+B8h] [rbp-40h] BYREF
  __int64 *v43; // [rsp+100h] [rbp+8h] BYREF
  struct CExternalBase *v44; // [rsp+118h] [rbp+20h] BYREF

  memset(&v42, 0, sizeof(v42));
  VariantInit(&v42);
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  memset(&v39, 0, sizeof(v39));
  VariantInit(&v39);
  v6 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  v40 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 40);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( *((_QWORD *)this + 4) )
  {
    v7 = 0;
    while ( v7 < a2 )
    {
      try
      {
        if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *))a3[v7]->lpVtbl->Get)(a3[v7], L"__Class") >= 0 )
        {
          if ( ((int (__fastcall *)(struct IWbemClassObject *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))a3[v7]->lpVtbl->Get)(
                 a3[v7],
                 L"TargetInstance",
                 0,
                 &pvarg,
                 0,
                 0) >= 0 )
          {
            v43 = 0;
            if ( (**(int (__fastcall ***)(LONGLONG, GUID *, __int64 **))pvarg.llVal)(
                   pvarg.llVal,
                   &IID_IWbemClassObject,
                   &v43) >= 0 )
            {
              if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*v43 + 32))(
                     v43,
                     L"__Class",
                     0,
                     &v39,
                     0,
                     0) >= 0 )
              {
                bstrVal = v42.bstrVal;
                if ( !wcscmp_0(v42.bstrVal, L"__InstanceCreationEvent") )
                {
                  v9 = v39.bstrVal;
                  if ( !wcscmp_0(v39.bstrVal, L"AntiVirusProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AV_WMI_Change, 0, 0);
                    v44 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 1),
                                0,
                                v43,
                                &v44,
                                0) >= 0 )
                    {
                      CThirdPartyManager::AddExternalProduct(*((CThirdPartyManager **)this + 1), v44);
                      v10 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      IsAlerted = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 1));
                      CAlertStatus::SetComponentAlerted(v10, 1u, IsAlerted);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v44 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v44)(v44, 1);
                      v44 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v9, L"FirewallProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_FW_WMI_Change, 0, 0);
                    v31 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 2),
                                1u,
                                v43,
                                &v31,
                                0) >= 0 )
                    {
                      CThirdPartyManager::AddExternalProduct(*((CThirdPartyManager **)this + 2), v31);
                      v12 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v13 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 2));
                      CAlertStatus::SetComponentAlerted(v12, 2u, v13);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v31 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v31)(v31, 1);
                      v31 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v9, L"AntiSpywareProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AS_WMI_Change, 0, 0);
                    v32 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 3),
                                2u,
                                v43,
                                &v32,
                                0) >= 0 )
                    {
                      CThirdPartyManager::AddExternalProduct(*((CThirdPartyManager **)this + 3), v32);
                      v14 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v15 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 3));
                      CAlertStatus::SetComponentAlerted(v14, 8u, v15);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v32 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v32)(v32, 1);
                      v32 = 0;
                    }
                  }
                }
                else if ( !wcscmp_0(bstrVal, L"__InstanceModificationEvent") )
                {
                  v16 = v39.bstrVal;
                  if ( !wcscmp_0(v39.bstrVal, L"AntiVirusProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AV_WMI_Change, 0, 0);
                    v33 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 1),
                                0,
                                v43,
                                &v33,
                                0) >= 0 )
                    {
                      CThirdPartyManager::UpdateExternalProduct(*((CThirdPartyManager **)this + 1), v33);
                      v17 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v18 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 1));
                      CAlertStatus::SetComponentAlerted(v17, 1u, v18);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v33 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v33)(v33, 1);
                      v33 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v16, L"FirewallProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_FW_WMI_Change, 0, 0);
                    v34 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 2),
                                1u,
                                v43,
                                &v34,
                                0) >= 0 )
                    {
                      CThirdPartyManager::UpdateExternalProduct(*((CThirdPartyManager **)this + 2), v34);
                      v19 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v20 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 2));
                      CAlertStatus::SetComponentAlerted(v19, 2u, v20);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v34 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v34)(v34, 1);
                      v34 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v16, L"AntiSpywareProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AS_WMI_Change, 0, 0);
                    v35 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 3),
                                2u,
                                v43,
                                &v35,
                                0) >= 0 )
                    {
                      CThirdPartyManager::UpdateExternalProduct(*((CThirdPartyManager **)this + 3), v35);
                      v21 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v22 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 3));
                      CAlertStatus::SetComponentAlerted(v21, 8u, v22);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v35 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v35)(v35, 1);
                      v35 = 0;
                    }
                  }
                }
                else if ( !wcscmp_0(bstrVal, L"__InstanceDeletionEvent") )
                {
                  v23 = v39.bstrVal;
                  if ( !wcscmp_0(v39.bstrVal, L"AntiVirusProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AV_WMI_Change, 0, 0);
                    v36 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 1),
                                0,
                                v43,
                                &v36,
                                0) >= 0 )
                    {
                      CThirdPartyManager::RemoveExternalProduct(*((CThirdPartyManager **)this + 1), v36);
                      v24 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v25 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 1));
                      CAlertStatus::SetComponentAlerted(v24, 1u, v25);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v36 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v36)(v36, 1);
                      v36 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v23, L"FirewallProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_FW_WMI_Change, 0, 0);
                    v37 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 2),
                                1u,
                                v43,
                                &v37,
                                0) >= 0 )
                    {
                      CThirdPartyManager::RemoveExternalProduct(*((CThirdPartyManager **)this + 2), v37);
                      v26 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v27 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 2));
                      CAlertStatus::SetComponentAlerted(v26, 2u, v27);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v37 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v37)(v37, 1);
                      v37 = 0;
                    }
                  }
                  else if ( !wcscmp_0(v23, L"AntiSpywareProduct") )
                  {
                    EtwEventWrite(g_Provider, WSC_SVC_AS_WMI_Change, 0, 0);
                    v38 = 0;
                    if ( (int)CThirdPartyManager::CreateExternalBaseFromWbemProduct(
                                *((CSecurityVerificationManager ***)this + 3),
                                2u,
                                v43,
                                &v38,
                                0) >= 0 )
                    {
                      CThirdPartyManager::RemoveExternalProduct(*((CThirdPartyManager **)this + 3), v38);
                      v28 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 4);
                      v29 = CThirdPartyManager::IsAlerted(*((CThirdPartyManager **)this + 3));
                      CAlertStatus::SetComponentAlerted(v28, 8u, v29);
                      CAlertStatus::FireNotificationEvents(*((LPCRITICAL_SECTION *)this + 4), 0);
                      if ( v38 )
                        (**(void (__fastcall ***)(struct CExternalBase *, __int64))v38)(v38, 1);
                      v38 = 0;
                    }
                  }
                }
                VariantClear(&v39);
                SqmHelper::SetThirdPartyStatus(
                  *((struct CAntiVirusManager **)this + 1),
                  *((struct CAntiSpywareManager **)this + 3),
                  *((struct CFirewallManager **)this + 2));
              }
              (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
              v43 = 0;
            }
            VariantClear(&pvarg);
          }
          VariantClear(&v42);
        }
        ++v7;
      }
      catch ( ... )
      {
        v6 = v40;
        break;
      }
    }
  }
  LeaveCriticalSection(v6);
  return 0;
}

```

## disassembly

```asm
0x180038b20  mov     r11, rsp
0x180038b23  mov     [r11+10h], rbx
0x180038b27  mov     [r11+18h], rsi
0x180038b2b  push    rdi
0x180038b2c  push    r12
0x180038b2e  push    r13
0x180038b30  push    r14
0x180038b32  push    r15
0x180038b34  sub     rsp, 0D0h
0x180038b3b  mov     r12, r8
0x180038b3e  mov     r15d, edx
0x180038b41  mov     rbx, rcx
0x180038b44  xorps   xmm0, xmm0
0x180038b47  xor     eax, eax
0x180038b49  movups  xmmword ptr [r11-40h], xmm0
0x180038b4e  mov     [r11-30h], rax
0x180038b52  lea     rcx, [r11-40h]; pvarg
0x180038b56  call    cs:__imp_VariantInit
0x180038b5c  xorps   xmm0, xmm0
0x180038b5f  xor     eax, eax
0x180038b61  movups  xmmword ptr [rsp+0F8h+pvarg], xmm0
0x180038b69  mov     qword ptr [rsp+0F8h+pvarg+10h], rax
0x180038b71  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x180038b79  call    cs:__imp_VariantInit
0x180038b7f  xorps   xmm0, xmm0
0x180038b82  xor     eax, eax
0x180038b84  movups  xmmword ptr [rsp+0F8h+var_78], xmm0
0x180038b8c  mov     qword ptr [rsp+0F8h+var_78+10h], rax
0x180038b94  lea     rcx, [rsp+0F8h+var_78]; pvarg
0x180038b9c  call    cs:__imp_VariantInit
0x180038ba2  nop
0x180038ba3  lea     rsi, [rbx+28h]
0x180038ba7  mov     [rsp+0F8h+var_60], rsi
0x180038baf  mov     rcx, rsi; lpCriticalSection
0x180038bb2  call    cs:__imp_EnterCriticalSection
0x180038bb8  xor     r13d, r13d
0x180038bbb  cmp     [rbx+20h], r13
0x180038bbf  jz      loc_1800393DF
0x180038bc5  mov     r14d, r13d
0x180038bc8  cmp     r14d, r15d
0x180038bcb  jge     loc_1800393DF
0x180038bd1  movsxd  rdi, r14d
0x180038bd4  mov     rcx, [r12+rdi*8]
0x180038bd8  mov     rax, [rcx]
0x180038bdb  mov     [rsp+0F8h+var_D0], r13
0x180038be0  mov     [rsp+0F8h+var_D8], r13
0x180038be5  lea     r9, [rsp+0F8h+var_40]
0x180038bed  xor     r8d, r8d
0x180038bf0  lea     rdx, aClass_0; "__Class"
0x180038bf7  mov     rax, [rax+20h]
0x180038bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c00  test    eax, eax
0x180038c02  js      loc_1800393D7
0x180038c08  mov     rcx, [r12+rdi*8]
0x180038c0c  mov     rax, [rcx]
0x180038c0f  mov     [rsp+0F8h+var_D0], r13
0x180038c14  mov     [rsp+0F8h+var_D8], r13
0x180038c19  lea     r9, [rsp+0F8h+pvarg]
0x180038c21  xor     r8d, r8d
0x180038c24  lea     rdx, aTargetinstance; "TargetInstance"
0x180038c2b  mov     rax, [rax+20h]
0x180038c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c34  test    eax, eax
0x180038c36  js      loc_1800393C9
0x180038c3c  mov     [rsp+0F8h+arg_0], r13
0x180038c44  mov     rcx, qword ptr [rsp+0F8h+pvarg+8]
0x180038c4c  mov     rax, [rcx]
0x180038c4f  lea     r8, [rsp+0F8h+arg_0]
0x180038c57  lea     rdx, IID_IWbemClassObject
0x180038c5e  mov     rax, [rax]
0x180038c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c66  test    eax, eax
0x180038c68  js      loc_1800393BB
0x180038c6e  mov     rcx, [rsp+0F8h+arg_0]
0x180038c76  mov     rax, [rcx]
0x180038c79  mov     [rsp+0F8h+var_D0], r13
0x180038c7e  mov     [rsp+0F8h+var_D8], r13
0x180038c83  lea     r9, [rsp+0F8h+var_78]
0x180038c8b  xor     r8d, r8d
0x180038c8e  lea     rdx, aClass_0; "__Class"
0x180038c95  mov     rax, [rax+20h]
0x180038c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c9e  test    eax, eax
0x180038ca0  js      loc_18003939F
0x180038ca6  lea     rdx, aInstancecreati; "__InstanceCreationEvent"
0x180038cad  mov     rdi, qword ptr [rsp+0F8h+var_40+8]
0x180038cb5  mov     rcx, rdi; String1
0x180038cb8  call    wcscmp_0
0x180038cbd  test    eax, eax
0x180038cbf  jnz     loc_180038F01
0x180038cc5  lea     rdx, aAntivirusprodu; "AntiVirusProduct"
0x180038ccc  mov     rdi, qword ptr [rsp+0F8h+var_78+8]
0x180038cd4  mov     rcx, rdi; String1
0x180038cd7  call    wcscmp_0
0x180038cdc  test    eax, eax
0x180038cde  jnz     loc_180038D91
0x180038ce4  xor     r9d, r9d
0x180038ce7  xor     r8d, r8d
0x180038cea  lea     rdx, WSC_SVC_AV_WMI_Change
0x180038cf1  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180038cf8  call    cs:__imp_EtwEventWrite
0x180038cfe  mov     [rsp+0F8h+arg_18], r13
0x180038d06  mov     [rsp+0F8h+var_D8], r13; __int64
0x180038d0b  lea     r9, [rsp+0F8h+arg_18]
0x180038d13  mov     r8, [rsp+0F8h+arg_0]
0x180038d1b  xor     edx, edx; enum _SECURITY_PRODUCT_TYPE
0x180038d1d  mov     rcx, [rbx+8]; this
0x180038d21  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x180038d26  test    eax, eax
0x180038d28  js      loc_180039380
0x180038d2e  mov     rdx, [rsp+0F8h+arg_18]; struct CExternalBase *
0x180038d36  mov     rcx, [rbx+8]; this
0x180038d3a  call    ?AddExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::AddExternalProduct(CExternalBase *)
0x180038d3f  mov     rdi, [rbx+20h]
0x180038d43  mov     rcx, [rbx+8]; this
0x180038d47  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180038d4c  mov     r8d, eax; int
0x180038d4f  mov     edx, 1; unsigned int
0x180038d54  mov     rcx, rdi; lpCriticalSection
0x180038d57  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180038d5c  xor     edx, edx; int
0x180038d5e  mov     rcx, [rbx+20h]; lpCriticalSection
0x180038d62  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180038d67  mov     rcx, [rsp+0F8h+arg_18]
0x180038d6f  test    rcx, rcx
0x180038d72  jz      short loc_180038D84
0x180038d74  mov     rax, [rcx]
0x180038d77  mov     edx, 1
0x180038d7c  mov     rax, [rax]
0x180038d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038d84  mov     [rsp+0F8h+arg_18], r13
0x180038d8c  jmp     loc_180039380
0x180038d91  lea     rdx, aFirewallproduc_1; "FirewallProduct"
0x180038d98  mov     rcx, rdi; String1
0x180038d9b  call    wcscmp_0
0x180038da0  test    eax, eax
0x180038da2  jnz     loc_180038E49
0x180038da8  xor     r9d, r9d
0x180038dab  xor     r8d, r8d
0x180038dae  lea     rdx, WSC_SVC_FW_WMI_Change
0x180038db5  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180038dbc  call    cs:__imp_EtwEventWrite
0x180038dc2  mov     [rsp+0F8h+var_B8], r13
0x180038dc7  mov     [rsp+0F8h+var_D8], r13; __int64
0x180038dcc  lea     r9, [rsp+0F8h+var_B8]
0x180038dd1  mov     r8, [rsp+0F8h+arg_0]
0x180038dd9  mov     edx, 1; enum _SECURITY_PRODUCT_TYPE
0x180038dde  mov     rcx, [rbx+10h]; this
0x180038de2  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x180038de7  test    eax, eax
0x180038de9  js      loc_180039380
0x180038def  mov     rdx, [rsp+0F8h+var_B8]; struct CExternalBase *
0x180038df4  mov     rcx, [rbx+10h]; this
0x180038df8  call    ?AddExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::AddExternalProduct(CExternalBase *)
0x180038dfd  mov     rdi, [rbx+20h]
0x180038e01  mov     rcx, [rbx+10h]; this
0x180038e05  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180038e0a  mov     r8d, eax; int
0x180038e0d  mov     edx, 2; unsigned int
0x180038e12  mov     rcx, rdi; lpCriticalSection
0x180038e15  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180038e1a  xor     edx, edx; int
0x180038e1c  mov     rcx, [rbx+20h]; lpCriticalSection
0x180038e20  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180038e25  mov     rcx, [rsp+0F8h+var_B8]
0x180038e2a  test    rcx, rcx
0x180038e2d  jz      short loc_180038E3F
0x180038e2f  mov     rax, [rcx]
0x180038e32  mov     edx, 1
0x180038e37  mov     rax, [rax]
0x180038e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038e3f  mov     [rsp+0F8h+var_B8], r13
0x180038e44  jmp     loc_180039380
0x180038e49  lea     rdx, aAntispywarepro; "AntiSpywareProduct"
0x180038e50  mov     rcx, rdi; String1
0x180038e53  call    wcscmp_0
0x180038e58  test    eax, eax
0x180038e5a  jnz     loc_180039380
0x180038e60  xor     r9d, r9d
0x180038e63  xor     r8d, r8d
0x180038e66  lea     rdx, WSC_SVC_AS_WMI_Change
0x180038e6d  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180038e74  call    cs:__imp_EtwEventWrite
0x180038e7a  mov     [rsp+0F8h+var_B0], r13
0x180038e7f  mov     [rsp+0F8h+var_D8], r13; __int64
0x180038e84  lea     r9, [rsp+0F8h+var_B0]
0x180038e89  mov     r8, [rsp+0F8h+arg_0]
0x180038e91  mov     edx, 2; enum _SECURITY_PRODUCT_TYPE
0x180038e96  mov     rcx, [rbx+18h]; this
0x180038e9a  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x180038e9f  test    eax, eax
0x180038ea1  js      loc_180039380
0x180038ea7  mov     rdx, [rsp+0F8h+var_B0]; struct CExternalBase *
0x180038eac  mov     rcx, [rbx+18h]; this
0x180038eb0  call    ?AddExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::AddExternalProduct(CExternalBase *)
0x180038eb5  mov     rdi, [rbx+20h]
0x180038eb9  mov     rcx, [rbx+18h]; this
0x180038ebd  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180038ec2  mov     r8d, eax; int
0x180038ec5  mov     edx, 8; unsigned int
0x180038eca  mov     rcx, rdi; lpCriticalSection
0x180038ecd  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180038ed2  xor     edx, edx; int
0x180038ed4  mov     rcx, [rbx+20h]; lpCriticalSection
0x180038ed8  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180038edd  mov     rcx, [rsp+0F8h+var_B0]
0x180038ee2  test    rcx, rcx
0x180038ee5  jz      short loc_180038EF7
0x180038ee7  mov     rax, [rcx]
0x180038eea  mov     edx, 1
0x180038eef  mov     rax, [rax]
0x180038ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ef7  mov     [rsp+0F8h+var_B0], r13
0x180038efc  jmp     loc_180039380
0x180038f01  lea     rdx, aInstancemodifi; "__InstanceModificationEvent"
0x180038f08  mov     rcx, rdi; String1
0x180038f0b  call    wcscmp_0
0x180038f10  test    eax, eax
0x180038f12  jnz     loc_180039145
0x180038f18  lea     rdx, aAntivirusprodu; "AntiVirusProduct"
0x180038f1f  mov     rdi, qword ptr [rsp+0F8h+var_78+8]
0x180038f27  mov     rcx, rdi; String1
0x180038f2a  call    wcscmp_0
0x180038f2f  test    eax, eax
0x180038f31  jnz     loc_180038FD5
0x180038f37  xor     r9d, r9d
0x180038f3a  xor     r8d, r8d
0x180038f3d  lea     rdx, WSC_SVC_AV_WMI_Change
0x180038f44  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180038f4b  call    cs:__imp_EtwEventWrite
0x180038f51  mov     [rsp+0F8h+var_A8], r13
0x180038f56  mov     [rsp+0F8h+var_D8], r13; __int64
0x180038f5b  lea     r9, [rsp+0F8h+var_A8]
0x180038f60  mov     r8, [rsp+0F8h+arg_0]
0x180038f68  xor     edx, edx; enum _SECURITY_PRODUCT_TYPE
0x180038f6a  mov     rcx, [rbx+8]; this
0x180038f6e  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x180038f73  test    eax, eax
0x180038f75  js      loc_180039380
0x180038f7b  mov     rdx, [rsp+0F8h+var_A8]; struct CExternalBase *
0x180038f80  mov     rcx, [rbx+8]; this
0x180038f84  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x180038f89  mov     rdi, [rbx+20h]
0x180038f8d  mov     rcx, [rbx+8]; this
0x180038f91  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x180038f96  mov     r8d, eax; int
0x180038f99  mov     edx, 1; unsigned int
0x180038f9e  mov     rcx, rdi; lpCriticalSection
0x180038fa1  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x180038fa6  xor     edx, edx; int
0x180038fa8  mov     rcx, [rbx+20h]; lpCriticalSection
0x180038fac  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180038fb1  mov     rcx, [rsp+0F8h+var_A8]
0x180038fb6  test    rcx, rcx
0x180038fb9  jz      short loc_180038FCB
0x180038fbb  mov     rax, [rcx]
0x180038fbe  mov     edx, 1
0x180038fc3  mov     rax, [rax]
0x180038fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038fcb  mov     [rsp+0F8h+var_A8], r13
0x180038fd0  jmp     loc_180039380
0x180038fd5  lea     rdx, aFirewallproduc_1; "FirewallProduct"
0x180038fdc  mov     rcx, rdi; String1
0x180038fdf  call    wcscmp_0
0x180038fe4  test    eax, eax
0x180038fe6  jnz     loc_18003908D
0x180038fec  xor     r9d, r9d
0x180038fef  xor     r8d, r8d
0x180038ff2  lea     rdx, WSC_SVC_FW_WMI_Change
0x180038ff9  mov     rcx, cs:?g_Provider@@3_KA; unsigned __int64 g_Provider
0x180039000  call    cs:__imp_EtwEventWrite
0x180039006  mov     [rsp+0F8h+var_A0], r13
0x18003900b  mov     [rsp+0F8h+var_D8], r13; __int64
0x180039010  lea     r9, [rsp+0F8h+var_A0]
0x180039015  mov     r8, [rsp+0F8h+arg_0]
0x18003901d  mov     edx, 1; enum _SECURITY_PRODUCT_TYPE
0x180039022  mov     rcx, [rbx+10h]; this
0x180039026  call    ?CreateExternalBaseFromWbemProduct@CThirdPartyManager@@QEAAJW4_SECURITY_PRODUCT_TYPE@@PEAUIWbemClassObject@@PEAPEAVCExternalBase@@PEAV?$CList@PEAGPEAG@@@Z; CThirdPartyManager::CreateExternalBaseFromWbemProduct(_SECURITY_PRODUCT_TYPE,IWbemClassObject *,CExternalBase * *,CList<ushort *,ushort *> *)
0x18003902b  test    eax, eax
0x18003902d  js      loc_180039380
0x180039033  mov     rdx, [rsp+0F8h+var_A0]; struct CExternalBase *
0x180039038  mov     rcx, [rbx+10h]; this
0x18003903c  call    ?UpdateExternalProduct@CThirdPartyManager@@QEAAJPEAVCExternalBase@@@Z; CThirdPartyManager::UpdateExternalProduct(CExternalBase *)
0x180039041  mov     rdi, [rbx+20h]
0x180039045  mov     rcx, [rbx+10h]; this
0x180039049  call    ?IsAlerted@CThirdPartyManager@@QEAAHXZ; CThirdPartyManager::IsAlerted(void)
0x18003904e  mov     r8d, eax; int
0x180039051  mov     edx, 2; unsigned int
0x180039056  mov     rcx, rdi; lpCriticalSection
0x180039059  call    ?SetComponentAlerted@CAlertStatus@@QEAAJKH@Z; CAlertStatus::SetComponentAlerted(ulong,int)
0x18003905e  xor     edx, edx; int
0x180039060  mov     rcx, [rbx+20h]; lpCriticalSection
0x180039064  call    ?FireNotificationEvents@CAlertStatus@@QEAAXH@Z; CAlertStatus::FireNotificationEvents(int)
0x180039069  mov     rcx, [rsp+0F8h+var_A0]
0x18003906e  test    rcx, rcx
0x180039071  jz      short loc_180039083
0x180039073  mov     rax, [rcx]
0x180039076  mov     edx, 1
0x18003907b  mov     rax, [rax]
0x18003907e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
