# GetCurrentAccessToken(bool,bool,void * *)

- ea: `0x140030e90`
- end: `0x140031724`
- name: `?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z`
- size: `2196`
- prototype: `char __fastcall(char, char, void **)`
- caller_count: `5`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140003014`
- `0x14001940c`
- `0x14002f438`
- `0x140030230`
- `0x140030790`

## callees

- `0x140011a90`
- `0x1400137c0`
- `0x1400138e0`
- `0x140013c60`
- `0x140028b48`
- `0x140030e90`
- `0x140042aa0`
- `0x140049ec4`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031613`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031023`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031613`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003101b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003133b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003101b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x14003133b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140031004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140031324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140031004`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140031324`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400311db`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140031695`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1400311db`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140031695`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400311ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140031684`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400311ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140031684`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1400314c8`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x1400314c8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140030f3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400310b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003125a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140030f3f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400310b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003125a`
- `VssTrace!__imp_VssTraceMessage` at `0x1400313c8`
- `VssTrace!__imp_VssTraceMessage` at `0x1400313c8`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003116f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400311a0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031317`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14003116f`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x1400311a0`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140031317`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140030f7e`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x140030f7e`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140030ff0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140030ff0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031038`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140031038`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003108f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003109d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400310ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003118b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031226`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031234`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031250`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031081`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003108f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003109d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400310ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14003118b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031226`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031234`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031242`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140031250`

## string_xrefs

