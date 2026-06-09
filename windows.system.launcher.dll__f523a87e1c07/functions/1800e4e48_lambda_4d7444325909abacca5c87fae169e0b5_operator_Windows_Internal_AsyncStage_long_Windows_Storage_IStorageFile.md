# _lambda_4d7444325909abacca5c87fae169e0b5_::operator()(Windows::Internal::AsyncStage,long,Windows::Storage::IStorageFile *,Windows::System::ILauncherOptions *,ITelemetryCorrelationVector *,Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4> &)

- ea: `0x1800e4e48`
- end: `0x1800e50ee`
- name: `??R_lambda_4d7444325909abacca5c87fae169e0b5_@@QEAAJW4AsyncStage@Internal@Windows@@JPEAUIStorageFile@Storage@3@PEAUILauncherOptions@System@3@PEAUITelemetryCorrelationVector@@AEAV?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@23@@Z`
- size: `678`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, struct Windows::Storage::IStorageFile *, __int64, PCWSTR, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e22e0`

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
- `0x1800e4e48`
- `0x1800e83fc`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e501f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e502f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e501f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e502f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5082`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e4f51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5070`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5082`

## string_xrefs

- `0x1800e4f2a`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`
- `0x1800e4f7c`: `onecoreuap\shell\windows.system.launcher\assoclaunch\lib\brokeredlauncher.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_4d7444325909abacca5c87fae169e0b5_::operator()(
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
    *(_DWORD *)(a7 + 16) = (unsigned int)WindowData >> 31;
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
0x1800e4e48  mov     [rsp-8+arg_8], rbx
0x1800e4e4d  push    rbp
0x1800e4e4e  push    rsi
0x1800e4e4f  push    rdi
0x1800e4e50  push    r12
0x1800e4e52  push    r13
0x1800e4e54  push    r14
0x1800e4e56  push    r15
0x1800e4e58  lea     rbp, [rsp-90h]
0x1800e4e60  sub     rsp, 190h
0x1800e4e67  mov     rax, cs:__security_cookie
0x1800e4e6e  xor     rax, rsp
0x1800e4e71  mov     [rbp+0C0h+var_40], rax
0x1800e4e78  mov     rsi, r9
0x1800e4e7b  mov     ebx, r8d
0x1800e4e7e  mov     eax, edx
0x1800e4e80  mov     [rbp+0C0h+var_120], edx
0x1800e4e83  mov     rdi, rcx
0x1800e4e86  mov     r14, [rbp+0C0h+arg_20]
0x1800e4e8d  mov     rcx, [rbp+0C0h+arg_28]
0x1800e4e94  mov     [rbp+0C0h+var_118], rcx
0x1800e4e98  mov     r13, [rbp+0C0h+arg_30]
0x1800e4e9f  cmp     edx, 1
0x1800e4ea2  jnz     loc_1800E50B3
0x1800e4ea8  test    ebx, ebx
0x1800e4eaa  js      loc_1800E50B3
0x1800e4eb0  lea     r15, [rdi+58h]
0x1800e4eb4  lea     rdx, [rbp+0C0h+var_110]; this
0x1800e4eb8  mov     rcx, r15; struct wil::details::IFailureCallback *
0x1800e4ebb  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800e4ec0  nop
0x1800e4ec1  mov     [rbp+0C0h+var_130], 0
0x1800e4ec9  lea     rcx, [rbp+0C0h+var_130]
0x1800e4ecd  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e4ed2  lea     r8, [rbp+0C0h+var_130]; void **
0x1800e4ed6  lea     rcx, [rdi+38h]; this
0x1800e4eda  call    ?GetWindowData@AsyncWindowOperation@Internal@Windows@@QEAAJAEBU_GUID@@PEAPEAX@Z; Windows::Internal::AsyncWindowOperation::GetWindowData(_GUID const &,void * *)
0x1800e4edf  mov     ebx, eax
0x1800e4ee1  test    eax, eax
0x1800e4ee3  js      loc_1800E5088
0x1800e4ee9  mov     [rbp+0C0h+string], 0
0x1800e4ef1  test    r14, r14
0x1800e4ef4  jz      short loc_1800E4F3B
0x1800e4ef6  mov     rax, [r14]
0x1800e4ef9  mov     rbx, [rax+58h]
0x1800e4efd  xor     ecx, ecx; string
0x1800e4eff  call    cs:__imp_WindowsDeleteString
0x1800e4f05  mov     [rbp+0C0h+string], 0
0x1800e4f0d  lea     rdx, [rbp+0C0h+string]
0x1800e4f11  mov     rcx, r14
0x1800e4f14  mov     rax, rbx
0x1800e4f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f1c  mov     rcx, [rbp+0C8h]; this
0x1800e4f23  test    eax, eax
0x1800e4f25  jns     short loc_1800E4F3B
0x1800e4f27  mov     r9d, eax; char *
0x1800e4f2a  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e4f31  mov     edx, 4D4h; void *
0x1800e4f36  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e4f3b  mov     [rbp+0C0h+var_140], 0
0x1800e4f43  test    rsi, rsi
0x1800e4f46  jz      short loc_1800E4F8D
0x1800e4f48  mov     rax, [rsi]
0x1800e4f4b  mov     rbx, [rax+30h]
0x1800e4f4f  xor     ecx, ecx; string
0x1800e4f51  call    cs:__imp_WindowsDeleteString
0x1800e4f57  mov     [rbp+0C0h+var_140], 0
0x1800e4f5f  lea     rdx, [rbp+0C0h+var_140]
0x1800e4f63  mov     rcx, rsi
0x1800e4f66  mov     rax, rbx
0x1800e4f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e4f6e  mov     rcx, [rbp+0C8h]; this
0x1800e4f75  test    eax, eax
0x1800e4f77  jns     short loc_1800E4F8D
0x1800e4f79  mov     r9d, eax; char *
0x1800e4f7c  lea     r8, aOnecoreuapShel_4; "onecoreuap\\shell\\windows.system.launc"...
0x1800e4f83  mov     edx, 4DAh; void *
0x1800e4f88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800e4f8d  mov     [rbp+0C0h+var_128], 0
0x1800e4f95  lea     rdx, [rbp+0C0h+var_128]; HWND *
0x1800e4f99  lea     rcx, [rdi+38h]; this
0x1800e4f9d  call    ?GetOwner@AsyncWindowOperation@Internal@Windows@@QEAAJPEAPEAUHWND__@@@Z; Windows::Internal::AsyncWindowOperation::GetOwner(HWND__ * *)
0x1800e4fa2  cmp     eax, 80070578h
0x1800e4fa7  jnz     short loc_1800E4FB5
0x1800e4fa9  cmp     byte ptr [rdi+27h], 0
0x1800e4fad  jz      short loc_1800E4FB5
0x1800e4faf  mov     rax, [rdi+28h]
0x1800e4fb3  jmp     short loc_1800E4FB9
0x1800e4fb5  mov     rax, [rbp+0C0h+var_128]
0x1800e4fb9  mov     [rsp+1C0h+var_150], rax
0x1800e4fbe  mov     [rsp+1C0h+var_158], 0
0x1800e4fc3  mov     eax, [rdi+30h]
0x1800e4fc6  mov     [rsp+1C0h+var_160], eax
0x1800e4fca  mov     al, [rdi+26h]
0x1800e4fcd  mov     [rsp+1C0h+var_168], al
0x1800e4fd1  mov     al, [rdi+25h]
0x1800e4fd4  mov     [rsp+1C0h+var_170], al
0x1800e4fd8  mov     [rsp+1C0h+var_178], 0
0x1800e4fe1  mov     [rsp+1C0h+var_180], r14
0x1800e4fe6  mov     rax, [rbp+0C0h+var_130]
0x1800e4fea  mov     [rsp+1C0h+var_188], rax
0x1800e4fef  mov     rax, [rdi+18h]
0x1800e4ff3  mov     [rsp+1C0h+var_190], rax
0x1800e4ff8  mov     al, [rdi+24h]
0x1800e4ffb  mov     [rsp+1C0h+var_198], al
0x1800e4fff  mov     eax, [rdi+20h]
0x1800e5002  mov     [rsp+1C0h+var_1A0], eax
0x1800e5006  mov     r9, [rdi]
0x1800e5009  xor     r8d, r8d
0x1800e500c  mov     rdx, [rbp+0C0h+var_118]
0x1800e5010  lea     rcx, [rbp+0C0h+var_C0]
0x1800e5014  call    ??0CLaunchHelper@CBrokeredLauncher@@QEAA@PEAUITelemetryCorrelationVector@@KPEBGW4PROCESS_UICONTEXT@@_NPEAXPEAUIDisableWindow@@PEAUILauncherOptions@System@Windows@@PEAUIFolderLauncherOptions@67@33W4LaunchHelperOptions@@3PEAUHWND__@@@Z; CBrokeredLauncher::CLaunchHelper::CLaunchHelper(ITelemetryCorrelationVector *,ulong,ushort const *,PROCESS_UICONTEXT,bool,void *,IDisableWindow *,Windows::System::ILauncherOptions *,Windows::System::IFolderLauncherOptions *,bool,bool,LaunchHelperOptions,bool,HWND__ *)
0x1800e5019  xor     edx, edx; length
0x1800e501b  mov     rcx, [rbp+0C0h+string]; string
0x1800e501f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5025  mov     [rbp+0C0h+var_118], rax
0x1800e5029  xor     edx, edx; length
0x1800e502b  mov     rcx, [rbp+0C0h+var_140]; string
0x1800e502f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5035  mov     [rbp+0C0h+var_128], rax
0x1800e5039  lea     r9, [rbp+0C0h+var_118]
0x1800e503d  lea     r8, [rbp+0C0h+var_128]
0x1800e5041  mov     rdx, rdi
0x1800e5044  mov     rcx, r15
0x1800e5047  call    ??$LaunchFileRequest@AEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@PEBGPEBG@LaunchFiles@LauncherDesktopProvider@@QEAAXAEAV?$CMemString@UCMemString_PolicyCoTaskMem@@@@$$QEAPEBG1@Z; LauncherDesktopProvider::LaunchFiles::LaunchFileRequest<CMemString<CMemString_PolicyCoTaskMem> &,ushort const *,ushort const *>(CMemString<CMemString_PolicyCoTaskMem> &,ushort const * &&,ushort const * &&)
0x1800e504c  mov     r9, [rdi+10h]; unsigned __int16 *
0x1800e5050  mov     r8, [rdi+8]; unsigned __int16 *
0x1800e5054  mov     rdx, rsi; struct Windows::Storage::IStorageFile *
0x1800e5057  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800e505b  call    ?LaunchFile@CLaunchHelper@CBrokeredLauncher@@QEAAJPEAUIStorageFile@Storage@Windows@@PEBG1@Z; CBrokeredLauncher::CLaunchHelper::LaunchFile(Windows::Storage::IStorageFile *,ushort const *,ushort const *)
0x1800e5060  mov     ebx, eax
0x1800e5062  lea     rcx, [rbp+0C0h+var_C0]; this
0x1800e5066  call    ??1CLaunchHelper@CBrokeredLauncher@@QEAA@XZ; CBrokeredLauncher::CLaunchHelper::~CLaunchHelper(void)
0x1800e506b  nop
0x1800e506c  mov     rcx, [rbp+0C0h+var_140]; string
0x1800e5070  call    cs:__imp_WindowsDeleteString
0x1800e5076  mov     [rbp+0C0h+var_140], 0
0x1800e507e  mov     rcx, [rbp+0C0h+string]; string
0x1800e5082  call    cs:__imp_WindowsDeleteString
0x1800e5088  mov     eax, ebx
0x1800e508a  shr     eax, 1Fh
0x1800e508d  mov     [r13+10h], eax
0x1800e5091  mov     edx, ebx
0x1800e5093  mov     rcx, r15
0x1800e5096  call    ?Stop@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800e509b  xor     ebx, ebx
0x1800e509d  lea     rcx, [rbp+0C0h+var_130]
0x1800e50a1  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800e50a6  nop
0x1800e50a7  lea     rcx, [rbp+0C0h+var_110]; this
0x1800e50ab  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800e50b0  mov     eax, [rbp+0C0h+var_120]
0x1800e50b3  lea     rcx, [rdi+38h]
0x1800e50b7  mov     r9, r13
0x1800e50ba  mov     r8d, ebx
0x1800e50bd  mov     edx, eax
0x1800e50bf  call    ?ManageStage@AsyncWindowOperation@Internal@Windows@@QEAAJW4AsyncStage@23@JAEBVCResultBase@23@@Z; Windows::Internal::AsyncWindowOperation::ManageStage(Windows::Internal::AsyncStage,long,Windows::Internal::CResultBase const &)
0x1800e50c4  mov     rcx, [rbp+0C0h+var_40]
0x1800e50cb  xor     rcx, rsp; StackCookie
0x1800e50ce  call    __security_check_cookie
0x1800e50d3  mov     rbx, [rsp+1C0h+arg_8]
0x1800e50db  add     rsp, 190h
0x1800e50e2  pop     r15
0x1800e50e4  pop     r14
0x1800e50e6  pop     r13
0x1800e50e8  pop     r12
0x1800e50ea  pop     rdi
0x1800e50eb  pop     rsi
0x1800e50ec  pop     rbp
0x1800e50ed  retn
```
