# _lambda_34074e6b262c35511414209380769e3f_::operator()(Windows::Internal::AsyncStage,long,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,Windows::Internal::CBasicResult<Windows::System::LaunchUriStatus,3> &)

- ea: `0x1800e4ad0`
- end: `0x1800e4e41`
- name: `??R_lambda_34074e6b262c35511414209380769e3f_@@QEAAJW4AsyncStage@Internal@Windows@@JPEAUIUriRuntimeClass@Foundation@3@PEAUILauncherOptions@System@3@PEAUITelemetryCorrelationVector@@AEAV?$CBasicResult@W4LaunchUriStatus@System@Windows@@$02@23@@Z`
- size: `881`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, struct Windows::Foundation::IUriRuntimeClass *, __int64, PCWSTR, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2214`

## callees

- `0x1800049bc`
- `0x1800398c8`
- `0x18004966c`
- `0x18005591c`
- `0x180057084`
- `0x1800570b4`
- `0x180063820`
- `0x18006be44`
- `0x18006c64c`
- `0x18006f528`
- `0x18006f680`
- `0x180073094`
- `0x1800815b8`
- `0x180081610`
- `0x18008a030`
- `0x1800e0ab0`
- `0x1800e1794`
- `0x1800e1838`
- `0x1800e1b54`
- `0x1800e4ad0`
- `0x1800e8280`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4c94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4c94`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4ca4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4d78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4dee`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4b95`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4de0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4dee`

## pseudocode

```c
__int64 __fastcall _lambda_34074e6b262c35511414209380769e3f_::operator()(
        __int64 a1,
        unsigned int a2,
        int a3,
        struct Windows::Foundation::IUriRuntimeClass *a4,
        __int64 a5,
        PCWSTR a6,
        __int64 a7)
{
  unsigned int v8; // ebx
  unsigned int v9; // r14d
  __int64 v11; // rax
  bool v12; // r12
  __int64 v13; // r15
  void (__fastcall *v14)(__int64, HSTRING *); // rbx
  void (__fastcall *v15)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *); // rbx
  int IsCallerRunningOnLock; // ebx
  int Owner; // eax
  const unsigned __int16 *v18; // rdx
  HWND v19; // r14
  const struct _GUID *v20; // rdx
  bool v22; // [rsp+80h] [rbp-80h] BYREF
  HWND v23; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v24; // [rsp+90h] [rbp-70h]
  PCWSTR v25; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v26; // [rsp+A0h] [rbp-60h] BYREF
  HSTRING string; // [rsp+A8h] [rbp-58h] BYREF
  PCWSTR StringRawBuffer; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-48h] BYREF
  struct IUnknown *v30; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v31; // [rsp+C8h] [rbp-38h]
  __int64 v32; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v33[80]; // [rsp+E0h] [rbp-20h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v35[128]; // [rsp+150h] [rbp+50h] BYREF

  v8 = a3;
  v9 = a2;
  v24 = a2;
  StringRawBuffer = (PCWSTR)a4;
  v32 = a5;
  v25 = a6;
  v11 = a7;
  v31 = a7;
  if ( a2 == 1 )
  {
    v12 = 0;
    if ( a3 >= 0 )
    {
      v13 = a1 + 88;
      wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
        (struct wil::details::IFailureCallback *)(a1 + 88),
        (wil::ActivityThreadWatcher *)v33);
      string = 0;
      if ( a5 )
      {
        v14 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a5 + 88LL);
        WindowsDeleteString(0);
        string = 0;
        v14(a5, &string);
      }
      v26 = 0;
      v15 = *(void (__fastcall **)(struct Windows::Foundation::IUriRuntimeClass *, HSTRING *))(*(_QWORD *)a4 + 136LL);
      WindowsDeleteString(0);
      v26 = 0;
      v15(a4, &v26);
      v29 = 0;
      IsCallerRunningOnLock = CLockScreenInterop::Initialize((CLockScreenInterop *)&v29);
      v22 = 0;
      v23 = 0;
      if ( IsCallerRunningOnLock < 0 )
        goto LABEL_23;
      Owner = Windows::Internal::AsyncWindowOperation::GetOwner(
                (Windows::Internal::AsyncWindowOperation *)(a1 + 40),
                &v23);
      if ( Owner < 0 )
      {
        if ( Owner == -2147023496 && *(_BYTE *)(a1 + 74) )
          v19 = *(HWND *)(a1 + 80);
        else
          v19 = v23;
      }
      else
      {
        v18 = *(const unsigned __int16 **)(a1 + 8);
        v19 = v23;
        if ( v18 )
        {
          IsCallerRunningOnLock = CLockScreenInterop::IsCallerRunningOnLock(
                                    (CLockScreenInterop *)&v29,
                                    v18,
                                    (unsigned __int64)v23,
                                    &v22);
          v12 = v22;
        }
        if ( IsCallerRunningOnLock < 0 )
          goto LABEL_22;
      }
      if ( v12 )
      {
        v30 = 0;
        BYTE2(v23) = 0;
        LOBYTE(v23) = *(_BYTE *)(a1 + 36);
        BYTE1(v23) = *(_BYTE *)(a1 + 72);
        BYTE3(v23) = *(_BYTE *)(a1 + 73);
        v25 = *(PCWSTR *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader) + 24);
        IsCallerRunningOnLock = Microsoft::WRL::Details::MakeAndInitialize<CCachedLaunchUriRequest,CCachedLaunchUriRequest,Windows::Foundation::IUriRuntimeClass * &,HSTRING__ *,PendingLaunchConfiguration &,CAutoHandle<void *>,Windows::System::ILauncherOptions * &>(
                                  &v30,
                                  &StringRawBuffer,
                                  &v25,
                                  &v23,
                                  a1 + 24,
                                  &v32);
        if ( IsCallerRunningOnLock >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v25 = WindowsGetStringRawBuffer(v26, 0);
          LauncherDesktopProvider::LaunchUri::LaunchFromLockScreen<CMemString<CMemString_PolicyCoTaskMem> &,unsigned short const *,unsigned short const *>(
            v13,
            a1 + 8,
            &v25,
            &StringRawBuffer);
          IsCallerRunningOnLock = CLockScreenInterop::CacheLaunchRequest((CLockScreenInterop *)&v29, v30);
        }
        Microsoft::WRL::ComPtr<CCachedLaunchUriRequest>::InternalRelease(&v30);
      }
      else
      {
        v23 = 0;
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
        IsCallerRunningOnLock = Windows::Internal::AsyncWindowOperation::GetWindowData(
                                  (Windows::Internal::AsyncWindowOperation *)(a1 + 40),
                                  v20,
                                  (void **)&v23);
        if ( IsCallerRunningOnLock >= 0 )
        {
          CBrokeredLauncher::CLaunchHelper::CLaunchHelper(
            (__int64)v35,
            (__int64)v25,
            *(_DWORD *)a1,
            *(_QWORD *)(a1 + 8),
            *(_DWORD *)(a1 + 32),
            *(_BYTE *)(a1 + 36),
            *(_QWORD *)(a1 + 24),
            (__int64)v23,
            a5,
            0,
            *(_BYTE *)(a1 + 72),
            *(_BYTE *)(a1 + 73),
            0,
            0,
            (__int64)v19);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v25 = WindowsGetStringRawBuffer(v26, 0);
          LauncherDesktopProvider::LaunchUri::LaunchUriRequest<CMemString<CMemString_PolicyCoTaskMem> &,unsigned short const *,unsigned short const *>(
            v13,
            a1 + 8,
            &v25,
            &StringRawBuffer);
          IsCallerRunningOnLock = CBrokeredLauncher::CLaunchHelper::LaunchUri(
                                    (CBrokeredLauncher::CLaunchHelper *)v35,
                                    a4);
          CBrokeredLauncher::CLaunchHelper::~CLaunchHelper((CBrokeredLauncher::CLaunchHelper *)v35);
        }
        Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v23);
      }
