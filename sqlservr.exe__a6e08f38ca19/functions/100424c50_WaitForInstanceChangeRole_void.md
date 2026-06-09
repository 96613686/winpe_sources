# WaitForInstanceChangeRole(void)

- ea: `0x100424c50`
- end: `0x100424e3a`
- name: `?WaitForInstanceChangeRole@@YAXXZ`
- size: `490`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x100425030`

## callees

- `0x100423970`
- `0x100423a60`
- `0x100424c50`

## import_xrefs

- `KERNEL32!Sleep` at `0x100424d6b`
- `KERNEL32!Sleep` at `0x100424d6b`
- `KERNEL32!HeapFree` at `0x100424e14`
- `KERNEL32!HeapFree` at `0x100424e14`
- `KERNEL32!GetProcessHeap` at `0x100424e06`
- `KERNEL32!GetProcessHeap` at `0x100424e06`
- `sqlmin!?IsAuxiliaryReplicaRestart@InstanceConfigStoreManager@@QEAA_NU_GUID@@_J@Z` at `0x100424d5c`
- `sqlmin!?IsAuxiliaryReplicaRestart@InstanceConfigStoreManager@@QEAA_NU_GUID@@_J@Z` at `0x100424d5c`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100424d47`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100424d47`
- `sqlmin!GetXdbServerGlobals` at `0x100424cf7`
- `sqlmin!GetXdbServerGlobals` at `0x100424d1c`
- `sqlmin!GetXdbServerGlobals` at `0x100424d2c`
- `sqlmin!GetXdbServerGlobals` at `0x100424d3e`
- `sqlmin!GetXdbServerGlobals` at `0x100424d84`
- `sqlmin!GetXdbServerGlobals` at `0x100424da9`
- `sqlmin!GetXdbServerGlobals` at `0x100424de8`
- `sqlmin!GetXdbServerGlobals` at `0x100424cf7`
- `sqlmin!GetXdbServerGlobals` at `0x100424d1c`
- `sqlmin!GetXdbServerGlobals` at `0x100424d2c`
- `sqlmin!GetXdbServerGlobals` at `0x100424d3e`
- `sqlmin!GetXdbServerGlobals` at `0x100424d84`
- `sqlmin!GetXdbServerGlobals` at `0x100424da9`
- `sqlmin!GetXdbServerGlobals` at `0x100424de8`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x100424ce1`
- `api-ms-win-crt-convert-l1-1-0!_wtoi` at `0x100424ce1`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x100424cc7`
- `hostregdll!HostReg_ReadConfigurationSetting` at `0x100424cc7`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424c87`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424ca3`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424c87`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100424ca3`
- `RgThinClient!RgClient_SetReplicaType` at `0x100424dfa`
- `RgThinClient!RgClient_SetReplicaType` at `0x100424dfa`

## string_xrefs

- `0x100424c80`: `SQL.Config`
- `0x100424c9c`: `SQL.Config`
- `0x100424cc0`: `SQL.Config`
- `0x100424c95`: `EnableReplicaInfoCacheForAuxiliaryReplica`
- `0x100424c79`: `EnableInstanceConfigStore`
- `0x100424ceb`: `Auxiliary Replica Enabled - Read change role max wait time from config failed\n`
- `0x100424cb2`: `MarkerServiceChangeRoleThresholdInMilliSeconds`
- `0x100424d78`: `Auxiliary Replica Enabled - is same replica restart, Waited for [%d] ms before InstanceOpen.\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void WaitForInstanceChangeRole(void)
{
  int v0; // esi
  unsigned int v1; // edi
  char IsFeatureSwitchOn; // bp
  char v3; // r14
  const wchar_t *v4; // rax
  wchar_t *v5; // r15
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 XdbServerGlobals; // rbx
  __int64 v15; // rcx
  InstanceConfigStoreManager *InstanceConfigStoreManager; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  unsigned int v22; // ebx
  __int64 v23; // rdx
  __int64 v24; // rcx
  HANDLE ProcessHeap; // rax
  struct _GUID v26; // [rsp+30h] [rbp-38h] BYREF
  char v27; // [rsp+70h] [rbp+8h] BYREF
  int v28; // [rsp+78h] [rbp+10h] BYREF
  const wchar_t *v29; // [rsp+80h] [rbp+18h]

  v0 = 0;
  v1 = 0;
  v28 = 0;
  v27 = 0;
  IsFeatureSwitchOn = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableInstanceConfigStore", &v27);
  v3 = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableReplicaInfoCacheForAuxiliaryReplica", &v27);
  v4 = (const wchar_t *)HostReg_ReadConfigurationSetting(
                          L"SQL.Config",
                          L"SQL",
                          L"MarkerServiceChangeRoleThresholdInMilliSeconds",
                          &v28);
  v5 = (wchar_t *)v4;
  v29 = v4;
  if ( v28 )
    TraceInitFabric(L"Auxiliary Replica Enabled - Read change role max wait time from config failed\r\n");
  else
    v0 = _wtoi(v4);
  while ( *(_DWORD *)(GetXdbServerGlobals(v7, v6) + 20248) == -1 && (int)v1 < v0 )
  {
    if ( v3 )
    {
      if ( IsFeatureSwitchOn )
      {
        if ( *(_QWORD *)(GetXdbServerGlobals(v9, v8) + 20240) )
        {
          v26 = *(struct _GUID *)(GetXdbServerGlobals(v11, v10) + 20224);
          XdbServerGlobals = GetXdbServerGlobals(v13, v12);
          InstanceConfigStoreManager = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager(v15);
          if ( InstanceConfigStoreManager::IsAuxiliaryReplicaRestart(
                 InstanceConfigStoreManager,
                 &v26,
                 *(_QWORD *)(XdbServerGlobals + 20240)) )
          {
            TraceInitFabric(
              L"Auxiliary Replica Enabled - is same replica restart, Waited for [%d] ms before InstanceOpen.\r\n",
              v1);
            *(_DWORD *)(GetXdbServerGlobals(v18, v17) + 20256) = 1;
            v19 = 6;
            goto LABEL_16;
          }
        }
      }
    }
    Sleep(0x32u);
    v1 += 50;
  }
  TraceInitFabric(L"Auxiliary Replica Enabled - Waited for [%d] ms before changeRole was invoked\r\n", v1);
  v22 = *(_DWORD *)(GetXdbServerGlobals(v21, v20) + 20248);
  if ( v22 - 5 <= 2 )
  {
    ReplicaChangeRoleCallback();
    TraceInitFabric(L"Auxiliary Replica Enabled - Set Replica Role [%d] to RG Client.\r\n", v22);
    *(_DWORD *)(GetXdbServerGlobals(v24, v23) + 20256) = 1;
  }
  else
  {
    TraceInitFabric(L"Auxiliary Replica Enabled - Set Replica Role [%d] to RG Client.\r\n", v22);
  }
  v19 = v22;
LABEL_16:
  RgClient_SetReplicaType(v19);
  if ( v5 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v5);
  }
}

