# CVsServiceModule::SetServiceStatus(ulong,bool)

- ea: `0x14002a8ac`
- end: `0x14002ad2b`
- name: `?SetServiceStatus@CVsServiceModule@@IEAAXK_N@Z`
- size: `1151`
- prototype: `void __fastcall(CVsServiceModule *__hidden this, unsigned int, bool)`
- caller_count: `3`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x140028d60`
- `0x14003ef20`
- `0x14004498c`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002a8ac`
- `0x140032fcc`
- `0x1400330fc`
- `0x140046aa0`
- `0x14005632c`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ab91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002abe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002abf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ab91`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002abe7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002abf0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002a96d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002a96d`
- `VssTrace!__imp_VssTraceMessage` at `0x14002aa8f`
- `VssTrace!__imp_VssTraceMessage` at `0x14002aa8f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002a9d4`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002a9d4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002a9c2`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002a9c2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002aaab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002aaab`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14002ab29`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14002ab29`

## string_xrefs

- `0x14002ab04`: `Attempt to change the service status to %lu`
- `0x14002a8dd`: `CVsServiceModule::SetServiceStatus`
- `0x14002ac78`: `CVsServiceModule::SetServiceStatus`
- `0x14002ac4c`: `Error on calling SetServiceStatus. 0x%08lx`
- `0x14002acdf`: `Error on calling SetServiceStatus. 0x%08lx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVsServiceModule::SetServiceStatus(CVsServiceModule *this, unsigned int a2, unsigned __int8 a3)
{
  int v5; // eax
  __int64 v6; // rcx
  int v7; // edi
  __int64 i; // rdi
  void *v9; // rcx
  struct CVssDebugInfo *v10; // rdi
  int LastError; // eax
  CVssDebugInfo *v12; // rax
  DWORD v13; // r12d
  signed int v14; // eax
  unsigned int v15; // edi
  unsigned int v16; // edi
  _BYTE *v17; // rdx
  _BYTE *v18; // rdx
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  _BYTE v21[32]; // [rsp+0h] [rbp-308h] BYREF
  __int64 v22; // [rsp+20h] [rbp-2E8h]
  __int64 v23; // [rsp+28h] [rbp-2E0h]
  const unsigned __int16 *v24; // [rsp+50h] [rbp-2B8h] BYREF
  const unsigned __int16 *v25; // [rsp+58h] [rbp-2B0h]
  const unsigned __int16 *v26; // [rsp+60h] [rbp-2A8h]
  int v27; // [rsp+68h] [rbp-2A0h]
  int v28; // [rsp+6Ch] [rbp-29Ch]
  int v29; // [rsp+70h] [rbp-298h]
  LPVOID pv[15]; // [rsp+78h] [rbp-290h] BYREF
  int v31; // [rsp+F0h] [rbp-218h]
  unsigned __int64 v32; // [rsp+100h] [rbp-208h] BYREF
  int v33; // [rsp+108h] [rbp-200h]
  const unsigned __int16 *v34; // [rsp+110h] [rbp-1F8h]
  const unsigned __int16 *v35; // [rsp+118h] [rbp-1F0h]
  unsigned int v36; // [rsp+120h] [rbp-1E8h]
  int v37; // [rsp+124h] [rbp-1E4h]
  const unsigned __int16 *v38; // [rsp+128h] [rbp-1E0h]
  unsigned int v39; // [rsp+130h] [rbp-1D8h]
  DWORD TickCount; // [rsp+134h] [rbp-1D4h]
  int v41; // [rsp+138h] [rbp-1D0h]
  __int128 v42; // [rsp+140h] [rbp-1C8h]
  __int128 v43; // [rsp+150h] [rbp-1B8h]
  __int64 v44; // [rsp+160h] [rbp-1A8h]
  __int64 v45; // [rsp+170h] [rbp-198h] BYREF
  const std::exception *v46; // [rsp+178h] [rbp-190h] BYREF
  _com_error *v47; // [rsp+180h] [rbp-188h] BYREF
  _BYTE v48[168]; // [rsp+188h] [rbp-180h] BYREF
  _BYTE v49[176]; // [rsp+230h] [rbp-D8h] BYREF
  __int64 v50; // [rsp+310h] [rbp+8h] BYREF
  unsigned __int8 v51; // [rsp+320h] [rbp+18h]

  v51 = a3;
  v24 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v25 = L"CVsServiceModule::SetServiceStatus";
  v26 = L"CORSVCC";
  v27 = 481;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  v33 = 0;
  v38 = L"CVsServiceModule::SetServiceStatus";
  v34 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v35 = L"CORSVCC";
  v36 = 481;
  v37 = 1;
  TickCount = GetTickCount();
  v41 = 255;
  v32 = 0xFFFFFFFF00000000uLL;
  v44 = 0;
  v42 = 0;
  v43 = 0;
  v50 = 0;
  if ( (int)VssGetTracingContextPerThread(&v50) < 0 )
  {
    v6 = v44;
  }
  else
  {
    v5 = VssSetTracingContextPerThread(&v32);
    v6 = v44;
    if ( v5 >= 0 )
      v6 = v50;
    v44 = v6;
  }
  if ( v6 )
    v39 = *(_DWORD *)(v6 + 48) + 1;
  else
    v39 = 0;
  v7 = 160;
  if ( v41 != 255 )
    v7 = v41;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v32) )
    VssTraceMessage(v34, v35, v36, v39, v37, v38, L"ENTER", v7, 0);
  if ( HIBYTE(v31) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v9 = pv[i];
      if ( v9 )
      {
        CoTaskMemFree(v9);
        pv[i] = 0;
      }
    }
  }
  v24 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
  v25 = L"CVsServiceModule::SetServiceStatus";
  v26 = L"CORSVCC";
  v27 = 485;
  v28 = 1;
  v29 = 255;
  v31 = 0x1000000;
  memset_0(pv, 0, sizeof(pv));
  CVssFunctionTracer::Trace(&v32, &v24, L"Attempt to change the service status to %lu", a2);
  *((_DWORD *)this + 25) = a2;
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 10), (LPSERVICE_STATUS)((char *)this + 96)) )
  {
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
    v25 = L"CVsServiceModule::SetServiceStatus";
    v26 = L"CORSVCC";
    v27 = 492;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    v10 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v24, (CVssDebugInfo *)v49);
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v12 = CVssDebugInfo::operator<<(v10, (CVssDebugInfo *)v48, LastError);
    CVssFunctionTracer::LogError((__int64)&v32, 8u, (__int64)v12, 1u);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v49);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v24);
    v13 = GetLastError();
    v14 = GetLastError();
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
    v25 = L"CVsServiceModule::SetServiceStatus";
    v26 = L"CORSVCC";
    v27 = 493;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    try
    {
      LODWORD(v22) = v13;
      CVssFunctionTracer::Throw(&v32, &v24, v15, L"Error on calling SetServiceStatus. 0x%08lx", v22);
    }
    catch ( long v45 )
    {
      v17 = v21;
      CVssFunctionTracer::HandleHresultException(
        (CVssFunctionTracer *)(v17 + 256),
        *((_DWORD *)v17 + 92),
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::SetServiceStatus",
        0x1F1u,
        *((_DWORD *)v17 + 73));
    }
    catch ( _com_error *v47 )
    {
      v18 = v21;
      CVssFunctionTracer::HandleComException(
        (CVssFunctionTracer *)(v18 + 256),
        *((struct _com_error **)v18 + 48),
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::SetServiceStatus",
        0x1F1u,
        *((_DWORD *)v18 + 73));
    }
    catch ( std::bad_alloc )
    {
      v19 = v21;
      CVssFunctionTracer::HandleStdBadAllocException(
        (CVssFunctionTracer *)(v19 + 256),
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::SetServiceStatus",
        0x1F1u,
        *((_DWORD *)v19 + 73));
    }
    catch ( const std::exception *v46 )
    {
      v20 = v21;
      CVssFunctionTracer::HandleStdGenericException(
        (CVssFunctionTracer *)(v20 + 256),
        *((const struct std::exception **)v20 + 47),
        L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx",
        L"CORSVCC",
        L"CVsServiceModule::SetServiceStatus",
        0x1F1u,
        *((_DWORD *)v20 + 73));
    }
  }
  v16 = v33;
  if ( v33 < 0 )
  {
    v24 = L"base\\stor\\vss\\modules\\coord\\src\\svc.cxx";
    v25 = L"CVsServiceModule::SetServiceStatus";
    v26 = L"CORSVCC";
    v27 = 500;
    v28 = 1;
    v29 = 255;
    v31 = 0x1000000;
    memset_0(pv, 0, sizeof(pv));
    LODWORD(v23) = v16;
    CVssFunctionTracer::ThrowIf(&v32, v51, &v24, v16, L"Error on calling SetServiceStatus. 0x%08lx", v23);
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v32);
}

```

