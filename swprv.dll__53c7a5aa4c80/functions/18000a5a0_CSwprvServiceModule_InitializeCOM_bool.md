# CSwprvServiceModule::InitializeCOM(bool)

- ea: `0x18000a5a0`
- end: `0x18000a6bd`
- name: `?InitializeCOM@CSwprvServiceModule@@QEAAX_N@Z`
- size: `285`
- prototype: `void __fastcall(CSwprvServiceModule *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000aa5c`

## callees

- `0x18000212c`
- `0x18000a5a0`
- `0x180033a8c`
- `0x180033c78`
- `0x180037080`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a61f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a61f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a62f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000a62f`

## string_xrefs

- `0x18000a5c6`: `CSwprvServiceModule::InitializeCOM`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall CSwprvServiceModule::InitializeCOM(CSwprvServiceModule *this)
{
  HRESULT v1; // ebx
  const unsigned __int16 *v2; // [rsp+20h] [rbp-E0h] BYREF
  const wchar_t *v3; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v4; // [rsp+30h] [rbp-D0h]
  int v5; // [rsp+38h] [rbp-C8h]
  int v6; // [rsp+3Ch] [rbp-C4h]
  int v7; // [rsp+40h] [rbp-C0h]
  _BYTE v8[120]; // [rsp+48h] [rbp-B8h] BYREF
  int v9; // [rsp+C0h] [rbp-40h]
  LPVOID v10; // [rsp+D0h] [rbp-30h] BYREF
  HRESULT v11; // [rsp+D8h] [rbp-28h]

  v2 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v3 = L"CSwprvServiceModule::InitializeCOM";
  v4 = L"SPRSWPRC";
  v5 = 218;
  v6 = 2;
  v7 = 255;
  v9 = 0x1000000;
  memset_0(v8, 0, sizeof(v8));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v10, (__int64)&v2, 0);
  dword_18006B474 = GetCurrentThreadId();
  v1 = CoInitializeEx(0, 0);
  v11 = v1;
  if ( v1 < 0 )
  {
    v2 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
    v3 = L"CSwprvServiceModule::InitializeCOM";
    v4 = L"SPRSWPRC";
    v5 = 231;
    v6 = 2;
    v7 = 255;
    v9 = 0x1000000;
    memset_0(v8, 0, sizeof(v8));
    CVssFunctionTracer::TranslateGenericError(&v10, &v2, (unsigned int)v1, L"CoInitializeEx");
  }
  byte_18006B479 = 1;
  CVssFunctionTracer::~CVssFunctionTracer(&v10);
}

```

## disassembly

```asm
0x18000a5a0  mov     [rsp-8+arg_8], rbx
0x18000a5a5  mov     [rsp-8+arg_10], rsi
0x18000a5aa  push    rbp
0x18000a5ab  push    rdi
0x18000a5ac  push    r14
0x18000a5ae  lea     rbp, [rsp-40h]
0x18000a5b3  sub     rsp, 140h
0x18000a5ba  lea     rdi, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000a5c1  mov     [rsp+150h+var_130], rdi
0x18000a5c6  lea     rsi, aCswprvservicem_9; "CSwprvServiceModule::InitializeCOM"
0x18000a5cd  mov     [rsp+150h+var_128], rsi
0x18000a5d2  lea     r14, aSprswprc; "SPRSWPRC"
0x18000a5d9  mov     [rsp+150h+var_120], r14
0x18000a5de  mov     [rsp+150h+var_118], 0DAh
0x18000a5e6  mov     [rsp+150h+var_114], 2
0x18000a5ee  mov     [rsp+150h+var_110], 0FFh
0x18000a5f6  mov     [rbp+50h+var_90], 1000000h
0x18000a5fd  xor     edx, edx; Val
0x18000a5ff  lea     r8d, [rdx+78h]; Size
0x18000a603  lea     rcx, [rsp+150h+var_108]; void *
0x18000a608  call    memset_0
0x18000a60d  xor     r8d, r8d
0x18000a610  lea     rdx, [rsp+150h+var_130]
0x18000a615  lea     rcx, [rbp+50h+var_80]
0x18000a619  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000a61e  nop
0x18000a61f  call    cs:__imp_GetCurrentThreadId
0x18000a625  mov     cs:dword_18006B474, eax
0x18000a62b  xor     edx, edx; dwCoInit
0x18000a62d  xor     ecx, ecx; pvReserved
0x18000a62f  call    cs:__imp_CoInitializeEx
0x18000a635  mov     ebx, eax
0x18000a637  mov     [rbp+50h+var_78], eax
0x18000a63a  test    eax, eax
0x18000a63c  js      short loc_18000A666
0x18000a63e  mov     cs:byte_18006B479, 1
0x18000a645  lea     rcx, [rbp+50h+var_80]; this
0x18000a649  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000a64e  lea     r11, [rsp+150h+var_10]
0x18000a656  mov     rbx, [r11+28h]
0x18000a65a  mov     rsi, [r11+30h]
0x18000a65e  mov     rsp, r11
0x18000a661  pop     r14
0x18000a663  pop     rdi
0x18000a664  pop     rbp
0x18000a665  retn
0x18000a666  mov     [rsp+150h+var_130], rdi
0x18000a66b  mov     [rsp+150h+var_128], rsi
0x18000a670  mov     [rsp+150h+var_120], r14
0x18000a675  mov     [rsp+150h+var_118], 0E7h
0x18000a67d  mov     [rsp+150h+var_114], 2
0x18000a685  mov     [rsp+150h+var_110], 0FFh
0x18000a68d  mov     [rbp+50h+var_90], 1000000h
0x18000a694  xor     edx, edx; Val
0x18000a696  lea     r8d, [rdx+78h]; Size
0x18000a69a  lea     rcx, [rsp+150h+var_108]; void *
0x18000a69f  call    memset_0
0x18000a6a4  lea     r9, aCoinitializeex_0; "CoInitializeEx"
0x18000a6ab  mov     r8d, ebx
0x18000a6ae  lea     rdx, [rsp+150h+var_130]
0x18000a6b3  lea     rcx, [rbp+50h+var_80]
0x18000a6b7  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
```