```

## disassembly

```asm
0x100424c50  mov     rax, rsp
0x100424c53  push    rbp
0x100424c54  push    rsi
0x100424c55  push    rdi
0x100424c56  push    r14
0x100424c58  push    r15
0x100424c5a  sub     rsp, 40h
0x100424c5e  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x100424c66  mov     [rax+20h], rbx
0x100424c6a  xor     esi, esi
0x100424c6c  xor     edi, edi
0x100424c6e  mov     [rax+10h], esi
0x100424c71  mov     [rax+8], sil
0x100424c75  lea     r8, [rax+8]
0x100424c79  lea     rdx, aEnableinstance; "EnableInstanceConfigStore"
0x100424c80  lea     rcx, aSqlConfig; "SQL.Config"
0x100424c87  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100424c8d  movzx   ebp, al
0x100424c90  lea     r8, [rsp+68h+arg_0]
0x100424c95  lea     rdx, aEnablereplicai; "EnableReplicaInfoCacheForAuxiliaryRepli"...
0x100424c9c  lea     rcx, aSqlConfig; "SQL.Config"
0x100424ca3  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100424ca9  movzx   r14d, al
0x100424cad  lea     r9, [rsp+68h+arg_8]
0x100424cb2  lea     r8, aMarkerservicec; "MarkerServiceChangeRoleThresholdInMilli"...
0x100424cb9  lea     rdx, aSql; "SQL"
0x100424cc0  lea     rcx, aSqlConfig; "SQL.Config"
0x100424cc7  call    cs:__imp_HostReg_ReadConfigurationSetting
0x100424ccd  mov     r15, rax
0x100424cd0  mov     [rsp+68h+arg_10], rax
0x100424cd8  cmp     [rsp+68h+arg_8], edi
0x100424cdc  jnz     short loc_100424CEB
0x100424cde  mov     rcx, rax; String
0x100424ce1  call    cs:__imp__wtoi
0x100424ce7  mov     esi, eax
0x100424ce9  jmp     short loc_100424CF7
0x100424ceb  lea     rcx, aAuxiliaryRepli_4; "Auxiliary Replica Enabled - Read change"...
0x100424cf2  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100424cf7  call    cs:__imp_GetXdbServerGlobals
0x100424cfd  cmp     dword ptr [rax+4F18h], 0FFFFFFFFh
0x100424d04  jnz     loc_100424D9B
0x100424d0a  cmp     edi, esi
0x100424d0c  jge     loc_100424D9B
0x100424d12  test    r14b, r14b
0x100424d15  jz      short loc_100424D66
0x100424d17  test    bpl, bpl
0x100424d1a  jz      short loc_100424D66
0x100424d1c  call    cs:__imp_GetXdbServerGlobals
0x100424d22  cmp     qword ptr [rax+4F10h], 0
0x100424d2a  jz      short loc_100424D66
0x100424d2c  call    cs:__imp_GetXdbServerGlobals
0x100424d32  movups  xmm0, xmmword ptr [rax+4F00h]
0x100424d39  movaps  [rsp+68h+var_38], xmm0
0x100424d3e  call    cs:__imp_GetXdbServerGlobals
0x100424d44  mov     rbx, rax
0x100424d47  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x100424d4d  mov     rcx, rax
0x100424d50  mov     r8, [rbx+4F10h]
0x100424d57  lea     rdx, [rsp+68h+var_38]
0x100424d5c  call    cs:__imp_?IsAuxiliaryReplicaRestart@InstanceConfigStoreManager@@QEAA_NU_GUID@@_J@Z; InstanceConfigStoreManager::IsAuxiliaryReplicaRestart(_GUID,__int64)
0x100424d62  test    al, al
0x100424d64  jnz     short loc_100424D76
0x100424d66  mov     ecx, 32h ; '2'; dwMilliseconds
0x100424d6b  call    cs:__imp_Sleep
0x100424d71  add     edi, 32h ; '2'
0x100424d74  jmp     short loc_100424CF7
0x100424d76  mov     edx, edi
0x100424d78  lea     rcx, aAuxiliaryRepli_3; "Auxiliary Replica Enabled - is same rep"...
0x100424d7f  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100424d84  call    cs:__imp_GetXdbServerGlobals
0x100424d8a  mov     dword ptr [rax+4F20h], 1
0x100424d94  mov     ecx, 6
0x100424d99  jmp     short loc_100424DFA
0x100424d9b  mov     edx, edi
0x100424d9d  lea     rcx, aAuxiliaryRepli_5; "Auxiliary Replica Enabled - Waited for "...
0x100424da4  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100424da9  call    cs:__imp_GetXdbServerGlobals
0x100424daf  mov     ebx, [rax+4F18h]
0x100424db5  lea     eax, [rbx-5]
0x100424db8  cmp     eax, 2
0x100424dbb  jbe     short loc_100424DCD
0x100424dbd  mov     edx, ebx
0x100424dbf  lea     rcx, aAuxiliaryRepli_1; "Auxiliary Replica Enabled - Set Replica"...
0x100424dc6  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100424dcb  jmp     short loc_100424DF8
0x100424dcd  call    ?ReplicaChangeRoleCallback@@YAXXZ; ReplicaChangeRoleCallback(void)
0x100424dd2  mov     edx, ebx
0x100424dd4  lea     rcx, aAuxiliaryRepli_1; "Auxiliary Replica Enabled - Set Replica"...
0x100424ddb  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100424de0  lea     eax, [rbx-5]
0x100424de3  cmp     eax, 2
0x100424de6  ja      short loc_100424DF8
0x100424de8  call    cs:__imp_GetXdbServerGlobals
0x100424dee  mov     dword ptr [rax+4F20h], 1
0x100424df8  mov     ecx, ebx
0x100424dfa  call    cs:__imp_RgClient_SetReplicaType
0x100424e00  nop
0x100424e01  test    r15, r15
0x100424e04  jz      short loc_100424E26
0x100424e06  call    cs:__imp_GetProcessHeap
0x100424e0c  mov     rcx, rax; hHeap
0x100424e0f  mov     r8, r15; lpMem
0x100424e12  xor     edx, edx; dwFlags
0x100424e14  call    cs:__imp_HeapFree
0x100424e1a  mov     [rsp+68h+arg_10], 0
0x100424e26  mov     rbx, [rsp+68h+arg_18]
0x100424e2e  add     rsp, 40h
0x100424e32  pop     r15
0x100424e34  pop     r14
0x100424e36  pop     rdi
0x100424e37  pop     rsi
0x100424e38  pop     rbp
0x100424e39  retn
```
