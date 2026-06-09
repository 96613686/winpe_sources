# GetAuthenticatedIdentity(HWND__ *,bool,bool,ulong,Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IUserIdentity> &)

- ea: `0x180038194`
- end: `0x180038631`
- name: `?GetAuthenticatedIdentity@@YAJPEAUHWND__@@_N1KAEAV?$ComPtr@UIUserIdentity@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Z`
- size: `1181`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800389a0`

## callees

- `0x180004824`
- `0x180004910`
- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x180012828`
- `0x180013cd8`
- `0x18002ae68`
- `0x180037ed4`
- `0x180038194`
- `0x180038638`
- `0x180038e80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003835a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18003835a`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038486`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180038486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038379`

## string_xrefs

- `0x180038416`: `hr = spAuthOperation->put_Completed(spCompletionHandler.Get())`
- `0x180038493`: `hr = CoWaitForMultipleHandles(COWAIT_DISPATCH_CALLS | COWAIT_DISPATCH_WINDOW_MESSAGES, INFINITE, 1, &hCompletedEventRaw, &waitIndex)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetAuthenticatedIdentity(__int64 a1, char a2, char a3, __int16 a4, __int64 a5)
{
  __int64 v9; // rdi
  const WCHAR *v10; // rcx
  unsigned int v11; // r14d
  int TargetsForRequest; // eax
  unsigned int v13; // r8d
  const char *v14; // rcx
  __int64 (__fastcall ***v15)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rsi
  __int64 v17; // rsi
  __int64 (__fastcall *v18)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  HANDLE Event; // rbx
  __int64 *v20; // rax
  __int64 v21; // rcx
  __int64 (__fastcall ***v22)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v23)(_QWORD, GUID *, __int64 *); // rsi
  __int64 (__fastcall ***v24)(_QWORD, _QWORD, _QWORD); // rsi
  __int64 (__fastcall *v25)(_QWORD, GUID *, __int64 *); // rbx
  unsigned int v26; // ebx
  const unsigned __int16 *lpdwindex; // [rsp+20h] [rbp-91h]
  const char *lpdwindexa; // [rsp+20h] [rbp-91h]
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+30h] [rbp-81h] BYREF
  __int64 v31; // [rsp+38h] [rbp-79h] BYREF
  __int64 v32; // [rsp+40h] [rbp-71h] BYREF
  __int64 v33; // [rsp+48h] [rbp-69h] BYREF
  DWORD dwindex; // [rsp+50h] [rbp-61h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-59h] BYREF
  __int64 v36; // [rsp+60h] [rbp-51h] BYREF
  HANDLE pHandles; // [rsp+68h] [rbp-49h] BYREF
  _QWORD v38[3]; // [rsp+70h] [rbp-41h] BYREF
  __int64 v39; // [rsp+88h] [rbp-29h]
  int *v40[4]; // [rsp+90h] [rbp-21h] BYREF
  _QWORD v41[10]; // [rsp+B0h] [rbp-1h] BYREF
  int v42; // [rsp+118h] [rbp+67h] BYREF
  int v43; // [rsp+120h] [rbp+6Fh] BYREF

  v42 = 0;
  v41[0] = "GetAuthenticatedIdentity";
  v41[1] = &v42;
  v41[2] = 0;
  v41[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "GetAuthenticatedIdentity",
    (const char *)0x95,
    0,
    lpdwindex);
  ErrorVerifier::ErrorVerifier((ErrorVerifier *)v40, "GetAuthenticatedIdentity", &v42, 0x17u, &qword_18006BB20);
  dwindex = 0;
  memset(v38, 0, sizeof(v38));
  pHandles = 0;
  v43 = 0;
  v32 = 0;
  v36 = 0;
  v9 = 0;
  v39 = 0;
  v30 = 0;
  v35 = 0;
  v33 = 0;
  v10 = L"PURPOSE_KEYREGISTER";
  if ( a2 != 1 )
    v10 = L"PURPOSE_KEYREGISTER_WEAK";
  if ( a3 == 1 || (v11 = 2, (a4 & 4) != 0) )
    v11 = 0;
  TargetsForRequest = GetTargetsForRequest(v10, &v35);
  v42 = TargetsForRequest;
  if ( TargetsForRequest >= 0 )
  {
    TargetsForRequest = GetAuthenticator(a1, a3, a4, &v36);
    v42 = TargetsForRequest;
    if ( TargetsForRequest >= 0 )
    {
      v15 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v35;
      v16 = **v35;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
      TargetsForRequest = v16(v15, &GUID_cb72d686_9516_520d_a274_fa4cd1762cb2, &v33);
      v42 = TargetsForRequest;
      if ( TargetsForRequest >= 0 )
      {
        v17 = v36;
        v18 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v36 + 56LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
        TargetsForRequest = v18(v17, v33, v11, &v30);
        v42 = TargetsForRequest;
        if ( TargetsForRequest >= 0 )
        {
          Event = CreateEventExW(0, 0, 0, 0x1F0003u);
          pHandles = Event;
          Auto<void *,HandleFunctor,IWinApiLite>::Clear(v38);
          v38[0] = Event;
          if ( Event )
            goto LABEL_19;
          TargetsForRequest = GetLastError();
          if ( TargetsForRequest > 0 )
            TargetsForRequest = (unsigned __int16)TargetsForRequest | 0x80070000;
          v42 = TargetsForRequest;
          if ( TargetsForRequest >= 0 )
          {
LABEL_19:
            v20 = (__int64 *)Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::UserIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::UserIdentity *>>,Auto<void *,HandleFunctor,IWinApiLite> &>(
                               &v31,
                               v38);
            v9 = *v20;
            *v20 = 0;
            v39 = v9;
            v21 = v31;
            if ( v31 )
            {
              v31 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
            }
            if ( !v9 )
            {
              v42 = -2147024882;
              Telemetry::IfFailExit(
                "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
                "GetAuthenticatedIdentity",
                0xC7u,
                -2147024882,
                "hr = E_OUTOFMEMORY");
              goto LABEL_42;
            }
            TargetsForRequest = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v30)[6])(
                                  v30,
                                  v9);
            v42 = TargetsForRequest;
            if ( TargetsForRequest >= 0 )
            {
              v22 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
              v23 = **v30;
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
              TargetsForRequest = v23(v22, &GUID_00000036_0000_0000_c000_000000000046, &v32);
              v42 = TargetsForRequest;
              if ( TargetsForRequest >= 0 )
              {
                TargetsForRequest = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, &pHandles, &dwindex);
                v42 = TargetsForRequest;
                if ( TargetsForRequest >= 0 )
                {
                  TargetsForRequest = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 56LL))(v32, &v43);
                  v42 = TargetsForRequest;
                  if ( TargetsForRequest >= 0 )
                  {
                    if ( v43 == 3 )
                    {
                      LODWORD(v31) = 0;
                      TargetsForRequest = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 64LL))(
                                            v32,
                                            &v31);
                      v42 = TargetsForRequest;
                      if ( TargetsForRequest < 0 )
                      {
                        v14 = "hr = spAsyncInfo->get_ErrorCode(&hrAsync)";
                        v13 = 210;
                        goto LABEL_40;
                      }
                      v42 = v31;
                      if ( (int)v31 < 0 )
                      {
                        Telemetry::IfFailExit(
                          "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
                          "GetAuthenticatedIdentity",
                          0xD3u,
                          v31,
                          "hr = hrAsync");
                        goto LABEL_42;
                      }
                    }
                    else if ( v43 == 2 )
                    {
                      v42 = -2147023673;
                      Telemetry::IfFailExit(
                        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
                        "GetAuthenticatedIdentity",
                        0xD7u,
                        -2147023673,
                        "hr = HRESULT_FROM_WIN32(ERROR_CANCELLED)");
                      goto LABEL_42;
                    }
                    v24 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v30;
                    v25 = (*v30)[8];
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a5);
                    TargetsForRequest = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD), __int64))v25)(
                                          v24,
                                          a5);
                    v42 = TargetsForRequest;
                    if ( TargetsForRequest >= 0 )
                      goto LABEL_42;
                    v14 = "hr = spAuthOperation->GetResults(&spUserIdentity)";
                    v13 = 218;
                    goto LABEL_40;
                  }
                  v14 = "hr = spAsyncInfo->get_Status(&status)";
                  v13 = 205;
                }
                else
                {
                  v14 = "hr = CoWaitForMultipleHandles(COWAIT_DISPATCH_CALLS | COWAIT_DISPATCH_WINDOW_MESSAGES, INFINITE,"
                        " 1, &hCompletedEventRaw, &waitIndex)";
                  v13 = 204;
                }
              }
              else
              {
                v14 = "hr = spAuthOperation.As(&spAsyncInfo)";
                v13 = 203;
              }
            }
            else
            {
              v14 = "hr = spAuthOperation->put_Completed(spCompletionHandler.Get())";
              v13 = 202;
            }
          }
          else
          {
            v14 = "hr = HRESULT_FROM_WIN32(GetLastError())";
            v13 = 193;
          }
        }
        else
        {
          v14 = "hr = spAuthenticator->AuthenticateUserAsyncAdvanced(spTargetsIterable.Get(), promptType, &spAuthOperation)";
          v13 = 187;
        }
      }
      else
      {
        v14 = "hr = spTargets.As(&spTargetsIterable)";
        v13 = 186;
      }
    }
    else
    {
      v14 = "hr = GetAuthenticator(hwnd, isPinReset, dwflags, spAuthenticator)";
      v13 = 185;
    }
LABEL_40:
    lpdwindexa = v14;
    goto LABEL_41;
  }
  lpdwindexa = "hr = GetTargetsForRequest(pPolicy, spTargets)";
  v13 = 184;
LABEL_41:
  Telemetry::IfFailExit(
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\authenticationadapter.cpp",
    "GetAuthenticatedIdentity",
    v13,
    TargetsForRequest,
    lpdwindexa);
LABEL_42:
  v26 = v42;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v36);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
  Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(v38);
  ErrorVerifier::CheckAgainstList((const char *)v40[3], *v40[2], (unsigned __int64)v40[1], v40[0]);
  CTraceFuncW<long>::~CTraceFuncW<long>(v41);
  return v26;
}

```