## disassembly

```asm
0x14002a8ac  mov     rax, rsp
0x14002a8af  mov     [rax+10h], rbx
0x14002a8b3  mov     [rax+20h], rsi
0x14002a8b7  mov     [rax+18h], r8b
0x14002a8bb  push    rdi
0x14002a8bc  push    r12
0x14002a8be  push    r13
0x14002a8c0  push    r14
0x14002a8c2  push    r15
0x14002a8c4  sub     rsp, 2E0h
0x14002a8cb  mov     r12d, edx
0x14002a8ce  mov     r13, rcx
0x14002a8d1  lea     rsi, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14002a8d8  mov     [rsp+308h+var_2B8], rsi
0x14002a8dd  lea     r14, aCvsservicemodu_0; "CVsServiceModule::SetServiceStatus"
0x14002a8e4  mov     [rsp+308h+var_2B0], r14
0x14002a8e9  lea     r15, aCorsvcc; "CORSVCC"
0x14002a8f0  mov     [rsp+308h+var_2A8], r15
0x14002a8f5  mov     [rsp+308h+var_2A0], 1E1h
0x14002a8fd  mov     [rsp+308h+var_29C], 1
0x14002a905  mov     [rsp+308h+var_298], 0FFh
0x14002a90d  xor     ebx, ebx
0x14002a90f  mov     dword ptr [rax-218h], 1000000h
0x14002a919  xor     edx, edx; Val
0x14002a91b  lea     r8d, [rbx+78h]; Size
0x14002a91f  lea     rcx, [rsp+308h+pv]; void *
0x14002a924  call    memset_0
0x14002a929  mov     [rsp+308h+var_200], ebx
0x14002a930  mov     rax, [rsp+308h+var_2B0]
0x14002a935  mov     [rsp+308h+var_1E0], rax
0x14002a93d  mov     rax, [rsp+308h+var_2B8]
0x14002a942  mov     [rsp+308h+var_1F8], rax
0x14002a94a  mov     rax, [rsp+308h+var_2A8]
0x14002a94f  mov     [rsp+308h+var_1F0], rax
0x14002a957  mov     eax, [rsp+308h+var_2A0]
0x14002a95b  mov     [rsp+308h+var_1E8], eax
0x14002a962  mov     eax, [rsp+308h+var_29C]
0x14002a966  mov     [rsp+308h+var_1E4], eax
0x14002a96d  call    cs:__imp_GetTickCount
0x14002a973  mov     [rsp+308h+var_1D4], eax
0x14002a97a  mov     [rsp+308h+var_204], 0FFFFFFFFh
0x14002a985  mov     eax, [rsp+308h+var_298]
0x14002a989  mov     [rsp+308h+var_1D0], eax
0x14002a990  mov     [rsp+308h+var_208], ebx
0x14002a997  mov     [rsp+308h+var_1A8], rbx
0x14002a99f  xorps   xmm0, xmm0
0x14002a9a2  movups  [rsp+308h+var_1C8], xmm0
0x14002a9aa  movups  [rsp+308h+var_1B8], xmm0
0x14002a9b2  mov     [rsp+308h+arg_0], rbx
0x14002a9ba  lea     rcx, [rsp+308h+arg_0]
0x14002a9c2  call    cs:__imp_VssGetTracingContextPerThread
0x14002a9c8  test    eax, eax
0x14002a9ca  js      short loc_14002A9F7
0x14002a9cc  lea     rcx, [rsp+308h+var_208]
0x14002a9d4  call    cs:__imp_VssSetTracingContextPerThread
0x14002a9da  mov     rcx, [rsp+308h+var_1A8]
0x14002a9e2  test    eax, eax
0x14002a9e4  cmovns  rcx, [rsp+308h+arg_0]
0x14002a9ed  mov     [rsp+308h+var_1A8], rcx
0x14002a9f5  jmp     short loc_14002A9FF
0x14002a9f7  mov     rcx, [rsp+308h+var_1A8]
0x14002a9ff  test    rcx, rcx
0x14002aa02  jz      short loc_14002AA12
0x14002aa04  mov     eax, [rcx+30h]
0x14002aa07  inc     eax
0x14002aa09  mov     [rsp+308h+var_1D8], eax
0x14002aa10  jmp     short loc_14002AA19
0x14002aa12  mov     [rsp+308h+var_1D8], ebx
0x14002aa19  mov     edi, 0A0h
0x14002aa1e  cmp     [rsp+308h+var_1D0], 0FFh
0x14002aa29  cmovnz  edi, [rsp+308h+var_1D0]
0x14002aa31  lea     rcx, [rsp+308h+var_208]; this
0x14002aa39  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002aa3e  test    eax, eax
0x14002aa40  jz      short loc_14002AA95
0x14002aa42  mov     [rsp+308h+var_2C8], rbx
0x14002aa47  mov     [rsp+308h+var_2D0], edi
0x14002aa4b  lea     rax, aEnter; "ENTER"
0x14002aa52  mov     [rsp+308h+var_2D8], rax
0x14002aa57  mov     rax, [rsp+308h+var_1E0]
0x14002aa5f  mov     [rsp+308h+var_2E0], rax
0x14002aa64  mov     eax, [rsp+308h+var_1E4]
0x14002aa6b  mov     dword ptr [rsp+308h+var_2E8], eax
0x14002aa6f  mov     r9d, [rsp+308h+var_1D8]
0x14002aa77  mov     r8d, [rsp+308h+var_1E8]
0x14002aa7f  mov     rdx, [rsp+308h+var_1F0]
0x14002aa87  mov     rcx, [rsp+308h+var_1F8]
0x14002aa8f  call    cs:__imp_VssTraceMessage
0x14002aa95  cmp     [rsp+308h+var_215], bl
0x14002aa9c  jz      short loc_14002AABF
0x14002aa9e  mov     rdi, rbx
0x14002aaa1  mov     rcx, [rsp+rdi*8+308h+pv]; pv
0x14002aaa6  test    rcx, rcx
0x14002aaa9  jz      short loc_14002AAB6
0x14002aaab  call    cs:__imp_CoTaskMemFree
0x14002aab1  mov     [rsp+rdi*8+308h+pv], rbx
0x14002aab6  inc     rdi
0x14002aab9  cmp     rdi, 0Fh
0x14002aabd  jnz     short loc_14002AAA1
0x14002aabf  mov     [rsp+308h+var_2B8], rsi
0x14002aac4  mov     [rsp+308h+var_2B0], r14
0x14002aac9  mov     [rsp+308h+var_2A8], r15
0x14002aace  mov     [rsp+308h+var_2A0], 1E5h
0x14002aad6  mov     [rsp+308h+var_29C], 1
0x14002aade  mov     [rsp+308h+var_298], 0FFh
0x14002aae6  mov     dword ptr [rsp+0F0h], 1000000h
0x14002aaf1  xor     edx, edx; Val
0x14002aaf3  lea     r8d, [rdx+78h]; Size
0x14002aaf7  lea     rcx, [rsp+308h+pv]; void *
0x14002aafc  call    memset_0
0x14002ab01  mov     r9d, r12d
0x14002ab04  lea     r8, aAttemptToChang; "Attempt to change the service status to"...
0x14002ab0b  lea     rdx, [rsp+308h+var_2B8]
0x14002ab10  lea     rcx, [rsp+308h+var_208]
0x14002ab18  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14002ab1d  lea     rdx, [r13+60h]; lpServiceStatus
0x14002ab21  mov     [rdx+4], r12d
0x14002ab25  mov     rcx, [r13+50h]; hServiceStatus
0x14002ab29  call    cs:__imp_SetServiceStatus
0x14002ab2f  test    eax, eax
0x14002ab31  jnz     loc_14002AC69
0x14002ab37  mov     [rsp+308h+var_2B8], rsi
0x14002ab3c  mov     [rsp+308h+var_2B0], r14
0x14002ab41  mov     [rsp+308h+var_2A8], r15
0x14002ab46  mov     [rsp+308h+var_2A0], 1ECh
0x14002ab4e  mov     [rsp+308h+var_29C], 1
0x14002ab56  mov     [rsp+308h+var_298], 0FFh
0x14002ab5e  mov     dword ptr [rsp+0F0h], 1000000h
0x14002ab69  xor     edx, edx; Val
0x14002ab6b  lea     r8d, [rax+78h]; Size
0x14002ab6f  lea     rcx, [rsp+308h+pv]; void *
0x14002ab74  call    memset_0
0x14002ab79  mov     r8d, r12d
0x14002ab7c  lea     rdx, [rsp+308h+var_D8]; this
0x14002ab84  lea     rcx, [rsp+308h+var_2B8]; struct CVssDebugInfo *
0x14002ab89  call    ??6CVssDebugInfo@@QEAA?AU0@H@Z; CVssDebugInfo::operator<<(int)
0x14002ab8e  mov     rdi, rax
0x14002ab91  call    cs:__imp_GetLastError
0x14002ab97  test    eax, eax
0x14002ab99  jle     short loc_14002ABA3
0x14002ab9b  movzx   eax, ax
0x14002ab9e  or      eax, 80070000h
0x14002aba3  mov     r8d, eax; dwMessageId
0x14002aba6  lea     rdx, [rsp+308h+var_180]; this
0x14002abae  mov     rcx, rdi; struct CVssDebugInfo *
0x14002abb1  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x14002abb6  mov     r9d, 1
0x14002abbc  mov     r8, rax
0x14002abbf  lea     edx, [r9+7]
0x14002abc3  lea     rcx, [rsp+308h+var_208]
0x14002abcb  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14002abd0  lea     rcx, [rsp+308h+var_D8]; this
0x14002abd8  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002abdd  lea     rcx, [rsp+308h+var_2B8]; this
0x14002abe2  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002abe7  call    cs:__imp_GetLastError
0x14002abed  mov     r12d, eax
0x14002abf0  call    cs:__imp_GetLastError
0x14002abf6  mov     edi, eax
0x14002abf8  test    eax, eax
0x14002abfa  jle     short loc_14002AC05
0x14002abfc  movzx   edi, ax
0x14002abff  or      edi, 80070000h
0x14002ac05  mov     [rsp+308h+var_2B8], rsi
0x14002ac0a  mov     [rsp+308h+var_2B0], r14
0x14002ac0f  mov     [rsp+308h+var_2A8], r15
0x14002ac14  mov     [rsp+308h+var_2A0], 1EDh
0x14002ac1c  mov     [rsp+308h+var_29C], 1
0x14002ac24  mov     [rsp+308h+var_298], 0FFh
0x14002ac2c  mov     dword ptr [rsp+0F0h], 1000000h
0x14002ac37  xor     edx, edx; Val
0x14002ac39  lea     r8d, [rdx+78h]; Size
0x14002ac3d  lea     rcx, [rsp+308h+pv]; void *
0x14002ac42  call    memset_0
0x14002ac47  mov     dword ptr [rsp+308h+var_2E8], r12d
0x14002ac4c  lea     r9, aErrorOnCalling; "Error on calling SetServiceStatus. 0x%0"...
0x14002ac53  mov     r8d, edi
0x14002ac56  lea     rdx, [rsp+308h+var_2B8]
0x14002ac5b  lea     rcx, [rsp+308h+var_208]
0x14002ac63  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002ac69  jmp     short loc_14002AC86
0x14002ac6b  jmp     short loc_14002AC71
0x14002ac6d  jmp     short loc_14002AC71
0x14002ac6f  jmp     short $+2
0x14002ac71  lea     r15, aCorsvcc; "CORSVCC"
0x14002ac78  lea     r14, aCvsservicemodu_0; "CVsServiceModule::SetServiceStatus"
0x14002ac7f  lea     rsi, aBaseStorVssMod_5; "base\\stor\\vss\\modules\\coord\\src\\s"...
0x14002ac86  mov     edi, [rsp+308h+var_200]
0x14002ac8d  test    edi, edi
0x14002ac8f  jns     short loc_14002AD01
0x14002ac91  mov     [rsp+308h+var_2B8], rsi
0x14002ac96  mov     [rsp+308h+var_2B0], r14
0x14002ac9b  mov     [rsp+308h+var_2A8], r15
0x14002aca0  mov     [rsp+308h+var_2A0], 1F4h
0x14002aca8  mov     [rsp+308h+var_29C], 1
0x14002acb0  mov     [rsp+308h+var_298], 0FFh
0x14002acb8  mov     dword ptr [rsp+0F0h], 1000000h
0x14002acc3  xor     edx, edx; Val
0x14002acc5  lea     r8d, [rdx+78h]; Size
0x14002acc9  lea     rcx, [rsp+308h+pv]; void *
0x14002acce  call    memset_0
0x14002acd3  movzx   edx, [rsp+308h+arg_10]
0x14002acdb  mov     dword ptr [rsp+308h+var_2E0], edi
0x14002acdf  lea     rax, aErrorOnCalling; "Error on calling SetServiceStatus. 0x%0"...
0x14002ace6  mov     [rsp+308h+var_2E8], rax
0x14002aceb  mov     r9d, edi
0x14002acee  lea     r8, [rsp+308h+var_2B8]
0x14002acf3  lea     rcx, [rsp+308h+var_208]
0x14002acfb  call    ?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)
0x14002ad00  nop
0x14002ad01  lea     rcx, [rsp+308h+var_208]; this
0x14002ad09  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002ad0e  lea     r11, [rsp+308h+var_28]
0x14002ad16  mov     rbx, [r11+38h]
0x14002ad1a  mov     rsi, [r11+48h]
0x14002ad1e  mov     rsp, r11
0x14002ad21  pop     r15
0x14002ad23  pop     r14
0x14002ad25  pop     r13
0x14002ad27  pop     r12
0x14002ad29  pop     rdi
0x14002ad2a  retn
```
