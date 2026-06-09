# _lambda_4c3535c0fa3976dd819b46a4876c5029_::operator()(Windows::Internal::CBasicResult<uchar,0> &)

- ea: `0x180093c5c`
- end: `0x180094084`
- name: `??R_lambda_4c3535c0fa3976dd819b46a4876c5029_@@QEAAJAEAV?$CBasicResult@E$0A@@Internal@Windows@@@Z`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ea20`

## callees

- `0x1800049bc`
- `0x180010c04`
- `0x1800488f4`
- `0x180068af4`
- `0x18006e350`
- `0x18006f528`
- `0x180073094`
- `0x18008f7e4`
- `0x18008f890`
- `0x18008f93c`
- `0x18008fa28`
- `0x18008fb14`
- `0x1800905bc`
- `0x1800906f4`
- `0x180093c5c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180093caf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180093caf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093d5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ca6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093cd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093ce8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093d5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093dd4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093eeb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093eff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180093f6c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093fd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093ec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093f58`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093f8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180093fd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094041`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _lambda_4c3535c0fa3976dd819b46a4876c5029_::operator()(HSTRING *a1, __int64 a2)
{
  _QWORD *v4; // rsi
  HSTRING v5; // rcx
  const WCHAR *StringRawBuffer; // rax
  HSTRING v7; // rcx
  unsigned int *v8; // r15
  __int64 *v9; // r12
  struct Windows::Storage::IStorageItem **v10; // r13
  int v11; // edx
  int v12; // eax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // edi
  __int64 v16; // rdx
  HSTRING v17; // r12
  __int64 (__fastcall *v18)(HSTRING, HSTRING *); // rbx
  int v19; // ebx
  HSTRING v20; // rcx
  HSTRING v21; // r12
  void (__fastcall *v22)(HSTRING, HSTRING *); // rbx
  int v23; // edx
  __int64 v24; // rdx
  int v25; // eax
  unsigned int v26; // ebx
  int v28[2]; // [rsp+20h] [rbp-59h]
  __int64 v29; // [rsp+28h] [rbp-51h]
  _QWORD v30[2]; // [rsp+40h] [rbp-39h] BYREF
  _BYTE v31[128]; // [rsp+50h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  void *ExtensionW; // [rsp+E0h] [rbp+67h] BYREF
  HSTRING string; // [rsp+F0h] [rbp+77h] BYREF
  HSTRING v35; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = a1 + 11;
  wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
    (struct wil::details::IFailureCallback *)(a1 + 11),
    (wil::ActivityThreadWatcher *)v31);
  ExtensionW = 0;
  v5 = a1[3];
  if ( v5 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(*((HSTRING *)v5 + 1), 0);
    ExtensionW = PathFindExtensionW(StringRawBuffer);
  }
  v7 = (HSTRING)*((_QWORD *)a1[5] + 1);
  v8 = (unsigned int *)(a1 + 2);
  v9 = (__int64 *)(a1 + 8);
  v10 = (struct Windows::Storage::IStorageItem **)(a1 + 4);
  if ( v7 )
  {
    string = (HSTRING)WindowsGetStringRawBuffer(v7, 0);
    v35 = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
    LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<unsigned short const (&)[37],unsigned short const *,unsigned long &,unsigned short const * &,unsigned short const *>(
      (_DWORD)v4,
      v11,
      (unsigned int)&v35,
      (_DWORD)a1 + 16,
      (__int64)&ExtensionW,
      (__int64)&string);
    v29 = *v9;
    *(_QWORD *)v28 = *((_QWORD *)a1[5] + 1);
    v12 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, struct Windows::Storage::IStorageItem *, HSTRING))(*(_QWORD *)*a1 + 64LL))(
            *a1,
            *v8,
            *v10,
            a1[7]);
  }
  else
  {
    string = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
    LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<unsigned short const (&)[24],unsigned short const *,unsigned long &,unsigned short const * &,unsigned short const (&)[1]>(
      (_DWORD)v4,
      v13,
      (unsigned int)&string,
      (_DWORD)a1 + 16,
      (__int64)&ExtensionW);
    v29 = *((_QWORD *)a1[9] + 1);
    *(_QWORD *)v28 = *v9;
    v12 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, struct Windows::Storage::IStorageItem *, HSTRING))(*(_QWORD *)*a1 + 48LL))(
            *a1,
            *v8,
            *v10,
            a1[7]);
  }
  v14 = v12;
  LODWORD(ExtensionW) = v12;
  if ( v12 >= 0 )
  {
    *(_BYTE *)(a2 + 16) = 1;
    TryAddItemToRecent(*v10);
    v15 = v14;
LABEL_29:
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v4,
      v14);
    v26 = v15;
    goto LABEL_30;
  }
  string = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
  LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<unsigned short const (&)[28],unsigned short const *,long &>(
    v4,
    v16,
    &string,
    &ExtensionW);
  if ( v14 == -2147219711 )
  {
    *(_BYTE *)(a2 + 16) = 0;
    ExtensionW = 0;
    string = *a1;
    if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,unsigned long &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(
                &ExtensionW,
                a1 + 2,
                a1 + 8,
                &string) >= 0 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ExtensionW + 48LL))(ExtensionW, *((_QWORD *)a1[5] + 1));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ExtensionW);
    goto LABEL_28;
  }
  if ( v14 != -2147023741 || *((_QWORD *)a1[5] + 1) )
  {
    *(_BYTE *)(a2 + 16) = 0;
    goto LABEL_28;
  }
  v30[1] = 0;
  v17 = a1[6];
  if ( v17 )
  {
    v35 = 0;
    v18 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v17 + 128LL);
    WindowsDeleteString(0);
    v35 = 0;
    v19 = v18(v17, &v35);
    LODWORD(ExtensionW) = v19;
    if ( v19 < 0 )
      goto LABEL_19;
    v20 = 0;
    string = 0;
    v21 = a1[6];
    if ( v21 )
    {
      v22 = *(void (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v21 + 136LL);
      WindowsDeleteString(0);
      string = 0;
      v22(v21, &string);
      v20 = string;
    }
    ExtensionW = (void *)WindowsGetStringRawBuffer(v20, 0);
    v30[0] = WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
    LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<unsigned short const (&)[18],unsigned short const *,unsigned long &,unsigned short const *,unsigned short const (&)[1]>(
      (_DWORD)v4,
      v23,
      (unsigned int)v30,
      (_DWORD)a1 + 16,
      (__int64)&ExtensionW,
      v29);
    v19 = (*(__int64 (__fastcall **)(HSTRING, _QWORD, HSTRING, _QWORD, int, _QWORD))(*(_QWORD *)*a1 + 56LL))(
            *a1,
            *v8,
            v35,
            0,
            32,
            *((_QWORD *)a1[9] + 1));
    LODWORD(ExtensionW) = v19;
    WindowsDeleteString(string);
    if ( v19 < 0 )
    {
LABEL_19:
      string = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
      LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<unsigned short const (&)[29],unsigned short const *,long &>(
        v4,
        v24,
        &string,
        &ExtensionW);
    }
    WindowsDeleteString(v35);
LABEL_26:
    *(_BYTE *)(a2 + 16) = v19 >= 0;
    WindowsDeleteString(0);
LABEL_28:
    v14 = 0;
    v15 = 0;
    goto LABEL_29;
  }
  string = 0;
  v25 = Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<Windows::Storage::IStorageFile>(
          (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))a1 + 4,
          (__int64)&string);
  v26 = v25;
  if ( v25 >= 0 )
  {
    v35 = 0;
    v30[0] = *a1;
    LODWORD(ExtensionW) = 0;
    v19 = Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,unsigned long &,int,Windows::System::Internal::Launch::ILauncherService *>(
            &v35,
            a1 + 2,
            &ExtensionW,
            v30);
    if ( v19 >= 0 )
      v19 = (*(__int64 (__fastcall **)(HSTRING, HSTRING))(*(_QWORD *)v35 + 64LL))(v35, string);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72D,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
    (const char *)(unsigned int)v25,
    v28[0]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  WindowsDeleteString(0);
LABEL_30:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
  return v26;
}

