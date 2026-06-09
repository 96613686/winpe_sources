# GetAuthenticator(HWND__ *,bool,ulong,Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IOnlineIdAuthenticator> &)

- ea: `0x180038638`
- end: `0x18003898d`
- name: `?GetAuthenticator@@YAJPEAUHWND__@@_NKAEAV?$ComPtr@UIOnlineIdAuthenticator@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Z`
- size: `853`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180038194`

## callees

- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x1800102d0`
- `0x18001a0d0`
- `0x18002ae68`
- `0x180038638`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038778`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180038778`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003875f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18003875f`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800387a0`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1800387a0`

## string_xrefs

- `0x180038758`: `Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator`
- `0x1800387fb`: `hr = ActivateInstance(StringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdAuthenticator).Get(), &spAuthenticator)`
- `0x180038845`: `hr = spAuthenticator.As(&spInitializeAsBroker)`
- `0x18003886e`: `hr = spInitializeAsBroker->Initialize()`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetAuthenticator(__int64 a1, char a2, __int16 a3, _QWORD *a4)
{
  HSTRING v8; // rbx
  int v9; // ebx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  int v12; // eax
  const char *v13; // rcx
  unsigned int v14; // r8d
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v17; // ebx
  char *v19; // [rsp+20h] [rbp-79h]
  int v20[4]; // [rsp+30h] [rbp-69h] BYREF
  __int64 v21; // [rsp+40h] [rbp-59h] BYREF
  unsigned __int64 v22; // [rsp+48h] [rbp-51h]
  __int64 v23; // [rsp+50h] [rbp-49h] BYREF
  __int64 v24; // [rsp+58h] [rbp-41h] BYREF
  __int64 v25; // [rsp+60h] [rbp-39h] BYREF
  int *v26[4]; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v27[4]; // [rsp+88h] [rbp-11h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp+17h] BYREF

  v20[0] = 0;
  v27[0] = "GetAuthenticator";
  v27[1] = v20;
  v27[2] = 0;
  v27[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "GetAuthenticator",
    (const char *)0x67,
    0,
    (const unsigned __int16 *)v19);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v26, "GetAuthenticator", v20, 0xBu, &qword_18006BB80);
  v25 = 0;
  v24 = 0;
  if ( (a3 & 0x200) != 0 )
  {
    v21 = 0x4CC4CC4C7D629E2ELL;
    v22 = 0x3DC5118BC425B795LL;
  }
  else if ( a2 == 1 )
  {
    v21 = 0x43DB4B1CCC553C39LL;
    v22 = 0xEFAC51F7783BA094uLL;
  }
  else
  {
    v21 = 0x11E103F556B26D4ELL;
    v22 = 0x9B0124489192CDB7uLL;
  }
  if ( WindowsCreateStringReference(
         L"Windows.Security.Authentication.OnlineId.OnlineIdAuthenticator",
         0x3Eu,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v8 = string;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a4);
  *a4 = 0;
  v23 = 0;
  v9 = RoActivateInstance(v8, &v23);
  if ( v9 >= 0 )
  {
    if ( (unsigned int)InlineIsEqualGUID(
                         &GUID_a003f58a_29ab_4817_b884_d7516dad18b9,
                         &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
    {
      *a4 = v23;
    }
    else
    {
      v9 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v23)(
             v23,
             &GUID_a003f58a_29ab_4817_b884_d7516dad18b9,
             a4);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  v20[0] = v9;
  if ( v9 >= 0 )
  {
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a4;
    v11 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a4;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v12 = v11(v10, &GUID_f2d7a32c_a4f9_483c_bbc5_3cff03609807, &v24);
    v20[0] = v12;
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v24 + 24LL))(v24);
      v20[0] = v12;
      if ( v12 >= 0 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a4 + 72LL))(*a4, &v21);
        v20[0] = v12;
        if ( v12 >= 0 )
        {
          v15 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a4;
          v16 = **(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*a4;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
          v12 = v16(v15, &GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1, &v25);
          v20[0] = v12;
          if ( v12 >= 0 )
          {
            v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 24LL))(v25, a1);
            v20[0] = v12;
            if ( v12 >= 0 )
              goto LABEL_25;
            v13 = "hr = spInitializeWithWindow->Initialize(hwnd)";
            v14 = 132;
          }
          else
          {
            v13 = "hr = spAuthenticator.As<IInitializeWithWindow>(&spInitializeWithWindow)";
            v14 = 131;
          }
        }
        else
        {
          v13 = "hr = spAuthenticator->put_ApplicationId(applicationId)";
          v14 = 130;
        }
      }
      else
      {
        v13 = "hr = spInitializeAsBroker->Initialize()";
        v14 = 129;
      }
    }
    else
    {
      v13 = "hr = spAuthenticator.As(&spInitializeAsBroker)";
      v14 = 128;
    }
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
      "GetAuthenticator",
      v14,
      v12,
      v13);
    goto LABEL_25;
  }
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "GetAuthenticator",
    0x7Fu,
    v9,
    "hr = ActivateInstance(StringReference(RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdAuthenticator).G"
    "et(), &spAuthenticator)");
LABEL_25:
  v17 = v20[0];
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v25);
  ErrorVerifier::CheckAgainstList((const char *)v26[3], *v26[2], (unsigned __int64)v26[1], v26[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v27);
  return v17;
}

```

