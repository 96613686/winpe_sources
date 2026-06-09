# CDataPackageView::RequestAccessWithEnterpriseIdAsync(HSTRING__ *,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> * *)

- ea: `0x180048480`
- end: `0x18004862a`
- name: `?RequestAccessWithEnterpriseIdAsync@CDataPackageView@@UEAAJPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@Windows@@@Z`
- size: `426`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180048470`
- `0x18004ff50`

## callees

- `0x18000adb8`
- `0x18002ce48`
- `0x18002cfcc`
- `0x180046710`
- `0x180048480`
- `0x180048954`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800484bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800484bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800485df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800484a7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800485df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048615`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800484ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800484ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDataPackageView::RequestAccessWithEnterpriseIdAsync(__int64 a1, HSTRING a2, __int64 a3)
{
  HRESULT v6; // eax
  __int64 v7; // rdx
  DataPackageViewCommon *v8; // rcx
  unsigned int v9; // ebx
  int CallerOrCurrentProcessId; // esi
  DWORD CurrentThreadId; // r14d
  HWND CallerWindow; // r8
  __int64 v13; // rbx
  signed __int64 v14; // rcx
  bool v15; // zf
  signed __int64 v16; // rax
  signed __int32 v17; // eax
  signed __int64 v18; // rcx
  signed __int64 v19; // rax
  signed __int32 v20; // eax
  int v21; // edi
  int v23; // [rsp+20h] [rbp-58h] BYREF
  __int64 v24; // [rsp+24h] [rbp-54h]
  HSTRING newString; // [rsp+30h] [rbp-48h] BYREF
  char v26; // [rsp+38h] [rbp-40h]
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  char v28; // [rsp+48h] [rbp-30h]
  __int64 v29; // [rsp+50h] [rbp-28h]
  int v30; // [rsp+58h] [rbp-20h]
  DWORD v31; // [rsp+5Ch] [rbp-1Ch]
  HWND v32; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  v26 = 0;
  WindowsDeleteString(0);
  newString = 0;
  v6 = WindowsDuplicateString(a2, &newString);
  v9 = v6;
  if ( v6 >= 0 )
  {
    CallerOrCurrentProcessId = DataPackageViewCommon::GetCallerOrCurrentProcessId(v8, v7);
    CurrentThreadId = GetCurrentThreadId();
    CallerWindow = DataPackageViewCommon::GetCallerWindow((DataPackageViewCommon *)(a1 + 96));
    v13 = a1 - 24;
    if ( a1 != 24 )
    {
      v14 = *(_QWORD *)(v13 + 112);
      while ( v14 >= 0 )
      {
        if ( (_DWORD)v14 != 0x7FFFFFFF )
        {
          v16 = _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 112), v14 + 1, v14);
          v15 = v14 == v16;
          v14 = v16;
          if ( !v15 )
            continue;
        }
        goto LABEL_11;
      }
      do
        v17 = *(_DWORD *)(2 * v14 + 0x10);
      while ( v17 != 0x7FFFFFFF
           && v17 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v14 + 16), v17 + 1, v17) );
    }
LABEL_11:
    string = newString;
    newString = 0;
    v28 = 0;
    v26 = 1;
    v29 = a1 - 24;
    if ( a1 != 24 )
    {
      v18 = *(_QWORD *)(v13 + 112);
      while ( v18 >= 0 )
      {
        if ( (_DWORD)v18 != 0x7FFFFFFF )
        {
          v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v13 + 112), v18 + 1, v18);
          v15 = v18 == v19;
          v18 = v19;
          if ( !v15 )
            continue;
        }
        goto LABEL_19;
      }
      do
        v20 = *(_DWORD *)(2 * v18 + 0x10);
      while ( v20 != 0x7FFFFFFF
           && v20 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v18 + 16), v20 + 1, v20) );
    }
LABEL_19:
    v30 = CallerOrCurrentProcessId;
    v31 = CurrentThreadId;
    v32 = CallerWindow;
    v23 = 3;
    v24 = 128;
    v21 = Windows::Internal::MakeAsyncOperation<Windows::Internal::CBasicResult<enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult,0>,enum Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult,Windows::Internal::ComTaskPoolHandler,_lambda_41cd686f22d980da34ef68bd8fac3600_>(
            &v23,
            a3,
            CallerWindow,
            &string);
    if ( v29 )
      ((void (*)(void))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::DataTransfer::IDataPackageView,Windows::ApplicationModel::DataTransfer::IDataPackageView2,Windows::ApplicationModel::DataTransfer::IDataPackageView3,Windows::ApplicationModel::DataTransfer::IDataPackageView4,IDataPackageViewPriv,Microsoft::WRL::ChainInterfaces<Microsoft::WRL::CloakedIid<IAgileDataObject>,Microsoft::WRL::CloakedIid<IDataObject>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDataObjectAsyncCapability,IInitializeWithWindow,Microsoft::WRL::FtmBase>::Release)();
    WindowsDeleteString(string);
    if ( v21 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x138F,
        (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
        (const char *)(unsigned int)v21,
        v23);
    if ( v13 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::DataTransfer::IDataPackageView,Windows::ApplicationModel::DataTransfer::IDataPackageView2,Windows::ApplicationModel::DataTransfer::IDataPackageView3,Windows::ApplicationModel::DataTransfer::IDataPackageView4,IDataPackageViewPriv,Microsoft::WRL::ChainInterfaces<Microsoft::WRL::CloakedIid<IAgileDataObject>,Microsoft::WRL::CloakedIid<IDataObject>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDataObjectAsyncCapability,IInitializeWithWindow,Microsoft::WRL::FtmBase>::Release(v13);
    v9 = v21;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1372,
      (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
      (const char *)(unsigned int)v6,
      v23);
  }
  WindowsDeleteString(newString);
  return v9;
}

