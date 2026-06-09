# CSwprvServiceModule::OnSignalShutdown(void)

- ea: `0x18000b270`
- end: `0x18000b43f`
- name: `?OnSignalShutdown@CSwprvServiceModule@@IEAAXXZ`
- size: `463`
- prototype: `void __fastcall(CSwprvServiceModule *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a378`

## callees

- `0x18000212c`
- `0x18000b270`
- `0x180033a8c`
- `0x180033c78`
- `0x1800367b8`
- `0x1800377c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000b390`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18000b390`

## string_xrefs

- `0x18000b297`: `CSwprvServiceModule::OnSignalShutdown`
- `0x18000b33d`: `SWPRV: Trying to shutdown the service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSwprvServiceModule::OnSignalShutdown(CSwprvServiceModule *this)
{
  unsigned int *v1; // rdx
  _BYTE *v2; // rdx
  _BYTE *v3; // rdx
  _BYTE *v4; // rdx
  _BYTE v5[32]; // [rsp+0h] [rbp-188h] BYREF
  __int64 v6; // [rsp+40h] [rbp-148h] BYREF
  const unsigned __int16 *v7; // [rsp+48h] [rbp-140h] BYREF
  const unsigned __int16 *v8; // [rsp+50h] [rbp-138h]
  const unsigned __int16 *v9; // [rsp+58h] [rbp-130h]
  int v10; // [rsp+60h] [rbp-128h]
  int v11; // [rsp+64h] [rbp-124h]
  int v12; // [rsp+68h] [rbp-120h]
  _BYTE v13[120]; // [rsp+70h] [rbp-118h] BYREF
  int v14; // [rsp+E8h] [rbp-A0h]
  const std::exception *v15; // [rsp+F0h] [rbp-98h] BYREF
  _com_error *v16; // [rsp+F8h] [rbp-90h] BYREF
  LPVOID v17; // [rsp+100h] [rbp-88h] BYREF
  __int64 v18; // [rsp+108h] [rbp-80h]
  LARGE_INTEGER DueTime; // [rsp+190h] [rbp+8h] BYREF

  DueTime.QuadPart = (LONGLONG)this;
  v7 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v8 = L"CSwprvServiceModule::OnSignalShutdown";
  v9 = L"SPRSWPRC";
  v10 = 661;
  v11 = 2;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v17, (__int64)&v7, 0);
  v7 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
  v8 = L"CSwprvServiceModule::OnSignalShutdown";
  v9 = L"SPRSWPRC";
  v10 = 666;
  v11 = 2;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CVssFunctionTracer::Trace(&v17, &v7, L"SWPRV: Trying to shutdown the service");
  if ( hTimer )
  {
    DueTime.QuadPart = -1;
    byte_18006B478 = 1;
    if ( !SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0) )
    {
      v7 = L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx";
      v8 = L"CSwprvServiceModule::OnSignalShutdown";
      v9 = L"SPRSWPRC";
      v10 = 677;
      v11 = 2;
      v12 = 255;
      v14 = 0x1000000;
      memset_0(v13, 0, sizeof(v13));
      try
      {
        CVssFunctionTracer::TranslateWin32Error(&v17, &v7, L"SetWaitableTimer");
      }
      catch ( long v6 )
      {
        v1 = (unsigned int *)v5;
        CVssFunctionTracer::HandleHresultException(
          (CVssFunctionTracer *)(v1 + 64),
          v1[16],
          L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
          L"SPRSWPRC",
          L"CSwprvServiceModule::OnSignalShutdown",
          0x2AAu,
          v1[73]);
      }
      catch ( _com_error *v16 )
      {
        v2 = v5;
        CVssFunctionTracer::HandleComException(
          (CVssFunctionTracer *)(v2 + 256),
          *((struct _com_error **)v2 + 31),
          L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
          L"SPRSWPRC",
          L"CSwprvServiceModule::OnSignalShutdown",
          0x2AAu,
          *((_DWORD *)v2 + 73));
      }
      catch ( std::bad_alloc )
      {
        v3 = v5;
        CVssFunctionTracer::HandleStdBadAllocException(
          (CVssFunctionTracer *)(v3 + 256),
          L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
          L"SPRSWPRC",
          L"CSwprvServiceModule::OnSignalShutdown",
          0x2AAu,
          *((_DWORD *)v3 + 73));
      }
      catch ( const std::exception *v15 )
      {
        v4 = v5;
        CVssFunctionTracer::HandleStdGenericException(
          (CVssFunctionTracer *)(v4 + 256),
          *((const struct std::exception **)v4 + 30),
          L"base\\stor\\vss\\modules\\softprv\\src\\swprv.cxx",
          L"SPRSWPRC",
          L"CSwprvServiceModule::OnSignalShutdown",
          0x2AAu,
          *((_DWORD *)v4 + 73));
      }
    }
  }
  if ( (int)v18 < 0 )
  {
    ServiceStatus.dwWin32ExitCode = 1066;
    ServiceStatus.dwServiceSpecificExitCode = v18;
  }
  CVssFunctionTracer::~CVssFunctionTracer(&v17);
}

