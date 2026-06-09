# _lambda_677a0aa250d01c8e687696f106069bec_::operator()(Windows::Internal::CBasicResult<Windows::System::LaunchFileStatus,4> &)

- ea: `0x18009408c`
- end: `0x1800944d8`
- name: `??R_lambda_677a0aa250d01c8e687696f106069bec_@@QEAAJAEAV?$CBasicResult@W4LaunchFileStatus@System@Windows@@$03@Internal@Windows@@@Z`
- size: `1100`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18009ea60`

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
- `0x18009408c`
- `0x180111010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800940df`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800940df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800940d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009418a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800943c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800940d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094104`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094118`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009418a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094206`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094341`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180094355`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800943c2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800942da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009431e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800942da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009431e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800943e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094427`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180094493`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall _lambda_677a0aa250d01c8e687696f106069bec_::operator()(HSTRING *a1, __int64 a2)
{
  _QWORD *v4; // r14
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
    *(_DWORD *)(a2 + 16) = 0;
    TryAddItemToRecent(*v10);
    v15 = v14;
LABEL_32:
    wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
      v4,
      v14);
    v26 = v15;
    goto LABEL_33;
  }
  string = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
  LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<unsigned short const (&)[28],unsigned short const *,long &>(
    v4,
    v16,
    &string,
    &ExtensionW);
  if ( v14 == -2147219711 )
  {
    *(_DWORD *)(a2 + 16) = 1;
    ExtensionW = 0;
    string = *a1;
    if ( (int)Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,unsigned long &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(
                &ExtensionW,
                a1 + 2,
                a1 + 8,
                &string) >= 0 )
      (*(void (__fastcall **)(void *, _QWORD))(*(_QWORD *)ExtensionW + 48LL))(ExtensionW, *((_QWORD *)a1[5] + 1));
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ExtensionW);
    goto LABEL_31;
  }
  if ( v14 == -2147024891 )
  {
    *(_DWORD *)(a2 + 16) = 2;
LABEL_31:
    v14 = 0;
    v15 = 0;
    goto LABEL_32;
  }
  if ( v14 != -2147023741 )
  {
    *(_DWORD *)(a2 + 16) = 4;
    goto LABEL_31;
  }
  if ( *((_QWORD *)a1[5] + 1) )
  {
    *(_DWORD *)(a2 + 16) = 3;
    goto LABEL_31;
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
      goto LABEL_22;
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
LABEL_22:
      string = (HSTRING)WindowsGetStringRawBuffer(*((HSTRING *)a1[10] + 1), 0);
      LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<unsigned short const (&)[29],unsigned short const *,long &>(
        v4,
        v24,
        &string,
        &ExtensionW);
    }
    WindowsDeleteString(v35);
LABEL_29:
    *(_DWORD *)(a2 + 16) = (unsigned int)v19 >> 31;
    WindowsDeleteString(0);
    goto LABEL_31;
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
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x72D,
    (unsigned int)"onecoreuap\\shell\\windows.system.launcher\\lib\\windows.system.launcher.cpp",
    (const char *)(unsigned int)v25,
    v28[0]);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&string);
  WindowsDeleteString(0);
LABEL_33:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v31);
  return v26;
}

