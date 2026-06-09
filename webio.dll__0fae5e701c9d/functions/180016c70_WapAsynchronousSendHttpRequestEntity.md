# WapAsynchronousSendHttpRequestEntity

- ea: `0x180016c70`
- end: `0x18001753b`
- name: `WapAsynchronousSendHttpRequestEntity`
- size: `2251`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005db14`

## callees

- `0x180016c70`
- `0x1800180e0`
- `0x180018370`
- `0x18001b150`
- `0x18001f9e8`
- `0x180024390`
- `0x18002e460`
- `0x180035edc`
- `0x1800722f0`
- `0x180092500`
- `0x180092564`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017087`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001723f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180017087`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001723f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017212`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017212`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800171f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800171f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017381`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ec1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180016ec1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016d51`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180016d51`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016d71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017274`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180016d71`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180017274`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016dad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016dce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017197`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016dad`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180016dce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180017197`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800170a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800170a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800174e6`

## pseudocode

```c
__int64 __fastcall WapAsynchronousSendHttpRequestEntity(
        unsigned __int64 a1,
        int a2,
        _DWORD *a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6)
{
  unsigned int v6; // r15d
  char *v10; // r8
  __int64 v11; // rbx
  RTL_SRWLOCK *v12; // rcx
  __int64 v13; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int64 v17; // rdi
  int v18; // r9d
  __int64 v19; // r14
  __int64 v20; // r13
  int v21; // eax
  int v22; // ecx
  bool v23; // r14
  __int64 i; // rdx
  __int64 HttpRequestSendTracker; // rax
  __int64 v26; // r8
  __int64 v27; // r15
  unsigned int v28; // ecx
  bool v29; // zf
  int v30; // r14d
  _QWORD *v31; // rdx
  _QWORD *v32; // rax
  __int64 v33; // rax
  unsigned __int64 v34; // rax
  __int64 v35; // r8
  unsigned int locked; // edi
  int v37; // esi
  HANDLE CurrentThread; // rax
  __int64 v40; // r8
  DWORD LastError; // eax
  __int64 v45; // [rsp+58h] [rbp-A8h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h] BYREF
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  int v50; // [rsp+80h] [rbp-80h] BYREF
  HANDLE Token; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v52; // [rsp+90h] [rbp-70h] BYREF
  __int128 v53; // [rsp+98h] [rbp-68h]
  GUID ActivityId; // [rsp+A8h] [rbp-58h] BYREF
  int v55; // [rsp+B8h] [rbp-48h]
  _BYTE v56[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v57; // [rsp+D0h] [rbp-30h]
  __int64 v58; // [rsp+D8h] [rbp-28h]
  HANDLE *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  void **p_TokenHandle; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]
  __int64 *v63; // [rsp+100h] [rbp+0h]
  __int64 v64; // [rsp+108h] [rbp+8h]
  HANDLE *p_Token; // [rsp+110h] [rbp+10h]
  __int64 v66; // [rsp+118h] [rbp+18h]
  HANDLE *v67; // [rsp+120h] [rbp+20h]
  __int64 v68; // [rsp+128h] [rbp+28h]
  void **v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]

  v6 = a4;
  v45 = a5;
  v53 = 0;
  v55 = 0;
  ActivityId = 0;
  if ( !WaHandleTableInitialized )
    return 6;
  if ( (a1 & 0xF0000000) != 0x30000000 )
    return 6;
  v10 = (char *)WaHandleTable + 64 * (unsigned __int64)BYTE4(a1);
  if ( (unsigned int)(unsigned __int16)(HIDWORD(a1) >> 8) >= *((_DWORD *)v10 + 4) )
    return 6;
  v11 = 32 * HIBYTE(a1) + *(_QWORD *)(*((_QWORD *)v10 + 1) + 8LL * (unsigned __int16)(HIDWORD(a1) >> 8));
  if ( *(_QWORD *)(v11 + 24) != a1 )
    return 6;
  AcquireSRWLockShared((PSRWLOCK)(v11 + 16));
  v12 = (RTL_SRWLOCK *)(v11 + 16);
  if ( *(_QWORD *)(v11 + 24) != a1 )
  {
    ReleaseSRWLockShared(v12);
    return 6;
  }
  v13 = *(_QWORD *)v11;
  _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
  ReleaseSRWLockShared(v12);
  if ( !v13 )
    return 6;
  v53 = 0;
  v55 = 0;
  ActivityId = 0;
  v53 = *(_OWORD *)(v13 + 4572);
  if ( !EventActivityIdControl(1u, &ActivityId) )
  {
    if ( !(_BYTE)v55 )
      LOBYTE(v55) = EventActivityIdControl(2u, (LPGUID)(v13 + 4572)) == 0;
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
      EtwEx_tidActivityInfoTransfer(v15, v14, v13 + 4572, &ActivityId);
  }
  if ( !(_BYTE)v55 )
    ActivityId = 0;
  v17 = 0;
  if ( (Microsoft_Windows_WebIOEnableBits & 0x80u) != 0 )
  {
    v50 = 0;
    v57 = &v49;
    v52 = a6;
    v59 = (HANDLE *)&v48;
    LODWORD(Token) = v6;
    p_TokenHandle = &TokenHandle;
    v47 = (__int64)a3;
    v63 = &v47;
    p_Token = &Token;
    v67 = (HANDLE *)&v52;
    v69 = (void **)&v50;
    LODWORD(TokenHandle) = a2;
    v48 = a1;
    v49 = v13;
    v58 = 8;
    v60 = 8;
    v62 = 4;
    v64 = 8;
    v66 = 4;
    v68 = 8;
    v70 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, HttpSendHttpRequestEntity, v16, 8, v56);
  }
  EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 8));
  v19 = *(_QWORD *)(v13 + 72);
  if ( !*(_BYTE *)(v19 + 33) )
  {
    Token = *(HANDLE *)(v19 + 112);
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x2000Cu, 1, &TokenHandle) )
    {
      v20 = (__int64)TokenHandle;
    }
    else
    {
      LastError = GetLastError();
      if ( !LastError )
        LastError = 1359;
      if ( LastError != 1008 )
        LODWORD(v17) = LastError;
      v20 = -(__int64)(LastError != 1008);
      TokenHandle = (void *)v20;
      if ( (_DWORD)v17 )
        goto LABEL_69;
    }
    if ( !Token && !v20 )
      goto LABEL_84;
    LODWORD(v17) = 0;
    if ( !SetThreadToken(0, Token) )
      LODWORD(v17) = WaGetLastError();
