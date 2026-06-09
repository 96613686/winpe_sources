# _lambda_1c837b4cf627ae89728bf991f02ea9b3_::operator()(Windows::Internal::AsyncStage,long,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,Windows::Internal::CBasicResult<uchar,0> &)

- ea: `0x1800e4820`
- end: `0x1800e4ac8`
- name: `??R_lambda_1c837b4cf627ae89728bf991f02ea9b3_@@QEAAJW4AsyncStage@Internal@Windows@@JPEAUIStorageFile@Storage@3@PEAUILauncherOptions@System@3@PEAUITelemetryCorrelationVector@@AEAV?$CBasicResult@E$0A@@23@@Z`
- size: `680`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, struct Windows::Storage::IStorageFile *, __int64, PCWSTR, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e2148`

## callees

- `0x18004966c`
- `0x18005591c`
- `0x180057084`
- `0x1800596d8`
- `0x180063820`
- `0x18006be44`
- `0x18006c64c`
- `0x18006f528`
- `0x18006f680`
- `0x180073094`
- `0x18008a030`
- `0x1800e167c`
- `0x1800e4820`
- `0x1800e83fc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e49f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4a07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e49f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e4a07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e48d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e48d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4929`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4a5a`

## string_xrefs

- `0x1800e4902`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800e4954`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_1c837b4cf627ae89728bf991f02ea9b3_::operator()(
        __int64 a1,
        unsigned int a2,
        int a3,
        struct Windows::Storage::IStorageFile *a4,
        __int64 a5,
        PCWSTR a6,
        __int64 a7)
{
  unsigned int v8; // ebx
  unsigned int v9; // eax
  const struct _GUID *v11; // rdx
  int WindowData; // ebx
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  __int64 (__fastcall *v15)(struct Windows::Storage::IStorageFile *, HSTRING *); // rbx
  int v16; // eax
  HWND v17; // rax
  int v19; // [rsp+20h] [rbp-E0h]
  HSTRING v20; // [rsp+80h] [rbp-80h] BYREF
  HSTRING string; // [rsp+88h] [rbp-78h] BYREF
  void *v22; // [rsp+90h] [rbp-70h] BYREF
  HWND v23; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp-60h]
  PCWSTR StringRawBuffer; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v26[80]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v27[128]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v8 = a3;
  v9 = a2;
  v24 = a2;
  StringRawBuffer = a6;
  if ( a2 == 1 && a3 >= 0 )
  {
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
      (struct wil::details::IFailureCallback *)(a1 + 88),
      (wil::ActivityThreadWatcher *)v26);
    v22 = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
    WindowData = Windows::Internal::AsyncWindowOperation::GetWindowData(
                   (Windows::Internal::AsyncWindowOperation *)(a1 + 56),
                   v11,
                   &v22);
    if ( WindowData >= 0 )
    {
      string = 0;
      if ( a5 )
      {
        v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a5 + 88LL);
        WindowsDeleteString(0);
        string = 0;
        v14 = v13(a5, &string);
        if ( v14 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4D4,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v14,
            v19);
      }
      v20 = 0;
      if ( a4 )
      {
        v15 = *(__int64 (__fastcall **)(struct Windows::Storage::IStorageFile *, HSTRING *))(*(_QWORD *)a4 + 48LL);
        WindowsDeleteString(0);
        v20 = 0;
        v16 = v15(a4, &v20);
        if ( v16 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4DA,
            (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\assoclaunch\\lib\\brokeredlauncher.cpp",
            (const char *)(unsigned int)v16,
            v19);
      }
      v23 = 0;
      if ( (unsigned int)Windows::Internal::AsyncWindowOperation::GetOwner(
                           (Windows::Internal::AsyncWindowOperation *)(a1 + 56),
                           &v23) == -2147023496
        && *(_BYTE *)(a1 + 39) )
      {
        v17 = *(HWND *)(a1 + 40);
      }
      else
      {
        v17 = v23;
      }
      CBrokeredLauncher::CLaunchHelper::CLaunchHelper(
        (__int64)v27,
        (__int64)StringRawBuffer,
        0,
        *(_QWORD *)a1,
        *(_DWORD *)(a1 + 32),
        *(_BYTE *)(a1 + 36),
        *(_QWORD *)(a1 + 24),
        (__int64)v22,
        a5,
        0,
        *(_BYTE *)(a1 + 37),
        *(_BYTE *)(a1 + 38),
        *(_DWORD *)(a1 + 48),
        0,
        (__int64)v17);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v23 = (HWND)WindowsGetStringRawBuffer(v20, 0);
      LauncherDesktopProvider::LaunchFiles::LaunchFileRequest<CMemString<CMemString_PolicyCoTaskMem> &,unsigned short const *,unsigned short const *>(
        a1 + 88,
        a1,
        &v23,
        &StringRawBuffer);
      WindowData = CBrokeredLauncher::CLaunchHelper::LaunchFile(
                     (CBrokeredLauncher::CLaunchHelper *)v27,
                     a4,
                     *(const unsigned __int16 **)(a1 + 8),
                     *(const unsigned __int16 **)(a1 + 16));
      CBrokeredLauncher::CLaunchHelper::~CLaunchHelper((CBrokeredLauncher::CLaunchHelper *)v27);
      WindowsDeleteString(v20);
      v20 = 0;
      WindowsDeleteString(string);
    }
    *(_BYTE *)(a7 + 16) = WindowData >= 0;
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
      a1 + 88,
      (unsigned int)WindowData);
    v8 = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v22);
    wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v26);
    v9 = v24;
  }
  return Windows::Internal::AsyncWindowOperation::ManageStage(a1 + 56, v9, v8, a7);
}

```