## disassembly

```asm
0x180038194  mov     [rsp-8+arg_0], rbx
0x180038199  push    rbp
0x18003819a  push    rsi
0x18003819b  push    rdi
0x18003819c  push    r12
0x18003819e  push    r13
0x1800381a0  push    r14
0x1800381a2  push    r15
0x1800381a4  lea     rbp, [rsp-1Fh]
0x1800381a9  sub     rsp, 0D0h
0x1800381b0  mov     esi, r9d
0x1800381b3  mov     r15b, r8b
0x1800381b6  mov     bl, dl
0x1800381b8  mov     r12, rcx
0x1800381bb  xor     r13d, r13d
0x1800381be  mov     [rbp+4Fh+arg_8], r13d
0x1800381c2  lea     rdi, aGetauthenticat_0; "GetAuthenticatedIdentity"
0x1800381c9  mov     [rbp+4Fh+var_50], rdi
0x1800381cd  lea     rax, [rbp+4Fh+arg_8]
0x1800381d1  mov     [rbp+4Fh+var_48], rax
0x1800381d5  mov     [rbp+4Fh+var_40], r13
0x1800381d9  mov     [rbp+4Fh+var_38], r13
0x1800381dd  xor     r9d, r9d; unsigned int
0x1800381e0  mov     r8d, 95h; char *
0x1800381e6  mov     rdx, rdi; char *
0x1800381e9  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800381f0  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800381f5  nop
0x1800381f6  lea     rax, qword_18006BB20
0x1800381fd  mov     [rsp+100h+lpdwindex], rax; int *
0x180038202  lea     r9d, [r13+17h]; unsigned __int64
0x180038206  lea     r8, [rbp+4Fh+arg_8]; int *
0x18003820a  mov     rdx, rdi; char *
0x18003820d  lea     rcx, [rbp+4Fh+var_70]; this
0x180038211  call    ??0ErrorVerifier@@QEAA@PEBDPEAJ_KPEBJ@Z; ErrorVerifier::ErrorVerifier(char const *,long *,unsigned __int64,long const *)
0x180038216  nop
0x180038217  mov     [rbp+4Fh+dwindex], r13d
0x18003821b  mov     [rbp+4Fh+var_90], r13
0x18003821f  mov     [rbp+4Fh+var_80], r13
0x180038223  mov     [rbp+4Fh+var_88], r13
0x180038227  mov     [rbp+4Fh+pHandles], r13
0x18003822b  mov     [rbp+4Fh+arg_10], r13d
0x18003822f  mov     [rbp+4Fh+var_C0], r13
0x180038233  mov     [rbp+4Fh+var_A0], r13
0x180038237  mov     edi, r13d
0x18003823a  mov     [rbp+4Fh+var_78], r13
0x18003823e  mov     [rsp+100h+var_D0], r13
0x180038243  mov     [rbp+4Fh+var_A8], r13
0x180038247  mov     [rbp+4Fh+var_B8], r13
0x18003824b  lea     rax, aPurposeKeyregi; "PURPOSE_KEYREGISTER_WEAK"
0x180038252  lea     rcx, aPurposeKeyregi_0; "PURPOSE_KEYREGISTER"
0x180038259  cmp     bl, 1
0x18003825c  cmovnz  rcx, rax; sourceString
0x180038260  cmp     r15b, 1
0x180038264  jz      short loc_180038270
0x180038266  test    sil, 4
0x18003826a  lea     r14d, [r13+2]
0x18003826e  jz      short loc_180038273
0x180038270  mov     r14d, r13d
0x180038273  lea     rdx, [rbp+4Fh+var_A8]
0x180038277  call    ?GetTargetsForRequest@@YAJPEBGAEAV?$ComPtr@V?$Vector@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@U?$DefaultEqualityPredicate@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@Internal@Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@U?$DefaultVectorOptions@PEAVOnlineIdServiceTicketRequest@OnlineId@Authentication@Security@Windows@@@7895@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; GetTargetsForRequest(ushort const *,Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::Vector<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Security::Authentication::OnlineId::OnlineIdServiceTicketRequest *>>> &)
0x18003827c  mov     [rbp+4Fh+arg_8], eax
0x18003827f  test    eax, eax
0x180038281  jns     short loc_18003829A
0x180038283  lea     r8, aHrGettargetsfo; "hr = GetTargetsForRequest(pPolicy, spTa"...
0x18003828a  mov     [rsp+100h+lpdwindex], r8
0x18003828f  mov     r8d, 0B8h
0x180038295  jmp     loc_180038588
0x18003829a  lea     r9, [rbp+4Fh+var_A0]
0x18003829e  mov     r8d, esi
0x1800382a1  mov     dl, r15b
0x1800382a4  mov     rcx, r12
0x1800382a7  call    ?GetAuthenticator@@YAJPEAUHWND__@@_NKAEAV?$ComPtr@UIOnlineIdAuthenticator@OnlineId@Authentication@Security@Windows@@@WRL@Microsoft@@@Z; GetAuthenticator(HWND__ *,bool,ulong,Microsoft::WRL::ComPtr<Windows::Security::Authentication::OnlineId::IOnlineIdAuthenticator> &)
0x1800382ac  mov     [rbp+4Fh+arg_8], eax
0x1800382af  test    eax, eax
0x1800382b1  jns     short loc_1800382C5
0x1800382b3  lea     rcx, aHrGetauthentic; "hr = GetAuthenticator(hwnd, isPinReset,"...
0x1800382ba  mov     r8d, 0B9h
0x1800382c0  jmp     loc_180038583
0x1800382c5  mov     rbx, [rbp+4Fh+var_A8]
0x1800382c9  mov     rax, [rbx]
0x1800382cc  mov     rsi, [rax]
0x1800382cf  lea     rcx, [rbp+4Fh+var_B8]
0x1800382d3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800382d8  lea     r8, [rbp+4Fh+var_B8]
0x1800382dc  lea     rdx, _GUID_cb72d686_9516_520d_a274_fa4cd1762cb2
0x1800382e3  mov     rcx, rbx
0x1800382e6  mov     rax, rsi
0x1800382e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382ee  nop
0x1800382ef  mov     [rbp+4Fh+arg_8], eax
0x1800382f2  test    eax, eax
0x1800382f4  jns     short loc_180038308
0x1800382f6  lea     rcx, aHrSptargetsAsS; "hr = spTargets.As(&spTargetsIterable)"
0x1800382fd  mov     r8d, 0BAh
0x180038303  jmp     loc_180038583
0x180038308  mov     rsi, [rbp+4Fh+var_A0]
0x18003830c  mov     rax, [rsi]
0x18003830f  mov     rbx, [rax+38h]
0x180038313  lea     rcx, [rsp+100h+var_D0]
0x180038318  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003831d  lea     r9, [rsp+100h+var_D0]
0x180038322  mov     r8d, r14d
0x180038325  mov     rdx, [rbp+4Fh+var_B8]
0x180038329  mov     rcx, rsi
0x18003832c  mov     rax, rbx
0x18003832f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038334  mov     [rbp+4Fh+arg_8], eax
0x180038337  test    eax, eax
0x180038339  jns     short loc_18003834D
0x18003833b  lea     rcx, aHrSpauthentica_0; "hr = spAuthenticator->AuthenticateUserA"...
0x180038342  mov     r8d, 0BBh
0x180038348  jmp     loc_180038583
0x18003834d  mov     r9d, 1F0003h; dwDesiredAccess
0x180038353  xor     r8d, r8d; dwFlags
0x180038356  xor     edx, edx; lpName
0x180038358  xor     ecx, ecx; lpEventAttributes
0x18003835a  call    cs:__imp_CreateEventExW
0x180038360  mov     rbx, rax
0x180038363  mov     [rbp+4Fh+pHandles], rax
0x180038367  lea     rcx, [rbp+4Fh+var_90]
0x18003836b  call    ?Clear@?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAAXXZ; Auto<void *,HandleFunctor,IWinApiLite>::Clear(void)
0x180038370  mov     [rbp+4Fh+var_90], rbx
0x180038374  test    rbx, rbx
0x180038377  jnz     short loc_1800383A4
0x180038379  call    cs:__imp_GetLastError
0x18003837f  test    eax, eax
0x180038381  jle     short loc_18003838B
0x180038383  movzx   eax, ax
0x180038386  or      eax, 80070000h
0x18003838b  mov     [rbp+4Fh+arg_8], eax
0x18003838e  test    eax, eax
0x180038390  jns     short loc_1800383A4
0x180038392  lea     rcx, aHrHresultFromW_2; "hr = HRESULT_FROM_WIN32(GetLastError())"
0x180038399  mov     r8d, 0C1h
0x18003839f  jmp     loc_180038583
0x1800383a4  lea     rdx, [rbp+4Fh+var_90]
0x1800383a8  lea     rcx, [rbp+4Fh+var_C8]
0x1800383ac  call    ??$Make@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserIdentity@OnlineId@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserIdentity@OnlineId@Authentication@Security@Windows@@@23@@@AEAV?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$AuthenticationCompletedHandler@U?$IAsyncOperation@PEAVUserIdentity@OnlineId@Authentication@Security@Windows@@@Foundation@Windows@@U?$IAsyncOperationCompletedHandler@PEAVUserIdentity@OnlineId@Authentication@Security@Windows@@@23@@@@12@AEAV?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@@Z; Microsoft::WRL::Details::Make<AuthenticationCompletedHandler<Windows::Foundation::IAsyncOperation<Windows::Security::Authentication::OnlineId::UserIdentity *>,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::OnlineId::UserIdentity *>>,Auto<void *,HandleFunctor,IWinApiLite> &>(Auto<void *,HandleFunctor,IWinApiLite> &)
0x1800383b1  mov     rdi, [rax]
0x1800383b4  mov     [rax], r13
0x1800383b7  mov     [rbp+4Fh+var_78], rdi
0x1800383bb  mov     rcx, [rbp+4Fh+var_C8]
0x1800383bf  test    rcx, rcx
0x1800383c2  jz      short loc_1800383D5
0x1800383c4  mov     [rbp+4Fh+var_C8], r13
0x1800383c8  mov     rax, [rcx]
0x1800383cb  mov     rax, [rax+10h]
0x1800383cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800383d4  nop
0x1800383d5  test    rdi, rdi
0x1800383d8  jnz     short loc_1800383FB
0x1800383da  mov     r9d, 8007000Eh
0x1800383e0  mov     [rbp+4Fh+arg_8], r9d
0x1800383e4  lea     rax, aHrEOutofmemory; "hr = E_OUTOFMEMORY"
0x1800383eb  mov     [rsp+100h+lpdwindex], rax
0x1800383f0  mov     r8d, 0C7h
0x1800383f6  jmp     loc_18003858B
0x1800383fb  mov     rcx, [rsp+100h+var_D0]
0x180038400  mov     rax, [rcx]
0x180038403  mov     rdx, rdi
0x180038406  mov     rax, [rax+30h]
0x18003840a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003840f  mov     [rbp+4Fh+arg_8], eax
0x180038412  test    eax, eax
0x180038414  jns     short loc_180038428
0x180038416  lea     rcx, aHrSpauthoperat_0; "hr = spAuthOperation->put_Completed(spC"...
0x18003841d  mov     r8d, 0CAh
0x180038423  jmp     loc_180038583
0x180038428  mov     rbx, [rsp+100h+var_D0]
0x18003842d  mov     rax, [rbx]
0x180038430  mov     rsi, [rax]
0x180038433  lea     rcx, [rbp+4Fh+var_C0]
0x180038437  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003843c  lea     r8, [rbp+4Fh+var_C0]
0x180038440  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180038447  mov     rcx, rbx
0x18003844a  mov     rax, rsi
0x18003844d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038452  nop
0x180038453  mov     [rbp+4Fh+arg_8], eax
0x180038456  test    eax, eax
0x180038458  jns     short loc_18003846C
0x18003845a  lea     rcx, aHrSpauthoperat; "hr = spAuthOperation.As(&spAsyncInfo)"
0x180038461  mov     r8d, 0CBh
0x180038467  jmp     loc_180038583
0x18003846c  lea     rax, [rbp+4Fh+dwindex]
0x180038470  mov     [rsp+100h+lpdwindex], rax; lpdwindex
0x180038475  lea     r9, [rbp+4Fh+pHandles]; pHandles
0x180038479  mov     r8d, 1; cHandles
0x18003847f  or      edx, 0FFFFFFFFh; dwTimeout
0x180038482  lea     ecx, [r8+17h]; dwFlags
0x180038486  call    cs:__imp_CoWaitForMultipleHandles
0x18003848c  mov     [rbp+4Fh+arg_8], eax
0x18003848f  test    eax, eax
0x180038491  jns     short loc_1800384A5
0x180038493  lea     rcx, aHrCowaitformul; "hr = CoWaitForMultipleHandles(COWAIT_DI"...
0x18003849a  mov     r8d, 0CCh
0x1800384a0  jmp     loc_180038583
0x1800384a5  mov     rcx, [rbp+4Fh+var_C0]
0x1800384a9  mov     rax, [rcx]
0x1800384ac  lea     rdx, [rbp+4Fh+arg_10]
0x1800384b0  mov     rax, [rax+38h]
0x1800384b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384b9  mov     [rbp+4Fh+arg_8], eax
0x1800384bc  test    eax, eax
0x1800384be  jns     short loc_1800384D2
0x1800384c0  lea     rcx, aHrSpasyncinfoG; "hr = spAsyncInfo->get_Status(&status)"
0x1800384c7  mov     r8d, 0CDh
0x1800384cd  jmp     loc_180038583
0x1800384d2  cmp     [rbp+4Fh+arg_10], 3
0x1800384d6  jnz     short loc_180038527
0x1800384d8  mov     dword ptr [rbp+4Fh+var_C8], r13d
0x1800384dc  mov     rcx, [rbp+4Fh+var_C0]
0x1800384e0  mov     rax, [rcx]
0x1800384e3  lea     rdx, [rbp+4Fh+var_C8]
0x1800384e7  mov     rax, [rax+40h]
0x1800384eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384f0  mov     [rbp+4Fh+arg_8], eax
0x1800384f3  test    eax, eax
0x1800384f5  jns     short loc_180038506
0x1800384f7  lea     rcx, aHrSpasyncinfoG_0; "hr = spAsyncInfo->get_ErrorCode(&hrAsyn"...
0x1800384fe  mov     r8d, 0D2h
0x180038504  jmp     short loc_180038583
0x180038506  mov     r9d, dword ptr [rbp+4Fh+var_C8]
0x18003850a  mov     [rbp+4Fh+arg_8], r9d
0x18003850e  test    r9d, r9d
0x180038511  jns     short loc_18003854B
0x180038513  lea     rax, aHrHrasync; "hr = hrAsync"
0x18003851a  mov     [rsp+100h+lpdwindex], rax
0x18003851f  mov     r8d, 0D3h
0x180038525  jmp     short loc_18003858B
0x180038527  cmp     [rbp+4Fh+arg_10], 2
0x18003852b  jnz     short loc_18003854B
0x18003852d  mov     r9d, 800704C7h
0x180038533  mov     [rbp+4Fh+arg_8], r9d
0x180038537  lea     rax, aHrHresultFromW_7; "hr = HRESULT_FROM_WIN32(ERROR_CANCELLED"...
0x18003853e  mov     [rsp+100h+lpdwindex], rax
0x180038543  mov     r8d, 0D7h
0x180038549  jmp     short loc_18003858B
0x18003854b  mov     rsi, [rsp+100h+var_D0]
0x180038550  mov     rax, [rsi]
0x180038553  mov     rbx, [rax+40h]
0x180038557  mov     rcx, [rbp+4Fh+arg_20]
0x18003855b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180038560  mov     rdx, [rbp+4Fh+arg_20]
0x180038564  mov     rcx, rsi
0x180038567  mov     rax, rbx
0x18003856a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003856f  mov     [rbp+4Fh+arg_8], eax
0x180038572  test    eax, eax
0x180038574  jns     short loc_18003859E
0x180038576  lea     rcx, aHrSpauthoperat_1; "hr = spAuthOperation->GetResults(&spUse"...
0x18003857d  mov     r8d, 0DAh; unsigned int
0x180038583  mov     [rsp+100h+lpdwindex], rcx; char *
0x180038588  mov     r9d, eax; int
0x18003858b  lea     rdx, aGetauthenticat_0; "GetAuthenticatedIdentity"
0x180038592  lea     rcx, aOnecoreuapDsEx_24; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180038599  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003859e  mov     ebx, [rbp+4Fh+arg_8]
0x1800385a1  lea     rcx, [rbp+4Fh+var_B8]
0x1800385a5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800385aa  nop
0x1800385ab  lea     rcx, [rbp+4Fh+var_A8]
0x1800385af  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800385b4  nop
0x1800385b5  lea     rcx, [rsp+100h+var_D0]
0x1800385ba  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800385bf  nop
0x1800385c0  test    rdi, rdi
0x1800385c3  jz      short loc_1800385D5
0x1800385c5  mov     rax, [rdi]
0x1800385c8  mov     rcx, rdi
0x1800385cb  mov     rax, [rax+10h]
0x1800385cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800385d4  nop
0x1800385d5  lea     rcx, [rbp+4Fh+var_A0]
0x1800385d9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800385de  nop
0x1800385df  lea     rcx, [rbp+4Fh+var_C0]
0x1800385e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800385e8  nop
0x1800385e9  lea     rcx, [rbp+4Fh+var_90]
0x1800385ed  call    ??1?$Auto@PEAXVHandleFunctor@@VIWinApiLite@@@@QEAA@XZ; Auto<void *,HandleFunctor,IWinApiLite>::~Auto<void *,HandleFunctor,IWinApiLite>(void)
0x1800385f2  nop
0x1800385f3  mov     r9, [rbp+4Fh+var_70]; int *
0x1800385f7  mov     r8, [rbp+4Fh+var_68]; unsigned __int64
0x1800385fb  mov     rdx, [rbp+4Fh+var_60]
0x1800385ff  mov     edx, [rdx]; int
0x180038601  mov     rcx, [rbp+4Fh+var_58]; char *
0x180038605  call    ?CheckAgainstList@ErrorVerifier@@SAXPEBDJ_KPEBJ@Z; ErrorVerifier::CheckAgainstList(char const *,long,unsigned __int64,long const *)
0x18003860a  nop
0x18003860b  lea     rcx, [rbp+4Fh+var_50]
0x18003860f  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180038614  mov     eax, ebx
0x180038616  mov     rbx, [rsp+100h+arg_0]
0x18003861e  add     rsp, 0D0h
0x180038625  pop     r15
0x180038627  pop     r14
0x180038629  pop     r13
  ... truncated ...
```
