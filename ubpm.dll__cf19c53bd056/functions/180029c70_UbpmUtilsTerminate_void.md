# UbpmUtilsTerminate(void)

- ea: `0x180029c70`
- end: `0x180029e0d`
- name: `?UbpmUtilsTerminate@@YAXXZ`
- size: `413`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, service_task`

## callers

- `0x180029ad0`

## callees

- `0x180019d90`
- `0x180029c70`
- `0x180029e14`
- `0x1800307f0`
- `0x1800347bc`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x180029c8b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180029c8b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180029d51`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180029d51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029c91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029c91`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180029cc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x180029cc4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180029d08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180029d08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180029cb7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180029cb7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dec`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029dec`

## pseudocode

```c
void UbpmUtilsTerminate(void)
{
  unsigned int i; // ebx
  __int64 v1; // rcx

  UbpmUninitializeMaintenance();
  RtlAcquireSRWLockExclusive(&g_TpSubmitLock);
  dword_18004CA80 = GetCurrentThreadId();
  if ( g_pCleanupGroup )
  {
    CloseThreadpoolCleanupGroupMembers(g_pCleanupGroup, 1, 0);
    CloseThreadpoolCleanupGroup(g_pCleanupGroup);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids);
    g_pCleanupGroup = 0;
  }
  if ( g_pThreadpool )
  {
    CloseThreadpool(g_pThreadpool);
    g_pThreadpool = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids);
  }
  dword_18004CA80 = 0;
  RtlReleaseSRWLockExclusive(&g_TpSubmitLock);
  UbpmSystemInterfaceCleanup();
  if ( g_CriticalTasks )
    UBPM_MIDL_user_free(g_CriticalTasks);
  if ( g_CriticalMaintenanceTasks )
    UBPM_MIDL_user_free(g_CriticalMaintenanceTasks);
  if ( g_OOBEExemptedTasks )
    UBPM_MIDL_user_free(g_OOBEExemptedTasks);
  if ( g_CriticalMeasuredTasks )
    UBPM_MIDL_user_free(g_CriticalMeasuredTasks);
  UBPM_MIDL_user_free(*(_QWORD *)&g_pCriticalActions.Data1);
  for ( i = 0; i < 5; ++i )
  {
    v1 = **((_QWORD **)&g_SidData.Revision + 2 * (int)i);
    if ( v1 )
    {
      UBPM_MIDL_user_free(v1);
      **((_QWORD **)&g_SidData.Revision + 2 * (int)i) = 0;
    }
  }
  if ( g_Globals )
  {
    CloseHandle(g_Globals);
    g_Globals = 0;
  }
}

