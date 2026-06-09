# NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(void * *,int *)

- ea: `0x140025504`
- end: `0x140025784`
- name: `?ElevateIntegrityLevelIfLowViaBroker@NSecurityLibrary@@YAJPEAPEAXPEAH@Z`
- size: `640`
- prototype: `__int64 __fastcall(NSecurityLibrary *__hidden this, void **, int *)`
- caller_count: `4`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400043e0`
- `0x140005630`
- `0x1400065e0`
- `0x14000cfe0`

## callees

- `0x140018f84`
- `0x140019380`
- `0x140019410`
- `0x140025504`
- `0x14002578c`
- `0x14002d0a0`
- `0x14002dd20`
- `0x140077880`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400255cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002562c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025712`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400255cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002562c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140025712`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400256f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1400256f1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002555f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400255bc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14002555f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1400255bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140025545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400255a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140025545`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400255a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025589`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140025589`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002561c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002561c`
- `KERNELBASE!GetIsEdpEnabled` at `0x14002566a`
- `KERNELBASE!GetIsEdpEnabled` at `0x14002566a`
- `ADVAPI32!IsWellKnownSid` at `0x140025658`
- `ADVAPI32!IsWellKnownSid` at `0x140025658`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140025748`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140025748`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140025682`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140025682`

## pseudocode

```c
__int64 __fastcall NSecurityLibrary::ElevateIntegrityLevelIfLowViaBroker(NSecurityLibrary *this, void **a2, int *a3)
{
  int PrintScanBroker; // ebx
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
0x140025504  mov     [rsp-8+arg_10], rbx
0x140025509  mov     [rsp-8+arg_18], rsi
0x14002550e  push    rbp
0x14002550f  push    rdi
0x140025510  push    r14
0x140025512  lea     rbp, [rsp-47h]
0x140025517  sub     rsp, 0D0h
0x14002551e  mov     rax, cs:__security_cookie
0x140025525  xor     rax, rsp
0x140025528  mov     [rbp+57h+var_20], rax
0x14002552c  mov     qword ptr [rcx], 0
0x140025533  xor     ebx, ebx
0x140025535  mov     [rbp+57h+TokenHandle], rbx
0x140025539  mov     rsi, rdx
0x14002553c  mov     r14, rcx
0x14002553f  mov     dword ptr [rdx], 0
0x140025545  call    cs:__imp_GetCurrentThread
0x14002554c  nop     dword ptr [rax+rax+00h]
0x140025551  mov     rcx, rax; ThreadHandle
0x140025554  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x140025558  lea     edx, [rbx+0Eh]; DesiredAccess
0x14002555b  lea     r8d, [rbx+1]; OpenAsSelf
0x14002555f  call    cs:__imp_OpenThreadToken
0x140025566  nop     dword ptr [rax+rax+00h]
0x14002556b  test    eax, eax
0x14002556d  jnz     short loc_1400255E7
0x14002556f  mov     rdi, [rbp+57h+TokenHandle]
0x140025573  lea     rax, [rdi-1]
0x140025577  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002557b  ja      short loc_14002559E
0x14002557d  lea     rcx, [rbp+57h+Token]; this
0x140025581  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140025586  mov     rcx, rdi; hObject
0x140025589  call    cs:__imp_CloseHandle
0x140025590  nop     dword ptr [rax+rax+00h]
0x140025595  lea     rcx, [rbp+57h+Token]; this
0x140025599  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14002559e  mov     [rbp+57h+TokenHandle], rbx
0x1400255a2  call    cs:__imp_GetCurrentThread
0x1400255a9  nop     dword ptr [rax+rax+00h]
0x1400255ae  xor     r8d, r8d; OpenAsSelf
0x1400255b1  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1400255b5  mov     rcx, rax; ThreadHandle
0x1400255b8  lea     edx, [r8+0Eh]; DesiredAccess
0x1400255bc  call    cs:__imp_OpenThreadToken
0x1400255c3  nop     dword ptr [rax+rax+00h]
0x1400255c8  test    eax, eax
0x1400255ca  jnz     short loc_1400255E7
0x1400255cc  call    cs:__imp_GetLastError
0x1400255d3  nop     dword ptr [rax+rax+00h]
0x1400255d8  mov     ebx, eax
0x1400255da  test    eax, eax
0x1400255dc  jle     short loc_1400255E7
0x1400255de  movzx   ebx, ax
0x1400255e1  or      ebx, 80070000h
0x1400255e7  mov     edi, 58h ; 'X'
0x1400255ec  lea     rcx, [rbp+57h+TokenInformation]; void *
0x1400255f0  mov     r8d, edi; Size
0x1400255f3  xor     edx, edx; Val
0x1400255f5  call    memset_0
0x1400255fa  mov     [rbp+57h+var_A0], edi
0x1400255fd  test    ebx, ebx
0x1400255ff  js      loc_140025754
0x140025605  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140025609  lea     rax, [rbp+57h+var_A0]
0x14002560d  mov     r9d, edi; TokenInformationLength
0x140025610  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x140025615  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140025619  lea     edx, [rdi-3Fh]; TokenInformationClass
0x14002561c  call    cs:__imp_GetTokenInformation
0x140025623  nop     dword ptr [rax+rax+00h]
0x140025628  test    eax, eax
0x14002562a  jnz     short loc_14002564F
0x14002562c  call    cs:__imp_GetLastError
0x140025633  nop     dword ptr [rax+rax+00h]
0x140025638  mov     ebx, eax
0x14002563a  test    eax, eax
0x14002563c  jle     short loc_140025647
0x14002563e  movzx   ebx, ax
0x140025641  or      ebx, 80070000h
0x140025647  test    ebx, ebx
0x140025649  js      loc_140025754
0x14002564f  mov     rcx, [rbp+57h+TokenInformation]; pSid
0x140025653  mov     edx, 42h ; 'B'; WellKnownSidType
0x140025658  call    cs:__imp_IsWellKnownSid
0x14002565f  nop     dword ptr [rax+rax+00h]
0x140025664  mov     [rsi], eax
0x140025666  test    eax, eax
0x140025668  jnz     short loc_14002567E
0x14002566a  call    cs:__imp_GetIsEdpEnabled
0x140025671  nop     dword ptr [rax+rax+00h]
0x140025676  test    eax, eax
0x140025678  jz      loc_140025754
0x14002567e  xor     edx, edx; dwCoInit
0x140025680  xor     ecx, ecx; pvReserved
0x140025682  call    cs:__imp_CoInitializeEx
0x140025689  nop     dword ptr [rax+rax+00h]
0x14002568e  mov     ecx, 80000000h
0x140025693  mov     edi, eax
0x140025695  add     eax, ecx
0x140025697  test    ecx, eax
0x140025699  jnz     short loc_1400256AA
0x14002569b  cmp     edi, 80010106h
0x1400256a1  jz      short loc_1400256AA
0x1400256a3  mov     ebx, edi
0x1400256a5  jmp     loc_140025754
0x1400256aa  lea     rcx, [rbp+57h+var_98]
0x1400256ae  mov     [rbp+57h+var_98], 0
0x1400256b6  call    ?GetPrintScanBroker@NSecurityLibrary@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; NSecurityLibrary::GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1400256bb  mov     ebx, eax
0x1400256bd  test    eax, eax
0x1400256bf  js      short loc_140025736
0x1400256c1  mov     rcx, [rbp+57h+var_98]
0x1400256c5  lea     r8, [rbp+57h+Token]
0x1400256c9  mov     rdx, [rbp+57h+TokenHandle]
0x1400256cd  mov     [rbp+57h+Token], 0
0x1400256d5  mov     rax, [rcx]
0x1400256d8  mov     rax, [rax+48h]
0x1400256dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400256e1  mov     ebx, eax
0x1400256e3  test    eax, eax
0x1400256e5  js      short loc_140025736
0x1400256e7  mov     rdx, [rbp+57h+Token]; Token
0x1400256eb  xor     ecx, ecx; Thread
0x1400256ed  mov     [rbp+57h+var_90], rdx
0x1400256f1  call    cs:__imp_SetThreadToken
0x1400256f8  nop     dword ptr [rax+rax+00h]
0x1400256fd  test    eax, eax
0x1400256ff  jz      short loc_140025712
0x140025701  mov     rax, [rbp+57h+TokenHandle]
0x140025705  mov     [r14], rax
0x140025708  mov     [rbp+57h+TokenHandle], 0
0x140025710  jmp     short loc_14002572D
0x140025712  call    cs:__imp_GetLastError
0x140025719  nop     dword ptr [rax+rax+00h]
0x14002571e  mov     ebx, eax
0x140025720  test    eax, eax
0x140025722  jle     short loc_14002572D
0x140025724  movzx   ebx, ax
0x140025727  or      ebx, 80070000h
0x14002572d  lea     rcx, [rbp+57h+var_90]
0x140025731  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140025736  lea     rcx, [rbp+57h+var_98]; this
0x14002573a  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14002573f  shr     edi, 1Fh
0x140025742  xor     dil, 1
0x140025746  jz      short loc_140025754
0x140025748  call    cs:__imp_CoUninitialize
0x14002574f  nop     dword ptr [rax+rax+00h]
0x140025754  lea     rcx, [rbp+57h+TokenHandle]
0x140025758  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14002575d  mov     eax, ebx
0x14002575f  mov     rcx, [rbp+57h+var_20]
0x140025763  xor     rcx, rsp; StackCookie
0x140025766  call    __security_check_cookie
0x14002576b  lea     r11, [rsp+0E0h+var_10]
0x140025773  mov     rbx, [r11+30h]
0x140025777  mov     rsi, [r11+38h]
0x14002577b  mov     rsp, r11
0x14002577e  pop     r14
0x140025780  pop     rdi
0x140025781  pop     rbp
0x140025782  retn
```