- `0x140030eb6`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400313d3`: `base\stor\vss\modules\sec\security.cxx`
- `0x14003143a`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400314d2`: `base\stor\vss\modules\sec\security.cxx`
- `0x140031548`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400315ac`: `base\stor\vss\modules\sec\security.cxx`
- `0x140031620`: `base\stor\vss\modules\sec\security.cxx`
- `0x14003169f`: `base\stor\vss\modules\sec\security.cxx`
- `0x140030ec1`: `GetCurrentAccessToken`
- `0x1400313de`: `GetCurrentAccessToken`
- `0x140031445`: `GetCurrentAccessToken`
- `0x1400314dd`: `GetCurrentAccessToken`
- `0x140031553`: `GetCurrentAccessToken`
- `0x1400315b7`: `GetCurrentAccessToken`
- `0x14003162b`: `GetCurrentAccessToken`
- `0x1400316aa`: `GetCurrentAccessToken`
- `0x140031421`: `CoImpersonateClient`
- `0x140031520`: `DuplicateToken(..., SecurityIdentification, ...)`
- `0x140031488`: `OpenProcessToken`
- `0x1400316ed`: `OpenProcessToken`
- `0x1400315fa`: `OpenThreadToken`
- `0x14003166e`: `OpenThreadToken`

## pseudocode

```c
char __fastcall GetCurrentAccessToken(char a1, char a2, void **a3)
{
  __int64 v6; // rax
  unsigned int v7; // esi
  unsigned int v8; // ebx
  __int64 i; // rbx
  void *v10; // rcx
  HRESULT v11; // ebx
  HANDLE CurrentThread; // rax
  BOOL v13; // edi
  signed int LastError; // eax
  unsigned int v15; // ebx
  DWORD v16; // edi
  HANDLE CurrentProcess; // rax
  DWORD v19; // edi
  HANDLE v20; // rax
  void *v21; // rbx
  HANDLE v22; // rax
  bool v23; // bl
  __int64 v24; // [rsp+20h] [rbp-E0h]
  __int64 v25; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+28h] [rbp-D8h]
  __int64 v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  _DWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  HRESULT v31; // [rsp+58h] [rbp-A8h]
  const unsigned __int16 *v32; // [rsp+60h] [rbp-A0h]
  const unsigned __int16 *v33; // [rsp+68h] [rbp-98h]
  unsigned int v34; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+74h] [rbp-8Ch]
  const wchar_t *v36; // [rsp+78h] [rbp-88h]
  unsigned int v37; // [rsp+80h] [rbp-80h]
  DWORD TickCount; // [rsp+84h] [rbp-7Ch]
  unsigned int v39; // [rsp+88h] [rbp-78h]
  LPVOID pv[2]; // [rsp+90h] [rbp-70h]
  LPVOID v41[2]; // [rsp+A0h] [rbp-60h]
  __int64 v42; // [rsp+B0h] [rbp-50h]
  const unsigned __int16 *v43; // [rsp+C0h] [rbp-40h] BYREF
  const wchar_t *v44; // [rsp+C8h] [rbp-38h]
  const unsigned __int16 *v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+D8h] [rbp-28h]
  int v47; // [rsp+DCh] [rbp-24h]
  int v48; // [rsp+E0h] [rbp-20h]
  LPVOID v49[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v50; // [rsp+F8h] [rbp-8h]
  __int128 v51; // [rsp+108h] [rbp+8h]
  __int128 v52; // [rsp+118h] [rbp+18h]
  __int128 v53; // [rsp+128h] [rbp+28h]
  __int128 v54; // [rsp+138h] [rbp+38h]
  __int128 v55; // [rsp+148h] [rbp+48h]
  __int64 v56; // [rsp+158h] [rbp+58h]
  int v57; // [rsp+160h] [rbp+60h]
  void **v58; // [rsp+168h] [rbp+68h] BYREF
  void *v59; // [rsp+170h] [rbp+70h]
  __int64 v60; // [rsp+1E8h] [rbp+E8h] BYREF

  v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v44 = L"GetCurrentAccessToken";
  v45 = L"SECSECRC";
  v46 = 92;
  v47 = 11;
  v48 = 255;
  v57 = 0x1000000;
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v31 = 0;
  v36 = L"GetCurrentAccessToken";
  v32 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v33 = L"SECSECRC";
  v34 = 92;
  v35 = 11;
  TickCount = GetTickCount();
  v30[1] = -1;
  v39 = 255;
  v30[0] = 0;
  v42 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v41 = 0;
  v60 = 0;
  if ( (int)VssGetTracingContextPerThread(&v60) < 0 || (int)VssSetTracingContextPerThread(v30) < 0 )
  {
    v6 = v42;
  }
  else
  {
    v6 = v60;
    v42 = v60;
  }
  if ( v6 )
    v37 = *(_DWORD *)(v6 + 48) + 1;
  else
    v37 = 0;
  v7 = 160;
  v8 = 160;
  if ( v39 != 255 )
    v8 = v39;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v30, v35) )
    VssTraceMessage(v32, v33, v34, v37, v35, v36, L"ENTER", v8, 0);
  for ( i = 0; i != 15; ++i )
  {
    v10 = v49[i];
    if ( v10 )
    {
      CoTaskMemFree(v10);
      v49[i] = 0;
    }
  }
  if ( a1 )
  {
    v11 = CoImpersonateClient();
    v31 = v11;
    if ( v11 < 0 )
    {
      if ( v11 != -2147417833 )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 107;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateGenericError(v30, &v43, (unsigned int)v11, L"CoImpersonateClient");
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 0xAu, a3) )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 112;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateWin32Error(v30, &v43, L"OpenProcessToken");
      }
      if ( a2 )
      {
        v59 = 0;
        v58 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
        v21 = *a3;
        CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v58);
        v59 = v21;
        if ( !DuplicateToken(v21, SecurityIdentification, a3) )
        {
          v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
          v44 = L"GetCurrentAccessToken";
          v45 = L"SECSECRC";
          v46 = 121;
          v47 = 11;
          v48 = 255;
          v57 = 0x1000000;
          memset_0(v49, 0, 0x78u);
          CVssFunctionTracer::TranslateWin32Error(v30, &v43, L"DuplicateToken(..., SecurityIdentification, ...)");
        }
        v58 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
        CVssAutoGenericValue_Storage<void *,0,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>::Close(&v58);
      }
      v31 = 0;
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)v30,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        L"FALSE");
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      CoTaskMemFree(v41[0]);
      v41[0] = 0;
      CoTaskMemFree(v41[1]);
      v41[1] = 0;
      v19 = GetTickCount() - TickCount;
      if ( v39 != 255 )
        v7 = v39;
      LODWORD(v29) = v19;
      LODWORD(v28) = v19 % 0x3E8;
      LODWORD(v27) = v19 / 0x3E8 % 0x3C;
      LODWORD(v26) = v19 / 0xEA60 % 0x3C;
      LODWORD(v25) = v19 / 0x36EE80 % 0x3C;
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)v30,
        L"EXIT",
        v7,
        L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
        v25,
        v26,
        v27,
        v28,
        v29,
        v31);
      VssSetTracingContextPerThread(v42);
      return 0;
    }
    else
    {
      CurrentThread = GetCurrentThread();
      v13 = OpenThreadToken(CurrentThread, 8u, 1, a3);
      LastError = GetLastError();
      v15 = LastError;
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      v31 = CoRevertToSelf();
      if ( v31 < 0 )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 140;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateWin32Error(v30, &v43, L"CoRevertToSelf");
      }
      if ( !v13 )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 143;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateGenericError(v30, &v43, v15, L"OpenThreadToken");
      }
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)v30,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        L"TRUE");
      CoTaskMemFree(pv[0]);
      pv[0] = 0;
      CoTaskMemFree(pv[1]);
      pv[1] = 0;
      CoTaskMemFree(v41[0]);
      v41[0] = 0;
      CoTaskMemFree(v41[1]);
      v41[1] = 0;
      v16 = GetTickCount() - TickCount;
      if ( v39 != 255 )
        v7 = v39;
      LODWORD(v29) = v16;
      LODWORD(v28) = v16 % 0x3E8;
      LODWORD(v27) = v16 / 0x3E8 % 0x3C;
      LODWORD(v26) = v16 / 0xEA60 % 0x3C;
      LODWORD(v24) = v16 / 0x36EE80 % 0x3C;
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)v30,
        L"EXIT",
        v7,
        L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
        v24,
        v26,
        v27,
        v28,
        v29,
        v31);
      VssSetTracingContextPerThread(v42);
      return 1;
    }
  }
  else
  {
    v20 = GetCurrentThread();
    if ( OpenThreadToken(v20, 8u, 1, a3) )
    {
      CVssFunctionTracer::TraceInternalWithFormat(
        (CVssFunctionTracer *)v30,
        L"RETURN",
        0xAAu,
        L"Returning BOOL: %s",
        L"TRUE");
      CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v30);
      return 1;
    }
    else
    {
      if ( GetLastError() != 1008 )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 174;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateWin32Error(v30, &v43, L"OpenThreadToken");
      }
      v22 = GetCurrentProcess();
      if ( !OpenProcessToken(v22, 8u, a3) )
      {
        v43 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
        v44 = L"GetCurrentAccessToken";
        v45 = L"SECSECRC";
        v46 = 182;
        v47 = 11;
        v48 = 255;
        v57 = 0x1000000;
        memset_0(v49, 0, 0x78u);
        CVssFunctionTracer::TranslateWin32Error(v30, &v43, L"OpenProcessToken");
      }
      v23 = CVssFunctionTracer::Exit((CVssFunctionTracer *)v30, 0);
      CVssFunctionTracer::~CVssFunctionTracer((CVssFunctionTracer *)v30);
      return v23;
    }
  }
}

