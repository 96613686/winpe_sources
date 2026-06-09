# _lambda_12a93b8d7660d2cdca714be35ee02a8e_::operator()(Windows::Internal::AsyncStage,long,Windows::Foundation::IUriRuntimeClass *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,Windows::Internal::CBasicResult<uchar,0> &)

- ea: `0x180062888`
- end: `0x180062bfc`
- name: `??R_lambda_12a93b8d7660d2cdca714be35ee02a8e_@@QEAAJW4AsyncStage@Internal@Windows@@JPEAUIUriRuntimeClass@Foundation@3@PEAUILauncherOptions@System@3@PEAUITelemetryCorrelationVector@@AEAV?$CBasicResult@E$0A@@23@@Z`
- size: `884`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, struct Windows::Foundation::IUriRuntimeClass *, __int64, PCWSTR, __int64)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062728`

## callees

- `0x1800049bc`
- `0x1800398c8`
- `0x18004966c`
- `0x18005591c`
- `0x180057084`
- `0x1800570b4`
- `0x180062888`
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
- `0x1800e8280`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062b21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a5d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062b21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062b31`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006294d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062ba9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062923`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006294d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062b9b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062ba9`

## pseudocode

```c
__int64 __fastcall _lambda_12a93b8d7660d2cdca714be35ee02a8e_::operator()(
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
      *(_BYTE *)(v31 + 16) = IsCallerRunningOnLock >= 0;
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
0x180062888  mov     [rsp-8+arg_8], rbx
0x18006288d  push    rbp
0x18006288e  push    rsi
0x18006288f  push    rdi
0x180062890  push    r12
0x180062892  push    r13
0x180062894  push    r14
0x180062896  push    r15
0x180062898  lea     rbp, [rsp-0E0h]
0x1800628a0  sub     rsp, 1E0h
0x1800628a7  mov     rax, cs:__security_cookie
0x1800628ae  xor     rax, rsp
0x1800628b1  mov     [rbp+110h+var_40], rax
0x1800628b8  mov     r13, r9
0x1800628bb  mov     ebx, r8d
0x1800628be  mov     r14d, edx
0x1800628c1  mov     [rbp+110h+var_180], edx
0x1800628c4  mov     rdi, rcx
0x1800628c7  mov     rsi, [rbp+110h+arg_20]
0x1800628ce  mov     [rbp+110h+var_160], r9
0x1800628d2  mov     [rbp+110h+var_140], rsi
0x1800628d6  mov     rax, [rbp+110h+arg_28]
0x1800628dd  mov     [rbp+110h+var_178], rax
0x1800628e1  mov     rax, [rbp+110h+arg_30]
0x1800628e8  mov     [rbp+110h+var_148], rax
0x1800628ec  cmp     edx, 1
0x1800628ef  jnz     loc_180062BC0
0x1800628f5  xor     r12d, r12d
0x1800628f8  test    ebx, ebx
0x1800628fa  js      loc_180062BC0
0x180062900  lea     r15, [rcx+58h]
0x180062904  lea     rdx, [rbp+110h+var_130]; this
0x180062908  mov     rcx, r15; struct wil::details::IFailureCallback *
0x18006290b  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180062910  nop
0x180062911  mov     [rbp+110h+string], r12
0x180062915  test    rsi, rsi
0x180062918  jz      short loc_18006293C
0x18006291a  mov     rax, [rsi]
0x18006291d  mov     rbx, [rax+58h]
0x180062921  xor     ecx, ecx; string
0x180062923  call    cs:__imp_WindowsDeleteString
0x180062929  mov     [rbp+110h+string], r12
0x18006292d  lea     rdx, [rbp+110h+string]
0x180062931  mov     rcx, rsi
0x180062934  mov     rax, rbx
0x180062937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006293c  mov     [rbp+110h+var_170], r12
0x180062940  mov     rax, [r13+0]
0x180062944  mov     rbx, [rax+88h]
0x18006294b  xor     ecx, ecx; string
0x18006294d  call    cs:__imp_WindowsDeleteString
0x180062953  mov     [rbp+110h+var_170], r12
0x180062957  lea     rdx, [rbp+110h+var_170]
0x18006295b  mov     rcx, r13
0x18006295e  mov     rax, rbx
0x180062961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062966  mov     [rbp+110h+var_158], r12
0x18006296a  lea     rcx, [rbp+110h+var_158]; this
0x18006296e  call    ?Initialize@CLockScreenInterop@@QEAAJXZ; CLockScreenInterop::Initialize(void)
0x180062973  mov     ebx, eax
0x180062975  mov     [rbp+110h+var_190], r12b
0x180062979  mov     [rbp+110h+var_188], 0
0x180062981  test    eax, eax
0x180062983  js      loc_180062B73
0x180062989  lea     rcx, [rdi+28h]; this
0x18006298d  lea     rdx, [rbp+110h+var_188]; HWND *
0x180062991  call    ?GetOwner@AsyncWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::AsyncWindowOperation::GetOwner(HWND__ * *)
0x180062996  test    eax, eax
0x180062998  js      short loc_1800629C7
0x18006299a  mov     rdx, [rdi+8]; unsigned __int16 *
0x18006299e  mov     r14, [rbp+110h+var_188]
0x1800629a2  test    rdx, rdx
0x1800629a5  jz      short loc_1800629BD
0x1800629a7  lea     r9, [rbp+110h+var_190]; bool *
0x1800629ab  mov     r8, r14; unsigned __int64
0x1800629ae  lea     rcx, [rbp+110h+var_158]; this
0x1800629b2  call    ?IsCallerRunningOnLock@CLockScreenInterop@@QEAAJPEBG_KPEA_N@Z; CLockScreenInterop::IsCallerRunningOnLock(ushort const *,unsigned __int64,bool *)
0x1800629b7  mov     ebx, eax
0x1800629b9  mov     r12b, [rbp+110h+var_190]
0x1800629bd  test    ebx, ebx
0x1800629bf  js      loc_180062B6F
0x1800629c5  jmp     short loc_1800629DE
0x1800629c7  cmp     eax, 80070578h
0x1800629cc  jnz     short loc_1800629DA
0x1800629ce  cmp     byte ptr [rdi+4Ah], 0
0x1800629d2  jz      short loc_1800629DA
0x1800629d4  mov     r14, [rdi+50h]
0x1800629d8  jmp     short loc_1800629DE
0x1800629da  mov     r14, [rbp+110h+var_188]
0x1800629de  test    r12b, r12b
0x1800629e1  jz      loc_180062A98
0x1800629e7  mov     [rbp+110h+var_150], 0
0x1800629ef  mov     byte ptr [rbp+110h+var_188+2], 0
0x1800629f3  mov     al, [rdi+24h]
0x1800629f6  mov     byte ptr [rbp+110h+var_188], al
0x1800629f9  mov     al, [rdi+48h]
0x1800629fc  mov     byte ptr [rbp+110h+var_188+1], al
0x1800629ff  mov     al, [rdi+49h]
0x180062a02  mov     byte ptr [rbp+110h+var_188+3], al
0x180062a05  lea     rdx, [rdi+8]
0x180062a09  lea     rcx, [rbp+110h+hstringHeader]; hstringHeader
0x180062a0d  call    ??$?0V?$CMemString@UCMemString_PolicyCoTaskMem@@@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$CMemString@UCMemString_PolicyCoTaskMem@@@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(CMemString<CMemString_PolicyCoTaskMem> const &,Microsoft::WRL::Details::Dummy)
0x180062a12  mov     rcx, [rax+18h]
0x180062a16  mov     [rbp+110h+var_178], rcx
0x180062a1a  lea     rax, [rdi+18h]
0x180062a1e  lea     rcx, [rbp+110h+var_140]
0x180062a22  mov     [rsp+210h+var_1E8], rcx
0x180062a27  mov     [rsp+210h+var_1F0], rax
0x180062a2c  lea     r9, [rbp+110h+var_188]
0x180062a30  lea     r8, [rbp+110h+var_178]
0x180062a34  lea     rdx, [rbp+110h+var_160]
0x180062a38  lea     rcx, [rbp+110h+var_150]
0x180062a3c  call    ??$MakeAndInitialize@VCCachedLaunchUriRequest@@V1@AEAPEAUIUriRuntimeClass@Foundation@Windows@@PEAUHSTRING__@@AEAUPendingLaunchConfiguration@@V?$CAutoHandle@PEAX@@AEAPEAUILauncherOptions@System@4@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VCCachedLaunchUriRequest@@@WRL@Microsoft@@@012@AEAPEAUIUriRuntimeClass@Foundation@Windows@@$$QEAPEAUHSTRING__@@AEAUPendingLaunchConfiguration@@$$QEAV?$CAutoHandle@PEAX@@AEAPEAUILauncherOptions@System@6@@Z; Microsoft::WRL::Details::MakeAndInitialize<CCachedLaunchUriRequest,CCachedLaunchUriRequest,Windows::Foundation::IUriRuntimeClass * &,HSTRING__ *,PendingLaunchConfiguration &,CAutoHandle<void *>,Windows::System::ILauncherOptions * &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<CCachedLaunchUriRequest>>,Windows::Foundation::IUriRuntimeClass * &,HSTRING__ * &&,PendingLaunchConfiguration &,CAutoHandle<void *> &&,Windows::System::ILauncherOptions * &)
0x180062a41  mov     ebx, eax
0x180062a43  test    eax, eax
0x180062a45  js      short loc_180062A8A
0x180062a47  xor     edx, edx; length
0x180062a49  mov     rcx, [rbp+110h+string]; string
0x180062a4d  call    cs:__imp_WindowsGetStringRawBuffer
0x180062a53  mov     [rbp+110h+var_160], rax
0x180062a57  xor     edx, edx; length
0x180062a59  mov     rcx, [rbp+110h+var_170]; string
0x180062a5d  call    cs:__imp_WindowsGetStringRawBuffer
0x180062a63  mov     [rbp+110h+var_178], rax
0x180062a67  lea     r9, [rbp+110h+var_160]
0x180062a6b  lea     r8, [rbp+110h+var_178]
0x180062a6f  lea     rdx, [rdi+8]
0x180062a73  mov     rcx, r15
0x180062a76  call    ??$LaunchFromLockScreen@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchUri@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchUri::LaunchFromLockScreen<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x180062a7b  mov     rdx, [rbp+110h+var_150]; struct IUnknown *
0x180062a7f  lea     rcx, [rbp+110h+var_158]; this
0x180062a83  call    ?CacheLaunchRequest@CLockScreenInterop@@QEAAJPEAUIUnknown@@@Z; CLockScreenInterop::CacheLaunchRequest(IUnknown *)
0x180062a88  mov     ebx, eax
0x180062a8a  lea     rcx, [rbp+110h+var_150]
0x180062a8e  call    ?InternalRelease@?$ComPtr@VCCachedLaunchUriRequest@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CCachedLaunchUriRequest>::InternalRelease(void)
0x180062a93  jmp     loc_180062B6F
0x180062a98  mov     [rbp+110h+var_188], 0
0x180062aa0  lea     rcx, [rbp+110h+var_188]
0x180062aa4  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180062aa9  lea     r8, [rbp+110h+var_188]; void **
0x180062aad  lea     rcx, [rdi+28h]; this
0x180062ab1  call    ?GetWindowData@AsyncWindowOperation@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::AsyncWindowOperation::GetWindowData(_GUID const &,void * *)
0x180062ab6  mov     ebx, eax
0x180062ab8  xor     ecx, ecx
0x180062aba  test    eax, eax
0x180062abc  js      loc_180062B66
0x180062ac2  mov     [rsp+210h+var_1A0], r14
0x180062ac7  mov     [rsp+210h+var_1A8], cl
0x180062acb  mov     [rsp+210h+var_1B0], ecx
0x180062acf  mov     al, [rdi+49h]
0x180062ad2  mov     [rsp+210h+var_1B8], al
0x180062ad6  mov     al, [rdi+48h]
0x180062ad9  mov     [rsp+210h+var_1C0], al
0x180062add  mov     [rsp+210h+var_1C8], rcx
0x180062ae2  mov     [rsp+210h+var_1D0], rsi
0x180062ae7  mov     rax, [rbp+110h+var_188]
0x180062aeb  mov     [rsp+210h+var_1D8], rax
0x180062af0  mov     rax, [rdi+18h]
0x180062af4  mov     [rsp+210h+var_1E0], rax
0x180062af9  mov     al, [rdi+24h]
0x180062afc  mov     byte ptr [rsp+210h+var_1E8], al
0x180062b00  mov     eax, [rdi+20h]
0x180062b03  mov     dword ptr [rsp+210h+var_1F0], eax
0x180062b07  mov     r9, [rdi+8]
0x180062b0b  mov     r8d, [rdi]
0x180062b0e  mov     rdx, [rbp+110h+var_178]
0x180062b12  lea     rcx, [rbp+110h+var_C0]
0x180062b16  call    ??0CLaunchHelper@CBrokeredLauncher@@QEAA@PEAUITelemetryCorrelationVector@@KPEBGW4PROCESS_UICONTEXT@@_NPEAXPEAUIDisableWindow@@PEAUILauncherOptions@System@Windows@@PEAUIFolderLauncherOptions@67@33W4LaunchHelperOptions@@3PEAUHWND__@@@Z; CBrokeredLauncher::CLaunchHelper::CLaunchHelper(ITelemetryCorrelationVector *,ulong,ushort const *,PROCESS_UICONTEXT,bool,void *,IDisableWindow *,Windows::System::ILauncherOptions *,Windows::System::IFolderLauncherOptions *,bool,bool,LaunchHelperOptions,bool,HWND__ *)
0x180062b1b  xor     edx, edx; length
0x180062b1d  mov     rcx, [rbp+110h+string]; string
0x180062b21  call    cs:__imp_WindowsGetStringRawBuffer
0x180062b27  mov     [rbp+110h+var_160], rax
0x180062b2b  xor     edx, edx; length
0x180062b2d  mov     rcx, [rbp+110h+var_170]; string
0x180062b31  call    cs:__imp_WindowsGetStringRawBuffer
0x180062b37  mov     [rbp+110h+var_178], rax
0x180062b3b  lea     r9, [rbp+110h+var_160]
0x180062b3f  lea     r8, [rbp+110h+var_178]
0x180062b43  lea     rdx, [rdi+8]
0x180062b47  mov     rcx, r15
0x180062b4a  call    ??$LaunchUriRequest@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchUri@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchUri::LaunchUriRequest<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x180062b4f  mov     rdx, r13; struct Windows::Foundation::IUriRuntimeClass *
0x180062b52  lea     rcx, [rbp+110h+var_C0]; this
0x180062b56  call    ?LaunchUri@CLaunchHelper@CBrokeredLauncher@@QEAAJPEAUIUriRuntimeClass@Foundation@Windows@@@Z; CBrokeredLauncher::CLaunchHelper::LaunchUri(Windows::Foundation::IUriRuntimeClass *)
0x180062b5b  mov     ebx, eax
0x180062b5d  lea     rcx, [rbp+110h+var_C0]; this
0x180062b61  call    ??1CLaunchHelper@CBrokeredLauncher@@QEAA@XZ; CBrokeredLauncher::CLaunchHelper::~CLaunchHelper(void)
0x180062b66  lea     rcx, [rbp+110h+var_188]
0x180062b6a  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180062b6f  mov     r14d, [rbp+110h+var_180]
0x180062b73  mov     eax, ebx
0x180062b75  shr     eax, 1Fh
0x180062b78  xor     al, 1
0x180062b7a  mov     rcx, [rbp+110h+var_148]
0x180062b7e  mov     [rcx+10h], al
0x180062b81  mov     edx, ebx
0x180062b83  mov     rcx, r15
0x180062b86  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180062b8b  xor     ebx, ebx
0x180062b8d  lea     rcx, [rbp+110h+var_158]
0x180062b91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180062b96  nop
0x180062b97  mov     rcx, [rbp+110h+var_170]; string
0x180062b9b  call    cs:__imp_WindowsDeleteString
0x180062ba1  mov     [rbp+110h+var_170], rbx
0x180062ba5  mov     rcx, [rbp+110h+string]; string
0x180062ba9  call    cs:__imp_WindowsDeleteString
0x180062baf  mov     [rbp+110h+string], rbx
0x180062bb3  lea     rcx, [rbp+110h+var_130]; this
0x180062bb7  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180062bbc  mov     rax, [rbp+110h+var_148]
0x180062bc0  lea     rcx, [rdi+28h]
0x180062bc4  mov     r9, rax
0x180062bc7  mov     r8d, ebx
0x180062bca  mov     edx, r14d
0x180062bcd  call    ?ManageStage@AsyncWindowOperation@Internal@Windows@@QEAAJW4AsyncStage@23@JAEBVCResultBase@23@@Z; Windows::Internal::AsyncWindowOperation::ManageStage(Windows::Internal::AsyncStage,long,Windows::Internal::CResultBase const &)
0x180062bd2  mov     rcx, [rbp+110h+var_40]
0x180062bd9  xor     rcx, rsp; StackCookie
0x180062bdc  call    __security_check_cookie
0x180062be1  mov     rbx, [rsp+210h+arg_8]
0x180062be9  add     rsp, 1E0h
0x180062bf0  pop     r15
0x180062bf2  pop     r14
0x180062bf4  pop     r13
0x180062bf6  pop     r12
0x180062bf8  pop     rdi
0x180062bf9  pop     rsi
0x180062bfa  pop     rbp
0x180062bfb  retn
```
