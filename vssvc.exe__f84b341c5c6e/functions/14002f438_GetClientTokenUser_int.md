# GetClientTokenUser(int)

- ea: `0x14002f438`
- end: `0x14002f949`
- name: `?GetClientTokenUser@@YAPEAU_TOKEN_USER@@H@Z`
- size: `1297`
- prototype: `struct _TOKEN_USER *__fastcall(int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14002e7f4`

## callees

- `0x140006020`
- `0x1400137c0`
- `0x140013cb0`
- `0x140015e38`
- `0x14002f438`
- `0x140030e90`
- `0x140032fcc`
- `0x1400330fc`
- `0x14005632c`
- `0x140070fcc`
- `0x1400919a0`
- `0x1400921dc`
- `0x1400921e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f612`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f694`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f83f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002f83f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f60a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f68a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f60a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002f68a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002f4d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14002f4d7`
- `VssTrace!__imp_VssTraceMessage` at `0x14002f59a`
- `VssTrace!__imp_VssTraceMessage` at `0x14002f59a`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002f51b`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x14002f51b`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002f50d`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x14002f50d`

## string_xrefs

- `0x14002f455`: `base\stor\vss\modules\sec\security.cxx`
- `0x14002f461`: `GetClientTokenUser`
- `0x14002f6ae`: `GetClientTokenUser`
- `0x14002f720`: `GetClientTokenUser`
- `0x14002f879`: `GetClientTokenUser`
- `0x14002f6f0`: `GetTokenInformation`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _TOKEN_USER *__fastcall GetClientTokenUser(DWORD a1)
{
  int v1; // eax
  __int64 v2; // rcx
  int v3; // ebx
  BOOL TokenInformation; // edi
  DWORD LastError; // ebx
  void *v6; // rbx
  signed int v7; // eax
  unsigned int v8; // ebx
  struct CVssDebugInfo *v9; // rax
  __int64 v10; // rax
  DWORD v11; // ebx
  DWORD v12; // edi
  CVssDebugInfo *v14; // rax
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  PDWORD ReturnLengtha; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+28h] [rbp-D8h]
  HANDLE TokenHandle; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v19; // [rsp+60h] [rbp-A0h] BYREF
  const wchar_t *v20; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v21; // [rsp+70h] [rbp-90h]
  int v22; // [rsp+78h] [rbp-88h]
  int v23; // [rsp+7Ch] [rbp-84h]
  int v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[120]; // [rsp+88h] [rbp-78h] BYREF
  int v26; // [rsp+100h] [rbp+0h]
  unsigned __int64 v27; // [rsp+110h] [rbp+10h] BYREF
  int v28; // [rsp+118h] [rbp+18h]
  const unsigned __int16 *v29; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v30; // [rsp+128h] [rbp+28h]
  unsigned int v31; // [rsp+130h] [rbp+30h]
  int v32; // [rsp+134h] [rbp+34h]
  const wchar_t *v33; // [rsp+138h] [rbp+38h]
  unsigned int v34; // [rsp+140h] [rbp+40h]
  DWORD TickCount; // [rsp+144h] [rbp+44h]
  int v36; // [rsp+148h] [rbp+48h]
  __int128 v37; // [rsp+150h] [rbp+50h]
  __int128 v38; // [rsp+160h] [rbp+60h]
  __int64 v39; // [rsp+170h] [rbp+70h]
  void **v40; // [rsp+180h] [rbp+80h]
  void *v41; // [rsp+188h] [rbp+88h]
  _BYTE v42[168]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v43[216]; // [rsp+238h] [rbp+138h] BYREF
  DWORD TokenInformationLength; // [rsp+320h] [rbp+220h] BYREF
  DWORD v45; // [rsp+328h] [rbp+228h] BYREF
  __int64 pExceptionObject; // [rsp+330h] [rbp+230h] BYREF

  TokenInformationLength = a1;
  v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v20 = L"GetClientTokenUser";
  v21 = L"SECSECRC";
  v22 = 395;
  v23 = 11;
  v24 = 255;
  v26 = 0x1000000;
  memset_0(v25, 0, sizeof(v25));
  v28 = 0;
  v33 = L"GetClientTokenUser";
  v29 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
  v30 = L"SECSECRC";
  v31 = 395;
  v32 = 11;
  TickCount = GetTickCount();
  v36 = 255;
  v27 = 0xFFFFFFFF00000000uLL;
  v39 = 0;
  v37 = 0;
  v38 = 0;
  pExceptionObject = 0;
  if ( (int)VssGetTracingContextPerThread(&pExceptionObject) < 0 )
  {
    v2 = v39;
  }
  else
  {
    v1 = VssSetTracingContextPerThread(&v27);
    v2 = v39;
    if ( v1 >= 0 )
      v2 = pExceptionObject;
    v39 = v2;
  }
  if ( v2 )
    v34 = *(_DWORD *)(v2 + 48) + 1;
  else
    v34 = 0;
  v3 = 160;
  if ( v36 != 255 )
    v3 = v36;
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled((CVssFunctionTracer *)&v27) )
    VssTraceMessage(v29, v30, v31, v34, v32, v33, L"ENTER", v3, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v19);
  v41 = 0;
  v40 = &CVssAuto<unsigned short * *,CVssAutoCppPtr_Storage<unsigned short * *>>::`vftable';
  v45 = 0;
  TokenInformationLength = 0;
  TokenHandle = (HANDLE)-1LL;
  GetCurrentAccessToken(1, 0, &TokenHandle);
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LastError = GetLastError();
  if ( LastError != 122 || TokenInformation )
  {
    v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v20 = L"GetClientTokenUser";
    v21 = L"SECSECRC";
    v22 = 419;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    v14 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v19, (CVssDebugInfo *)v42, LastError);
    CVssFunctionTracer::LogError(&v27, 8197, v14, 1);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v19);
    v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v20 = L"GetClientTokenUser";
    v21 = L"SECSECRC";
    v22 = 421;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    LODWORD(ReturnLength) = LastError;
    CVssFunctionTracer::Throw(
      &v27,
      &v19,
      2147754754LL,
      L"ERROR_INSUFFICIENT_BUFFER expected error . [0x%08lx]",
      ReturnLength);
  }
  v6 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  v41 = v6;
  if ( !v6 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
  if ( !GetTokenInformation(TokenHandle, TokenUser, v6, TokenInformationLength, &v45) )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v20 = L"GetClientTokenUser";
    v21 = L"SECSECRC";
    v22 = 442;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    CVssFunctionTracer::TranslateError(&v27, &v19, v8, L"GetTokenInformation");
  }
  if ( v45 > TokenInformationLength )
  {
    v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v20 = L"GetClientTokenUser";
    v21 = L"SECSECRC";
    v22 = 449;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    v9 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v19, (CVssDebugInfo *)v42);
    v10 = CVssDebugInfo::operator<<(v9, (CVssDebugInfo *)v43);
    CVssFunctionTracer::LogError(&v27, 8198, v10, 1);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v42);
    CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v19);
    v11 = TokenInformationLength;
    v12 = v45;
    v19 = L"base\\stor\\vss\\modules\\sec\\security.cxx";
    v20 = L"GetClientTokenUser";
    v21 = L"SECSECRC";
    v22 = 451;
    v23 = 11;
    v24 = 255;
    v26 = 0x1000000;
    memset_0(v25, 0, sizeof(v25));
    LODWORD(v17) = v11;
    LODWORD(ReturnLengtha) = v12;
    CVssFunctionTracer::Throw(
      &v27,
      &v19,
      2147754754LL,
      L"Unexpected error. Final buffer size = %lu, original size was %lu",
      ReturnLengtha,
      v17);
  }
  if ( TokenHandle != (HANDLE)-1LL )
    CloseHandle(TokenHandle);
  TokenHandle = (HANDLE)-1LL;
  CVssFunctionTracer::~CVssFunctionTracer((LPVOID *)&v27);
  return (struct _TOKEN_USER *)v6;
}

```