```

## disassembly

```asm
0x180048480  push    rbp
0x180048482  push    rbx
0x180048483  push    rsi
0x180048484  push    rdi
0x180048485  push    r14
0x180048487  push    r15
0x180048489  mov     rbp, rsp
0x18004848c  sub     rsp, 78h
0x180048490  mov     r15, r8
0x180048493  mov     rbx, rdx
0x180048496  mov     rdi, rcx
0x180048499  mov     [rbp+newString], 0
0x1800484a1  mov     [rbp+var_40], 0
0x1800484a5  xor     ecx, ecx; string
0x1800484a7  call    cs:__imp_WindowsDeleteString
0x1800484ad  mov     [rbp+newString], 0
0x1800484b5  lea     rdx, [rbp+newString]; newString
0x1800484b9  mov     rcx, rbx; string
0x1800484bc  call    cs:__imp_WindowsDuplicateString
0x1800484c2  mov     ebx, eax
0x1800484c4  test    eax, eax
0x1800484c6  jns     short loc_1800484E5
0x1800484c8  mov     rcx, [rbp+30h]; this
0x1800484cc  mov     r9d, eax; char *
0x1800484cf  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800484d6  mov     edx, 1372h; void *
0x1800484db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800484e0  jmp     loc_180048611
0x1800484e5  call    ?GetCallerOrCurrentProcessId@DataPackageViewCommon@@IEAAKXZ; DataPackageViewCommon::GetCallerOrCurrentProcessId(void)
0x1800484ea  mov     esi, eax
0x1800484ec  call    cs:__imp_GetCurrentThreadId
0x1800484f2  mov     r14d, eax
0x1800484f5  lea     rcx, [rdi+60h]; this
0x1800484f9  call    ?GetCallerWindow@DataPackageViewCommon@@IEAAPEAUHWND__@@XZ; DataPackageViewCommon::GetCallerWindow(void)
0x1800484fe  mov     r8, rax
0x180048501  lea     rbx, [rdi-18h]
0x180048505  mov     [rbp+arg_8], rbx
0x180048509  mov     r9d, 7FFFFFFFh
0x18004850f  test    rbx, rbx
0x180048512  jz      short loc_18004854A
0x180048514  mov     rcx, [rbx+70h]
0x180048518  test    rcx, rcx
0x18004851b  js      short loc_180048541
0x18004851d  cmp     ecx, r9d
0x180048520  jz      short loc_18004854A
0x180048522  lea     rdx, [rcx+1]
0x180048526  mov     rax, rcx
0x180048529  lock cmpxchg [rbx+70h], rdx
0x18004852f  mov     rcx, rax
0x180048532  jnz     short loc_180048518
0x180048534  jmp     short loc_18004854A
0x180048536  lea     edx, [rax+1]
0x180048539  lock cmpxchg [rcx+rcx+10h], edx
0x18004853f  jz      short loc_18004854A
0x180048541  mov     eax, [rcx+rcx+10h]
0x180048545  cmp     eax, r9d
0x180048548  jnz     short loc_180048536
0x18004854a  mov     rax, [rbp+newString]
0x18004854e  mov     [rbp+string], rax
0x180048552  mov     [rbp+newString], 0
0x18004855a  mov     [rbp+var_30], 0
0x18004855e  mov     [rbp+var_40], 1
0x180048562  mov     [rbp+var_28], rbx
0x180048566  test    rbx, rbx
0x180048569  jz      short loc_1800485A1
0x18004856b  mov     rcx, [rbx+70h]
0x18004856f  test    rcx, rcx
0x180048572  js      short loc_180048598
0x180048574  cmp     ecx, r9d
0x180048577  jz      short loc_1800485A1
0x180048579  lea     rdx, [rcx+1]
0x18004857d  mov     rax, rcx
0x180048580  lock cmpxchg [rbx+70h], rdx
0x180048586  mov     rcx, rax
0x180048589  jnz     short loc_18004856F
0x18004858b  jmp     short loc_1800485A1
0x18004858d  lea     edx, [rax+1]
0x180048590  lock cmpxchg [rcx+rcx+10h], edx
0x180048596  jz      short loc_1800485A1
0x180048598  mov     eax, [rcx+rcx+10h]
0x18004859c  cmp     eax, r9d
0x18004859f  jnz     short loc_18004858D
0x1800485a1  mov     [rbp+var_20], esi
0x1800485a4  mov     [rbp+var_1C], r14d
0x1800485a8  mov     [rbp+var_18], r8
0x1800485ac  mov     [rbp+var_58], 3
0x1800485b3  mov     [rbp+var_54], 80h
0x1800485bb  lea     r9, [rbp+string]
0x1800485bf  mov     rdx, r15
0x1800485c2  lea     rcx, [rbp+var_58]
0x1800485c6  call    ??$MakeAsyncOperation@V?$CBasicResult@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@$0A@@Internal@Windows@@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@3@VComTaskPoolHandler@23@V_lambda_41cd686f22d980da34ef68bd8fac3600_@@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@W4ProtectionPolicyEvaluationResult@EnterpriseData@Security@Windows@@@Foundation@1@W4TrustLevel@@$$QEAV_lambda_41cd686f22d980da34ef68bd8fac3600_@@@Z; Windows::Internal::MakeAsyncOperation<Windows::Internal::CBasicResult<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult,0>,Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult,Windows::Internal::ComTaskPoolHandler,_lambda_41cd686f22d980da34ef68bd8fac3600_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Security::EnterpriseData::ProtectionPolicyEvaluationResult> * *,TrustLevel,_lambda_41cd686f22d980da34ef68bd8fac3600_ &&)
0x1800485cb  mov     edi, eax
0x1800485cd  mov     rcx, [rbp+var_28]
0x1800485d1  test    rcx, rcx
0x1800485d4  jz      short loc_1800485DB
0x1800485d6  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@UIDataPackageView2@567@UIDataPackageView3@567@UIDataPackageView4@567@UIDataPackageViewPriv@@U?$ChainInterfaces@U?$CloakedIid@UIAgileDataObject@@@WRL@Microsoft@@U?$CloakedIid@UIDataObject@@@23@VNil@Details@23@V5623@V5623@V5623@V5623@V5623@V5623@V5623@@23@UIDataObjectAsyncCapability@@UIInitializeWithWindow@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::DataTransfer::IDataPackageView,Windows::ApplicationModel::DataTransfer::IDataPackageView2,Windows::ApplicationModel::DataTransfer::IDataPackageView3,Windows::ApplicationModel::DataTransfer::IDataPackageView4,IDataPackageViewPriv,Microsoft::WRL::ChainInterfaces<Microsoft::WRL::CloakedIid<IAgileDataObject>,Microsoft::WRL::CloakedIid<IDataObject>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDataObjectAsyncCapability,IInitializeWithWindow,Microsoft::WRL::FtmBase>::Release(void)
0x1800485db  mov     rcx, [rbp+string]; string
0x1800485df  call    cs:__imp_WindowsDeleteString
0x1800485e5  test    edi, edi
0x1800485e7  jns     short loc_180048602
0x1800485e9  mov     rcx, [rbp+30h]; this
0x1800485ed  mov     r9d, edi; char *
0x1800485f0  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800485f7  mov     edx, 138Fh; void *
0x1800485fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180048601  nop
0x180048602  test    rbx, rbx
0x180048605  jz      short loc_18004860F
0x180048607  mov     rcx, rbx
0x18004860a  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIDataPackageView@DataTransfer@ApplicationModel@Windows@@UIDataPackageView2@567@UIDataPackageView3@567@UIDataPackageView4@567@UIDataPackageViewPriv@@U?$ChainInterfaces@U?$CloakedIid@UIAgileDataObject@@@WRL@Microsoft@@U?$CloakedIid@UIDataObject@@@23@VNil@Details@23@V5623@V5623@V5623@V5623@V5623@V5623@V5623@@23@UIDataObjectAsyncCapability@@UIInitializeWithWindow@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::ApplicationModel::DataTransfer::IDataPackageView,Windows::ApplicationModel::DataTransfer::IDataPackageView2,Windows::ApplicationModel::DataTransfer::IDataPackageView3,Windows::ApplicationModel::DataTransfer::IDataPackageView4,IDataPackageViewPriv,Microsoft::WRL::ChainInterfaces<Microsoft::WRL::CloakedIid<IAgileDataObject>,Microsoft::WRL::CloakedIid<IDataObject>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IDataObjectAsyncCapability,IInitializeWithWindow,Microsoft::WRL::FtmBase>::Release(void)
0x18004860f  mov     ebx, edi
0x180048611  mov     rcx, [rbp+newString]; string
0x180048615  call    cs:__imp_WindowsDeleteString
0x18004861b  mov     eax, ebx
0x18004861d  add     rsp, 78h
0x180048621  pop     r15
0x180048623  pop     r14
0x180048625  pop     rdi
0x180048626  pop     rsi
0x180048627  pop     rbx
0x180048628  pop     rbp
0x180048629  retn
```