LABEL_69:
    if ( v20 != -1 && (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v52 = (unsigned __int64)Token;
      v50 = v17;
      v57 = (__int64 *)&v52;
      v47 = v20;
      v59 = (HANDLE *)&v47;
      p_TokenHandle = (void **)&v50;
      v58 = 8;
      v60 = 8;
      v62 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenSet, v40, 4, v56);
    }
    if ( !(_DWORD)v17 )
    {
LABEL_73:
      v17 = 0;
      goto LABEL_18;
    }
    if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle((HANDLE)v20);
LABEL_84:
    v20 = -1;
    if ( (_DWORD)v17 )
    {
      if ( (xmmword_1800AD710 & 2) != 0 )
        WPP_SF_qD(513, 17, WPP_247e30510a1b3c47cfbd7b690ee005cd_Traceguids, v19, v17);
      goto LABEL_87;
    }
    goto LABEL_73;
  }
  v20 = -1;
LABEL_18:
  if ( *(_BYTE *)(v13 + 56) || (v21 = *(_DWORD *)(v13 + 48)) == 0 )
  {
    LODWORD(v17) = *(_DWORD *)(v13 + 52);
LABEL_47:
    v30 = a2;
    goto LABEL_48;
  }
  if ( v21 <= 1 )
  {
    LODWORD(v17) = 5023;
LABEL_87:
    v30 = a2;
    goto LABEL_92;
  }
  if ( (a2 & 0x7FFFFFFF) != 0 )
    goto LABEL_91;
  if ( a2 < 0 )
  {
    if ( !a3 || !v6 )
      goto LABEL_25;
LABEL_91:
    LODWORD(v17) = 87;
    v30 = a2;
    goto LABEL_92;
  }
  if ( !a3 || !v6 )
    goto LABEL_91;
