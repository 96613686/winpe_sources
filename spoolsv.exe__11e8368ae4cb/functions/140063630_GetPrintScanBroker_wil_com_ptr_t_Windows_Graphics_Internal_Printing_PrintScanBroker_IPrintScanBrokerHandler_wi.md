# GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)

- ea: `0x140063630`
- end: `0x140063723`
- name: `?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z`
- size: `243`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400631d4`
- `0x1400633f8`

## callees

- `0x1400140cc`
- `0x140017ae0`
- `0x14002abc0`
- `0x140063630`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140063688`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x140063688`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140063699`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x140063699`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140063672`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x140063672`

## string_xrefs

- `0x1400636e0`: `QueryTo IPrintScanBrokerHandler failed. Error 0x%x`
- `0x1400636e9`: `RoActivateInstance for PrintScanBrokerHandler failed. Error 0x%x`
- `0x140063656`: `Windows.Graphics.Internal.Printing.PrintScanBroker.PrintScanBrokerHandler`
- `0x1400636f3`: `GetPrintScanBroker`

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
0x140063630  mov     r11, rsp
0x140063633  mov     [r11+10h], rbx
0x140063637  push    rdi
0x140063638  sub     rsp, 50h
0x14006363c  mov     rax, cs:__security_cookie
0x140063643  xor     rax, rsp
0x140063646  mov     [rsp+58h+var_10], rax
0x14006364b  mov     rdi, rcx
0x14006364e  mov     qword ptr [r11-38h], 0
0x140063656  lea     rcx, ?RuntimeClass_Windows_Graphics_Internal_Printing_PrintScanBroker_PrintScanBrokerHandler@@3QBGB; "Windows.Graphics.Internal.Printing.Prin"...
0x14006365d  mov     qword ptr [r11-18h], 0
0x140063665  lea     r9, [r11-18h]; string
0x140063669  mov     edx, 49h ; 'I'; length
0x14006366e  lea     r8, [r11-30h]; hstringHeader
0x140063672  call    cs:__imp_WindowsCreateStringReference
0x140063678  test    eax, eax
0x14006367a  jns     short loc_14006368F
0x14006367c  xor     r9d, r9d; lpArguments
0x14006367f  xor     r8d, r8d; nNumberOfArguments
0x140063682  mov     ecx, eax; dwExceptionCode
0x140063684  lea     edx, [r9+1]; dwExceptionFlags
0x140063688  call    cs:__imp_RaiseException
0x14006368e  int     3; Trap to Debugger
0x14006368f  mov     rcx, [rsp+58h+var_18]
0x140063694  lea     rdx, [rsp+58h+var_38]
0x140063699  call    cs:__imp_RoActivateInstance
0x14006369f  mov     ebx, eax
0x1400636a1  test    eax, eax
0x1400636a3  js      short loc_1400636E9
0x1400636a5  mov     rcx, [rdi]
0x1400636a8  mov     qword ptr [rdi], 0
0x1400636af  test    rcx, rcx
0x1400636b2  jz      short loc_1400636C0
0x1400636b4  mov     rax, [rcx]
0x1400636b7  mov     rax, [rax+10h]
0x1400636bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400636c0  mov     rcx, [rsp+58h+var_38]
0x1400636c5  lea     rdx, _GUID_42964634_70ff_4d1c_8ea0_520607b4c1c3
0x1400636cc  mov     r8, rdi
0x1400636cf  mov     rax, [rcx]
0x1400636d2  mov     rax, [rax]
0x1400636d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400636da  mov     ebx, eax
0x1400636dc  test    eax, eax
0x1400636de  jns     short loc_1400636FF
0x1400636e0  lea     rdx, aQuerytoIprints_0; "QueryTo IPrintScanBrokerHandler failed."...
0x1400636e7  jmp     short loc_1400636F0
0x1400636e9  lea     rdx, aRoactivateinst; "RoActivateInstance for PrintScanBrokerH"...
0x1400636f0  mov     r8d, eax
0x1400636f3  lea     rcx, aGetprintscanbr_0; "GetPrintScanBroker"
0x1400636fa  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400636ff  lea     rcx, [rsp+58h+var_38]; this
0x140063704  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x140063709  mov     eax, ebx
0x14006370b  mov     rcx, [rsp+58h+var_10]
0x140063710  xor     rcx, rsp; StackCookie
0x140063713  call    __security_check_cookie
0x140063718  mov     rbx, [rsp+58h+arg_8]
0x14006371d  add     rsp, 50h
0x140063721  pop     rdi
0x140063722  retn
```