LABEL_22:
      v9 = v24;
LABEL_23:
      *(_DWORD *)(v31 + 16) = (unsigned int)IsCallerRunningOnLock >> 31;
      wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        v13,
        (unsigned int)IsCallerRunningOnLock);
      v8 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
      WindowsDeleteString(v26);
      v26 = 0;
      WindowsDeleteString(string);
      string = 0;
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v33);
      v11 = v31;
    }
  }
  return Windows::Internal::AsyncWindowOperation::ManageStage(a1 + 40, v9, v8, v11);
}

```

## disassembly

```asm
0x1800e4ad0  mov     [rsp-8+arg_8], rbx
0x1800e4ad5  push    rbp
0x1800e4ad6  push    rsi
0x1800e4ad7  push    rdi
0x1800e4ad8  push    r12
0x1800e4ada  push    r13
0x1800e4adc  push    r14
0x1800e4ade  push    r15
0x1800e4ae0  lea     rbp, [rsp-0E0h]
0x1800e4ae8  sub     rsp, 1E0h
0x1800e4aef  mov     rax, cs:__security_cookie
0x1800e4af6  xor     rax, rsp
0x1800e4af9  mov     [rbp+110h+var_40], rax
0x1800e4b00  mov     r13, r9
0x1800e4b03  mov     ebx, r8d
0x1800e4b06  mov     r14d, edx
0x1800e4b09  mov     [rbp+110h+var_180], edx
0x1800e4b0c  mov     rdi, rcx
0x1800e4b0f  mov     rsi, [rbp+110h+arg_20]
0x1800e4b16  mov     [rbp+110h+var_160], r9
0x1800e4b1a  mov     [rbp+110h+var_140], rsi
0x1800e4b1e  mov     rax, [rbp+110h+arg_28]
0x1800e4b25  mov     [rbp+110h+var_178], rax
0x1800e4b29  mov     rax, [rbp+110h+arg_30]
0x1800e4b30  mov     [rbp+110h+var_148], rax
0x1800e4b34  cmp     edx, 1
0x1800e4b37  jnz     loc_1800E4E05
0x1800e4b3d  xor     r12d, r12d
0x1800e4b40  test    ebx, ebx
0x1800e4b42  js      loc_1800E4E05
0x1800e4b48  lea     r15, [rcx+58h]
0x1800e4b4c  lea     rdx, [rbp+110h+var_130]; this
0x1800e4b50  mov     rcx, r15; struct wil::details::IFailureCallback *
0x1800e4b53  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800e4b58  nop
0x1800e4b59  mov     [rbp+110h+string], r12
0x1800e4b5d  test    rsi, rsi
0x1800e4b60  jz      short loc_1800E4B84
0x1800e4b62  mov     rax, [rsi]
0x1800e4b65  mov     rbx, [rax+58h]
0x1800e4b69  xor     ecx, ecx; string
0x1800e4b6b  call    cs:__imp_WindowsDeleteString
0x1800e4b71  mov     [rbp+110h+string], r12
0x1800e4b75  lea     rdx, [rbp+110h+string]
0x1800e4b79  mov     rcx, rsi
0x1800e4b7c  mov     rax, rbx
0x1800e4b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4b84  mov     [rbp+110h+var_170], r12
0x1800e4b88  mov     rax, [r13+0]
0x1800e4b8c  mov     rbx, [rax+88h]
0x1800e4b93  xor     ecx, ecx; string
0x1800e4b95  call    cs:__imp_WindowsDeleteString
0x1800e4b9b  mov     [rbp+110h+var_170], r12
0x1800e4b9f  lea     rdx, [rbp+110h+var_170]
0x1800e4ba3  mov     rcx, r13
0x1800e4ba6  mov     rax, rbx
0x1800e4ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4bae  mov     [rbp+110h+var_158], r12
0x1800e4bb2  lea     rcx, [rbp+110h+var_158]; this
0x1800e4bb6  call    ?Initialize@CLockScreenInterop@@QEAAJXZ; CLockScreenInterop::Initialize(void)
0x1800e4bbb  mov     ebx, eax
0x1800e4bbd  mov     [rbp+110h+var_190], r12b
0x1800e4bc1  mov     [rbp+110h+var_188], 0
0x1800e4bc9  test    eax, eax
0x1800e4bcb  js      loc_1800E4DBA
0x1800e4bd1  lea     rcx, [rdi+28h]; this
0x1800e4bd5  lea     rdx, [rbp+110h+var_188]; HWND *
0x1800e4bd9  call    ?GetOwner@AsyncWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::AsyncWindowOperation::GetOwner(HWND__ * *)
0x1800e4bde  test    eax, eax
0x1800e4be0  js      short loc_1800E4C0E
0x1800e4be2  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800e4be6  mov     r14, [rbp+110h+var_188]
0x1800e4bea  test    rdx, rdx
0x1800e4bed  jz      short loc_1800E4C05
0x1800e4bef  lea     r9, [rbp+110h+var_190]; bool *
0x1800e4bf3  mov     r8, r14; unsigned __int64
0x1800e4bf6  lea     rcx, [rbp+110h+var_158]; this
0x1800e4bfa  call    ?IsCallerRunningOnLock@CLockScreenInterop@@QEAAJPEBG_KPEA_N@Z; CLockScreenInterop::IsCallerRunningOnLock(ushort const *,unsigned __int64,bool *)
0x1800e4bff  mov     ebx, eax
0x1800e4c01  mov     r12b, [rbp+110h+var_190]
0x1800e4c05  test    ebx, ebx
0x1800e4c07  jns     short loc_1800E4C25
0x1800e4c09  jmp     loc_1800E4DB6
0x1800e4c0e  cmp     eax, 80070578h
0x1800e4c13  jnz     short loc_1800E4C21
0x1800e4c15  cmp     byte ptr [rdi+4Ah], 0
0x1800e4c19  jz      short loc_1800E4C21
0x1800e4c1b  mov     r14, [rdi+50h]
0x1800e4c1f  jmp     short loc_1800E4C25
0x1800e4c21  mov     r14, [rbp+110h+var_188]
0x1800e4c25  test    r12b, r12b
0x1800e4c28  jz      loc_1800E4CDF
0x1800e4c2e  mov     [rbp+110h+var_150], 0
0x1800e4c36  mov     byte ptr [rbp+110h+var_188+2], 0
0x1800e4c3a  mov     al, [rdi+24h]
0x1800e4c3d  mov     byte ptr [rbp+110h+var_188], al
0x1800e4c40  mov     al, [rdi+48h]
0x1800e4c43  mov     byte ptr [rbp+110h+var_188+1], al
0x1800e4c46  mov     al, [rdi+49h]
0x1800e4c49  mov     byte ptr [rbp+110h+var_188+3], al
0x1800e4c4c  lea     rdx, [rdi+8]
0x1800e4c50  lea     rcx, [rbp+110h+hstringHeader]; hstringHeader
0x1800e4c54  call    ??$?0V?$CMemString@UCMemString_PolicyCoTaskMem@@@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$CMemString@UCMemString_PolicyCoTaskMem@@@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(CMemString<CMemString_PolicyCoTaskMem> const &,Microsoft::WRL::Details::Dummy)
0x1800e4c59  mov     rcx, [rax+18h]
0x1800e4c5d  mov     [rbp+110h+var_178], rcx
0x1800e4c61  lea     rax, [rdi+18h]
0x1800e4c65  lea     rcx, [rbp+110h+var_140]
0x1800e4c69  mov     [rsp+210h+var_1E8], rcx
0x1800e4c6e  mov     [rsp+210h+var_1F0], rax
0x1800e4c73  lea     r9, [rbp+110h+var_188]
0x1800e4c77  lea     r8, [rbp+110h+var_178]
0x1800e4c7b  lea     rdx, [rbp+110h+var_160]
0x1800e4c7f  lea     rcx, [rbp+110h+var_150]
0x1800e4c83  call    ??$MakeAndInitialize@VCCachedLaunchUriRequest@@V1@AEAPEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@AEAUPendingLaunchConfiguration@@V?$CAutoHandle@PEAX@@AEAPEAUILauncherOptions@System@4@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCCachedLaunchUriRequest@@@WRL@Microsoft@@@012@AEAPEAUIUriRuntimeClass@Foundation@Windows@@$$QEAPEAUHSTRING__@@AEAUPendingLaunchConfiguration@@$$QEAV?$CAutoHandle@PEAX@@AEAPEAUILauncherOptions@System@6@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCachedLaunchUriRequest,CCachedLaunchUriRequest,Windows::Foundation::IUriRuntimeClass * &,HSTRING__ *,PendingLaunchConfiguration &,CAutoHandle<void *>,Windows::System::ILauncherOptions * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CCachedLaunchUriRequest>>,Windows::Foundation::IUriRuntimeClass * &,HSTRING__ * &&,PendingLaunchConfiguration &,CAutoHandle<void *> &&,Windows::System::ILauncherOptions * &)
0x1800e4c88  mov     ebx, eax
0x1800e4c8a  test    eax, eax
0x1800e4c8c  js      short loc_1800E4CD1
0x1800e4c8e  xor     edx, edx; length
0x1800e4c90  mov     rcx, [rbp+110h+string]; string
0x1800e4c94  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4c9a  mov     [rbp+110h+var_160], rax
0x1800e4c9e  xor     edx, edx; length
0x1800e4ca0  mov     rcx, [rbp+110h+var_170]; string
0x1800e4ca4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4caa  mov     [rbp+110h+var_178], rax
0x1800e4cae  lea     r9, [rbp+110h+var_160]
0x1800e4cb2  lea     r8, [rbp+110h+var_178]
0x1800e4cb6  lea     rdx, [rdi+8]
0x1800e4cba  mov     rcx, r15
0x1800e4cbd  call    ??$LaunchFromLockScreen@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchUri@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchUri::LaunchFromLockScreen<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x1800e4cc2  mov     rdx, [rbp+110h+var_150]; struct IUnknown *
0x1800e4cc6  lea     rcx, [rbp+110h+var_158]; this
0x1800e4cca  call    ?CacheLaunchRequest@CLockScreenInterop@@QEAAJPEAUIUnknown@@@Z; CLockScreenInterop::CacheLaunchRequest(IUnknown *)
0x1800e4ccf  mov     ebx, eax
0x1800e4cd1  lea     rcx, [rbp+110h+var_150]
0x1800e4cd5  call    ?InternalRelease@?$ComPtr@VCCachedLaunchUriRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CCachedLaunchUriRequest>::InternalRelease(void)
0x1800e4cda  jmp     loc_1800E4DB6
0x1800e4cdf  mov     [rbp+110h+var_188], 0
0x1800e4ce7  lea     rcx, [rbp+110h+var_188]
0x1800e4ceb  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e4cf0  lea     r8, [rbp+110h+var_188]; void **
0x1800e4cf4  lea     rcx, [rdi+28h]; this
0x1800e4cf8  call    ?GetWindowData@AsyncWindowOperation@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::AsyncWindowOperation::GetWindowData(_GUID const &,void * *)
0x1800e4cfd  mov     ebx, eax
0x1800e4cff  xor     ecx, ecx
0x1800e4d01  test    eax, eax
0x1800e4d03  js      loc_1800E4DAD
0x1800e4d09  mov     [rsp+210h+var_1A0], r14
0x1800e4d0e  mov     [rsp+210h+var_1A8], cl
0x1800e4d12  mov     [rsp+210h+var_1B0], ecx
0x1800e4d16  mov     al, [rdi+49h]
0x1800e4d19  mov     [rsp+210h+var_1B8], al
0x1800e4d1d  mov     al, [rdi+48h]
0x1800e4d20  mov     [rsp+210h+var_1C0], al
0x1800e4d24  mov     [rsp+210h+var_1C8], rcx
0x1800e4d29  mov     [rsp+210h+var_1D0], rsi
0x1800e4d2e  mov     rax, [rbp+110h+var_188]
0x1800e4d32  mov     [rsp+210h+var_1D8], rax
0x1800e4d37  mov     rax, [rdi+18h]
0x1800e4d3b  mov     [rsp+210h+var_1E0], rax
0x1800e4d40  mov     al, [rdi+24h]
0x1800e4d43  mov     byte ptr [rsp+210h+var_1E8], al
0x1800e4d47  mov     eax, [rdi+20h]
0x1800e4d4a  mov     dword ptr [rsp+210h+var_1F0], eax
0x1800e4d4e  mov     r9, [rdi+8]
0x1800e4d52  mov     r8d, [rdi]
0x1800e4d55  mov     rdx, [rbp+110h+var_178]
0x1800e4d59  lea     rcx, [rbp+110h+var_C0]
0x1800e4d5d  call    ??0CLaunchHelper@CBrokeredLauncher@@QEAA@PEAUITelemetryCorrelationVector@@KPEBGW4PROCESS_UICONTEXT@@_NPEAXPEAUIDisableWindow@@PEAUILauncherOptions@System@Windows@@PEAUIFolderLauncherOptions@67@33W4LaunchHelperOptions@@3PEAUHWND__@@@Z; CBrokeredLauncher::CLaunchHelper::CLaunchHelper(ITelemetryCorrelationVector *,ulong,ushort const *,PROCESS_UICONTEXT,bool,void *,IDisableWindow *,Windows::System::ILauncherOptions *,Windows::System::IFolderLauncherOptions *,bool,bool,LaunchHelperOptions,bool,HWND__ *)
0x1800e4d62  xor     edx, edx; length
0x1800e4d64  mov     rcx, [rbp+110h+string]; string
0x1800e4d68  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4d6e  mov     [rbp+110h+var_160], rax
0x1800e4d72  xor     edx, edx; length
0x1800e4d74  mov     rcx, [rbp+110h+var_170]; string
0x1800e4d78  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4d7e  mov     [rbp+110h+var_178], rax
0x1800e4d82  lea     r9, [rbp+110h+var_160]
0x1800e4d86  lea     r8, [rbp+110h+var_178]
0x1800e4d8a  lea     rdx, [rdi+8]
0x1800e4d8e  mov     rcx, r15
0x1800e4d91  call    ??$LaunchUriRequest@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchUri@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchUri::LaunchUriRequest<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x1800e4d96  mov     rdx, r13; struct Windows::Foundation::IUriRuntimeClass *
0x1800e4d99  lea     rcx, [rbp+110h+var_C0]; this
0x1800e4d9d  call    ?LaunchUri@CLaunchHelper@CBrokeredLauncher@@QEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z; CBrokeredLauncher::CLaunchHelper::LaunchUri(Windows::Foundation::IUriRuntimeClass *)
0x1800e4da2  mov     ebx, eax
0x1800e4da4  lea     rcx, [rbp+110h+var_C0]; this
0x1800e4da8  call    ??1CLaunchHelper@CBrokeredLauncher@@QEAA@XZ; CBrokeredLauncher::CLaunchHelper::~CLaunchHelper(void)
0x1800e4dad  lea     rcx, [rbp+110h+var_188]
0x1800e4db1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e4db6  mov     r14d, [rbp+110h+var_180]
0x1800e4dba  mov     eax, ebx
0x1800e4dbc  shr     eax, 1Fh
0x1800e4dbf  mov     rcx, [rbp+110h+var_148]
0x1800e4dc3  mov     [rcx+10h], eax
0x1800e4dc6  mov     edx, ebx
0x1800e4dc8  mov     rcx, r15
0x1800e4dcb  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800e4dd0  xor     ebx, ebx
0x1800e4dd2  lea     rcx, [rbp+110h+var_158]
0x1800e4dd6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800e4ddb  nop
0x1800e4ddc  mov     rcx, [rbp+110h+var_170]; string
0x1800e4de0  call    cs:__imp_WindowsDeleteString
0x1800e4de6  mov     [rbp+110h+var_170], rbx
0x1800e4dea  mov     rcx, [rbp+110h+string]; string
0x1800e4dee  call    cs:__imp_WindowsDeleteString
0x1800e4df4  mov     [rbp+110h+string], rbx
0x1800e4df8  lea     rcx, [rbp+110h+var_130]; this
0x1800e4dfc  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800e4e01  mov     rax, [rbp+110h+var_148]
0x1800e4e05  lea     rcx, [rdi+28h]
0x1800e4e09  mov     r9, rax
0x1800e4e0c  mov     r8d, ebx
0x1800e4e0f  mov     edx, r14d
0x1800e4e12  call    ?ManageStage@AsyncWindowOperation@Internal@Windows@@QEAAJW4AsyncStage@23@JAEBVCResultBase@23@@Z; Windows::Internal::AsyncWindowOperation::ManageStage(Windows::Internal::AsyncStage,long,Windows::Internal::CResultBase const &)
0x1800e4e17  mov     rcx, [rbp+110h+var_40]
0x1800e4e1e  xor     rcx, rsp; StackCookie
0x1800e4e21  call    __security_check_cookie
0x1800e4e26  mov     rbx, [rsp+210h+arg_8]
0x1800e4e2e  add     rsp, 1E0h
0x1800e4e35  pop     r15
0x1800e4e37  pop     r14
0x1800e4e39  pop     r13
0x1800e4e3b  pop     r12
0x1800e4e3d  pop     rdi
0x1800e4e3e  pop     rsi
0x1800e4e3f  pop     rbp
0x1800e4e40  retn
```
