# GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)

- ea: `0x140069778`
- end: `0x14006987e`
- name: `?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400692c0`
- `0x140069514`

## callees

- `0x140015378`
- `0x140018f84`
- `0x14002d0a0`
- `0x140069778`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400697d6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1400697d6`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400697ed`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x1400697ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400697ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400697ba`

## string_xrefs

- `0x14006983a`: `QueryTo IPrintScanBrokerHandler failed. Error 0x%x`
- `0x140069843`: `RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x`
- `0x14006979e`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x14006984d`: `GetPrintScanBroker`

## pseudocode

```c
__int64 __fastcall GetPrintScanBroker(__int64 *a1)
{
  HRESULT v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rcx
  int v6; // eax
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-38h] BYREF
  HSTRING_HEADER v9; // [rsp+28h] [rbp-30h] BYREF
  HSTRING v10; // [rsp+40h] [rbp-18h] BYREF

  v8 = 0;
  v10 = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler",
         0x49u,
         &v9,
         &v10);
  if ( v2 < 0 )
  {
    RaiseException(v2, 1u, 0, 0);
    __debugbreak();
  }
  v3 = RoActivateInstance(v10, &v8);
  v4 = v3;
  if ( v3 < 0 )
  {
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "GetPrintScanBroker",
      L"RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x",
      (unsigned int)v3);
  }
  else
  {
    v5 = *a1;
    *a1 = 0;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    v6 = (**v8)(v8, &GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3, a1);
    v4 = v6;
    if ( v6 < 0 )
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "GetPrintScanBroker",
        L"QueryTo IPrintScanBrokerHandler failed. Error 0x%x",
        (unsigned int)v6);
  }
  sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)&v8);
  return v4;
}

```

## disassembly

```asm
0x140069778  mov     r11, rsp
0x14006977b  mov     [r11+10h], rbx
0x14006977f  push    rdi
0x140069780  sub     rsp, 50h
0x140069784  mov     rax, cs:__security_cookie
0x14006978b  xor     rax, rsp
0x14006978e  mov     [rsp+58h+var_10], rax
0x140069793  mov     rdi, rcx
0x140069796  mov     qword ptr [r11-38h], 0
0x14006979e  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x1400697a5  mov     qword ptr [r11-18h], 0
0x1400697ad  lea     r9, [r11-18h]; string
0x1400697b1  mov     edx, 49h ; 'I'; length
0x1400697b6  lea     r8, [r11-30h]; hstringHeader
0x1400697ba  call    cs:__imp_WindowsCreateStringReference
0x1400697c1  nop     dword ptr [rax+rax+00h]
0x1400697c6  test    eax, eax
0x1400697c8  jns     short loc_1400697E3
0x1400697ca  xor     r9d, r9d; lpArguments
0x1400697cd  xor     r8d, r8d; nNumberOfArguments
0x1400697d0  mov     ecx, eax; dwExceptionCode
0x1400697d2  lea     edx, [r9+1]; dwExceptionFlags
0x1400697d6  call    cs:__imp_RaiseException
0x1400697dd  nop     dword ptr [rax+rax+00h]
0x1400697e2  int     3; Trap to Debugger
0x1400697e3  mov     rcx, [rsp+58h+var_18]
0x1400697e8  lea     rdx, [rsp+58h+var_38]
0x1400697ed  call    cs:__imp_RoActivateInstance
0x1400697f4  nop     dword ptr [rax+rax+00h]
0x1400697f9  mov     ebx, eax
0x1400697fb  test    eax, eax
0x1400697fd  js      short loc_140069843
0x1400697ff  mov     rcx, [rdi]
0x140069802  mov     qword ptr [rdi], 0
0x140069809  test    rcx, rcx
0x14006980c  jz      short loc_14006981A
0x14006980e  mov     rax, [rcx]
0x140069811  mov     rax, [rax+10h]
0x140069815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006981a  mov     rcx, [rsp+58h+var_38]
0x14006981f  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x140069826  mov     r8, rdi
0x140069829  mov     rax, [rcx]
0x14006982c  mov     rax, [rax]
0x14006982f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069834  mov     ebx, eax
0x140069836  test    eax, eax
0x140069838  jns     short loc_140069859
0x14006983a  lea     rdx, aQuerytoIprints_0; "QueryTo IPrintScanBrokerHandler failed."...
0x140069841  jmp     short loc_14006984A
0x140069843  lea     rdx, aRoactivateinst; "RoActivateInstance for PrintScanBrokerH"...
0x14006984a  mov     r8d, eax
0x14006984d  lea     rcx, aGetprintscanbr_0; "GetPrintScanBroker"
0x140069854  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140069859  lea     rcx, [rsp+58h+var_38]; this
0x14006985e  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x140069863  mov     eax, ebx
0x140069865  mov     rcx, [rsp+58h+var_10]
0x14006986a  xor     rcx, rsp; StackCookie
0x14006986d  call    __security_check_cookie
0x140069872  mov     rbx, [rsp+58h+arg_8]
0x140069877  add     rsp, 50h
0x14006987b  pop     rdi
0x14006987c  retn
```
