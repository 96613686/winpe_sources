# ServiceDataSession::_UpdateSecurityFlagsForPrivacy(ulong,ulong)

- ea: `0x18000b620`
- end: `0x18000bb29`
- name: `?_UpdateSecurityFlagsForPrivacy@ServiceDataSession@@AEAAJKK@Z`
- size: `1289`
- prototype: `__int64 __fastcall(ServiceDataSession *__hidden this, unsigned int, unsigned int)`
- caller_count: `10`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800033c0`
- `0x180008870`
- `0x180009990`
- `0x180009a90`
- `0x18000a530`
- `0x18000c8e0`
- `0x18000d8b0`
- `0x1800201b0`
- `0x180030978`
- `0x180061110`

## callees

- `0x180008f0c`
- `0x18000b620`
- `0x1800a4dfc`
- `0x18012c7b0`
- `0x18012e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b65c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b65c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b77b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb1c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b726`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b77b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ba49`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000bb1c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b902`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b6af`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000b902`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000b984`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18000b984`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b915`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b695`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000b915`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b6e3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000b6e3`

## string_xrefs

- `0x18000b6f5`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000b9d7`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000ba83`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000bac8`: `onecoreuap\base\appmodel\userdataaccess\services\userdata\service\lib\datasession.cpp`
- `0x18000b68e`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18000b817`: `userDataTasks`
- `0x18000b822`: `userDataTasksSystem`

## pseudocode

```c
__int64 __fastcall ServiceDataSession::_UpdateSecurityFlagsForPrivacy(ServiceDataSession *this, int a2, int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  int v5; // r15d
  int ActivationFactory; // eax
  unsigned int v7; // edi
  __int64 v8; // rcx
  __int64 v9; // rcx
  unsigned int v10; // r12d
  int v11; // r14d
  const WCHAR *v12; // r15
  unsigned __int64 v13; // rdi
  __int64 v14; // r13
  int v15; // eax
  HRESULT v16; // eax
  int v17; // eax
  IUnknown *v18; // rcx
  __int64 v19; // rcx
  IUnknown *v21; // rcx
  __int64 v22; // rcx
  IUnknown *v23; // rcx
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *pProxy; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh]
  int v28; // [rsp+58h] [rbp-A8h]
  unsigned int v29; // [rsp+5Ch] [rbp-A4h]
  __int64 (__fastcall *v30)(__int64, _QWORD, HSTRING, _QWORD, int, IUnknown **); // [rsp+60h] [rbp-A0h]
  _DWORD v31[2]; // [rsp+70h] [rbp-90h]
  PCWSTR sourceString; // [rsp+78h] [rbp-88h]
  int v33; // [rsp+80h] [rbp-80h]
  const wchar_t *v34; // [rsp+88h] [rbp-78h]
  int v35; // [rsp+90h] [rbp-70h]
  const WCHAR *v36; // [rsp+98h] [rbp-68h]
  int v37; // [rsp+A0h] [rbp-60h]
  const wchar_t *v38; // [rsp+A8h] [rbp-58h]
  int v39; // [rsp+B0h] [rbp-50h]
  const WCHAR *v40; // [rsp+B8h] [rbp-48h]
  int v41; // [rsp+C0h] [rbp-40h]
  const wchar_t *v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+D0h] [rbp-30h]
  const wchar_t *v44; // [rsp+D8h] [rbp-28h]
  int v45; // [rsp+E0h] [rbp-20h]
  const wchar_t *v46; // [rsp+E8h] [rbp-18h]
  int v47; // [rsp+F0h] [rbp-10h]
  const wchar_t *v48; // [rsp+F8h] [rbp-8h]
  int v49; // [rsp+100h] [rbp+0h]
  const wchar_t *v50; // [rsp+108h] [rbp+8h]
  int v51; // [rsp+110h] [rbp+10h]
  const wchar_t *v52; // [rsp+118h] [rbp+18h]
  int v53; // [rsp+120h] [rbp+20h]
  const wchar_t *v54; // [rsp+128h] [rbp+28h]
  HSTRING string; // [rsp+130h] [rbp+30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+138h] [rbp+38h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1744);
  v27 = a3;
  v28 = a2;
  v5 = a3;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1744));
  if ( (*((_DWORD *)this + 447) & ~*((_DWORD *)this + 448) & v5) == 0 )
  {
LABEL_33:
    LeaveCriticalSection(v3);
    return 0;
  }
  v24 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Internal.CapabilityAccess.CapabilityAccess",
         0x32u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  ActivationFactory = RoGetActivationFactory(string, &GUID_518f3880_4e5c_4524_ab03_cd01336b2178, &v24);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    Log_HREvent(
      (unsigned int)ActivationFactory,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
      1860);
    v8 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_43;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SWATCS>::GetImpl'::`2'::impl)
    && *((_DWORD *)this + 470) )
  {
    v9 = v24;
    *((_DWORD *)this + 449) |= *((_DWORD *)this + 447) & 0x22082;
    if ( v9 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_33;
  }
  sourceString = L"appointments";
  v10 = 0;
  v34 = L"appointmentsSystem";
  v31[0] = 1;
  v36 = L"contacts";
  v38 = L"contactsSystem";
  v40 = L"chat";
  v42 = L"chatSystem";
  v44 = L"phoneCallHistory";
  v46 = L"phoneCallHistorySystem";
  v48 = L"email";
  v50 = L"emailSystem";
  v52 = L"userDataTasks";
  v54 = L"userDataTasksSystem";
  v33 = 4096;
  v35 = 2;
  v37 = 0x2000;
  v39 = 4;
  v41 = 0x4000;
  v43 = 16;
  v45 = 0x10000;
  v47 = 8;
  v49 = 0x8000;
  v51 = 128;
  v53 = 0x20000;
  while ( 1 )
  {
    v11 = v31[4 * v10];
    if ( (*((_DWORD *)this + 447) & v11 & v5) != 0 && (v11 & *((_DWORD *)this + 448)) == 0 )
      break;
LABEL_30:
    if ( ++v10 >= 0xC )
    {
      v19 = v24;
      if ( v24 )
      {
        v24 = 0;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v19 + 16LL))(v19, 0xFFFFFFFFLL);
      }
      goto LABEL_33;
    }
  }
  v12 = (&sourceString)[2 * v10];
  v13 = -1;
  pProxy = 0;
  v14 = v24;
  v30 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD, int, IUnknown **))(*(_QWORD *)v24 + 56LL);
  v29 = *((_DWORD *)this + 471);
  do
    ++v13;
  while ( v12[v13] );
  if ( v13 > 0xFFFFFFFF )
  {
    LODWORD(v13) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v12, v13, &hstringHeader, &string);
  v15 = v30(v14, 0, string, v29, v28, &pProxy);
  v7 = v15;
  if ( v15 >= 0 )
  {
    v16 = CoSetProxyBlanket(
            pProxy,
            0xFFFFFFFF,
            0xFFFFFFFF,
            (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
            0,
            3u,
            (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
            0x40u);
    v7 = v16;
    if ( v16 < 0 )
    {
      Log_HREvent(
        (unsigned int)v16,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        1921);
      v21 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v21->lpVtbl->Release)(v21);
      }
      v22 = v24;
      if ( v24 )
      {
        v24 = 0;
LABEL_42:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        goto LABEL_43;
      }
      goto LABEL_43;
    }
    v26 = 3;
    v17 = ((__int64 (__fastcall *)(IUnknown *, int *))pProxy->lpVtbl[6].AddRef)(pProxy, &v26);
    if ( v17 < 0 )
    {
      Log_HREvent(
        (unsigned int)v17,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
        1934);
    }
    else if ( v26 == 3 )
    {
      *((_DWORD *)this + 449) |= *((_DWORD *)this + 447) & v11;
LABEL_27:
      *((_DWORD *)this + 448) |= v11;
      v18 = pProxy;
      if ( pProxy )
      {
        pProxy = 0;
        ((void (__fastcall *)(IUnknown *))v18->lpVtbl->Release)(v18);
      }
      v5 = v27;
      goto LABEL_30;
    }
    *((_DWORD *)this + 449) &= ~v11;
    goto LABEL_27;
  }
  Log_HREvent(
    (unsigned int)v15,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\userdata\\service\\lib\\datasession.cpp",
    1910);
  v23 = pProxy;
  if ( pProxy )
  {
    pProxy = 0;
    ((void (__fastcall *)(IUnknown *))v23->lpVtbl->Release)(v23);
  }
  v22 = v24;
  if ( v24 )
  {
    v24 = 0;
    goto LABEL_42;
  }
