# UmpoInternalCleanupAdvancedPowerSettings

- ea: `0x18000e844`
- end: `0x18000e947`
- name: `UmpoInternalCleanupAdvancedPowerSettings`
- size: `259`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180013630`

## callees

- `0x18000e844`
- `0x18000f3dc`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000e890`
- `ntdll!RtlFreeHeap` at `0x18000e8e2`
- `ntdll!RtlFreeHeap` at `0x18000e890`
- `ntdll!RtlFreeHeap` at `0x18000e8e2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000e855`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000e870`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000e855`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x18000e870`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e928`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e928`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e916`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e916`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8ae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8ae`

## pseudocode

```c
void UmpoInternalCleanupAdvancedPowerSettings()
{
  __int64 i; // rbx
  __int64 v1; // rcx
  _QWORD *v2; // rax

  RtlUnsubscribeWnfNotificationWaitForCompletion(ProvisioningCompleteSubscription);
  for ( i = 0; (unsigned int)i < UmpoAdvancedSettingCount; i = (unsigned int)(i + 1) )
    RtlUnsubscribeWnfNotificationWaitForCompletion(*((_QWORD *)UmpoAdvancedPowerSettingWnfSubscription + i));
  RtlFreeHeap(UmpoHeapHandle, 0, UmpoAdvancedPowerSettingWnfSubscription);
  if ( byte_180024D68 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  EnterCriticalSection(&UmpoAdvancedSettingListLock);
  while ( 1 )
  {
    v2 = UmpoAdvancedSettingList;
    if ( UmpoAdvancedSettingList == &UmpoAdvancedSettingList )
      break;
    if ( *((PVOID **)UmpoAdvancedSettingList + 1) != &UmpoAdvancedSettingList
      || (v1 = qword_180024CA8, *(PVOID **)qword_180024CA8 != &UmpoAdvancedSettingList) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)qword_180024CA8 = UmpoAdvancedSettingList;
    v2[1] = v1;
    RtlFreeHeap(UmpoHeapHandle, 0, v2);
  }
  UmpoAdvancedSettingCount = 0;
  UmpoIsPolicyManagerSupported = 0;
  if ( byte_180024D68 != 1 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LeaveCriticalSection(&UmpoAdvancedSettingListLock);
  if ( byte_180024D68 )
  {
    DeleteCriticalSection(&UmpoAdvancedSettingListLock);
    byte_180024D68 = 0;
  }
}

```

## disassembly

```asm
0x18000e844  mov     [rsp+arg_0], rbx
0x18000e849  push    rsi
0x18000e84a  sub     rsp, 20h
0x18000e84e  mov     rcx, cs:ProvisioningCompleteSubscription
0x18000e855  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000e85b  xor     ebx, ebx
0x18000e85d  cmp     cs:UmpoAdvancedSettingCount, ebx
0x18000e863  jbe     short loc_18000E880
0x18000e865  mov     rcx, cs:UmpoAdvancedPowerSettingWnfSubscription
0x18000e86c  mov     rcx, [rcx+rbx*8]
0x18000e870  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x18000e876  inc     ebx
0x18000e878  cmp     ebx, cs:UmpoAdvancedSettingCount
0x18000e87e  jb      short loc_18000E865
0x18000e880  mov     r8, cs:UmpoAdvancedPowerSettingWnfSubscription; P
0x18000e887  xor     edx, edx; Flags
0x18000e889  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000e890  call    cs:__imp_RtlFreeHeap
0x18000e896  cmp     cs:byte_180024D68, 1
0x18000e89d  jz      short loc_18000E8A4
0x18000e89f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e8a4  lea     rbx, UmpoAdvancedSettingListLock
0x18000e8ab  mov     rcx, rbx; lpCriticalSection
0x18000e8ae  call    cs:__imp_EnterCriticalSection
0x18000e8b4  lea     rsi, UmpoAdvancedSettingList
0x18000e8bb  jmp     short loc_18000E8E8
0x18000e8bd  cmp     [rax+8], rsi
0x18000e8c1  jnz     short loc_18000E940
0x18000e8c3  mov     rcx, cs:qword_180024CA8
0x18000e8ca  cmp     [rcx], rsi
0x18000e8cd  jnz     short loc_18000E940
0x18000e8cf  mov     [rcx], rax
0x18000e8d2  mov     r8, rax; P
0x18000e8d5  mov     [rax+8], rcx
0x18000e8d9  xor     edx, edx; Flags
0x18000e8db  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x18000e8e2  call    cs:__imp_RtlFreeHeap
0x18000e8e8  mov     rax, cs:UmpoAdvancedSettingList
0x18000e8ef  cmp     rax, rsi
0x18000e8f2  jnz     short loc_18000E8BD
0x18000e8f4  cmp     cs:byte_180024D68, 1
0x18000e8fb  mov     cs:UmpoAdvancedSettingCount, 0
0x18000e905  mov     cs:UmpoIsPolicyManagerSupported, 0
0x18000e90c  jz      short loc_18000E913
0x18000e90e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000e913  mov     rcx, rbx; lpCriticalSection
0x18000e916  call    cs:__imp_LeaveCriticalSection
0x18000e91c  cmp     cs:byte_180024D68, 0
0x18000e923  jz      short loc_18000E935
0x18000e925  mov     rcx, rbx; lpCriticalSection
0x18000e928  call    cs:__imp_DeleteCriticalSection
0x18000e92e  mov     cs:byte_180024D68, 0
0x18000e935  mov     rbx, [rsp+28h+arg_0]
0x18000e93a  add     rsp, 20h
0x18000e93e  pop     rsi
0x18000e93f  retn
0x18000e940  mov     ecx, 3
0x18000e945  int     29h; Win8: RtlFailFast(ecx)
```
