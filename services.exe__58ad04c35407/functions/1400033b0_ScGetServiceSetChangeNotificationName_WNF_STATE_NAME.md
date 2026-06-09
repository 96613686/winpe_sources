# ScGetServiceSetChangeNotificationName(_WNF_STATE_NAME *)

- ea: `0x1400033b0`
- end: `0x140003497`
- name: `?ScGetServiceSetChangeNotificationName@@YAKPEAU_WNF_STATE_NAME@@@Z`
- size: `231`
- prototype: `unsigned int __fastcall(struct _WNF_STATE_NAME *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000538c`

## callees

- `0x1400033b0`
- `0x140004190`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1400033cf`
- `ntdll!RtlAcquireResourceExclusive` at `0x1400033cf`
- `ntdll!NtCreateWnfStateName` at `0x140003430`
- `ntdll!NtCreateWnfStateName` at `0x140003430`
- `ntdll!RtlReleaseResource` at `0x140003484`
- `ntdll!RtlReleaseResource` at `0x140003484`
- `ntdll!RtlNtStatusToDosError` at `0x140003449`
- `ntdll!RtlNtStatusToDosError` at `0x140003449`
- `ntdll!RtlDeleteSecurityObject` at `0x14000343d`
- `ntdll!RtlDeleteSecurityObject` at `0x14000343d`
- `ntdll!RtlPublishWnfStateData` at `0x14000346b`
- `ntdll!RtlPublishWnfStateData` at `0x14000346b`

## pseudocode

```c
__int64 __fastcall ScGetServiceSetChangeNotificationName(struct _WNF_STATE_NAME *a1)
{
  struct _WNF_STATE_NAME v2; // rax
  unsigned int v3; // ebx
  NTSTATUS WnfStateName; // ebx
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+58h] [rbp+10h] BYREF

  ObjectDescriptor = 0;
  RtlAcquireResourceExclusive(&ScServiceRecordLock, 1u);
  v2 = g_ServiceDatabaseChangeStateName;
  if ( g_ServiceDatabaseChangeStateName != __PAIR64__(g_ServiceDatabaseChangeStateName.Data[0], 0) )
    goto LABEL_6;
  v3 = ScCreateNotificationSecurityDescriptor(0, 4, &ObjectDescriptor);
  if ( !v3 )
  {
    WnfStateName = NtCreateWnfStateName(&g_ServiceDatabaseChangeStateName, 3, 0);
    RtlDeleteSecurityObject(&ObjectDescriptor);
    if ( WnfStateName < 0 )
    {
      v3 = RtlNtStatusToDosError(WnfStateName);
      goto LABEL_7;
    }
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))RtlPublishWnfStateData)(
      g_ServiceDatabaseChangeStateName,
      0,
      0,
      0,
      0);
    v2 = g_ServiceDatabaseChangeStateName;
LABEL_6:
    *a1 = v2;
    v3 = 0;
  }
LABEL_7:
  RtlReleaseResource(&ScServiceRecordLock);
  return v3;
}

```

## disassembly

```asm
0x1400033b0  mov     [rsp+arg_0], rbx
0x1400033b5  push    rdi
0x1400033b6  sub     rsp, 40h
0x1400033ba  mov     rdi, rcx
0x1400033bd  mov     [rsp+48h+ObjectDescriptor], 0
0x1400033c6  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x1400033cd  mov     dl, 1; Wait
0x1400033cf  call    cs:__imp_RtlAcquireResourceExclusive
0x1400033d5  mov     rax, cs:?g_ServiceDatabaseChangeStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_ServiceDatabaseChangeStateName
0x1400033dc  test    eax, eax
0x1400033de  jnz     loc_140003478
0x1400033e4  cmp     dword ptr cs:?g_ServiceDatabaseChangeStateName@@3U_WNF_STATE_NAME@@A+4, eax; _WNF_STATE_NAME g_ServiceDatabaseChangeStateName
0x1400033ea  jnz     loc_140003478
0x1400033f0  lea     r8, [rsp+48h+ObjectDescriptor]; void **
0x1400033f5  xor     ecx, ecx; SecurityDescriptor
0x1400033f7  lea     edx, [rax+4]; unsigned int
0x1400033fa  call    ?ScCreateNotificationSecurityDescriptor@@YAKPEAXKPEAPEAX@Z; ScCreateNotificationSecurityDescriptor(void *,ulong,void * *)
0x1400033ff  mov     ebx, eax
0x140003401  test    eax, eax
0x140003403  jnz     short loc_14000347D
0x140003405  mov     rax, [rsp+48h+ObjectDescriptor]
0x14000340a  lea     edx, [rbx+3]
0x14000340d  mov     [rsp+48h+var_18], rax
0x140003412  lea     rcx, ?g_ServiceDatabaseChangeStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_ServiceDatabaseChangeStateName
0x140003419  mov     [rsp+48h+var_20], 4
0x140003421  xor     r9d, r9d
0x140003424  xor     r8d, r8d
0x140003427  mov     [rsp+48h+var_28], 0
0x140003430  call    cs:__imp_NtCreateWnfStateName
0x140003436  lea     rcx, [rsp+48h+ObjectDescriptor]; ObjectDescriptor
0x14000343b  mov     ebx, eax
0x14000343d  call    cs:__imp_RtlDeleteSecurityObject
0x140003443  test    ebx, ebx
0x140003445  jns     short loc_140003453
0x140003447  mov     ecx, ebx; Status
0x140003449  call    cs:__imp_RtlNtStatusToDosError
0x14000344f  mov     ebx, eax
0x140003451  jmp     short loc_14000347D
0x140003453  mov     rcx, cs:?g_ServiceDatabaseChangeStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_ServiceDatabaseChangeStateName
0x14000345a  xor     r9d, r9d
0x14000345d  xor     r8d, r8d
0x140003460  mov     [rsp+48h+var_28], 0
0x140003469  xor     edx, edx
0x14000346b  call    cs:__imp_RtlPublishWnfStateData
0x140003471  mov     rax, cs:?g_ServiceDatabaseChangeStateName@@3U_WNF_STATE_NAME@@A; _WNF_STATE_NAME g_ServiceDatabaseChangeStateName
0x140003478  mov     [rdi], rax
0x14000347b  xor     ebx, ebx
0x14000347d  lea     rcx, ?ScServiceRecordLock@@3VCServiceRecordLock@@A; Resource
0x140003484  call    cs:__imp_RtlReleaseResource
0x14000348a  mov     eax, ebx
0x14000348c  mov     rbx, [rsp+48h+arg_0]
0x140003491  add     rsp, 40h
0x140003495  pop     rdi
0x140003496  retn
```
