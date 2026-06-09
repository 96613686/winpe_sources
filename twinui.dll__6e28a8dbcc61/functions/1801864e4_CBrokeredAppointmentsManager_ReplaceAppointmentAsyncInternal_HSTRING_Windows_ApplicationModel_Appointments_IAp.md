# CBrokeredAppointmentsManager::_ReplaceAppointmentAsyncInternal(HSTRING__ *,Windows::ApplicationModel::Appointments::IAppointment *,Windows::Foundation::Rect const &,Windows::UI::Popups::Placement,Windows::Foundation::DateTime *,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *)

- ea: `0x1801864e4`
- end: `0x1801866e0`
- name: `?_ReplaceAppointmentAsyncInternal@CBrokeredAppointmentsManager@@CAJPEAUHSTRING__@@PEAUIAppointment@Appointments@ApplicationModel@Windows@@AEBURect@Foundation@6@W4Placement@Popups@UI@6@PEAUDateTime@86@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@86@@Z`
- size: `508`
- prototype: `__int64 __usercall@<rax>(HSTRING string@<rcx>, struct Windows::ApplicationModel::Appointments::IAppointment *@<rdx>, __int64, __int64)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801852c0`
- `0x180185300`
- `0x180185340`

## callees

- `0x18001f3c0`
- `0x180054170`
- `0x18013d354`
- `0x18017b128`
- `0x18017c9b4`
- `0x18017de38`
- `0x180182e10`
- `0x18018622c`
- `0x1801864e4`
- `0x180186a48`
- `0x180186de0`
- `0x18036dd0c`
- `0x1803a3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801865bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801865bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018652a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsIsStringEmpty` at `0x18018652a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186593`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801865b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018668c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801866ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801866bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186593`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801865b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180186684`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018668c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801866ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801866bd`

## pseudocode

```c
__int64 __fastcall CBrokeredAppointmentsManager::_ReplaceAppointmentAsyncInternal(
        HSTRING string,
        struct Windows::ApplicationModel::Appointments::IAppointment *a2,
        __int64 a3,
        int a4,
        __int64 *a5,
        _QWORD *a6)
{
  char v6; // r15
  int CallingApplicationWindowAndVerifyVisibility; // esi
  unsigned int v11; // r8d
  void *v12; // rbx
  unsigned __int16 **v13; // rdx
  PCWSTR StringRawBuffer; // rax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rsi
  void *v18; // rdi
  __int128 v19; // xmm0
  void *v20; // rax
  __int64 v21; // r8
  void *v23; // [rsp+20h] [rbp-59h] BYREF
  void *v24; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v25[2]; // [rsp+30h] [rbp-49h] BYREF
  HWND v26; // [rsp+40h] [rbp-39h] BYREF
  struct Windows::ApplicationModel::Appointments::IAppointment *v27; // [rsp+48h] [rbp-31h] BYREF
  void *v28; // [rsp+50h] [rbp-29h] BYREF
  __int128 v29; // [rsp+58h] [rbp-21h]
  int v30; // [rsp+68h] [rbp-11h]
  char v31; // [rsp+6Ch] [rbp-Dh]
  __int64 v32; // [rsp+70h] [rbp-9h]
  void *v33; // [rsp+78h] [rbp-1h]
  HWND v34; // [rsp+80h] [rbp+7h]
  struct Windows::ApplicationModel::Appointments::IAppointment *v35; // [rsp+88h] [rbp+Fh] BYREF

  v6 = 0;
  v25[0] = a3;
  *a6 = 0;
  if ( !a2 )
  {
    CallingApplicationWindowAndVerifyVisibility = -2147467261;
    v11 = 11206;
LABEL_5:
    OriginateErrorWithResourceString(CallingApplicationWindowAndVerifyVisibility, 0, v11);
    return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
  }
  if ( WindowsIsStringEmpty(string) )
  {
    CallingApplicationWindowAndVerifyVisibility = -2147024809;
    v11 = 11208;
    goto LABEL_5;
  }
  CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_ValidateAppointmentInternalImplementation(a2);
  if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
  {
    CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_ValidateAppointmentPropertyValues(a2);
    if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
    {
      v12 = 0;
      v26 = 0;
      v23 = 0;
      CallingApplicationWindowAndVerifyVisibility = CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(
                                                      &v26,
                                                      0);
      if ( CallingApplicationWindowAndVerifyVisibility >= 0 )
      {
        CoTaskMemFree(0);
        CallingApplicationWindowAndVerifyVisibility = CallerIdentity::GetCallingProcessPackageFamilyName(
                                                        (CallerIdentity *)&v23,
                                                        v13);
        if ( CallingApplicationWindowAndVerifyVisibility < 0 )
        {
          v12 = v23;
        }
        else
        {
          v24 = 0;
          CoTaskMemFree(0);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          CallingApplicationWindowAndVerifyVisibility = _AllocString<CTCoAllocPolicy>(v16, v15, StringRawBuffer, &v24);
          if ( CallingApplicationWindowAndVerifyVisibility < 0 )
          {
            v12 = v23;
            v18 = v24;
          }
          else
          {
            if ( a5 )
            {
              v17 = *a5;
              v6 = 1;
            }
            else
            {
              v17 = 0;
            }
            v27 = a2;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v27);
            v18 = 0;
            v28 = v24;
            v33 = v23;
            v30 = a4;
            v31 = v6;
            v19 = *(_OWORD *)v25[0];
            v32 = v17;
            v29 = v19;
            v34 = v26;
            v35 = a2;
            Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(&v35);
            LODWORD(v25[0]) = 1;
            *(_QWORD *)((char *)v25 + 4) = 4;
            v20 = operator new(0x58u, (const struct std::nothrow_t *)&std::nothrow);
            if ( v20 )
              v20 = (void *)Windows::Internal::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>(
                              v20,
                              &v28);
            CallingApplicationWindowAndVerifyVisibility = Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CHSTRINGResult,HSTRING__ *,Windows::Internal::ComTaskPoolHandler>(
                                                            v25,
                                                            a6,
                                                            v21,
                                                            v20);
            _lambda_05f3cc7b8d847fd5ad9f7c464deabe87_::~_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_((_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_ *)&v28);
            CoTaskMemFree(0);
            CoTaskMemFree(0);
            (*(void (__fastcall **)(struct Windows::ApplicationModel::Appointments::IAppointment *))(*(_QWORD *)a2 + 16LL))(a2);
          }
          CoTaskMemFree(v18);
        }
      }
      CoTaskMemFree(v12);
    }
  }
  return (unsigned int)CallingApplicationWindowAndVerifyVisibility;
}

