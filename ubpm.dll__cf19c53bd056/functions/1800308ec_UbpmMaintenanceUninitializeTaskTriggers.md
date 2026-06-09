# UbpmMaintenanceUninitializeTaskTriggers

- ea: `0x1800308ec`
- end: `0x180030996`
- name: `UbpmMaintenanceUninitializeTaskTriggers`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800307f0`

## callees

- `0x1800308ec`
- `0x180032e38`
- `0x18003488c`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180030939`
- `ntdll!NtDeleteWnfStateName` at `0x180030939`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180030921`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180030921`

## pseudocode

```c
__int64 UbpmMaintenanceUninitializeTaskTriggers()
{
  unsigned int i; // edi
  struct _MAINTENANCE_TRIGGER near **v1; // rbx
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx

  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
      return 0;
    v1 = &g_MaintenanceTriggers + 2 * i;
    if ( *((_DWORD *)v1 + 2) || *((_DWORD *)v1 + 3) )
    {
      v2 = CSebDeleteEvent(v1[1]);
      if ( v2 < 0 )
        break;
    }
    if ( *(_DWORD *)v1 || *((_DWORD *)v1 + 1) )
    {
      if ( (int)NtDeleteWnfStateName(&g_MaintenanceTriggers + 2 * i) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v3);
      *v1 = 0;
    }
  }
  v4 = (unsigned __int16)v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_78bab00beccc37ee093aed9e3146db9a_Traceguids,
      (unsigned __int16)v2);
  return v4;
}

```

## disassembly

```asm
0x1800308ec  mov     [rsp+arg_0], rbx
0x1800308f1  push    rdi
0x1800308f2  sub     rsp, 20h
0x1800308f6  xor     edi, edi
0x1800308f8  cmp     edi, 5
0x1800308fb  jnb     loc_180030987
0x180030901  mov     ebx, edi
0x180030903  lea     rcx, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x18003090a  shl     rbx, 4
0x18003090e  add     rbx, rcx
0x180030911  cmp     dword ptr [rbx+8], 0
0x180030915  jnz     short loc_18003091D
0x180030917  cmp     dword ptr [rbx+0Ch], 0
0x18003091b  jz      short loc_18003092B
0x18003091d  mov     rcx, [rbx+8]
0x180030921  call    cs:__imp_CSebDeleteEvent
0x180030927  test    eax, eax
0x180030929  js      short loc_180030951
0x18003092b  cmp     dword ptr [rbx], 0
0x18003092e  jnz     short loc_180030936
0x180030930  cmp     dword ptr [rbx+4], 0
0x180030934  jz      short loc_18003094D
0x180030936  mov     rcx, rbx
0x180030939  call    cs:__imp_NtDeleteWnfStateName
0x18003093f  test    eax, eax
0x180030941  jns     short loc_180030948
0x180030943  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030948  xor     eax, eax
0x18003094a  mov     [rbx], rax
0x18003094d  inc     edi
0x18003094f  jmp     short loc_1800308F8
0x180030951  movzx   ebx, ax
0x180030954  mov     rcx, cs:WPP_GLOBAL_Control
0x18003095b  lea     rax, WPP_GLOBAL_Control
0x180030962  cmp     rcx, rax
0x180030965  jz      short loc_180030989
0x180030967  test    byte ptr [rcx+1Ch], 1
0x18003096b  jz      short loc_180030989
0x18003096d  mov     rcx, [rcx+10h]
0x180030971  lea     r8, WPP_78bab00beccc37ee093aed9e3146db9a_Traceguids
0x180030978  mov     edx, 0Ah
0x18003097d  mov     r9d, ebx
0x180030980  call    WPP_SF_d
0x180030985  jmp     short loc_180030989
0x180030987  xor     ebx, ebx
0x180030989  mov     eax, ebx
0x18003098b  mov     rbx, [rsp+28h+arg_0]
0x180030990  add     rsp, 20h
0x180030994  pop     rdi
0x180030995  retn
```