```

## disassembly

```asm
0x180093c5c  mov     [rsp-8+arg_8], rbx
0x180093c61  push    rbp
0x180093c62  push    rsi
0x180093c63  push    rdi
0x180093c64  push    r12
0x180093c66  push    r13
0x180093c68  push    r14
0x180093c6a  push    r15
0x180093c6c  lea     rbp, [rsp-27h]
0x180093c71  sub     rsp, 0A0h
0x180093c78  mov     r14, rdx
0x180093c7b  mov     rdi, rcx
0x180093c7e  lea     rsi, [rcx+58h]
0x180093c82  lea     rdx, [rbp+57h+var_80]; this
0x180093c86  mov     rcx, rsi; struct wil::details::IFailureCallback *
0x180093c89  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x180093c8e  nop
0x180093c8f  mov     [rbp+57h+arg_0], 0
0x180093c97  mov     rcx, [rdi+18h]
0x180093c9b  test    rcx, rcx
0x180093c9e  jz      short loc_180093CB9
0x180093ca0  xor     edx, edx; length
0x180093ca2  mov     rcx, [rcx+8]; string
0x180093ca6  call    cs:__imp_WindowsGetStringRawBuffer
0x180093cac  mov     rcx, rax; pszPath
0x180093caf  call    cs:__imp_PathFindExtensionW
0x180093cb5  mov     [rbp+57h+arg_0], rax
0x180093cb9  mov     rax, [rdi+28h]
0x180093cbd  mov     rcx, [rax+8]; string
0x180093cc1  lea     r15, [rdi+10h]
0x180093cc5  lea     r12, [rdi+40h]
0x180093cc9  lea     r13, [rdi+20h]
0x180093ccd  xor     edx, edx; length
0x180093ccf  test    rcx, rcx
0x180093cd2  jz      short loc_180093D52
0x180093cd4  call    cs:__imp_WindowsGetStringRawBuffer
0x180093cda  mov     [rbp+57h+string], rax
0x180093cde  mov     rcx, [rdi+50h]
0x180093ce2  xor     edx, edx; length
0x180093ce4  mov     rcx, [rcx+8]; string
0x180093ce8  call    cs:__imp_WindowsGetStringRawBuffer
0x180093cee  mov     [rbp+57h+arg_18], rax
0x180093cf2  lea     rax, [rbp+57h+string]
0x180093cf6  mov     [rsp+0D0h+var_A8], rax
0x180093cfb  lea     rax, [rbp+57h+arg_0]
0x180093cff  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180093d04  mov     r9, r15
0x180093d07  lea     r8, [rbp+57h+arg_18]
0x180093d0b  mov     rcx, rsi
0x180093d0e  call    ??$LaunchFileRequest@AEAY0CF@$$CBGPEBGAEAKAEAPEBGPEBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0CF@$$CBG$$QEAPEBGAEAKAEAPEBG1@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[37],ushort const *,ulong &,ushort const * &,ushort const *>(ushort const (&)[37],ushort const * &&,ulong &,ushort const * &,ushort const * &&)
0x180093d13  mov     rcx, [rdi]
0x180093d16  mov     rax, [rcx]
0x180093d19  mov     r8, [rdi+48h]
0x180093d1d  mov     r9, [rdi+28h]
0x180093d21  mov     edx, [r15]
0x180093d24  mov     r8, [r8+8]
0x180093d28  mov     [rsp+0D0h+var_A0], r8
0x180093d2d  mov     r8, [r12]
0x180093d31  mov     [rsp+0D0h+var_A8], r8
0x180093d36  mov     r8, [r9+8]
0x180093d3a  mov     qword ptr [rsp+0D0h+var_B0], r8
0x180093d3f  mov     r9, [rdi+38h]
0x180093d43  mov     r8, [r13+0]
0x180093d47  mov     rax, [rax+40h]
0x180093d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093d50  jmp     short loc_180093DAC
0x180093d52  mov     rcx, [rdi+50h]
0x180093d56  mov     rcx, [rcx+8]; string
0x180093d5a  call    cs:__imp_WindowsGetStringRawBuffer
0x180093d60  mov     [rbp+57h+string], rax
0x180093d64  lea     rax, [rbp+57h+arg_0]
0x180093d68  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180093d6d  mov     r9, r15
0x180093d70  lea     r8, [rbp+57h+string]
0x180093d74  mov     rcx, rsi
0x180093d77  call    ??$LaunchFileRequest@AEAY0BI@$$CBGPEBGAEAKAEAPEBGAEAY00$$CBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BI@$$CBG$$QEAPEBGAEAKAEAPEBGAEAY00$$CBG@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[24],ushort const *,ulong &,ushort const * &,ushort const (&)[1]>(ushort const (&)[24],ushort const * &&,ulong &,ushort const * &,ushort const (&)[1])
0x180093d7c  mov     rcx, [rdi]
0x180093d7f  mov     rax, [rcx]
0x180093d82  mov     r8, [rdi+48h]
0x180093d86  mov     edx, [r15]
0x180093d89  mov     r8, [r8+8]
0x180093d8d  mov     [rsp+0D0h+var_A8], r8
0x180093d92  mov     r8, [r12]
0x180093d96  mov     qword ptr [rsp+0D0h+var_B0], r8; int
0x180093d9b  mov     r9, [rdi+38h]
0x180093d9f  mov     r8, [r13+0]
0x180093da3  mov     rax, [rax+30h]
0x180093da7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093dac  mov     ebx, eax
0x180093dae  mov     dword ptr [rbp+57h+arg_0], eax
0x180093db1  test    eax, eax
0x180093db3  js      short loc_180093DCA
0x180093db5  mov     byte ptr [r14+10h], 1
0x180093dba  mov     rcx, [r13+0]; struct Windows::Storage::IStorageItem *
0x180093dbe  call    ?TryAddItemToRecent@@YAXPEAUIStorageItem@Storage@Windows@@@Z; TryAddItemToRecent(Windows::Storage::IStorageItem *)
0x180093dc3  mov     edi, ebx
0x180093dc5  jmp     loc_180094052
0x180093dca  mov     rcx, [rdi+50h]
0x180093dce  xor     edx, edx; length
0x180093dd0  mov     rcx, [rcx+8]; string
0x180093dd4  call    cs:__imp_WindowsGetStringRawBuffer
0x180093dda  mov     [rbp+57h+string], rax
0x180093dde  lea     r9, [rbp+57h+arg_0]
0x180093de2  lea     r8, [rbp+57h+string]
0x180093de6  mov     rcx, rsi
0x180093de9  call    ??$LaunchFileFailure@AEAY0BM@$$CBGPEBGAEAJ@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BM@$$CBG$$QEAPEBGAEAJ@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<ushort const (&)[28],ushort const *,long &>(ushort const (&)[28],ushort const * &&,long &)
0x180093dee  cmp     ebx, 80040701h
0x180093df4  jnz     short loc_180093E48
0x180093df6  mov     byte ptr [r14+10h], 0
0x180093dfb  mov     [rbp+57h+arg_0], 0
0x180093e03  mov     rax, [rdi]
0x180093e06  mov     [rbp+57h+string], rax
0x180093e0a  lea     r9, [rbp+57h+string]
0x180093e0e  mov     r8, r12
0x180093e11  mov     rdx, r15
0x180093e14  lea     rcx, [rbp+57h+arg_0]
0x180093e18  call    ??$MakeAndInitialize@VStoreLauncher@Launch@Internal@System@Windows@@V12345@AEAKAEA_KPEAUILauncherService@2345@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VStoreLauncher@Launch@Internal@System@Windows@@@WRL@Microsoft@@@012@AEAKAEA_K$$QEAPEAUILauncherService@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::StoreLauncher>>,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService * &&)
0x180093e1d  test    eax, eax
0x180093e1f  js      short loc_180093E3A
0x180093e21  mov     rcx, [rbp+57h+arg_0]
0x180093e25  mov     rax, [rcx]
0x180093e28  mov     rdx, [rdi+28h]
0x180093e2c  mov     rdx, [rdx+8]
0x180093e30  mov     rax, [rax+30h]
0x180093e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093e39  nop
0x180093e3a  lea     rcx, [rbp+57h+arg_0]
0x180093e3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180093e43  jmp     loc_18009404E
0x180093e48  cmp     ebx, 80070483h
0x180093e4e  jnz     loc_180094049
0x180093e54  mov     rax, [rdi+28h]
0x180093e58  xor     ecx, ecx; string
0x180093e5a  cmp     [rax+8], rcx
0x180093e5e  jnz     loc_180094049
0x180093e64  mov     [rbp+57h+var_88], rcx
0x180093e68  mov     r12, [rdi+30h]
0x180093e6c  test    r12, r12
0x180093e6f  jz      loc_180093F96
0x180093e75  mov     [rbp+57h+arg_18], rcx
0x180093e79  mov     rax, [r12]
0x180093e7d  mov     rbx, [rax+80h]
0x180093e84  call    cs:__imp_WindowsDeleteString
0x180093e8a  mov     [rbp+57h+arg_18], 0
0x180093e92  lea     rdx, [rbp+57h+arg_18]
0x180093e96  mov     rcx, r12
0x180093e99  mov     rax, rbx
0x180093e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ea1  mov     ebx, eax
0x180093ea3  mov     dword ptr [rbp+57h+arg_0], eax
0x180093ea6  test    eax, eax
0x180093ea8  js      loc_180093F62
0x180093eae  xor     ecx, ecx; string
0x180093eb0  mov     [rbp+57h+string], rcx
0x180093eb4  mov     r12, [rdi+30h]
0x180093eb8  test    r12, r12
0x180093ebb  jz      short loc_180093EE9
0x180093ebd  mov     rax, [r12]
0x180093ec1  mov     rbx, [rax+88h]
0x180093ec8  call    cs:__imp_WindowsDeleteString
0x180093ece  mov     [rbp+57h+string], 0
0x180093ed6  lea     rdx, [rbp+57h+string]
0x180093eda  mov     rcx, r12
0x180093edd  mov     rax, rbx
0x180093ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093ee5  mov     rcx, [rbp+57h+string]; string
0x180093ee9  xor     edx, edx; length
0x180093eeb  call    cs:__imp_WindowsGetStringRawBuffer
0x180093ef1  mov     [rbp+57h+arg_0], rax
0x180093ef5  mov     rcx, [rdi+50h]
0x180093ef9  xor     edx, edx; length
0x180093efb  mov     rcx, [rcx+8]; string
0x180093eff  call    cs:__imp_WindowsGetStringRawBuffer
0x180093f05  mov     [rbp+57h+var_90], rax
0x180093f09  lea     rax, [rbp+57h+arg_0]
0x180093f0d  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180093f12  mov     r9, r15
0x180093f15  lea     r8, [rbp+57h+var_90]
0x180093f19  mov     rcx, rsi
0x180093f1c  call    ??$LaunchFileRequest@AEAY0BC@$$CBGPEBGAEAKPEBGAEAY00$$CBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BC@$$CBG$$QEAPEBGAEAK1AEAY00$$CBG@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[18],ushort const *,ulong &,ushort const *,ushort const (&)[1]>(ushort const (&)[18],ushort const * &&,ulong &,ushort const * &&,ushort const (&)[1])
0x180093f21  mov     rcx, [rdi]
0x180093f24  mov     rax, [rcx]
0x180093f27  mov     r8, [rdi+48h]
0x180093f2b  mov     edx, [r15]
0x180093f2e  mov     r8, [r8+8]
0x180093f32  mov     [rsp+0D0h+var_A8], r8
0x180093f37  mov     [rsp+0D0h+var_B0], 20h ; ' '
0x180093f3f  xor     r9d, r9d
0x180093f42  mov     r8, [rbp+57h+arg_18]
0x180093f46  mov     rax, [rax+38h]
0x180093f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093f4f  mov     ebx, eax
0x180093f51  mov     dword ptr [rbp+57h+arg_0], eax
0x180093f54  mov     rcx, [rbp+57h+string]; string
0x180093f58  call    cs:__imp_WindowsDeleteString
0x180093f5e  test    ebx, ebx
0x180093f60  jns     short loc_180093F87
0x180093f62  mov     rcx, [rdi+50h]
0x180093f66  xor     edx, edx; length
0x180093f68  mov     rcx, [rcx+8]; string
0x180093f6c  call    cs:__imp_WindowsGetStringRawBuffer
0x180093f72  mov     [rbp+57h+string], rax
0x180093f76  lea     r9, [rbp+57h+arg_0]
0x180093f7a  lea     r8, [rbp+57h+string]
0x180093f7e  mov     rcx, rsi
0x180093f81  call    ??$LaunchFileFailure@AEAY0BN@$$CBGPEBGAEAJ@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BN@$$CBG$$QEAPEBGAEAJ@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<ushort const (&)[29],ushort const *,long &>(ushort const (&)[29],ushort const * &&,long &)
0x180093f86  nop
0x180093f87  mov     rcx, [rbp+57h+arg_18]; string
0x180093f8b  call    cs:__imp_WindowsDeleteString
0x180093f91  jmp     loc_180094035
0x180093f96  mov     [rbp+57h+string], rcx
0x180093f9a  lea     rdx, [rbp+57h+string]
0x180093f9e  mov     rcx, r13
0x180093fa1  call    ??$As@UIStorageFile@Storage@Windows@@@?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<Windows::Storage::IStorageFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>)
0x180093fa6  mov     ebx, eax
0x180093fa8  test    eax, eax
0x180093faa  jns     short loc_180093FDC
0x180093fac  mov     rcx, [rbp+5Fh]; this
0x180093fb0  mov     r9d, eax; char *
0x180093fb3  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180093fba  mov     edx, 72Dh; void *
0x180093fbf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180093fc4  nop
0x180093fc5  lea     rcx, [rbp+57h+string]
0x180093fc9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180093fce  nop
0x180093fcf  xor     ecx, ecx; string
0x180093fd1  call    cs:__imp_WindowsDeleteString
0x180093fd7  jmp     loc_18009405E
0x180093fdc  mov     [rbp+57h+arg_18], 0
0x180093fe4  mov     rax, [rdi]
0x180093fe7  mov     [rbp+57h+var_90], rax
0x180093feb  mov     dword ptr [rbp+57h+arg_0], 0
0x180093ff2  lea     r9, [rbp+57h+var_90]
0x180093ff6  lea     r8, [rbp+57h+arg_0]
0x180093ffa  mov     rdx, r15
0x180093ffd  lea     rcx, [rbp+57h+arg_18]
0x180094001  call    ??$MakeAndInitialize@VStoreLauncher@Launch@Internal@System@Windows@@V12345@AEAKHPEAUILauncherService@2345@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VStoreLauncher@Launch@Internal@System@Windows@@@WRL@Microsoft@@@012@AEAK$$QEAH$$QEAPEAUILauncherService@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,ulong &,int,Windows::System::Internal::Launch::ILauncherService *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::StoreLauncher>>,ulong &,int &&,Windows::System::Internal::Launch::ILauncherService * &&)
0x180094006  mov     ebx, eax
0x180094008  test    eax, eax
0x18009400a  js      short loc_180094022
0x18009400c  mov     rcx, [rbp+57h+arg_18]
0x180094010  mov     rax, [rcx]
0x180094013  mov     rdx, [rbp+57h+string]
0x180094017  mov     rax, [rax+40h]
0x18009401b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094020  mov     ebx, eax
0x180094022  lea     rcx, [rbp+57h+arg_18]
0x180094026  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009402b  nop
0x18009402c  lea     rcx, [rbp+57h+string]
0x180094030  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180094035  shr     ebx, 1Fh
0x180094038  xor     bl, 1
0x18009403b  mov     [r14+10h], bl
0x18009403f  xor     ecx, ecx; string
0x180094041  call    cs:__imp_WindowsDeleteString
0x180094047  jmp     short loc_18009404E
0x180094049  mov     byte ptr [r14+10h], 0
0x18009404e  xor     ebx, ebx
0x180094050  xor     edi, edi
0x180094052  mov     edx, ebx
0x180094054  mov     rcx, rsi
0x180094057  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18009405c  mov     ebx, edi
0x18009405e  lea     rcx, [rbp+57h+var_80]; this
0x180094062  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180094067  mov     eax, ebx
0x180094069  mov     rbx, [rsp+0D0h+arg_8]
0x180094071  add     rsp, 0A0h
0x180094078  pop     r15
0x18009407a  pop     r14
0x18009407c  pop     r13
0x18009407e  pop     r12
0x180094080  pop     rdi
0x180094081  pop     rsi
0x180094082  pop     rbp
0x180094083  retn
```