LABEL_25:
  v22 = *(_DWORD *)(v13 + 1800);
  v23 = (v22 & 0x40000000) == 0 && v22 >= 0;
  for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
  {
    if ( a3[6 * i] )
      goto LABEL_76;
    if ( !*(_QWORD *)&a3[6 * i + 2] )
      goto LABEL_76;
    v33 = *(_QWORD *)&a3[6 * i + 4];
    if ( !v33 )
      goto LABEL_76;
    v34 = v17 + v33;
    if ( v34 < v17 )
    {
      if ( (xmmword_1800AD710 & 2) != 0 )
        WPP_SF_(513, 12, WPP_f51a302de63d353b45f08d7caef3fd03_Traceguids);
      LODWORD(v17) = 534;
      goto LABEL_47;
    }
    v17 = v34;
  }
  if ( v23 && v17 > *(_QWORD *)(v13 + 1816) )
  {
LABEL_76:
    LODWORD(v17) = 87;
    goto LABEL_47;
  }
  LOBYTE(v18) = 1;
  HttpRequestSendTracker = WapCreateHttpRequestSendTracker(v13, (_DWORD)a3, v6, v18, v45, a6);
  v27 = HttpRequestSendTracker;
  if ( !HttpRequestSendTracker )
  {
    v6 = a4;
    LODWORD(v17) = 8;
    goto LABEL_47;
  }
  *(_DWORD *)(v13 + 304) |= 2u;
  v28 = *(_DWORD *)(v13 + 304);
  if ( v23 )
  {
    v29 = *(_QWORD *)(v13 + 1816) == v17;
    *(_QWORD *)(v13 + 1816) -= v17;
    if ( v29 )
    {
      v28 |= 0x10u;
      *(_DWORD *)(v13 + 304) = v28;
    }
  }
  v30 = a2;
  if ( a2 < 0 )
  {
    v28 |= 0x10u;
    *(_DWORD *)(v13 + 304) = v28;
  }
  if ( (Microsoft_Windows_WebIOEnableBits & 0x100) != 0 )
  {
    v50 = *(unsigned __int8 *)(HttpRequestSendTracker + 65);
    v52 = (unsigned __int64)a3;
    v57 = &v45;
    v59 = (HANDLE *)&v52;
    p_TokenHandle = (void **)&v47;
    v63 = (__int64 *)&v50;
    p_Token = &Token;
    LODWORD(Token) = (v28 >> 4) & 1;
    v47 = v17;
    v45 = v13;
    v58 = 8;
    v60 = 8;
    v62 = 8;
    v64 = 4;
    v66 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, HttpQueueRequestEntity, v26, 6, v56);
  }
  v31 = *(_QWORD **)(v13 + 1872);
  if ( *v31 != v13 + 1864 )
    __fastfail(3u);
  v32 = (_QWORD *)(v27 + 16);
  v6 = a4;
  *v32 = v13 + 1864;
  LODWORD(v17) = 0;
  v32[1] = v31;
  *v31 = v32;
  *(_QWORD *)(v13 + 1872) = v32;
LABEL_48:
  if ( (_DWORD)v17 )
  {
LABEL_92:
    locked = WaCancelLockedHttpRequest(v13, (unsigned int)v17);
    goto LABEL_50;
  }
  WapSendHttpRequestEntities(v13);
  locked = 997;
LABEL_50:
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 4), 0xFFFFFFFF) == 1 )
    WapDestroyHttpRequest((LPVOID)v13);
  if ( v20 != -1 )
  {
    v37 = 0;
    if ( !SetThreadToken(0, (HANDLE)v20) )
      v37 = WaGetLastError();
    if ( v20 )
      CloseHandle((HANDLE)v20);
    if ( (Microsoft_Windows_WebIOEnableBits & 0x20000) != 0 )
    {
      v50 = v37;
      v57 = &v45;
      v45 = v20;
      v59 = (HANDLE *)&v50;
      v58 = 8;
      v60 = 4;
      McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, ThreadTokenRestore, v35, 3, v56);
    }
  }
  if ( (Microsoft_Windows_WebIOEnableBits & 0x80u) != 0 )
  {
    v48 = a6;
    v47 = (__int64)a3;
    v57 = &v45;
    v59 = (HANDLE *)&v52;
    p_TokenHandle = (void **)&v50;
    v63 = &v47;
    p_Token = &Token;
    v67 = (HANDLE *)&v48;
    v69 = &TokenHandle;
    LODWORD(TokenHandle) = locked;
    LODWORD(Token) = v6;
    v50 = v30;
    v52 = a1;
    v45 = v13;
    v58 = 8;
    v60 = 8;
    v62 = 4;
    v64 = 8;
    v66 = 4;
    v68 = 8;
    v70 = 4;
    McGenEventWrite_EventWriteTransfer(&WEB_ETW_PROVIDER_ID_Context, "l", v35, 8, v56);
  }
  if ( (_BYTE)v55 )
    EventActivityIdControl(2u, &ActivityId);
  return locked;
}

