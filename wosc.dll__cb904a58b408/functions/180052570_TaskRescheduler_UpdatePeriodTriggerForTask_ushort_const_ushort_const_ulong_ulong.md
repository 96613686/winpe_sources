# TaskRescheduler::UpdatePeriodTriggerForTask(ushort const *,ushort const *,ulong,ulong)

- ea: `0x180052570`
- end: `0x180052b91`
- name: `?UpdatePeriodTriggerForTask@TaskRescheduler@@SAXPEBG0KK@Z`
- size: `1569`
- prototype: `static void(const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024188`

## callees

- `0x180009fcc`
- `0x180010130`
- `0x1800101fc`
- `0x18005235c`
- `0x18005238c`
- `0x18005242c`
- `0x180052570`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800525c4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800525c4`
- `OLEAUT32!__imp_VariantInit` at `0x1800525f1`
- `OLEAUT32!__imp_VariantInit` at `0x1800525f1`
- `OLEAUT32!__imp_VariantClear` at `0x180052b60`
- `OLEAUT32!__imp_VariantClear` at `0x180052b60`

## string_xrefs

- `0x180052709`: `RefreshCache`
- `0x180052ab8`: `RefreshCache`
- `0x1800525d9`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x180052695`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800526e0`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x180052728`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x18005276c`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800527ad`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800527ee`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x18005281e`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800528d2`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800528e7`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x180052913`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x18005296a`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800529ba`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x1800529f4`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`
- `0x180052ada`: `onecore\base\flighting\common\taskutils\taskrescheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
void __fastcall TaskRescheduler::UpdatePeriodTriggerForTask(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        unsigned int a4)
{
  char v6; // di
  HRESULT Instance; // eax
  int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rax
  int v16; // eax
  int v17; // eax
  int v18; // edx
  struct ITrigger *v19; // rcx
  int v20; // eax
  int i; // esi
  __int64 v22; // r14
  __int64 (__fastcall *v23)(__int64, _QWORD, struct ITrigger **); // r15
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  int v29; // eax
  const char *v30; // r9
  __int64 v31; // rax
  int v32; // eax
  int ppv; // [rsp+20h] [rbp-148h]
  struct ITrigger *v34; // [rsp+50h] [rbp-118h] BYREF
  __int64 v35; // [rsp+58h] [rbp-110h] BYREF
  __int64 *v36; // [rsp+60h] [rbp-108h] BYREF
  __int64 *v37; // [rsp+68h] [rbp-100h] BYREF
  __int64 v38; // [rsp+70h] [rbp-F8h] BYREF
  __int64 *v39; // [rsp+78h] [rbp-F0h] BYREF
  __int64 *v40; // [rsp+80h] [rbp-E8h] BYREF
  __int64 v41; // [rsp+88h] [rbp-E0h] BYREF
  __int64 v42[2]; // [rsp+90h] [rbp-D8h] BYREF
  VARIANTARG v43; // [rsp+A0h] [rbp-C8h] BYREF
  VARIANTARG pvarg; // [rsp+C0h] [rbp-A8h] BYREF
  VARIANTARG v45; // [rsp+E0h] [rbp-88h] BYREF
  VARIANTARG v46; // [rsp+100h] [rbp-68h] BYREF
  VARIANTARG v47; // [rsp+120h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+0h]
  const unsigned __int16 *v49; // [rsp+170h] [rbp+8h] BYREF
  const unsigned __int16 *v50; // [rsp+178h] [rbp+10h] BYREF

  v50 = a2;
  v49 = a1;
  v40 = 0;
  v6 = 1;
  Instance = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, (LPVOID *)&v40);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  VariantInit(&pvarg);
  v43 = pvarg;
  v45 = pvarg;
  v46 = pvarg;
  v47 = pvarg;
  v8 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*v40 + 80))(
         v40,
         &v47,
         &v46,
         &v45);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v8,
      (int)&v43);
  v37 = 0;
  v9 = *v40;
  v37 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v9 + 56))(
          v40,
          L"\\Microsoft\\Windows\\Flighting\\OneSettings",
          &v37);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v10,
      (int)&v43);
  v39 = 0;
  v11 = *v37;
  v39 = 0;
  v12 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v11 + 104))(v37, L"RefreshCache", &v39);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x18,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v12,
      (int)&v43);
  v36 = 0;
  v13 = *v39;
  v36 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(v13 + 152))(v39, &v36);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v14,
      (int)&v43);
  v35 = 0;
  v15 = *v36;
  v35 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v15 + 72))(v36, &v35);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v16,
      (int)&v43);
  LODWORD(v50) = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 **))(*(_QWORD *)v35 + 56LL))(v35, &v50);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v17,
      (int)&v43);
  v18 = (int)v50;
  if ( !(_DWORD)v50 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x23,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v43);
  v19 = 0;
  v34 = 0;
  v20 = 0;
  LODWORD(v49) = 0;
  for ( i = 1; i <= v18; ++i )
  {
    v22 = v35;
    v23 = *(__int64 (__fastcall **)(__int64, _QWORD, struct ITrigger **))(*(_QWORD *)v35 + 64LL);
    v34 = 0;
    if ( v19 )
      ((void (__fastcall *)(struct ITrigger *, struct ITriggerVtbl *))v19->lpVtbl->Release)(v19, v19->lpVtbl);
    v24 = v23(v22, (unsigned int)i, &v34);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v24,
        (int)&v43);
    v25 = ((__int64 (__fastcall *)(struct ITrigger *, const unsigned __int16 **))v34->lpVtbl->get_Type)(v34, &v49);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
        (const char *)(unsigned int)v25,
        (int)&v43);
    v20 = (int)v49;
    if ( (_DWORD)v49 == 1 )
      goto LABEL_28;
    v18 = (int)v50;
    v19 = v34;
  }
  if ( v20 != 1 )
    goto LABEL_29;
