# UmpoInternalInitializeAdvancedPowerSettings

- ea: `0x180013414`
- end: `0x18001352c`
- name: `UmpoInternalInitializeAdvancedPowerSettings`
- size: `280`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a030`
- `0x180013540`

## callees

- `0x18000f3dc`
- `0x180013414`
- `0x18001459c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180013497`
- `ntdll!RtlAllocateHeap` at `0x180013497`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800134e1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x1800134e1`
- `policymanager!SettingsManagerStore_GetWnfsForSettingPath` at `0x180013461`
- `policymanager!SettingsManagerStore_GetWnfsForSettingPath` at `0x180013461`

## pseudocode

```c
__int64 UmpoInternalInitializeAdvancedPowerSettings()
{
  int WnfsForSettingPath; // eax
  __int64 i; // rbx
  char *Heap; // rdi
  unsigned int v4; // [rsp+50h] [rbp+8h] BYREF
  __int64 v5; // [rsp+58h] [rbp+10h] BYREF

  v4 = 0;
  v5 = 0;
  UmpoAdvancedPowerSettingWnfSubscription = 0;
  UmpoAdvancedSettingCount = 0;
  WnfsForSettingPath = SettingsManagerStore_GetWnfsForSettingPath(L"knobs", L"Power/Policy", &v5, &v4, 1);
  if ( WnfsForSettingPath )
  {
    LODWORD(i) = 0;
    Heap = 0;
    if ( WnfsForSettingPath != 2 )
LABEL_3:
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  else
  {
    Heap = (char *)RtlAllocateHeap(UmpoHeapHandle, 8u, 8LL * v4);
    for ( i = 0; (unsigned int)i < v4; i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)RtlSubscribeWnfStateChangeNotification(
                           &Heap[8 * i],
                           *(_QWORD *)(v5 + 8 * i),
                           0,
                           UmpoInternalAdvancedSettingCallback,
                           0,
                           0,
                           0,
                           0) )
        goto LABEL_3;
    }
    UmpoAdvancedPowerSettingWnfSubscription = Heap;
    Heap = 0;
    LODWORD(i) = 0;
    UmpoAdvancedSettingCount = v4;
  }
  UnsubscribeNotifications((unsigned int)i, Heap, v5, v4);
  return 0;
}

```

## disassembly

```asm
0x180013414  mov     rax, rsp
0x180013417  mov     [rax+18h], rbx
0x18001341b  push    rdi
0x18001341c  sub     rsp, 40h
0x180013420  lea     r9, [rax+8]
0x180013424  mov     dword ptr [rax+8], 0
0x18001342b  lea     r8, [rax+10h]
0x18001342f  mov     qword ptr [rax+10h], 0
0x180013437  lea     rdx, aPowerPolicy; "Power/Policy"
0x18001343e  mov     cs:UmpoAdvancedPowerSettingWnfSubscription, 0
0x180013449  lea     rcx, aKnobs; "knobs"
0x180013450  mov     cs:UmpoAdvancedSettingCount, 0
0x18001345a  mov     dword ptr [rax-28h], 1
0x180013461  call    cs:__imp_SettingsManagerStore_GetWnfsForSettingPath
0x180013467  test    eax, eax
0x180013469  jz      short loc_180013482
0x18001346b  xor     ebx, ebx
0x18001346d  xor     edi, edi
0x18001346f  cmp     eax, 2
0x180013472  jz      loc_18001350B
0x180013478  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001347d  jmp     loc_18001350B
0x180013482  mov     r8d, [rsp+48h+arg_0]
0x180013487  mov     edx, 8; Flags
0x18001348c  mov     rcx, cs:UmpoHeapHandle; HeapHandle
0x180013493  shl     r8, 3; Size
0x180013497  call    cs:__imp_RtlAllocateHeap
0x18001349d  mov     rdi, rax
0x1800134a0  xor     ebx, ebx
0x1800134a2  cmp     ebx, [rsp+48h+arg_0]
0x1800134a6  jnb     short loc_1800134F6
0x1800134a8  mov     rdx, [rsp+48h+arg_8]
0x1800134ad  lea     rcx, [rdi+rbx*8]
0x1800134b1  mov     [rsp+48h+var_10], 0
0x1800134b9  lea     r9, UmpoInternalAdvancedSettingCallback
0x1800134c0  mov     [rsp+48h+var_18], 0
0x1800134c8  xor     r8d, r8d
0x1800134cb  mov     [rsp+48h+var_20], 0
0x1800134d4  mov     rdx, [rdx+rbx*8]
0x1800134d8  mov     [rsp+48h+var_28], 0
0x1800134e1  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x1800134e7  test    eax, eax
0x1800134e9  jnz     short loc_1800134EF
0x1800134eb  inc     ebx
0x1800134ed  jmp     short loc_1800134A2
0x1800134ef  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800134f4  jmp     short loc_18001350B
0x1800134f6  mov     eax, [rsp+48h+arg_0]
0x1800134fa  mov     cs:UmpoAdvancedPowerSettingWnfSubscription, rdi
0x180013501  xor     edi, edi
0x180013503  xor     ebx, ebx
0x180013505  mov     cs:UmpoAdvancedSettingCount, eax
0x18001350b  mov     r9d, [rsp+48h+arg_0]
0x180013510  mov     rdx, rdi
0x180013513  mov     r8, [rsp+48h+arg_8]
0x180013518  mov     ecx, ebx
0x18001351a  call    UnsubscribeNotifications
0x18001351f  mov     rbx, [rsp+48h+arg_10]
0x180013524  xor     eax, eax
0x180013526  add     rsp, 40h
0x18001352a  pop     rdi
0x18001352b  retn
```
