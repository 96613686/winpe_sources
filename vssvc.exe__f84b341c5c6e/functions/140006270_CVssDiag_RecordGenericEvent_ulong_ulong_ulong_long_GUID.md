# CVssDiag::RecordGenericEvent(ulong,ulong,ulong,long,_GUID)

- ea: `0x140006270`
- end: `0x140006c0d`
- name: `?RecordGenericEvent@CVssDiag@@QEAAXKKKJU_GUID@@@Z`
- size: `2461`
- prototype: `void __fastcall(CVssDiag *__hidden this, unsigned int, unsigned int, unsigned int, int, struct _GUID *)`
- caller_count: `25`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140006078`
- `0x1400090d0`
- `0x14000a988`
- `0x140040690`
- `0x140040c48`
- `0x140041b3c`
- `0x14004229c`
- `0x140043c70`
- `0x14004a0c8`
- `0x14004d814`
- `0x14004fd80`
- `0x14005aa00`
- `0x14006aef0`
- `0x14006cc40`
- `0x14008c610`
- `0x1400a8900`
- `0x1400a8bf0`
- `0x1400a8e10`
- `0x1400a8ec0`
- `0x1400a8f70`
- `0x1400aa1f0`
- `0x1400b01b0`
- `0x1400b0700`
- `0x1400cbb50`
- `0x1400cbc40`

## callees

- `0x140006020`
- `0x140006270`
- `0x140007a14`
- `0x140008094`
- `0x1400137c0`
- `0x1400139c0`
- `0x140013c60`
- `0x140049ec4`
- `0x140091560`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000671d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000671d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006710`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140006710`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006a04`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140006a04`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006387`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006914`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006387`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140006914`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400066ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400066ee`
- `VssTrace!__imp_VssTraceMessage` at `0x140006b67`
- `VssTrace!__imp_VssTraceMessage` at `0x140006bed`
- `VssTrace!__imp_VssTraceMessage` at `0x140006b67`
- `VssTrace!__imp_VssTraceMessage` at `0x140006bed`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006801`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006a38`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006801`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140006a38`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400063e4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140006972`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x1400063e4`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140006972`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400065d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400065d9`

## string_xrefs

