# WapDestroyHttpRequest

- ea: `0x18001b150`
- end: `0x18001b777`
- name: `WapDestroyHttpRequest`
- size: `1575`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `48`
- callee_count: `21`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016c70`
- `0x180017550`
- `0x180018860`
- `0x1800194a0`
- `0x180019580`
- `0x180019a20`
- `0x18001b780`
- `0x18001c5c0`
- `0x18001ec68`
- `0x1800218e0`
- `0x180023410`
- `0x180024630`
- `0x1800265d0`
- `0x18002678c`
- `0x180033fe4`
- `0x180034580`
- `0x180035df4`
- `0x180036a70`
- `0x180036da0`
- `0x180039210`
- `0x18003a020`
- `0x18003a420`
- `0x18003a7b0`
- `0x18003ad00`
- `0x18003b970`
- `0x18003c570`
- `0x18004e7f0`
- `0x180054da0`
- `0x180055c70`
- `0x1800560e0`
- `0x180056aa0`
- `0x180058314`
- `0x180059460`
- `0x180059770`
- `0x1800599f0`
- `0x18005b190`
- `0x18005ce20`
- `0x18005d0f8`
- `0x180060ea8`
- `0x180061ac0`
- `0x180062478`
- `0x180063d28`
- `0x18007630c`
- `0x180076700`
- `0x18007688c`
- `0x180081570`
- `0x180081d08`
- `0x180081f08`

## callees

- `0x180005168`
- `0x180013284`
- `0x180013820`
- `0x18001b150`
- `0x18001d320`
- `0x18001d620`
- `0x180021840`
- `0x180021e84`
- `0x180026504`
- `0x180026544`
- `0x180034db8`
- `0x180035f30`
- `0x18003d290`
- `0x18005a3dc`
- `0x18005ae10`
- `0x180061a64`
- `0x180062914`
- `0x18006ad9c`
- `0x1800722f0`
- `0x1800923bc`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b33d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001b33d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b3aa`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b3ce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b3ee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b416`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b3ce`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b3ee`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18001b416`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6a8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b6a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b27e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b43b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b6f6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b27e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b43b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b4ad`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001b6f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001b6e2`
- `CRYPT32!CertFreeCertificateContext` at `0x18001b662`
- `CRYPT32!CertFreeCertificateContext` at `0x18001b662`

## pseudocode

