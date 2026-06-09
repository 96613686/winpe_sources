# CreateUiRacProcess(Windows::ApplicationModel::Core::IRestrictedAppContainer *,_ISO_ISOLATION_OPTIONS *,_ISO_PROCESS_CREATION_OPTIONS *,_PROCESS_INFORMATION *)

- ea: `0x180049914`
- end: `0x180049c38`
- name: `?CreateUiRacProcess@@YAJPEAUIRestrictedAppContainer@Core@ApplicationModel@Windows@@PEAU_ISO_ISOLATION_OPTIONS@@PEAU_ISO_PROCESS_CREATION_OPTIONS@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `804`
- prototype: `__int64 __fastcall(struct Windows::ApplicationModel::Core::IRestrictedAppContainer *, struct _ISO_ISOLATION_OPTIONS *, struct _ISO_PROCESS_CREATION_OPTIONS *, struct _PROCESS_INFORMATION *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180049688`

## callees

- `0x180042dec`
- `0x18004834c`
- `0x1800483c8`
- `0x180048a7c`
- `0x1800498cc`
- `0x180049914`
- `0x18004a7ac`
- `0x18004fa50`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004998e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800499ea`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18004998e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800499ea`

## string_xrefs

- `0x18004999a`: `Call: GetActivationFactory() for IComponentStatics2`
- `0x180049b80`: `Call: ComponentStatics2->LaunchAsyncRestrictedWithActivationType() `
- `0x180049955`: `Windows.Foundation.Private.Component2`

## pseudocode

```c
__int64 __fastcall CreateUiRacProcess(
        struct Windows::ApplicationModel::Core::IRestrictedAppContainer *a1,
        struct _ISO_ISOLATION_OPTIONS *a2,
        struct _ISO_PROCESS_CREATION_OPTIONS *a3,
        struct _PROCESS_INFORMATION *a4)
{
  __int64 v6; // rbx
  int ActivationFactory; // eax
  int v8; // ebx
  __int64 v9; // rbx
  int v10; // eax
  int v11; // ebx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING_HEADER *); // rbx
  PVOID Reserved1; // rdi
  __int64 v15; // r15
  __int64 (__fastcall *v16)(__int64, struct Windows::ApplicationModel::Core::IRestrictedAppContainer *, __int64, __int64, __int64, __int64, _QWORD, HSTRING_HEADER *, __int64, int, int, __int64 *); // r14
  int v17; // ebx
  __int64 v18; // rdi
  __int128 v19; // xmm6
  __int64 v20; // rsi
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  const unsigned __int16 *v24; // rdx
  int v25; // ecx
  int v26; // eax
  __int64 v28; // [rsp+28h] [rbp-E0h]
  __int64 v29; // [rsp+78h] [rbp-90h] BYREF
  __int64 v30; // [rsp+80h] [rbp-88h] BYREF
  __int64 v31; // [rsp+88h] [rbp-80h] BYREF
  __int64 v32; // [rsp+90h] [rbp-78h] BYREF
  int v33; // [rsp+98h] [rbp-70h] BYREF
  struct _ISO_ISOLATION_OPTIONS *v34; // [rsp+A0h] [rbp-68h]
  struct Windows::ApplicationModel::Core::IRestrictedAppContainer *v35; // [rsp+A8h] [rbp-60h]
  HSTRING_HEADER hstringHeader; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v37; // [rsp+D0h] [rbp-38h]
  _BYTE v38[32]; // [rsp+D8h] [rbp-30h] BYREF

  v34 = a2;
  v35 = a1;
  v30 = 0;
  v37 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Foundation.Private.Component2",
    0x26u,
    0x25u);
  v6 = v37;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  ActivationFactory = RoGetActivationFactory(v6, &GUID_b375b455_2064_43b5_b094_790b6f20dd6e, &v30);
  v8 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v31 = 0;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.Core.CoreApplication",
      0x2Eu,
      0x2Du);
    v9 = v37;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
    v10 = RoGetActivationFactory(v9, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &v31);
    v8 = v10;
    if ( v10 < 0 )
    {
      IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(
        v10,
        L"Call: GetActivationFactory() for ICoreApplication");
LABEL_24:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
      goto LABEL_25;
    }
    v29 = 0;
    v33 = 1;
    v37 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.ApplicationModel.ExtendedExecution.Foreground.ExtendedExecutionForegroundSession",
      0x59u,
      0x58u);
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::ExtendedExecution::Foreground::IExtendedExecutionForegroundSession>>(
            v37,
            &v29);
    if ( v11 < 0 )
      goto LABEL_12;
    v11 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v29 + 96LL))(v29, 3);
    if ( v11 < 0 )
      goto LABEL_12;
    v12 = v29;
    hstringHeader.Reserved.Reserved1 = 0;
    v13 = *(__int64 (__fastcall **)(__int64, HSTRING_HEADER *))(*(_QWORD *)v29 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
    v11 = v13(v12, &hstringHeader);
    if ( v11 >= 0 )
    {
      Reserved1 = hstringHeader.Reserved.Reserved1;
      v11 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(hstringHeader.Reserved.Reserved1);
      if ( v11 >= 0 )
        v11 = (*(__int64 (__fastcall **)(PVOID, int *))(*(_QWORD *)Reserved1 + 64LL))(Reserved1, &v33);
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&hstringHeader);
    if ( v11 < 0 || v33 )
    {
LABEL_12:
      IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(v11, L"ExtendedExecutionForegroundSession denied");
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    }
    v15 = v30;
    v32 = 0;
    v16 = *(__int64 (__fastcall **)(__int64, struct Windows::ApplicationModel::Core::IRestrictedAppContainer *, __int64, __int64, __int64, __int64, _QWORD, HSTRING_HEADER *, __int64, int, int, __int64 *))(*(_QWORD *)v30 + 64LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
    v17 = *(_DWORD *)a3;
    v18 = *((_QWORD *)a3 + 4);
    v19 = *((_OWORD *)a3 + 1);
    v20 = v31;
    v21 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v38, (char *)a3 + 8);
    v22 = *((unsigned int *)v34 + 8);
    v28 = *(_QWORD *)(v21 + 24);
    v23 = *((_QWORD *)v34 + 3);
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = v19;
    v8 = v16(v15, v35, v22, v23, v28, v20, 0, &hstringHeader, v18, v17, 19, &v32);
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)a3 + 5) + 24LL))(
             *((_QWORD *)a3 + 5),
             v32,
             v29);
      if ( v8 >= 0 )
      {
        if ( !*((_DWORD *)a3 + 12)
          || (v26 = (*(__int64 (__fastcall **)(_QWORD, struct _PROCESS_INFORMATION *))(**((_QWORD **)a3 + 5) + 32LL))(
                      *((_QWORD *)a3 + 5),
                      a4),
              v8 = v26,
              v26 >= 0) )
        {
          v8 = 0;
          goto LABEL_23;
        }
        v24 = L"Call: processOptions->LaunchWatcher->WaitForSuccess()";
        v25 = v26;
LABEL_21:
        IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(v25, v24);
LABEL_23:
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
        goto LABEL_24;
      }
      v24 = L"Call: processOptions->LaunchWatcher->Initialize()";
    }
    else
    {
      v24 = L"Call: ComponentStatics2->LaunchAsyncRestrictedWithActivationType() ";
    }
    v25 = v8;
    goto LABEL_21;
  }
  IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(
    ActivationFactory,
    L"Call: GetActivationFactory() for IComponentStatics2");
