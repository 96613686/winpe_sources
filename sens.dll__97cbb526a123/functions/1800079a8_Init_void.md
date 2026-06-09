# Init(void)

- ea: `0x1800079a8`
- end: `0x180007d09`
- name: `?Init@@YAHXZ`
- size: `865`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180007ecc`

## callees

- `0x18000732c`
- `0x180007698`
- `0x1800079a8`
- `0x180008300`
- `0x1800093b0`
- `0x18000a766`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007bfe`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180007bfe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007c4e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180007c4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007c78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007be1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007be1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007aed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180007aed`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007a83`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180007a83`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007cee`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180007cee`

## pseudocode

```c
__int64 Init(void)
{
  HRESULT v0; // eax
  int v1; // esi
  unsigned int v2; // edi
  HRESULT v3; // eax
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  DWORD LastError; // eax
  LPVOID ppv; // [rsp+50h] [rbp+8h] BYREF

  ppv = 0;
  TraceLoggingRegisterEx_EventRegister_EventSetInformation();
  gpSensCache = 0;
  gdwMediaSenseState = 1;
  gpChangeCF = 0;
  ghSensHeap = 0;
  ghSensFileMap = 0;
  ghSensStartedEvent = 0;
  ghSCM = 0;
  ghRasMan = 0;
  gIsRasInstalled = 0;
  gdwLocked = 0;
  gdwLastLANTime = 0;
  gdwLANState = 0;
  gdwLastWANTime = 0;
  gdwWANState = 0;
  gdwRegCO = 0;
  g_cFilterObj = 0;
  memset_0(&gIfState, 0, 0xC8u);
  memset_0(&gIpStats, 0, sizeof(gIpStats));
  *(_QWORD *)&gSystemPowerState.ACLineStatus = 0;
  gSystemPowerState.BatteryFullLifeTime = 0;
  *(_OWORD *)&gSensLock.DebugInfo = 0;
  gSensLock.SpinCount = 0;
  *(_OWORD *)&gSensLock.OwningThread = 0;
  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
  {
    v1 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids,
        (unsigned int)v0);
    }
    v2 = 0;
    goto LABEL_39;
  }
  v2 = 0;
  v1 = 1;
  v3 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v5 = 22;
    goto LABEL_12;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 5, 1);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v5 = 23;
    goto LABEL_12;
  }
  v3 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
  if ( v3 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_39;
    }
    v5 = 24;
LABEL_12:
    WPP_SF_d(v4[2], v5, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids, (unsigned int)v3);
    goto LABEL_39;
  }
  ghSensHeap = GetProcessHeap();
  if ( ghSensHeap )
  {
    InitializeCriticalSection(&gSensLock);
    if ( !CreateSensCache()
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
    }
    ghSensStartedEvent = CreateEventW(0, 1, 0, L"SENS Started Event");
    if ( ghSensStartedEvent )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids, LastError);
    }
    v2 = 1;
  }
LABEL_39:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( !v2 && v1 == 1 )
    CoUninitialize();
  return v2;
}