```c
int __fastcall WapDestroyHttpRequest(char *lpMem)
{
  const CERT_CONTEXT *v2; // rcx
  volatile signed __int32 *v3; // rcx
  volatile signed __int32 *v4; // rcx
  volatile signed __int32 *v5; // rcx
  void *v6; // r8
  void *v7; // rsi
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rbp
  volatile signed __int32 *v15; // rsi
  volatile signed __int32 *v16; // rcx
  __int64 v17; // rcx
  int result; // eax
  void *v19; // r8
  volatile signed __int32 *v20; // rcx
  volatile signed __int32 *v21; // rcx
  volatile signed __int32 *v22; // rcx
  void (__fastcall *v23)(__int64, __int64, _QWORD, _QWORD); // rax
  __int64 v24; // rcx
  HANDLE ProcessHeap; // rax
  GUID ActivityId; // [rsp+30h] [rbp-38h] BYREF

  if ( *((_DWORD *)lpMem + 1197) == 1 )
  {
    v23 = (void (__fastcall *)(__int64, __int64, _QWORD, _QWORD))*((_QWORD *)lpMem + 596);
    *((_DWORD *)lpMem + 1197) = 0;
    v24 = *((_QWORD *)lpMem + 597);
    *((_QWORD *)lpMem + 597) = 0;
    *((_QWORD *)lpMem + 596) = 0;
    v23(v24, 999, 0, 0);
  }
  WaAuthTerminate(lpMem + 4320);
  WaAuthTerminate(lpMem + 4384);
  if ( *((_DWORD *)lpMem + 1090) == 3 && *((_QWORD *)lpMem + 546) )
  {
    *(_QWORD *)&ActivityId.Data1 = *((_QWORD *)lpMem + 546);
    WxFreeHeapEx(&ActivityId);
  }
  if ( *((_DWORD *)lpMem + 1106) == 3 && *((_QWORD *)lpMem + 554) )
  {
    *(_QWORD *)&ActivityId.Data1 = *((_QWORD *)lpMem + 554);
    WxFreeHeapEx(&ActivityId);
  }
  v2 = (const CERT_CONTEXT *)*((_QWORD *)lpMem + 511);
  if ( v2 )
  {
    CertFreeCertificateContext(v2);
    *((_QWORD *)lpMem + 511) = 0;
  }
  if ( *((_QWORD *)lpMem + 564) )
  {
    if ( (xmmword_1800AD720 & 2) != 0 )
      WPP_SF_qq(
        1025,
        16,
        (unsigned int)WPP_e34e57bda8c13693a3ee8538e9ac5fa0_Traceguids,
        (_DWORD)lpMem,
        *((_QWORD *)lpMem + 564));
    CloseHandle(*((HANDLE *)lpMem + 564));
    *((_QWORD *)lpMem + 564) = 0;
  }
  if ( *((_QWORD *)lpMem + 563) )
    WaDereferenceProxyConfig();
  if ( *((_QWORD *)lpMem + 565) )
    WaDereferenceProxyResolver();
  v3 = (volatile signed __int32 *)*((_QWORD *)lpMem + 41);
  *((_DWORD *)lpMem + 36) = 1819370866;
  if ( v3 && _InterlockedExchangeAdd(v3 + 1, 0xFFFFFFFF) == 1 )
    WapUriFreeUriObject((LPVOID)v3);
  v4 = (volatile signed __int32 *)*((_QWORD *)lpMem + 566);
  if ( v4 && _InterlockedExchangeAdd(v4 + 1, 0xFFFFFFFF) == 1 )
    WapUriFreeUriObject((LPVOID)v4);
  v5 = (volatile signed __int32 *)*((_QWORD *)lpMem + 505);
  if ( v5 && _InterlockedExchangeAdd(v5 + 1, 0xFFFFFFFF) == 1 )
    WapUriFreeUriObject((LPVOID)v5);
  if ( !*((_DWORD *)lpMem + 80) )
  {
    v19 = (void *)*((_QWORD *)lpMem + 39);
    if ( v19 )
    {
      if ( g_fWxHeapExtensionInitialized )
        g_WxHeapExtensionInterfaces(*((_QWORD *)lpMem + 39));
      else
        HeapFree(g_hWxProcessHeap, 0, v19);
    }
  }
  v6 = (void *)*((_QWORD *)lpMem + 228);
  if ( v6 )
  {
    if ( g_fWxHeapExtensionInitialized )
      g_WxHeapExtensionInterfaces(*((_QWORD *)lpMem + 228));
    else
      HeapFree(g_hWxProcessHeap, 0, v6);
  }
  WaPoolTerminate(lpMem + 4928);
  WaTerminateHttpParsedRequestHeaders(lpMem + 344);
  WaTerminateHttpParsedRequestHeaders(lpMem + 1072);
  WapTerminateHttpResponse(lpMem + 1968);
  if ( *((_QWORD *)lpMem + 594) )
  {
    *(_QWORD *)&ActivityId.Data1 = *((_QWORD *)lpMem + 594);
    WxFreeHeapEx(&ActivityId);
    *((_QWORD *)lpMem + 594) = 0;
    *((_QWORD *)lpMem + 595) = 0;
  }
  v7 = (void *)*((_QWORD *)lpMem + 609);
  if ( v7 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v7);
    *((_QWORD *)lpMem + 609) = 0;
    *((_QWORD *)lpMem + 610) = 0;
  }
  v8 = *((_QWORD *)lpMem + 593);
  if ( v8 )
  {
    WaHttpAbortConnectionCore(*(_QWORD *)(v8 + 64), 0, 995);
    v20 = *(volatile signed __int32 **)(*((_QWORD *)lpMem + 593) + 64LL);
    if ( _InterlockedExchangeAdd(v20 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v20);
  }
  v9 = *((_QWORD *)lpMem + 608);
  if ( v9 )
  {
    WaHttpAbortConnectionCore(*(_QWORD *)(v9 + 64), 0, 995);
    v21 = *(volatile signed __int32 **)(*((_QWORD *)lpMem + 608) + 64LL);
    if ( _InterlockedExchangeAdd(v21 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v21);
  }
  v10 = *((_QWORD *)lpMem + 615);
  if ( v10 )
  {
    WaHttpAbortConnectionCore(*(_QWORD *)(v10 + 64), 0, 995);
    v22 = *(volatile signed __int32 **)(*((_QWORD *)lpMem + 615) + 64LL);
    if ( _InterlockedExchangeAdd(v22 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v22);
  }
  v11 = *((_QWORD *)lpMem + 14);
  if ( v11 )
  {
    v12 = *(volatile signed __int32 **)(v11 + 64);
    if ( _InterlockedExchangeAdd(v12 + 1, 0xFFFFFFFF) == 1 )
      WaDestroyConnection((LPVOID)v12);
  }
  v13 = *((_QWORD *)lpMem + 10);
  if ( v13 )
  {
    v14 = *((_QWORD *)lpMem + 11);
    WaDereferenceConnectionManager(*((LPVOID *)lpMem + 13));
    *(_QWORD *)(v13 + 32) = GetTickCount64();
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v13 + 24), 0xFFFFFFFF) == 1 )
      WapDestroyEndpoint(v13);
    if ( v14 )
      WaDereferenceEndpoint(v14);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)lpMem + 9);
  *((_QWORD *)lpMem + 9) = 0;
  WaHttpExtensionOnDestroyRequest(lpMem);
  WaDecompDestroyContext(lpMem + 4800);
  if ( *((_QWORD *)lpMem + 561) )
  {
    *(_QWORD *)&ActivityId.Data1 = *((_QWORD *)lpMem + 561);
    WxFreeHeapEx(&ActivityId);
    *((_QWORD *)lpMem + 561) = 0;
    *((_QWORD *)lpMem + 562) = 0;
  }
  v16 = (volatile signed __int32 *)*((_QWORD *)lpMem + 539);
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16, 0xFFFFFFFF) == 1 )
    {
      *(_QWORD *)&ActivityId.Data1 = v16;
      WxFreeHeapEx(&ActivityId);
    }
    *((_QWORD *)lpMem + 539) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(lpMem + 8));
  *(_DWORD *)lpMem = 1902473832;
  ActivityId = 0;
  if ( EventActivityIdControl(1u, &ActivityId) )
    ActivityId = 0;
  if ( !EventActivityIdControl(2u, (LPGUID)(lpMem + 4572)) && Microsoft_Windows_Networking_CorrelationEnabled )
    EtwEx_tidActivityInfo(v17, ActivityStop, lpMem + 4572);
  EventActivityIdControl(2u, &ActivityId);
  if ( g_fWxHeapExtensionInitialized )
    result = g_WxHeapExtensionInterfaces(lpMem);
  else
    result = HeapFree(g_hWxProcessHeap, 0, lpMem);
  if ( _InterlockedExchangeAdd(v15 + 1, 0xFFFFFFFF) == 1 )
    return WapDestroySession((LPVOID)v15);
  return result;
}

```

