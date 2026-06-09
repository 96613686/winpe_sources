# PrinterPLM::~PrinterPLM(void)

- ea: `0x140076bf8`
- end: `0x140076c97`
- name: `??1PrinterPLM@@UEAA@XZ`
- size: `159`
- prototype: `void __fastcall(PrinterPLM *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140076ca0`

## callees

- `0x14000e590`
- `0x14001488c`
- `0x140014eb0`
- `0x140076bf8`
- `0x140076ea0`
- `0x14007740c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140076c70`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140076c70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076c2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140076c2f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140076c53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140076c53`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x140076c4b`
- `api-ms-win-core-com-l1-1-0!CoFreeUnusedLibrariesEx` at `0x140076c4b`

## string_xrefs

- `0x140076c14`: `Delete PLM object`

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
0x140076bf8  mov     [rsp+arg_0], rbx
0x140076bfd  mov     [rsp+arg_8], rsi
0x140076c02  push    rdi
0x140076c03  sub     rsp, 20h
0x140076c07  lea     rax, ??_7PrinterPLM@@6B@; const PrinterPLM::`vftable'
0x140076c0e  mov     rdi, rcx
0x140076c11  mov     [rcx], rax
0x140076c14  lea     rdx, aDeletePlmObjec; "Delete PLM object"
0x140076c1b  lea     rcx, aPrinterplmPrin; "PrinterPLM::~PrinterPLM"
0x140076c22  call    ?WriteDbgTraceInfo@PrintPLMTelemetry@@SAXPEADPEAGZZ; PrintPLMTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x140076c27  call    RevertToPrinterSelf
0x140076c2c  mov     rsi, rax
0x140076c2f  call    cs:__imp_GetLastError
0x140076c35  mov     rcx, rdi; this
0x140076c38  mov     ebx, eax
0x140076c3a  call    ?EndExemption@PrinterPLM@@AEAAXXZ; PrinterPLM::EndExemption(void)
0x140076c3f  mov     rcx, rdi; this
0x140076c42  call    ?StopTimer@PrinterPLM@@AEAAXXZ; PrinterPLM::StopTimer(void)
0x140076c47  xor     edx, edx; dwReserved
0x140076c49  xor     ecx, ecx; dwUnloadDelay
0x140076c4b  call    cs:__imp_CoFreeUnusedLibrariesEx
0x140076c51  mov     ecx, ebx; dwErrCode
0x140076c53  call    cs:__imp_SetLastError
0x140076c59  test    rsi, rsi
0x140076c5c  jz      short loc_140076C66
0x140076c5e  mov     rcx, rsi; hToken
0x140076c61  call    ImpersonatePrinterClient
0x140076c66  cmp     dword ptr [rdi+58h], 0
0x140076c6a  jl      short loc_140076C7D
0x140076c6c  lea     rcx, [rdi+28h]; lpCriticalSection
0x140076c70  call    cs:__imp_DeleteCriticalSection
0x140076c76  mov     dword ptr [rdi+58h], 80004005h
0x140076c7d  mov     rbx, [rsp+28h+arg_0]
0x140076c82  lea     rax, ??_7TReferenceCount@NCoreLibrary@@6B@; const NCoreLibrary::TReferenceCount::`vftable'
0x140076c89  mov     rsi, [rsp+28h+arg_8]
0x140076c8e  mov     [rdi], rax
0x140076c91  add     rsp, 20h
0x140076c95  pop     rdi
0x140076c96  retn
```