```

## disassembly

```asm
0x1800079a8  mov     [rsp+arg_8], rbx
0x1800079ad  mov     [rsp+arg_10], rbp
0x1800079b2  push    rsi
0x1800079b3  push    rdi
0x1800079b4  push    r14
0x1800079b6  sub     rsp, 30h
0x1800079ba  xor     ebp, ebp
0x1800079bc  mov     [rsp+48h+arg_0], rbp
0x1800079c1  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800079c6  lea     r14d, [rbp+1]
0x1800079ca  mov     cs:?gpSensCache@@3PEAU_SENS_CACHE@@EA, rbp; _SENS_CACHE * gpSensCache
0x1800079d1  xor     edx, edx; Val
0x1800079d3  mov     cs:?gdwMediaSenseState@@3KA, r14d; ulong gdwMediaSenseState
0x1800079da  mov     r8d, 0C8h; Size
0x1800079e0  mov     cs:?gpChangeCF@@3PEAUIClassFactory@@EA, rbp; IClassFactory * gpChangeCF
0x1800079e7  lea     rcx, ?gIfState@@3PAU_IF_STATE@@A; void *
0x1800079ee  mov     cs:?ghSensHeap@@3PEAXEA, rbp; void * ghSensHeap
0x1800079f5  mov     cs:?ghSensFileMap@@3PEAXEA, rbp; void * ghSensFileMap
0x1800079fc  mov     cs:?ghSensStartedEvent@@3PEAXEA, rbp; void * ghSensStartedEvent
0x180007a03  mov     cs:?ghSCM@@3PEAUSC_HANDLE__@@EA, rbp; SC_HANDLE__ * ghSCM
0x180007a0a  mov     cs:?ghRasMan@@3PEAUSC_HANDLE__@@EA, rbp; SC_HANDLE__ * ghRasMan
0x180007a11  mov     cs:?gIsRasInstalled@@3W4SERVICE_INSTALL_STATE@@A, ebp; SERVICE_INSTALL_STATE gIsRasInstalled
0x180007a17  mov     cs:?gdwLocked@@3KA, ebp; ulong gdwLocked
0x180007a1d  mov     cs:?gdwLastLANTime@@3JA, ebp; long gdwLastLANTime
0x180007a23  mov     cs:?gdwLANState@@3JA, ebp; long gdwLANState
0x180007a29  mov     cs:?gdwLastWANTime@@3JA, ebp; long gdwLastWANTime
0x180007a2f  mov     cs:?gdwWANState@@3JA, ebp; long gdwWANState
0x180007a35  mov     cs:?gdwRegCO@@3KA, ebp; ulong gdwRegCO
0x180007a3b  mov     cs:?g_cFilterObj@@3JA, ebp; long g_cFilterObj
0x180007a41  call    memset_0
0x180007a46  xor     edx, edx; Val
0x180007a48  lea     r8d, [rbp+5Ch]; Size
0x180007a4c  lea     rcx, ?gIpStats@@3U_MIB_IPSTATS_LH@@A; void *
0x180007a53  call    memset_0
0x180007a58  xor     eax, eax
0x180007a5a  xorps   xmm0, xmm0
0x180007a5d  xor     edx, edx; dwCoInit
0x180007a5f  mov     qword ptr cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.ACLineStatus, rax; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180007a66  xor     ecx, ecx; pvReserved
0x180007a68  mov     cs:?gSystemPowerState@@3U_SYSTEM_POWER_STATUS@@A.BatteryFullLifeTime, eax; _SYSTEM_POWER_STATUS gSystemPowerState ...
0x180007a6e  movups  xmmword ptr cs:?gSensLock@@3U_RTL_CRITICAL_SECTION@@A.DebugInfo, xmm0; _RTL_CRITICAL_SECTION gSensLock ...
0x180007a75  mov     cs:?gSensLock@@3U_RTL_CRITICAL_SECTION@@A.SpinCount, rax; _RTL_CRITICAL_SECTION gSensLock ...
0x180007a7c  movups  xmmword ptr cs:?gSensLock@@3U_RTL_CRITICAL_SECTION@@A.OwningThread, xmm0; _RTL_CRITICAL_SECTION gSensLock ...
0x180007a83  call    cs:__imp_CoInitializeEx
0x180007a89  test    eax, eax
0x180007a8b  jns     short loc_180007ACB
0x180007a8d  mov     esi, ebp
0x180007a8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a96  lea     rbx, WPP_GLOBAL_Control
0x180007a9d  cmp     rcx, rbx
0x180007aa0  jz      short loc_180007AC4
0x180007aa2  test    [rcx+1Ch], r14b
0x180007aa6  jz      short loc_180007AC4
0x180007aa8  cmp     byte ptr [rcx+19h], 2
0x180007aac  jb      short loc_180007AC4
0x180007aae  mov     rcx, [rcx+10h]
0x180007ab2  lea     edx, [rbp+15h]
0x180007ab5  mov     r9d, eax
0x180007ab8  lea     r8, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007abf  call    WPP_SF_d
0x180007ac4  mov     edi, ebp
0x180007ac6  jmp     loc_180007CCF
0x180007acb  lea     rax, [rsp+48h+arg_0]
0x180007ad0  mov     r8d, r14d; dwClsContext
0x180007ad3  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x180007ada  mov     [rsp+48h+ppv], rax; ppv
0x180007adf  xor     edx, edx; pUnkOuter
0x180007ae1  lea     rcx, CLSID_GlobalOptions; rclsid
0x180007ae8  mov     edi, ebp
0x180007aea  mov     esi, r14d
0x180007aed  call    cs:__imp_CoCreateInstance
0x180007af3  test    eax, eax
0x180007af5  jns     short loc_180007B3F
0x180007af7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007afe  lea     rbx, WPP_GLOBAL_Control
0x180007b05  cmp     rcx, rbx
0x180007b08  jz      loc_180007CCF
0x180007b0e  test    [rcx+1Ch], r14b
0x180007b12  jz      loc_180007CCF
0x180007b18  cmp     byte ptr [rcx+19h], 2
0x180007b1c  jb      loc_180007CCF
0x180007b22  mov     edx, 16h
0x180007b27  mov     rcx, [rcx+10h]
0x180007b2b  lea     r8, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007b32  mov     r9d, eax
0x180007b35  call    WPP_SF_d
0x180007b3a  jmp     loc_180007CCF
0x180007b3f  mov     rcx, [rsp+48h+arg_0]
0x180007b44  mov     r8, r14
0x180007b47  mov     edx, 5
0x180007b4c  mov     rax, [rcx]
0x180007b4f  mov     rax, [rax+18h]
0x180007b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b58  test    eax, eax
0x180007b5a  jns     short loc_180007B8E
0x180007b5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b63  lea     rbx, WPP_GLOBAL_Control
0x180007b6a  cmp     rcx, rbx
0x180007b6d  jz      loc_180007CCF
0x180007b73  test    [rcx+1Ch], r14b
0x180007b77  jz      loc_180007CCF
0x180007b7d  cmp     byte ptr [rcx+19h], 2
0x180007b81  jb      loc_180007CCF
0x180007b87  mov     edx, 17h
0x180007b8c  jmp     short loc_180007B27
0x180007b8e  mov     rcx, [rsp+48h+arg_0]
0x180007b93  mov     r8d, 2
0x180007b99  mov     edx, r14d
0x180007b9c  mov     rax, [rcx]
0x180007b9f  mov     rax, [rax+18h]
0x180007ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba8  test    eax, eax
0x180007baa  jns     short loc_180007BE1
0x180007bac  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bb3  lea     rbx, WPP_GLOBAL_Control
0x180007bba  cmp     rcx, rbx
0x180007bbd  jz      loc_180007CCF
0x180007bc3  test    [rcx+1Ch], r14b
0x180007bc7  jz      loc_180007CCF
0x180007bcd  cmp     byte ptr [rcx+19h], 2
0x180007bd1  jb      loc_180007CCF
0x180007bd7  mov     edx, 18h
0x180007bdc  jmp     loc_180007B27
0x180007be1  call    cs:__imp_GetProcessHeap
0x180007be7  mov     cs:?ghSensHeap@@3PEAXEA, rax; void * ghSensHeap
0x180007bee  test    rax, rax
0x180007bf1  jz      loc_180007CCF
0x180007bf7  lea     rcx, ?gSensLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180007bfe  call    cs:__imp_InitializeCriticalSection
0x180007c04  call    ?CreateSensCache@@YAHXZ; CreateSensCache(void)
0x180007c09  lea     rbx, WPP_GLOBAL_Control
0x180007c10  test    eax, eax
0x180007c12  jnz     short loc_180007C3F
0x180007c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c1b  cmp     rcx, rbx
0x180007c1e  jz      short loc_180007C3F
0x180007c20  test    [rcx+1Ch], r14b
0x180007c24  jz      short loc_180007C3F
0x180007c26  cmp     byte ptr [rcx+19h], 2
0x180007c2a  jb      short loc_180007C3F
0x180007c2c  mov     rcx, [rcx+10h]
0x180007c30  lea     edx, [rax+19h]
0x180007c33  lea     r8, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007c3a  call    WPP_SF_
0x180007c3f  lea     r9, aSensStartedEve; "SENS Started Event"
0x180007c46  xor     r8d, r8d; bInitialState
0x180007c49  mov     edx, r14d; bManualReset
0x180007c4c  xor     ecx, ecx; lpEventAttributes
0x180007c4e  call    cs:__imp_CreateEventW
0x180007c54  mov     cs:?ghSensStartedEvent@@3PEAXEA, rax; void * ghSensStartedEvent
0x180007c5b  test    rax, rax
0x180007c5e  jnz     short loc_180007C9F
0x180007c60  mov     rax, cs:WPP_GLOBAL_Control
0x180007c67  cmp     rax, rbx
0x180007c6a  jz      short loc_180007CCC
0x180007c6c  test    [rax+1Ch], r14b
0x180007c70  jz      short loc_180007CCC
0x180007c72  cmp     byte ptr [rax+19h], 2
0x180007c76  jb      short loc_180007CCC
0x180007c78  call    cs:__imp_GetLastError
0x180007c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c85  lea     r8, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007c8c  mov     edx, 1Ah
0x180007c91  mov     r9d, eax
0x180007c94  mov     rcx, [rcx+10h]
0x180007c98  call    WPP_SF_d
0x180007c9d  jmp     short loc_180007CCC
0x180007c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ca6  cmp     rcx, rbx
0x180007ca9  jz      short loc_180007CCC
0x180007cab  test    [rcx+1Ch], r14b
0x180007caf  jz      short loc_180007CCC
0x180007cb1  cmp     byte ptr [rcx+19h], 5
0x180007cb5  jb      short loc_180007CCC
0x180007cb7  mov     rcx, [rcx+10h]
0x180007cbb  lea     r8, WPP_806191927c0c3ac359d6ef1d0e80ee46_Traceguids
0x180007cc2  mov     edx, 1Bh
0x180007cc7  call    WPP_SF_
0x180007ccc  mov     edi, r14d
0x180007ccf  mov     rcx, [rsp+48h+arg_0]
0x180007cd4  test    rcx, rcx
0x180007cd7  jz      short loc_180007CE5
0x180007cd9  mov     rax, [rcx]
0x180007cdc  mov     rax, [rax+10h]
0x180007ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce5  test    edi, edi
0x180007ce7  jnz     short loc_180007CF4
0x180007ce9  cmp     esi, r14d
0x180007cec  jnz     short loc_180007CF4
0x180007cee  call    cs:__imp_CoUninitialize
0x180007cf4  mov     rbx, [rsp+48h+arg_8]
0x180007cf9  mov     eax, edi
0x180007cfb  mov     rbp, [rsp+48h+arg_10]
0x180007d00  add     rsp, 30h
0x180007d04  pop     r14
0x180007d06  pop     rdi
0x180007d07  pop     rsi
0x180007d08  retn
```
