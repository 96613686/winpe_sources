# NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)

- ea: `0x1400235dc`
- end: `0x140023807`
- name: `?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z`
- size: `555`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400038f0`
- `0x140004e90`
- `0x140005c30`
- `0x14000c0e0`

## callees

- `0x140017ae0`
- `0x140017e74`
- `0x140017ef8`
- `0x1400235dc`
- `0x140023810`
- `0x14002abc0`
- `0x14002b810`
- `0x14007093c`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400236da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400237a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023686`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400236da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400237a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140023787`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140023787`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140023631`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002367c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140023631`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002367c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002361d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023668`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14002361d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140023668`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023655`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140023655`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400236d0`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400236d0`
- `KERNELBASE!GetIsEdpEnabled` at `0x14002370c`
- `KERNELBASE!GetIsEdpEnabled` at `0x14002370c`
- `ADVAPI32!IsWellKnownSid` at `0x140023700`
- `ADVAPI32!IsWellKnownSid` at `0x140023700`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400237d2`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400237d2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002371e`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002371e`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(NSecurityLibrary *this, void **a2, int *a3)
{
  signed int PrintScanBroker; // ebx
  HANDLE CurrentThread; // rax
  HANDLE v7; // rdi
  HANDLE v8; // rax
  signed int LastError; // eax
  signed int v10; // eax
  BOOL v11; // eax
  HRESULT v12; // edi
  signed int v13; // eax
  HANDLE TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-51h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-49h] BYREF
  __int64 v18; // [rsp+48h] [rbp-41h] BYREF
  HANDLE v19[2]; // [rsp+50h] [rbp-39h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-29h] BYREF

  *(_QWORD *)this = 0;
  PrintScanBroker = 0;
  TokenHandle = 0;
  *(_DWORD *)a2 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    v7 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Token);
      CloseHandle(v7);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Token);
    }
    TokenHandle = 0;
    v8 = GetCurrentThread();
    if ( !OpenThreadToken(v8, 0xEu, 0, &TokenHandle) )
    {
      LastError = GetLastError();
      PrintScanBroker = LastError;
      if ( LastError > 0 )
        PrintScanBroker = (unsigned __int16)LastError | 0x80070000;
    }
  }
  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 88;
  if ( PrintScanBroker >= 0 )
  {
    if ( GetTokenInformation(TokenHandle, TokenIntegrityLevel, TokenInformation, 0x58u, &ReturnLength) )
      goto LABEL_12;
    v10 = GetLastError();
    PrintScanBroker = v10;
    if ( v10 > 0 )
      PrintScanBroker = (unsigned __int16)v10 | 0x80070000;
    if ( PrintScanBroker >= 0 )
    {
LABEL_12:
      v11 = IsWellKnownSid(TokenInformation[0], WinLowLabelSid);
      *(_DWORD *)a2 = v11;
      if ( v11 || (unsigned int)GetIsEdpEnabled() )
      {
        v12 = CoInitializeEx(0, 0);
        if ( (int)(v12 + 0x80000000) < 0 || v12 == -2147417850 )
        {
          v18 = 0;
          PrintScanBroker = NSecurityLibrary::GetPrintScanBroker(&v18);
          if ( PrintScanBroker >= 0 )
          {
            Token = 0;
            PrintScanBroker = (*(__int64 (__fastcall **)(__int64, HANDLE, HANDLE *))(*(_QWORD *)v18 + 72LL))(
                                v18,
                                TokenHandle,
                                &Token);
            if ( PrintScanBroker >= 0 )
            {
              v19[0] = Token;
              if ( SetThreadToken(0, Token) )
              {
                *(_QWORD *)this = TokenHandle;
                TokenHandle = 0;
              }
              else
              {
                v13 = GetLastError();
                PrintScanBroker = v13;
                if ( v13 > 0 )
                  PrintScanBroker = (unsigned __int16)v13 | 0x80070000;
              }
              wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v19);
            }
          }
          sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v18);
          if ( v12 >= 0 )
            CoUninitialize();
        }
        else
        {
          PrintScanBroker = v12;
        }
      }
    }
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)PrintScanBroker;
}

```

