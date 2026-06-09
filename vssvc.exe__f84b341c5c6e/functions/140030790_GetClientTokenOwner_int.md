# GetClientTokenOwner(int)

- ea: `0x140030790`
- end: `0x140030e88`
- name: `?GetClientTokenOwner@@YAPEAU_TOKEN_OWNER@@H@Z`
- size: `1784`
- prototype: `struct _TOKEN_OWNER *__fastcall(int)`
- caller_count: `7`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x14002e580`
- `0x14002f950`
- `0x140054e30`
- `0x140055590`
- `0x1400a7860`
- `0x1400a79c0`
- `0x1400a85f0`

## callees

- `0x140006020`
- `0x140010170`
- `0x1400138e0`
- `0x140013c60`
- `0x140015e38`
- `0x140030790`
- `0x140030e90`
- `0x1400326c0`
- `0x140032fcc`
- `0x1400330fc`
- `0x140070fcc`
- `0x140091560`
- `0x1400919a0`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030ce8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030949`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140030ce8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400309cd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400309cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030941`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400309a1`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140030941`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400309a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003083f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140030a20`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003083f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140030a20`
- `VssTrace!__imp_VssTraceMessage` at `0x140030d93`
- `VssTrace!__imp_VssTraceMessage` at `0x140030d93`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140030adc`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140030b1c`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140030adc`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x140030b1c`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003087a`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14003087a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400309ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400309fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030cd0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400309ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400309fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030a08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030a16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030b08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030cbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030cd0`

## string_xrefs

- `0x1400307bd`: `base\stor\vss\modules\sec\security.cxx`
- `0x1400307c9`: `GetClientTokenOwner`
- `0x140030b40`: `GetClientTokenOwner`
- `0x140030d02`: `GetClientTokenOwner`
- `0x140030d45`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _TOKEN_OWNER *__fastcall GetClientTokenOwner()
{
  __int64 v0; // rax
  unsigned int v1; // r15d
  unsigned int v2; // ebx
  __int64 i; // rbx
  void *v4; // rcx
  BOOL TokenInformation; // ebx
  DWORD LastError; // edi
  void *v7; // r14
  DWORD v8; // ebx
  DWORD v9; // esi
  __int64 j; // rbx
  void *v12; // rcx
  __int64 k; // rbx
  void *v14; // rcx
  DWORD v15; // ebx
  DWORD v16; // edi
  signed int v17; // eax
  unsigned int v18; // ebx
  CVssDebugInfo *v19; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-E0h]
  __int64 v22; // [rsp+28h] [rbp-D8h]
  __int64 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  __int64 v25; // [rsp+40h] [rbp-C0h]
  DWORD TokenInformationLength; // [rsp+50h] [rbp-B0h] BYREF
  __int64 pExceptionObject; // [rsp+58h] [rbp-A8h] BYREF
  DWORD v28; // [rsp+60h] [rbp-A0h] BYREF
  void **v29; // [rsp+68h] [rbp-98h]
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v31; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v32; // [rsp+80h] [rbp-80h]
  const unsigned __int16 *v33; // [rsp+88h] [rbp-78h]
  int v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+94h] [rbp-6Ch]
  int v36; // [rsp+98h] [rbp-68h]
  LPVOID v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int128 v39; // [rsp+C0h] [rbp-40h]
  __int128 v40; // [rsp+D0h] [rbp-30h]
  __int128 v41; // [rsp+E0h] [rbp-20h]
  __int128 v42; // [rsp+F0h] [rbp-10h]
  __int128 v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+110h] [rbp+10h]
  int v45; // [rsp+118h] [rbp+18h]
  _DWORD v46[2]; // [rsp+120h] [rbp+20h] BYREF
  int v47; // [rsp+128h] [rbp+28h]
  const unsigned __int16 *v48; // [rsp+130h] [rbp+30h]
  const unsigned __int16 *v49; // [rsp+138h] [rbp+38h]
  unsigned int v50; // [rsp+140h] [rbp+40h]
  unsigned int v51; // [rsp+144h] [rbp+44h]
  const wchar_t *v52; // [rsp+148h] [rbp+48h]
  unsigned int v53; // [rsp+150h] [rbp+50h]
  DWORD TickCount; // [rsp+154h] [rbp+54h]
  unsigned int v55; // [rsp+158h] [rbp+58h]
  LPVOID pv[2]; // [rsp+160h] [rbp+60h]
  LPVOID v57[2]; // [rsp+170h] [rbp+70h]
  __int64 v58; // [rsp+180h] [rbp+80h]
  void **v59; // [rsp+190h] [rbp+90h]
  void *v60; // [rsp+198h] [rbp+98h]
  _BYTE v61[40]; // [rsp+1A0h] [rbp+A0h] BYREF
  LPVOID v62[15]; // [rsp+1C8h] [rbp+C8h]
  char v63; // [rsp+243h] [rbp+143h]
  _BYTE v64[168]; // [rsp+248h] [rbp+148h] BYREF
  unsigned __int16 v65[32]; // [rsp+2F0h] [rbp+1F0h] BYREF

  v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v32 = L"GetClientTokenOwner";
  v33 = L"SECSECRC";
  v34 = 493;
  v35 = 11;
  v36 = 255;
  v45 = 0x1000000;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v47 = 0;
  v52 = L"GetClientTokenOwner";
  v48 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v49 = L"SECSECRC";
  v50 = 493;
  v51 = 11;
  TickCount = GetTickCount();
  v46[1] = -1;
  v55 = 255;
  v46[0] = 0;
  v58 = 0;
  *(_OWORD *)pv = 0;
  *(_OWORD *)v57 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 || (int)VssSetTracingContextPerThread(v46) < 0 )
  {
    v0 = v58;
  }
  else
  {
    v0 = pExceptionObject;
    v58 = pExceptionObject;
  }
  if ( v0 )
    v53 = *(_DWORD *)(v0 + 48) + 1;
  else
    v53 = 0;
  v1 = 160;
  v2 = 160;
  if ( v55 != 255 )
    v2 = v55;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)v46, v51) )
    VssTraceMessage(v48, v49, v50, v53, v51, v52, L"ENTER", v2, 0);
  for ( i = 0; i != 15; ++i )
  {
    v4 = v37[i];
    if ( v4 )
    {
      CoTaskMemFree(v4);
      v37[i] = 0;
    }
  }
  v29 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  v60 = 0;
  v59 = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
  v28 = 0;
  TokenInformationLength = 0;
  TokenHandle = (HANDLE)-1LL;
  GetCurrentAccessToken(1, 0, &TokenHandle);
  TokenInformation = GetTokenInformation(TokenHandle, TokenOwner, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError != 122 || TokenInformation )
  {
    v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v32 = L"GetClientTokenOwner";
    v33 = L"SECSECRC";
    v34 = 517;
    v35 = 11;
    v36 = 255;
    v45 = 0x1000000;
    memset_0(v37, 0, 0x78u);
    v19 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v31, (CVssDebugInfo *)v64, LastError);
    CVssFunctionTracer::LogError(v46, 8197, v19, 1);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v31);
    v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v32 = L"GetClientTokenOwner";
    v33 = L"SECSECRC";
    v34 = 519;
    v35 = 11;
    v36 = 255;
    v45 = 0x1000000;
    memset_0(v37, 0, 0x78u);
    LODWORD(ReturnLength) = LastError;
    CVssFunctionTracer::Throw(
      v46,
      &v31,
      2147754754LL,
      L"ERROR_INSUFFICIENT_BUFFER expected error . [0x%08lx]",
      ReturnLength);
  }
  v7 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v60 = v7;
  if ( !v7 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !GetTokenInformation(TokenHandle, TokenOwner, v7, TokenInformationLength, &v28) )
  {
    v17 = GetLastError();
    v18 = v17;
    if ( v17 > 0 )
      v18 = (unsigned __int16)v17 | 0x80070000;
    v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v32 = L"GetClientTokenOwner";
    v33 = L"SECSECRC";
    v34 = 540;
    v35 = 11;
    v36 = 255;
    v45 = 0x1000000;
    memset_0(v37, 0, 0x78u);
    CVssFunctionTracer::TranslateError(v46, &v31, v18, L"GetTokenInformation");
  }
  v8 = v28;
  if ( v28 > TokenInformationLength )
  {
    v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v32 = L"GetClientTokenOwner";
    v33 = L"SECSECRC";
    v34 = 547;
    v35 = 11;
    v36 = 255;
    v45 = 0x1000000;
    memset_0(v37, 0, 0x78u);
    StringCchPrintfW(v65, 0x1Fu, L"%d", v8);
    CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v31, (CVssDebugInfo *)v61, v65);
    StringCchPrintfW(v65, 0x1Fu, L"%d", TokenInformationLength);
    CVssDebugInfo::operator<<((struct CVssDebugInfo *)v61, (CVssDebugInfo *)v64, v65);
    CVssFunctionTracer::LogError(v46, 8198, v64, 1);
    if ( v63 )
    {
      for ( j = 0; j != 15; ++j )
      {
        v12 = v62[j];
        if ( v12 )
        {
          CoTaskMemFree(v12);
          v62[j] = 0;
        }
      }
    }
    if ( HIBYTE(v45) )
    {
      for ( k = 0; k != 15; ++k )
      {
        v14 = v37[k];
        if ( v14 )
        {
          CoTaskMemFree(v14);
          v37[k] = 0;
        }
      }
    }
    v15 = TokenInformationLength;
    v16 = v28;
    v31 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v32 = L"GetClientTokenOwner";
    v33 = L"SECSECRC";
    v34 = 549;
    v35 = 11;
    v36 = 255;
    v45 = 0x1000000;
    memset_0(v37, 0, 0x78u);
    LODWORD(v22) = v15;
    LODWORD(ReturnLengtha) = v16;
    CVssFunctionTracer::Throw(
      v46,
      &v31,
      2147754754LL,
      L"Unexpected error. Final buffer size = %lu, original size was %lu",
      ReturnLengtha,
      v22);
  }
  v29 = &CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&int CloseHandle(void *),void * & (*)(void * &),&public: static void * & DTyper<void *>::Identity(void * &)>>::`vftable';
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  TokenHandle = (HANDLE)-1LL;
  v29 = &CVssAutoGenericValue_Storage<unsigned char *,0,unsigned long (*)(void *),&unsigned long NetApiBufferFree(void *),unsigned char * & (*)(unsigned char * &),&public: static unsigned char * & DTyper<unsigned char *>::Identity(unsigned char * &)>::`vftable';
  CoTaskMemFree(pv[0]);
  pv[0] = 0;
  CoTaskMemFree(pv[1]);
  pv[1] = 0;
  CoTaskMemFree(v57[0]);
  v57[0] = 0;
  CoTaskMemFree(v57[1]);
  v57[1] = 0;
  v9 = GetTickCount() - TickCount;
  if ( v55 != 255 )
    v1 = v55;
  LODWORD(v25) = v9;
  LODWORD(v24) = v9 % 0x3E8;
  LODWORD(v23) = v9 / 0x3E8 % 0x3C;
  LODWORD(v22) = v9 / 0xEA60 % 0x3C;
  LODWORD(ReturnLengtha) = v9 / 0x36EE80 % 0x3C;
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)v46,
    L"EXIT",
    v1,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    ReturnLengtha,
    v22,
    v23,
    v24,
    v25,
    v47);
  VssSetTracingContextPerThread(v58);
  return (struct _TOKEN_OWNER *)v7;
}

```