```

## disassembly

```asm
0x18000b270  mov     rax, rsp
0x18000b273  mov     [rax+18h], rbx
0x18000b277  mov     [rax+20h], rsi
0x18000b27b  mov     [rax+8], rcx
0x18000b27f  push    rdi
0x18000b280  push    r13
0x18000b282  push    r14
0x18000b284  sub     rsp, 170h
0x18000b28b  lea     rdi, aBaseStorVssMod_15; "base\\stor\\vss\\modules\\softprv\\src"...
0x18000b292  mov     [rsp+188h+var_140], rdi
0x18000b297  lea     rsi, aCswprvservicem_2; "CSwprvServiceModule::OnSignalShutdown"
0x18000b29e  mov     [rsp+188h+var_138], rsi
0x18000b2a3  lea     r14, aSprswprc; "SPRSWPRC"
0x18000b2aa  mov     [rsp+188h+var_130], r14
0x18000b2af  mov     [rsp+188h+var_128], 295h
0x18000b2b7  mov     [rsp+188h+var_124], 2
0x18000b2bf  mov     [rsp+188h+var_120], 0FFh
0x18000b2c7  xor     ebx, ebx
0x18000b2c9  mov     dword ptr [rax-0A0h], 1000000h
0x18000b2d3  lea     r13d, [rbx+78h]
0x18000b2d7  mov     r8d, r13d; Size
0x18000b2da  xor     edx, edx; Val
0x18000b2dc  lea     rcx, [rsp+188h+var_118]; void *
0x18000b2e1  call    memset_0
0x18000b2e6  xor     r8d, r8d
0x18000b2e9  lea     rdx, [rsp+188h+var_140]
0x18000b2ee  lea     rcx, [rsp+188h+var_88]
0x18000b2f6  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x18000b2fb  nop
0x18000b2fc  mov     [rsp+188h+var_140], rdi
0x18000b301  mov     [rsp+188h+var_138], rsi
0x18000b306  mov     [rsp+188h+var_130], r14
0x18000b30b  mov     [rsp+188h+var_128], 29Ah
0x18000b313  mov     [rsp+188h+var_124], 2
0x18000b31b  mov     [rsp+188h+var_120], 0FFh
0x18000b323  mov     [rsp+188h+var_A0], 1000000h
0x18000b32e  mov     r8d, r13d; Size
0x18000b331  xor     edx, edx; Val
0x18000b333  lea     rcx, [rsp+188h+var_118]; void *
0x18000b338  call    memset_0
0x18000b33d  lea     r8, aSwprvTryingToS; "SWPRV: Trying to shutdown the service"
0x18000b344  lea     rdx, [rsp+188h+var_140]
0x18000b349  lea     rcx, [rsp+188h+var_88]
0x18000b351  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x18000b356  mov     rcx, cs:hTimer; hTimer
0x18000b35d  test    rcx, rcx
0x18000b360  jz      loc_18000B3F5
0x18000b366  mov     qword ptr [rsp+188h+DueTime], 0FFFFFFFFFFFFFFFFh
0x18000b372  mov     cs:byte_18006B478, 1
0x18000b379  mov     [rsp+188h+fResume], ebx; fResume
0x18000b37d  mov     [rsp+188h+lpArgToCompletionRoutine], rbx; lpArgToCompletionRoutine
0x18000b382  xor     r9d, r9d; pfnCompletionRoutine
0x18000b385  xor     r8d, r8d; lPeriod
0x18000b388  lea     rdx, [rsp+188h+DueTime]; lpDueTime
0x18000b390  call    cs:__imp_SetWaitableTimer
0x18000b396  test    eax, eax
0x18000b398  jnz     short loc_18000B3F5
0x18000b39a  mov     [rsp+188h+var_140], rdi
0x18000b39f  mov     [rsp+188h+var_138], rsi
0x18000b3a4  mov     [rsp+188h+var_130], r14
0x18000b3a9  mov     [rsp+188h+var_128], 2A5h
0x18000b3b1  mov     [rsp+188h+var_124], 2
0x18000b3b9  mov     [rsp+188h+var_120], 0FFh
0x18000b3c1  mov     [rsp+188h+var_A0], 1000000h
0x18000b3cc  mov     r8d, r13d; Size
0x18000b3cf  xor     edx, edx; Val
0x18000b3d1  lea     rcx, [rsp+188h+var_118]; void *
0x18000b3d6  call    memset_0
0x18000b3db  lea     r8, aSetwaitabletim_1; "SetWaitableTimer"
0x18000b3e2  lea     rdx, [rsp+188h+var_140]
0x18000b3e7  lea     rcx, [rsp+188h+var_88]
0x18000b3ef  call    ?TranslateWin32Error@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGZZ; CVssFunctionTracer::TranslateWin32Error(CVssDebugInfo,ushort const *,...)
0x18000b3f5  jmp     short loc_18000B3FD
0x18000b3f7  jmp     short loc_18000B3FD
0x18000b3f9  jmp     short loc_18000B3FD
0x18000b3fb  jmp     short $+2
0x18000b3fd  mov     rax, [rsp+188h+var_80]
0x18000b405  test    eax, eax
0x18000b407  jns     short loc_18000B419
0x18000b409  mov     cs:ServiceStatus.dwWin32ExitCode, 42Ah
0x18000b413  mov     cs:ServiceStatus.dwServiceSpecificExitCode, eax
0x18000b419  lea     rcx, [rsp+188h+var_88]; this
0x18000b421  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x18000b426  lea     r11, [rsp+188h+var_18]
0x18000b42e  mov     rbx, [r11+30h]
0x18000b432  mov     rsi, [r11+38h]
0x18000b436  mov     rsp, r11
0x18000b439  pop     r14
0x18000b43b  pop     r13
0x18000b43d  pop     rdi
0x18000b43e  retn
```
