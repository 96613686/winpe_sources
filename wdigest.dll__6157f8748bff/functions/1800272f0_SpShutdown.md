# SpShutdown

- ea: `0x1800272f0`
- end: `0x18002751f`
- name: `SpShutdown`
- size: `559`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180026ad0`

## callees

- `0x180006d00`
- `0x180006de0`
- `0x180009770`
- `0x180011fec`
- `0x1800272f0`
- `0x180036874`

## import_xrefs

- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180027412`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002742d`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180027412`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x18002742d`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800274f4`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800274f4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027497`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027497`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002747e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002747e`
- `ntdll!RtlDeregisterWaitEx` at `0x180027465`
- `ntdll!RtlDeregisterWaitEx` at `0x180027465`
- `ntdll!RtlDeleteResource` at `0x180027370`
- `ntdll!RtlDeleteResource` at `0x1800274ab`
- `ntdll!RtlDeleteResource` at `0x180027370`
- `ntdll!RtlDeleteResource` at `0x1800274ab`
- `ntdll!RtlDeleteCriticalSection` at `0x18002733e`
- `ntdll!RtlDeleteCriticalSection` at `0x180027395`
- `ntdll!RtlDeleteCriticalSection` at `0x1800273b0`
- `ntdll!RtlDeleteCriticalSection` at `0x18002733e`
- `ntdll!RtlDeleteCriticalSection` at `0x180027395`
- `ntdll!RtlDeleteCriticalSection` at `0x1800273b0`

## pseudocode

```c
__int64 SpShutdown()
{
  unsigned int i; // ebx
  _QWORD *v1; // rbx
  TRACEHANDLE v2; // rcx

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
  if ( l_bSsiInitialized )
  {
    RtlDeleteCriticalSection(&l_SsiCritSect);
    l_bSsiInitialized = 0;
  }
  if ( g_bContextInitialized )
  {
    for ( i = 0; i < DigestContextLockCount; ++i )
      RtlDeleteResource((PRTL_RESOURCE)&(&DigestContextLock)[12 * i]);
    g_bContextInitialized = 0;
  }
  if ( g_bCredentialsInitialized )
  {
    RtlDeleteCriticalSection(&l_CredentialCritSect);
    g_bCredentialsInitialized = 0;
  }
  if ( g_bLogSessInitialized )
  {
    RtlDeleteCriticalSection(&l_LogSessCritSect);
    g_bLogSessInitialized = 0;
  }
  StringFree(&g_strNtDigestUTF8ServerRealm);
  StringFree(&g_strNTDigestISO8859ServerRealm);
  if ( hMem )
  {
    DigestFreeMemory(hMem);
    hMem = 0;
  }
  UnicodeStringFree(&word_1800459F8);
  UnicodeStringFree(&stru_180045A08);
  if ( g_hCryptProv )
  {
    CryptReleaseContext(g_hCryptProv, 0);
    g_hCryptProv = 0;
  }
  if ( g_hCryptProvAES )
  {
    CryptReleaseContext(g_hCryptProvAES, 0);
    g_hCryptProvAES = 0;
  }
  if ( g_ustrWorkstationName.Buffer )
  {
    DigestFreeMemory(g_ustrWorkstationName.Buffer);
    g_ustrWorkstationName = 0;
  }
  if ( g_hWait )
  {
    RtlDeregisterWaitEx(g_hWait, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    g_hWait = 0;
  }
  if ( g_hkBase )
  {
    RegCloseKey(g_hkBase);
    g_hkBase = 0;
  }
  if ( g_hParamEvent )
  {
    CloseHandle(g_hParamEvent);
    g_hParamEvent = 0;
  }
  RtlDeleteResource(&g_RtlResource_CipherList);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids);
  DeleteDebugTracing();
  v1 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    while ( v1 )
    {
      v2 = v1[1];
      if ( v2 )
      {
        UnregisterTraceGuids(v2);
        v1[1] = 0;
      }
      v1 = (_QWORD *)*v1;
    }
    WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
  }
  return 0;
}