```

## disassembly

```asm
0x140030e90  push    rbp
0x140030e92  push    rbx
0x140030e93  push    rsi
0x140030e94  push    rdi
0x140030e95  push    r12
0x140030e97  push    r13
0x140030e99  push    r14
0x140030e9b  push    r15
0x140030e9d  lea     rbp, [rsp-88h]
0x140030ea5  sub     rsp, 188h
0x140030eac  mov     r14, r8
0x140030eaf  movzx   r15d, dl
0x140030eb3  movzx   edi, cl
0x140030eb6  lea     rcx, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x140030ebd  mov     [rbp+0C0h+var_100], rcx
0x140030ec1  lea     rdx, aGetcurrentacce; "GetCurrentAccessToken"
0x140030ec8  mov     [rbp+0C0h+var_F8], rdx
0x140030ecc  lea     r8, aSecsecrc; "SECSECRC"
0x140030ed3  mov     [rbp+0C0h+var_F0], r8
0x140030ed7  mov     [rbp+0C0h+var_E8], 5Ch ; '\'
0x140030ede  mov     [rbp+0C0h+var_E4], 0Bh
0x140030ee5  mov     [rbp+0C0h+var_E0], 0FFh
0x140030eec  xor     r12d, r12d
0x140030eef  mov     [rbp+0C0h+var_60], 1000000h
0x140030ef6  xorps   xmm0, xmm0
0x140030ef9  xor     eax, eax
0x140030efb  movups  xmmword ptr [rbp+0C0h+var_D8], xmm0
0x140030eff  movups  [rbp+0C0h+var_C8], xmm0
0x140030f03  movups  [rbp+0C0h+var_B8], xmm0
0x140030f07  movups  [rbp+0C0h+var_A8], xmm0
0x140030f0b  movups  [rbp+0C0h+var_98], xmm0
0x140030f0f  movups  [rbp+0C0h+var_88], xmm0
0x140030f13  movups  [rbp+0C0h+var_78], xmm0
0x140030f17  mov     [rbp+0C0h+var_68], rax
0x140030f1b  mov     [rsp+1C0h+var_168], r12d
0x140030f20  mov     [rsp+1C0h+var_148], rdx
0x140030f25  mov     [rsp+1C0h+var_160], rcx
0x140030f2a  mov     [rsp+1C0h+var_158], r8
0x140030f2f  mov     [rsp+1C0h+var_150], 5Ch ; '\'
0x140030f37  mov     [rsp+1C0h+var_14C], 0Bh
0x140030f3f  call    cs:__imp_GetTickCount
0x140030f45  mov     [rbp+0C0h+var_13C], eax
0x140030f48  mov     [rsp+1C0h+var_16C], 0FFFFFFFFh
0x140030f50  mov     [rbp+0C0h+var_138], 0FFh
0x140030f57  mov     [rsp+1C0h+var_170], r12d
0x140030f5c  mov     [rbp+0C0h+var_110], r12
0x140030f60  xorps   xmm0, xmm0
0x140030f63  movdqa  xmmword ptr [rbp+0C0h+pv], xmm0
0x140030f68  xorps   xmm1, xmm1
0x140030f6b  movdqa  xmmword ptr [rbp+0C0h+var_120], xmm1
0x140030f70  mov     [rbp+0C0h+arg_18], r12
0x140030f77  lea     rcx, [rbp+0C0h+arg_18]
0x140030f7e  call    cs:__imp_VssGetTracingContextPerThread
0x140030f84  test    eax, eax
0x140030f86  jns     loc_14003119B
0x140030f8c  mov     rax, [rbp+0C0h+var_110]
0x140030f90  test    rax, rax
0x140030f93  jz      loc_140031385
0x140030f99  mov     eax, [rax+30h]
0x140030f9c  inc     eax
0x140030f9e  mov     [rbp+0C0h+var_140], eax
0x140030fa1  mov     esi, 0A0h
0x140030fa6  mov     ebx, esi
0x140030fa8  cmp     [rbp+0C0h+var_138], 0FFh
0x140030faf  cmovnz  ebx, [rbp+0C0h+var_138]
0x140030fb3  mov     edx, [rsp+1C0h+var_14C]; unsigned int
0x140030fb7  lea     rcx, [rsp+1C0h+var_170]; this
0x140030fbc  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x140030fc1  test    eax, eax
0x140030fc3  jnz     loc_14003138E
0x140030fc9  mov     rbx, r12
0x140030fcc  nop     dword ptr [rax+00h]
0x140030fd0  mov     rcx, [rbp+rbx*8+0C0h+var_D8]; pv
0x140030fd5  test    rcx, rcx
0x140030fd8  jnz     loc_14003118B
0x140030fde  inc     rbx
0x140030fe1  cmp     rbx, 0Fh
0x140030fe5  jnz     short loc_140030FD0
0x140030fe7  test    dil, dil
0x140030fea  jz      loc_140031324
0x140030ff0  call    cs:__imp_CoImpersonateClient
0x140030ff6  mov     ebx, eax
0x140030ff8  mov     [rsp+1C0h+var_168], eax
0x140030ffc  test    eax, eax
0x140030ffe  js      loc_1400311BE
0x140031004  call    cs:__imp_GetCurrentThread
0x14003100a  mov     rcx, rax; ThreadHandle
0x14003100d  mov     r9, r14; TokenHandle
0x140031010  mov     edx, 8; DesiredAccess
0x140031015  mov     r8d, 1; OpenAsSelf
0x14003101b  call    cs:__imp_OpenThreadToken
0x140031021  mov     edi, eax
0x140031023  call    cs:__imp_GetLastError
0x140031029  mov     ebx, eax
0x14003102b  test    eax, eax
0x14003102d  jle     short loc_140031038
0x14003102f  movzx   ebx, ax
0x140031032  or      ebx, 80070000h
0x140031038  call    cs:__imp_CoRevertToSelf
0x14003103e  mov     [rsp+1C0h+var_168], eax
0x140031042  test    eax, eax
0x140031044  js      loc_140031548
0x14003104a  test    edi, edi
0x14003104c  jz      loc_1400315AC
0x140031052  lea     rax, aTrue; "TRUE"
0x140031059  mov     [rsp+1C0h+var_1A0], rax
0x14003105e  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x140031065  mov     r8d, 0AAh; unsigned int
0x14003106b  lea     rdx, aReturn; "RETURN"
0x140031072  lea     rcx, [rsp+1C0h+var_170]; this
0x140031077  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003107c  nop
0x14003107d  mov     rcx, [rbp+0C0h+pv]; pv
0x140031081  call    cs:__imp_CoTaskMemFree
0x140031087  mov     [rbp+0C0h+pv], r12
0x14003108b  mov     rcx, [rbp+0C0h+pv+8]; pv
0x14003108f  call    cs:__imp_CoTaskMemFree
0x140031095  mov     [rbp+0C0h+pv+8], r12
0x140031099  mov     rcx, [rbp+0C0h+var_120]; pv
0x14003109d  call    cs:__imp_CoTaskMemFree
0x1400310a3  mov     [rbp+0C0h+var_120], r12
0x1400310a7  mov     rcx, [rbp+0C0h+var_120+8]; pv
0x1400310ab  call    cs:__imp_CoTaskMemFree
0x1400310b1  mov     [rbp+0C0h+var_120+8], r12
0x1400310b5  call    cs:__imp_GetTickCount
0x1400310bb  mov     edi, eax
0x1400310bd  sub     edi, [rbp+0C0h+var_13C]
0x1400310c0  mov     eax, 10624DD3h
0x1400310c5  mul     edi
0x1400310c7  mov     ecx, edx
0x1400310c9  shr     ecx, 6
0x1400310cc  mov     eax, 88888889h
0x1400310d1  mul     ecx
0x1400310d3  shr     edx, 5
0x1400310d6  imul    eax, edx, 3Ch ; '<'
0x1400310d9  mov     ebx, ecx
0x1400310db  sub     ebx, eax
0x1400310dd  mov     eax, 45E7B273h
0x1400310e2  mul     edi
0x1400310e4  mov     r11d, edx
0x1400310e7  shr     r11d, 0Eh
0x1400310eb  mov     eax, 88888889h
0x1400310f0  mul     r11d
0x1400310f3  shr     edx, 5
0x1400310f6  imul    eax, edx, 3Ch ; '<'
0x1400310f9  sub     r11d, eax
0x1400310fc  mov     eax, 95217CB1h
0x140031101  mul     edi
0x140031103  mov     r10d, edx
0x140031106  shr     r10d, 15h
0x14003110a  mov     eax, 88888889h
0x14003110f  mul     r10d
0x140031112  shr     edx, 5
0x140031115  imul    eax, edx, 3Ch ; '<'
0x140031118  sub     r10d, eax
0x14003111b  mov     r9d, [rsp+1C0h+var_168]
0x140031120  cmp     [rbp+0C0h+var_138], 0FFh
0x140031127  cmovnz  esi, [rbp+0C0h+var_138]
0x14003112b  imul    eax, ecx, 3E8h
0x140031131  mov     ecx, edi
0x140031133  sub     ecx, eax
0x140031135  mov     [rsp+1C0h+var_178], r9d
0x14003113a  mov     dword ptr [rsp+1C0h+var_180], edi
0x14003113e  mov     dword ptr [rsp+1C0h+var_188], ecx
0x140031142  mov     dword ptr [rsp+1C0h+var_190], ebx
0x140031146  mov     dword ptr [rsp+1C0h+var_198], r11d
0x14003114b  mov     dword ptr [rsp+1C0h+var_1A0], r10d
0x140031150  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140031157  mov     r8d, esi; unsigned int
0x14003115a  lea     rdx, aExit; "EXIT"
0x140031161  lea     rcx, [rsp+1C0h+var_170]; this
0x140031166  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x14003116b  mov     rcx, [rbp+0C0h+var_110]
0x14003116f  call    cs:__imp_VssSetTracingContextPerThread
0x140031175  mov     al, 1
0x140031177  add     rsp, 188h
0x14003117e  pop     r15
0x140031180  pop     r14
0x140031182  pop     r13
0x140031184  pop     r12
0x140031186  pop     rdi
0x140031187  pop     rsi
0x140031188  pop     rbx
0x140031189  pop     rbp
0x14003118a  retn
0x14003118b  call    cs:__imp_CoTaskMemFree
0x140031191  mov     [rbp+rbx*8+0C0h+var_D8], r12
0x140031196  jmp     loc_140030FDE
0x14003119b  lea     rcx, [rsp+1C0h+var_170]
0x1400311a0  call    cs:__imp_VssSetTracingContextPerThread
0x1400311a6  test    eax, eax
0x1400311a8  js      loc_140030F8C
0x1400311ae  mov     rax, [rbp+0C0h+arg_18]
0x1400311b5  mov     [rbp+0C0h+var_110], rax
0x1400311b9  jmp     loc_140030F90
0x1400311be  cmp     ebx, 80010117h
0x1400311c4  jnz     loc_1400313D3
0x1400311ca  call    cs:__imp_GetCurrentProcess
0x1400311d0  mov     rcx, rax; ProcessHandle
0x1400311d3  mov     r8, r14; TokenHandle
0x1400311d6  mov     edx, 0Ah; DesiredAccess
0x1400311db  call    cs:__imp_OpenProcessToken
0x1400311e1  test    eax, eax
0x1400311e3  jz      loc_14003143A
0x1400311e9  test    r15b, r15b
0x1400311ec  jnz     loc_14003149E
0x1400311f2  mov     [rsp+1C0h+var_168], r12d
0x1400311f7  lea     rax, aFalse; "FALSE"
0x1400311fe  mov     [rsp+1C0h+var_1A0], rax
0x140031203  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x14003120a  mov     r8d, 0AAh; unsigned int
0x140031210  lea     rdx, aReturn; "RETURN"
0x140031217  lea     rcx, [rsp+1C0h+var_170]; this
0x14003121c  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140031221  nop
0x140031222  mov     rcx, [rbp+0C0h+pv]; pv
0x140031226  call    cs:__imp_CoTaskMemFree
0x14003122c  mov     [rbp+0C0h+pv], r12
0x140031230  mov     rcx, [rbp+0C0h+pv+8]; pv
0x140031234  call    cs:__imp_CoTaskMemFree
0x14003123a  mov     [rbp+0C0h+pv+8], r12
0x14003123e  mov     rcx, [rbp+0C0h+var_120]; pv
0x140031242  call    cs:__imp_CoTaskMemFree
0x140031248  mov     [rbp+0C0h+var_120], r12
0x14003124c  mov     rcx, [rbp+0C0h+var_120+8]; pv
0x140031250  call    cs:__imp_CoTaskMemFree
0x140031256  mov     [rbp+0C0h+var_120+8], r12
0x14003125a  call    cs:__imp_GetTickCount
0x140031260  mov     edi, eax
0x140031262  sub     edi, [rbp+0C0h+var_13C]
0x140031265  mov     eax, 10624DD3h
0x14003126a  mul     edi
0x14003126c  mov     ebx, edx
0x14003126e  shr     ebx, 6
0x140031271  mov     eax, 88888889h
0x140031276  mul     ebx
0x140031278  shr     edx, 5
0x14003127b  imul    eax, edx, 3Ch ; '<'
0x14003127e  mov     r11d, ebx
0x140031281  sub     r11d, eax
0x140031284  mov     eax, 45E7B273h
0x140031289  mul     edi
0x14003128b  mov     r10d, edx
0x14003128e  shr     r10d, 0Eh
0x140031292  mov     eax, 88888889h
0x140031297  mul     r10d
0x14003129a  shr     edx, 5
0x14003129d  imul    ecx, edx, 3Ch ; '<'
0x1400312a0  sub     r10d, ecx
0x1400312a3  mov     eax, 95217CB1h
0x1400312a8  mul     edi
0x1400312aa  mov     r9d, edx
0x1400312ad  shr     r9d, 15h
0x1400312b1  mov     eax, 88888889h
0x1400312b6  mul     r9d
0x1400312b9  shr     edx, 5
0x1400312bc  imul    eax, edx, 3Ch ; '<'
0x1400312bf  sub     r9d, eax
0x1400312c2  mov     r8d, [rsp+1C0h+var_168]
0x1400312c7  cmp     [rbp+0C0h+var_138], 0FFh
0x1400312ce  cmovnz  esi, [rbp+0C0h+var_138]
0x1400312d2  imul    eax, ebx, 3E8h
0x1400312d8  mov     ecx, edi
0x1400312da  sub     ecx, eax
0x1400312dc  mov     [rsp+1C0h+var_178], r8d
0x1400312e1  mov     dword ptr [rsp+1C0h+var_180], edi
0x1400312e5  mov     dword ptr [rsp+1C0h+var_188], ecx
0x1400312e9  mov     dword ptr [rsp+1C0h+var_190], r11d
0x1400312ee  mov     dword ptr [rsp+1C0h+var_198], r10d
0x1400312f3  mov     dword ptr [rsp+1C0h+var_1A0], r9d
0x1400312f8  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x1400312ff  mov     r8d, esi; unsigned int
0x140031302  lea     rdx, aExit; "EXIT"
0x140031309  lea     rcx, [rsp+1C0h+var_170]; this
0x14003130e  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140031313  mov     rcx, [rbp+0C0h+var_110]
0x140031317  call    cs:__imp_VssSetTracingContextPerThread
0x14003131d  xor     al, al
0x14003131f  jmp     loc_140031177
0x140031324  call    cs:__imp_GetCurrentThread
0x14003132a  mov     rcx, rax; ThreadHandle
0x14003132d  mov     r9, r14; TokenHandle
0x140031330  mov     edx, 8; DesiredAccess
0x140031335  mov     r8d, 1; OpenAsSelf
0x14003133b  call    cs:__imp_OpenThreadToken
0x140031341  test    eax, eax
0x140031343  jz      loc_140031613
0x140031349  lea     rax, aTrue; "TRUE"
0x140031350  mov     [rsp+1C0h+var_1A0], rax
0x140031355  lea     r9, aReturningBoolS; "Returning BOOL: %s"
0x14003135c  mov     r8d, 0AAh; unsigned int
0x140031362  lea     rdx, aReturn; "RETURN"
0x140031369  lea     rcx, [rsp+1C0h+var_170]; this
0x14003136e  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140031373  nop
0x140031374  lea     rcx, [rsp+1C0h+var_170]; this
0x140031379  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14003137e  mov     al, 1
0x140031380  jmp     loc_140031177
0x140031385  mov     [rbp+0C0h+var_140], r12d
  ... truncated ...
```
