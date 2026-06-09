# _lambda_da225a7cdf57dc8e8263eb3946dbc5ab_::operator()(Windows::Internal::AsyncStage,long,Windows::Internal::CBasicResult<uchar,0> &)

- ea: `0x180081adc`
- end: `0x1800821a8`
- name: `??R_lambda_da225a7cdf57dc8e8263eb3946dbc5ab_@@QEAAJW4AsyncStage@Internal@Windows@@JAEAV?$CBasicResult@E$0A@@23@@Z`
- size: `1740`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009e8b0`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x18001efd0`
- `0x18001f000`
- `0x1800596d8`
- `0x18006e350`
- `0x18006f528`
- `0x180073094`
- `0x18007e590`
- `0x180081adc`
- `0x180083024`
- `0x1800830f4`
- `0x180083184`
- `0x18008326c`
- `0x18008effc`
- `0x18008fe88`
- `0x18008ff34`
- `0x18008ffe0`
- `0x1800905bc`
- `0x18009a254`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081f9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081c7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081d51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081d65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081e5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081f86`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180081f9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180082011`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081b8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081e1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180081ffd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180082042`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800820f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall _lambda_da225a7cdf57dc8e8263eb3946dbc5ab_::operator()(_QWORD *a1, int a2, int a3, __int64 a4)
{
  _QWORD *v5; // r13
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, HSTRING *); // rbx
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdi
  void (__fastcall *v11)(__int64, HSTRING *); // rbx
  _QWORD *v12; // r12
  int ActiveShellUser; // eax
  int v14; // r15d
  int v15; // r14d
  int v16; // edx
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, HSTRING, _QWORD); // rbx
  int v19; // ebx
  unsigned int *v20; // rdi
  int v21; // edx
  int v22; // eax
  __int64 v23; // r9
  __int64 v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rdx
  bool v27; // cl
  __int64 v28; // r14
  __int64 (__fastcall *v29)(__int64, HSTRING *); // rbx
  int v30; // ebx
  HSTRING v31; // rcx
  __int64 v32; // r14
  void (__fastcall *v33)(__int64, HSTRING *); // rbx
  int v34; // edx
  __int64 v35; // rdx
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, HSTRING *); // rbx
  __int64 v38; // r8
  __int64 v40; // rbx
  __int64 v41; // rdx
  int ProtocolOperation; // eax
  __int64 v43; // rdx
  int v44; // [rsp+20h] [rbp-B9h]
  int v45; // [rsp+20h] [rbp-B9h]
  __int64 v46; // [rsp+28h] [rbp-B1h]
  HSTRING v47; // [rsp+70h] [rbp-69h] BYREF
  HSTRING v48; // [rsp+78h] [rbp-61h] BYREF
  PCWSTR v49; // [rsp+80h] [rbp-59h] BYREF
  HSTRING v50; // [rsp+88h] [rbp-51h] BYREF
  HSTRING string; // [rsp+90h] [rbp-49h] BYREF
  __int64 (__fastcall ***v52)(_QWORD, GUID *, __int64); // [rsp+98h] [rbp-41h] BYREF
  PCWSTR v53; // [rsp+A0h] [rbp-39h] BYREF
  PCWSTR StringRawBuffer; // [rsp+A8h] [rbp-31h] BYREF
  _BYTE v55[128]; // [rsp+B0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]
  int v57; // [rsp+150h] [rbp+77h] BYREF
  __int64 v58; // [rsp+158h] [rbp+7Fh]

  v58 = a4;
  if ( a3 >= 0 && a2 == 1 )
  {
    v5 = a1 + 14;
    wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
      (struct wil::details::IFailureCallback *)(a1 + 14),
      (wil::ActivityThreadWatcher *)v55);
    v50 = 0;
    v6 = a1[2];
    v7 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v6 + 128LL);
    WindowsDeleteString(0);
    v50 = 0;
    v8 = v7(v6, &v50);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x284,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)v8,
        v44);
LABEL_48:
      WindowsDeleteString(v50);
      v50 = 0;
      wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v55);
      return v9;
    }
    string = 0;
    v10 = a1[2];
    if ( v10 )
    {
      v11 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v10 + 136LL);
      WindowsDeleteString(0);
      string = 0;
      v11(v10, &string);
    }
    v12 = a1 + 9;
    if ( !a1[9] && (IsMuaApp() || IsNonInteractiveUserProcess()) )
    {
      ActiveShellUser = GetActiveShellUser(a1 + 9);
      if ( ActiveShellUser < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x293,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)(unsigned int)ActiveShellUser,
          v44);
    }
    v14 = ((a1[12] & 0xE) << 6) | ((a1[12] & 1) << 6);
    v52 = 0;
    v15 = v14 | (*((_BYTE *)a1 + 81) != 0 ? 0x20 : 0);
    if ( *((_BYTE *)a1 + 80) )
      v15 |= 0x400u;
    if ( *(_QWORD *)(a1[5] + 8LL) )
    {
      GetSerializedPropertySet(
        (struct Windows::Foundation::Collections::IPropertySet *)&v47,
        (LauncherMiscHelpers *)a1[6]);
      GetSerializedPropertySet(
        (struct Windows::Foundation::Collections::IPropertySet *)&v48,
        (LauncherMiscHelpers *)a1[7]);
      LOBYTE(v57) = *v12 != 0;
      StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(a1[5] + 8LL), 0);
      v53 = WindowsGetStringRawBuffer(string, 0);
      v49 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[13] + 8LL), 0);
      LauncherClientProvider::LaunchUriAsync::LaunchUriRequest<unsigned short const (&)[22],unsigned short const *,unsigned long &,unsigned short const *,unsigned short const *,bool>(
        (_DWORD)v5,
        v16,
        (unsigned int)&v49,
        (_DWORD)a1 + 8,
        (__int64)&v53,
        (__int64)&StringRawBuffer,
        (__int64)&v57);
      v17 = *a1;
      v18 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, _QWORD))(*(_QWORD *)*a1 + 72LL);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
      v46 = a1[4];
      v45 = *((_DWORD *)a1 + 6);
      v19 = v18(v17, *((unsigned int *)a1 + 2), v50, *(_QWORD *)(a1[5] + 8LL));
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      v20 = (unsigned int *)(a1 + 1);
    }
    else
    {
      LOBYTE(v57) = *v12 != 0;
      v49 = WindowsGetStringRawBuffer(string, 0);
      v53 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[13] + 8LL), 0);
      v20 = (unsigned int *)(a1 + 1);
      LauncherClientProvider::LaunchUriAsync::LaunchUriRequest<unsigned short const (&)[10],unsigned short const *,unsigned long &,unsigned short const *,unsigned short const (&)[1],bool>(
        (_DWORD)v5,
        v21,
        (unsigned int)&v53,
        (_DWORD)a1 + 8,
        (__int64)&v49);
      v46 = *(_QWORD *)(a1[11] + 8LL);
      v45 = v15;
      v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING, _QWORD))(*(_QWORD *)*a1 + 56LL))(
              *a1,
              *((unsigned int *)a1 + 2),
              v50,
              *v12);
    }
    v57 = v19;
    if ( v19 < 0 )
    {
      v49 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[13] + 8LL), 0);
      LauncherClientProvider::LaunchUriAsync::LaunchUriFailure<unsigned short const (&)[32],unsigned short const *,long &>(
        v5,
        v26,
        &v49,
        &v57);
      if ( v19 == -2147219711 )
      {
        *(_BYTE *)(v58 + 16) = 0;
        v48 = 0;
        v49 = (PCWSTR)*a1;
        if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,unsigned long &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(
                    &v48,
                    v20,
                    a1 + 9,
                    &v49) >= 0 )
          (*(void (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v48 + 48LL))(v48, *(_QWORD *)(a1[5] + 8LL));
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v48);
      }
      else if ( v19 == -2147023741 )
      {
        if ( *(_QWORD *)(a1[5] + 8LL) )
        {
          v27 = 0;
        }
        else
        {
          v28 = a1[8];
          if ( v28 )
          {
            v48 = 0;
            v29 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v28 + 128LL);
            WindowsDeleteString(0);
            v48 = 0;
            v30 = v29(v28, &v48);
            v57 = v30;
            if ( v30 < 0 )
              goto LABEL_36;
            v31 = 0;
            v47 = 0;
            v32 = a1[8];
            if ( v32 )
            {
              v33 = *(void (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v32 + 136LL);
              WindowsDeleteString(0);
              v47 = 0;
              v33(v32, &v47);
              v31 = v47;
            }
            LOBYTE(v57) = *v12 != 0;
            v49 = WindowsGetStringRawBuffer(v31, 0);
            v53 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[13] + 8LL), 0);
            LauncherClientProvider::LaunchUriAsync::LaunchUriRequest<unsigned short const (&)[18],unsigned short const *,unsigned long &,unsigned short const *,unsigned short const (&)[1],bool>(
              (_DWORD)v5,
              v34,
              (unsigned int)&v53,
              (_DWORD)v20,
              (__int64)&v49,
              v46,
              (__int64)&v57);
            v30 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, HSTRING, _QWORD, unsigned int, _QWORD))(*(_QWORD *)*a1 + 56LL))(
                    *a1,
                    *v20,
                    v48,
                    *v12,
                    v14 | 0x20u,
                    *(_QWORD *)(a1[11] + 8LL));
            v57 = v30;
            WindowsDeleteString(v47);
            if ( v30 < 0 )
            {
LABEL_36:
              v49 = WindowsGetStringRawBuffer(*(HSTRING *)(a1[13] + 8LL), 0);
              LauncherClientProvider::LaunchUriAsync::LaunchUriFailure<unsigned short const (&)[29],unsigned short const *,long &>(
                v5,
                v35,
                &v49,
                &v57);
            }
          }
          else
          {
            v48 = 0;
            v36 = a1[2];
            v37 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 136LL);
            WindowsDeleteString(0);
            v48 = 0;
            v30 = v37(v36, &v48);
            if ( v30 >= 0 )
            {
              v47 = 0;
              v49 = (PCWSTR)*a1;
              v30 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,unsigned long &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(
                      &v47,
                      a1 + 1,
                      a1 + 9,
                      &v49);
              if ( v30 >= 0 )
              {
                LOBYTE(v38) = 1;
                v30 = (*(__int64 (__fastcall **)(HSTRING, HSTRING, __int64))(*(_QWORD *)v47 + 56LL))(v47, v48, v38);
              }
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            }
          }
          WindowsDeleteString(v48);
          v27 = v30 >= 0;
        }
        *(_BYTE *)(v58 + 16) = v27;
      }
      else
      {
        *(_BYTE *)(v58 + 16) = 0;
      }
      v19 = 0;
      v25 = 0;
    }
    else
    {
      if ( *((_DWORD *)a1 + 6) == 3 )
      {
        v47 = 0;
        v22 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::System::Private::IProtocolOperationWaitForResultsPriv>(
                &v52,
                (__int64)&v47);
        v9 = v22;
        if ( v22 >= 0 )
        {
          `Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<unsigned char,0>>'::`3'::LaunchUriAsyncOpState::SetProtocolOperation(
            a1[56],
            v47);
          v9 = -2147467263;
          v23 = 2147500033LL;
          v24 = 704;
        }
        else
        {
          v23 = (unsigned int)v22;
          v24 = 698;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v24,
          (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
          (const char *)v23,
          v45);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
        WindowsDeleteString(string);
        goto LABEL_47;
      }
      *(_BYTE *)(v58 + 16) = 1;
      v25 = v19;
    }
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v5,
      (unsigned int)v19);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
    WindowsDeleteString(string);
    v9 = v25;
