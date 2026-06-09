# CVsServiceModule::ServiceMain(ulong,ushort * *)

- ea: `0x14004498c`
- end: `0x140044ca7`
- name: `?ServiceMain@CVsServiceModule@@IEAAXKPEAPEAG@Z`
- size: `795`
- prototype: `void __fastcall(CVsServiceModule *__hidden this, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140099340`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013b00`
- `0x140015e38`
- `0x14002a8ac`
- `0x140032fcc`
- `0x1400330fc`
- `0x1400347a0`
- `0x14004498c`
- `0x1400921dc`
- `0x1400f4010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044c54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044a3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044c0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044c54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140044aa1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140044aa1`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140044a30`
- `api-ms-win-core-processthreads-l1-1-1!SetProcessMitigationPolicy` at `0x140044a30`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140044ac8`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x140044ac8`

## string_xrefs

- `0x1400449b3`: `CVsServiceModule::ServiceMain`
- `0x140044c88`: `RegisterServiceCtrlHandlerEx failed. 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
void __fastcall CVsServiceModule::ServiceMain(CVsServiceModule *this, int a2, unsigned __int16 **a3)
{
  DWORD LastError; // ebx
  struct CVssDebugInfo *v4; // rbx
  int v5; // eax
  CVssDebugInfo *v6; // rax
  __int64 v7; // rax
  int v8; // r10d
  __int64 v9; // [rsp+20h] [rbp-218h]
  const unsigned __int16 *v10; // [rsp+48h] [rbp-1F0h] BYREF
  const unsigned __int16 *v11; // [rsp+50h] [rbp-1E8h]
  const unsigned __int16 *v12; // [rsp+58h] [rbp-1E0h]
  int v13; // [rsp+60h] [rbp-1D8h]
  int v14; // [rsp+64h] [rbp-1D4h]
  int v15; // [rsp+68h] [rbp-1D0h]
  _BYTE v16[120]; // [rsp+70h] [rbp-1C8h] BYREF
  int v17; // [rsp+E8h] [rbp-150h]
  LPVOID v18; // [rsp+F0h] [rbp-148h] BYREF
  __int64 v19; // [rsp+F8h] [rbp-140h]
  _BYTE v20[176]; // [rsp+170h] [rbp-C8h] BYREF
  int v21; // [rsp+248h] [rbp+10h] BYREF

  v21 = a2;
  v10 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v11 = L"CVsServiceModule::ServiceMain";
  v12 = L"CORSVCC";
  v13 = 325;
  v14 = 1;
  v15 = 255;
  v17 = 0x1000000;
  memset_0(v16, 0, sizeof(v16));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v18, (__int64)&v10, 0);
  v21 = 1;
  if ( !(unsigned int)SetProcessMitigationPolicy(16, &v21) )
  {
    LastError = GetLastError();
    v10 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
    v11 = L"CVsServiceModule::ServiceMain";
    v12 = L"CORSVCC";
    v13 = 332;
    v14 = 1;
    v15 = 255;
    v17 = 0x1000000;
    memset_0(v16, 0, sizeof(v16));
    CVssFunctionTracer::Trace(&v18, &v10, L"SetProcessMitigationPolicy failed with error %lu", LastError);
  }
  dwThreadId = GetCurrentThreadId();
  DWORD1(xmmword_14014F990) = 2;
  *(_QWORD *)&xmmword_14014F980 = RegisterServiceCtrlHandlerExW(
                                    L"VSS",
                                    (LPHANDLER_FUNCTION_EX)CVsServiceModule::_Handler,
                                    0);
  if ( !(_QWORD)xmmword_14014F980 )
  {
    v4 = (struct CVssDebugInfo *)CVssDebugInfo::CVssDebugInfo(
                                   v20,
                                   L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
                                   L"CORSVCC",
                                   L"CVsServiceModule::ServiceMain",
                                   346,
                                   1);
    v5 = GetLastError();
    if ( v5 > 0 )
      v5 = (unsigned __int16)v5 | 0x80070000;
    v6 = CVssDebugInfo::operator<<(v4, (CVssDebugInfo *)&v10, v5);
    CVssFunctionTracer::LogError((__int64)&v18, 2u, (__int64)v6, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v20);
    GetLastError();
    v7 = CVssDebugInfo::CVssDebugInfo(
           v20,
           L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
           L"CORSVCC",
           L"CVsServiceModule::ServiceMain",
           347,
           1);
    LODWORD(v9) = v8;
    CVssFunctionTracer::Throw(&v18, v7, 2147754754LL, L"RegisterServiceCtrlHandlerEx failed. 0x%08lx", v9);
  }
  CVsServiceModule::SetServiceStatus((CVsServiceModule *)&_Module, 2u, 1u);
  (*(void (__fastcall **)(void *))(_Module + 80LL))(&_Module);
  (*(void (__fastcall **)(void *))(_Module + 88LL))(&_Module);
  CVsServiceModule::SetServiceStatus((CVsServiceModule *)&_Module, 3u, 1u);
  (*(void (__fastcall **)(void *, char *))(_Module + 96LL))(&_Module, &byte_14014F9D0);
  CVsServiceModule::SetServiceStatus((CVsServiceModule *)&_Module, 1u, 1u);
  if ( (int)v19 < 0 )
  {
    HIDWORD(xmmword_14014F990) = 1066;
    dword_14014F9A0 = v19;
    (*(void (__fastcall **)(void *, char *))(_Module + 96LL))(&_Module, &byte_14014F9D0);
    CVsServiceModule::SetServiceStatus((CVsServiceModule *)&_Module, 1u, 0);
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v18);
}

```