## disassembly

```asm
0x140030790  push    rbp
0x140030792  push    rbx
0x140030793  push    rsi
0x140030794  push    rdi
0x140030795  push    r12
0x140030797  push    r13
0x140030799  push    r14
0x14003079b  push    r15
0x14003079d  lea     rbp, [rsp-248h]
0x1400307a5  sub     rsp, 348h
0x1400307ac  mov     rax, cs:__security_cookie
0x1400307b3  xor     rax, rsp
0x1400307b6  mov     [rbp+280h+var_50], rax
0x1400307bd  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x1400307c4  mov     [rsp+380h+var_308], r13
0x1400307c9  lea     r14, aGetclienttoken_0; "GetClientTokenOwner"
0x1400307d0  mov     [rbp+280h+var_300], r14
0x1400307d4  lea     rcx, aSecsecrc; "SECSECRC"
0x1400307db  mov     [rbp+280h+var_2F8], rcx
0x1400307df  mov     [rbp+280h+var_2F0], 1EDh
0x1400307e6  mov     [rbp+280h+var_2EC], 0Bh
0x1400307ed  mov     [rbp+280h+var_2E8], 0FFh
0x1400307f4  xor     esi, esi
0x1400307f6  mov     [rbp+280h+var_268], 1000000h
0x1400307fd  xorps   xmm0, xmm0
0x140030800  xor     eax, eax
0x140030802  movups  xmmword ptr [rbp+280h+var_2E0], xmm0
0x140030806  movups  [rbp+280h+var_2D0], xmm0
0x14003080a  movups  [rbp+280h+var_2C0], xmm0
0x14003080e  movups  [rbp+280h+var_2B0], xmm0
0x140030812  movups  [rbp+280h+var_2A0], xmm0
0x140030816  movups  [rbp+280h+var_290], xmm0
0x14003081a  movups  [rbp+280h+var_280], xmm0
0x14003081e  mov     [rbp+280h+var_270], rax
0x140030822  mov     [rbp+280h+var_258], esi
0x140030825  mov     [rbp+280h+var_238], r14
0x140030829  mov     [rbp+280h+var_250], r13
0x14003082d  mov     [rbp+280h+var_248], rcx
0x140030831  mov     [rbp+280h+var_240], 1EDh
0x140030838  mov     [rbp+280h+var_23C], 0Bh
0x14003083f  call    cs:__imp_GetTickCount
0x140030845  mov     [rbp+280h+var_22C], eax
0x140030848  mov     [rbp+280h+var_25C], 0FFFFFFFFh
0x14003084f  mov     [rbp+280h+var_228], 0FFh
0x140030856  mov     [rbp+280h+var_260], esi
0x140030859  mov     [rbp+280h+var_200], rsi
0x140030860  xorps   xmm0, xmm0
0x140030863  movdqa  xmmword ptr [rbp+280h+pv], xmm0
0x140030868  xorps   xmm1, xmm1
0x14003086b  movdqa  xmmword ptr [rbp+280h+var_210], xmm1
0x140030870  mov     [rsp+380h+pExceptionObject], rsi
0x140030875  lea     rcx, [rsp+380h+pExceptionObject]
0x14003087a  call    cs:__imp_VssGetTracingContextPerThread
0x140030880  test    eax, eax
0x140030882  jns     loc_140030B18
0x140030888  mov     rax, [rbp+280h+var_200]
0x14003088f  test    rax, rax
0x140030892  jz      loc_140030CE0
0x140030898  mov     eax, [rax+30h]
0x14003089b  inc     eax
0x14003089d  mov     [rbp+280h+var_230], eax
0x1400308a0  mov     r15d, 0A0h
0x1400308a6  mov     ebx, r15d
0x1400308a9  cmp     [rbp+280h+var_228], 0FFh
0x1400308b0  cmovnz  ebx, [rbp+280h+var_228]
0x1400308b4  mov     edx, [rbp+280h+var_23C]; unsigned int
0x1400308b7  lea     rcx, [rbp+280h+var_260]; this
0x1400308bb  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x1400308c0  test    eax, eax
0x1400308c2  jnz     loc_140030D5E
0x1400308c8  mov     rbx, rsi
0x1400308cb  nop     dword ptr [rax+rax+00h]
0x1400308d0  mov     rcx, [rbp+rbx*8+280h+var_2E0]; pv
0x1400308d5  test    rcx, rcx
0x1400308d8  jnz     loc_140030B08
0x1400308de  inc     rbx
0x1400308e1  cmp     rbx, 0Fh
0x1400308e5  jnz     short loc_1400308D0
0x1400308e7  lea     r12, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x1400308ee  mov     [rsp+380h+var_318], r12
0x1400308f3  mov     [rbp+280h+var_1E8], rsi
0x1400308fa  lea     rax, ??_7?$CVssAuto@PEAPEAGV?$CVssAutoCppPtr_Storage@PEAPEAG@@@@6B@; const CVssAuto<ushort * *,CVssAutoCppPtr_Storage<ushort * *>>::`vftable'
0x140030901  mov     [rbp+280h+var_1F0], rax
0x140030908  mov     [rsp+380h+var_320], esi
0x14003090c  mov     [rsp+380h+TokenInformationLength], esi
0x140030910  mov     [rsp+380h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140030919  lea     r8, [rsp+380h+TokenHandle]; void **
0x14003091e  xor     edx, edx; bool
0x140030920  mov     cl, 1; bool
0x140030922  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x140030927  lea     rax, [rsp+380h+TokenInformationLength]
0x14003092c  mov     [rsp+380h+ReturnLength], rax; ReturnLength
0x140030931  xor     r9d, r9d; TokenInformationLength
0x140030934  xor     r8d, r8d; TokenInformation
0x140030937  mov     edx, 4; TokenInformationClass
0x14003093c  mov     rcx, [rsp+380h+TokenHandle]; TokenHandle
0x140030941  call    cs:__imp_GetTokenInformation
0x140030947  mov     ebx, eax
0x140030949  call    cs:__imp_GetLastError
0x14003094f  mov     edi, eax
0x140030951  cmp     eax, 7Ah ; 'z'
0x140030954  jnz     loc_140030DB8
0x14003095a  test    ebx, ebx
0x14003095c  jnz     loc_140030DB8
0x140030962  mov     ecx, [rsp+380h+TokenInformationLength]; unsigned __int64
0x140030966  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003096d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140030972  mov     r14, rax
0x140030975  mov     [rbp+280h+var_1E8], rax
0x14003097c  test    rax, rax
0x14003097f  jz      loc_140030D9E
0x140030985  lea     rax, [rsp+380h+var_320]
0x14003098a  mov     [rsp+380h+ReturnLength], rax; ReturnLength
0x14003098f  mov     r9d, [rsp+380h+TokenInformationLength]; TokenInformationLength
0x140030994  mov     r8, r14; TokenInformation
0x140030997  mov     edx, 4; TokenInformationClass
0x14003099c  mov     rcx, [rsp+380h+TokenHandle]; TokenHandle
0x1400309a1  call    cs:__imp_GetTokenInformation
0x1400309a7  test    eax, eax
0x1400309a9  jz      loc_140030CE8
0x1400309af  mov     ebx, [rsp+380h+var_320]
0x1400309b3  cmp     ebx, [rsp+380h+TokenInformationLength]
0x1400309b7  ja      loc_140030B3B
0x1400309bd  mov     [rsp+380h+var_318], r12
0x1400309c2  mov     rcx, [rsp+380h+TokenHandle]; hObject
0x1400309c7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400309cb  jz      short loc_1400309D3
0x1400309cd  call    cs:__imp_CloseHandle
0x1400309d3  mov     [rsp+380h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1400309dc  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x1400309e3  mov     [rsp+380h+var_318], rax
0x1400309e8  mov     rcx, [rbp+280h+pv]; pv
0x1400309ec  call    cs:__imp_CoTaskMemFree
0x1400309f2  mov     [rbp+280h+pv], rsi
0x1400309f6  mov     rcx, [rbp+280h+pv+8]; pv
0x1400309fa  call    cs:__imp_CoTaskMemFree
0x140030a00  mov     [rbp+280h+pv+8], rsi
0x140030a04  mov     rcx, [rbp+280h+var_210]; pv
0x140030a08  call    cs:__imp_CoTaskMemFree
0x140030a0e  mov     [rbp+280h+var_210], rsi
0x140030a12  mov     rcx, [rbp+280h+var_210+8]; pv
0x140030a16  call    cs:__imp_CoTaskMemFree
0x140030a1c  mov     [rbp+280h+var_210+8], rsi
0x140030a20  call    cs:__imp_GetTickCount
0x140030a26  mov     esi, eax
0x140030a28  sub     esi, [rbp+280h+var_22C]
0x140030a2b  mov     eax, 10624DD3h
0x140030a30  mul     esi
0x140030a32  mov     edi, edx
0x140030a34  shr     edi, 6
0x140030a37  mov     eax, 88888889h
0x140030a3c  mul     edi
0x140030a3e  shr     edx, 5
0x140030a41  imul    ecx, edx, 3Ch ; '<'
0x140030a44  mov     ebx, edi
0x140030a46  sub     ebx, ecx
0x140030a48  mov     eax, 45E7B273h
0x140030a4d  mul     esi
0x140030a4f  mov     r11d, edx
0x140030a52  shr     r11d, 0Eh
0x140030a56  mov     eax, 88888889h
0x140030a5b  mul     r11d
0x140030a5e  shr     edx, 5
0x140030a61  imul    ecx, edx, 3Ch ; '<'
0x140030a64  sub     r11d, ecx
0x140030a67  mov     eax, 95217CB1h
0x140030a6c  mul     esi
0x140030a6e  mov     r10d, edx
0x140030a71  shr     r10d, 15h
0x140030a75  mov     eax, 88888889h
0x140030a7a  mul     r10d
0x140030a7d  shr     edx, 5
0x140030a80  imul    eax, edx, 3Ch ; '<'
0x140030a83  sub     r10d, eax
0x140030a86  mov     r9d, [rbp+280h+var_258]
0x140030a8a  cmp     [rbp+280h+var_228], 0FFh
0x140030a91  cmovnz  r15d, [rbp+280h+var_228]
0x140030a96  imul    eax, edi, 3E8h
0x140030a9c  mov     ecx, esi
0x140030a9e  sub     ecx, eax
0x140030aa0  mov     [rsp+380h+var_338], r9d
0x140030aa5  mov     dword ptr [rsp+380h+var_340], esi
0x140030aa9  mov     dword ptr [rsp+380h+var_348], ecx
0x140030aad  mov     dword ptr [rsp+380h+var_350], ebx
0x140030ab1  mov     dword ptr [rsp+380h+var_358], r11d
0x140030ab6  mov     dword ptr [rsp+380h+ReturnLength], r10d
0x140030abb  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x140030ac2  mov     r8d, r15d; unsigned int
0x140030ac5  lea     rdx, aExit; "EXIT"
0x140030acc  lea     rcx, [rbp+280h+var_260]; this
0x140030ad0  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x140030ad5  mov     rcx, [rbp+280h+var_200]
0x140030adc  call    cs:__imp_VssSetTracingContextPerThread
0x140030ae2  mov     rax, r14
0x140030ae5  mov     rcx, [rbp+280h+var_50]
0x140030aec  xor     rcx, rsp; StackCookie
0x140030aef  call    __security_check_cookie
0x140030af4  add     rsp, 348h
0x140030afb  pop     r15
0x140030afd  pop     r14
0x140030aff  pop     r13
0x140030b01  pop     r12
0x140030b03  pop     rdi
0x140030b04  pop     rsi
0x140030b05  pop     rbx
0x140030b06  pop     rbp
0x140030b07  retn
0x140030b08  call    cs:__imp_CoTaskMemFree
0x140030b0e  mov     [rbp+rbx*8+280h+var_2E0], rsi
0x140030b13  jmp     loc_1400308DE
0x140030b18  lea     rcx, [rbp+280h+var_260]
0x140030b1c  call    cs:__imp_VssSetTracingContextPerThread
0x140030b22  test    eax, eax
0x140030b24  js      loc_140030888
0x140030b2a  mov     rax, [rsp+380h+pExceptionObject]
0x140030b2f  mov     [rbp+280h+var_200], rax
0x140030b36  jmp     loc_14003088F
0x140030b3b  mov     [rsp+380h+var_308], r13
0x140030b40  lea     r14, aGetclienttoken_0; "GetClientTokenOwner"
0x140030b47  mov     [rbp+280h+var_300], r14
0x140030b4b  lea     r15, aSecsecrc; "SECSECRC"
0x140030b52  mov     [rbp+280h+var_2F8], r15
0x140030b56  mov     [rbp+280h+var_2F0], 223h
0x140030b5d  mov     [rbp+280h+var_2EC], 0Bh
0x140030b64  mov     [rbp+280h+var_2E8], 0FFh
0x140030b6b  mov     [rbp+280h+var_268], 1000000h
0x140030b72  xor     edx, edx; Val
0x140030b74  mov     r8d, 78h ; 'x'; Size
0x140030b7a  lea     rcx, [rbp+280h+var_2E0]; void *
0x140030b7e  call    memset_0
0x140030b83  mov     r9d, ebx
0x140030b86  lea     r8, aD; "%d"
0x140030b8d  mov     edx, 1Fh; unsigned __int64
0x140030b92  lea     rcx, [rbp+280h+var_90]; unsigned __int16 *
0x140030b99  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030b9e  lea     r8, [rbp+280h+var_90]
0x140030ba5  lea     rdx, [rbp+280h+var_1E0]; this
0x140030bac  lea     rcx, [rsp+380h+var_308]; struct CVssDebugInfo *
0x140030bb1  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x140030bb6  mov     r9d, [rsp+380h+TokenInformationLength]
0x140030bbb  lea     r8, aD; "%d"
0x140030bc2  mov     edx, 1Fh; unsigned __int64
0x140030bc7  lea     rcx, [rbp+280h+var_90]; unsigned __int16 *
0x140030bce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140030bd3  lea     r8, [rbp+280h+var_90]
0x140030bda  lea     rdx, [rbp+280h+var_138]; this
0x140030be1  lea     rcx, [rbp+280h+var_1E0]; struct CVssDebugInfo *
0x140030be8  call    ??6CVssDebugInfo@@QEAA?AU0@PEBG@Z; CVssDebugInfo::operator<<(ushort const *)
0x140030bed  mov     r9d, 1
0x140030bf3  lea     r8, [rbp+280h+var_138]
0x140030bfa  mov     edx, 2006h
0x140030bff  lea     rcx, [rbp+280h+var_260]
0x140030c03  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x140030c08  cmp     [rbp+280h+var_13D], 0
0x140030c0f  jz      short loc_140030C2E
0x140030c11  mov     rbx, rsi
0x140030c14  mov     rcx, [rbp+rbx*8+280h+var_1B8]; pv
0x140030c1c  test    rcx, rcx
0x140030c1f  jnz     loc_140030CBD
0x140030c25  inc     rbx
0x140030c28  cmp     rbx, 0Fh
0x140030c2c  jnz     short loc_140030C14
0x140030c2e  cmp     byte ptr [rbp+280h+var_268+3], 0
0x140030c32  jz      short loc_140030C57
0x140030c34  mov     rbx, rsi
0x140030c37  nop     word ptr [rax+rax+00000000h]
0x140030c40  mov     rcx, [rbp+rbx*8+280h+var_2E0]; pv
0x140030c45  test    rcx, rcx
0x140030c48  jnz     loc_140030CD0
0x140030c4e  inc     rbx
0x140030c51  cmp     rbx, 0Fh
0x140030c55  jnz     short loc_140030C40
0x140030c57  mov     ebx, [rsp+380h+TokenInformationLength]
0x140030c5b  mov     edi, [rsp+380h+var_320]
0x140030c5f  mov     [rsp+380h+var_308], r13
0x140030c64  mov     [rbp+280h+var_300], r14
0x140030c68  mov     [rbp+280h+var_2F8], r15
0x140030c6c  mov     [rbp+280h+var_2F0], 225h
0x140030c73  mov     [rbp+280h+var_2EC], 0Bh
0x140030c7a  mov     [rbp+280h+var_2E8], 0FFh
0x140030c81  mov     [rbp+280h+var_268], 1000000h
0x140030c88  xor     edx, edx; Val
0x140030c8a  mov     r8d, 78h ; 'x'; Size
0x140030c90  lea     rcx, [rbp+280h+var_2E0]; void *
0x140030c94  call    memset_0
0x140030c99  mov     dword ptr [rsp+380h+var_358], ebx
0x140030c9d  mov     dword ptr [rsp+380h+ReturnLength], edi
0x140030ca1  lea     r9, aUnexpectedErro_4; "Unexpected error. Final buffer size = %"...
0x140030ca8  mov     r8d, 80042302h
0x140030cae  lea     rdx, [rsp+380h+var_308]
0x140030cb3  lea     rcx, [rbp+280h+var_260]
0x140030cb7  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140030cbd  call    cs:__imp_CoTaskMemFree
0x140030cc3  mov     [rbp+rbx*8+280h+var_1B8], rsi
0x140030ccb  jmp     loc_140030C25
0x140030cd0  call    cs:__imp_CoTaskMemFree
0x140030cd6  mov     [rbp+rbx*8+280h+var_2E0], rsi
0x140030cdb  jmp     loc_140030C4E
0x140030ce0  mov     [rbp+280h+var_230], esi
0x140030ce3  jmp     loc_1400308A0
  ... truncated ...
```