LABEL_28:
  v6 = 0;
LABEL_29:
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)0x8000FFFFLL,
      (int)&v43);
  wil::com_ptr_t<ITrigger,wil::err_exception_policy>::query<ITimeTrigger>(
    (__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *))&v34,
    v42);
  v38 = 0;
  v26 = *(_QWORD *)v42[0];
  v38 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(v26 + 80))(v42[0], &v38);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v27,
      (int)&v43);
  memset(&v43, 0, sizeof(v43));
  v28 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
          &v43,
          L"PT%dM",
          a3);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v28,
      (int)&v43);
  v29 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v38 + 64LL))(v38, *(_QWORD *)&v43.vt);
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v29,
      (int)&v43);
  try
  {
    TaskRescheduler::AdjustNextRunTime(v34, a4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      v30);
  }
  v41 = 0;
  v31 = *v37;
  v41 = 0;
  v47 = pvarg;
  v46 = pvarg;
  v45 = pvarg;
  v32 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v31 + 136))(v37, L"RefreshCache", v36);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecore\\base\\flighting\\common\\taskutils\\taskrescheduler.cpp",
      (const char *)(unsigned int)v32,
      (int)&v45);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v41);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v43);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v38);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(v42);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v34);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(&v35);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v36);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v39);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v37);
  VariantClear(&pvarg);
  wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>((__int64 *)&v40);
}

