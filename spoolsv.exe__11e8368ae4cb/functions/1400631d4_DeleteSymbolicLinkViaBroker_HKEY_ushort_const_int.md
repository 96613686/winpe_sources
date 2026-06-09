# DeleteSymbolicLinkViaBroker(HKEY__ *,ushort const *,int *)

- ea: `0x1400631d4`
- end: `0x14006332d`
- name: `?DeleteSymbolicLinkViaBroker@@YAJPEAUHKEY__@@PEBGPEAH@Z`
- size: `345`
- prototype: `int(HKEY, const unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x140069910`

## callees

- `0x1400140cc`
- `0x140017ae0`
- `0x140047b98`
- `0x1400631d4`
- `0x140063630`
- `0x14007a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400632e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400632e3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140063314`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140063314`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400631f7`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1400631f7`

## string_xrefs

- `0x1400632ee`: `GetPrintScanBroker failed. Error 0x%x`
- `0x1400632bc`: `DeleteSymbolicLink failed. Error 0x%x`
- `0x14006321c`: `DeleteSymbolicLinkViaBroker`
- `0x1400632cf`: `DeleteSymbolicLinkViaBroker`
- `0x1400632f5`: `DeleteSymbolicLinkViaBroker`

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
  _QWORD v13[7]; // [rsp+30h] [rbp-38h] BYREF
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
        v11 = (*(__int64 (__fastcall **)(_QWORD, HKEY, HSTRING, char *))(*(_QWORD *)v13[0] + 160LL))(
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
0x1400631d4  mov     [rsp+arg_0], rbx
0x1400631d9  push    rbp
0x1400631da  push    rsi
0x1400631db  push    rdi
0x1400631dc  push    r14
0x1400631de  push    r15
0x1400631e0  sub     rsp, 40h
0x1400631e4  mov     rsi, rdx
0x1400631e7  mov     rbp, rcx
0x1400631ea  xor     r15d, r15d
0x1400631ed  xor     edx, edx; dwCoInit
0x1400631ef  xor     ecx, ecx; pvReserved
0x1400631f1  mov     [r8], r15d
0x1400631f4  mov     r14, r8
0x1400631f7  call    cs:__imp_CoInitializeEx
0x1400631fd  mov     ecx, 80000000h
0x140063202  mov     edi, eax
0x140063204  add     eax, ecx
0x140063206  test    ecx, eax
0x140063208  jnz     short loc_14006322F
0x14006320a  cmp     edi, 80010106h
0x140063210  jz      short loc_14006322F
0x140063212  mov     r8d, edi
0x140063215  lea     rdx, aCoinitializeex_0; "CoInitializeEx failed. Error 0x%x"
0x14006321c  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x140063223  mov     ebx, edi
0x140063225  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x14006322a  jmp     loc_14006331A
0x14006322f  lea     rcx, [rsp+68h+var_38]
0x140063234  mov     [rsp+68h+var_38], r15
0x140063239  call    ?GetPrintScanBroker@@YAJAEAV?$com_ptr_t@UIPrintScanBrokerHandler@PrintScanBroker@Printing@Internal@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@@Z; GetPrintScanBroker(wil::com_ptr_t<Windows::Graphics::Internal::Printing::PrintScanBroker::IPrintScanBrokerHandler,wil::err_returncode_policy> &)
0x14006323e  mov     ebx, eax
0x140063240  test    eax, eax
0x140063242  js      loc_1400632EB
0x140063248  mov     [rsp+68h+string], r15
0x140063250  or      r8, 0FFFFFFFFFFFFFFFFh
0x140063254  inc     r8; unsigned int
0x140063257  cmp     [rsi+r8*2], r15w
0x14006325c  jnz     short loc_140063254
0x14006325e  mov     rdx, rsi; unsigned __int16 *
0x140063261  lea     rcx, [rsp+68h+string]; this
0x140063269  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x14006326e  mov     ebx, eax
0x140063270  test    eax, eax
0x140063272  js      short loc_1400632C5
0x140063274  mov     rcx, [rsp+68h+var_38]
0x140063279  lea     r9, [rsp+68h+arg_10]
0x140063281  mov     r8, [rsp+68h+string]
0x140063289  mov     rdx, rbp
0x14006328c  mov     [rsp+68h+arg_10], r15b
0x140063294  mov     rax, [rcx]
0x140063297  mov     rax, [rax+0A0h]
0x14006329e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400632a3  mov     ebx, eax
0x1400632a5  test    eax, eax
0x1400632a7  js      short loc_1400632BC
0x1400632a9  cmp     [rsp+68h+arg_10], r15b
0x1400632b1  mov     eax, r15d
0x1400632b4  setnz   al
0x1400632b7  mov     [r14], eax
0x1400632ba  jmp     short loc_1400632DB
0x1400632bc  lea     rdx, aDeletesymbolic_2; "DeleteSymbolicLink failed. Error 0x%x"
0x1400632c3  jmp     short loc_1400632CC
0x1400632c5  lea     rdx, aHstringSetFail; "HString::Set failed. Error 0x%x"
0x1400632cc  mov     r8d, eax
0x1400632cf  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x1400632d6  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1400632db  mov     rcx, [rsp+68h+string]; string
0x1400632e3  call    cs:__imp_WindowsDeleteString
0x1400632e9  jmp     short loc_140063301
0x1400632eb  mov     r8d, eax
0x1400632ee  lea     rdx, aGetprintscanbr; "GetPrintScanBroker failed. Error 0x%x"
0x1400632f5  lea     rcx, aDeletesymbolic_1; "DeleteSymbolicLinkViaBroker"
0x1400632fc  call    ?WriteDbgTraceError@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140063301  lea     rcx, [rsp+68h+var_38]; this
0x140063306  call    ??1DriverConfigModuleAdapter@sandbox@@QEAA@XZ; sandbox::DriverConfigModuleAdapter::~DriverConfigModuleAdapter(void)
0x14006330b  shr     edi, 1Fh
0x14006330e  xor     dil, 1
0x140063312  jz      short loc_14006331A
0x140063314  call    cs:__imp_CoUninitialize
0x14006331a  mov     eax, ebx
0x14006331c  mov     rbx, [rsp+68h+arg_0]
0x140063321  add     rsp, 40h
0x140063325  pop     r15
0x140063327  pop     r14
0x140063329  pop     rdi
0x14006332a  pop     rsi
0x14006332b  pop     rbp
0x14006332c  retn
```
