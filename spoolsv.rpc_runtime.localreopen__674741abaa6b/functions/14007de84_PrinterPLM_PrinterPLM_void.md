# PrinterPLM::~PrinterPLM(void)

- ea: `0x14007de84`
- end: `0x14007df3c`
- name: `??1PrinterPLM@@UEAA@XZ`
- size: `184`
- prototype: `void __fastcall(PrinterPLM *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14007df50`

## callees

- `0x14000f600`
- `0x140015b60`
- `0x1400161d0`
- `0x14007de84`
- `0x14007e154`
- `0x14007e70c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14007df0e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14007df0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007debb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14007debb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007deeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14007deeb`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x14007dedd`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x14007dedd`

## string_xrefs

- `0x14007dea0`: `Delete PLM object`

## pseudocode

```c
void __fastcall PrinterPLM::~PrinterPLM(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE v2; // rsi
  DWORD LastError; // ebx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&PrinterPLM::`vftable';
  PrintPLMTelemetry::WriteDbgTraceInfo("PrinterPLM::~PrinterPLM", L"Delete PLM object");
  v2 = RevertToPrinterSelf();
  LastError = GetLastError();
  PrinterPLM::EndExemption((PrinterPLM *)this);
  PrinterPLM::StopTimer((PrinterPLM *)this);
  CoFreeUnusedLibrariesEx(0, 0);
  SetLastError(LastError);
  if ( v2 )
    ImpersonatePrinterClient(v2);
  if ( this[2].LockCount >= 0 )
  {
    DeleteCriticalSection(this + 1);
    this[2].LockCount = -2147467259;
  }
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&NCoreLibrary::TReferenceCount::`vftable';
}

```

## disassembly

```asm
0x14007de84  mov     [rsp+arg_0], rbx
0x14007de89  mov     [rsp+arg_8], rsi
0x14007de8e  push    rdi
0x14007de8f  sub     rsp, 20h
0x14007de93  lea     rax, ??_7PrinterPLM@@6B@; const PrinterPLM::`vftable'
0x14007de9a  mov     rdi, rcx
0x14007de9d  mov     [rcx], rax
0x14007dea0  lea     rdx, aDeletePlmObjec; "Delete PLM object"
0x14007dea7  lea     rcx, aPrinterplmPrin; "PrinterPLM::~PrinterPLM"
0x14007deae  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007deb3  call    RevertToPrinterSelf
0x14007deb8  mov     rsi, rax
0x14007debb  call    cs:__imp_GetLastError
0x14007dec2  nop     dword ptr [rax+rax+00h]
0x14007dec7  mov     rcx, rdi; this
0x14007deca  mov     ebx, eax
0x14007decc  call    ?EndExemption@PrinterPLM@@AEAAXXZ; PrinterPLM::EndExemption(void)
0x14007ded1  mov     rcx, rdi; this
0x14007ded4  call    ?StopTimer@PrinterPLM@@AEAAXXZ; PrinterPLM::StopTimer(void)
0x14007ded9  xor     edx, edx; dwReserved
0x14007dedb  xor     ecx, ecx; dwUnloadDelay
0x14007dedd  call    cs:__imp_CoFreeUnusedLibrariesEx
0x14007dee4  nop     dword ptr [rax+rax+00h]
0x14007dee9  mov     ecx, ebx; dwErrCode
0x14007deeb  call    cs:__imp_SetLastError
0x14007def2  nop     dword ptr [rax+rax+00h]
0x14007def7  test    rsi, rsi
0x14007defa  jz      short loc_14007DF04
0x14007defc  mov     rcx, rsi; hToken
0x14007deff  call    ImpersonatePrinterClient
0x14007df04  cmp     dword ptr [rdi+58h], 0
0x14007df08  jl      short loc_14007DF21
0x14007df0a  lea     rcx, [rdi+28h]; lpCriticalSection
0x14007df0e  call    cs:__imp_DeleteCriticalSection
0x14007df15  nop     dword ptr [rax+rax+00h]
0x14007df1a  mov     dword ptr [rdi+58h], 80004005h
0x14007df21  mov     rbx, [rsp+28h+arg_0]
0x14007df26  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x14007df2d  mov     rsi, [rsp+28h+arg_8]
0x14007df32  mov     [rdi], rax
0x14007df35  add     rsp, 20h
0x14007df39  pop     rdi
0x14007df3a  retn
```