- `0x140006861`: `CVssRegistryKey::SetBinaryValue`
- `0x140006afa`: `RegSetValueExW(0x%08lx,%s,0,REG_BINARY,%p.%lu)`
- `0x1400062c4`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140006492`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140006614`: `base\stor\vss\modules\registry\registry.cxx`
- `0x140006852`: `base\stor\vss\modules\registry\registry.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void __fastcall CVssDiag::RecordGenericEvent(
        CVssDiag *this,
        unsigned int a2,
        int a3,
        DWORD a4,
        unsigned int a5,
        struct _GUID *a6)
{
  __int64 v6; // rax
  int v7; // ebx
  __int64 i; // rbx
  void *v9; // rcx
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  int v13; // r14d
  int v14; // r15d
  int v15; // r12d
  int v16; // r13d
  _OWORD *v17; // r14
  int v18; // r15d
  unsigned int v19; // r12d
  CVssDiag *v20; // rcx
  CVssDiag *v21; // r13
  const WCHAR *StringFromOperation; // rsi
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // ebx
  LSTATUS v27; // eax
  unsigned int v28; // ebx
  __int64 v29; // rdi
  __int64 v30; // rsi
  unsigned int v31; // r12d
  BYTE *lpData; // [rsp+20h] [rbp-328h]
  DWORD cbData[2]; // [rsp+28h] [rbp-320h]
  __int64 v34; // [rsp+30h] [rbp-318h]
  __int64 v35; // [rsp+38h] [rbp-310h]
  __int64 v36; // [rsp+38h] [rbp-310h]
  __int64 v37; // [rsp+40h] [rbp-308h]
  int v38; // [rsp+60h] [rbp-2E8h]
  int v39; // [rsp+68h] [rbp-2E0h]
  int v40; // [rsp+70h] [rbp-2D8h]
  __int64 v41; // [rsp+90h] [rbp-2B8h] BYREF
  DWORD v42; // [rsp+98h] [rbp-2B0h]
  _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-2A8h] BYREF
  CVssDiag *v44; // [rsp+A8h] [rbp-2A0h]
  int v45; // [rsp+B0h] [rbp-298h]
  unsigned int v46; // [rsp+B4h] [rbp-294h]
  unsigned __int64 v47; // [rsp+C0h] [rbp-288h] BYREF
  int v48; // [rsp+C8h] [rbp-280h]
  const unsigned __int16 *v49; // [rsp+D0h] [rbp-278h]
  const unsigned __int16 *v50; // [rsp+D8h] [rbp-270h]
  __int64 v51; // [rsp+E0h] [rbp-268h]
  const unsigned __int16 *v52; // [rsp+E8h] [rbp-260h]
  unsigned int v53; // [rsp+F0h] [rbp-258h]
  DWORD TickCount; // [rsp+F4h] [rbp-254h]
  int v55; // [rsp+F8h] [rbp-250h]
  __int128 v56; // [rsp+100h] [rbp-248h]
  __int128 v57; // [rsp+110h] [rbp-238h]
  __int64 v58; // [rsp+120h] [rbp-228h]
  const unsigned __int16 *v59; // [rsp+130h] [rbp-218h] BYREF
  wchar_t *v60; // [rsp+138h] [rbp-210h]
  const unsigned __int16 *v61; // [rsp+140h] [rbp-208h]
  int v62; // [rsp+148h] [rbp-200h]
  unsigned int v63; // [rsp+14Ch] [rbp-1FCh]
  int v64; // [rsp+150h] [rbp-1F8h]
  _BYTE v65[120]; // [rsp+158h] [rbp-1F0h] BYREF
  int v66; // [rsp+1D0h] [rbp-178h]
  const unsigned __int16 *v67; // [rsp+1E0h] [rbp-168h] BYREF
  const unsigned __int16 *v68; // [rsp+1E8h] [rbp-160h]
  const unsigned __int16 *v69; // [rsp+1F0h] [rbp-158h]
  __int64 v70; // [rsp+1F8h] [rbp-150h]
  unsigned int v71; // [rsp+200h] [rbp-148h]
  unsigned int v72; // [rsp+204h] [rbp-144h]
  LPVOID pv; // [rsp+208h] [rbp-140h] BYREF
  unsigned int v74; // [rsp+210h] [rbp-138h]
  DWORD v75; // [rsp+214h] [rbp-134h]
  int v76; // [rsp+218h] [rbp-130h]
  __int128 v77; // [rsp+220h] [rbp-128h]
  __int128 v78; // [rsp+230h] [rbp-118h]
  __int64 v79; // [rsp+240h] [rbp-108h]
  int v80; // [rsp+280h] [rbp-C8h]
  BYTE Data[16]; // [rsp+2B0h] [rbp-98h] BYREF
  __int128 v82; // [rsp+2C0h] [rbp-88h]
  __m256i v83; // [rsp+2D0h] [rbp-78h] BYREF
  __int64 v84; // [rsp+2F0h] [rbp-58h]

  v42 = a4;
  v45 = a3;
  v46 = a2;
  v44 = this;
  SystemTimeAsFileTime = (_FILETIME)a6;
  v67 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v68 = L"CVssDiag::RecordGenericEvent";
  v69 = L"REGREGSC";
  v70 = 0xB0000052DLL;
  v71 = 255;
  v80 = 0x1000000;
  memset_0(&pv, 0, 0x78u);
  v48 = 0;
  v52 = L"CVssDiag::RecordGenericEvent";
  v49 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v50 = L"REGREGSC";
  v51 = 0xB0000052DLL;
  TickCount = GetTickCount();
  v55 = 255;
  v47 = 0xFFFFFFFF00000000uLL;
  v58 = 0;
  v56 = 0;
  v57 = 0;
  v41 = 0;
  if ( (int)VssGetTracingContextPerThread(&v41) < 0 || (int)VssSetTracingContextPerThread(&v47) < 0 )
  {
    v6 = v58;
  }
  else
  {
    v6 = v41;
    v58 = v41;
  }
  if ( v6 )
    v53 = *(_DWORD *)(v6 + 48) + 1;
  else
    v53 = 0;
  v7 = 160;
  if ( v55 != 255 )
    v7 = v55;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v47, HIDWORD(v51)) )
    VssTraceMessage(v49, v50, (unsigned int)v51, v53, HIDWORD(v51), v52, L"ENTER", v7, 0);
  if ( HIBYTE(v80) )
  {
    for ( i = 0; i != 15; ++i )
    {
      v9 = *(&pv + i);
      if ( v9 )
      {
        CoTaskMemFree(v9);
        *(&pv + i) = 0;
      }
    }
  }
  v10 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 15LL);
  v11 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 14LL);
  v12 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 13LL);
  v13 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 12LL);
  v14 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 11LL);
  v15 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 10LL);
  v16 = *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 9LL);
  v59 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
  v60 = (wchar_t *)L"CVssDiag::RecordGenericEvent";
  v61 = L"REGREGSC";
  v62 = 1329;
  v63 = 11;
  v64 = 255;
  v66 = 0x1000000;
  memset_0(v65, 0, sizeof(v65));
  v40 = v13;
  v39 = v14;
  v38 = v15;
  v17 = (_OWORD *)SystemTimeAsFileTime;
  LODWORD(v37) = *(unsigned __int16 *)(*(_QWORD *)&SystemTimeAsFileTime + 4LL);
  LODWORD(v35) = *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime;
  LODWORD(v34) = a5;
  cbData[0] = v42;
  v18 = v45;
  LODWORD(lpData) = v45;
  v19 = v46;
  CVssFunctionTracer::Trace(
    &v47,
    &v59,
    L"Parameters %ld, %ld, %ld, 0x%08lx, {%.8x-%.4x-%.4x-%.2x%.2x-%.2x%.2x%.2x%.2x%.2x%.2x}",
    v46,
    lpData,
    *(_QWORD *)cbData,
    v34,
    v35,
    v37,
    *(unsigned __int16 *)(*(_QWORD *)&SystemTimeAsFileTime + 6LL),
    *(unsigned __int8 *)(*(_QWORD *)&SystemTimeAsFileTime + 8LL),
    v16,
    v38,
    v39,
    v40,
    v12,
    v11,
    v10);
  v21 = v44;
  if ( *((_BYTE *)v44 + 32) )
  {
    if ( (v18 & 2) == 0 )
    {
      StringFromOperation = CVssDiag::GetStringFromOperation(v20, v18 & 1, v19);
      if ( StringFromOperation )
      {
        v59 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
        v60 = (wchar_t *)L"CVssDiag::RecordGenericEvent";
        v61 = L"REGREGSC";
        v62 = 1348;
        v63 = 11;
        v64 = 255;
        v66 = 0x1000000;
        memset_0(v65, 0, sizeof(v65));
        CVssFunctionTracer::Trace(&v47, &v59, L"Event name: %s", StringFromOperation);
        *(_QWORD *)&Data[8] = 0;
        v82 = 0;
        memset(&v83, 0, sizeof(v83));
        v84 = 0;
        *(_QWORD *)Data = 72;
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(_FILETIME *)&Data[8] = SystemTimeAsFileTime;
        LODWORD(v82) = GetCurrentProcessId();
        *(_QWORD *)((char *)&v82 + 4) = __PAIR64__(v19, GetCurrentThreadId());
        HIDWORD(v82) = v18;
        v83.m256i_i64[0] = __PAIR64__(a5, v42);
        *(_OWORD *)&v83.m256i_u64[1] = *v17;
        v83.m256i_i64[3] = 0;
        v84 = 0;
        if ( v19 == 1028 || (v31 = v19 - 1022) == 0 || v31 == 1 && (v18 & 1) != 0 )
        {
          v23 = *((unsigned int *)v21 + 210);
          if ( (unsigned int)v23 < 0xA )
          {
            *((_QWORD *)v21 + 10 * v23 + 14) = StringFromOperation;
            v24 = 10LL * *((unsigned int *)v21 + 210);
            *(_OWORD *)((char *)v21 + 8 * v24 + 40) = *(_OWORD *)Data;
            *(_OWORD *)((char *)v21 + 8 * v24 + 56) = v82;
            *(__m256i *)((char *)v21 + 8 * v24 + 72) = v83;
            *((_QWORD *)v21 + v24 + 13) = v84;
            ++*((_DWORD *)v21 + 210);
          }
        }
        else
        {
          CVssDiag::FlushQueue(v21);
          v59 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
          v60 = L"CVssRegistryKey::SetBinaryValue";
          v61 = L"REGREGSC";
          v62 = 362;
          v63 = 11;
          v64 = 255;
          v66 = 0x1000000;
          memset_0(v65, 0, sizeof(v65));
          LODWORD(v68) = 0;
          pv = v60;
          v69 = v59;
          v70 = (__int64)v61;
          v71 = v62;
          v72 = v63;
          v75 = GetTickCount();
          v76 = v64;
          v67 = (const unsigned __int16 *)0xFFFFFFFF00000000LL;
          v79 = 0;
          v77 = 0;
          v78 = 0;
          v41 = 0;
          if ( (int)VssGetTracingContextPerThread(&v41) < 0 || (int)VssSetTracingContextPerThread(&v67) < 0 )
          {
            v25 = v79;
          }
          else
          {
            v25 = v41;
            v79 = v41;
          }
          if ( v25 )
            v74 = *(_DWORD *)(v25 + 48) + 1;
          else
            v74 = 0;
          v26 = 160;
          if ( v76 != 255 )
            v26 = v76;
          if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v67, v72) )
            VssTraceMessage(v69, v70, v71, v74, v72, pv, L"ENTER", v26, 0);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v59);
          v27 = RegSetValueExW(*((HKEY *)v21 + 1), StringFromOperation, 0, 3u, Data, 0x48u);
          v28 = v27;
          if ( v27 )
          {
            v29 = *((_QWORD *)v21 + 3);
            v30 = *((_QWORD *)v21 + 1);
            if ( v27 > 0 )
              v28 = (unsigned __int16)v27 | 0x80070000;
            v59 = L"base\\stor\\vss\\modules\\registry\\registry.cxx";
            v60 = L"CVssRegistryKey::SetBinaryValue";
            v61 = L"REGREGSC";
            v62 = 381;
            v63 = 11;
            v64 = 255;
            v66 = 0x1000000;
            memset_0(v65, 0, sizeof(v65));
            LODWORD(v36) = 72;
            CVssFunctionTracer::TranslateGenericError(
              &v67,
              &v59,
              v28,
              L"RegSetValueExW(0x%08lx,%s,0,REG_BINARY,%p.%lu)",
              v30,
              v29,
              Data,
              v36);
          }
          CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v67);
        }
      }
    }
  }
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v47);
}

```

