# GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)

- ea: `0x140069514`
- end: `0x140069772`
- name: `?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z`
- size: `606`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14006c574`
- `0x1400709e0`

## callees

- `0x140015290`
- `0x140015378`
- `0x140018f84`
- `0x14004bf6c`
- `0x140069514`
- `0x140069778`
- `0x140081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140069560`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006957a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140069594`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400695ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140069560`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006957a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140069594`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1400695ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400696c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400696c7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006974b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006974b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400695df`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400695df`

## string_xrefs

- `0x140069646`: `Getting user token for SID %ws`
- `0x1400696de`: `Getting user token for session id %d`
- `0x14006960b`: `GetImpersonationTokenForUserViaBroker`
- `0x14006964d`: `GetImpersonationTokenForUserViaBroker`
- `0x1400696b7`: `GetImpersonationTokenForUserViaBroker`
- `0x1400696e5`: `GetImpersonationTokenForUserViaBroker`
- `0x14006972d`: `GetImpersonationTokenForUserViaBroker`
- `0x1400696a4`: `GetUserToken failed. Error 0x%x`
- `0x14006971a`: `GetUserTokenForSession failed. Error 0x%x`
- `0x140069723`: `GetPrintScanBroker failed. Error 0x%x`

## pseudocode

```c
__int64 __fastcall GetImpersonationTokenForUserViaBroker(
        int a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        void **a4)
{
  HRESULT v9; // edi
  unsigned int v10; // ebx
  int PrintScanBroker; // eax
  __int64 v12; // r8
  int v13; // eax
  int v14; // eax
  int v15; // eax
  __int64 v16; // [rsp+20h] [rbp-18h] BYREF
  HSTRING string[2]; // [rsp+28h] [rbp-10h] BYREF
  void *v18; // [rsp+98h] [rbp+60h] BYREF

  *a4 = 0;
  if ( a1 == 1 )
  {
    if ( a2 && *a2 )
    {
      if ( !(unsigned int)_o__wcsicmp(a2, L"S-1-5-18")
        || !(unsigned int)_o__wcsicmp(a2, L"S-1-5-19")
        || !(unsigned int)_o__wcsicmp(a2, L"S-1-5-20")
        || !(unsigned int)_o__wcsicmp(a2, L".Default") )
      {
        return 2147549485LL;
      }
      goto LABEL_11;
    }
    return 2147942487LL;
  }
  if ( a1 != 2 || !a3 )
    return 2147942487LL;
LABEL_11:
  v9 = CoInitializeEx(0, 0);
  if ( (int)(v9 + 0x80000000) < 0 || v9 == -2147417850 )
  {
    v16 = 0;
    PrintScanBroker = GetPrintScanBroker(&v16);
    v10 = PrintScanBroker;
    if ( PrintScanBroker < 0 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "GetImpersonationTokenForUserViaBroker",
        L"GetPrintScanBroker failed. Error 0x%x",
        (unsigned int)PrintScanBroker);
    }
    else
    {
      v18 = 0;
      if ( a1 == 1 )
      {
        PrvSpoolssTelemetry::WriteDbgTraceInfo(
          "GetImpersonationTokenForUserViaBroker",
          L"Getting user token for SID %ws",
          a2);
        v12 = -1;
        string[0] = 0;
        do
          ++v12;
        while ( a2[v12] );
        v13 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)string, a2, v12);
        v10 = v13;
        if ( v13 < 0 )
        {
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "GetImpersonationTokenForUserViaBroker",
            L"HString::Set failed. Error 0x%x",
            (unsigned int)v13);
        }
        else
        {
          v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, void **))(*(_QWORD *)v16 + 112LL))(v16, string[0], &v18);
          v10 = v14;
          if ( v14 < 0 )
            PrvSpoolssTelemetry::WriteDbgTraceError(
              "GetImpersonationTokenForUserViaBroker",
              L"GetUserToken failed. Error 0x%x",
              (unsigned int)v14);
          else
            *a4 = v18;
        }
        WindowsDeleteString(string[0]);
      }
      else
      {
        PrvSpoolssTelemetry::WriteDbgTraceInfo(
          "GetImpersonationTokenForUserViaBroker",
          L"Getting user token for session id %d",
          a3);
        v15 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **))(*(_QWORD *)v16 + 128LL))(v16, a3, &v18);
        v10 = v15;
        if ( v15 < 0 )
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "GetImpersonationTokenForUserViaBroker",
            L"GetUserTokenForSession failed. Error 0x%x",
            (unsigned int)v15);
        else
          *a4 = v18;
      }
    }
    sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v16);
    if ( v9 >= 0 )
      CoUninitialize();
  }
  else
  {
    v10 = v9;
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "GetImpersonationTokenForUserViaBroker",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)v9);
  }
  return v10;
}

```