```

## disassembly

```asm
0x18009408c  mov     [rsp-8+arg_8], rbx
0x180094091  push    rbp
0x180094092  push    rsi
0x180094093  push    rdi
0x180094094  push    r12
0x180094096  push    r13
0x180094098  push    r14
0x18009409a  push    r15
0x18009409c  lea     rbp, [rsp-27h]
0x1800940a1  sub     rsp, 0A0h
0x1800940a8  mov     rsi, rdx
0x1800940ab  mov     rdi, rcx
0x1800940ae  lea     r14, [rcx+58h]
0x1800940b2  lea     rdx, [rbp+57h+var_80]; this
0x1800940b6  mov     rcx, r14; struct wil::details::IFailureCallback *
0x1800940b9  call    ?ContinueOnCurrentThread@?$ActivityBase@VLauncherDesktopProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<LauncherDesktopProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x1800940be  nop
0x1800940bf  mov     [rbp+57h+arg_0], 0
0x1800940c7  mov     rcx, [rdi+18h]
0x1800940cb  test    rcx, rcx
0x1800940ce  jz      short loc_1800940E9
0x1800940d0  xor     edx, edx; length
0x1800940d2  mov     rcx, [rcx+8]; string
0x1800940d6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800940dc  mov     rcx, rax; pszPath
0x1800940df  call    cs:__imp_PathFindExtensionW
0x1800940e5  mov     [rbp+57h+arg_0], rax
0x1800940e9  mov     rax, [rdi+28h]
0x1800940ed  mov     rcx, [rax+8]; string
0x1800940f1  lea     r15, [rdi+10h]
0x1800940f5  lea     r12, [rdi+40h]
0x1800940f9  lea     r13, [rdi+20h]
0x1800940fd  xor     edx, edx; length
0x1800940ff  test    rcx, rcx
0x180094102  jz      short loc_180094182
0x180094104  call    cs:__imp_WindowsGetStringRawBuffer
0x18009410a  mov     [rbp+57h+string], rax
0x18009410e  mov     rcx, [rdi+50h]
0x180094112  xor     edx, edx; length
0x180094114  mov     rcx, [rcx+8]; string
0x180094118  call    cs:__imp_WindowsGetStringRawBuffer
0x18009411e  mov     [rbp+57h+arg_18], rax
0x180094122  lea     rax, [rbp+57h+string]
0x180094126  mov     [rsp+0D0h+var_A8], rax
0x18009412b  lea     rax, [rbp+57h+arg_0]
0x18009412f  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180094134  mov     r9, r15
0x180094137  lea     r8, [rbp+57h+arg_18]
0x18009413b  mov     rcx, r14
0x18009413e  call    ??$LaunchFileRequest@AEAY0CF@$$CBGPEBGAEAKAEAPEBGPEBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0CF@$$CBG$$QEAPEBGAEAKAEAPEBG1@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[37],ushort const *,ulong &,ushort const * &,ushort const *>(ushort const (&)[37],ushort const * &&,ulong &,ushort const * &,ushort const * &&)
0x180094143  mov     rcx, [rdi]
0x180094146  mov     rax, [rcx]
0x180094149  mov     r8, [rdi+48h]
0x18009414d  mov     r9, [rdi+28h]
0x180094151  mov     edx, [r15]
0x180094154  mov     r8, [r8+8]
0x180094158  mov     [rsp+0D0h+var_A0], r8
0x18009415d  mov     r8, [r12]
0x180094161  mov     [rsp+0D0h+var_A8], r8
0x180094166  mov     r8, [r9+8]
0x18009416a  mov     qword ptr [rsp+0D0h+var_B0], r8
0x18009416f  mov     r9, [rdi+38h]
0x180094173  mov     r8, [r13+0]
0x180094177  mov     rax, [rax+40h]
0x18009417b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094180  jmp     short loc_1800941DC
0x180094182  mov     rcx, [rdi+50h]
0x180094186  mov     rcx, [rcx+8]; string
0x18009418a  call    cs:__imp_WindowsGetStringRawBuffer
0x180094190  mov     [rbp+57h+string], rax
0x180094194  lea     rax, [rbp+57h+arg_0]
0x180094198  mov     qword ptr [rsp+0D0h+var_B0], rax
0x18009419d  mov     r9, r15
0x1800941a0  lea     r8, [rbp+57h+string]
0x1800941a4  mov     rcx, r14
0x1800941a7  call    ??$LaunchFileRequest@AEAY0BI@$$CBGPEBGAEAKAEAPEBGAEAY00$$CBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BI@$$CBG$$QEAPEBGAEAKAEAPEBGAEAY00$$CBG@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[24],ushort const *,ulong &,ushort const * &,ushort const (&)[1]>(ushort const (&)[24],ushort const * &&,ulong &,ushort const * &,ushort const (&)[1])
0x1800941ac  mov     rcx, [rdi]
0x1800941af  mov     rax, [rcx]
0x1800941b2  mov     r8, [rdi+48h]
0x1800941b6  mov     edx, [r15]
0x1800941b9  mov     r8, [r8+8]
0x1800941bd  mov     [rsp+0D0h+var_A8], r8
0x1800941c2  mov     r8, [r12]
0x1800941c6  mov     qword ptr [rsp+0D0h+var_B0], r8; int
0x1800941cb  mov     r9, [rdi+38h]
0x1800941cf  mov     r8, [r13+0]
0x1800941d3  mov     rax, [rax+30h]
0x1800941d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941dc  mov     ebx, eax
0x1800941de  mov     dword ptr [rbp+57h+arg_0], eax
0x1800941e1  test    eax, eax
0x1800941e3  js      short loc_1800941FC
0x1800941e5  mov     dword ptr [rsi+10h], 0
0x1800941ec  mov     rcx, [r13+0]; struct Windows::Storage::IStorageItem *
0x1800941f0  call    ?TryAddItemToRecent@@YAXPEAUIStorageItem@Storage@Windows@@@Z; TryAddItemToRecent(Windows::Storage::IStorageItem *)
0x1800941f5  mov     edi, ebx
0x1800941f7  jmp     loc_1800944A6
0x1800941fc  mov     rcx, [rdi+50h]
0x180094200  xor     edx, edx; length
0x180094202  mov     rcx, [rcx+8]; string
0x180094206  call    cs:__imp_WindowsGetStringRawBuffer
0x18009420c  mov     [rbp+57h+string], rax
0x180094210  lea     r9, [rbp+57h+arg_0]
0x180094214  lea     r8, [rbp+57h+string]
0x180094218  mov     rcx, r14
0x18009421b  call    ??$LaunchFileFailure@AEAY0BM@$$CBGPEBGAEAJ@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BM@$$CBG$$QEAPEBGAEAJ@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<ushort const (&)[28],ushort const *,long &>(ushort const (&)[28],ushort const * &&,long &)
0x180094220  cmp     ebx, 80040701h
0x180094226  jnz     short loc_18009427C
0x180094228  mov     dword ptr [rsi+10h], 1
0x18009422f  mov     [rbp+57h+arg_0], 0
0x180094237  mov     rax, [rdi]
0x18009423a  mov     [rbp+57h+string], rax
0x18009423e  lea     r9, [rbp+57h+string]
0x180094242  mov     r8, r12
0x180094245  mov     rdx, r15
0x180094248  lea     rcx, [rbp+57h+arg_0]
0x18009424c  call    ??$MakeAndInitialize@VStoreLauncher@Launch@Internal@System@Windows@@V12345@AEAKAEA_KPEAUILauncherService@2345@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VStoreLauncher@Launch@Internal@System@Windows@@@WRL@Microsoft@@@012@AEAKAEA_K$$QEAPEAUILauncherService@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::StoreLauncher>>,ulong &,unsigned __int64 &,Windows::System::Internal::Launch::ILauncherService * &&)
0x180094251  test    eax, eax
0x180094253  js      short loc_18009426E
0x180094255  mov     rcx, [rbp+57h+arg_0]
0x180094259  mov     rax, [rcx]
0x18009425c  mov     rdx, [rdi+28h]
0x180094260  mov     rdx, [rdx+8]
0x180094264  mov     rax, [rax+30h]
0x180094268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009426d  nop
0x18009426e  lea     rcx, [rbp+57h+arg_0]
0x180094272  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180094277  jmp     loc_1800944A2
0x18009427c  cmp     ebx, 80070005h
0x180094282  jnz     short loc_180094290
0x180094284  mov     dword ptr [rsi+10h], 2
0x18009428b  jmp     loc_1800944A2
0x180094290  cmp     ebx, 80070483h
0x180094296  jnz     loc_18009449B
0x18009429c  mov     rax, [rdi+28h]
0x1800942a0  xor     ecx, ecx
0x1800942a2  cmp     [rax+8], rcx
0x1800942a6  jz      short loc_1800942B4
0x1800942a8  mov     dword ptr [rsi+10h], 3
0x1800942af  jmp     loc_1800944A2
0x1800942b4  mov     [rbp+57h+var_88], rcx
0x1800942b8  mov     r12, [rdi+30h]
0x1800942bc  test    r12, r12
0x1800942bf  jz      loc_1800943EC
0x1800942c5  mov     [rbp+57h+arg_18], 0
0x1800942cd  mov     rax, [r12]
0x1800942d1  mov     rbx, [rax+80h]
0x1800942d8  xor     ecx, ecx; string
0x1800942da  call    cs:__imp_WindowsDeleteString
0x1800942e0  mov     [rbp+57h+arg_18], 0
0x1800942e8  lea     rdx, [rbp+57h+arg_18]
0x1800942ec  mov     rcx, r12
0x1800942ef  mov     rax, rbx
0x1800942f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800942f7  mov     ebx, eax
0x1800942f9  mov     dword ptr [rbp+57h+arg_0], eax
0x1800942fc  test    eax, eax
0x1800942fe  js      loc_1800943B8
0x180094304  xor     ecx, ecx; string
0x180094306  mov     [rbp+57h+string], rcx
0x18009430a  mov     r12, [rdi+30h]
0x18009430e  test    r12, r12
0x180094311  jz      short loc_18009433F
0x180094313  mov     rax, [r12]
0x180094317  mov     rbx, [rax+88h]
0x18009431e  call    cs:__imp_WindowsDeleteString
0x180094324  mov     [rbp+57h+string], 0
0x18009432c  lea     rdx, [rbp+57h+string]
0x180094330  mov     rcx, r12
0x180094333  mov     rax, rbx
0x180094336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009433b  mov     rcx, [rbp+57h+string]; string
0x18009433f  xor     edx, edx; length
0x180094341  call    cs:__imp_WindowsGetStringRawBuffer
0x180094347  mov     [rbp+57h+arg_0], rax
0x18009434b  mov     rcx, [rdi+50h]
0x18009434f  xor     edx, edx; length
0x180094351  mov     rcx, [rcx+8]; string
0x180094355  call    cs:__imp_WindowsGetStringRawBuffer
0x18009435b  mov     [rbp+57h+var_90], rax
0x18009435f  lea     rax, [rbp+57h+arg_0]
0x180094363  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180094368  mov     r9, r15
0x18009436b  lea     r8, [rbp+57h+var_90]
0x18009436f  mov     rcx, r14
0x180094372  call    ??$LaunchFileRequest@AEAY0BC@$$CBGPEBGAEAKPEBGAEAY00$$CBG@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BC@$$CBG$$QEAPEBGAEAK1AEAY00$$CBG@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileRequest<ushort const (&)[18],ushort const *,ulong &,ushort const *,ushort const (&)[1]>(ushort const (&)[18],ushort const * &&,ulong &,ushort const * &&,ushort const (&)[1])
0x180094377  mov     rcx, [rdi]
0x18009437a  mov     rax, [rcx]
0x18009437d  mov     r8, [rdi+48h]
0x180094381  mov     edx, [r15]
0x180094384  mov     r8, [r8+8]
0x180094388  mov     [rsp+0D0h+var_A8], r8
0x18009438d  mov     [rsp+0D0h+var_B0], 20h ; ' '
0x180094395  xor     r9d, r9d
0x180094398  mov     r8, [rbp+57h+arg_18]
0x18009439c  mov     rax, [rax+38h]
0x1800943a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800943a5  mov     ebx, eax
0x1800943a7  mov     dword ptr [rbp+57h+arg_0], eax
0x1800943aa  mov     rcx, [rbp+57h+string]; string
0x1800943ae  call    cs:__imp_WindowsDeleteString
0x1800943b4  test    ebx, ebx
0x1800943b6  jns     short loc_1800943DD
0x1800943b8  mov     rcx, [rdi+50h]
0x1800943bc  xor     edx, edx; length
0x1800943be  mov     rcx, [rcx+8]; string
0x1800943c2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800943c8  mov     [rbp+57h+string], rax
0x1800943cc  lea     r9, [rbp+57h+arg_0]
0x1800943d0  lea     r8, [rbp+57h+string]
0x1800943d4  mov     rcx, r14
0x1800943d7  call    ??$LaunchFileFailure@AEAY0BN@$$CBGPEBGAEAJ@LaunchFileAsync@LauncherClientProvider@@QEAAXAEAY0BN@$$CBG$$QEAPEBGAEAJ@Z; LauncherClientProvider::LaunchFileAsync::LaunchFileFailure<ushort const (&)[29],ushort const *,long &>(ushort const (&)[29],ushort const * &&,long &)
0x1800943dc  nop
0x1800943dd  mov     rcx, [rbp+57h+arg_18]; string
0x1800943e1  call    cs:__imp_WindowsDeleteString
0x1800943e7  jmp     loc_18009448B
0x1800943ec  mov     [rbp+57h+string], rcx
0x1800943f0  lea     rdx, [rbp+57h+string]
0x1800943f4  mov     rcx, r13
0x1800943f7  call    ??$As@UIStorageFile@Storage@Windows@@@?$ComPtr@UIStorageItem@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIStorageFile@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::IStorageItem>::As<Windows::Storage::IStorageFile>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::IStorageFile>>)
0x1800943fc  mov     ebx, eax
0x1800943fe  test    eax, eax
0x180094400  jns     short loc_180094432
0x180094402  mov     rcx, [rbp+5Fh]; this
0x180094406  mov     r9d, eax; char *
0x180094409  lea     r8, aOnecoreuapShel_26; "onecoreuap\\shell\\windows.system.launc"...
0x180094410  mov     edx, 72Dh; void *
0x180094415  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009441a  nop
0x18009441b  lea     rcx, [rbp+57h+string]
0x18009441f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180094424  nop
0x180094425  xor     ecx, ecx; string
0x180094427  call    cs:__imp_WindowsDeleteString
0x18009442d  jmp     loc_1800944B2
0x180094432  mov     [rbp+57h+arg_18], 0
0x18009443a  mov     rax, [rdi]
0x18009443d  mov     [rbp+57h+var_90], rax
0x180094441  mov     dword ptr [rbp+57h+arg_0], 0
0x180094448  lea     r9, [rbp+57h+var_90]
0x18009444c  lea     r8, [rbp+57h+arg_0]
0x180094450  mov     rdx, r15
0x180094453  lea     rcx, [rbp+57h+arg_18]
0x180094457  call    ??$MakeAndInitialize@VStoreLauncher@Launch@Internal@System@Windows@@V12345@AEAKHPEAUILauncherService@2345@@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VStoreLauncher@Launch@Internal@System@Windows@@@WRL@Microsoft@@@012@AEAK$$QEAH$$QEAPEAUILauncherService@Launch@Internal@System@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::System::Internal::Launch::StoreLauncher,Windows::System::Internal::Launch::StoreLauncher,ulong &,int,Windows::System::Internal::Launch::ILauncherService *>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::System::Internal::Launch::StoreLauncher>>,ulong &,int &&,Windows::System::Internal::Launch::ILauncherService * &&)
0x18009445c  mov     ebx, eax
0x18009445e  test    eax, eax
0x180094460  js      short loc_180094478
0x180094462  mov     rcx, [rbp+57h+arg_18]
0x180094466  mov     rax, [rcx]
0x180094469  mov     rdx, [rbp+57h+string]
0x18009446d  mov     rax, [rax+40h]
0x180094471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094476  mov     ebx, eax
0x180094478  lea     rcx, [rbp+57h+arg_18]
0x18009447c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180094481  nop
0x180094482  lea     rcx, [rbp+57h+string]
0x180094486  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18009448b  shr     ebx, 1Fh
0x18009448e  mov     [rsi+10h], ebx
0x180094491  xor     ecx, ecx; string
0x180094493  call    cs:__imp_WindowsDeleteString
0x180094499  jmp     short loc_1800944A2
0x18009449b  mov     dword ptr [rsi+10h], 4
0x1800944a2  xor     ebx, ebx
0x1800944a4  xor     edi, edi
0x1800944a6  mov     edx, ebx
0x1800944a8  mov     rcx, r14
0x1800944ab  call    ?Stop@?$ActivityBase@VLauncherClientProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LauncherClientProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800944b0  mov     ebx, edi
0x1800944b2  lea     rcx, [rbp+57h+var_80]; this
0x1800944b6  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x1800944bb  mov     eax, ebx
0x1800944bd  mov     rbx, [rsp+0D0h+arg_8]
0x1800944c5  add     rsp, 0A0h
0x1800944cc  pop     r15
0x1800944ce  pop     r14
0x1800944d0  pop     r13
0x1800944d2  pop     r12
0x1800944d4  pop     rdi
0x1800944d5  pop     rsi
0x1800944d6  pop     rbp
0x1800944d7  retn
```