```

## disassembly

```asm
0x180052570  mov     rax, rsp
0x180052573  mov     [rax+18h], rbx
0x180052577  mov     [rax+20h], rsi
0x18005257b  mov     [rax+10h], rdx
0x18005257f  mov     [rax+8], rcx
0x180052583  push    rdi
0x180052584  push    r12
0x180052586  push    r13
0x180052588  push    r14
0x18005258a  push    r15
0x18005258c  sub     rsp, 140h
0x180052593  mov     r12d, r9d
0x180052596  mov     r13d, r8d
0x180052599  xor     ebx, ebx
0x18005259b  mov     [rax-0E8h], rbx
0x1800525a2  lea     rax, [rax-0E8h]
0x1800525a9  mov     [rsp+168h+ppv], rax; int
0x1800525ae  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x1800525b5  lea     edi, [rbx+1]
0x1800525b8  mov     r8d, edi; dwClsContext
0x1800525bb  xor     edx, edx; pUnkOuter
0x1800525bd  lea     rcx, CLSID_TaskScheduler; rclsid
0x1800525c4  call    cs:__imp_CoCreateInstance
0x1800525ca  mov     rcx, [rsp+168h]; this
0x1800525d2  test    eax, eax
0x1800525d4  jns     short loc_1800525E9
0x1800525d6  mov     r9d, eax; char *
0x1800525d9  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800525e0  lea     edx, [rbx+0Eh]; void *
0x1800525e3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800525e9  lea     rcx, [rsp+168h+pvarg]; pvarg
0x1800525f1  call    cs:__imp_VariantInit
0x1800525f7  nop
0x1800525f8  mov     rcx, [rsp+168h+var_E8]
0x180052600  movups  xmm1, xmmword ptr [rsp+168h+pvarg]
0x180052608  movsd   xmm0, qword ptr [rsp+168h+pvarg+10h]
0x180052611  movaps  xmmword ptr [rsp+168h+var_C8], xmm1
0x180052619  movsd   [rsp+168h+var_B8], xmm0
0x180052622  movaps  xmmword ptr [rsp+168h+var_88], xmm1
0x18005262a  movsd   [rsp+168h+var_78], xmm0
0x180052633  movaps  [rsp+168h+var_68], xmm1
0x18005263b  movsd   [rsp+168h+var_58], xmm0
0x180052644  movaps  [rsp+168h+var_48], xmm1
0x18005264c  movsd   [rsp+168h+var_38], xmm0
0x180052655  mov     rax, [rcx]
0x180052658  lea     rdx, [rsp+168h+var_C8]
0x180052660  mov     [rsp+168h+ppv], rdx; int
0x180052665  lea     r9, [rsp+168h+var_88]
0x18005266d  lea     r8, [rsp+168h+var_68]
0x180052675  lea     rdx, [rsp+168h+var_48]
0x18005267d  mov     rax, [rax+50h]
0x180052681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052686  mov     rcx, [rsp+168h]; this
0x18005268e  test    eax, eax
0x180052690  jns     short loc_1800526A7
0x180052692  mov     r9d, eax; char *
0x180052695  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x18005269c  mov     edx, 11h; void *
0x1800526a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800526a7  mov     [rsp+168h+var_100], rbx
0x1800526ac  mov     rcx, [rsp+168h+var_E8]
0x1800526b4  mov     rax, [rcx]
0x1800526b7  mov     [rsp+168h+var_100], rbx
0x1800526bc  lea     r8, [rsp+168h+var_100]
0x1800526c1  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\Flighting\\OneSet"...
0x1800526c8  mov     rax, [rax+38h]
0x1800526cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800526d1  mov     rcx, [rsp+168h]; this
0x1800526d9  test    eax, eax
0x1800526db  jns     short loc_1800526F2
0x1800526dd  mov     r9d, eax; char *
0x1800526e0  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800526e7  mov     edx, 15h; void *
0x1800526ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800526f2  mov     [rsp+168h+var_F0], rbx
0x1800526f7  mov     rcx, [rsp+168h+var_100]
0x1800526fc  mov     rax, [rcx]
0x1800526ff  mov     [rsp+168h+var_F0], rbx
0x180052704  lea     r8, [rsp+168h+var_F0]
0x180052709  lea     rdx, aRefreshcache; "RefreshCache"
0x180052710  mov     rax, [rax+68h]
0x180052714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052719  mov     rcx, [rsp+168h]; this
0x180052721  test    eax, eax
0x180052723  jns     short loc_18005273A
0x180052725  mov     r9d, eax; char *
0x180052728  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x18005272f  mov     edx, 18h; void *
0x180052734  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005273a  mov     [rsp+168h+var_108], rbx
0x18005273f  mov     rcx, [rsp+168h+var_F0]
0x180052744  mov     rax, [rcx]
0x180052747  mov     [rsp+168h+var_108], rbx
0x18005274c  lea     rdx, [rsp+168h+var_108]
0x180052751  mov     rax, [rax+98h]
0x180052758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005275d  mov     rcx, [rsp+168h]; this
0x180052765  test    eax, eax
0x180052767  jns     short loc_18005277E
0x180052769  mov     r9d, eax; char *
0x18005276c  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x180052773  mov     edx, 1Bh; void *
0x180052778  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005277e  mov     [rsp+168h+var_110], rbx
0x180052783  mov     rcx, [rsp+168h+var_108]
0x180052788  mov     rax, [rcx]
0x18005278b  mov     [rsp+168h+var_110], rbx
0x180052790  lea     rdx, [rsp+168h+var_110]
0x180052795  mov     rax, [rax+48h]
0x180052799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005279e  mov     rcx, [rsp+168h]; this
0x1800527a6  test    eax, eax
0x1800527a8  jns     short loc_1800527BF
0x1800527aa  mov     r9d, eax; char *
0x1800527ad  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800527b4  mov     edx, 1Fh; void *
0x1800527b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800527bf  mov     dword ptr [rsp+168h+arg_8], ebx
0x1800527c6  mov     rcx, [rsp+168h+var_110]
0x1800527cb  mov     rax, [rcx]
0x1800527ce  lea     rdx, [rsp+168h+arg_8]
0x1800527d6  mov     rax, [rax+38h]
0x1800527da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800527df  mov     rcx, [rsp+168h]; this
0x1800527e7  test    eax, eax
0x1800527e9  jns     short loc_180052800
0x1800527eb  mov     r9d, eax; char *
0x1800527ee  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800527f5  mov     edx, 22h ; '"'; void *
0x1800527fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052800  mov     edx, dword ptr [rsp+168h+arg_8]
0x180052807  test    edx, edx
0x180052809  setz    al
0x18005280c  mov     rcx, [rsp+168h]; this
0x180052814  test    al, al
0x180052816  jz      short loc_180052830
0x180052818  mov     r9d, 8000FFFFh; char *
0x18005281e  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x180052825  mov     edx, 23h ; '#'; void *
0x18005282a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052830  mov     rcx, rbx
0x180052833  mov     [rsp+168h+var_118], rbx
0x180052838  mov     eax, ebx
0x18005283a  mov     dword ptr [rsp+168h+arg_0], ebx
0x180052841  mov     esi, edi
0x180052843  cmp     esi, edx
0x180052845  jg      loc_1800528F9
0x18005284b  mov     r14, [rsp+168h+var_110]
0x180052850  mov     rax, [r14]
0x180052853  mov     r15, [rax+40h]
0x180052857  mov     [rsp+168h+var_118], rbx
0x18005285c  test    rcx, rcx
0x18005285f  jz      short loc_18005286E
0x180052861  mov     rdx, [rcx]
0x180052864  mov     rax, [rdx+10h]
0x180052868  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005286d  nop
0x18005286e  lea     r8, [rsp+168h+var_118]
0x180052873  mov     edx, esi
0x180052875  mov     rcx, r14
0x180052878  mov     rax, r15
0x18005287b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052880  mov     rcx, [rsp+168h]; this
0x180052888  test    eax, eax
0x18005288a  js      short loc_1800528E4
0x18005288c  mov     rcx, [rsp+168h+var_118]
0x180052891  mov     rax, [rcx]
0x180052894  lea     rdx, [rsp+168h+arg_0]
0x18005289c  mov     rax, [rax+38h]
0x1800528a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800528a5  mov     rcx, [rsp+168h]; this
0x1800528ad  test    eax, eax
0x1800528af  js      short loc_1800528CF
0x1800528b1  mov     eax, dword ptr [rsp+168h+arg_0]
0x1800528b8  cmp     eax, edi
0x1800528ba  jz      short loc_1800528FD
0x1800528bc  add     esi, edi
0x1800528be  mov     edx, dword ptr [rsp+168h+arg_8]
0x1800528c5  mov     rcx, [rsp+168h+var_118]
0x1800528ca  jmp     loc_180052843
0x1800528cf  mov     r9d, eax; char *
0x1800528d2  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800528d9  mov     edx, 2Bh ; '+'; void *
0x1800528de  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800528e4  mov     r9d, eax; char *
0x1800528e7  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800528ee  mov     edx, 2Ah ; '*'; void *
0x1800528f3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800528f9  cmp     eax, edi
0x1800528fb  jnz     short loc_180052900
0x1800528fd  mov     dil, bl
0x180052900  mov     rcx, [rsp+168h]; this
0x180052908  test    dil, dil
0x18005290b  jz      short loc_180052925
0x18005290d  mov     r9d, 8000FFFFh; char *
0x180052913  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x18005291a  mov     edx, 33h ; '3'; void *
0x18005291f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052925  lea     rdx, [rsp+168h+var_D8]
0x18005292d  lea     rcx, [rsp+168h+var_118]
0x180052932  call    ??$query@UITimeTrigger@@@?$com_ptr_t@UITrigger@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UITimeTrigger@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<ITrigger,wil::err_exception_policy>::query<ITimeTrigger>(void)
0x180052937  nop
0x180052938  mov     [rsp+168h+var_F8], rbx
0x18005293d  mov     rcx, [rsp+168h+var_D8]
0x180052945  mov     rax, [rcx]
0x180052948  mov     [rsp+168h+var_F8], rbx
0x18005294d  lea     rdx, [rsp+168h+var_F8]
0x180052952  mov     rax, [rax+50h]
0x180052956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005295b  mov     rcx, [rsp+168h]; this
0x180052963  test    eax, eax
0x180052965  jns     short loc_18005297C
0x180052967  mov     r9d, eax; char *
0x18005296a  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x180052971  mov     edx, 37h ; '7'; void *
0x180052976  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005297c  mov     qword ptr [rsp+168h+var_C8], rbx
0x180052984  mov     qword ptr [rsp+168h+var_C8+8], rbx
0x18005298c  mov     [rsp+168h+var_B8], rbx
0x180052994  mov     r8d, r13d
0x180052997  lea     rdx, aPtDm; "PT%dM"
0x18005299e  lea     rcx, [rsp+168h+var_C8]
0x1800529a6  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800529ab  mov     rcx, [rsp+168h]; this
0x1800529b3  test    eax, eax
0x1800529b5  jns     short loc_1800529CC
0x1800529b7  mov     r9d, eax; char *
0x1800529ba  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800529c1  mov     edx, 3Ch ; '<'; void *
0x1800529c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800529cc  mov     rcx, [rsp+168h+var_F8]
0x1800529d1  mov     rax, [rcx]
0x1800529d4  mov     rdx, qword ptr [rsp+168h+var_C8]
0x1800529dc  mov     rax, [rax+40h]
0x1800529e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800529e5  mov     rcx, [rsp+168h]; this
0x1800529ed  test    eax, eax
0x1800529ef  jns     short loc_180052A06
0x1800529f1  mov     r9d, eax; char *
0x1800529f4  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x1800529fb  mov     edx, 3Dh ; '='; void *
0x180052a00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052a06  mov     edx, r12d; unsigned int
0x180052a09  mov     rcx, [rsp+168h+var_118]; struct ITrigger *
0x180052a0e  call    ?AdjustNextRunTime@TaskRescheduler@@CAXPEAUITrigger@@K@Z; TaskRescheduler::AdjustNextRunTime(ITrigger *,ulong)
0x180052a13  nop
0x180052a14  jmp     short loc_180052A18
0x180052a16  xor     ebx, ebx
0x180052a18  mov     [rsp+168h+var_E0], rbx
0x180052a20  mov     rcx, [rsp+168h+var_100]
0x180052a25  mov     rax, [rcx]
0x180052a28  mov     [rsp+168h+var_E0], rbx
0x180052a30  movups  xmm1, xmmword ptr [rsp+168h+pvarg]
0x180052a38  movsd   xmm0, qword ptr [rsp+168h+pvarg+10h]
0x180052a41  movaps  [rsp+168h+var_48], xmm1
0x180052a49  movsd   [rsp+168h+var_38], xmm0
0x180052a52  movaps  [rsp+168h+var_68], xmm1
0x180052a5a  movsd   [rsp+168h+var_58], xmm0
0x180052a63  movaps  xmmword ptr [rsp+168h+var_88], xmm1
0x180052a6b  movsd   [rsp+168h+var_78], xmm0
0x180052a74  lea     rdx, [rsp+168h+var_E0]
0x180052a7c  mov     [rsp+168h+var_128], rdx
0x180052a81  lea     rdx, [rsp+168h+var_48]
0x180052a89  mov     [rsp+168h+var_130], rdx
0x180052a8e  mov     r9d, 4
0x180052a94  mov     [rsp+168h+var_138], r9d
0x180052a99  lea     rdx, [rsp+168h+var_68]
0x180052aa1  mov     [rsp+168h+var_140], rdx
0x180052aa6  lea     rdx, [rsp+168h+var_88]
0x180052aae  mov     [rsp+168h+ppv], rdx; int
0x180052ab3  mov     r8, [rsp+168h+var_108]
0x180052ab8  lea     rdx, aRefreshcache; "RefreshCache"
0x180052abf  mov     rax, [rax+88h]
0x180052ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052acb  mov     rcx, [rsp+168h]; this
0x180052ad3  test    eax, eax
0x180052ad5  jns     short loc_180052AEC
0x180052ad7  mov     r9d, eax; char *
0x180052ada  lea     r8, aOnecoreBaseFli_26; "onecore\\base\\flighting\\common\\tasku"...
0x180052ae1  mov     edx, 51h ; 'Q'; void *
0x180052ae6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180052aec  lea     rcx, [rsp+168h+var_E0]
0x180052af4  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180052af9  nop
0x180052afa  lea     rcx, [rsp+168h+var_C8]
0x180052b02  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180052b07  nop
0x180052b08  lea     rcx, [rsp+168h+var_F8]
0x180052b0d  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180052b12  nop
0x180052b13  lea     rcx, [rsp+168h+var_D8]
0x180052b1b  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180052b20  nop
0x180052b21  lea     rcx, [rsp+168h+var_118]
0x180052b26  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180052b2b  nop
0x180052b2c  lea     rcx, [rsp+168h+var_110]
0x180052b31  call    ??1?$com_ptr_t@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>,wil::err_exception_policy>(void)
0x180052b36  nop
0x180052b37  lea     rcx, [rsp+168h+var_108]
  ... truncated ...
```
