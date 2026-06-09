# CDataPackage::FireShareCompleted(char const *,__int64,IUnknown *,IUnknown *)

- ea: `0x180029890`
- end: `0x180029d6f`
- name: `?FireShareCompleted@CDataPackage@@UEAAJPEBD_JPEAUIUnknown@@2@Z`
- size: `1247`
- prototype: `int(CDataPackage *__hidden this, const char *, __int64, struct IUnknown *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002ad0`
- `0x180002ea0`
- `0x180008c2c`
- `0x180009d44`
- `0x180009e2c`
- `0x18000d204`
- `0x180025f94`
- `0x180029890`
- `0x180043b6c`
- `0x180048954`
- `0x18004f08c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002996f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002996f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029932`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029932`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002990b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002990b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800299ad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800299ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDataPackage::FireShareCompleted(
        RTL_SRWLOCK *this,
        const char *a2,
        __int64 a3,
        struct IUnknown *a4,
        struct IUnknown *a5)
{
  TraceLoggingCorrelationVector *v7; // rbx
  RTL_SRWLOCK *v8; // r12
  __int64 v9; // rdi
  HRESULT v10; // eax
  int v11; // edx
  unsigned int v12; // r8d
  int ActivationFactory; // eax
  unsigned int v14; // edi
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 *v26; // rax
  __int64 v27; // rdi
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 *v31; // rax
  __int64 v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  int v38[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v39; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v41; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v42; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING string; // [rsp+60h] [rbp-A0h] BYREF
  char Destination[144]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v41 = a3;
  v7 = TraceLoggingCorrelationVector::Extend(a2);
  TraceLoggingCorrelationVector::ToString(v7, Destination);
  DataPackageTracing::ShareCompletedEventFired<__int64 &>(&v41, Destination);
  v8 = this + 34;
  if ( this[34].Ptr )
  {
    AcquireSRWLockExclusive(this + 35);
    if ( v8->Ptr )
      v9 = (__int64)(*((_QWORD *)v8->Ptr + 3) - *((_QWORD *)v8->Ptr + 2)) >> 3;
    else
      v9 = 0;
    if ( this != (RTL_SRWLOCK *)-280LL )
      ReleaseSRWLockExclusive(this + 35);
    if ( v9 )
    {
      *(_QWORD *)v38 = 0;
      if ( a3 )
      {
        v39 = 0;
        string = 0;
        v10 = WindowsCreateStringReference(L"Windows.ApplicationModel.AppInfo", 0x20u, &hstringHeader, &string);
        if ( v10 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v10, v11, v12);
          JUMPOUT(0x180029D6ELL);
        }
        ActivationFactory = RoGetActivationFactory(string, &GUID_32cb3d52_6a9e_45b6_8d83_95b6458efcc0, &v39);
        v14 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EB1,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v38[0]);
          v15 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          v16 = *(_QWORD *)v38;
          if ( *(_QWORD *)v38 )
          {
            *(_QWORD *)v38 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          }
LABEL_15:
          if ( v7 )
            operator delete(v7, (const struct std::nothrow_t *)0x90);
          return v14;
        }
        v18 = (*(__int64 (__fastcall **)(__int64, __int64, int *))(*(_QWORD *)v39 + 48LL))(v39, a3, v38);
        v14 = v18;
        if ( v18 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EB3,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v18,
            v38[0]);
          v19 = v39;
          if ( v39 )
          {
            v39 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          v20 = *(_QWORD *)v38;
          if ( *(_QWORD *)v38 )
          {
            *(_QWORD *)v38 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
          }
          goto LABEL_15;
        }
        v21 = v39;
        if ( v39 )
        {
          v39 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
      }
      v22 = 0;
      v40 = 0;
      if ( a5 )
      {
        v23 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a5->lpVtbl->QueryInterface)(
                a5,
                &GUID_2fabe026_443e_4cda_af25_8d81070efd80,
                &v40);
        v14 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1EB9,
            (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
            (const char *)(unsigned int)v23,
            v38[0]);
          v24 = v40;
          if ( v40 )
          {
            v40 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          }
          v25 = *(_QWORD *)v38;
          if ( *(_QWORD *)v38 )
          {
            *(_QWORD *)v38 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
          }
          goto LABEL_15;
        }
        v22 = v40;
      }
      v41 = v22;
      v42 = *(_QWORD *)v38;
      v26 = (__int64 *)Microsoft::WRL::Details::Make<ShareTargetInfoImpl,Windows::ApplicationModel::IAppInfo *,Windows::ApplicationModel::DataTransfer::IShareProvider *>(
                         &v39,
                         &v42,
                         &v41);
      v27 = *v26;
      *v26 = 0;
      v28 = v39;
      if ( v39 )
      {
        v39 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      if ( !v27 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EBD,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
          (const char *)0x8007000ELL,
          v38[0]);
        v29 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = *(_QWORD *)v38;
        if ( *(_QWORD *)v38 )
        {
          *(_QWORD *)v38 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        }
LABEL_49:
        if ( v7 )
          operator delete(v7, (const struct std::nothrow_t *)0x90);
        return 2147942414LL;
      }
      v42 = v27;
      v31 = (__int64 *)Microsoft::WRL::Details::Make<ShareCompletedEventArgsImpl,Windows::ApplicationModel::DataTransfer::IShareTargetInfo *>(
                         &v41,
                         &v42);
      v32 = *v31;
      *v31 = 0;
      v33 = v41;
      if ( v41 )
      {
        v41 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      }
      if ( !v32 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1EC0,
          (unsigned int)"onecoreuap\\shell\\datatransfer\\lib\\datapackage.cpp",
          (const char *)0x8007000ELL,
          v38[0]);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        v34 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
        }
        v35 = *(_QWORD *)v38;
        if ( *(_QWORD *)v38 )
        {
          *(_QWORD *)v38 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        goto LABEL_49;
      }
      Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::DataTransfer::DataPackage *,Windows::ApplicationModel::DataTransfer::ShareCompletedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<CDataPackage *,Windows::ApplicationModel::DataTransfer::IShareCompletedEventArgs *>(
        &this[34],
        &this[-8],
        v32);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v36 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
      }
      v37 = *(_QWORD *)v38;
      if ( *(_QWORD *)v38 )
      {
        *(_QWORD *)v38 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
      }
    }
  }
  if ( v7 )
    operator delete(v7, (const struct std::nothrow_t *)0x90);
  return 0;
}

```