## disassembly

```asm
0x180038638  mov     [rsp-8+arg_8], rbx
0x18003863d  mov     [rsp-8+arg_10], rsi
0x180038642  push    rbp
0x180038643  push    rdi
0x180038644  push    r12
0x180038646  push    r13
0x180038648  push    r14
0x18003864a  lea     rbp, [rsp-37h]
0x18003864f  sub     rsp, 0D0h
0x180038656  mov     rax, cs:__security_cookie
0x18003865d  xor     rax, rsp
0x180038660  mov     [rbp+57h+var_28], rax
0x180038664  mov     rsi, r9
0x180038667  mov     ebx, r8d
0x18003866a  mov     dil, dl
0x18003866d  mov     r14, rcx
0x180038670  mov     [rbp+57h+var_C0], 0
0x180038677  lea     r12, aGetauthenticat; "GetAuthenticator"
0x18003867e  mov     [rbp+57h+var_68], r12
0x180038682  lea     rax, [rbp+57h+var_C0]
0x180038686  mov     [rbp+57h+var_60], rax
0x18003868a  mov     [rbp+57h+var_58], 0
0x180038692  mov     [rbp+57h+var_50], 0
0x18003869a  xor     r9d, r9d; unsigned int
0x18003869d  lea     r8d, [r9+67h]; char *
0x1800386a1  mov     rdx, r12; char *
0x1800386a4  lea     r13, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800386ab  mov     rcx, r13; this
0x1800386ae  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800386b3  nop
0x1800386b4  lea     rax, qword_18006BB80
0x1800386bb  mov     [rsp+0F0h+var_D0], rax; int *
0x1800386c0  mov     r9d, 0Bh; unsigned __int64
0x1800386c6  lea     r8, [rbp+57h+var_C0]; int *
0x1800386ca  mov     rdx, r12; char *
0x1800386cd  lea     rcx, [rbp+57h+var_88]; this
0x1800386d1  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x1800386d6  nop
0x1800386d7  mov     [rbp+57h+var_90], 0
0x1800386df  mov     [rbp+57h+var_98], 0
0x1800386e7  bt      ebx, 9
0x1800386eb  jnb     short loc_18003870B
0x1800386ed  mov     dword ptr [rbp+57h+var_B0], 7D629E2Eh
0x1800386f4  mov     dword ptr [rbp+57h+var_B0+4], 4CC4CC4Ch
0x1800386fb  mov     dword ptr [rbp+57h+var_B0+8], 0C425B795h
0x180038702  mov     dword ptr [rbp+57h+var_B0+0Ch], 3DC5118Bh
0x180038709  jmp     short loc_18003874B
0x18003870b  cmp     dil, 1
0x18003870f  jnz     short loc_18003872F
0x180038711  mov     dword ptr [rbp+57h+var_B0], 0CC553C39h
0x180038718  mov     dword ptr [rbp+57h+var_B0+4], 43DB4B1Ch
0x18003871f  mov     dword ptr [rbp+57h+var_B0+8], 783BA094h
0x180038726  mov     dword ptr [rbp+57h+var_B0+0Ch], 0EFAC51F7h
0x18003872d  jmp     short loc_18003874B
0x18003872f  mov     dword ptr [rbp+57h+var_B0], 56B26D4Eh
0x180038736  mov     dword ptr [rbp+57h+var_B0+4], 11E103F5h
0x18003873d  mov     dword ptr [rbp+57h+var_B0+8], 9192CDB7h
0x180038744  mov     dword ptr [rbp+57h+var_B0+0Ch], 9B012448h
0x18003874b  lea     r9, [rbp+57h+string]; string
0x18003874f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180038753  mov     edx, 3Eh ; '>'; length
0x180038758  lea     rcx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdAuthenticator@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18003875f  call    cs:__imp_WindowsCreateStringReference
0x180038765  test    eax, eax
0x180038767  jns     short loc_18003877E
0x180038769  xor     r9d, r9d; lpArguments
0x18003876c  xor     r8d, r8d; nNumberOfArguments
0x18003876f  lea     edx, [r9+1]; dwExceptionFlags
0x180038773  mov     ecx, 0C000000Dh; dwExceptionCode
0x180038778  call    cs:__imp_RaiseException
0x18003877e  mov     rbx, [rbp+57h+string]
0x180038782  mov     rcx, rsi
0x180038785  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003878a  mov     qword ptr [rsi], 0
0x180038791  mov     [rbp+57h+var_A0], 0
0x180038799  lea     rdx, [rbp+57h+var_A0]
0x18003879d  mov     rcx, rbx
0x1800387a0  call    cs:__imp_RoActivateInstance
0x1800387a6  mov     ebx, eax
0x1800387a8  test    eax, eax
0x1800387aa  js      short loc_1800387F4
0x1800387ac  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x1800387b3  lea     rcx, _GUID_a003f58a_29ab_4817_b884_d7516dad18b9; struct _GUID *
0x1800387ba  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1800387bf  mov     rcx, [rbp+57h+var_A0]
0x1800387c3  test    eax, eax
0x1800387c5  jz      short loc_1800387CC
0x1800387c7  mov     [rsi], rcx
0x1800387ca  jmp     short loc_1800387F4
0x1800387cc  mov     rax, [rcx]
0x1800387cf  mov     r8, rsi
0x1800387d2  lea     rdx, _GUID_a003f58a_29ab_4817_b884_d7516dad18b9
0x1800387d9  mov     rax, [rax]
0x1800387dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387e1  mov     ebx, eax
0x1800387e3  mov     rcx, [rbp+57h+var_A0]
0x1800387e7  mov     rax, [rcx]
0x1800387ea  mov     rax, [rax+10h]
0x1800387ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800387f3  nop
0x1800387f4  mov     [rbp+57h+var_C0], ebx
0x1800387f7  test    ebx, ebx
0x1800387f9  jns     short loc_180038815
0x1800387fb  lea     rax, aHrActivateinst; "hr = ActivateInstance(StringReference(R"...
0x180038802  mov     [rsp+0F0h+var_D0], rax
0x180038807  mov     r9d, ebx
0x18003880a  mov     r8d, 7Fh
0x180038810  jmp     loc_180038920
0x180038815  mov     rdi, [rsi]
0x180038818  mov     rax, [rdi]
0x18003881b  mov     rbx, [rax]
0x18003881e  lea     rcx, [rbp+57h+var_98]
0x180038822  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038827  lea     r8, [rbp+57h+var_98]
0x18003882b  lea     rdx, _GUID_f2d7a32c_a4f9_483c_bbc5_3cff03609807
0x180038832  mov     rcx, rdi
0x180038835  mov     rax, rbx
0x180038838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003883d  nop
0x18003883e  mov     [rbp+57h+var_C0], eax
0x180038841  test    eax, eax
0x180038843  jns     short loc_180038857
0x180038845  lea     rcx, aHrSpauthentica_1; "hr = spAuthenticator.As(&spInitializeAs"...
0x18003884c  mov     r8d, 80h
0x180038852  jmp     loc_180038918
0x180038857  mov     rcx, [rbp+57h+var_98]
0x18003885b  mov     rax, [rcx]
0x18003885e  mov     rax, [rax+18h]
0x180038862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038867  mov     [rbp+57h+var_C0], eax
0x18003886a  test    eax, eax
0x18003886c  jns     short loc_180038880
0x18003886e  lea     rcx, aHrSpinitialize; "hr = spInitializeAsBroker->Initialize()"
0x180038875  mov     r8d, 81h
0x18003887b  jmp     loc_180038918
0x180038880  mov     rcx, [rsi]
0x180038883  movaps  xmm0, [rbp+57h+var_B0]
0x180038887  movdqa  [rbp+57h+var_B0], xmm0
0x18003888c  mov     rax, [rcx]
0x18003888f  lea     rdx, [rbp+57h+var_B0]
0x180038893  mov     rax, [rax+48h]
0x180038897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003889c  mov     [rbp+57h+var_C0], eax
0x18003889f  test    eax, eax
0x1800388a1  jns     short loc_1800388B2
0x1800388a3  lea     rcx, aHrSpauthentica_2; "hr = spAuthenticator->put_ApplicationId"...
0x1800388aa  mov     r8d, 82h
0x1800388b0  jmp     short loc_180038918
0x1800388b2  mov     rdi, [rsi]
0x1800388b5  mov     rax, [rdi]
0x1800388b8  mov     rbx, [rax]
0x1800388bb  lea     rcx, [rbp+57h+var_90]
0x1800388bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800388c4  lea     r8, [rbp+57h+var_90]
0x1800388c8  lea     rdx, _GUID_3e68d4bd_7135_4d10_8018_9fb6d9f33fa1
0x1800388cf  mov     rcx, rdi
0x1800388d2  mov     rax, rbx
0x1800388d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388da  nop
0x1800388db  mov     [rbp+57h+var_C0], eax
0x1800388de  test    eax, eax
0x1800388e0  jns     short loc_1800388F1
0x1800388e2  lea     rcx, aHrSpauthentica; "hr = spAuthenticator.As<IInitializeWith"...
0x1800388e9  mov     r8d, 83h
0x1800388ef  jmp     short loc_180038918
0x1800388f1  mov     rcx, [rbp+57h+var_90]
0x1800388f5  mov     rax, [rcx]
0x1800388f8  mov     rdx, r14
0x1800388fb  mov     rax, [rax+18h]
0x1800388ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038904  mov     [rbp+57h+var_C0], eax
0x180038907  test    eax, eax
0x180038909  jns     short loc_18003892B
0x18003890b  lea     rcx, aHrSpinitialize_0; "hr = spInitializeWithWindow->Initialize"...
0x180038912  mov     r8d, 84h; unsigned int
0x180038918  mov     [rsp+0F0h+var_D0], rcx; char *
0x18003891d  mov     r9d, eax; int
0x180038920  mov     rdx, r12; char *
0x180038923  mov     rcx, r13; char *
0x180038926  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003892b  mov     ebx, [rbp+57h+var_C0]
0x18003892e  lea     rcx, [rbp+57h+var_98]
0x180038932  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038937  nop
0x180038938  lea     rcx, [rbp+57h+var_90]
0x18003893c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038941  nop
0x180038942  mov     r9, [rbp+57h+var_88]; int *
0x180038946  mov     r8, [rbp+57h+var_80]; unsigned __int64
0x18003894a  mov     rdx, [rbp+57h+var_78]
0x18003894e  mov     edx, [rdx]; int
0x180038950  mov     rcx, [rbp+57h+var_70]; char *
0x180038954  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x180038959  nop
0x18003895a  lea     rcx, [rbp+57h+var_68]
0x18003895e  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180038963  mov     eax, ebx
0x180038965  mov     rcx, [rbp+57h+var_28]
0x180038969  xor     rcx, rsp; StackCookie
0x18003896c  call    __security_check_cookie
0x180038971  lea     r11, [rsp+0F0h+var_20]
0x180038979  mov     rbx, [r11+38h]
0x18003897d  mov     rsi, [r11+40h]
0x180038981  mov     rsp, r11
0x180038984  pop     r14
0x180038986  pop     r13
0x180038988  pop     r12
0x18003898a  pop     rdi
0x18003898b  pop     rbp
0x18003898c  retn
```
