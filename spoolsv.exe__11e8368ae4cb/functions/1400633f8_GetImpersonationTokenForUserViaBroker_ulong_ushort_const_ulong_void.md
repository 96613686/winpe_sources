# GetImpersonationTokenForUserViaBroker(ulong,ushort const *,ulong,void * *)

- ea: `0x1400633f8`
- end: `0x140063627`
- name: `?GetImpersonationTokenForUserViaBroker@@YAJKPEBGKPEAPEAX@Z`
- size: `559`
- prototype: `int(unsigned int, const unsigned __int16 *, unsigned int, void **)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140066058`
- `0x140069f68`

## callees

- `0x140013fe8`
- `0x1400140cc`
- `0x140017ae0`
- `0x140047b98`
- `0x1400633f8`
- `0x140063630`
- `0x14007a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063440`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063454`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063468`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006347c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063440`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063454`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140063468`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14006347c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140063589`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140063589`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140063607`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140063607`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400634a7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400634a7`

## string_xrefs

- `0x140063566`: `GetUserToken failed. Error 0x%x`
- `0x140063508`: `Getting user token for SID %ws`
- `0x1400634cd`: `GetImpersonationTokenForUserViaBroker`
- `0x14006350f`: `GetImpersonationTokenForUserViaBroker`
- `0x140063579`: `GetImpersonationTokenForUserViaBroker`
- `0x1400635a1`: `GetImpersonationTokenForUserViaBroker`
- `0x1400635e9`: `GetImpersonationTokenForUserViaBroker`
- `0x1400635df`: `GetPrintScanBroker failed. Error 0x%x`
- `0x14006359a`: `Getting user token for session id %d`
- `0x1400635d6`: `GetUserTokenForSession failed. Error 0x%x`

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
0x1400633f8  push    rbp
0x1400633fa  push    rbx
0x1400633fb  push    rsi
0x1400633fc  push    rdi
0x1400633fd  push    r12
0x1400633ff  push    r13
0x140063401  push    r14
0x140063403  push    r15
0x140063405  mov     rbp, rsp
0x140063408  sub     rsp, 38h
0x14006340c  xor     r13d, r13d
0x14006340f  mov     r15, r9
0x140063412  mov     [r9], r13
0x140063415  mov     r12d, r8d
0x140063418  mov     rsi, rdx
0x14006341b  mov     r14d, ecx
0x14006341e  cmp     ecx, 1
0x140063421  jnz     short loc_140063490
0x140063423  test    rdx, rdx
0x140063426  jz      loc_140063611
0x14006342c  cmp     [rdx], r13w
0x140063430  jz      loc_140063611
0x140063436  lea     rdx, aS1518; "S-1-5-18"
0x14006343d  mov     rcx, rsi
0x140063440  call    cs:__imp__o__wcsicmp
0x140063446  test    eax, eax
0x140063448  jz      short loc_140063486
0x14006344a  lea     rdx, aS1519; "S-1-5-19"
0x140063451  mov     rcx, rsi
0x140063454  call    cs:__imp__o__wcsicmp
0x14006345a  test    eax, eax
0x14006345c  jz      short loc_140063486
0x14006345e  lea     rdx, aS1520; "S-1-5-20"
0x140063465  mov     rcx, rsi
0x140063468  call    cs:__imp__o__wcsicmp
0x14006346e  test    eax, eax
0x140063470  jz      short loc_140063486
0x140063472  lea     rdx, aDefault; ".Default"
0x140063479  mov     rcx, rsi
0x14006347c  call    cs:__imp__o__wcsicmp
0x140063482  test    eax, eax
0x140063484  jnz     short loc_1400634A3
0x140063486  mov     eax, 8001012Dh
0x14006348b  jmp     loc_140063616
0x140063490  cmp     r14d, 2
0x140063494  jnz     loc_140063611
0x14006349a  test    r12d, r12d
0x14006349d  jz      loc_140063611
0x1400634a3  xor     edx, edx; dwCoInit
0x1400634a5  xor     ecx, ecx; pvReserved
0x1400634a7  call    cs:__imp_CoInitializeEx
0x1400634ad  mov     edi, eax
0x1400634af  mov     eax, 80000000h
0x1400634b4  lea     ecx, [rdi+rax]
0x1400634b7  test    eax, ecx
0x1400634b9  jnz     short loc_1400634E0
0x1400634bb  cmp     edi, 80010106h
0x1400634c1  jz      short loc_1400634E0
0x1400634c3  mov     r8d, edi
0x1400634c6  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x1400634cd  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x1400634d4  mov     ebx, edi
0x1400634d6  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400634db  jmp     loc_14006360D
0x1400634e0  lea     rcx, [rbp+var_18]
0x1400634e4  mov     [rbp+var_18], r13
0x1400634e8  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x1400634ed  mov     ebx, eax
0x1400634ef  test    eax, eax
0x1400634f1  js      loc_1400635DF
0x1400634f7  mov     [rbp+arg_18], r13
0x1400634fb  cmp     r14d, 1
0x1400634ff  jnz     loc_140063591
0x140063505  mov     r8, rsi
0x140063508  lea     rdx, aGettingUserTok_0; "Getting user token for SID %ws"
0x14006350f  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x140063516  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006351b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14006351f  mov     [rbp+string], r13
0x140063523  inc     r8; unsigned int
0x140063526  cmp     [rsi+r8*2], r13w
0x14006352b  jnz     short loc_140063523
0x14006352d  mov     rdx, rsi; unsigned __int16 *
0x140063530  lea     rcx, [rbp+string]; this
0x140063534  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140063539  mov     ebx, eax
0x14006353b  test    eax, eax
0x14006353d  js      short loc_14006356F
0x14006353f  mov     rcx, [rbp+var_18]
0x140063543  lea     r8, [rbp+arg_18]
0x140063547  mov     rdx, [rbp+string]
0x14006354b  mov     rax, [rcx]
0x14006354e  mov     rax, [rax+70h]
0x140063552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140063557  mov     ebx, eax
0x140063559  test    eax, eax
0x14006355b  js      short loc_140063566
0x14006355d  mov     rax, [rbp+arg_18]
0x140063561  mov     [r15], rax
0x140063564  jmp     short loc_140063585
0x140063566  lea     rdx, aGetusertokenFa; "GetUserToken failed. Error 0x%x"
0x14006356d  jmp     short loc_140063576
0x14006356f  lea     rdx, aHstringSetFail; "HString::Set failed. Error 0x%x"
0x140063576  mov     r8d, eax
0x140063579  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x140063580  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140063585  mov     rcx, [rbp+string]; string
0x140063589  call    cs:__imp_WindowsDeleteString
0x14006358f  jmp     short loc_1400635F5
0x140063591  cmp     r14d, 2
0x140063595  jnz     short loc_1400635F5
0x140063597  mov     r8d, r12d
0x14006359a  lea     rdx, aGettingUserTok; "Getting user token for session id %d"
0x1400635a1  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x1400635a8  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400635ad  mov     rcx, [rbp+var_18]
0x1400635b1  lea     r8, [rbp+arg_18]
0x1400635b5  mov     edx, r12d
0x1400635b8  mov     rax, [rcx]
0x1400635bb  mov     rax, [rax+80h]
0x1400635c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400635c7  mov     ebx, eax
0x1400635c9  test    eax, eax
0x1400635cb  js      short loc_1400635D6
0x1400635cd  mov     rax, [rbp+arg_18]
0x1400635d1  mov     [r15], rax
0x1400635d4  jmp     short loc_1400635F5
0x1400635d6  lea     rdx, aGetusertokenfo; "GetUserTokenForSession failed. Error 0x"...
0x1400635dd  jmp     short loc_1400635E6
0x1400635df  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1400635e6  mov     r8d, eax
0x1400635e9  lea     rcx, aGetimpersonati; "GetImpersonationTokenForUserViaBroker"
0x1400635f0  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400635f5  lea     rcx, [rbp+var_18]; this
0x1400635f9  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x1400635fe  shr     edi, 1Fh
0x140063601  xor     dil, 1
0x140063605  jz      short loc_14006360D
0x140063607  call    cs:__imp_CoUninitialize
0x14006360d  mov     eax, ebx
0x14006360f  jmp     short loc_140063616
0x140063611  mov     eax, 80070057h
0x140063616  add     rsp, 38h
0x14006361a  pop     r15
0x14006361c  pop     r14
0x14006361e  pop     r13
0x140063620  pop     r12
0x140063622  pop     rdi
0x140063623  pop     rsi
0x140063624  pop     rbx
0x140063625  pop     rbp
0x140063626  retn
```