LABEL_47:
    string = 0;
    goto LABEL_48;
  }
  if ( a2 == 2 )
  {
    v50 = 0;
    v40 = a1[56];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    ProtocolOperation = `Launcher::_LaunchUriInternalAsync<Windows::System::LaunchUriResult *,Windows::Internal::CMarshaledInterfaceResult<Windows::System::ILaunchUriResult>>'::`3'::LaunchUriAsyncOpState::GetProtocolOperation(
                          v40,
                          v41,
                          &v50);
    v9 = ProtocolOperation;
    if ( ProtocolOperation < 0 )
    {
      v43 = 807;
LABEL_56:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v43,
        (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
        (const char *)(unsigned int)ProtocolOperation,
        v44);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
      return v9;
    }
    if ( v50 )
    {
      ProtocolOperation = (*(__int64 (__fastcall **)(HSTRING, _QWORD))(*(_QWORD *)v50 + 48LL))(v50, 0);
      v9 = ProtocolOperation;
      if ( ProtocolOperation < 0 )
      {
        v43 = 810;
        goto LABEL_56;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  }
  return 0;
}

```

## disassembly

```asm
0x180081adc  mov     [rsp-8+arg_0], rbx
0x180081ae1  mov     [rsp-8+arg_18], r9
0x180081ae6  push    rbp
0x180081ae7  push    rsi
0x180081ae8  push    rdi
0x180081ae9  push    r12
0x180081aeb  push    r13
0x180081aed  push    r14
0x180081aef  push    r15
0x180081af1  lea     rbp, [rsp-27h]
0x180081af6  sub     rsp, 100h
0x180081afd  mov     rsi, rcx
0x180081b00  xor     r14d, r14d
0x180081b03  test    r8d, r8d
0x180081b06  js      loc_18008210F
0x180081b0c  cmp     edx, 1
0x180081b0f  jnz     loc_18008210F
0x180081b15  lea     r13, [rcx+70h]
0x180081b19  lea     rdx, [rbp+57h+var_80]; this
0x180081b1d  mov     rcx, r13; struct wil::details::IFailureCallback *
0x180081b20  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180081b25  nop
0x180081b26  mov     [rbp+57h+var_A8], r14
0x180081b2a  mov     rdi, [rsi+10h]
0x180081b2e  mov     rax, [rdi]
0x180081b31  mov     rbx, [rax+80h]
0x180081b38  xor     ecx, ecx; string
0x180081b3a  call    cs:__imp_WindowsDeleteString
0x180081b40  mov     [rbp+57h+var_A8], r14
0x180081b44  lea     rdx, [rbp+57h+var_A8]
0x180081b48  mov     rcx, rdi
0x180081b4b  mov     rax, rbx
0x180081b4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081b53  mov     ebx, eax
0x180081b55  test    eax, eax
0x180081b57  jns     short loc_180081B76
0x180081b59  mov     rcx, [rbp+5Fh]; this
0x180081b5d  mov     r9d, eax; char *
0x180081b60  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180081b67  mov     edx, 284h; void *
0x180081b6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081b71  jmp     loc_1800820F4
0x180081b76  mov     [rbp+57h+string], r14
0x180081b7a  mov     rdi, [rsi+10h]
0x180081b7e  test    rdi, rdi
0x180081b81  jz      short loc_180081BA8
0x180081b83  mov     rax, [rdi]
0x180081b86  mov     rbx, [rax+88h]
0x180081b8d  xor     ecx, ecx; string
0x180081b8f  call    cs:__imp_WindowsDeleteString
0x180081b95  mov     [rbp+57h+string], r14
0x180081b99  lea     rdx, [rbp+57h+string]
0x180081b9d  mov     rcx, rdi
0x180081ba0  mov     rax, rbx
0x180081ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ba8  lea     r12, [rsi+48h]
0x180081bac  cmp     [r12], r14
0x180081bb0  jnz     short loc_180081BE8
0x180081bb2  call    ?IsMuaApp@@YA_NXZ; IsMuaApp(void)
0x180081bb7  test    al, al
0x180081bb9  jnz     short loc_180081BC4
0x180081bbb  call    ?IsNonInteractiveUserProcess@@YA_NXZ; IsNonInteractiveUserProcess(void)
0x180081bc0  test    al, al
0x180081bc2  jz      short loc_180081BE8
0x180081bc4  mov     rcx, r12; unsigned __int64 *
0x180081bc7  call    ?GetActiveShellUser@@YAJPEA_K@Z; GetActiveShellUser(unsigned __int64 *)
0x180081bcc  mov     rcx, [rbp+5Fh]; this
0x180081bd0  test    eax, eax
0x180081bd2  jns     short loc_180081BE8
0x180081bd4  mov     r9d, eax; char *
0x180081bd7  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180081bde  mov     edx, 293h; void *
0x180081be3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180081be8  mov     eax, [rsi+60h]
0x180081beb  mov     r15d, eax
0x180081bee  and     r15d, 1
0x180081bf2  shl     r15d, 6
0x180081bf6  and     eax, 0Eh
0x180081bf9  shl     eax, 6
0x180081bfc  or      r15d, eax
0x180081bff  mov     [rbp+57h+var_98], r14
0x180081c03  mov     al, [rsi+51h]
0x180081c06  neg     al
0x180081c08  sbb     r14d, r14d
0x180081c0b  and     r14d, 20h
0x180081c0f  or      r14d, r15d
0x180081c12  xor     ebx, ebx
0x180081c14  cmp     [rsi+50h], bl
0x180081c17  jz      short loc_180081C1E
0x180081c19  bts     r14d, 0Ah
0x180081c1e  mov     rax, [rsi+28h]
0x180081c22  cmp     [rax+8], rbx
0x180081c26  jz      loc_180081D43
0x180081c2c  mov     rdx, [rsi+30h]; this
0x180081c30  lea     rcx, [rbp+57h+var_C0]; struct Windows::Foundation::Collections::IPropertySet *
0x180081c34  call    ?GetSerializedPropertySet@@YA?AV?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; GetSerializedPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180081c39  nop
0x180081c3a  mov     rdx, [rsi+38h]; this
0x180081c3e  lea     rcx, [rbp+57h+var_B8]; struct Windows::Foundation::Collections::IPropertySet *
0x180081c42  call    ?GetSerializedPropertySet@@YA?AV?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@PEAUIPropertySet@Collections@Foundation@Windows@@@Z; GetSerializedPropertySet(Windows::Foundation::Collections::IPropertySet *)
0x180081c47  nop
0x180081c48  cmp     [r12], rbx
0x180081c4c  setnz   byte ptr [rbp+57h+arg_10]
0x180081c50  mov     rcx, [rsi+28h]
0x180081c54  xor     edx, edx; length
0x180081c56  mov     rcx, [rcx+8]; string
0x180081c5a  call    cs:__imp_WindowsGetStringRawBuffer
0x180081c60  mov     [rbp+57h+var_88], rax
0x180081c64  xor     edx, edx; length
0x180081c66  mov     rcx, [rbp+57h+string]; string
0x180081c6a  call    cs:__imp_WindowsGetStringRawBuffer
0x180081c70  mov     [rbp+57h+var_90], rax
0x180081c74  mov     rcx, [rsi+68h]
0x180081c78  xor     edx, edx; length
0x180081c7a  mov     rcx, [rcx+8]; string
0x180081c7e  call    cs:__imp_WindowsGetStringRawBuffer
0x180081c84  mov     [rbp+57h+var_B0], rax
0x180081c88  lea     r9, [rsi+8]
0x180081c8c  lea     rcx, [rbp+57h+arg_10]
0x180081c90  mov     [rsp+130h+var_100], rcx
0x180081c95  lea     rcx, [rbp+57h+var_88]
0x180081c99  mov     [rsp+130h+var_108], rcx
0x180081c9e  lea     rcx, [rbp+57h+var_90]
0x180081ca2  mov     qword ptr [rsp+130h+var_110], rcx
0x180081ca7  lea     r8, [rbp+57h+var_B0]
0x180081cab  mov     rcx, r13
0x180081cae  call    ??$LaunchUriRequest@AEAY0BG@$$CBGPEBGAEAKPEBGPEBG_N@LaunchUriAsync@LauncherClientProvider@@QEAAXAEAY0BG@$$CBG$$QEAPEBGAEAK11$$QEA_N@Z; LauncherClientProvider::LaunchUriAsync::LaunchUriRequest<ushort const (&)[22],ushort const *,ulong &,ushort const *,ushort const *,bool>(ushort const (&)[22],ushort const * &&,ulong &,ushort const * &&,ushort const * &&,bool &&)
0x180081cb3  mov     rdi, [rsi]
0x180081cb6  mov     rax, [rdi]
0x180081cb9  mov     rbx, [rax+48h]
0x180081cbd  lea     rcx, [rbp+57h+var_98]
0x180081cc1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081cc6  mov     rax, [rsi+58h]
0x180081cca  mov     r9, [rsi+28h]
0x180081cce  mov     edx, [rsi+8]
0x180081cd1  lea     rcx, [rbp+57h+var_98]
0x180081cd5  mov     [rsp+130h+var_D8], rcx
0x180081cda  mov     rax, [rax+8]
0x180081cde  mov     [rsp+130h+var_E0], rax
0x180081ce3  mov     [rsp+130h+var_E8], r14d
0x180081ce8  mov     r8, [r12]
0x180081cec  mov     [rsp+130h+var_F0], r8
0x180081cf1  mov     r8, [rbp+57h+var_C0]
0x180081cf5  mov     [rsp+130h+var_F8], r8
0x180081cfa  mov     r8, [rbp+57h+var_B8]
0x180081cfe  mov     [rsp+130h+var_100], r8
0x180081d03  mov     r8, [rsi+20h]
0x180081d07  mov     [rsp+130h+var_108], r8
0x180081d0c  mov     r8d, [rsi+18h]
0x180081d10  mov     [rsp+130h+var_110], r8d
0x180081d15  mov     r9, [r9+8]
0x180081d19  mov     r8, [rbp+57h+var_A8]
0x180081d1d  mov     rcx, rdi
0x180081d20  mov     rax, rbx
0x180081d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d28  mov     ebx, eax
0x180081d2a  lea     rcx, [rbp+57h+var_B8]
0x180081d2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081d33  nop
0x180081d34  lea     rcx, [rbp+57h+var_C0]
0x180081d38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081d3d  lea     rdi, [rsi+8]
0x180081d41  jmp     short loc_180081DC1
0x180081d43  cmp     [r12], rbx
0x180081d47  setnz   byte ptr [rbp+57h+arg_10]
0x180081d4b  xor     edx, edx; length
0x180081d4d  mov     rcx, [rbp+57h+string]; string
0x180081d51  call    cs:__imp_WindowsGetStringRawBuffer
0x180081d57  mov     [rbp+57h+var_B0], rax
0x180081d5b  mov     rcx, [rsi+68h]
0x180081d5f  xor     edx, edx; length
0x180081d61  mov     rcx, [rcx+8]; string
0x180081d65  call    cs:__imp_WindowsGetStringRawBuffer
0x180081d6b  mov     [rbp+57h+var_90], rax
0x180081d6f  lea     rdi, [rsi+8]
0x180081d73  lea     rax, [rbp+57h+arg_10]
0x180081d77  mov     [rsp+130h+var_100], rax
0x180081d7c  lea     rax, [rbp+57h+var_B0]
0x180081d80  mov     qword ptr [rsp+130h+var_110], rax
0x180081d85  mov     r9, rdi
0x180081d88  lea     r8, [rbp+57h+var_90]
0x180081d8c  mov     rcx, r13
0x180081d8f  call    ??$LaunchUriRequest@AEAY09$$CBGPEBGAEAKPEBGAEAY00$$CBG_N@LaunchUriAsync@LauncherClientProvider@@QEAAXAEAY09$$CBG$$QEAPEBGAEAK1AEAY00$$CBG$$QEA_N@Z; LauncherClientProvider::LaunchUriAsync::LaunchUriRequest<ushort const (&)[10],ushort const *,ulong &,ushort const *,ushort const (&)[1],bool>(ushort const (&)[10],ushort const * &&,ulong &,ushort const * &&,ushort const (&)[1],bool &&)
0x180081d94  mov     rcx, [rsi]
0x180081d97  mov     rax, [rcx]
0x180081d9a  mov     r9, [rsi+58h]
0x180081d9e  mov     edx, [rdi]
0x180081da0  mov     r9, [r9+8]
0x180081da4  mov     [rsp+130h+var_108], r9
0x180081da9  mov     [rsp+130h+var_110], r14d; int
0x180081dae  mov     r9, [r12]
0x180081db2  mov     r8, [rbp+57h+var_A8]
0x180081db6  mov     rax, [rax+38h]
0x180081dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081dbf  mov     ebx, eax
0x180081dc1  mov     [rbp+57h+arg_10], ebx
0x180081dc4  xor     r14d, r14d
0x180081dc7  test    ebx, ebx
0x180081dc9  js      loc_180081E55
0x180081dcf  cmp     dword ptr [rsi+18h], 3
0x180081dd3  jnz     short loc_180081E46
0x180081dd5  mov     [rbp+57h+var_C0], r14
0x180081dd9  lea     rdx, [rbp+57h+var_C0]
0x180081ddd  lea     rcx, [rbp+57h+var_98]
0x180081de1  call    ??$As@UIProtocolOperationWaitForResultsPriv@Private@System@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIProtocolOperationWaitForResultsPriv@Private@System@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::System::Private::IProtocolOperationWaitForResultsPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Private::IProtocolOperationWaitForResultsPriv>>)
0x180081de6  mov     ebx, eax
0x180081de8  test    eax, eax
0x180081dea  jns     short loc_180081E27
0x180081dec  mov     r9d, eax; char *
0x180081def  mov     edx, 2BAh; void *
0x180081df4  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180081dfb  mov     rcx, [rbp+5Fh]; this
0x180081dff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081e04  lea     rcx, [rbp+57h+var_C0]
0x180081e08  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081e0d  nop
0x180081e0e  lea     rcx, [rbp+57h+var_98]
0x180081e12  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081e17  nop
0x180081e18  mov     rcx, [rbp+57h+string]; string
0x180081e1c  call    cs:__imp_WindowsDeleteString
0x180081e22  jmp     loc_1800820F0
0x180081e27  mov     rdx, [rbp+57h+var_C0]
0x180081e2b  mov     rcx, [rsi+1C0h]
0x180081e32  call    ?SetProtocolOperation@LaunchUriAsyncOpState@?2???$_LaunchUriInternalAsync@_NV?$CBasicResult@E$0A@@Internal@Windows@@@Launcher@@AEAAJPEAUIUriRuntimeClass@Foundation@Windows@@W4LaunchType@Launch@Internal@System@5@PEAUILauncherOptions@95@PEAUIPropertySet@Collections@45@3_KPEAUHSTRING__@@PEAPEAU?$IAsyncOperation@_N@45@@Z@QEAAXPEAUIProtocolOperationWaitForResultsPriv@Private@95@@Z; `Launcher::_LaunchUriInternalAsync<bool,Windows::Internal::CBasicResult<uchar,0>>(Windows::Foundation::IUriRuntimeClass *,Windows::System::Internal::Launch::LaunchType,Windows::System::ILauncherOptions *,Windows::Foundation::Collections::IPropertySet *,Windows::Foundation::Collections::IPropertySet *,unsigned __int64,HSTRING__ *,Windows::Foundation::IAsyncOperation<bool> * *)'::`3'::LaunchUriAsyncOpState::SetProtocolOperation(Windows::System::Private::IProtocolOperationWaitForResultsPriv *)
0x180081e37  mov     ebx, 80004001h
0x180081e3c  mov     r9d, ebx
0x180081e3f  mov     edx, 2C0h
0x180081e44  jmp     short loc_180081DF4
0x180081e46  mov     rax, [rbp+57h+arg_18]
0x180081e4a  mov     byte ptr [rax+10h], 1
0x180081e4e  mov     edi, ebx
0x180081e50  jmp     loc_1800820CF
0x180081e55  mov     rcx, [rsi+68h]
0x180081e59  xor     edx, edx; length
0x180081e5b  mov     rcx, [rcx+8]; string
0x180081e5f  call    cs:__imp_WindowsGetStringRawBuffer
0x180081e65  mov     [rbp+57h+var_B0], rax
0x180081e69  lea     r9, [rbp+57h+arg_10]
0x180081e6d  lea     r8, [rbp+57h+var_B0]
0x180081e71  mov     rcx, r13
0x180081e74  call    ??$LaunchUriFailure@AEAY0CA@$$CBGPEBGAEAJ@LaunchUriAsync@LauncherClientProvider@@QEAAXAEAY0CA@$$CBG$$QEAPEBGAEAJ@Z; LauncherClientProvider::LaunchUriAsync::LaunchUriFailure<ushort const (&)[32],ushort const *,long &>(ushort const (&)[32],ushort const * &&,long &)
0x180081e79  cmp     ebx, 80040701h
0x180081e7f  jnz     short loc_180081ED2
0x180081e81  mov     rax, [rbp+57h+arg_18]
0x180081e85  mov     [rax+10h], r14b
0x180081e89  mov     [rbp+57h+var_B8], r14
0x180081e8d  mov     rax, [rsi]
0x180081e90  mov     [rbp+57h+var_B0], rax
0x180081e94  lea     r9, [rbp+57h+var_B0]
0x180081e98  mov     r8, r12
0x180081e9b  mov     rdx, rdi
0x180081e9e  lea     rcx, [rbp+57h+var_B8]
0x180081ea2  call    ??$MakeAndInitialize@VStoreLauncher@Launch@Internal@System@Windows@@V12345@AEAKAEA_KPEAUILauncherService@2345@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VStoreLauncher@Launch@Internal@System@Windows@@@WRL@Microsoft@@@012@AEAKAEA_K$$QEAPEAUILauncherService@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::StoreLauncher>>,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService * &&)
0x180081ea7  test    eax, eax
0x180081ea9  js      short loc_180081EC4
0x180081eab  mov     rcx, [rbp+57h+var_B8]
0x180081eaf  mov     rax, [rcx]
0x180081eb2  mov     rdx, [rsi+28h]
0x180081eb6  mov     rdx, [rdx+8]
0x180081eba  mov     rax, [rax+30h]
0x180081ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081ec3  nop
0x180081ec4  lea     rcx, [rbp+57h+var_B8]
0x180081ec8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180081ecd  jmp     loc_1800820C9
0x180081ed2  cmp     ebx, 80070483h
0x180081ed8  jnz     loc_1800820C1
0x180081ede  mov     rax, [rsi+28h]
0x180081ee2  cmp     [rax+8], r14
0x180081ee6  jz      short loc_180081EF0
0x180081ee8  mov     cl, r14b
0x180081eeb  jmp     loc_1800820B8
0x180081ef0  mov     r14, [rsi+40h]
0x180081ef4  test    r14, r14
0x180081ef7  jz      loc_18008202E
0x180081efd  mov     [rbp+57h+var_B8], 0
0x180081f05  mov     rax, [r14]
0x180081f08  mov     rbx, [rax+80h]
0x180081f0f  xor     ecx, ecx; string
0x180081f11  call    cs:__imp_WindowsDeleteString
0x180081f17  mov     [rbp+57h+var_B8], 0
0x180081f1f  lea     rdx, [rbp+57h+var_B8]
0x180081f23  mov     rcx, r14
0x180081f26  mov     rax, rbx
0x180081f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081f2e  mov     ebx, eax
0x180081f30  mov     [rbp+57h+arg_10], eax
0x180081f33  xor     r14d, r14d
0x180081f36  test    eax, eax
0x180081f38  js      loc_180082007
0x180081f3e  mov     ecx, r14d; string
0x180081f41  mov     [rbp+57h+var_C0], rcx
0x180081f45  mov     r14, [rsi+40h]
0x180081f49  test    r14, r14
0x180081f4c  jz      short loc_180081F79
0x180081f4e  mov     rax, [r14]
0x180081f51  mov     rbx, [rax+88h]
0x180081f58  call    cs:__imp_WindowsDeleteString
0x180081f5e  mov     [rbp+57h+var_C0], 0
  ... truncated ...
```
