# DeleteSymbolicLinkViaBroker(HKEY__ *,ushort const *,int *)

- ea: `0x1400692c0`
- end: `0x14006942c`
- name: `?DeleteSymbolicLinkViaBroker@@YAJPEAUHKEY__@@PEBGPEAH@Z`
- size: `364`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1400702f8`

## callees

- `0x140015378`
- `0x140018f84`
- `0x14004bf6c`
- `0x1400692c0`
- `0x140069778`
- `0x140081010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400693d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400693d5`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006940c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006940c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400692e3`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400692e3`

## string_xrefs

- `0x1400693ae`: `DeleteSymbolicLink failed. Error 0x%x`
- `0x14006930e`: `DeleteSymbolicLinkViaBroker`
- `0x1400693c1`: `DeleteSymbolicLinkViaBroker`
- `0x1400693ed`: `DeleteSymbolicLinkViaBroker`
- `0x1400693e6`: `GetPrintScanBroker failed. Error 0x%x`

## pseudocode

```c
__int64 __fastcall DeleteSymbolicLinkViaBroker(HKEY a1, const unsigned __int16 *a2, int *a3)
{
  HRESULT v6; // edi
  unsigned int v7; // ebx
  int PrintScanBroker; // eax
  __int64 v9; // r8
  int v10; // eax
  int v11; // eax
  __int64 v13[7]; // [rsp+30h] [rbp-38h] BYREF
  char v14; // [rsp+80h] [rbp+18h] BYREF
  HSTRING string; // [rsp+88h] [rbp+20h] BYREF

  *a3 = 0;
  v6 = CoInitializeEx(0, 0);
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147417850 )
  {
    v13[0] = 0;
    PrintScanBroker = GetPrintScanBroker(v13);
    v7 = PrintScanBroker;
    if ( PrintScanBroker < 0 )
    {
      PrvSpoolssTelemetry::WriteDbgTraceError(
        "DeleteSymbolicLinkViaBroker",
        L"GetPrintScanBroker failed. Error 0x%x",
        (unsigned int)PrintScanBroker);
    }
    else
    {
      string = 0;
      v9 = -1;
      do
        ++v9;
      while ( a2[v9] );
      v10 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, a2, v9);
      v7 = v10;
      if ( v10 < 0 )
      {
        PrvSpoolssTelemetry::WriteDbgTraceError(
          "DeleteSymbolicLinkViaBroker",
          L"HString::Set failed. Error 0x%x",
          (unsigned int)v10);
      }
      else
      {
        v14 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64, HKEY, HSTRING, char *))(*(_QWORD *)v13[0] + 160LL))(
                v13[0],
                a1,
                string,
                &v14);
        v7 = v11;
        if ( v11 < 0 )
          PrvSpoolssTelemetry::WriteDbgTraceError(
            "DeleteSymbolicLinkViaBroker",
            L"DeleteSymbolicLink failed. Error 0x%x",
            (unsigned int)v11);
        else
          *a3 = v14 != 0;
      }
      WindowsDeleteString(string);
    }
    sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter((sandbox::DriverConfigModuleAdapter *)v13);
    if ( v6 >= 0 )
      CoUninitialize();
  }
  else
  {
    v7 = v6;
    PrvSpoolssTelemetry::WriteDbgTraceError(
      "DeleteSymbolicLinkViaBroker",
      L"CoInitializeEx failed. Error 0x%x",
      (unsigned int)v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1400692c0  mov     [rsp+arg_0], rbx
0x1400692c5  push    rbp
0x1400692c6  push    rsi
0x1400692c7  push    rdi
0x1400692c8  push    r14
0x1400692ca  push    r15
0x1400692cc  sub     rsp, 40h
0x1400692d0  mov     rsi, rdx
0x1400692d3  mov     rbp, rcx
0x1400692d6  xor     r15d, r15d
0x1400692d9  xor     edx, edx; dwCoInit
0x1400692db  xor     ecx, ecx; pvReserved
0x1400692dd  mov     [r8], r15d
0x1400692e0  mov     r14, r8
0x1400692e3  call    cs:__imp_CoInitializeEx
0x1400692ea  nop     dword ptr [rax+rax+00h]
0x1400692ef  mov     ecx, 80000000h
0x1400692f4  mov     edi, eax
0x1400692f6  add     eax, ecx
0x1400692f8  test    ecx, eax
0x1400692fa  jnz     short loc_140069321
0x1400692fc  cmp     edi, 80010106h
0x140069302  jz      short loc_140069321
0x140069304  mov     r8d, edi
0x140069307  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x14006930e  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x140069315  mov     ebx, edi
0x140069317  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006931c  jmp     loc_140069418
0x140069321  lea     rcx, [rsp+68h+var_38]
0x140069326  mov     [rsp+68h+var_38], r15
0x14006932b  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x140069330  mov     ebx, eax
0x140069332  test    eax, eax
0x140069334  js      loc_1400693E3
0x14006933a  mov     [rsp+68h+string], r15
0x140069342  or      r8, 0FFFFFFFFFFFFFFFFh
0x140069346  inc     r8; unsigned int
0x140069349  cmp     [rsi+r8*2], r15w
0x14006934e  jnz     short loc_140069346
0x140069350  mov     rdx, rsi; unsigned __int16 *
0x140069353  lea     rcx, [rsp+68h+string]; this
0x14006935b  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x140069360  mov     ebx, eax
0x140069362  test    eax, eax
0x140069364  js      short loc_1400693B7
0x140069366  mov     rcx, [rsp+68h+var_38]
0x14006936b  lea     r9, [rsp+68h+arg_10]
0x140069373  mov     r8, [rsp+68h+string]
0x14006937b  mov     rdx, rbp
0x14006937e  mov     [rsp+68h+arg_10], r15b
0x140069386  mov     rax, [rcx]
0x140069389  mov     rax, [rax+0A0h]
0x140069390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140069395  mov     ebx, eax
0x140069397  test    eax, eax
0x140069399  js      short loc_1400693AE
0x14006939b  cmp     [rsp+68h+arg_10], r15b
0x1400693a3  mov     eax, r15d
0x1400693a6  setnz   al
0x1400693a9  mov     [r14], eax
0x1400693ac  jmp     short loc_1400693CD
0x1400693ae  lea     rdx, aDeletesymbolic_2; "DeleteSymbolicLink failed. Error 0x%x"
0x1400693b5  jmp     short loc_1400693BE
0x1400693b7  lea     rdx, aHstringSetFail; "HString::Set failed. Error 0x%x"
0x1400693be  mov     r8d, eax
0x1400693c1  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x1400693c8  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400693cd  mov     rcx, [rsp+68h+string]; string
0x1400693d5  call    cs:__imp_WindowsDeleteString
0x1400693dc  nop     dword ptr [rax+rax+00h]
0x1400693e1  jmp     short loc_1400693F9
0x1400693e3  mov     r8d, eax
0x1400693e6  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1400693ed  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x1400693f4  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400693f9  lea     rcx, [rsp+68h+var_38]; this
0x1400693fe  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x140069403  shr     edi, 1Fh
0x140069406  xor     dil, 1
0x14006940a  jz      short loc_140069418
0x14006940c  call    cs:__imp_CoUninitialize
0x140069413  nop     dword ptr [rax+rax+00h]
0x140069418  mov     eax, ebx
0x14006941a  mov     rbx, [rsp+68h+arg_0]
0x14006941f  add     rsp, 40h
0x140069423  pop     r15
0x140069425  pop     r14
0x140069427  pop     rdi
0x140069428  pop     rsi
0x140069429  pop     rbp
0x14006942a  retn
```