## disassembly

```asm
0x14002f438  mov     [rsp-8+TokenInformationLength], ecx
0x14002f43c  push    rbp
0x14002f43d  push    rbx
0x14002f43e  push    rsi
0x14002f43f  push    rdi
0x14002f440  push    r12
0x14002f442  push    r13
0x14002f444  push    r15
0x14002f446  lea     rbp, [rsp-1E0h]
0x14002f44e  sub     rsp, 2E0h
0x14002f455  lea     r13, aBaseStorVssMod_24; "base\\stor\\vss\\modules\\sec\\security"...
0x14002f45c  mov     [rsp+310h+var_2B0], r13
0x14002f461  lea     rax, aGetclienttoken; "GetClientTokenUser"
0x14002f468  mov     [rsp+310h+var_2A8], rax
0x14002f46d  lea     rax, aSecsecrc; "SECSECRC"
0x14002f474  mov     [rsp+310h+var_2A0], rax
0x14002f479  mov     [rsp+310h+var_298], 18Bh
0x14002f481  mov     [rsp+310h+var_294], 0Bh
0x14002f489  mov     r12d, 0FFh
0x14002f48f  mov     [rbp+210h+var_290], r12d
0x14002f493  xor     esi, esi
0x14002f495  mov     [rbp+210h+var_210], 1000000h
0x14002f49c  xor     edx, edx; Val
0x14002f49e  lea     r8d, [rsi+78h]; Size
0x14002f4a2  lea     rcx, [rbp+210h+var_288]; void *
0x14002f4a6  call    memset_0
0x14002f4ab  mov     [rbp+210h+var_1F8], esi
0x14002f4ae  mov     rax, [rsp+310h+var_2A8]
0x14002f4b3  mov     [rbp+210h+var_1D8], rax
0x14002f4b7  mov     rax, [rsp+310h+var_2B0]
0x14002f4bc  mov     [rbp+210h+var_1F0], rax
0x14002f4c0  mov     rax, [rsp+310h+var_2A0]
0x14002f4c5  mov     [rbp+210h+var_1E8], rax
0x14002f4c9  mov     eax, [rsp+310h+var_298]
0x14002f4cd  mov     [rbp+210h+var_1E0], eax
0x14002f4d0  mov     eax, [rsp+310h+var_294]
0x14002f4d4  mov     [rbp+210h+var_1DC], eax
0x14002f4d7  call    cs:__imp_GetTickCount
0x14002f4dd  mov     [rbp+210h+var_1CC], eax
0x14002f4e0  mov     [rbp+210h+var_1FC], 0FFFFFFFFh
0x14002f4e7  mov     eax, [rbp+210h+var_290]
0x14002f4ea  mov     [rbp+210h+var_1C8], eax
0x14002f4ed  mov     [rbp+210h+var_200], esi
0x14002f4f0  mov     [rbp+210h+var_1A0], rsi
0x14002f4f4  xorps   xmm0, xmm0
0x14002f4f7  movups  [rbp+210h+var_1C0], xmm0
0x14002f4fb  movups  [rbp+210h+var_1B0], xmm0
0x14002f4ff  mov     [rbp+210h+pExceptionObject], rsi
0x14002f506  lea     rcx, [rbp+210h+pExceptionObject]
0x14002f50d  call    cs:__imp_VssGetTracingContextPerThread
0x14002f513  test    eax, eax
0x14002f515  js      short loc_14002F535
0x14002f517  lea     rcx, [rbp+210h+var_200]
0x14002f51b  call    cs:__imp_VssSetTracingContextPerThread
0x14002f521  mov     rcx, [rbp+210h+var_1A0]
0x14002f525  test    eax, eax
0x14002f527  cmovns  rcx, [rbp+210h+pExceptionObject]
0x14002f52f  mov     [rbp+210h+var_1A0], rcx
0x14002f533  jmp     short loc_14002F539
0x14002f535  mov     rcx, [rbp+210h+var_1A0]
0x14002f539  test    rcx, rcx
0x14002f53c  jz      short loc_14002F548
0x14002f53e  mov     eax, [rcx+30h]
0x14002f541  inc     eax
0x14002f543  mov     [rbp+210h+var_1D0], eax
0x14002f546  jmp     short loc_14002F54B
0x14002f548  mov     [rbp+210h+var_1D0], esi
0x14002f54b  mov     ebx, 0A0h
0x14002f550  cmp     [rbp+210h+var_1C8], r12d
0x14002f554  cmovnz  ebx, [rbp+210h+var_1C8]
0x14002f558  lea     rcx, [rbp+210h+var_200]; this
0x14002f55c  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x14002f561  test    eax, eax
0x14002f563  jz      short loc_14002F5A0
0x14002f565  mov     [rsp+310h+var_2D0], rsi
0x14002f56a  mov     [rsp+310h+var_2D8], ebx
0x14002f56e  lea     rax, aEnter; "ENTER"
0x14002f575  mov     [rsp+310h+var_2E0], rax
0x14002f57a  mov     rax, [rbp+210h+var_1D8]
0x14002f57e  mov     [rsp+310h+var_2E8], rax
0x14002f583  mov     eax, [rbp+210h+var_1DC]
0x14002f586  mov     dword ptr [rsp+310h+ReturnLength], eax
0x14002f58a  mov     r9d, [rbp+210h+var_1D0]
0x14002f58e  mov     r8d, [rbp+210h+var_1E0]
0x14002f592  mov     rdx, [rbp+210h+var_1E8]
0x14002f596  mov     rcx, [rbp+210h+var_1F0]
0x14002f59a  call    cs:__imp_VssTraceMessage
0x14002f5a0  lea     rcx, [rsp+310h+var_2B0]; this
0x14002f5a5  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002f5aa  nop
0x14002f5ab  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14002f5b2  mov     [rsp+310h+var_2C0], rax
0x14002f5b7  mov     [rbp+210h+var_188], rsi
0x14002f5be  lea     rax, ??_7?$CVssAuto@PEAPEAGV?$CVssAutoCppPtr_Storage@PEAPEAG@@@@6B@; const CVssAuto<ushort * *,CVssAutoCppPtr_Storage<ushort * *>>::`vftable'
0x14002f5c5  mov     [rbp+210h+var_190], rax
0x14002f5cc  mov     [rbp+210h+arg_8], esi
0x14002f5d2  mov     [rbp+210h+TokenInformationLength], esi
0x14002f5d8  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002f5dc  mov     [rsp+310h+TokenHandle], r15
0x14002f5e1  lea     r8, [rsp+310h+TokenHandle]; void **
0x14002f5e6  xor     edx, edx; bool
0x14002f5e8  mov     cl, 1; bool
0x14002f5ea  call    ?GetCurrentAccessToken@@YA_N_N0PEAPEAX@Z; GetCurrentAccessToken(bool,bool,void * *)
0x14002f5ef  lea     rax, [rbp+210h+TokenInformationLength]
0x14002f5f6  mov     [rsp+310h+ReturnLength], rax; ReturnLength
0x14002f5fb  xor     r9d, r9d; TokenInformationLength
0x14002f5fe  xor     r8d, r8d; TokenInformation
0x14002f601  lea     edx, [r15+2]; TokenInformationClass
0x14002f605  mov     rcx, [rsp+310h+TokenHandle]; TokenHandle
0x14002f60a  call    cs:__imp_GetTokenInformation
0x14002f610  mov     edi, eax
0x14002f612  call    cs:__imp_GetLastError
0x14002f618  mov     ebx, eax
0x14002f61a  cmp     eax, 7Ah ; 'z'
0x14002f61d  jnz     loc_14002F874
0x14002f623  test    edi, edi
0x14002f625  jnz     loc_14002F874
0x14002f62b  mov     ecx, [rbp+210h+TokenInformationLength]; unsigned __int64
0x14002f631  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002f638  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x14002f63d  mov     rbx, rax
0x14002f640  mov     [rbp+210h+var_188], rax
0x14002f647  test    rax, rax
0x14002f64a  jnz     short loc_14002F66A
0x14002f64c  mov     dword ptr [rbp+210h+pExceptionObject], 8007000Eh
0x14002f656  lea     rdx, _TI1J; pThrowInfo
0x14002f65d  lea     rcx, [rbp+210h+pExceptionObject]; pExceptionObject
0x14002f664  call    _CxxThrowException_0
0x14002f66a  lea     rax, [rbp+210h+arg_8]
0x14002f671  mov     [rsp+310h+ReturnLength], rax; ReturnLength
0x14002f676  mov     r9d, [rbp+210h+TokenInformationLength]; TokenInformationLength
0x14002f67d  mov     r8, rbx; TokenInformation
0x14002f680  mov     edx, 1; TokenInformationClass
0x14002f685  mov     rcx, [rsp+310h+TokenHandle]; TokenHandle
0x14002f68a  call    cs:__imp_GetTokenInformation
0x14002f690  test    eax, eax
0x14002f692  jnz     short loc_14002F709
0x14002f694  call    cs:__imp_GetLastError
0x14002f69a  mov     ebx, eax
0x14002f69c  test    eax, eax
0x14002f69e  jle     short loc_14002F6A9
0x14002f6a0  movzx   ebx, ax
0x14002f6a3  or      ebx, 80070000h
0x14002f6a9  mov     [rsp+310h+var_2B0], r13
0x14002f6ae  lea     r15, aGetclienttoken; "GetClientTokenUser"
0x14002f6b5  mov     [rsp+310h+var_2A8], r15
0x14002f6ba  lea     rax, aSecsecrc; "SECSECRC"
0x14002f6c1  mov     [rsp+310h+var_2A0], rax
0x14002f6c6  mov     [rsp+310h+var_298], 1BAh
0x14002f6ce  mov     [rsp+310h+var_294], 0Bh
0x14002f6d6  mov     [rbp+210h+var_290], r12d
0x14002f6da  mov     [rbp+210h+var_210], 1000000h
0x14002f6e1  xor     edx, edx; Val
0x14002f6e3  lea     r8d, [rdx+78h]; Size
0x14002f6e7  lea     rcx, [rbp+210h+var_288]; void *
0x14002f6eb  call    memset_0
0x14002f6f0  lea     r9, aGettokeninform; "GetTokenInformation"
0x14002f6f7  mov     r8d, ebx
0x14002f6fa  lea     rdx, [rsp+310h+var_2B0]
0x14002f6ff  lea     rcx, [rbp+210h+var_200]
0x14002f703  call    ?TranslateError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBG@Z; CVssFunctionTracer::TranslateError(CVssDebugInfo,long,ushort const *)
0x14002f709  mov     edi, [rbp+210h+arg_8]
0x14002f70f  cmp     edi, [rbp+210h+TokenInformationLength]
0x14002f715  jbe     loc_14002F829
0x14002f71b  mov     [rsp+310h+var_2B0], r13
0x14002f720  lea     r15, aGetclienttoken; "GetClientTokenUser"
0x14002f727  mov     [rsp+310h+var_2A8], r15
0x14002f72c  lea     rax, aSecsecrc; "SECSECRC"
0x14002f733  mov     [rsp+310h+var_2A0], rax
0x14002f738  mov     [rsp+310h+var_298], 1C1h
0x14002f740  mov     [rsp+310h+var_294], 0Bh
0x14002f748  mov     [rbp+210h+var_290], r12d
0x14002f74c  mov     [rbp+210h+var_210], 1000000h
0x14002f753  xor     edx, edx; Val
0x14002f755  lea     r8d, [rdx+78h]; Size
0x14002f759  lea     rcx, [rbp+210h+var_288]; void *
0x14002f75d  call    memset_0
0x14002f762  mov     r8d, edi
0x14002f765  lea     rdx, [rbp+210h+var_180]; this
0x14002f76c  lea     rcx, [rsp+310h+var_2B0]; struct CVssDebugInfo *
0x14002f771  call    ??6CVssDebugInfo@@QEAA?AU0@H@Z; CVssDebugInfo::operator<<(int)
0x14002f776  mov     r8d, [rbp+210h+TokenInformationLength]
0x14002f77d  lea     rdx, [rbp+210h+var_D8]; this
0x14002f784  mov     rcx, rax; struct CVssDebugInfo *
0x14002f787  call    ??6CVssDebugInfo@@QEAA?AU0@H@Z; CVssDebugInfo::operator<<(int)
0x14002f78c  mov     r9d, 1
0x14002f792  mov     r8, rax
0x14002f795  mov     edx, 2006h
0x14002f79a  lea     rcx, [rbp+210h+var_200]
0x14002f79e  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14002f7a3  lea     rcx, [rbp+210h+var_180]; this
0x14002f7aa  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002f7af  lea     rcx, [rsp+310h+var_2B0]; this
0x14002f7b4  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002f7b9  mov     ebx, [rbp+210h+TokenInformationLength]
0x14002f7bf  mov     edi, [rbp+210h+arg_8]
0x14002f7c5  mov     [rsp+310h+var_2B0], r13
0x14002f7ca  mov     [rsp+310h+var_2A8], r15
0x14002f7cf  lea     rax, aSecsecrc; "SECSECRC"
0x14002f7d6  mov     [rsp+310h+var_2A0], rax
0x14002f7db  mov     [rsp+310h+var_298], 1C3h
0x14002f7e3  mov     [rsp+310h+var_294], 0Bh
0x14002f7eb  mov     [rbp+210h+var_290], r12d
0x14002f7ef  mov     [rbp+210h+var_210], 1000000h
0x14002f7f6  xor     edx, edx; Val
0x14002f7f8  lea     r8d, [rdx+78h]; Size
0x14002f7fc  lea     rcx, [rbp+210h+var_288]; void *
0x14002f800  call    memset_0
0x14002f805  mov     dword ptr [rsp+310h+var_2E8], ebx
0x14002f809  mov     dword ptr [rsp+310h+ReturnLength], edi
0x14002f80d  lea     r9, aUnexpectedErro_4; "Unexpected error. Final buffer size = %"...
0x14002f814  mov     r8d, 80042302h
0x14002f81a  lea     rdx, [rsp+310h+var_2B0]
0x14002f81f  lea     rcx, [rbp+210h+var_200]
0x14002f823  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14002f829  lea     rax, ??_7?$CVssAuto@PEAXV?$CVssAutoGenericValue_Storage@PEAX$0?0P6AHPEAX@Z$1?CloseHandle@@YAH0@ZP6AAEAPEAXAEAPEAX@Z$1?Identity@?$DTyper@PEAX@@SAAEAPEAX1@Z@@@@6B@; const CVssAuto<void *,CVssAutoGenericValue_Storage<void *,-1,int (*)(void *),&CloseHandle(void *),void * & (*)(void * &),&DTyper<void *>::Identity(void * &)>>::`vftable'
0x14002f830  mov     [rsp+310h+var_2C0], rax
0x14002f835  mov     rcx, [rsp+310h+TokenHandle]; hObject
0x14002f83a  cmp     rcx, r15
0x14002f83d  jz      short loc_14002F845
0x14002f83f  call    cs:__imp_CloseHandle
0x14002f845  mov     [rsp+310h+TokenHandle], r15
0x14002f84a  lea     rax, ??_7?$CVssAutoGenericValue_Storage@PEAE$0A@P6AKPEAX@Z$1?NetApiBufferFree@@YAK0@ZP6AAEAPEAEAEAPEAE@Z$1?Identity@?$DTyper@PEAE@@SAAEAPEAE1@Z@@6B@; const CVssAutoGenericValue_Storage<uchar *,0,ulong (*)(void *),&NetApiBufferFree(void *),uchar * & (*)(uchar * &),&DTyper<uchar *>::Identity(uchar * &)>::`vftable'
0x14002f851  mov     [rsp+310h+var_2C0], rax
0x14002f856  lea     rcx, [rbp+210h+var_200]; this
0x14002f85a  call    ??1CVssFunctionTracer@@QEAA@XZ; CVssFunctionTracer::~CVssFunctionTracer(void)
0x14002f85f  mov     rax, rbx
0x14002f862  add     rsp, 2E0h
0x14002f869  pop     r15
0x14002f86b  pop     r13
0x14002f86d  pop     r12
0x14002f86f  pop     rdi
0x14002f870  pop     rsi
0x14002f871  pop     rbx
0x14002f872  pop     rbp
0x14002f873  retn
0x14002f874  mov     [rsp+310h+var_2B0], r13
0x14002f879  lea     r15, aGetclienttoken; "GetClientTokenUser"
0x14002f880  mov     [rsp+310h+var_2A8], r15
0x14002f885  lea     rdi, aSecsecrc; "SECSECRC"
0x14002f88c  mov     [rsp+310h+var_2A0], rdi
0x14002f891  mov     [rsp+310h+var_298], 1A3h
0x14002f899  mov     [rsp+310h+var_294], 0Bh
0x14002f8a1  mov     [rbp+210h+var_290], r12d
0x14002f8a5  mov     [rbp+210h+var_210], 1000000h
0x14002f8ac  xor     edx, edx; Val
0x14002f8ae  lea     r8d, [rdx+78h]; Size
0x14002f8b2  lea     rcx, [rbp+210h+var_288]; void *
0x14002f8b6  call    memset_0
0x14002f8bb  mov     r8d, ebx; dwMessageId
0x14002f8be  lea     rdx, [rbp+210h+var_180]; this
0x14002f8c5  lea     rcx, [rsp+310h+var_2B0]; struct CVssDebugInfo *
0x14002f8ca  call    ??6CVssDebugInfo@@QEAA?AU0@J@Z; CVssDebugInfo::operator<<(long)
0x14002f8cf  mov     r9d, 1
0x14002f8d5  mov     r8, rax
0x14002f8d8  mov     edx, 2005h
0x14002f8dd  lea     rcx, [rbp+210h+var_200]
0x14002f8e1  call    ?LogError@CVssFunctionTracer@@QEAAXKUCVssDebugInfo@@G@Z; CVssFunctionTracer::LogError(ulong,CVssDebugInfo,ushort)
0x14002f8e6  lea     rcx, [rsp+310h+var_2B0]; this
0x14002f8eb  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x14002f8f0  mov     [rsp+310h+var_2B0], r13
0x14002f8f5  mov     [rsp+310h+var_2A8], r15
0x14002f8fa  mov     [rsp+310h+var_2A0], rdi
0x14002f8ff  mov     [rsp+310h+var_298], 1A5h
0x14002f907  mov     [rsp+310h+var_294], 0Bh
0x14002f90f  mov     [rbp+210h+var_290], r12d
0x14002f913  mov     [rbp+210h+var_210], 1000000h
0x14002f91a  xor     edx, edx; Val
0x14002f91c  lea     r8d, [rdx+78h]; Size
0x14002f920  lea     rcx, [rbp+210h+var_288]; void *
0x14002f924  call    memset_0
0x14002f929  mov     dword ptr [rsp+310h+ReturnLength], ebx
0x14002f92d  lea     r9, aErrorInsuffici_0; "ERROR_INSUFFICIENT_BUFFER expected erro"...
0x14002f934  mov     r8d, 80042302h
0x14002f93a  lea     rdx, [rsp+310h+var_2B0]
0x14002f93f  lea     rcx, [rbp+210h+var_200]
0x14002f943  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