## disassembly

```asm
0x1800e4820  mov     [rsp-8+arg_8], rbx
0x1800e4825  push    rbp
0x1800e4826  push    rsi
0x1800e4827  push    rdi
0x1800e4828  push    r12
0x1800e482a  push    r13
0x1800e482c  push    r14
0x1800e482e  push    r15
0x1800e4830  lea     rbp, [rsp-90h]
0x1800e4838  sub     rsp, 190h
0x1800e483f  mov     rax, cs:__security_cookie
0x1800e4846  xor     rax, rsp
0x1800e4849  mov     [rbp+0C0h+var_40], rax
0x1800e4850  mov     rsi, r9
0x1800e4853  mov     ebx, r8d
0x1800e4856  mov     eax, edx
0x1800e4858  mov     [rbp+0C0h+var_120], edx
0x1800e485b  mov     rdi, rcx
0x1800e485e  mov     r14, [rbp+0C0h+arg_20]
0x1800e4865  mov     rcx, [rbp+0C0h+arg_28]
0x1800e486c  mov     [rbp+0C0h+var_118], rcx
0x1800e4870  mov     r13, [rbp+0C0h+arg_30]
0x1800e4877  cmp     edx, 1
0x1800e487a  jnz     loc_1800E4A8D
0x1800e4880  test    ebx, ebx
0x1800e4882  js      loc_1800E4A8D
0x1800e4888  lea     r12, [rdi+58h]
0x1800e488c  lea     rdx, [rbp+0C0h+var_110]; this
0x1800e4890  mov     rcx, r12; struct wil::details::IFailureCallback *
0x1800e4893  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800e4898  nop
0x1800e4899  mov     [rbp+0C0h+var_130], 0
0x1800e48a1  lea     rcx, [rbp+0C0h+var_130]
0x1800e48a5  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e48aa  lea     r8, [rbp+0C0h+var_130]; void **
0x1800e48ae  lea     rcx, [rdi+38h]; this
0x1800e48b2  call    ?GetWindowData@AsyncWindowOperation@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::AsyncWindowOperation::GetWindowData(_GUID const &,void * *)
0x1800e48b7  mov     ebx, eax
0x1800e48b9  test    eax, eax
0x1800e48bb  js      loc_1800E4A60
0x1800e48c1  mov     [rbp+0C0h+string], 0
0x1800e48c9  test    r14, r14
0x1800e48cc  jz      short loc_1800E4913
0x1800e48ce  mov     rax, [r14]
0x1800e48d1  mov     rbx, [rax+58h]
0x1800e48d5  xor     ecx, ecx; string
0x1800e48d7  call    cs:__imp_WindowsDeleteString
0x1800e48dd  mov     [rbp+0C0h+string], 0
0x1800e48e5  lea     rdx, [rbp+0C0h+string]
0x1800e48e9  mov     rcx, r14
0x1800e48ec  mov     rax, rbx
0x1800e48ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e48f4  mov     rcx, [rbp+0C8h]; this
0x1800e48fb  test    eax, eax
0x1800e48fd  jns     short loc_1800E4913
0x1800e48ff  mov     r9d, eax; char *
0x1800e4902  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e4909  mov     edx, 4D4h; void *
0x1800e490e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e4913  mov     [rbp+0C0h+var_140], 0
0x1800e491b  test    rsi, rsi
0x1800e491e  jz      short loc_1800E4965
0x1800e4920  mov     rax, [rsi]
0x1800e4923  mov     rbx, [rax+30h]
0x1800e4927  xor     ecx, ecx; string
0x1800e4929  call    cs:__imp_WindowsDeleteString
0x1800e492f  mov     [rbp+0C0h+var_140], 0
0x1800e4937  lea     rdx, [rbp+0C0h+var_140]
0x1800e493b  mov     rcx, rsi
0x1800e493e  mov     rax, rbx
0x1800e4941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4946  mov     rcx, [rbp+0C8h]; this
0x1800e494d  test    eax, eax
0x1800e494f  jns     short loc_1800E4965
0x1800e4951  mov     r9d, eax; char *
0x1800e4954  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e495b  mov     edx, 4DAh; void *
0x1800e4960  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e4965  mov     [rbp+0C0h+var_128], 0
0x1800e496d  lea     rdx, [rbp+0C0h+var_128]; HWND *
0x1800e4971  lea     rcx, [rdi+38h]; this
0x1800e4975  call    ?GetOwner@AsyncWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::AsyncWindowOperation::GetOwner(HWND__ * *)
0x1800e497a  cmp     eax, 80070578h
0x1800e497f  jnz     short loc_1800E498D
0x1800e4981  cmp     byte ptr [rdi+27h], 0
0x1800e4985  jz      short loc_1800E498D
0x1800e4987  mov     rax, [rdi+28h]
0x1800e498b  jmp     short loc_1800E4991
0x1800e498d  mov     rax, [rbp+0C0h+var_128]
0x1800e4991  mov     [rsp+1C0h+var_150], rax
0x1800e4996  mov     [rsp+1C0h+var_158], 0
0x1800e499b  mov     eax, [rdi+30h]
0x1800e499e  mov     [rsp+1C0h+var_160], eax
0x1800e49a2  mov     al, [rdi+26h]
0x1800e49a5  mov     [rsp+1C0h+var_168], al
0x1800e49a9  mov     al, [rdi+25h]
0x1800e49ac  mov     [rsp+1C0h+var_170], al
0x1800e49b0  mov     [rsp+1C0h+var_178], 0
0x1800e49b9  mov     [rsp+1C0h+var_180], r14
0x1800e49be  mov     rax, [rbp+0C0h+var_130]
0x1800e49c2  mov     [rsp+1C0h+var_188], rax
0x1800e49c7  mov     rax, [rdi+18h]
0x1800e49cb  mov     [rsp+1C0h+var_190], rax
0x1800e49d0  mov     al, [rdi+24h]
0x1800e49d3  mov     [rsp+1C0h+var_198], al
0x1800e49d7  mov     eax, [rdi+20h]
0x1800e49da  mov     [rsp+1C0h+var_1A0], eax
0x1800e49de  mov     r9, [rdi]
0x1800e49e1  xor     r8d, r8d
0x1800e49e4  mov     rdx, [rbp+0C0h+var_118]
0x1800e49e8  lea     rcx, [rbp+0C0h+var_C0]
0x1800e49ec  call    ??0CLaunchHelper@CBrokeredLauncher@@QEAA@PEAUITelemetryCorrelationVector@@KPEBGW4PROCESS_UICONTEXT@@_NPEAXPEAUIDisableWindow@@PEAUILauncherOptions@System@Windows@@PEAUIFolderLauncherOptions@67@33W4LaunchHelperOptions@@3PEAUHWND__@@@Z; CBrokeredLauncher::CLaunchHelper::CLaunchHelper(ITelemetryCorrelationVector *,ulong,ushort const *,PROCESS_UICONTEXT,bool,void *,IDisableWindow *,Windows::System::ILauncherOptions *,Windows::System::IFolderLauncherOptions *,bool,bool,LaunchHelperOptions,bool,HWND__ *)
0x1800e49f1  xor     edx, edx; length
0x1800e49f3  mov     rcx, [rbp+0C0h+string]; string
0x1800e49f7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e49fd  mov     [rbp+0C0h+var_118], rax
0x1800e4a01  xor     edx, edx; length
0x1800e4a03  mov     rcx, [rbp+0C0h+var_140]; string
0x1800e4a07  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e4a0d  mov     [rbp+0C0h+var_128], rax
0x1800e4a11  lea     r9, [rbp+0C0h+var_118]
0x1800e4a15  lea     r8, [rbp+0C0h+var_128]
0x1800e4a19  mov     rdx, rdi
0x1800e4a1c  mov     rcx, r12
0x1800e4a1f  call    ??$LaunchFileRequest@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchFiles@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchFiles::LaunchFileRequest<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x1800e4a24  mov     r9, [rdi+10h]; unsigned __int16 *
0x1800e4a28  mov     r8, [rdi+8]; unsigned __int16 *
0x1800e4a2c  mov     rdx, rsi; struct Windows::Storage::IStorageFile *
0x1800e4a2f  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800e4a33  call    ?LaunchFile@CLaunchHelper@CBrokeredLauncher@@QEAAJPEAUIStorageFile@Storage@Windows@@PEBG1@Z; CBrokeredLauncher::CLaunchHelper::LaunchFile(Windows::Storage::IStorageFile *,ushort const *,ushort const *)
0x1800e4a38  mov     ebx, eax
0x1800e4a3a  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800e4a3e  call    ??1CLaunchHelper@CBrokeredLauncher@@QEAA@XZ; CBrokeredLauncher::CLaunchHelper::~CLaunchHelper(void)
0x1800e4a43  nop
0x1800e4a44  mov     rcx, [rbp+0C0h+var_140]; string
0x1800e4a48  call    cs:__imp_WindowsDeleteString
0x1800e4a4e  mov     [rbp+0C0h+var_140], 0
0x1800e4a56  mov     rcx, [rbp+0C0h+string]; string
0x1800e4a5a  call    cs:__imp_WindowsDeleteString
0x1800e4a60  mov     eax, ebx
0x1800e4a62  shr     eax, 1Fh
0x1800e4a65  xor     al, 1
0x1800e4a67  mov     [r13+10h], al
0x1800e4a6b  mov     edx, ebx
0x1800e4a6d  mov     rcx, r12
0x1800e4a70  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800e4a75  xor     ebx, ebx
0x1800e4a77  lea     rcx, [rbp+0C0h+var_130]
0x1800e4a7b  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e4a80  nop
0x1800e4a81  lea     rcx, [rbp+0C0h+var_110]; this
0x1800e4a85  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800e4a8a  mov     eax, [rbp+0C0h+var_120]
0x1800e4a8d  lea     rcx, [rdi+38h]
0x1800e4a91  mov     r9, r13
0x1800e4a94  mov     r8d, ebx
0x1800e4a97  mov     edx, eax
0x1800e4a99  call    ?ManageStage@AsyncWindowOperation@Internal@Windows@@QEAAJW4AsyncStage@23@JAEBVCResultBase@23@@Z; Windows::Internal::AsyncWindowOperation::ManageStage(Windows::Internal::AsyncStage,long,Windows::Internal::CResultBase const &)
0x1800e4a9e  mov     rcx, [rbp+0C0h+var_40]
0x1800e4aa5  xor     rcx, rsp; StackCookie
0x1800e4aa8  call    __security_check_cookie
0x1800e4aad  mov     rbx, [rsp+1C0h+arg_8]
0x1800e4ab5  add     rsp, 190h
0x1800e4abc  pop     r15
0x1800e4abe  pop     r14
0x1800e4ac0  pop     r13
0x1800e4ac2  pop     r12
0x1800e4ac4  pop     rdi
0x1800e4ac5  pop     rsi
0x1800e4ac6  pop     rbp
0x1800e4ac7  retn
```