LABEL_25:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049914  mov     rax, rsp
0x180049917  push    rbp
0x180049918  push    rbx
0x180049919  push    rsi
0x18004991a  push    rdi
0x18004991b  push    r12
0x18004991d  push    r13
0x18004991f  push    r14
0x180049921  push    r15
0x180049923  lea     rbp, [rax-58h]
0x180049927  sub     rsp, 118h
0x18004992e  movaps  xmmword ptr [rax-58h], xmm6
0x180049932  mov     rax, cs:__security_cookie
0x180049939  xor     rax, rsp
0x18004993c  mov     [rbp+50h+var_60], rax
0x180049940  xor     esi, esi
0x180049942  mov     [rbp+50h+var_B8], rdx
0x180049946  mov     r13, r9
0x180049949  mov     [rbp+50h+var_B0], rcx
0x18004994d  mov     r12, r8
0x180049950  mov     [rsp+150h+var_D8], rsi
0x180049955  lea     rdx, ?RuntimeClass_Windows_Foundation_Private_Component2@@3QBGB; "Windows.Foundation.Private.Component2"
0x18004995c  mov     [rbp+50h+var_88], rsi
0x180049960  lea     r9d, [rsi+25h]; unsigned int
0x180049964  lea     r8d, [rsi+26h]; unsigned int
0x180049968  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x18004996c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049971  mov     rbx, [rbp+50h+var_88]
0x180049975  lea     rcx, [rsp+150h+var_D8]
0x18004997a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004997f  lea     r8, [rsp+150h+var_D8]
0x180049984  mov     rcx, rbx
0x180049987  lea     rdx, _GUID_b375b455_2064_43b5_b094_790b6f20dd6e
0x18004998e  call    cs:__imp_RoGetActivationFactory
0x180049994  mov     ebx, eax
0x180049996  test    eax, eax
0x180049998  jns     short loc_1800499AD
0x18004999a  lea     rdx, aCallGetactivat_0; "Call: GetActivationFactory() for ICompo"...
0x1800499a1  mov     ecx, eax; int
0x1800499a3  call    ?LogUiRacProcessCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(long,ushort const *)
0x1800499a8  jmp     loc_180049C04
0x1800499ad  mov     r9d, 2Dh ; '-'; unsigned int
0x1800499b3  mov     [rbp+50h+var_D0], rsi
0x1800499b7  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x1800499be  mov     [rbp+50h+var_88], rsi
0x1800499c2  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x1800499c6  lea     r8d, [r9+1]; unsigned int
0x1800499ca  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800499cf  mov     rbx, [rbp+50h+var_88]
0x1800499d3  lea     rcx, [rbp+50h+var_D0]
0x1800499d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800499dc  lea     r8, [rbp+50h+var_D0]
0x1800499e0  mov     rcx, rbx
0x1800499e3  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x1800499ea  call    cs:__imp_RoGetActivationFactory
0x1800499f0  mov     ebx, eax
0x1800499f2  test    eax, eax
0x1800499f4  jns     short loc_180049A09
0x1800499f6  lea     rdx, aCallGetactivat_1; "Call: GetActivationFactory() for ICoreA"...
0x1800499fd  mov     ecx, eax; int
0x1800499ff  call    ?LogUiRacProcessCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(long,ushort const *)
0x180049a04  jmp     loc_180049BFB
0x180049a09  mov     r9d, 58h ; 'X'; unsigned int
0x180049a0f  mov     [rsp+150h+var_E0], rsi
0x180049a14  lea     rdx, ?RuntimeClass_Windows_ApplicationModel_ExtendedExecution_Foreground_ExtendedExecutionForegroundSession@@3QBGB; "Windows.ApplicationModel.ExtendedExecut"...
0x180049a1b  mov     [rbp+50h+var_C0], 1
0x180049a22  lea     rcx, [rbp+50h+hstringHeader]; hstringHeader
0x180049a26  mov     [rbp+50h+var_88], rsi
0x180049a2a  lea     r8d, [r9+1]; unsigned int
0x180049a2e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180049a33  mov     rcx, [rbp+50h+var_88]
0x180049a37  lea     rdx, [rsp+150h+var_E0]
0x180049a3c  call    ??$ActivateInstance@V?$ComPtr@UIExtendedExecutionForegroundSession@Foreground@ExtendedExecution@ApplicationModel@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIExtendedExecutionForegroundSession@Foreground@ExtendedExecution@ApplicationModel@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::ApplicationModel::ExtendedExecution::Foreground::IExtendedExecutionForegroundSession>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::ApplicationModel::ExtendedExecution::Foreground::IExtendedExecutionForegroundSession>>)
0x180049a41  mov     ebx, eax
0x180049a43  test    eax, eax
0x180049a45  js      loc_180049ACE
0x180049a4b  mov     rcx, [rsp+150h+var_E0]
0x180049a50  mov     edx, 3
0x180049a55  mov     rax, [rcx]
0x180049a58  mov     rax, [rax+60h]
0x180049a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a61  mov     ebx, eax
0x180049a63  test    eax, eax
0x180049a65  js      short loc_180049ACE
0x180049a67  mov     rdi, [rsp+150h+var_E0]
0x180049a6c  lea     rcx, [rbp+50h+hstringHeader]
0x180049a70  mov     qword ptr [rbp+50h+hstringHeader.Reserved], rsi
0x180049a74  mov     rax, [rdi]
0x180049a77  mov     rbx, [rax+50h]
0x180049a7b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049a80  lea     rdx, [rbp+50h+hstringHeader]
0x180049a84  mov     rcx, rdi
0x180049a87  mov     rax, rbx
0x180049a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049a8f  mov     ebx, eax
0x180049a91  test    eax, eax
0x180049a93  js      short loc_180049ABC
0x180049a95  mov     rdi, qword ptr [rbp+50h+hstringHeader.Reserved]
0x180049a99  mov     rcx, rdi
0x180049a9c  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4ExtendedExecutionForegroundResult@Foreground@ExtendedExecution@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::ExtendedExecution::Foreground::ExtendedExecutionForegroundResult> *,tagCOWAIT_FLAGS,void *)
0x180049aa1  mov     ebx, eax
0x180049aa3  test    eax, eax
0x180049aa5  js      short loc_180049ABC
0x180049aa7  mov     rax, [rdi]
0x180049aaa  lea     rdx, [rbp+50h+var_C0]
0x180049aae  mov     rcx, rdi
0x180049ab1  mov     rax, [rax+40h]
0x180049ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049aba  mov     ebx, eax
0x180049abc  lea     rcx, [rbp+50h+hstringHeader]
0x180049ac0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049ac5  test    ebx, ebx
0x180049ac7  js      short loc_180049ACE
0x180049ac9  cmp     [rbp+50h+var_C0], esi
0x180049acc  jz      short loc_180049AE6
0x180049ace  lea     rdx, aExtendedexecut; "ExtendedExecutionForegroundSession deni"...
0x180049ad5  mov     ecx, ebx; int
0x180049ad7  call    ?LogUiRacProcessCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(long,ushort const *)
0x180049adc  lea     rcx, [rsp+150h+var_E0]
0x180049ae1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049ae6  mov     r15, [rsp+150h+var_D8]
0x180049aeb  lea     rcx, [rbp+50h+var_C8]
0x180049aef  mov     [rbp+50h+var_C8], rsi
0x180049af3  mov     rax, [r15]
0x180049af6  mov     r14, [rax+40h]
0x180049afa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049aff  mov     ebx, [r12]
0x180049b03  lea     rdx, [r12+8]
0x180049b08  mov     rdi, [r12+20h]
0x180049b0d  lea     rcx, [rbp+50h+var_80]
0x180049b11  movups  xmm6, xmmword ptr [r12+10h]
0x180049b17  mov     rsi, [rbp+50h+var_D0]
0x180049b1b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180049b20  mov     rdx, [rbp+50h+var_B0]
0x180049b24  lea     rcx, [rbp+50h+var_C8]
0x180049b28  mov     [rsp+58h], rcx
0x180049b2d  lea     rcx, [rbp+50h+hstringHeader]
0x180049b31  mov     dword ptr [rsp+150h+var_100], 13h
0x180049b39  mov     r9, [rax+18h]
0x180049b3d  mov     rax, [rbp+50h+var_B8]
0x180049b41  mov     [rsp+150h+var_108], ebx
0x180049b45  mov     qword ptr [rsp+150h+var_110], rdi
0x180049b4a  mov     [rsp+150h+var_118], rcx
0x180049b4f  mov     rcx, r15
0x180049b52  mov     r8d, [rax+20h]
0x180049b56  mov     [rsp+150h+var_120], 0
0x180049b5f  mov     [rsp+150h+var_128], rsi
0x180049b64  mov     [rsp+150h+var_130], r9
0x180049b69  mov     r9, [rax+18h]
0x180049b6d  mov     rax, r14
0x180049b70  movdqu  xmmword ptr [rbp+50h+hstringHeader.Reserved], xmm6
0x180049b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049b7a  mov     ebx, eax
0x180049b7c  test    eax, eax
0x180049b7e  jns     short loc_180049B8B
0x180049b80  lea     rdx, aCallComponents; "Call: ComponentStatics2->LaunchAsyncRes"...
0x180049b87  mov     ecx, ebx
0x180049b89  jmp     short loc_180049BDF
0x180049b8b  mov     rcx, [r12+28h]
0x180049b90  mov     r8, [rsp+150h+var_E0]
0x180049b95  mov     rdx, [rbp+50h+var_C8]
0x180049b99  mov     rax, [rcx]
0x180049b9c  mov     rax, [rax+18h]
0x180049ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ba5  mov     ebx, eax
0x180049ba7  test    eax, eax
0x180049ba9  jns     short loc_180049BB4
0x180049bab  lea     rdx, aCallProcessopt; "Call: processOptions->LaunchWatcher->In"...
0x180049bb2  jmp     short loc_180049B87
0x180049bb4  cmp     dword ptr [r12+30h], 0
0x180049bba  jz      short loc_180049BE6
0x180049bbc  mov     rcx, [r12+28h]
0x180049bc1  mov     rdx, r13
0x180049bc4  mov     rax, [rcx]
0x180049bc7  mov     rax, [rax+20h]
0x180049bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049bd0  mov     ebx, eax
0x180049bd2  test    eax, eax
0x180049bd4  jns     short loc_180049BE6
0x180049bd6  lea     rdx, aCallProcessopt_0; "Call: processOptions->LaunchWatcher->Wa"...
0x180049bdd  mov     ecx, eax; int
0x180049bdf  call    ?LogUiRacProcessCreationFailure@TelemetryHelper@IsolationApi@@SAXJPEBG@Z; IsolationApi::TelemetryHelper::LogUiRacProcessCreationFailure(long,ushort const *)
0x180049be4  jmp     short loc_180049BE8
0x180049be6  xor     ebx, ebx
0x180049be8  lea     rcx, [rbp+50h+var_C8]
0x180049bec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049bf1  lea     rcx, [rsp+150h+var_E0]
0x180049bf6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049bfb  lea     rcx, [rbp+50h+var_D0]
0x180049bff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049c04  lea     rcx, [rsp+150h+var_D8]
0x180049c09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049c0e  mov     eax, ebx
0x180049c10  mov     rcx, [rbp+50h+var_60]
0x180049c14  xor     rcx, rsp; StackCookie
0x180049c17  call    __security_check_cookie
0x180049c1c  movaps  xmm6, [rsp+150h+var_58+8]
0x180049c24  add     rsp, 118h
0x180049c2b  pop     r15
0x180049c2d  pop     r14
0x180049c2f  pop     r13
0x180049c31  pop     r12
0x180049c33  pop     rdi
0x180049c34  pop     rsi
0x180049c35  pop     rbx
0x180049c36  pop     rbp
0x180049c37  retn
```