## disassembly

```asm
0x180029890  mov     [rsp-8+arg_18], rbx
0x180029895  push    rbp
0x180029896  push    rsi
0x180029897  push    rdi
0x180029898  push    r12
0x18002989a  push    r13
0x18002989c  push    r14
0x18002989e  push    r15
0x1800298a0  lea     rbp, [rsp-10h]
0x1800298a5  sub     rsp, 110h
0x1800298ac  mov     rax, cs:__security_cookie
0x1800298b3  xor     rax, rsp
0x1800298b6  mov     [rbp+40h+var_40], rax
0x1800298ba  mov     r15, r8
0x1800298bd  mov     r13, rcx
0x1800298c0  mov     [rsp+140h+var_108], r8
0x1800298c5  mov     r14, [rbp+40h+arg_20]
0x1800298c9  mov     rcx, rdx; char *
0x1800298cc  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x1800298d1  mov     rbx, rax
0x1800298d4  lea     rdx, [rsp+140h+Destination]; Destination
0x1800298d9  mov     rcx, rax; this
0x1800298dc  call    ?ToString@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::ToString(char *)
0x1800298e1  lea     rdx, [rsp+140h+Destination]
0x1800298e6  lea     rcx, [rsp+140h+var_108]
0x1800298eb  call    ??$ShareCompletedEventFired@AEA_J@DataPackageTracing@@SAXAEA_JPEBD@Z; DataPackageTracing::ShareCompletedEventFired<__int64 &>(__int64 &,char const *)
0x1800298f0  lea     r12, [r13+110h]
0x1800298f7  xor     esi, esi
0x1800298f9  cmp     [r12], rsi
0x1800298fd  jz      loc_180029D2C
0x180029903  lea     rsi, [r12+8]
0x180029908  mov     rcx, rsi; SRWLock
0x18002990b  call    cs:__imp_AcquireSRWLockExclusive
0x180029911  mov     rax, [r12]
0x180029915  test    rax, rax
0x180029918  jnz     short loc_18002991E
0x18002991a  xor     edi, edi
0x18002991c  jmp     short loc_18002992A
0x18002991e  mov     rdi, [rax+18h]
0x180029922  sub     rdi, [rax+10h]
0x180029926  sar     rdi, 3
0x18002992a  test    rsi, rsi
0x18002992d  jz      short loc_180029938
0x18002992f  mov     rcx, rsi; SRWLock
0x180029932  call    cs:__imp_ReleaseSRWLockExclusive
0x180029938  xor     esi, esi
0x18002993a  test    rdi, rdi
0x18002993d  jz      loc_180029D2C
0x180029943  mov     qword ptr [rsp+140h+var_120], rsi; int
0x180029948  test    r15, r15
0x18002994b  jz      loc_180029ADC
0x180029951  mov     [rsp+140h+var_118], rsi
0x180029956  mov     [rsp+140h+string], rsi
0x18002995b  lea     r9, [rsp+140h+string]; string
0x180029960  lea     r8, [rsp+140h+hstringHeader]; hstringHeader
0x180029965  lea     edx, [rsi+20h]; length
0x180029968  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_AppInfo@@3QBGB; "Windows.ApplicationModel.AppInfo"
0x18002996f  call    cs:__imp_WindowsCreateStringReference
0x180029975  test    eax, eax
0x180029977  js      loc_180029D67
0x18002997d  mov     rdi, [rsp+140h+string]
0x180029982  mov     rcx, [rsp+140h+var_118]
0x180029987  test    rcx, rcx
0x18002998a  jz      short loc_18002999E
0x18002998c  mov     [rsp+140h+var_118], rsi
0x180029991  mov     rax, [rcx]
0x180029994  mov     rax, [rax+10h]
0x180029998  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002999d  nop
0x18002999e  lea     r8, [rsp+140h+var_118]
0x1800299a3  lea     rdx, _GUID_32cb3d52_6a9e_45b6_8d83_95b6458efcc0
0x1800299aa  mov     rcx, rdi
0x1800299ad  call    cs:__imp_RoGetActivationFactory
0x1800299b3  mov     edi, eax
0x1800299b5  test    eax, eax
0x1800299b7  jns     short loc_180029A23
0x1800299b9  mov     rcx, [rbp+48h]; this
0x1800299bd  mov     r9d, eax; char *
0x1800299c0  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x1800299c7  mov     edx, 1EB1h; void *
0x1800299cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299d1  nop
0x1800299d2  mov     rcx, [rsp+140h+var_118]
0x1800299d7  test    rcx, rcx
0x1800299da  jz      short loc_1800299EE
0x1800299dc  mov     [rsp+140h+var_118], rsi
0x1800299e1  mov     rax, [rcx]
0x1800299e4  mov     rax, [rax+10h]
0x1800299e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299ed  nop
0x1800299ee  mov     rcx, qword ptr [rsp+140h+var_120]
0x1800299f3  test    rcx, rcx
0x1800299f6  jz      short loc_180029A0A
0x1800299f8  mov     qword ptr [rsp+140h+var_120], rsi
0x1800299fd  mov     rax, [rcx]
0x180029a00  mov     rax, [rax+10h]
0x180029a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a09  nop
0x180029a0a  test    rbx, rbx
0x180029a0d  jz      short loc_180029A1C
0x180029a0f  mov     edx, 90h; struct std::nothrow_t *
0x180029a14  mov     rcx, rbx; void *
0x180029a17  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029a1c  mov     eax, edi
0x180029a1e  jmp     loc_180029D40
0x180029a23  mov     rdi, [rsp+140h+var_118]
0x180029a28  mov     rax, [rdi]
0x180029a2b  mov     rsi, [rax+30h]
0x180029a2f  mov     rcx, qword ptr [rsp+140h+var_120]
0x180029a34  test    rcx, rcx
0x180029a37  jz      short loc_180029A4F
0x180029a39  mov     qword ptr [rsp+140h+var_120], 0; int
0x180029a42  mov     r8, [rcx]
0x180029a45  mov     rax, [r8+10h]
0x180029a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a4e  nop
0x180029a4f  lea     r8, [rsp+140h+var_120]
0x180029a54  mov     rdx, r15
0x180029a57  mov     rcx, rdi
0x180029a5a  mov     rax, rsi
0x180029a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a62  mov     edi, eax
0x180029a64  xor     esi, esi
0x180029a66  test    eax, eax
0x180029a68  jns     short loc_180029AC0
0x180029a6a  mov     rcx, [rbp+48h]; this
0x180029a6e  mov     r9d, eax; char *
0x180029a71  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180029a78  mov     edx, 1EB3h; void *
0x180029a7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a82  nop
0x180029a83  mov     rcx, [rsp+140h+var_118]
0x180029a88  test    rcx, rcx
0x180029a8b  jz      short loc_180029A9F
0x180029a8d  mov     [rsp+140h+var_118], rsi
0x180029a92  mov     rax, [rcx]
0x180029a95  mov     rax, [rax+10h]
0x180029a99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a9e  nop
0x180029a9f  mov     rcx, qword ptr [rsp+140h+var_120]
0x180029aa4  test    rcx, rcx
0x180029aa7  jz      short loc_180029ABB
0x180029aa9  mov     qword ptr [rsp+140h+var_120], rsi
0x180029aae  mov     rax, [rcx]
0x180029ab1  mov     rax, [rax+10h]
0x180029ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029aba  nop
0x180029abb  jmp     loc_180029A0A
0x180029ac0  mov     rcx, [rsp+140h+var_118]
0x180029ac5  test    rcx, rcx
0x180029ac8  jz      short loc_180029ADC
0x180029aca  mov     [rsp+140h+var_118], rsi
0x180029acf  mov     rax, [rcx]
0x180029ad2  mov     rax, [rax+10h]
0x180029ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029adb  nop
0x180029adc  mov     rax, rsi
0x180029adf  mov     [rsp+140h+var_110], rax
0x180029ae4  test    r14, r14
0x180029ae7  jz      short loc_180029B64
0x180029ae9  mov     rax, [r14]
0x180029aec  lea     r8, [rsp+140h+var_110]
0x180029af1  lea     rdx, _GUID_2fabe026_443e_4cda_af25_8d81070efd80
0x180029af8  mov     rcx, r14
0x180029afb  mov     rax, [rax]
0x180029afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b03  mov     edi, eax
0x180029b05  test    eax, eax
0x180029b07  jns     short loc_180029B5F
0x180029b09  mov     rcx, [rbp+48h]; this
0x180029b0d  mov     r9d, eax; char *
0x180029b10  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180029b17  mov     edx, 1EB9h; void *
0x180029b1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029b21  nop
0x180029b22  mov     rcx, [rsp+140h+var_110]
0x180029b27  test    rcx, rcx
0x180029b2a  jz      short loc_180029B3E
0x180029b2c  mov     [rsp+140h+var_110], rsi
0x180029b31  mov     rax, [rcx]
0x180029b34  mov     rax, [rax+10h]
0x180029b38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b3d  nop
0x180029b3e  mov     rcx, qword ptr [rsp+140h+var_120]
0x180029b43  test    rcx, rcx
0x180029b46  jz      short loc_180029B5A
0x180029b48  mov     qword ptr [rsp+140h+var_120], rsi
0x180029b4d  mov     rax, [rcx]
0x180029b50  mov     rax, [rax+10h]
0x180029b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029b59  nop
0x180029b5a  jmp     loc_180029A0A
0x180029b5f  mov     rax, [rsp+140h+var_110]
0x180029b64  mov     [rsp+140h+var_108], rax
0x180029b69  mov     rax, qword ptr [rsp+140h+var_120]
0x180029b6e  mov     [rsp+140h+var_100], rax
0x180029b73  lea     r8, [rsp+140h+var_108]
0x180029b78  lea     rdx, [rsp+140h+var_100]
0x180029b7d  lea     rcx, [rsp+140h+var_118]
0x180029b82  call    ??$Make@VShareTargetInfoImpl@@PEAUIAppInfo@ApplicationModel@Windows@@PEAUIShareProvider@DataTransfer@34@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VShareTargetInfoImpl@@@12@$$QEAPEAUIAppInfo@ApplicationModel@Windows@@$$QEAPEAUIShareProvider@DataTransfer@56@@Z; Microsoft::WRL::Details::Make<ShareTargetInfoImpl,Windows::ApplicationModel::IAppInfo *,Windows::ApplicationModel::DataTransfer::IShareProvider *>(Windows::ApplicationModel::IAppInfo * &&,Windows::ApplicationModel::DataTransfer::IShareProvider * &&)
0x180029b87  mov     rdi, [rax]
0x180029b8a  mov     [rax], rsi
0x180029b8d  mov     rcx, [rsp+140h+var_118]
0x180029b92  test    rcx, rcx
0x180029b95  jz      short loc_180029BA9
0x180029b97  mov     [rsp+140h+var_118], rsi
0x180029b9c  mov     rax, [rcx]
0x180029b9f  mov     rax, [rax+10h]
0x180029ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ba8  nop
0x180029ba9  test    rdi, rdi
0x180029bac  jnz     short loc_180029C07
0x180029bae  mov     rcx, [rbp+48h]; this
0x180029bb2  mov     r9d, 8007000Eh; char *
0x180029bb8  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180029bbf  mov     edx, 1EBDh; void *
0x180029bc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029bc9  nop
0x180029bca  mov     rcx, [rsp+140h+var_110]
0x180029bcf  test    rcx, rcx
0x180029bd2  jz      short loc_180029BE6
0x180029bd4  mov     [rsp+140h+var_110], rsi
0x180029bd9  mov     rax, [rcx]
0x180029bdc  mov     rax, [rax+10h]
0x180029be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029be5  nop
0x180029be6  mov     rcx, qword ptr [rsp+140h+var_120]
0x180029beb  test    rcx, rcx
0x180029bee  jz      short loc_180029C02
0x180029bf0  mov     qword ptr [rsp+140h+var_120], rsi
0x180029bf5  mov     rax, [rcx]
0x180029bf8  mov     rax, [rax+10h]
0x180029bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c01  nop
0x180029c02  jmp     loc_180029CA9
0x180029c07  mov     [rsp+140h+var_100], rdi
0x180029c0c  lea     rdx, [rsp+140h+var_100]
0x180029c11  lea     rcx, [rsp+140h+var_108]
0x180029c16  call    ??$Make@VShareCompletedEventArgsImpl@@PEAUIShareTargetInfo@DataTransfer@ApplicationModel@Windows@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VShareCompletedEventArgsImpl@@@12@$$QEAPEAUIShareTargetInfo@DataTransfer@ApplicationModel@Windows@@@Z; Microsoft::WRL::Details::Make<ShareCompletedEventArgsImpl,Windows::ApplicationModel::DataTransfer::IShareTargetInfo *>(Windows::ApplicationModel::DataTransfer::IShareTargetInfo * &&)
0x180029c1b  mov     rsi, [rax]
0x180029c1e  xor     r14d, r14d
0x180029c21  mov     [rax], r14
0x180029c24  mov     rcx, [rsp+140h+var_108]
0x180029c29  test    rcx, rcx
0x180029c2c  jz      short loc_180029C40
0x180029c2e  mov     [rsp+140h+var_108], r14
0x180029c33  mov     rax, [rcx]
0x180029c36  mov     rax, [rax+10h]
0x180029c3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c3f  nop
0x180029c40  test    rsi, rsi
0x180029c43  jnz     short loc_180029CC2
0x180029c45  mov     rcx, [rbp+48h]; this
0x180029c49  mov     r9d, 8007000Eh; char *
0x180029c4f  lea     r8, aOnecoreuapShel; "onecoreuap\\shell\\datatransfer\\lib\\d"...
0x180029c56  mov     edx, 1EC0h; void *
0x180029c5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029c60  nop
0x180029c61  mov     rax, [rdi]
0x180029c64  mov     rcx, rdi
0x180029c67  mov     rax, [rax+10h]
0x180029c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c70  nop
0x180029c71  mov     rcx, [rsp+140h+var_110]
0x180029c76  test    rcx, rcx
0x180029c79  jz      short loc_180029C8D
0x180029c7b  mov     [rsp+140h+var_110], r14
0x180029c80  mov     rax, [rcx]
0x180029c83  mov     rax, [rax+10h]
0x180029c87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c8c  nop
0x180029c8d  mov     rcx, qword ptr [rsp+140h+var_120]
0x180029c92  test    rcx, rcx
0x180029c95  jz      short loc_180029CA9
0x180029c97  mov     qword ptr [rsp+140h+var_120], r14
0x180029c9c  mov     rax, [rcx]
0x180029c9f  mov     rax, [rax+10h]
0x180029ca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ca8  nop
0x180029ca9  test    rbx, rbx
0x180029cac  jz      short loc_180029CBB
0x180029cae  mov     edx, 90h; struct std::nothrow_t *
0x180029cb3  mov     rcx, rbx; void *
0x180029cb6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180029cbb  mov     eax, 8007000Eh
0x180029cc0  jmp     short loc_180029D40
0x180029cc2  lea     rdx, [r13-40h]
0x180029cc6  mov     r8, rsi
0x180029cc9  mov     rcx, r12
0x180029ccc  call    ??$InvokeAll@PEAVCDataPackage@@PEAUIShareCompletedEventArgs@DataTransfer@ApplicationModel@Windows@@@?$EventSource@U?$ITypedEventHandler@PEAVDataPackage@DataTransfer@ApplicationModel@Windows@@PEAVShareCompletedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$01@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAVCDataPackage@@PEAUIShareCompletedEventArgs@DataTransfer@ApplicationModel@Windows@@@Z; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::ApplicationModel::DataTransfer::DataPackage *,Windows::ApplicationModel::DataTransfer::ShareCompletedEventArgs *>,Microsoft::WRL::InvokeModeOptions<2>>::InvokeAll<CDataPackage *,Windows::ApplicationModel::DataTransfer::IShareCompletedEventArgs *>(CDataPackage *,Windows::ApplicationModel::DataTransfer::IShareCompletedEventArgs *)
0x180029cd1  nop
0x180029cd2  mov     rax, [rsi]
0x180029cd5  mov     rcx, rsi
0x180029cd8  mov     rax, [rax+10h]
0x180029cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ce1  nop
0x180029ce2  mov     rax, [rdi]
0x180029ce5  mov     rcx, rdi
0x180029ce8  mov     rax, [rax+10h]
0x180029cec  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