## disassembly

```asm
0x14004498c  mov     rax, rsp
0x14004498f  mov     [rax+8], rbx
0x140044993  mov     [rax+20h], rdi
0x140044997  mov     [rax+10h], edx
0x14004499a  push    r12
0x14004499c  push    r14
0x14004499e  push    r15
0x1400449a0  sub     rsp, 220h
0x1400449a7  lea     r14, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x1400449ae  mov     [rsp+238h+var_1F0], r14
0x1400449b3  lea     r15, aCvsservicemodu_8; "CVsServiceModule::ServiceMain"
0x1400449ba  mov     [rsp+238h+var_1E8], r15
0x1400449bf  lea     r12, aCorsvcc; "CORSVCC"
0x1400449c6  mov     [rsp+238h+var_1E0], r12
0x1400449cb  mov     [rsp+238h+var_1D8], 145h
0x1400449d3  mov     [rsp+238h+var_1D4], 1
0x1400449db  mov     [rsp+238h+var_1D0], 0FFh
0x1400449e3  mov     dword ptr [rax-150h], 1000000h
0x1400449ed  xor     edx, edx; Val
0x1400449ef  lea     r8d, [rdx+78h]; Size
0x1400449f3  lea     rcx, [rsp+238h+var_1C8]; void *
0x1400449f8  call    memset_0
0x1400449fd  xor     r8d, r8d
0x140044a00  lea     rdx, [rsp+238h+var_1F0]
0x140044a05  lea     rcx, [rsp+238h+var_148]
0x140044a0d  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140044a12  nop
0x140044a13  mov     [rsp+238h+arg_8], 1
0x140044a1e  mov     r8d, 4
0x140044a24  lea     rdx, [rsp+238h+arg_8]
0x140044a2c  lea     ecx, [r8+0Ch]
0x140044a30  call    cs:__imp_SetProcessMitigationPolicy
0x140044a36  test    eax, eax
0x140044a38  jnz     short loc_140044AA1
0x140044a3a  call    cs:__imp_GetLastError
0x140044a40  mov     ebx, eax
0x140044a42  mov     [rsp+238h+var_1F0], r14
0x140044a47  mov     [rsp+238h+var_1E8], r15
0x140044a4c  mov     [rsp+238h+var_1E0], r12
0x140044a51  mov     [rsp+238h+var_1D8], 14Ch
0x140044a59  mov     [rsp+238h+var_1D4], 1
0x140044a61  mov     [rsp+238h+var_1D0], 0FFh
0x140044a69  mov     [rsp+238h+var_150], 1000000h
0x140044a74  xor     edx, edx; Val
0x140044a76  lea     r8d, [rdx+78h]; Size
0x140044a7a  lea     rcx, [rsp+238h+var_1C8]; void *
0x140044a7f  call    memset_0
0x140044a84  mov     r9d, ebx
0x140044a87  lea     r8, aSetprocessmiti; "SetProcessMitigationPolicy failed with "...
0x140044a8e  lea     rdx, [rsp+238h+var_1F0]
0x140044a93  lea     rcx, [rsp+238h+var_148]
0x140044a9b  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x140044aa0  nop
0x140044aa1  call    cs:__imp_GetCurrentThreadId
0x140044aa7  mov     cs:dwThreadId, eax
0x140044aad  mov     dword ptr cs:xmmword_14014F990+4, 2
0x140044ab7  xor     r8d, r8d; lpContext
0x140044aba  lea     rdx, ?_Handler@CVsServiceModule@@KAKKKPEAX0@Z; lpHandlerProc
0x140044ac1  lea     rcx, ServiceName; "VSS"
0x140044ac8  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140044ace  mov     qword ptr cs:xmmword_14014F980, rax
0x140044ad5  test    rax, rax
0x140044ad8  jz      loc_140044BE2
0x140044ade  mov     r8b, 1; bool
0x140044ae1  mov     edx, 2; unsigned int
0x140044ae6  lea     rcx, ?_Module@@3VCVsServiceModule@@A; this
0x140044aed  call    ?SetServiceStatus@CVsServiceModule@@IEAAXK_N@Z; CVsServiceModule::SetServiceStatus(ulong,bool)
0x140044af2  mov     rax, cs:?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044af9  lea     rcx, ?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b00  mov     rax, [rax+50h]
0x140044b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b09  mov     rax, cs:?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b10  lea     rcx, ?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b17  mov     rax, [rax+58h]
0x140044b1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b20  mov     r8b, 1; bool
0x140044b23  mov     edx, 3; unsigned int
0x140044b28  lea     rcx, ?_Module@@3VCVsServiceModule@@A; this
0x140044b2f  call    ?SetServiceStatus@CVsServiceModule@@IEAAXK_N@Z; CVsServiceModule::SetServiceStatus(ulong,bool)
0x140044b34  mov     rax, cs:?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b3b  lea     rdx, byte_14014F9D0
0x140044b42  lea     rcx, ?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b49  mov     rax, [rax+60h]
0x140044b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044b52  mov     r8b, 1; bool
0x140044b55  mov     edx, 1; unsigned int
0x140044b5a  lea     rcx, ?_Module@@3VCVsServiceModule@@A; this
0x140044b61  call    ?SetServiceStatus@CVsServiceModule@@IEAAXK_N@Z; CVsServiceModule::SetServiceStatus(ulong,bool)
0x140044b66  nop
0x140044b67  mov     rax, [rsp+238h+var_140]
0x140044b6f  test    eax, eax
0x140044b71  jns     short loc_140044BB5
0x140044b73  mov     dword ptr cs:xmmword_14014F990+0Ch, 42Ah
0x140044b7d  mov     cs:dword_14014F9A0, eax
0x140044b83  mov     rax, cs:?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b8a  lea     rdx, byte_14014F9D0
0x140044b91  lea     rcx, ?_Module@@3VCVsServiceModule@@A; CVsServiceModule _Module
0x140044b98  mov     rax, [rax+60h]
0x140044b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044ba1  xor     r8d, r8d; bool
0x140044ba4  lea     edx, [r8+1]; unsigned int
0x140044ba8  lea     rcx, ?_Module@@3VCVsServiceModule@@A; this
0x140044baf  call    ?SetServiceStatus@CVsServiceModule@@IEAAXK_N@Z; CVsServiceModule::SetServiceStatus(ulong,bool)
0x140044bb4  nop
0x140044bb5  lea     rcx, [rsp+238h+var_148]; this
0x140044bbd  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140044bc2  lea     r11, [rsp+238h+var_18]
0x140044bca  mov     rbx, [r11+20h]
0x140044bce  mov     rdi, [r11+38h]
0x140044bd2  mov     rsp, r11
0x140044bd5  pop     r15
0x140044bd7  pop     r14
0x140044bd9  pop     r12
0x140044bdb  retn
0x140044bdc  jmp     short loc_140044B67
0x140044bde  jmp     short loc_140044B67
0x140044be0  jmp     short loc_140044B67
0x140044be2  mov     [rsp+238h+var_210], 1
0x140044bea  mov     dword ptr [rsp+238h+var_218], 15Ah
0x140044bf2  mov     r9, r15
0x140044bf5  mov     r8, r12
0x140044bf8  mov     rdx, r14
0x140044bfb  lea     rcx, [rsp+238h+var_C8]
0x140044c03  call    ??0CVssDebugInfo@@QEAA@PEBG00KKW4_VSSDBG_SEV_ENUM@@@Z; CVssDebugInfo::CVssDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_VSSDBG_SEV_ENUM)
0x140044c08  mov     rbx, rax
0x140044c0b  call    cs:__imp_GetLastError
0x140044c11  test    eax, eax
0x140044c13  jle     short loc_140044C1D
0x140044c15  movzx   eax, ax
0x140044c18  or      eax, 80070000h
0x140044c1d  mov     r8d, eax; dwMessageId
0x140044c20  lea     rdx, [rsp+238h+var_1F0]; this
0x140044c25  mov     rcx, rbx; struct CVssDebugInfo *
0x140044c28  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x140044c2d  mov     r9d, 1
0x140044c33  mov     r8, rax
0x140044c36  lea     edx, [r9+1]
0x140044c3a  lea     rcx, [rsp+238h+var_148]
0x140044c42  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x140044c47  lea     rcx, [rsp+238h+var_C8]; this
0x140044c4f  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x140044c54  call    cs:__imp_GetLastError
0x140044c5a  mov     r10d, eax
0x140044c5d  mov     [rsp+238h+var_210], 1
0x140044c65  mov     dword ptr [rsp+238h+var_218], 15Bh
0x140044c6d  mov     r9, r15
0x140044c70  mov     r8, r12
0x140044c73  mov     rdx, r14
0x140044c76  lea     rcx, [rsp+238h+var_C8]
0x140044c7e  call    ??0CVssDebugInfo@@QEAA@PEBG00KKW4_VSSDBG_SEV_ENUM@@@Z; CVssDebugInfo::CVssDebugInfo(ushort const *,ushort const *,ushort const *,ulong,ulong,_VSSDBG_SEV_ENUM)
0x140044c83  mov     dword ptr [rsp+238h+var_218], r10d
0x140044c88  lea     r9, aRegisterservic_0; "RegisterServiceCtrlHandlerEx failed. 0x"...
0x140044c8f  mov     r8d, 80042302h
0x140044c95  mov     rdx, rax
0x140044c98  lea     rcx, [rsp+238h+var_148]
0x140044ca0  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