## disassembly

```asm
0x140006270  push    rbx
0x140006272  push    rsi
0x140006273  push    rdi
0x140006274  push    r12
0x140006276  push    r13
0x140006278  push    r14
0x14000627a  push    r15
0x14000627c  sub     rsp, 310h
0x140006283  mov     rax, cs:__security_cookie
0x14000628a  xor     rax, rsp
0x14000628d  mov     [rsp+348h+var_48], rax
0x140006295  mov     [rsp+348h+var_2B0], r9d
0x14000629d  mov     [rsp+348h+var_298], r8d
0x1400062a5  mov     [rsp+348h+var_294], edx
0x1400062ac  mov     [rsp+348h+var_2A0], rcx
0x1400062b4  mov     r14, [rsp+348h+arg_28]
0x1400062bc  mov     qword ptr [rsp+348h+SystemTimeAsFileTime.dwLowDateTime], r14
0x1400062c4  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x1400062cb  mov     [rsp+348h+var_168], rax
0x1400062d3  lea     rax, aCvssdiagRecord; "CVssDiag::RecordGenericEvent"
0x1400062da  mov     [rsp+348h+var_160], rax
0x1400062e2  lea     rax, aRegregsc; "REGREGSC"
0x1400062e9  mov     [rsp+348h+var_158], rax
0x1400062f1  mov     dword ptr [rsp+348h+var_150], 52Dh
0x1400062fc  mov     dword ptr [rsp+348h+var_150+4], 0Bh
0x140006307  mov     [rsp+348h+var_148], 0FFh
0x140006312  xor     edi, edi
0x140006314  mov     [rsp+348h+var_C8], 1000000h
0x14000631f  xor     edx, edx; Val
0x140006321  mov     r8d, 78h ; 'x'; Size
0x140006327  lea     rcx, [rsp+348h+pv]; void *
0x14000632f  call    memset_0
0x140006334  mov     [rsp+348h+var_280], edi
0x14000633b  mov     rax, [rsp+348h+var_160]
0x140006343  mov     [rsp+348h+var_260], rax
0x14000634b  mov     rax, [rsp+348h+var_168]
0x140006353  mov     [rsp+348h+var_278], rax
0x14000635b  mov     rax, [rsp+348h+var_158]
0x140006363  mov     [rsp+348h+var_270], rax
0x14000636b  mov     eax, dword ptr [rsp+348h+var_150]
0x140006372  mov     dword ptr [rsp+348h+var_268], eax
0x140006379  mov     eax, dword ptr [rsp+348h+var_150+4]
0x140006380  mov     dword ptr [rsp+348h+var_268+4], eax
0x140006387  call    cs:__imp_GetTickCount
0x14000638d  mov     [rsp+348h+var_254], eax
0x140006394  mov     [rsp+348h+var_284], 0FFFFFFFFh
0x14000639f  mov     eax, [rsp+348h+var_148]
0x1400063a6  mov     [rsp+348h+var_250], eax
0x1400063ad  mov     [rsp+348h+var_288], edi
0x1400063b4  mov     [rsp+348h+var_228], rdi
0x1400063bc  xorps   xmm0, xmm0
0x1400063bf  movdqa  [rsp+348h+var_248], xmm0
0x1400063c8  xorps   xmm1, xmm1
0x1400063cb  movdqa  [rsp+348h+var_238], xmm1
0x1400063d4  mov     [rsp+348h+var_2B8], rdi
0x1400063dc  lea     rcx, [rsp+348h+var_2B8]
0x1400063e4  call    cs:__imp_VssGetTracingContextPerThread
0x1400063ea  test    eax, eax
0x1400063ec  jns     loc_1400067F9
0x1400063f2  mov     rax, [rsp+348h+var_228]
0x1400063fa  test    rax, rax
0x1400063fd  jz      loc_140006836
0x140006403  mov     eax, [rax+30h]
0x140006406  inc     eax
0x140006408  mov     [rsp+348h+var_258], eax
0x14000640f  mov     ebx, 0A0h
0x140006414  cmp     [rsp+348h+var_250], 0FFh
0x14000641f  cmovnz  ebx, [rsp+348h+var_250]
0x140006427  mov     edx, dword ptr [rsp+348h+var_268+4]; unsigned int
0x14000642e  lea     rcx, [rsp+348h+var_288]; this
0x140006436  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x14000643b  test    eax, eax
0x14000643d  jnz     loc_140006B1A
0x140006443  cmp     byte ptr [rsp+348h+var_C8+3], dil
0x14000644b  jz      short loc_14000646A
0x14000644d  mov     rbx, rdi
0x140006450  mov     rcx, [rsp+rbx*8+348h+pv]; pv
0x140006458  test    rcx, rcx
0x14000645b  jnz     loc_1400065D9
0x140006461  inc     rbx
0x140006464  cmp     rbx, 0Fh
0x140006468  jnz     short loc_140006450
0x14000646a  mov     rcx, qword ptr [rsp+348h+SystemTimeAsFileTime.dwLowDateTime]
0x140006472  movzx   ebx, byte ptr [rcx+0Fh]
0x140006476  movzx   edi, byte ptr [rcx+0Eh]
0x14000647a  movzx   esi, byte ptr [rcx+0Dh]
0x14000647e  movzx   r14d, byte ptr [rcx+0Ch]
0x140006483  movzx   r15d, byte ptr [rcx+0Bh]
0x140006488  movzx   r12d, byte ptr [rcx+0Ah]
0x14000648d  movzx   r13d, byte ptr [rcx+9]
0x140006492  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140006499  mov     [rsp+348h+var_218], rax
0x1400064a1  lea     rax, aCvssdiagRecord; "CVssDiag::RecordGenericEvent"
0x1400064a8  mov     [rsp+348h+var_210], rax
0x1400064b0  lea     rax, aRegregsc; "REGREGSC"
0x1400064b7  mov     [rsp+348h+var_208], rax
0x1400064bf  mov     [rsp+348h+var_200], 531h
0x1400064ca  mov     [rsp+348h+var_1FC], 0Bh
0x1400064d5  mov     [rsp+348h+var_1F8], 0FFh
0x1400064e0  mov     [rsp+348h+var_178], 1000000h
0x1400064eb  xor     edx, edx; Val
0x1400064ed  mov     r8d, 78h ; 'x'; Size
0x1400064f3  lea     rcx, [rsp+348h+var_1F0]; void *
0x1400064fb  call    memset_0
0x140006500  mov     [rsp+348h+var_2C0], ebx
0x140006507  mov     [rsp+348h+var_2C8], edi
0x14000650e  mov     [rsp+348h+var_2D0], esi
0x140006512  mov     [rsp+348h+var_2D8], r14d
0x140006517  mov     [rsp+348h+var_2E0], r15d
0x14000651c  mov     [rsp+348h+var_2E8], r12d
0x140006521  mov     [rsp+348h+var_2F0], r13d
0x140006526  mov     r14, qword ptr [rsp+348h+SystemTimeAsFileTime.dwLowDateTime]
0x14000652e  movzx   eax, byte ptr [r14+8]
0x140006533  mov     [rsp+348h+var_2F8], eax
0x140006537  movzx   eax, word ptr [r14+6]
0x14000653c  mov     [rsp+348h+var_300], eax
0x140006540  movzx   eax, word ptr [r14+4]
0x140006545  mov     dword ptr [rsp+348h+var_308], eax
0x140006549  mov     eax, [r14]
0x14000654c  mov     dword ptr [rsp+348h+var_310], eax
0x140006550  mov     edi, [rsp+348h+arg_20]
0x140006557  mov     dword ptr [rsp+348h+var_318], edi
0x14000655b  mov     eax, [rsp+348h+var_2B0]
0x140006562  mov     [rsp+348h+cbData], eax
0x140006566  mov     r15d, [rsp+348h+var_298]
0x14000656e  mov     dword ptr [rsp+348h+lpData], r15d
0x140006573  mov     r12d, [rsp+348h+var_294]
0x14000657b  mov     r9d, r12d
0x14000657e  lea     r8, aParametersLdLd; "Parameters %ld, %ld, %ld, 0x%08lx, {%.8"...
0x140006585  lea     rdx, [rsp+348h+var_218]
0x14000658d  lea     rcx, [rsp+348h+var_288]
0x140006595  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x14000659a  mov     r13, [rsp+348h+var_2A0]
0x1400065a2  cmp     byte ptr [r13+20h], 0
0x1400065a7  jnz     short loc_1400065EC
0x1400065a9  lea     rcx, [rsp+348h+var_288]; this
0x1400065b1  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x1400065b6  mov     rcx, [rsp+348h+var_48]
0x1400065be  xor     rcx, rsp; StackCookie
0x1400065c1  call    __security_check_cookie
0x1400065c6  add     rsp, 310h
0x1400065cd  pop     r15
0x1400065cf  pop     r14
0x1400065d1  pop     r13
0x1400065d3  pop     r12
0x1400065d5  pop     rdi
0x1400065d6  pop     rsi
0x1400065d7  pop     rbx
0x1400065d8  retn
0x1400065d9  call    cs:__imp_CoTaskMemFree
0x1400065df  mov     [rsp+rbx*8+348h+pv], rdi
0x1400065e7  jmp     loc_140006461
0x1400065ec  test    r15b, 2
0x1400065f0  jnz     loc_140006824
0x1400065f6  movzx   ebx, r15b
0x1400065fa  and     bl, 1
0x1400065fd  mov     r8d, r12d; unsigned int
0x140006600  movzx   edx, bl; bool
0x140006603  call    ?GetStringFromOperation@CVssDiag@@AEAAPEBG_NK@Z; CVssDiag::GetStringFromOperation(bool,ulong)
0x140006608  mov     rsi, rax
0x14000660b  test    rax, rax
0x14000660e  jz      loc_140006B72
0x140006614  lea     rax, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x14000661b  mov     [rsp+348h+var_218], rax
0x140006623  lea     rax, aCvssdiagRecord; "CVssDiag::RecordGenericEvent"
0x14000662a  mov     [rsp+348h+var_210], rax
0x140006632  lea     rax, aRegregsc; "REGREGSC"
0x140006639  mov     [rsp+348h+var_208], rax
0x140006641  mov     [rsp+348h+var_200], 544h
0x14000664c  mov     [rsp+348h+var_1FC], 0Bh
0x140006657  mov     [rsp+348h+var_1F8], 0FFh
0x140006662  mov     [rsp+348h+var_178], 1000000h
0x14000666d  xor     edx, edx; Val
0x14000666f  mov     r8d, 78h ; 'x'; Size
0x140006675  lea     rcx, [rsp+348h+var_1F0]; void *
0x14000667d  call    memset_0
0x140006682  mov     r9, rsi
0x140006685  lea     r8, aEventNameS; "Event name: %s"
0x14000668c  lea     rdx, [rsp+348h+var_218]
0x140006694  lea     rcx, [rsp+348h+var_288]
0x14000669c  call    ?Trace@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@QEAGZZ; CVssFunctionTracer::Trace(CVssDebugInfo,ushort * const,...)
0x1400066a1  mov     qword ptr [rsp+348h+Data+8], 0
0x1400066ad  xorps   xmm0, xmm0
0x1400066b0  movdqa  [rsp+348h+var_88], xmm0
0x1400066b9  xorps   xmm1, xmm1
0x1400066bc  movdqa  [rsp+348h+var_78], xmm1
0x1400066c5  movdqa  [rsp+348h+var_68], xmm0
0x1400066ce  mov     [rsp+348h+var_58], 0
0x1400066da  mov     qword ptr [rsp+348h+Data], 48h ; 'H'
0x1400066e6  lea     rcx, [rsp+348h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400066ee  call    cs:__imp_GetSystemTimeAsFileTime
0x1400066f4  mov     eax, [rsp+348h+SystemTimeAsFileTime.dwLowDateTime]
0x1400066fb  mov     ecx, [rsp+348h+SystemTimeAsFileTime.dwHighDateTime]
0x140006702  mov     dword ptr [rsp+348h+Data+8], eax
0x140006709  mov     dword ptr [rsp+348h+Data+0Ch], ecx
0x140006710  call    cs:__imp_GetCurrentProcessId
0x140006716  mov     dword ptr [rsp+348h+var_88], eax
0x14000671d  call    cs:__imp_GetCurrentThreadId
0x140006723  mov     dword ptr [rsp+348h+var_88+4], eax
0x14000672a  mov     dword ptr [rsp+348h+var_88+8], r12d
0x140006732  mov     dword ptr [rsp+348h+var_88+0Ch], r15d
0x14000673a  mov     eax, [rsp+348h+var_2B0]
0x140006741  mov     dword ptr [rsp+348h+var_78], eax
0x140006748  mov     dword ptr [rsp+348h+var_78+4], edi
0x14000674f  movaps  xmm0, xmmword ptr [r14]
0x140006753  movups  [rsp+348h+var_78+8], xmm0
0x14000675b  xor     r14d, r14d
0x14000675e  mov     qword ptr [rsp+348h+var_68+8], r14
0x140006766  mov     [rsp+348h+var_58], r14
0x14000676e  cmp     r12d, 404h
0x140006775  jnz     loc_140006B84
0x14000677b  mov     eax, [r13+348h]
0x140006782  cmp     eax, 0Ah
0x140006785  jnb     loc_140006A1E
0x14000678b  lea     rcx, [rax+rax*4]
0x14000678f  add     rcx, rcx
0x140006792  mov     [r13+rcx*8+70h], rsi
0x140006797  mov     eax, [r13+348h]
0x14000679e  lea     rcx, [rax+rax*4]
0x1400067a2  add     rcx, rcx
0x1400067a5  movaps  xmm0, xmmword ptr [rsp+348h+Data]
0x1400067ad  movups  xmmword ptr [r13+rcx*8+28h], xmm0
0x1400067b3  movaps  xmm1, [rsp+348h+var_88]
0x1400067bb  movups  xmmword ptr [r13+rcx*8+38h], xmm1
0x1400067c1  movaps  xmm0, [rsp+348h+var_78]
0x1400067c9  movups  xmmword ptr [r13+rcx*8+48h], xmm0
0x1400067cf  movaps  xmm1, [rsp+348h+var_68]
0x1400067d7  movups  xmmword ptr [r13+rcx*8+58h], xmm1
0x1400067dd  movsd   xmm0, [rsp+348h+var_58]
0x1400067e6  movsd   qword ptr [r13+rcx*8+68h], xmm0
0x1400067ed  inc     dword ptr [r13+348h]
0x1400067f4  jmp     loc_140006A1E
0x1400067f9  lea     rcx, [rsp+348h+var_288]
0x140006801  call    cs:__imp_VssSetTracingContextPerThread
0x140006807  test    eax, eax
0x140006809  js      loc_1400063F2
0x14000680f  mov     rax, [rsp+348h+var_2B8]
0x140006817  mov     [rsp+348h+var_228], rax
0x14000681f  jmp     loc_1400063FA
0x140006824  lea     rcx, [rsp+348h+var_288]; this
0x14000682c  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x140006831  jmp     loc_1400065B6
0x140006836  mov     [rsp+348h+var_258], edi
0x14000683d  jmp     loc_14000640F
0x140006842  test    bl, bl
0x140006844  jnz     loc_14000677B
0x14000684a  mov     rcx, r13; this
0x14000684d  call    ?FlushQueue@CVssDiag@@AEAAXXZ; CVssDiag::FlushQueue(void)
0x140006852  lea     r12, aBaseStorVssMod_26; "base\\stor\\vss\\modules\\registry\\reg"...
0x140006859  mov     [rsp+348h+var_218], r12
0x140006861  lea     r15, aCvssregistryke_3; "CVssRegistryKey::SetBinaryValue"
0x140006868  mov     [rsp+348h+var_210], r15
0x140006870  lea     rax, aRegregsc; "REGREGSC"
0x140006877  mov     [rsp+348h+var_208], rax
0x14000687f  mov     [rsp+348h+var_200], 16Ah
0x14000688a  mov     [rsp+348h+var_1FC], 0Bh
0x140006895  mov     [rsp+348h+var_1F8], 0FFh
0x1400068a0  mov     [rsp+348h+var_178], 1000000h
0x1400068ab  xor     edx, edx; Val
0x1400068ad  mov     r8d, 78h ; 'x'; Size
0x1400068b3  lea     rcx, [rsp+348h+var_1F0]; void *
0x1400068bb  call    memset_0
0x1400068c0  mov     dword ptr [rsp+348h+var_160], r14d
0x1400068c8  mov     rax, [rsp+348h+var_210]
0x1400068d0  mov     [rsp+348h+pv], rax
0x1400068d8  mov     rax, [rsp+348h+var_218]
0x1400068e0  mov     [rsp+348h+var_158], rax
0x1400068e8  mov     rax, [rsp+348h+var_208]
0x1400068f0  mov     [rsp+348h+var_150], rax
0x1400068f8  mov     eax, [rsp+348h+var_200]
0x1400068ff  mov     [rsp+348h+var_148], eax
0x140006906  mov     eax, [rsp+348h+var_1FC]
0x14000690d  mov     [rsp+348h+var_144], eax
0x140006914  call    cs:__imp_GetTickCount
0x14000691a  mov     [rsp+348h+var_134], eax
0x140006921  mov     dword ptr [rsp+348h+var_168+4], 0FFFFFFFFh
0x14000692c  mov     eax, [rsp+348h+var_1F8]
0x140006933  mov     [rsp+348h+var_130], eax
0x14000693a  mov     dword ptr [rsp+348h+var_168], r14d
0x140006942  mov     [rsp+348h+var_108], r14
0x14000694a  xorps   xmm0, xmm0
0x14000694d  movdqa  [rsp+348h+var_128], xmm0
0x140006956  xorps   xmm1, xmm1
0x140006959  movdqa  [rsp+348h+var_118], xmm1
0x140006962  mov     [rsp+348h+var_2B8], r14
0x14000696a  lea     rcx, [rsp+348h+var_2B8]
0x140006972  call    cs:__imp_VssGetTracingContextPerThread
0x140006978  test    eax, eax
0x14000697a  jns     loc_140006A30
0x140006980  mov     rax, [rsp+348h+var_108]
0x140006988  test    rax, rax
0x14000698b  jz      loc_140006A5B
0x140006991  mov     eax, [rax+30h]
0x140006994  inc     eax
0x140006996  mov     [rsp+348h+var_138], eax
0x14000699d  cmp     [rsp+348h+var_130], 0FFh
0x1400069a8  mov     ebx, 0A0h
0x1400069ad  cmovnz  ebx, [rsp+348h+var_130]
0x1400069b5  mov     edx, [rsp+348h+var_144]; unsigned int
0x1400069bc  lea     rcx, [rsp+348h+var_168]; this
  ... truncated ...
```