## disassembly

```asm
0x1400235dc  mov     [rsp-8+arg_10], rbx
0x1400235e1  mov     [rsp-8+arg_18], rsi
0x1400235e6  push    rbp
0x1400235e7  push    rdi
0x1400235e8  push    r14
0x1400235ea  lea     rbp, [rsp-47h]
0x1400235ef  sub     rsp, 0D0h
0x1400235f6  mov     rax, cs:__security_cookie
0x1400235fd  xor     rax, rsp
0x140023600  mov     [rbp+57h+var_20], rax
0x140023604  mov     qword ptr [rcx], 0
0x14002360b  xor     ebx, ebx
0x14002360d  mov     [rbp+57h+TokenHandle], rbx
0x140023611  mov     rsi, rdx
0x140023614  mov     r14, rcx
0x140023617  mov     dword ptr [rdx], 0
0x14002361d  call    cs:__imp_GetCurrentThread
0x140023623  mov     rcx, rax; ThreadHandle
0x140023626  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x14002362a  lea     edx, [rbx+0Eh]; DesiredAccess
0x14002362d  lea     r8d, [rbx+1]; OpenAsSelf
0x140023631  call    cs:__imp_OpenThreadToken
0x140023637  test    eax, eax
0x140023639  jnz     short loc_14002369B
0x14002363b  mov     rdi, [rbp+57h+TokenHandle]
0x14002363f  lea     rax, [rdi-1]
0x140023643  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140023647  ja      short loc_140023664
0x140023649  lea     rcx, [rbp+57h+Token]; this
0x14002364d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140023652  mov     rcx, rdi; hObject
0x140023655  call    cs:__imp_CloseHandle
0x14002365b  lea     rcx, [rbp+57h+Token]; this
0x14002365f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140023664  mov     [rbp+57h+TokenHandle], rbx
0x140023668  call    cs:__imp_GetCurrentThread
0x14002366e  xor     r8d, r8d; OpenAsSelf
0x140023671  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140023675  mov     rcx, rax; ThreadHandle
0x140023678  lea     edx, [r8+0Eh]; DesiredAccess
0x14002367c  call    cs:__imp_OpenThreadToken
0x140023682  test    eax, eax
0x140023684  jnz     short loc_14002369B
0x140023686  call    cs:__imp_GetLastError
0x14002368c  mov     ebx, eax
0x14002368e  test    eax, eax
0x140023690  jle     short loc_14002369B
0x140023692  movzx   ebx, ax
0x140023695  or      ebx, 80070000h
0x14002369b  mov     edi, 58h ; 'X'
0x1400236a0  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1400236a4  mov     r8d, edi; Size
0x1400236a7  xor     edx, edx; Val
0x1400236a9  call    memset_0
0x1400236ae  mov     [rbp+57h+var_A0], edi
0x1400236b1  test    ebx, ebx
0x1400236b3  js      loc_1400237D8
0x1400236b9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1400236bd  lea     rax, [rbp+57h+var_A0]
0x1400236c1  mov     r9d, edi; TokenInformationLength
0x1400236c4  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x1400236c9  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400236cd  lea     edx, [rdi-3Fh]; TokenInformationClass
0x1400236d0  call    cs:__imp_GetTokenInformation
0x1400236d6  test    eax, eax
0x1400236d8  jnz     short loc_1400236F7
0x1400236da  call    cs:__imp_GetLastError
0x1400236e0  mov     ebx, eax
0x1400236e2  test    eax, eax
0x1400236e4  jle     short loc_1400236EF
0x1400236e6  movzx   ebx, ax
0x1400236e9  or      ebx, 80070000h
0x1400236ef  test    ebx, ebx
0x1400236f1  js      loc_1400237D8
0x1400236f7  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x1400236fb  mov     edx, 42h ; 'B'; WellKnownSidType
0x140023700  call    cs:__imp_IsWellKnownSid
0x140023706  mov     [rsi], eax
0x140023708  test    eax, eax
0x14002370a  jnz     short loc_14002371A
0x14002370c  call    cs:__imp_GetIsEdpEnabled
0x140023712  test    eax, eax
0x140023714  jz      loc_1400237D8
0x14002371a  xor     edx, edx; dwCoInit
0x14002371c  xor     ecx, ecx; pvReserved
0x14002371e  call    cs:__imp_CoInitializeEx
0x140023724  mov     ecx, 80000000h
0x140023729  mov     edi, eax
0x14002372b  add     eax, ecx
0x14002372d  test    ecx, eax
0x14002372f  jnz     short loc_140023740
0x140023731  cmp     edi, 80010106h
0x140023737  jz      short loc_140023740
0x140023739  mov     ebx, edi
0x14002373b  jmp     loc_1400237D8
0x140023740  lea     rcx, [rbp+57h+var_98]
0x140023744  mov     [rbp+57h+var_98], 0
0x14002374c  call    ?GetPrintScanBroker@NSecurityLibrary@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; NSecurityLibrary::GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x140023751  mov     ebx, eax
0x140023753  test    eax, eax
0x140023755  js      short loc_1400237C0
0x140023757  mov     rcx, [rbp+57h+var_98]
0x14002375b  lea     r8, [rbp+57h+Token]
0x14002375f  mov     rdx, [rbp+57h+TokenHandle]
0x140023763  mov     [rbp+57h+Token], 0
0x14002376b  mov     rax, [rcx]
0x14002376e  mov     rax, [rax+48h]
0x140023772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140023777  mov     ebx, eax
0x140023779  test    eax, eax
0x14002377b  js      short loc_1400237C0
0x14002377d  mov     rdx, [rbp+57h+Token]; Token
0x140023781  xor     ecx, ecx; Thread
0x140023783  mov     [rbp+57h+var_90], rdx
0x140023787  call    cs:__imp_SetThreadToken
0x14002378d  test    eax, eax
0x14002378f  jz      short loc_1400237A2
0x140023791  mov     rax, [rbp+57h+TokenHandle]
0x140023795  mov     [r14], rax
0x140023798  mov     [rbp+57h+TokenHandle], 0
0x1400237a0  jmp     short loc_1400237B7
0x1400237a2  call    cs:__imp_GetLastError
0x1400237a8  mov     ebx, eax
0x1400237aa  test    eax, eax
0x1400237ac  jle     short loc_1400237B7
0x1400237ae  movzx   ebx, ax
0x1400237b1  or      ebx, 80070000h
0x1400237b7  lea     rcx, [rbp+57h+var_90]
0x1400237bb  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400237c0  lea     rcx, [rbp+57h+var_98]; this
0x1400237c4  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400237c9  shr     edi, 1Fh
0x1400237cc  xor     dil, 1
0x1400237d0  jz      short loc_1400237D8
0x1400237d2  call    cs:__imp_CoUninitialize
0x1400237d8  lea     rcx, [rbp+57h+TokenHandle]
0x1400237dc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400237e1  mov     eax, ebx
0x1400237e3  mov     rcx, [rbp+57h+var_20]
0x1400237e7  xor     rcx, rsp; StackCookie
0x1400237ea  call    __security_check_cookie
0x1400237ef  lea     r11, [rsp+0E0h+var_10]
0x1400237f7  mov     rbx, [r11+30h]
0x1400237fb  mov     rsi, [r11+38h]
0x1400237ff  mov     rsp, r11
0x140023802  pop     r14
0x140023804  pop     rdi
0x140023805  pop     rbp
0x140023806  retn
```
