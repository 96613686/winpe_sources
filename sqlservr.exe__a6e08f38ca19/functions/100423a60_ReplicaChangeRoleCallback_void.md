# ReplicaChangeRoleCallback(void)

- ea: `0x100423a60`
- end: `0x100423b07`
- name: `?ReplicaChangeRoleCallback@@YAXXZ`
- size: `167`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x100424c50`

## callees

- `0x100423970`
- `0x100423a60`

## import_xrefs

- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100423ab4`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100423ae6`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100423ab4`
- `sqlmin!?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ` at `0x100423ae6`
- `sqlmin!GetXdbServerGlobals` at `0x100423acb`
- `sqlmin!GetXdbServerGlobals` at `0x100423add`
- `sqlmin!GetXdbServerGlobals` at `0x100423acb`
- `sqlmin!GetXdbServerGlobals` at `0x100423add`
- `sqlmin!?CacheReplicaInfoInMemory@InstanceConfigStoreManager@@QEAAXU_GUID@@_J@Z` at `0x100423afb`
- `sqlmin!?CacheReplicaInfoInMemory@InstanceConfigStoreManager@@QEAAXU_GUID@@_J@Z` at `0x100423afb`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100423a7e`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100423a9a`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100423a7e`
- `hostregdll!HostReg_IsFeatureSwitchOn` at `0x100423a9a`

## string_xrefs

- `0x100423a77`: `SQL.Config`
- `0x100423a93`: `SQL.Config`
- `0x100423a8c`: `EnableReplicaInfoCacheForAuxiliaryReplica`
- `0x100423a70`: `EnableInstanceConfigStore`

## pseudocode

```c
void ReplicaChangeRoleCallback(void)
{
  char IsFeatureSwitchOn; // bl
  __int64 v1; // rcx
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 XdbServerGlobals; // rbx
  __int64 v7; // rcx
  InstanceConfigStoreManager *InstanceConfigStoreManager; // rax
  struct _GUID v9; // [rsp+20h] [rbp-18h] BYREF
  char v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  IsFeatureSwitchOn = HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableInstanceConfigStore", &v10);
  if ( (unsigned __int8)HostReg_IsFeatureSwitchOn(L"SQL.Config", L"EnableReplicaInfoCacheForAuxiliaryReplica", &v10)
    && IsFeatureSwitchOn )
  {
    TraceInitFabric(L"Auxiliary Replica Enabled - ReplicaChangeRoleCallback gets called .\r\n");
    if ( InstanceConfigStoreManager::GetInstanceConfigStoreManager(v1) )
    {
      TraceInitFabric(L"Auxiliary Replica Enabled - caching replica Info In ICS structure.\r\n");
      v9 = *(struct _GUID *)(GetXdbServerGlobals(v3, v2) + 20224);
      XdbServerGlobals = GetXdbServerGlobals(v5, v4);
      InstanceConfigStoreManager = (InstanceConfigStoreManager *)InstanceConfigStoreManager::GetInstanceConfigStoreManager(v7);
      InstanceConfigStoreManager::CacheReplicaInfoInMemory(
        InstanceConfigStoreManager,
        &v9,
        *(_QWORD *)(XdbServerGlobals + 20240));
    }
  }
}

```

## disassembly

```asm
0x100423a60  push    rbx
0x100423a62  sub     rsp, 30h
0x100423a66  lea     r8, [rsp+38h+arg_0]
0x100423a6b  mov     [rsp+38h+arg_0], 0
0x100423a70  lea     rdx, aEnableinstance; "EnableInstanceConfigStore"
0x100423a77  lea     rcx, aSqlConfig; "SQL.Config"
0x100423a7e  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100423a84  lea     r8, [rsp+38h+arg_0]
0x100423a89  movzx   ebx, al
0x100423a8c  lea     rdx, aEnablereplicai; "EnableReplicaInfoCacheForAuxiliaryRepli"...
0x100423a93  lea     rcx, aSqlConfig; "SQL.Config"
0x100423a9a  call    cs:__imp_HostReg_IsFeatureSwitchOn
0x100423aa0  test    al, al
0x100423aa2  jz      short loc_100423B01
0x100423aa4  test    bl, bl
0x100423aa6  jz      short loc_100423B01
0x100423aa8  lea     rcx, aAuxiliaryRepli_0; "Auxiliary Replica Enabled - ReplicaChan"...
0x100423aaf  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100423ab4  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x100423aba  test    rax, rax
0x100423abd  jz      short loc_100423B01
0x100423abf  lea     rcx, aAuxiliaryRepli_6; "Auxiliary Replica Enabled - caching rep"...
0x100423ac6  call    ?TraceInitFabric@@YAXPEB_WZZ; TraceInitFabric(wchar_t const *,...)
0x100423acb  call    cs:__imp_GetXdbServerGlobals
0x100423ad1  movups  xmm0, xmmword ptr [rax+4F00h]
0x100423ad8  movaps  xmmword ptr [rsp+38h+var_18.Data1], xmm0
0x100423add  call    cs:__imp_GetXdbServerGlobals
0x100423ae3  mov     rbx, rax
0x100423ae6  call    cs:__imp_?GetInstanceConfigStoreManager@InstanceConfigStoreManager@@SAPEAV1@XZ; InstanceConfigStoreManager::GetInstanceConfigStoreManager(void)
0x100423aec  mov     r8, [rbx+4F10h]
0x100423af3  lea     rdx, [rsp+38h+var_18]
0x100423af8  mov     rcx, rax
0x100423afb  call    cs:__imp_?CacheReplicaInfoInMemory@InstanceConfigStoreManager@@QEAAXU_GUID@@_J@Z; InstanceConfigStoreManager::CacheReplicaInfoInMemory(_GUID,__int64)
0x100423b01  add     rsp, 30h
0x100423b05  pop     rbx
0x100423b06  retn
```