```

## disassembly

```asm
0x1800272f0  mov     [rsp+arg_0], rbx
0x1800272f5  mov     [rsp+arg_8], rsi
0x1800272fa  push    rdi
0x1800272fb  sub     rsp, 20h
0x1800272ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180027306  lea     rsi, WPP_GLOBAL_Control
0x18002730d  cmp     rcx, rsi
0x180027310  jz      short loc_18002732D
0x180027312  test    byte ptr [rcx+1Ch], 80h
0x180027316  jz      short loc_18002732D
0x180027318  mov     rcx, [rcx+10h]
0x18002731c  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x180027323  mov     edx, 1Eh
0x180027328  call    WPP_SF_
0x18002732d  xor     edi, edi
0x18002732f  cmp     cs:?l_bSsiInitialized@@3HA, edi; int l_bSsiInitialized
0x180027335  jz      short loc_18002734A
0x180027337  lea     rcx, ?l_SsiCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18002733e  call    cs:__imp_RtlDeleteCriticalSection
0x180027344  mov     cs:?l_bSsiInitialized@@3HA, edi; int l_bSsiInitialized
0x18002734a  cmp     cs:?g_bContextInitialized@@3HA, edi; int g_bContextInitialized
0x180027350  jz      short loc_180027386
0x180027352  cmp     cs:?DigestContextLockCount@@3KA, edi; ulong DigestContextLockCount
0x180027358  mov     ebx, edi
0x18002735a  jbe     short loc_180027380
0x18002735c  mov     eax, ebx
0x18002735e  lea     rcx, [rax+rax*2]
0x180027362  shl     rcx, 5
0x180027366  lea     rax, ?DigestContextLock@@3PAU_RTL_RESOURCE@@A; _RTL_RESOURCE near * DigestContextLock
0x18002736d  add     rcx, rax; Resource
0x180027370  call    cs:__imp_RtlDeleteResource
0x180027376  inc     ebx
0x180027378  cmp     ebx, cs:?DigestContextLockCount@@3KA; ulong DigestContextLockCount
0x18002737e  jb      short loc_18002735C
0x180027380  mov     cs:?g_bContextInitialized@@3HA, edi; int g_bContextInitialized
0x180027386  cmp     cs:?g_bCredentialsInitialized@@3HA, edi; int g_bCredentialsInitialized
0x18002738c  jz      short loc_1800273A1
0x18002738e  lea     rcx, ?l_CredentialCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180027395  call    cs:__imp_RtlDeleteCriticalSection
0x18002739b  mov     cs:?g_bCredentialsInitialized@@3HA, edi; int g_bCredentialsInitialized
0x1800273a1  cmp     cs:?g_bLogSessInitialized@@3HA, edi; int g_bLogSessInitialized
0x1800273a7  jz      short loc_1800273BC
0x1800273a9  lea     rcx, ?l_LogSessCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800273b0  call    cs:__imp_RtlDeleteCriticalSection
0x1800273b6  mov     cs:?g_bLogSessInitialized@@3HA, edi; int g_bLogSessInitialized
0x1800273bc  lea     rcx, g_strNtDigestUTF8ServerRealm
0x1800273c3  call    StringFree
0x1800273c8  lea     rcx, g_strNTDigestISO8859ServerRealm
0x1800273cf  call    StringFree
0x1800273d4  mov     rcx, cs:hMem; hMem
0x1800273db  test    rcx, rcx
0x1800273de  jz      short loc_1800273EC
0x1800273e0  call    DigestFreeMemory
0x1800273e5  mov     cs:hMem, rdi
0x1800273ec  lea     rcx, word_1800459F8
0x1800273f3  call    UnicodeStringFree
0x1800273f8  lea     rcx, stru_180045A08
0x1800273ff  call    UnicodeStringFree
0x180027404  mov     rcx, cs:g_hCryptProv; hProv
0x18002740b  test    rcx, rcx
0x18002740e  jz      short loc_18002741F
0x180027410  xor     edx, edx; dwFlags
0x180027412  call    cs:__imp_CryptReleaseContext
0x180027418  mov     cs:g_hCryptProv, rdi
0x18002741f  mov     rcx, cs:?g_hCryptProvAES@@3_KA; hProv
0x180027426  test    rcx, rcx
0x180027429  jz      short loc_18002743A
0x18002742b  xor     edx, edx; dwFlags
0x18002742d  call    cs:__imp_CryptReleaseContext
0x180027433  mov     cs:?g_hCryptProvAES@@3_KA, rdi; unsigned __int64 g_hCryptProvAES
0x18002743a  mov     rcx, cs:g_ustrWorkstationName.Buffer; hMem
0x180027441  test    rcx, rcx
0x180027444  jz      short loc_180027455
0x180027446  call    DigestFreeMemory
0x18002744b  xorps   xmm0, xmm0
0x18002744e  movups  xmmword ptr cs:g_ustrWorkstationName.Length, xmm0
0x180027455  mov     rcx, cs:?g_hWait@@3PEAXEA; hWaitHandle
0x18002745c  test    rcx, rcx
0x18002745f  jz      short loc_180027472
0x180027461  or      rdx, 0FFFFFFFFFFFFFFFFh; hCompletionEvent
0x180027465  call    cs:__imp_RtlDeregisterWaitEx
0x18002746b  mov     cs:?g_hWait@@3PEAXEA, rdi; void * g_hWait
0x180027472  mov     rcx, cs:?g_hkBase@@3PEAUHKEY__@@EA; hKey
0x180027479  test    rcx, rcx
0x18002747c  jz      short loc_18002748B
0x18002747e  call    cs:__imp_RegCloseKey
0x180027484  mov     cs:?g_hkBase@@3PEAUHKEY__@@EA, rdi; HKEY__ * g_hkBase
0x18002748b  mov     rcx, cs:?g_hParamEvent@@3PEAXEA; hObject
0x180027492  test    rcx, rcx
0x180027495  jz      short loc_1800274A4
0x180027497  call    cs:__imp_CloseHandle
0x18002749d  mov     cs:?g_hParamEvent@@3PEAXEA, rdi; void * g_hParamEvent
0x1800274a4  lea     rcx, g_RtlResource_CipherList; Resource
0x1800274ab  call    cs:__imp_RtlDeleteResource
0x1800274b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800274b8  cmp     rcx, rsi
0x1800274bb  jz      short loc_1800274D8
0x1800274bd  test    byte ptr [rcx+1Ch], 80h
0x1800274c1  jz      short loc_1800274D8
0x1800274c3  mov     rcx, [rcx+10h]
0x1800274c7  lea     r8, WPP_453d44b8382a3c0018786ee70e9fc51a_Traceguids
0x1800274ce  mov     edx, 1Fh
0x1800274d3  call    WPP_SF_
0x1800274d8  call    _DeleteDebugTracing
0x1800274dd  mov     rbx, cs:WPP_GLOBAL_Control
0x1800274e4  cmp     rbx, rsi
0x1800274e7  jz      short loc_18002750D
0x1800274e9  jmp     short loc_180027501
0x1800274eb  mov     rcx, [rbx+8]; RegistrationHandle
0x1800274ef  test    rcx, rcx
0x1800274f2  jz      short loc_1800274FE
0x1800274f4  call    cs:__imp_UnregisterTraceGuids
0x1800274fa  mov     [rbx+8], rdi
0x1800274fe  mov     rbx, [rbx]
0x180027501  test    rbx, rbx
0x180027504  jnz     short loc_1800274EB
0x180027506  mov     cs:WPP_GLOBAL_Control, rsi
0x18002750d  mov     rbx, [rsp+28h+arg_0]
0x180027512  xor     eax, eax
0x180027514  mov     rsi, [rsp+28h+arg_8]
0x180027519  add     rsp, 20h
0x18002751d  pop     rdi
0x18002751e  retn
```