## disassembly

```asm
0x18001b150  mov     [rsp+arg_8], rbx
0x18001b155  mov     [rsp+arg_10], rbp
0x18001b15a  push    rsi
0x18001b15b  push    rdi
0x18001b15c  push    r14
0x18001b15e  sub     rsp, 50h
0x18001b162  mov     rax, cs:__security_cookie
0x18001b169  xor     rax, rsp
0x18001b16c  mov     [rsp+68h+var_28], rax
0x18001b171  xor     r14d, r14d
0x18001b174  mov     rbx, rcx
0x18001b177  cmp     dword ptr [rcx+12B4h], 1
0x18001b17e  jz      loc_18001B5E2
0x18001b184  lea     rcx, [rbx+10E0h]
0x18001b18b  call    WaAuthTerminate
0x18001b190  lea     rcx, [rbx+1120h]
0x18001b197  call    WaAuthTerminate
0x18001b19c  cmp     dword ptr [rbx+1108h], 3
0x18001b1a3  jz      loc_18001B61A
0x18001b1a9  cmp     dword ptr [rbx+1148h], 3
0x18001b1b0  jz      loc_18001B63E
0x18001b1b6  mov     rcx, [rbx+0FF8h]; pCertContext
0x18001b1bd  test    rcx, rcx
0x18001b1c0  jnz     loc_18001B662
0x18001b1c6  mov     rax, [rbx+11A0h]
0x18001b1cd  test    rax, rax
0x18001b1d0  jnz     loc_18001B67A
0x18001b1d6  mov     rcx, [rbx+1198h]
0x18001b1dd  test    rcx, rcx
0x18001b1e0  jnz     loc_18001B4BE
0x18001b1e6  mov     rcx, [rbx+11A8h]
0x18001b1ed  test    rcx, rcx
0x18001b1f0  jnz     loc_18001B4C8
0x18001b1f6  mov     rcx, [rbx+148h]; lpMem
0x18001b1fd  mov     edi, 0FFFFFFFFh
0x18001b202  mov     dword ptr [rbx+90h], 6C716572h
0x18001b20c  test    rcx, rcx
0x18001b20f  jz      short loc_18001B222
0x18001b211  mov     eax, edi
0x18001b213  lock xadd [rcx+4], eax
0x18001b218  cmp     eax, 1
0x18001b21b  jnz     short loc_18001B222
0x18001b21d  call    WapUriFreeUriObject
0x18001b222  mov     rcx, [rbx+11B0h]; lpMem
0x18001b229  test    rcx, rcx
0x18001b22c  jnz     loc_18001B4FA
0x18001b232  mov     rcx, [rbx+0FC8h]; lpMem
0x18001b239  test    rcx, rcx
0x18001b23c  jz      short loc_18001B24F
0x18001b23e  mov     eax, edi
0x18001b240  lock xadd [rcx+4], eax
0x18001b245  cmp     eax, 1
0x18001b248  jnz     short loc_18001B24F
0x18001b24a  call    WapUriFreeUriObject
0x18001b24f  cmp     [rbx+140h], r14d
0x18001b256  jz      loc_18001B487
0x18001b25c  mov     r8, [rbx+720h]; lpMem
0x18001b263  test    r8, r8
0x18001b266  jz      short loc_18001B28A
0x18001b268  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r14d; int g_fWxHeapExtensionInitialized
0x18001b26f  jnz     loc_18001B4E6
0x18001b275  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001b27c  xor     edx, edx; dwFlags
0x18001b27e  call    cs:__imp_HeapFree
0x18001b285  nop     dword ptr [rax+rax+00h]
0x18001b28a  lea     rcx, [rbx+1340h]
0x18001b291  call    WaPoolTerminate
0x18001b296  lea     rcx, [rbx+158h]
0x18001b29d  call    WaTerminateHttpParsedRequestHeaders
0x18001b2a2  lea     rcx, [rbx+430h]
0x18001b2a9  call    WaTerminateHttpParsedRequestHeaders
0x18001b2ae  lea     rcx, [rbx+7B0h]
0x18001b2b5  call    WapTerminateHttpResponse
0x18001b2ba  mov     rax, [rbx+1290h]
0x18001b2c1  test    rax, rax
0x18001b2c4  jnz     loc_18001B6C0
0x18001b2ca  mov     rsi, [rbx+1308h]
0x18001b2d1  test    rsi, rsi
0x18001b2d4  jnz     loc_18001B6E2
0x18001b2da  mov     rcx, [rbx+1288h]
0x18001b2e1  test    rcx, rcx
0x18001b2e4  jnz     loc_18001B540
0x18001b2ea  mov     rcx, [rbx+1300h]
0x18001b2f1  test    rcx, rcx
0x18001b2f4  jnz     loc_18001B576
0x18001b2fa  mov     rcx, [rbx+1338h]
0x18001b301  test    rcx, rcx
0x18001b304  jnz     loc_18001B5AC
0x18001b30a  mov     rax, [rbx+70h]
0x18001b30e  test    rax, rax
0x18001b311  jz      short loc_18001B327
0x18001b313  mov     rcx, [rax+40h]; lpMem
0x18001b317  mov     eax, edi
0x18001b319  lock xadd [rcx+4], eax
0x18001b31e  cmp     eax, 1
0x18001b321  jz      loc_18001B47D
0x18001b327  mov     rsi, [rbx+50h]
0x18001b32b  test    rsi, rsi
0x18001b32e  jz      short loc_18001B36A
0x18001b330  mov     rcx, [rbx+68h]; lpMem
0x18001b334  mov     rbp, [rbx+58h]
0x18001b338  call    WaDereferenceConnectionManager
0x18001b33d  call    cs:__imp_GetTickCount64
0x18001b344  nop     dword ptr [rax+rax+00h]
0x18001b349  mov     [rsi+20h], rax
0x18001b34d  mov     eax, edi
0x18001b34f  lock xadd [rsi+18h], eax
0x18001b354  cmp     eax, 1
0x18001b357  jnz     short loc_18001B361
0x18001b359  mov     rcx, rsi
0x18001b35c  call    WapDestroyEndpoint
0x18001b361  test    rbp, rbp
0x18001b364  jnz     loc_18001B715
0x18001b36a  mov     rsi, [rbx+48h]
0x18001b36e  mov     rcx, rbx
0x18001b371  mov     [rbx+48h], r14
0x18001b375  call    WaHttpExtensionOnDestroyRequest
0x18001b37a  lea     rcx, [rbx+12C0h]
0x18001b381  call    WaDecompDestroyContext
0x18001b386  mov     rax, [rbx+1188h]
0x18001b38d  test    rax, rax
0x18001b390  jnz     loc_18001B722
0x18001b396  mov     rcx, [rbx+10D8h]
0x18001b39d  test    rcx, rcx
0x18001b3a0  jnz     loc_18001B744
0x18001b3a6  lea     rcx, [rbx+8]; lpCriticalSection
0x18001b3aa  call    cs:__imp_DeleteCriticalSection
0x18001b3b1  nop     dword ptr [rax+rax+00h]
0x18001b3b6  xorps   xmm0, xmm0
0x18001b3b9  mov     dword ptr [rbx], 71657268h
0x18001b3bf  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x18001b3c4  mov     ecx, 1; ControlCode
0x18001b3c9  movups  xmmword ptr [rsp+68h+ActivityId.Data1], xmm0
0x18001b3ce  call    cs:__imp_EventActivityIdControl
0x18001b3d5  nop     dword ptr [rax+rax+00h]
0x18001b3da  test    eax, eax
0x18001b3dc  jnz     loc_18001B76A
0x18001b3e2  lea     rdx, [rbx+11DCh]; ActivityId
0x18001b3e9  mov     ecx, 2; ControlCode
0x18001b3ee  call    cs:__imp_EventActivityIdControl
0x18001b3f5  nop     dword ptr [rax+rax+00h]
0x18001b3fa  test    eax, eax
0x18001b3fc  jnz     short loc_18001B40C
0x18001b3fe  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x18001b404  test    eax, eax
0x18001b406  jnz     loc_18001B514
0x18001b40c  lea     rdx, [rsp+68h+ActivityId]; ActivityId
0x18001b411  mov     ecx, 2; ControlCode
0x18001b416  call    cs:__imp_EventActivityIdControl
0x18001b41d  nop     dword ptr [rax+rax+00h]
0x18001b422  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r14d; int g_fWxHeapExtensionInitialized
0x18001b429  jnz     loc_18001B4D2
0x18001b42f  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001b436  mov     r8, rbx; lpMem
0x18001b439  xor     edx, edx; dwFlags
0x18001b43b  call    cs:__imp_HeapFree
0x18001b442  nop     dword ptr [rax+rax+00h]
0x18001b447  lock xadd [rsi+4], edi
0x18001b44c  cmp     edi, 1
0x18001b44f  jnz     short loc_18001B459
0x18001b451  mov     rcx, rsi; lpMem
0x18001b454  call    WapDestroySession
0x18001b459  mov     rcx, [rsp+68h+var_28]
0x18001b45e  xor     rcx, rsp; StackCookie
0x18001b461  call    __security_check_cookie
0x18001b466  mov     rbx, [rsp+68h+arg_8]
0x18001b46b  mov     rbp, [rsp+68h+arg_10]
0x18001b473  add     rsp, 50h
0x18001b477  pop     r14
0x18001b479  pop     rdi
0x18001b47a  pop     rsi
0x18001b47b  retn
0x18001b47d  call    WaDestroyConnection
0x18001b482  jmp     loc_18001B327
0x18001b487  mov     r8, [rbx+138h]; lpMem
0x18001b48e  test    r8, r8
0x18001b491  jz      loc_18001B25C
0x18001b497  cmp     cs:?g_fWxHeapExtensionInitialized@@3HA, r14d; int g_fWxHeapExtensionInitialized
0x18001b49e  jnz     loc_18001B52C
0x18001b4a4  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18001b4ab  xor     edx, edx; dwFlags
0x18001b4ad  call    cs:__imp_HeapFree
0x18001b4b4  nop     dword ptr [rax+rax+00h]
0x18001b4b9  jmp     loc_18001B25C
0x18001b4be  call    WaDereferenceProxyConfig
0x18001b4c3  jmp     loc_18001B1E6
0x18001b4c8  call    WaDereferenceProxyResolver
0x18001b4cd  jmp     loc_18001B1F6
0x18001b4d2  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18001b4d9  mov     rcx, rbx
0x18001b4dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4e1  jmp     loc_18001B447
0x18001b4e6  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18001b4ed  mov     rcx, r8
0x18001b4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4f5  jmp     loc_18001B28A
0x18001b4fa  mov     eax, edi
0x18001b4fc  lock xadd [rcx+4], eax
0x18001b501  cmp     eax, 1
0x18001b504  jnz     loc_18001B232
0x18001b50a  call    WapUriFreeUriObject
0x18001b50f  jmp     loc_18001B232
0x18001b514  lea     r8, [rbx+11DCh]
0x18001b51b  lea     rdx, ActivityStop
0x18001b522  call    EtwEx_tidActivityInfo
0x18001b527  jmp     loc_18001B40C
0x18001b52c  mov     rax, cs:?g_WxHeapExtensionInterfaces@@3U_WX_HEAP_EXTENSION@@A; _WX_HEAP_EXTENSION g_WxHeapExtensionInterfaces
0x18001b533  mov     rcx, r8
0x18001b536  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b53b  jmp     loc_18001B25C
0x18001b540  mov     rcx, [rcx+40h]
0x18001b544  xor     edx, edx
0x18001b546  mov     r8d, 3E3h
0x18001b54c  call    WaHttpAbortConnectionCore
0x18001b551  mov     rax, [rbx+1288h]
0x18001b558  mov     rcx, [rax+40h]; lpMem
0x18001b55c  mov     eax, edi
0x18001b55e  lock xadd [rcx+4], eax
0x18001b563  cmp     eax, 1
0x18001b566  jnz     loc_18001B2EA
0x18001b56c  call    WaDestroyConnection
0x18001b571  jmp     loc_18001B2EA
0x18001b576  mov     rcx, [rcx+40h]
0x18001b57a  xor     edx, edx
0x18001b57c  mov     r8d, 3E3h
0x18001b582  call    WaHttpAbortConnectionCore
0x18001b587  mov     rax, [rbx+1300h]
0x18001b58e  mov     rcx, [rax+40h]; lpMem
0x18001b592  mov     eax, edi
0x18001b594  lock xadd [rcx+4], eax
0x18001b599  cmp     eax, 1
0x18001b59c  jnz     loc_18001B2FA
0x18001b5a2  call    WaDestroyConnection
0x18001b5a7  jmp     loc_18001B2FA
0x18001b5ac  mov     rcx, [rcx+40h]
0x18001b5b0  xor     edx, edx
0x18001b5b2  mov     r8d, 3E3h
0x18001b5b8  call    WaHttpAbortConnectionCore
0x18001b5bd  mov     rax, [rbx+1338h]
0x18001b5c4  mov     rcx, [rax+40h]; lpMem
0x18001b5c8  mov     eax, edi
0x18001b5ca  lock xadd [rcx+4], eax
0x18001b5cf  cmp     eax, 1
0x18001b5d2  jnz     loc_18001B30A
0x18001b5d8  call    WaDestroyConnection
0x18001b5dd  jmp     loc_18001B30A
0x18001b5e2  mov     rax, [rcx+12A0h]
0x18001b5e9  xor     r9d, r9d
0x18001b5ec  mov     [rcx+12B4h], r14d
0x18001b5f3  xor     r8d, r8d
0x18001b5f6  mov     rcx, [rcx+12A8h]
0x18001b5fd  mov     edx, 3E7h
0x18001b602  mov     [rbx+12A8h], r14
0x18001b609  mov     [rbx+12A0h], r14
0x18001b610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b615  jmp     loc_18001B184
0x18001b61a  mov     rax, [rbx+1110h]
0x18001b621  test    rax, rax
0x18001b624  jz      loc_18001B1A9
0x18001b62a  lea     rcx, [rsp+68h+ActivityId]
0x18001b62f  mov     qword ptr [rsp+68h+ActivityId.Data1], rax
0x18001b634  call    WxFreeHeapEx
0x18001b639  jmp     loc_18001B1A9
0x18001b63e  mov     rax, [rbx+1150h]
0x18001b645  test    rax, rax
0x18001b648  jz      loc_18001B1B6
0x18001b64e  lea     rcx, [rsp+68h+ActivityId]
0x18001b653  mov     qword ptr [rsp+68h+ActivityId.Data1], rax
0x18001b658  call    WxFreeHeapEx
0x18001b65d  jmp     loc_18001B1B6
0x18001b662  call    cs:__imp_CertFreeCertificateContext
0x18001b669  nop     dword ptr [rax+rax+00h]
0x18001b66e  mov     [rbx+0FF8h], r14
0x18001b675  jmp     loc_18001B1C6
0x18001b67a  test    byte ptr cs:xmmword_1800AD720, 2
0x18001b681  jz      short loc_18001B6A1
0x18001b683  mov     edx, 10h
0x18001b688  mov     [rsp+68h+var_48], rax
0x18001b68d  mov     ecx, 401h
0x18001b692  lea     r8, WPP_e34e57bda8c13693a3ee8538e9ac5fa0_Traceguids
0x18001b699  mov     r9, rbx
0x18001b69c  call    WPP_SF_qq
0x18001b6a1  mov     rcx, [rbx+11A0h]; hObject
0x18001b6a8  call    cs:__imp_CloseHandle
0x18001b6af  nop     dword ptr [rax+rax+00h]
0x18001b6b4  mov     [rbx+11A0h], r14
0x18001b6bb  jmp     loc_18001B1D6
0x18001b6c0  lea     rcx, [rsp+68h+ActivityId]
0x18001b6c5  mov     qword ptr [rsp+68h+ActivityId.Data1], rax
0x18001b6ca  call    WxFreeHeapEx
0x18001b6cf  mov     [rbx+1290h], r14
0x18001b6d6  mov     [rbx+1298h], r14
0x18001b6dd  jmp     loc_18001B2CA
0x18001b6e2  call    cs:__imp_GetProcessHeap
0x18001b6e9  nop     dword ptr [rax+rax+00h]
0x18001b6ee  mov     r8, rsi; lpMem
0x18001b6f1  xor     edx, edx; dwFlags
0x18001b6f3  mov     rcx, rax; hHeap
0x18001b6f6  call    cs:__imp_HeapFree
0x18001b6fd  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