```

## disassembly

```asm
0x1801864e4  mov     [rsp-8+arg_10], rbx
0x1801864e9  push    rbp
0x1801864ea  push    rsi
0x1801864eb  push    rdi
0x1801864ec  push    r12
0x1801864ee  push    r13
0x1801864f0  push    r14
0x1801864f2  push    r15
0x1801864f4  lea     rbp, [rsp-17h]
0x1801864f9  sub     rsp, 90h
0x180186500  mov     r12, [rbp+47h+arg_28]
0x180186504  xor     r15d, r15d
0x180186507  mov     qword ptr [rbp+47h+var_90], r8
0x18018650b  mov     r13d, r9d
0x18018650e  mov     r14, rdx
0x180186511  mov     rdi, rcx
0x180186514  mov     [r12], r15
0x180186518  test    rdx, rdx
0x18018651b  jnz     short loc_18018652A
0x18018651d  mov     esi, 80004003h
0x180186522  mov     r8d, 2BC6h
0x180186528  jmp     short loc_18018653F
0x18018652a  call    cs:__imp_WindowsIsStringEmpty
0x180186530  test    eax, eax
0x180186532  jz      short loc_18018654D
0x180186534  mov     esi, 80070057h
0x180186539  mov     r8d, 2BC8h; unsigned int
0x18018653f  xor     edx, edx; HINSTANCE
0x180186541  mov     ecx, esi; int
0x180186543  call    ?OriginateErrorWithResourceString@@YAXJPEAUHINSTANCE__@@I@Z; OriginateErrorWithResourceString(long,HINSTANCE__ *,uint)
0x180186548  jmp     loc_1801866C3
0x18018654d  mov     rcx, r14; struct Windows::ApplicationModel::Appointments::IAppointment *
0x180186550  call    ?_ValidateAppointmentInternalImplementation@CBrokeredAppointmentsManager@@CAJPEAUIAppointment@Appointments@ApplicationModel@Windows@@@Z; CBrokeredAppointmentsManager::_ValidateAppointmentInternalImplementation(Windows::ApplicationModel::Appointments::IAppointment *)
0x180186555  mov     esi, eax
0x180186557  test    eax, eax
0x180186559  js      loc_1801866C3
0x18018655f  mov     rcx, r14; struct Windows::ApplicationModel::Appointments::IAppointment *
0x180186562  call    ?_ValidateAppointmentPropertyValues@CBrokeredAppointmentsManager@@CAJPEAUIAppointment@Appointments@ApplicationModel@Windows@@@Z; CBrokeredAppointmentsManager::_ValidateAppointmentPropertyValues(Windows::ApplicationModel::Appointments::IAppointment *)
0x180186567  mov     esi, eax
0x180186569  test    eax, eax
0x18018656b  js      loc_1801866C3
0x180186571  mov     rbx, r15
0x180186574  mov     [rbp+47h+var_80], r15
0x180186578  xor     edx, edx; unsigned __int16 **
0x18018657a  mov     [rbp+47h+var_A0], rbx
0x18018657e  lea     rcx, [rbp+47h+var_80]; this
0x180186582  call    ?_GetCallingApplicationWindowAndVerifyVisibility@CBrokeredAppointmentsManager@@CAJPEAPEAUHWND__@@PEAPEAG@Z; CBrokeredAppointmentsManager::_GetCallingApplicationWindowAndVerifyVisibility(HWND__ * *,ushort * *)
0x180186587  mov     esi, eax
0x180186589  test    eax, eax
0x18018658b  js      loc_1801866BA
0x180186591  xor     ecx, ecx; pv
0x180186593  call    cs:__imp_CoTaskMemFree
0x180186599  lea     rcx, [rbp+47h+var_A0]; this
0x18018659d  call    ?GetCallingProcessPackageFamilyName@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessPackageFamilyName(ushort * *)
0x1801865a2  mov     esi, eax
0x1801865a4  test    eax, eax
0x1801865a6  js      loc_1801866B6
0x1801865ac  xor     ecx, ecx; pv
0x1801865ae  mov     [rbp+47h+var_98], r15
0x1801865b2  call    cs:__imp_CoTaskMemFree
0x1801865b8  xor     edx, edx; length
0x1801865ba  mov     rcx, rdi; string
0x1801865bd  call    cs:__imp_WindowsGetStringRawBuffer
0x1801865c3  mov     r8, rax
0x1801865c6  lea     r9, [rbp+47h+var_98]
0x1801865ca  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1801865cf  mov     esi, eax
0x1801865d1  test    eax, eax
0x1801865d3  js      loc_1801866A3
0x1801865d9  mov     rsi, [rbp+47h+arg_20]
0x1801865dd  test    rsi, rsi
0x1801865e0  jz      short loc_1801865EA
0x1801865e2  mov     rsi, [rsi]
0x1801865e5  mov     r15b, 1
0x1801865e8  jmp     short loc_1801865ED
0x1801865ea  mov     rsi, r15
0x1801865ed  lea     rcx, [rbp+47h+var_78]
0x1801865f1  mov     [rbp+47h+var_78], r14
0x1801865f5  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x1801865fa  mov     rax, [rbp+47h+var_98]
0x1801865fe  xor     edi, edi
0x180186600  mov     rcx, [rbp+47h+var_A0]
0x180186604  mov     [rbp+47h+var_70], rax
0x180186608  mov     rax, qword ptr [rbp+47h+var_90]
0x18018660c  mov     [rbp+47h+var_48], rcx
0x180186610  lea     rcx, [rbp+47h+var_38]
0x180186614  mov     [rbp+47h+var_58], r13d
0x180186618  mov     [rbp+47h+var_54], r15b
0x18018661c  movups  xmm0, xmmword ptr [rax]
0x18018661f  mov     rax, [rbp+47h+var_80]
0x180186623  mov     [rbp+47h+var_50], rsi
0x180186627  movdqu  [rbp+47h+var_68], xmm0
0x18018662c  mov     [rbp+47h+var_40], rax
0x180186630  mov     [rbp+47h+var_38], r14
0x180186634  call    ?InternalAddRef@?$ComPtr@UIWindowingEnvironmentConfig@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IWindowingEnvironmentConfig>::InternalAddRef(void)
0x180186639  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180186640  mov     dword ptr [rbp+47h+var_90], 1
0x180186647  lea     ecx, [rdi+58h]; unsigned __int64
0x18018664a  mov     qword ptr [rbp+47h+var_90+4], 4
0x180186652  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180186657  test    rax, rax
0x18018665a  jz      short loc_180186668
0x18018665c  lea     rdx, [rbp+47h+var_70]
0x180186660  mov     rcx, rax
0x180186663  call    ??$?0V_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@@?$COperationLambdaVar@$0A@V_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@VCHSTRINGResult@Internal@Windows@@$$V@Internal@Windows@@QEAA@$$QEAV_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@@Z; Windows::Internal::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>::COperationLambdaVar<0,_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_,Windows::Internal::CHSTRINGResult,>(_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_ &&)
0x180186668  mov     r9, rax
0x18018666b  lea     rcx, [rbp+47h+var_90]
0x18018666f  mov     rdx, r12
0x180186672  call    ??$MakeAsyncOperationHelper@VCHSTRINGResult@Internal@Windows@@PEAUHSTRING__@@VComTaskPoolHandler@23@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@1@W4TrustLevel@@PEAV?$AsyncCallbackBase@VCHSTRINGResult@Internal@Windows@@@01@@Z; Windows::Internal::MakeAsyncOperationHelper<Windows::Internal::CHSTRINGResult,HSTRING__ *,Windows::Internal::ComTaskPoolHandler>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<HSTRING__ *> * *,TrustLevel,Windows::Internal::AsyncCallbackBase<Windows::Internal::CHSTRINGResult> *)
0x180186677  lea     rcx, [rbp+47h+var_70]; this
0x18018667b  mov     esi, eax
0x18018667d  call    ??1_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_@@QEAA@XZ; _lambda_05f3cc7b8d847fd5ad9f7c464deabe87_::~_lambda_05f3cc7b8d847fd5ad9f7c464deabe87_(void)
0x180186682  xor     ecx, ecx; pv
0x180186684  call    cs:__imp_CoTaskMemFree
0x18018668a  xor     ecx, ecx; pv
0x18018668c  call    cs:__imp_CoTaskMemFree
0x180186692  mov     rax, [r14]
0x180186695  mov     rcx, r14
0x180186698  mov     rax, [rax+10h]
0x18018669c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801866a1  jmp     short loc_1801866AB
0x1801866a3  mov     rbx, [rbp+47h+var_A0]
0x1801866a7  mov     rdi, [rbp+47h+var_98]
0x1801866ab  mov     rcx, rdi; pv
0x1801866ae  call    cs:__imp_CoTaskMemFree
0x1801866b4  jmp     short loc_1801866BA
0x1801866b6  mov     rbx, [rbp+47h+var_A0]
0x1801866ba  mov     rcx, rbx; pv
0x1801866bd  call    cs:__imp_CoTaskMemFree
0x1801866c3  mov     rbx, [rsp+0C0h+arg_10]
0x1801866cb  mov     eax, esi
0x1801866cd  add     rsp, 90h
0x1801866d4  pop     r15
0x1801866d6  pop     r14
0x1801866d8  pop     r13
0x1801866da  pop     r12
0x1801866dc  pop     rdi
0x1801866dd  pop     rsi
0x1801866de  pop     rbp
0x1801866df  retn
```