LABEL_43:
  LeaveCriticalSection(v3);
  return v7;
}

```

## disassembly

```asm
0x18000b620  push    rbp
0x18000b622  push    rbx
0x18000b623  push    rsi
0x18000b624  push    rdi
0x18000b625  push    r13
0x18000b627  push    r15
0x18000b629  lea     rbp, [rsp-68h]
0x18000b62e  sub     rsp, 168h
0x18000b635  mov     rax, cs:__security_cookie
0x18000b63c  xor     rax, rsp
0x18000b63f  mov     [rbp+90h+var_40], rax
0x18000b643  lea     rbx, [rcx+6D0h]
0x18000b64a  mov     [rsp+190h+var_13C], r8d
0x18000b64f  mov     rsi, rcx
0x18000b652  mov     [rsp+190h+var_138], edx
0x18000b656  mov     rcx, rbx; lpCriticalSection
0x18000b659  mov     r15d, r8d
0x18000b65c  call    cs:__imp_EnterCriticalSection
0x18000b662  mov     eax, [rsi+700h]
0x18000b668  not     eax
0x18000b66a  and     eax, [rsi+6FCh]
0x18000b670  test    r15d, eax
0x18000b673  jz      loc_18000B778
0x18000b679  xor     r13d, r13d
0x18000b67c  lea     r9, [rbp+90h+string]; string
0x18000b680  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000b684  mov     [rsp+190h+var_150], r13
0x18000b689  mov     edx, 32h ; '2'; length
0x18000b68e  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18000b695  call    cs:__imp_WindowsCreateStringReference
0x18000b69b  test    eax, eax
0x18000b69d  jns     short loc_18000B6B5
0x18000b69f  xor     r9d, r9d; lpArguments
0x18000b6a2  xor     r8d, r8d; nNumberOfArguments
0x18000b6a5  mov     edx, 1; dwExceptionFlags
0x18000b6aa  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b6af  call    cs:__imp_RaiseException
0x18000b6b5  mov     rcx, [rsp+190h+var_150]
0x18000b6ba  mov     rdi, [rbp+90h+string]
0x18000b6be  test    rcx, rcx
0x18000b6c1  jz      short loc_18000B6D4
0x18000b6c3  mov     [rsp+190h+var_150], r13
0x18000b6c8  mov     rax, [rcx]
0x18000b6cb  mov     rax, [rax+10h]
0x18000b6cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d4  lea     r8, [rsp+190h+var_150]
0x18000b6d9  mov     rcx, rdi
0x18000b6dc  lea     rdx, _GUID_518f3880_4e5c_4524_ab03_cd01336b2178
0x18000b6e3  call    cs:__imp_RoGetActivationFactory
0x18000b6e9  mov     edi, eax
0x18000b6eb  test    eax, eax
0x18000b6ed  jns     short loc_18000B733
0x18000b6ef  mov     r9d, 744h
0x18000b6f5  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b6fc  mov     edx, 1
0x18000b701  mov     ecx, eax
0x18000b703  call    Log_HREvent
0x18000b708  mov     rcx, [rsp+190h+var_150]
0x18000b70d  test    rcx, rcx
0x18000b710  jz      short loc_18000B723
0x18000b712  mov     [rsp+190h+var_150], r13
0x18000b717  mov     rax, [rcx]
0x18000b71a  mov     rax, [rax+10h]
0x18000b71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b723  mov     rcx, rbx; lpCriticalSection
0x18000b726  call    cs:__imp_LeaveCriticalSection
0x18000b72c  mov     eax, edi
0x18000b72e  jmp     loc_18000BA61
0x18000b733  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SWATCS@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SWATCS@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS> `wil::Feature<__WilFeatureTraits_Feature_SWATCS>::GetImpl(void)'::`2'::impl
0x18000b73a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SWATCS@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SWATCS>::__private_IsEnabled(void)
0x18000b73f  test    al, al
0x18000b741  jz      short loc_18000B788
0x18000b743  cmp     [rsi+758h], r13d
0x18000b74a  jz      short loc_18000B788
0x18000b74c  mov     eax, [rsi+6FCh]
0x18000b752  mov     rcx, [rsp+190h+var_150]
0x18000b757  and     eax, 22082h
0x18000b75c  or      [rsi+704h], eax
0x18000b762  test    rcx, rcx
0x18000b765  jz      short loc_18000B778
0x18000b767  mov     [rsp+190h+var_150], r13
0x18000b76c  mov     rax, [rcx]
0x18000b76f  mov     rax, [rax+10h]
0x18000b773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b778  mov     rcx, rbx; lpCriticalSection
0x18000b77b  call    cs:__imp_LeaveCriticalSection
0x18000b781  xor     eax, eax
0x18000b783  jmp     loc_18000BA61
0x18000b788  lea     rax, aAppointments; "appointments"
0x18000b78f  mov     [rsp+190h+arg_10], r12
0x18000b797  mov     [rsp+190h+sourceString], rax
0x18000b79c  mov     r12d, r13d
0x18000b79f  lea     rax, aAppointmentssy; "appointmentsSystem"
0x18000b7a6  mov     [rsp+190h+var_30], r14
0x18000b7ae  mov     [rbp+90h+var_108], rax
0x18000b7b2  mov     edx, 0FFFFFFFFh
0x18000b7b7  lea     rax, aContacts; "contacts"
0x18000b7be  mov     [rsp+190h+var_120], 1
0x18000b7c6  mov     [rbp+90h+var_F8], rax
0x18000b7ca  lea     rax, aContactssystem; "contactsSystem"
0x18000b7d1  mov     [rbp+90h+var_E8], rax
0x18000b7d5  lea     rax, aChat; "chat"
0x18000b7dc  mov     [rbp+90h+var_D8], rax
0x18000b7e0  lea     rax, aChatsystem; "chatSystem"
0x18000b7e7  mov     [rbp+90h+var_C8], rax
0x18000b7eb  lea     rax, aPhonecallhisto_0; "phoneCallHistory"
0x18000b7f2  mov     [rbp+90h+var_B8], rax
0x18000b7f6  lea     rax, aPhonecallhisto; "phoneCallHistorySystem"
0x18000b7fd  mov     [rbp+90h+var_A8], rax
0x18000b801  lea     rax, aEmail_0; "email"
0x18000b808  mov     [rbp+90h+var_98], rax
0x18000b80c  lea     rax, aEmailsystem; "emailSystem"
0x18000b813  mov     [rbp+90h+var_88], rax
0x18000b817  lea     rax, aUserdatatasks; "userDataTasks"
0x18000b81e  mov     [rbp+90h+var_78], rax
0x18000b822  lea     rax, aUserdatataskss; "userDataTasksSystem"
0x18000b829  mov     [rbp+90h+var_68], rax
0x18000b82d  mov     [rbp+90h+var_110], 1000h
0x18000b834  mov     [rbp+90h+var_100], 2
0x18000b83b  mov     [rbp+90h+var_F0], 2000h
0x18000b842  mov     [rbp+90h+var_E0], 4
0x18000b849  mov     [rbp+90h+var_D0], 4000h
0x18000b850  mov     [rbp+90h+var_C0], 10h
0x18000b857  mov     [rbp+90h+var_B0], 10000h
0x18000b85e  mov     [rbp+90h+var_A0], 8
0x18000b865  mov     [rbp+90h+var_90], 8000h
0x18000b86c  mov     [rbp+90h+var_80], 80h
0x18000b873  mov     [rbp+90h+var_70], 20000h
0x18000b87a  nop     word ptr [rax+rax+00h]
0x18000b880  mov     ecx, r12d
0x18000b883  add     rcx, rcx
0x18000b886  mov     r14d, [rsp+rcx*8+190h+var_120]
0x18000b88b  mov     eax, r14d
0x18000b88e  and     eax, [rsi+6FCh]
0x18000b894  test    r15d, eax
0x18000b897  jz      loc_18000BA1E
0x18000b89d  test    [rsi+700h], r14d
0x18000b8a4  jnz     loc_18000BA1E
0x18000b8aa  mov     r15, [rsp+rcx*8+190h+sourceString]
0x18000b8af  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000b8b6  mov     [rsp+190h+pProxy], r13
0x18000b8bb  mov     r13, [rsp+190h+var_150]
0x18000b8c0  mov     rax, [r13+0]
0x18000b8c4  mov     rax, [rax+38h]
0x18000b8c8  mov     [rsp+190h+var_130], rax
0x18000b8cd  mov     eax, [rsi+75Ch]
0x18000b8d3  mov     [rsp+190h+var_134], eax
0x18000b8d7  nop     word ptr [rax+rax+00000000h]
0x18000b8e0  inc     rdi
0x18000b8e3  cmp     word ptr [r15+rdi*2], 0
0x18000b8e9  jnz     short loc_18000B8E0
0x18000b8eb  cmp     rdi, rdx
0x18000b8ee  jbe     short loc_18000B908
0x18000b8f0  mov     edi, edx
0x18000b8f2  xor     r9d, r9d; lpArguments
0x18000b8f5  mov     edx, 1; dwExceptionFlags
0x18000b8fa  xor     r8d, r8d; nNumberOfArguments
0x18000b8fd  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000b902  call    cs:__imp_RaiseException
0x18000b908  lea     r9, [rbp+90h+string]; string
0x18000b90c  mov     edx, edi; length
0x18000b90e  lea     r8, [rbp+90h+hstringHeader]; hstringHeader
0x18000b912  mov     rcx, r15; sourceString
0x18000b915  call    cs:__imp_WindowsCreateStringReference
0x18000b91b  mov     r9d, [rsp+190h+var_134]
0x18000b920  lea     rax, [rsp+190h+pProxy]
0x18000b925  mov     r8, [rbp+90h+string]
0x18000b929  xor     edx, edx
0x18000b92b  mov     qword ptr [rsp+190h+dwImpLevel], rax
0x18000b930  mov     rcx, r13
0x18000b933  mov     eax, [rsp+190h+var_138]
0x18000b937  mov     [rsp+190h+dwAuthnLevel], eax
0x18000b93b  mov     rax, [rsp+190h+var_130]
0x18000b940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b945  mov     edi, eax
0x18000b947  test    eax, eax
0x18000b949  js      loc_18000BAC2
0x18000b94f  mov     rcx, [rsp+190h+pProxy]; pProxy
0x18000b954  mov     edx, 0FFFFFFFFh; dwAuthnSvc
0x18000b959  mov     [rsp+190h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18000b961  xor     r13d, r13d
0x18000b964  mov     [rsp+190h+pAuthInfo], 0FFFFFFFFFFFFFFFFh; pAuthInfo
0x18000b96d  mov     r8d, edx; dwAuthzSvc
0x18000b970  mov     [rsp+190h+dwImpLevel], 3; dwImpLevel
0x18000b978  mov     r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18000b97f  mov     [rsp+190h+dwAuthnLevel], r13d; dwAuthnLevel
0x18000b984  call    cs:__imp_CoSetProxyBlanket
0x18000b98a  mov     edi, eax
0x18000b98c  test    eax, eax
0x18000b98e  js      loc_18000BA7D
0x18000b994  mov     rcx, [rsp+190h+pProxy]
0x18000b999  lea     rdx, [rsp+190h+var_140]
0x18000b99e  mov     [rsp+190h+var_140], 3
0x18000b9a6  mov     rax, [rcx]
0x18000b9a9  mov     rax, [rax+98h]
0x18000b9b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9b5  test    eax, eax
0x18000b9b7  js      short loc_18000B9D1
0x18000b9b9  cmp     [rsp+190h+var_140], 3
0x18000b9be  jnz     short loc_18000B9E7
0x18000b9c0  mov     eax, r14d
0x18000b9c3  and     eax, [rsi+6FCh]
0x18000b9c9  or      [rsi+704h], eax
0x18000b9cf  jmp     short loc_18000B9F2
0x18000b9d1  mov     r9d, 78Eh
0x18000b9d7  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000b9de  xor     edx, edx
0x18000b9e0  mov     ecx, eax
0x18000b9e2  call    Log_HREvent
0x18000b9e7  mov     eax, r14d
0x18000b9ea  not     eax
0x18000b9ec  and     [rsi+704h], eax
0x18000b9f2  or      [rsi+700h], r14d
0x18000b9f9  mov     rcx, [rsp+190h+pProxy]
0x18000b9fe  test    rcx, rcx
0x18000ba01  jz      short loc_18000BA14
0x18000ba03  mov     [rsp+190h+pProxy], r13
0x18000ba08  mov     rax, [rcx]
0x18000ba0b  mov     rax, [rax+10h]
0x18000ba0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba14  mov     r15d, [rsp+190h+var_13C]
0x18000ba19  mov     edx, 0FFFFFFFFh
0x18000ba1e  inc     r12d
0x18000ba21  cmp     r12d, 0Ch
0x18000ba25  jb      loc_18000B880
0x18000ba2b  mov     rcx, [rsp+190h+var_150]
0x18000ba30  test    rcx, rcx
0x18000ba33  jz      short loc_18000BA46
0x18000ba35  mov     [rsp+190h+var_150], r13
0x18000ba3a  mov     rax, [rcx]
0x18000ba3d  mov     rax, [rax+10h]
0x18000ba41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba46  mov     rcx, rbx; lpCriticalSection
0x18000ba49  call    cs:__imp_LeaveCriticalSection
0x18000ba4f  xor     eax, eax
0x18000ba51  mov     r12, [rsp+190h+arg_10]
0x18000ba59  mov     r14, [rsp+190h+var_30]
0x18000ba61  mov     rcx, [rbp+90h+var_40]
0x18000ba65  xor     rcx, rsp; StackCookie
0x18000ba68  call    __security_check_cookie
0x18000ba6d  add     rsp, 168h
0x18000ba74  pop     r15
0x18000ba76  pop     r13
0x18000ba78  pop     rdi
0x18000ba79  pop     rsi
0x18000ba7a  pop     rbx
0x18000ba7b  pop     rbp
0x18000ba7c  retn
0x18000ba7d  mov     r9d, 781h
0x18000ba83  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ba8a  mov     edx, 1
0x18000ba8f  mov     ecx, edi
0x18000ba91  call    Log_HREvent
0x18000ba96  mov     rcx, [rsp+190h+pProxy]
0x18000ba9b  test    rcx, rcx
0x18000ba9e  jz      short loc_18000BAB1
0x18000baa0  mov     [rsp+190h+pProxy], r13
0x18000baa5  mov     rax, [rcx]
0x18000baa8  mov     rax, [rax+10h]
0x18000baac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab1  mov     rcx, [rsp+190h+var_150]
0x18000bab6  test    rcx, rcx
0x18000bab9  jz      short loc_18000BB19
0x18000babb  mov     [rsp+190h+var_150], r13
0x18000bac0  jmp     short loc_18000BB0D
0x18000bac2  mov     r9d, 776h
0x18000bac8  lea     r8, aOnecoreuapBase_62; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bacf  mov     edx, 1
0x18000bad4  mov     ecx, edi
0x18000bad6  call    Log_HREvent
0x18000badb  mov     rcx, [rsp+190h+pProxy]
0x18000bae0  test    rcx, rcx
0x18000bae3  jz      short loc_18000BAFA
0x18000bae5  mov     [rsp+190h+pProxy], 0
0x18000baee  mov     rax, [rcx]
0x18000baf1  mov     rax, [rax+10h]
0x18000baf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bafa  mov     rcx, [rsp+190h+var_150]
0x18000baff  test    rcx, rcx
0x18000bb02  jz      short loc_18000BB19
0x18000bb04  mov     [rsp+190h+var_150], 0
0x18000bb0d  mov     rax, [rcx]
0x18000bb10  mov     rax, [rax+10h]
0x18000bb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb19  mov     rcx, rbx; lpCriticalSection
0x18000bb1c  call    cs:__imp_LeaveCriticalSection
0x18000bb22  mov     eax, edi
0x18000bb24  jmp     loc_18000BA51
```
