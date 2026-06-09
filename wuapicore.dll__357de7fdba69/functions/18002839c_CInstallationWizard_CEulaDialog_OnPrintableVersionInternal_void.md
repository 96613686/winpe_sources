# CInstallationWizard::CEulaDialog::OnPrintableVersionInternal(void)

- ea: `0x18002839c`
- end: `0x1800287af`
- name: `?OnPrintableVersionInternal@CEulaDialog@CInstallationWizard@@AEAAJXZ`
- size: `1043`
- prototype: `__int64 __fastcall(CInstallationWizard::CEulaDialog *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800280f0`

## callees

- `0x1800054bc`
- `0x18000588c`
- `0x180006ac4`
- `0x18000725c`
- `0x180007d34`
- `0x18001b9cc`
- `0x18001bc98`
- `0x18002839c`
- `0x180030604`
- `0x18004124c`
- `0x1800413c8`
- `0x180041808`
- `0x180041b28`
- `0x180081a38`
- `0x180081adc`
- `0x18009ae75`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028769`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028459`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028769`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800286fb`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800286fb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002873a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002873a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028748`

## string_xrefs

- `0x1800285f5`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`
- `0x18002866a`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`
- `0x1800286b8`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`
- `0x18002870c`: `C:\__w\1\s\src\Client\comapi\installationwizard.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=59
__int64 __fastcall CInstallationWizard::CEulaDialog::OnPrintableVersionInternal(CInstallationWizard::CEulaDialog *this)
{
  wchar_t *v2; // rdi
  signed int LastError; // esi
  __int64 v4; // rdx
  __int64 v5; // r13
  unsigned int v6; // r12d
  int v7; // r15d
  int InnerSusInternal; // eax
  struct ISusInternal *v9; // rbx
  struct ISusInternal *v10; // r14
  __int64 v11; // rax
  bool v12; // zf
  unsigned int v13; // eax
  unsigned __int64 v14; // rbx
  int v15; // eax
  int v16; // eax
  const char *v17; // r9
  HANDLE hThread; // rbx
  void *v19; // rcx
  int bInheritHandles; // [rsp+28h] [rbp-E0h]
  int bInheritHandlesa; // [rsp+28h] [rbp-E0h]
  int bInheritHandlesb; // [rsp+28h] [rbp-E0h]
  struct ISusInternal *v24; // [rsp+58h] [rbp-B0h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+78h] [rbp-90h]
  LPVOID pv; // [rsp+80h] [rbp-88h] BYREF
  _BYTE v28[192]; // [rsp+88h] [rbp-80h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+148h] [rbp+40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F0h] [rbp+E8h]

  memset_0(v28, 0, 0xB8u);
  CSusInternalWrapper::CSusInternalWrapper((CSusInternalWrapper *)v28);
  pv = 0;
  v2 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v26 = 0;
  LastError = CSusInternalWrapper::Initialize((CSusInternalWrapper *)v28);
  if ( LastError < 0 )
  {
    v4 = 573;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)(unsigned int)LastError,
      bInheritHandles);
    goto LABEL_43;
  }
  v5 = **((_QWORD **)this + 11) + 88LL * *(int *)(*((_QWORD *)this + 12) + 4LL * *((int *)this + 30));
  v6 = *((_DWORD *)this + 34);
  v7 = 4;
  while ( 1 )
  {
    while ( 1 )
    {
      --v7;
      v24 = 0;
      InnerSusInternal = CSusInternalWrapper::GetInnerSusInternal((CSusInternalWrapper *)v28, &v24, 1, 1);
      LastError = InnerSusInternal;
      if ( InnerSusInternal != -2147023838 )
        break;
      LastError = ReenableWUService(0);
      if ( LastError < 0 )
        goto LABEL_28;
      if ( v24 )
        (*(void (**)(void))(*(_QWORD *)v24 + 16LL))();
    }
    if ( InnerSusInternal < 0 || v7 < 0 )
    {
LABEL_28:
      if ( v24 )
        (*(void (__fastcall **)(struct ISusInternal *))(*(_QWORD *)v24 + 16LL))(v24);
      if ( LastError >= 0 )
        goto LABEL_22;
LABEL_31:
      v4 = 580;
      goto LABEL_27;
    }
    v9 = v24;
    v10 = v24;
    LastError = (*(__int64 (__fastcall **)(struct ISusInternal *, __int64, _QWORD, LPVOID *))(*(_QWORD *)v24 + 56LL))(
                  v24,
                  v5 + 28,
                  v6,
                  &pv);
    if ( v9 )
    {
      v9 = 0;
      v24 = 0;
      (*(void (__fastcall **)(struct ISusInternal *))(*(_QWORD *)v10 + 16LL))(v10);
      v10 = 0;
    }
    if ( LastError >= 0 )
      break;
    if ( LastError != -2145124325 && LastError != -2145124322 && LastError != -2147220995 && LastError != -2147417848 )
    {
      TraceSelfUpdateLoopFailure1_0("GetEulaFile", (unsigned int)LastError);
      goto LABEL_31;
    }
    TraceSelfUpdateRetry("GetEulaFile", (unsigned int)LastError);
  }
  if ( v10 )
    (*(void (__fastcall **)(struct ISusInternal *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_22:
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  v12 = (_DWORD)v11 == -15;
  v13 = v11 + 15;
  v14 = v13;
  if ( !v12 )
  {
    v2 = (wchar_t *)SafeSusAllocArray(v13, 2u);
    LastError = v2 == 0 ? 0x8007000E : 0;
    if ( !v2 )
    {
      v4 = 585;
      goto LABEL_27;
    }
  }
  ProcessInformation.hProcess = 0;
  v24 = 0;
  v15 = StringCchCatExW(v2, v14, L"notepad.exe", (wchar_t **)&ProcessInformation, (unsigned __int64 *)&v24, 0x100u);
  if ( v15 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)(unsigned int)v15,
      bInheritHandlesa);
  v16 = StringCchPrintfExW((wchar_t *)ProcessInformation.hProcess, (unsigned __int64)v24, 0, 0, 0x100u, L" \"%s\"", pv);
  if ( v16 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x25C,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
      (const char *)(unsigned int)v16,
      bInheritHandlesb);
  if ( CreateProcessW(0, v2, 0, 0, 0, 0, 0, 0, &StartupInfo, (LPPROCESS_INFORMATION)&ProcessInformation.hThread) )
  {
    hThread = ProcessInformation.hThread;
    ProcessInformation.hThread = 0;
    v19 = *(void **)&ProcessInformation.dwProcessId;
    *(_QWORD *)&ProcessInformation.dwProcessId = 0;
    if ( v19 )
      CloseHandle(v19);
    if ( hThread )
      CloseHandle(hThread);
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x25E,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\installationwizard.cpp",
                  v17);
  }
LABEL_43:
  if ( v2 )
    SusFree(v2);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  CSusInternalWrapper::~CSusInternalWrapper((CSusInternalWrapper *)v28);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18002839c  mov     rax, rsp
0x18002839f  mov     [rax+10h], rbx
0x1800283a3  mov     [rax+18h], rsi
0x1800283a7  mov     [rax+20h], rdi
0x1800283ab  push    rbp
0x1800283ac  push    r12
0x1800283ae  push    r13
0x1800283b0  push    r14
0x1800283b2  push    r15
0x1800283b4  lea     rbp, [rax-0E8h]
0x1800283bb  sub     rsp, 1C0h
0x1800283c2  mov     rax, cs:__security_cookie
0x1800283c9  xor     rax, rsp
0x1800283cc  mov     [rbp+0E0h+var_30], rax
0x1800283d3  mov     rbx, rcx
0x1800283d6  xor     edx, edx; Val
0x1800283d8  mov     r8d, 0B8h; Size
0x1800283de  lea     rcx, [rbp+0E0h+var_160]; void *
0x1800283e2  call    memset_0
0x1800283e7  lea     rcx, [rbp+0E0h+var_160]; this
0x1800283eb  call    ??0CSusInternalWrapper@@QEAA@XZ; CSusInternalWrapper::CSusInternalWrapper(void)
0x1800283f0  nop
0x1800283f1  xor     r14d, r14d
0x1800283f4  mov     [rsp+1E0h+pv], r14
0x1800283f9  mov     edi, r14d
0x1800283fc  mov     [rsp+1E0h+ProcessInformation.hProcess], r14
0x180028401  xor     edx, edx; Val
0x180028403  lea     r8d, [r14+68h]; Size
0x180028407  lea     rcx, [rbp+0E0h+StartupInfo]; void *
0x18002840b  call    memset_0
0x180028410  xorps   xmm0, xmm0
0x180028413  xor     eax, eax
0x180028415  movups  xmmword ptr [rsp+1E0h+ProcessInformation.hThread], xmm0
0x18002841a  mov     [rsp+1E0h+var_170], rax
0x18002841f  lea     rcx, [rbp+0E0h+var_160]; this
0x180028423  call    ?Initialize@CSusInternalWrapper@@QEAAJXZ; CSusInternalWrapper::Initialize(void)
0x180028428  mov     esi, eax
0x18002842a  test    eax, eax
0x18002842c  jns     short loc_180028438
0x18002842e  mov     edx, 23Dh
0x180028433  jmp     loc_1800285EB
0x180028438  movsxd  rcx, dword ptr [rbx+78h]
0x18002843c  mov     rax, [rbx+60h]
0x180028440  movsxd  rcx, dword ptr [rax+rcx*4]
0x180028444  imul    r13, rcx, 58h ; 'X'
0x180028448  mov     rax, [rbx+58h]
0x18002844c  add     r13, [rax]
0x18002844f  mov     rcx, [rsp+1E0h+pv]; pv
0x180028454  test    rcx, rcx
0x180028457  jz      short loc_180028464
0x180028459  call    cs:__imp_CoTaskMemFree
0x18002845f  mov     [rsp+1E0h+pv], r14
0x180028464  mov     r12d, [rbx+88h]
0x18002846b  mov     r15d, 4
0x180028471  dec     r15d
0x180028474  mov     [rsp+1E0h+var_190], r14
0x180028479  mov     r9d, 1; int
0x18002847f  mov     r8d, r9d; int
0x180028482  lea     rdx, [rsp+1E0h+var_190]; struct ISusInternal **
0x180028487  lea     rcx, [rbp+0E0h+var_160]; this
0x18002848b  call    ?GetInnerSusInternal@CSusInternalWrapper@@AEAAJPEAPEAUISusInternal@@HH@Z; CSusInternalWrapper::GetInnerSusInternal(ISusInternal * *,int,int)
0x180028490  mov     esi, eax
0x180028492  cmp     eax, 80070422h
0x180028497  jnz     short loc_1800284C0
0x180028499  xor     ecx, ecx
0x18002849b  call    ReenableWUService
0x1800284a0  mov     esi, eax
0x1800284a2  test    eax, eax
0x1800284a4  js      loc_180028606
0x1800284aa  mov     rcx, [rsp+1E0h+var_190]
0x1800284af  test    rcx, rcx
0x1800284b2  jz      loc_18002855F
0x1800284b8  mov     rax, [rcx]
0x1800284bb  jmp     loc_180028555
0x1800284c0  test    eax, eax
0x1800284c2  js      loc_180028606
0x1800284c8  test    r15d, r15d
0x1800284cb  js      loc_180028606
0x1800284d1  mov     rbx, [rsp+1E0h+var_190]
0x1800284d6  mov     r14, rbx
0x1800284d9  mov     rax, [rbx]
0x1800284dc  lea     r9, [rsp+1E0h+pv]
0x1800284e1  mov     r8d, r12d
0x1800284e4  lea     rdx, [r13+1Ch]
0x1800284e8  mov     rcx, rbx
0x1800284eb  mov     rax, [rax+38h]
0x1800284ef  call    _guard_dispatch_icall
0x1800284f4  mov     esi, eax
0x1800284f6  test    rbx, rbx
0x1800284f9  jz      short loc_180028514
0x1800284fb  xor     ebx, ebx
0x1800284fd  mov     [rsp+1E0h+var_190], rbx
0x180028502  mov     rax, [r14]
0x180028505  mov     rcx, r14
0x180028508  mov     rax, [rax+10h]
0x18002850c  call    _guard_dispatch_icall
0x180028511  xor     r14d, r14d
0x180028514  test    esi, esi
0x180028516  jns     short loc_180028590
0x180028518  cmp     esi, 8024001Bh
0x18002851e  jz      short loc_180028538
0x180028520  cmp     esi, 8024001Eh
0x180028526  jz      short loc_180028538
0x180028528  cmp     esi, 800401FDh
0x18002852e  jz      short loc_180028538
0x180028530  cmp     esi, 80010108h
0x180028536  jnz     short loc_180028564
0x180028538  mov     edx, esi
0x18002853a  lea     rcx, aGeteulafile; "GetEulaFile"
0x180028541  call    TraceSelfUpdateRetry
0x180028546  nop
0x180028547  xor     r14d, r14d
0x18002854a  test    rbx, rbx
0x18002854d  jz      short loc_18002855F
0x18002854f  mov     rax, [rbx]
0x180028552  mov     rcx, rbx
0x180028555  mov     rax, [rax+10h]
0x180028559  call    _guard_dispatch_icall
0x18002855e  nop
0x18002855f  jmp     loc_180028471
0x180028564  mov     edx, esi
0x180028566  lea     rcx, aGeteulafile; "GetEulaFile"
0x18002856d  call    TraceSelfUpdateLoopFailure1_0
0x180028572  nop
0x180028573  xor     r14d, r14d
0x180028576  test    rbx, rbx
0x180028579  jz      short loc_18002858B
0x18002857b  mov     rax, [rbx]
0x18002857e  mov     rcx, rbx
0x180028581  mov     rax, [rax+10h]
0x180028585  call    _guard_dispatch_icall
0x18002858a  nop
0x18002858b  jmp     loc_180028621
0x180028590  test    r14, r14
0x180028593  jz      short loc_1800285A5
0x180028595  mov     rax, [rbx]
0x180028598  mov     rcx, rbx
0x18002859b  mov     rax, [rax+10h]
0x18002859f  call    _guard_dispatch_icall
0x1800285a4  nop
0x1800285a5  xor     r14d, r14d
0x1800285a8  mov     rcx, [rsp+1E0h+pv]
0x1800285ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800285b1  inc     rax
0x1800285b4  cmp     [rcx+rax*2], r14w
0x1800285b9  jnz     short loc_1800285B1
0x1800285bb  add     eax, 0Fh
0x1800285be  mov     ebx, eax
0x1800285c0  jz      short loc_180028628
0x1800285c2  mov     edx, 2; unsigned __int64
0x1800285c7  mov     ecx, ebx; unsigned __int64
0x1800285c9  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x1800285ce  mov     rdi, rax
0x1800285d1  mov     rcx, rax
0x1800285d4  neg     rcx
0x1800285d7  sbb     esi, esi
0x1800285d9  not     esi
0x1800285db  and     esi, 8007000Eh
0x1800285e1  test    rax, rax
0x1800285e4  jnz     short loc_180028628
0x1800285e6  mov     edx, 249h; void *
0x1800285eb  mov     rcx, [rbp+0E8h]; this
0x1800285f2  mov     r9d, esi; char *
0x1800285f5  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x1800285fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028601  jmp     loc_180028751
0x180028606  mov     rcx, [rsp+1E0h+var_190]
0x18002860b  test    rcx, rcx
0x18002860e  jz      short loc_18002861D
0x180028610  mov     rax, [rcx]
0x180028613  mov     rax, [rax+10h]
0x180028617  call    _guard_dispatch_icall
0x18002861c  nop
0x18002861d  test    esi, esi
0x18002861f  jns     short loc_1800285A8
0x180028621  mov     edx, 244h
0x180028626  jmp     short loc_1800285EB
0x180028628  mov     [rsp+1E0h+ProcessInformation.hProcess], r14
0x18002862d  mov     [rsp+1E0h+var_190], r14
0x180028632  mov     esi, 100h
0x180028637  mov     [rsp+1E0h+dwCreationFlags], esi; unsigned int
0x18002863b  lea     rax, [rsp+1E0h+var_190]
0x180028640  mov     qword ptr [rsp+1E0h+bInheritHandles], rax; int
0x180028645  lea     r9, [rsp+1E0h+ProcessInformation]; wchar_t **
0x18002864a  lea     r8, aNotepadExe; "notepad.exe"
0x180028651  mov     rdx, rbx; unsigned __int64
0x180028654  mov     rcx, rdi; pszDest
0x180028657  call    ?StringCchCatExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCatExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18002865c  mov     rcx, [rbp+0E8h]; this
0x180028663  test    eax, eax
0x180028665  jns     short loc_18002867B
0x180028667  mov     r9d, eax; char *
0x18002866a  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x180028671  mov     edx, 254h; void *
0x180028676  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002867b  mov     rax, [rsp+1E0h+pv]
0x180028680  mov     [rsp+1E0h+lpEnvironment], rax
0x180028685  lea     rax, aS_0; " \"%s\""
0x18002868c  mov     qword ptr [rsp+1E0h+dwCreationFlags], rax; wchar_t *
0x180028691  mov     [rsp+1E0h+bInheritHandles], esi; int
0x180028695  xor     r9d, r9d; unsigned __int64 *
0x180028698  xor     r8d, r8d; wchar_t **
0x18002869b  mov     rdx, [rsp+1E0h+var_190]; unsigned __int64
0x1800286a0  mov     rcx, [rsp+1E0h+ProcessInformation.hProcess]; Buffer
0x1800286a5  call    ?StringCchPrintfExW@@YAJPEA_W_KPEAPEA_WPEA_KKPEB_WZZ; StringCchPrintfExW(wchar_t *,unsigned __int64,wchar_t * *,unsigned __int64 *,ulong,wchar_t const *,...)
0x1800286aa  mov     rcx, [rbp+0E8h]; this
0x1800286b1  test    eax, eax
0x1800286b3  jns     short loc_1800286C9
0x1800286b5  mov     r9d, eax; char *
0x1800286b8  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x1800286bf  mov     edx, 25Ch; void *
0x1800286c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800286c9  lea     rax, [rsp+1E0h+ProcessInformation.hThread]
0x1800286ce  mov     [rsp+1E0h+lpProcessInformation], rax; lpProcessInformation
0x1800286d3  lea     rax, [rbp+0E0h+StartupInfo]
0x1800286d7  mov     [rsp+1E0h+lpStartupInfo], rax; lpStartupInfo
0x1800286dc  mov     [rsp+1E0h+lpCurrentDirectory], r14; lpCurrentDirectory
0x1800286e1  mov     [rsp+1E0h+lpEnvironment], r14; lpEnvironment
0x1800286e6  mov     [rsp+1E0h+dwCreationFlags], r14d; dwCreationFlags
0x1800286eb  mov     [rsp+1E0h+bInheritHandles], r14d; bInheritHandles
0x1800286f0  xor     r9d, r9d; lpThreadAttributes
0x1800286f3  xor     r8d, r8d; lpProcessAttributes
0x1800286f6  mov     rdx, rdi; lpCommandLine
0x1800286f9  xor     ecx, ecx; lpApplicationName
0x1800286fb  call    cs:__imp_CreateProcessW
0x180028701  test    eax, eax
0x180028703  jnz     short loc_180028721
0x180028705  mov     rcx, [rbp+0E8h]; this
0x18002870c  lea     r8, aCW1SSrcClientC_48; "C:\\__w\\1\\s\\src\\Client\\comapi\\ins"...
0x180028713  mov     edx, 25Eh; void *
0x180028718  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002871d  mov     esi, eax
0x18002871f  jmp     short loc_180028751
0x180028721  mov     rbx, [rsp+1E0h+ProcessInformation.hThread]
0x180028726  mov     [rsp+1E0h+ProcessInformation.hThread], r14
0x18002872b  mov     rcx, qword ptr [rsp+1E0h+ProcessInformation.dwProcessId]; hObject
0x180028730  mov     qword ptr [rsp+1E0h+ProcessInformation.dwProcessId], r14
0x180028735  test    rcx, rcx
0x180028738  jz      short loc_180028740
0x18002873a  call    cs:__imp_CloseHandle
0x180028740  test    rbx, rbx
0x180028743  jz      short loc_18002874E
0x180028745  mov     rcx, rbx; hObject
0x180028748  call    cs:__imp_CloseHandle
0x18002874e  mov     esi, r14d
0x180028751  test    rdi, rdi
0x180028754  jz      short loc_18002875F
0x180028756  mov     rcx, rdi; lpMem
0x180028759  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18002875e  nop
0x18002875f  mov     rcx, [rsp+1E0h+pv]; pv
0x180028764  test    rcx, rcx
0x180028767  jz      short loc_180028774
0x180028769  call    cs:__imp_CoTaskMemFree
0x18002876f  mov     [rsp+1E0h+pv], r14
0x180028774  lea     rcx, [rbp+0E0h+var_160]; this
0x180028778  call    ??1CSusInternalWrapper@@UEAA@XZ; CSusInternalWrapper::~CSusInternalWrapper(void)
0x18002877d  mov     eax, esi
0x18002877f  mov     rcx, [rbp+0E0h+var_30]
0x180028786  xor     rcx, rsp; StackCookie
0x180028789  call    __security_check_cookie
0x18002878e  lea     r11, [rsp+1E0h+var_20]
0x180028796  mov     rbx, [r11+38h]
0x18002879a  mov     rsi, [r11+40h]
0x18002879e  mov     rdi, [r11+48h]
0x1800287a2  mov     rsp, r11
0x1800287a5  pop     r15
0x1800287a7  pop     r14
0x1800287a9  pop     r13
0x1800287ab  pop     r12
0x1800287ad  pop     rbp
0x1800287ae  retn
```
