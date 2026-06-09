# SpLsaModeInitialize(ulong,ulong *,_SECPKG_FUNCTION_TABLE * *,ulong *)

- ea: `0x180017a40`
- end: `0x180017b65`
- name: `?SpLsaModeInitialize@@YAJKPEAKPEAPEAU_SECPKG_FUNCTION_TABLE@@0@Z`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int *, struct _SECPKG_FUNCTION_TABLE **, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a2bc`
- `0x18001627c`
- `0x180017a40`
- `0x180017cd8`
- `0x18001b7e4`
- `0x18001be88`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017a80`
- `ntdll!RtlInitializeCriticalSection` at `0x180017b1e`
- `ntdll!RtlInitializeCriticalSection` at `0x180017b1e`
- `LSASRV!LsaIRegisterNotification` at `0x180017aaf`
- `LSASRV!LsaIRegisterNotification` at `0x180017aaf`

## pseudocode

```c
__int64 __fastcall SpLsaModeInitialize(
        __int64 a1,
        unsigned int *a2,
        struct _SECPKG_FUNCTION_TABLE **a3,
        unsigned int *a4)
{
  HKEY v4; // rcx
  int v5; // ebx

  *a2 = 0x40000;
  *a3 = &TSGlobalFunctionTable;
  *a4 = 1;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\LSA\\CredSSP", 0, 0x20019u, &g_hKeyParams);
  g_LsaNotification = (void *)LsaIRegisterNotification(TSWatchParamKey, 0, 4);
  if ( g_LsaNotification )
  {
    TSGetRegParams(v4);
    SafeAllocaInitialize();
    qword_180025838 = 0;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_TSPkgDebugTraceGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WPP_MAIN_CB = 0;
    qword_180025840 = 1;
    WppInitUm();
    RtlInitializeCriticalSection(&WTSVirtualChannelLoaderLock);
    v5 = TSContextTrackingInit();
    if ( v5 >= 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_76ddc22de44c3ba40c130d8634e0bbce_Traceguids);
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180017a40  push    rbx
0x180017a42  sub     rsp, 40h
0x180017a46  mov     dword ptr [rdx], 40000h
0x180017a4c  lea     rax, ?TSGlobalFunctionTable@@3U_SECPKG_FUNCTION_TABLE@@A; _SECPKG_FUNCTION_TABLE TSGlobalFunctionTable
0x180017a53  mov     [r8], rax
0x180017a56  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\LSA"...
0x180017a5d  mov     dword ptr [r9], 1
0x180017a64  lea     rax, ?g_hKeyParams@@3PEAUHKEY__@@EA; HKEY__ * g_hKeyParams
0x180017a6b  mov     r9d, 20019h; samDesired
0x180017a71  mov     [rsp+48h+phkResult], rax; phkResult
0x180017a76  xor     r8d, r8d; ulOptions
0x180017a79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180017a80  call    cs:__imp_RegOpenKeyExW
0x180017a86  xor     edx, edx
0x180017a88  mov     [rsp+48h+var_18], 0
0x180017a91  mov     [rsp+48h+var_20], 0
0x180017a99  lea     rcx, ?TSWatchParamKey@@YAKPEAX@Z; TSWatchParamKey(void *)
0x180017aa0  mov     dword ptr [rsp+48h+phkResult], 0
0x180017aa8  lea     r9d, [rdx+4]
0x180017aac  mov     r8d, r9d
0x180017aaf  call    cs:__imp_LsaIRegisterNotification
0x180017ab5  mov     cs:?g_LsaNotification@@3PEAXEA, rax; void * g_LsaNotification
0x180017abc  test    rax, rax
0x180017abf  jnz     short loc_180017ACB
0x180017ac1  mov     ebx, 0C000009Ah
0x180017ac6  jmp     loc_180017B5D
0x180017acb  call    ?TSGetRegParams@@YAXPEAUHKEY__@@@Z; TSGetRegParams(HKEY__ *)
0x180017ad0  call    SafeAllocaInitialize
0x180017ad5  lea     rax, WPP_ThisDir_CTLGUID_TSPkgDebugTraceGuid
0x180017adc  mov     cs:qword_180025838, 0
0x180017ae7  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180017aee  lea     rax, WPP_MAIN_CB
0x180017af5  mov     cs:WPP_GLOBAL_Control, rax
0x180017afc  mov     cs:WPP_MAIN_CB, 0
0x180017b07  mov     cs:qword_180025840, 1
0x180017b12  call    WppInitUm
0x180017b17  lea     rcx, ?WTSVirtualChannelLoaderLock@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x180017b1e  call    cs:__imp_RtlInitializeCriticalSection
0x180017b24  call    ?TSContextTrackingInit@@YAJXZ; TSContextTrackingInit(void)
0x180017b29  mov     ebx, eax
0x180017b2b  test    eax, eax
0x180017b2d  js      short loc_180017B5D
0x180017b2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b36  lea     rax, WPP_GLOBAL_Control
0x180017b3d  cmp     rcx, rax
0x180017b40  jz      short loc_180017B5D
0x180017b42  test    byte ptr [rcx+1Ch], 4
0x180017b46  jz      short loc_180017B5D
0x180017b48  mov     rcx, [rcx+10h]
0x180017b4c  lea     r8, WPP_76ddc22de44c3ba40c130d8634e0bbce_Traceguids
0x180017b53  mov     edx, 0Ah
0x180017b58  call    WPP_SF_
0x180017b5d  mov     eax, ebx
0x180017b5f  add     rsp, 40h
0x180017b63  pop     rbx
0x180017b64  retn
```