```

## disassembly

```asm
0x180029c70  mov     [rsp+arg_0], rbx
0x180029c75  mov     [rsp+arg_8], rbp
0x180029c7a  push    rdi
0x180029c7b  sub     rsp, 20h
0x180029c7f  call    UbpmUninitializeMaintenance
0x180029c84  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180029c8b  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180029c91  call    cs:__imp_GetCurrentThreadId
0x180029c97  mov     rcx, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180029c9e  lea     rbx, WPP_GLOBAL_Control
0x180029ca5  mov     cs:dword_18004CA80, eax
0x180029cab  test    rcx, rcx
0x180029cae  jz      short loc_180029CFC
0x180029cb0  xor     r8d, r8d; pvCleanupContext
0x180029cb3  lea     edx, [r8+1]; fCancelPendingCallbacks
0x180029cb7  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180029cbd  mov     rcx, cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA; ptpcg
0x180029cc4  call    cs:__imp_CloseThreadpoolCleanupGroup
0x180029cca  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cd1  cmp     rcx, rbx
0x180029cd4  jz      short loc_180029CF1
0x180029cd6  test    byte ptr [rcx+1Ch], 4
0x180029cda  jz      short loc_180029CF1
0x180029cdc  mov     rcx, [rcx+10h]
0x180029ce0  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180029ce7  mov     edx, 11h
0x180029cec  call    WPP_SF_
0x180029cf1  mov     cs:?g_pCleanupGroup@@3PEAU_TP_CLEANUP_GROUP@@EA, 0; _TP_CLEANUP_GROUP * g_pCleanupGroup
0x180029cfc  mov     rcx, cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA; ptpp
0x180029d03  test    rcx, rcx
0x180029d06  jz      short loc_180029D40
0x180029d08  call    cs:__imp_CloseThreadpool
0x180029d0e  mov     cs:?g_pThreadpool@@3PEAU_TP_POOL@@EA, 0; _TP_POOL * g_pThreadpool
0x180029d19  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d20  cmp     rcx, rbx
0x180029d23  jz      short loc_180029D40
0x180029d25  test    byte ptr [rcx+1Ch], 4
0x180029d29  jz      short loc_180029D40
0x180029d2b  mov     rcx, [rcx+10h]
0x180029d2f  lea     r8, WPP_53cebd00d02b39c67ce9f6460dbe4812_Traceguids
0x180029d36  mov     edx, 12h
0x180029d3b  call    WPP_SF_
0x180029d40  lea     rcx, ?g_TpSubmitLock@@3U_UBPM_SRWLOCK@@A; _UBPM_SRWLOCK g_TpSubmitLock
0x180029d47  mov     cs:dword_18004CA80, 0
0x180029d51  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180029d57  call    ?UbpmSystemInterfaceCleanup@@YAXXZ; UbpmSystemInterfaceCleanup(void)
0x180029d5c  mov     rcx, cs:?g_CriticalTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalTasks
0x180029d63  test    rcx, rcx
0x180029d66  jz      short loc_180029D6D
0x180029d68  call    UBPM_MIDL_user_free
0x180029d6d  mov     rcx, cs:?g_CriticalMaintenanceTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMaintenanceTasks
0x180029d74  test    rcx, rcx
0x180029d77  jz      short loc_180029D7E
0x180029d79  call    UBPM_MIDL_user_free
0x180029d7e  mov     rcx, cs:?g_OOBEExemptedTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_OOBEExemptedTasks
0x180029d85  test    rcx, rcx
0x180029d88  jz      short loc_180029D8F
0x180029d8a  call    UBPM_MIDL_user_free
0x180029d8f  mov     rcx, cs:?g_CriticalMeasuredTasks@@3U_UBPM_SPECIAL_TASK_CLASS@@A; _UBPM_SPECIAL_TASK_CLASS g_CriticalMeasuredTasks
0x180029d96  test    rcx, rcx
0x180029d99  jz      short loc_180029DA0
0x180029d9b  call    UBPM_MIDL_user_free
0x180029da0  mov     rcx, qword ptr cs:?g_pCriticalActions@@3PEAU_GUID@@EA.Data1; _GUID * g_pCriticalActions ...
0x180029da7  call    UBPM_MIDL_user_free
0x180029dac  xor     ebx, ebx
0x180029dae  movsxd  rdi, ebx
0x180029db1  lea     rbp, ?g_SidData@@3PAU_SID_DATA@@A; _SID_DATA near * g_SidData
0x180029db8  add     rdi, rdi
0x180029dbb  mov     rax, [rbp+rdi*8+0]
0x180029dc0  mov     rcx, [rax]
0x180029dc3  test    rcx, rcx
0x180029dc6  jz      short loc_180029DD9
0x180029dc8  call    UBPM_MIDL_user_free
0x180029dcd  mov     rax, [rbp+rdi*8+0]
0x180029dd2  mov     qword ptr [rax], 0
0x180029dd9  inc     ebx
0x180029ddb  cmp     ebx, 5
0x180029dde  jb      short loc_180029DAE
0x180029de0  mov     rcx, cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A; hObject
0x180029de7  test    rcx, rcx
0x180029dea  jz      short loc_180029DFD
0x180029dec  call    cs:__imp_CloseHandle
0x180029df2  mov     cs:?g_Globals@@3U_UBPM_GLOBAL_DATA@@A, 0; _UBPM_GLOBAL_DATA g_Globals
0x180029dfd  mov     rbx, [rsp+28h+arg_0]
0x180029e02  mov     rbp, [rsp+28h+arg_8]
0x180029e07  add     rsp, 20h
0x180029e0b  pop     rdi
0x180029e0c  retn
```