```

## disassembly

```asm
0x180016c70  mov     [rsp-8+arg_8], rbx
0x180016c75  push    rbp
0x180016c76  push    rsi
0x180016c77  push    rdi
0x180016c78  push    r12
0x180016c7a  push    r13
0x180016c7c  push    r14
0x180016c7e  push    r15
0x180016c80  lea     rbp, [rsp-50h]
0x180016c85  sub     rsp, 150h
0x180016c8c  mov     rax, cs:__security_cookie
0x180016c93  xor     rax, rsp
0x180016c96  mov     [rbp+80h+var_40], rax
0x180016c9a  mov     rax, [rbp+80h+arg_20]
0x180016ca1  xorps   xmm0, xmm0
0x180016ca4  mov     r13, [rbp+80h+arg_28]
0x180016cab  mov     r15d, r9d
0x180016cae  mov     [rsp+180h+var_128], rax
0x180016cb3  mov     r14, r8
0x180016cb6  xor     eax, eax
0x180016cb8  mov     [rsp+180h+var_13C], r9d
0x180016cbd  cmp     cs:WaHandleTableInitialized, al
0x180016cc3  mov     esi, edx
0x180016cc5  mov     [rsp+180h+var_138], r8
0x180016cca  mov     r12, rcx
0x180016ccd  mov     [rsp+180h+var_140], edx
0x180016cd1  mov     [rsp+180h+var_130], r13
0x180016cd6  movups  [rbp+80h+var_E8], xmm0
0x180016cda  mov     [rbp+80h+var_C8], eax
0x180016cdd  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x180016ce1  jz      loc_180017280
0x180016ce7  mov     eax, r12d
0x180016cea  and     eax, 0F0000000h
0x180016cef  cmp     eax, 30000000h
0x180016cf4  jnz     loc_180017280
0x180016cfa  mov     rax, rcx
0x180016cfd  shr     rax, 20h
0x180016d01  movzx   r8d, al
0x180016d05  mov     rdx, rax
0x180016d08  shl     r8, 6
0x180016d0c  add     r8, cs:WaHandleTable
0x180016d13  shr     edx, 8
0x180016d16  movzx   eax, dx
0x180016d19  cmp     eax, [r8+10h]
0x180016d1d  jnb     loc_180017280
0x180016d23  mov     rax, rcx
0x180016d26  shr     rcx, 38h
0x180016d2a  shr     rax, 28h
0x180016d2e  movzx   edx, ax
0x180016d31  mov     rax, [r8+8]
0x180016d35  shl     rcx, 5
0x180016d39  mov     rbx, [rax+rdx*8]
0x180016d3d  add     rbx, rcx
0x180016d40  cmp     [rbx+18h], r12
0x180016d44  jnz     loc_180017280
0x180016d4a  lea     rdi, [rbx+10h]
0x180016d4e  mov     rcx, rdi; SRWLock
0x180016d51  call    cs:__imp_AcquireSRWLockShared
0x180016d58  nop     dword ptr [rax+rax+00h]
0x180016d5d  mov     rcx, rdi; SRWLock
0x180016d60  cmp     [rbx+18h], r12
0x180016d64  jnz     loc_180017274
0x180016d6a  mov     rbx, [rbx]
0x180016d6d  lock inc dword ptr [rbx+4]
0x180016d71  call    cs:__imp_ReleaseSRWLockShared
0x180016d78  nop     dword ptr [rax+rax+00h]
0x180016d7d  test    rbx, rbx
0x180016d80  jz      loc_180017280
0x180016d86  xorps   xmm0, xmm0
0x180016d89  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x180016d8d  xor     eax, eax
0x180016d8f  mov     ecx, 1; ControlCode
0x180016d94  movups  [rbp+80h+var_E8], xmm0
0x180016d98  mov     [rbp+80h+var_C8], eax
0x180016d9b  movups  xmmword ptr [rbp+80h+ActivityId.Data1], xmm0
0x180016d9f  movups  xmm0, xmmword ptr [rbx+11DCh]
0x180016da6  mov     byte ptr [rbp+80h+var_C8], al
0x180016da9  movups  [rbp+80h+var_E8], xmm0
0x180016dad  call    cs:__imp_EventActivityIdControl
0x180016db4  nop     dword ptr [rax+rax+00h]
0x180016db9  test    eax, eax
0x180016dbb  jnz     short loc_180016DF0
0x180016dbd  cmp     byte ptr [rbp+80h+var_C8], al
0x180016dc0  jnz     short loc_180016DE2
0x180016dc2  lea     rdx, [rbx+11DCh]; ActivityId
0x180016dc9  mov     ecx, 2; ControlCode
0x180016dce  call    cs:__imp_EventActivityIdControl
0x180016dd5  nop     dword ptr [rax+rax+00h]
0x180016dda  test    eax, eax
0x180016ddc  jnz     short loc_180016DE2
0x180016dde  mov     byte ptr [rbp+80h+var_C8], 1
0x180016de2  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x180016de8  test    eax, eax
0x180016dea  jnz     loc_1800174A1
0x180016df0  cmp     byte ptr [rbp+80h+var_C8], 0
0x180016df4  jz      loc_1800171DA
0x180016dfa  xor     edi, edi
0x180016dfc  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits, dil
0x180016e03  jge     loc_180016EBD
0x180016e09  lea     rax, [rsp+180h+var_108]
0x180016e0e  mov     [rbp+80h+var_100], edi
0x180016e11  mov     [rbp+80h+var_B0], rax
0x180016e15  lea     rdx, HttpSendHttpRequestEntity
0x180016e1c  lea     rax, [rsp+180h+var_110]
0x180016e21  mov     [rbp+80h+var_F0], r13
0x180016e25  mov     [rbp+80h+var_A0], rax
0x180016e29  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x180016e30  lea     rax, [rsp+180h+TokenHandle]
0x180016e35  mov     dword ptr [rbp+80h+Token], r15d
0x180016e39  mov     [rbp+80h+var_90], rax
0x180016e3d  mov     r9d, 8
0x180016e43  lea     rax, [rsp+180h+var_118]
0x180016e48  mov     [rsp+180h+var_118], r14
0x180016e4d  mov     [rbp+80h+var_80], rax
0x180016e51  lea     rax, [rbp+80h+Token]
0x180016e55  mov     [rbp+80h+var_70], rax
0x180016e59  lea     rax, [rbp+80h+var_F0]
0x180016e5d  mov     [rbp+80h+var_60], rax
0x180016e61  lea     rax, [rbp+80h+var_100]
0x180016e65  mov     [rbp+80h+var_50], rax
0x180016e69  lea     rax, [rbp+80h+var_C0]
0x180016e6d  mov     [rsp+180h+var_160], rax
0x180016e72  mov     dword ptr [rsp+180h+TokenHandle], esi
0x180016e76  mov     [rsp+180h+var_110], r12
0x180016e7b  mov     [rsp+180h+var_108], rbx
0x180016e80  mov     [rbp+80h+var_A8], 8
0x180016e88  mov     [rbp+80h+var_98], 8
0x180016e90  mov     [rbp+80h+var_88], 4
0x180016e98  mov     [rbp+80h+var_78], 8
0x180016ea0  mov     [rbp+80h+var_68], 4
0x180016ea8  mov     [rbp+80h+var_58], 8
0x180016eb0  mov     [rbp+80h+var_48], 4
0x180016eb8  call    McGenEventWrite_EventWriteTransfer
0x180016ebd  lea     rcx, [rbx+8]; lpCriticalSection
0x180016ec1  call    cs:__imp_EnterCriticalSection
0x180016ec8  nop     dword ptr [rax+rax+00h]
0x180016ecd  mov     r14, [rbx+48h]
0x180016ed1  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180016ed8  cmp     [r14+21h], dil
0x180016edc  jz      loc_1800171E6
0x180016ee2  mov     r13, rsi
0x180016ee5  cmp     byte ptr [rbx+38h], 0
0x180016ee9  jnz     loc_180017499
0x180016eef  mov     eax, [rbx+30h]
0x180016ef2  test    eax, eax
0x180016ef4  jz      loc_180017499
0x180016efa  cmp     eax, 1
0x180016efd  jle     loc_1800174F7
0x180016f03  mov     eax, [rsp+180h+var_140]
0x180016f07  test    eax, 7FFFFFFFh
0x180016f0c  jnz     loc_180017480
0x180016f12  mov     r10, [rsp+180h+var_138]
0x180016f17  test    eax, eax
0x180016f19  js      loc_18001746E
0x180016f1f  test    r10, r10
0x180016f22  jz      loc_180017480
0x180016f28  test    r15d, r15d
0x180016f2b  jz      loc_180017480
0x180016f31  mov     ecx, [rbx+708h]
0x180016f37  bt      ecx, 1Eh
0x180016f3b  jb      loc_180017501
0x180016f41  mov     al, 1
0x180016f43  test    ecx, ecx
0x180016f45  movzx   r14d, al
0x180016f49  cmovs   r14d, edi
0x180016f4d  xor     edx, edx
0x180016f4f  cmp     edx, r15d
0x180016f52  jb      loc_180017009
0x180016f58  test    r14b, r14b
0x180016f5b  jz      short loc_180016F6A
0x180016f5d  cmp     rdi, [rbx+718h]
0x180016f64  ja      loc_1800172DA
0x180016f6a  mov     rax, [rsp+180h+var_130]
0x180016f6f  mov     r9b, 1
0x180016f72  mov     [rsp+180h+var_158], rax
0x180016f77  mov     r8d, r15d
0x180016f7a  mov     rax, [rsp+180h+var_128]
0x180016f7f  mov     rdx, r10
0x180016f82  mov     rcx, rbx
0x180016f85  mov     [rsp+180h+var_160], rax
0x180016f8a  call    WapCreateHttpRequestSendTracker
0x180016f8f  mov     r15, rax
0x180016f92  test    rax, rax
0x180016f95  jz      loc_180017048
0x180016f9b  or      dword ptr [rbx+130h], 2
0x180016fa2  mov     ecx, [rbx+130h]
0x180016fa8  test    r14b, r14b
0x180016fab  jz      short loc_180016FBF
0x180016fad  sub     [rbx+718h], rdi
0x180016fb4  jnz     short loc_180016FBF
0x180016fb6  or      ecx, 10h
0x180016fb9  mov     [rbx+130h], ecx
0x180016fbf  mov     r14d, [rsp+180h+var_140]
0x180016fc4  test    r14d, r14d
0x180016fc7  js      loc_180017521
0x180016fcd  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+1, 1
0x180016fd4  jnz     loc_1800172E4
0x180016fda  lea     rcx, [rbx+748h]
0x180016fe1  mov     rdx, [rcx+8]
0x180016fe5  cmp     [rdx], rcx
0x180016fe8  jnz     loc_1800173FF
0x180016fee  lea     rax, [r15+10h]
0x180016ff2  mov     r15d, [rsp+180h+var_13C]
0x180016ff7  mov     [rax], rcx
0x180016ffa  xor     edi, edi
0x180016ffc  mov     [rax+8], rdx
0x180017000  mov     [rdx], rax
0x180017003  mov     [rcx+8], rax
0x180017007  jmp     short loc_180017057
0x180017009  lea     rcx, [rdx+rdx*2]
0x18001700d  cmp     dword ptr [r10+rcx*8], 0
0x180017012  jnz     loc_1800172DA
0x180017018  cmp     qword ptr [r10+rcx*8+8], 0
0x18001701e  jz      loc_1800172DA
0x180017024  mov     rax, [r10+rcx*8+10h]
0x180017029  test    rax, rax
0x18001702c  jz      loc_1800172DA
0x180017032  add     rax, rdi
0x180017035  cmp     rax, rdi
0x180017038  jb      loc_1800174B6
0x18001703e  mov     rdi, rax
0x180017041  inc     edx
0x180017043  jmp     loc_180016F4F
0x180017048  mov     r15d, [rsp+180h+var_13C]
0x18001704d  mov     edi, 8
0x180017052  mov     r14d, [rsp+180h+var_140]
0x180017057  test    edi, edi
0x180017059  jnz     loc_180017488
0x18001705f  mov     rcx, rbx
0x180017062  call    WapSendHttpRequestEntities
0x180017067  mov     edi, 3E5h
0x18001706c  lock xadd [rbx+4], esi
0x180017071  cmp     esi, 1
0x180017074  jz      loc_1800171CD
0x18001707a  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18001707e  jz      short loc_1800170BC
0x180017080  mov     rdx, r13; Token
0x180017083  xor     ecx, ecx; Thread
0x180017085  xor     esi, esi
0x180017087  call    cs:__imp_SetThreadToken
0x18001708e  nop     dword ptr [rax+rax+00h]
0x180017093  test    eax, eax
0x180017095  jz      loc_18001752F
0x18001709b  test    r13, r13
0x18001709e  jz      short loc_1800170AF
0x1800170a0  mov     rcx, r13; hObject
0x1800170a3  call    cs:__imp_CloseHandle
0x1800170aa  nop     dword ptr [rax+rax+00h]
0x1800170af  test    byte ptr cs:Microsoft_Windows_WebIOEnableBits+2, 2
0x1800170b6  jnz     loc_18001728A
0x1800170bc  cmp     byte ptr cs:Microsoft_Windows_WebIOEnableBits, 0
0x1800170c3  jge     loc_180017188
0x1800170c9  mov     rax, [rsp+180h+var_130]
0x1800170ce  lea     rdx, HttpSendHttpRequestEntityCompleteInline; "l"
0x1800170d5  mov     [rsp+180h+var_110], rax
0x1800170da  lea     rcx, WEB_ETW_PROVIDER_ID_Context
0x1800170e1  mov     rax, [rsp+180h+var_138]
0x1800170e6  mov     r9d, 8
0x1800170ec  mov     [rsp+180h+var_118], rax
0x1800170f1  lea     rax, [rsp+180h+var_128]
0x1800170f6  mov     [rbp+80h+var_B0], rax
0x1800170fa  lea     rax, [rbp+80h+var_F0]
0x1800170fe  mov     [rbp+80h+var_A0], rax
0x180017102  lea     rax, [rbp+80h+var_100]
0x180017106  mov     [rbp+80h+var_90], rax
0x18001710a  lea     rax, [rsp+180h+var_118]
0x18001710f  mov     [rbp+80h+var_80], rax
0x180017113  lea     rax, [rbp+80h+Token]
0x180017117  mov     [rbp+80h+var_70], rax
0x18001711b  lea     rax, [rsp+180h+var_110]
0x180017120  mov     [rbp+80h+var_60], rax
0x180017124  lea     rax, [rsp+180h+TokenHandle]
0x180017129  mov     [rbp+80h+var_50], rax
0x18001712d  lea     rax, [rbp+80h+var_C0]
0x180017131  mov     [rsp+180h+var_160], rax
0x180017136  mov     dword ptr [rsp+180h+TokenHandle], edi
0x18001713a  mov     dword ptr [rbp+80h+Token], r15d
0x18001713e  mov     [rbp+80h+var_100], r14d
0x180017142  mov     [rbp+80h+var_F0], r12
0x180017146  mov     [rsp+180h+var_128], rbx
0x18001714b  mov     [rbp+80h+var_A8], 8
0x180017153  mov     [rbp+80h+var_98], 8
0x18001715b  mov     [rbp+80h+var_88], 4
0x180017163  mov     [rbp+80h+var_78], 8
0x18001716b  mov     [rbp+80h+var_68], 4
0x180017173  mov     [rbp+80h+var_58], 8
0x18001717b  mov     [rbp+80h+var_48], 4
0x180017183  call    McGenEventWrite_EventWriteTransfer
0x180017188  cmp     byte ptr [rbp+80h+var_C8], 0
0x18001718c  jz      short loc_1800171A3
0x18001718e  lea     rdx, [rbp+80h+ActivityId]; ActivityId
0x180017192  mov     ecx, 2; ControlCode
0x180017197  call    cs:__imp_EventActivityIdControl
0x18001719e  nop     dword ptr [rax+rax+00h]
0x1800171a3  mov     eax, edi
0x1800171a5  mov     rcx, [rbp+80h+var_40]
0x1800171a9  xor     rcx, rsp; StackCookie
0x1800171ac  call    __security_check_cookie
0x1800171b1  mov     rbx, [rsp+180h+arg_8]
0x1800171b9  add     rsp, 150h
  ... truncated ...
```