## disassembly

```asm
0x140069514  push    rbp
0x140069516  push    rbx
0x140069517  push    rsi
0x140069518  push    rdi
0x140069519  push    r12
0x14006951b  push    r13
0x14006951d  push    r14
0x14006951f  push    r15
0x140069521  mov     rbp, rsp
0x140069524  sub     rsp, 38h
0x140069528  xor     r13d, r13d
0x14006952b  mov     r15, r9
0x14006952e  mov     [r9], r13
0x140069531  mov     r12d, r8d
0x140069534  mov     rsi, rdx
0x140069537  mov     r14d, ecx
0x14006953a  cmp     ecx, 1
0x14006953d  jnz     loc_1400695C8
0x140069543  test    rdx, rdx
0x140069546  jz      loc_14006975B
0x14006954c  cmp     [rdx], r13w
0x140069550  jz      loc_14006975B
0x140069556  lea     rdx, aS1518; "S-1-5-18"
0x14006955d  mov     rcx, rsi
0x140069560  call    cs:__imp__o__wcsicmp
0x140069567  nop     dword ptr [rax+rax+00h]
0x14006956c  test    eax, eax
0x14006956e  jz      short loc_1400695BE
0x140069570  lea     rdx, aS1519; "S-1-5-19"
0x140069577  mov     rcx, rsi
0x14006957a  call    cs:__imp__o__wcsicmp
0x140069581  nop     dword ptr [rax+rax+00h]
0x140069586  test    eax, eax
0x140069588  jz      short loc_1400695BE
0x14006958a  lea     rdx, aS1520; "S-1-5-20"
0x140069591  mov     rcx, rsi
0x140069594  call    cs:__imp__o__wcsicmp
0x14006959b  nop     dword ptr [rax+rax+00h]
0x1400695a0  test    eax, eax
0x1400695a2  jz      short loc_1400695BE
0x1400695a4  lea     rdx, aDefault; ".Default"
0x1400695ab  mov     rcx, rsi
0x1400695ae  call    cs:__imp__o__wcsicmp
0x1400695b5  nop     dword ptr [rax+rax+00h]
0x1400695ba  test    eax, eax
0x1400695bc  jnz     short loc_1400695DB
0x1400695be  mov     eax, 8001012Dh
0x1400695c3  jmp     loc_140069760
0x1400695c8  cmp     r14d, 2
0x1400695cc  jnz     loc_14006975B
0x1400695d2  test    r12d, r12d
0x1400695d5  jz      loc_14006975B
0x1400695db  xor     edx, edx; dwCoInit
0x1400695dd  xor     ecx, ecx; pvReserved
0x1400695df  call    cs:__imp_CoInitializeEx
0x1400695e6  nop     dword ptr [rax+rax+00h]
0x1400695eb  mov     edi, eax
0x1400695ed  mov     eax, 80000000h
0x1400695f2  lea     ecx, [rdi+rax]
0x1400695f5  test    eax, ecx
0x1400695f7  jnz     short loc_14006961E
0x1400695f9  cmp     edi, 80010106h
0x1400695ff  jz      short loc_14006961E
0x140069601  mov     r8d, edi
0x140069604  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x14006960b  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x140069612  mov     ebx, edi
0x140069614  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069619  jmp     loc_140069757
0x14006961e  lea     rcx, [rbp+var_18]
0x140069622  mov     [rbp+var_18], r13
0x140069626  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x14006962b  mov     ebx, eax
0x14006962d  test    eax, eax
0x14006962f  js      loc_140069723
0x140069635  mov     [rbp+arg_18], r13
0x140069639  cmp     r14d, 1
0x14006963d  jnz     loc_1400696D5
0x140069643  mov     r8, rsi
0x140069646  lea     rdx, aGettingUserTok_0; "Getting user token for SID %ws"
0x14006964d  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x140069654  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140069659  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006965d  mov     [rbp+string], r13
0x140069661  inc     r8; unsigned int
0x140069664  cmp     [rsi+r8*2], r13w
0x140069669  jnz     short loc_140069661
0x14006966b  mov     rdx, rsi; unsigned __int16 *
0x14006966e  lea     rcx, [rbp+string]; this
0x140069672  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140069677  mov     ebx, eax
0x140069679  test    eax, eax
0x14006967b  js      short loc_1400696AD
0x14006967d  mov     rcx, [rbp+var_18]
0x140069681  lea     r8, [rbp+arg_18]
0x140069685  mov     rdx, [rbp+string]
0x140069689  mov     rax, [rcx]
0x14006968c  mov     rax, [rax+70h]
0x140069690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069695  mov     ebx, eax
0x140069697  test    eax, eax
0x140069699  js      short loc_1400696A4
0x14006969b  mov     rax, [rbp+arg_18]
0x14006969f  mov     [r15], rax
0x1400696a2  jmp     short loc_1400696C3
0x1400696a4  lea     rdx, aGetusertokenFa; "GetUserToken failed. Error 0x%x"
0x1400696ab  jmp     short loc_1400696B4
0x1400696ad  lea     rdx, aHstringSetFail; "HString::Set failed. Error 0x%x"
0x1400696b4  mov     r8d, eax
0x1400696b7  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x1400696be  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400696c3  mov     rcx, [rbp+string]; string
0x1400696c7  call    cs:__imp_WindowsDeleteString
0x1400696ce  nop     dword ptr [rax+rax+00h]
0x1400696d3  jmp     short loc_140069739
0x1400696d5  cmp     r14d, 2
0x1400696d9  jnz     short loc_140069739
0x1400696db  mov     r8d, r12d
0x1400696de  lea     rdx, aGettingUserTok; "Getting user token for session id %d"
0x1400696e5  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x1400696ec  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400696f1  mov     rcx, [rbp+var_18]
0x1400696f5  lea     r8, [rbp+arg_18]
0x1400696f9  mov     edx, r12d
0x1400696fc  mov     rax, [rcx]
0x1400696ff  mov     rax, [rax+80h]
0x140069706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006970b  mov     ebx, eax
0x14006970d  test    eax, eax
0x14006970f  js      short loc_14006971A
0x140069711  mov     rax, [rbp+arg_18]
0x140069715  mov     [r15], rax
0x140069718  jmp     short loc_140069739
0x14006971a  lea     rdx, aGetusertokenfo; "GetUserTokenForSession failed. Error 0x"...
0x140069721  jmp     short loc_14006972A
0x140069723  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x14006972a  mov     r8d, eax
0x14006972d  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x140069734  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069739  lea     rcx, [rbp+var_18]; this
0x14006973d  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x140069742  shr     edi, 1Fh
0x140069745  xor     dil, 1
0x140069749  jz      short loc_140069757
0x14006974b  call    cs:__imp_CoUninitialize
0x140069752  nop     dword ptr [rax+rax+00h]
0x140069757  mov     eax, ebx
0x140069759  jmp     short loc_140069760
0x14006975b  mov     eax, 80070057h
0x140069760  add     rsp, 38h
0x140069764  pop     r15
0x140069766  pop     r14
0x140069768  pop     r13
0x14006976a  pop     r12
0x14006976c  pop     rdi
0x14006976d  pop     rsi
0x14006976e  pop     rbx
0x14006976f  pop     rbp
0x140069770  retn
```
