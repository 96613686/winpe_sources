# UbpmMaintenanceInitializeTaskTriggers

- ea: `0x18002f544`
- end: `0x18002f6e1`
- name: `UbpmMaintenanceInitializeTaskTriggers`
- size: `413`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002e220`

## callees

- `0x1800295cc`
- `0x18002f544`
- `0x18003d7de`

## import_xrefs

- `ntdll!NtCreateWnfStateName` at `0x18002f622`
- `ntdll!NtCreateWnfStateName` at `0x18002f622`
- `ntdll!RtlNtStatusToDosError` at `0x18002f679`
- `ntdll!RtlNtStatusToDosError` at `0x18002f679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f5a9`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002f59c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002f59c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f68a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002f68a`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x18002f651`
- `CSystemEventsBrokerClient!CSebCreatePrivateEvent` at `0x18002f651`

## pseudocode

```c
__int64 UbpmMaintenanceInitializeTaskTriggers()
{
  int v0; // edi
  ULONG LastError; // eax
  int v2; // r8d
  int v3; // r9d
  unsigned int v4; // ebx
  struct _MAINTENANCE_TRIGGER near **v5; // rdi
  NTSTATUS WnfStateName; // eax
  int v7; // eax
  ULONG v8; // ebx
  int v9; // ecx
  __int128 v11; // [rsp+48h] [rbp-79h]
  __m256i v12; // [rsp+58h] [rbp-69h] BYREF
  __int128 v13; // [rsp+88h] [rbp-39h] BYREF
  __m256i v14; // [rsp+98h] [rbp-29h]
  __int64 v15; // [rsp+B8h] [rbp-9h]
  ULONG SecurityDescriptorSize; // [rsp+128h] [rbp+67h] BYREF
  int v17; // [rsp+130h] [rbp+6Fh] BYREF
  ULONG v18; // [rsp+138h] [rbp+77h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+140h] [rbp+7Fh] BYREF

  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  memset_0(&g_MaintenanceTriggers, 0, 0x50u);
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"D:(A;;GA;;;SY)",
         1u,
         &SecurityDescriptor,
         &SecurityDescriptorSize) )
  {
    v4 = 0;
    v12.m256i_i64[0] = 1;
    memset(&v12.m256i_u64[1], 0, 24);
    *((_QWORD *)&v11 + 1) = 4124;
    while ( 1 )
    {
      v5 = &g_MaintenanceTriggers + 2 * v4;
      WnfStateName = NtCreateWnfStateName(v5, 3, 0, 0, 0, 4096, SecurityDescriptor);
      if ( WnfStateName < 0 )
        break;
      *(_QWORD *)&v11 = *v5;
      v14 = v12;
      v13 = v11;
      v15 = 0;
      v7 = CSebCreatePrivateEvent(&v13, v5 + 1);
      if ( v7 < 0 )
      {
        v0 = 30;
        v8 = (unsigned __int16)v7;
        goto LABEL_11;
      }
      if ( ++v4 >= 5 )
      {
        v0 = 0;
        v8 = 0;
        goto LABEL_11;
      }
    }
    v0 = 20;
    LastError = RtlNtStatusToDosError(WnfStateName);
  }
  else
  {
    v0 = 10;
    LastError = GetLastError();
  }
  v8 = LastError;
LABEL_11:
  v9 = (int)SecurityDescriptor;
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v17 = v0;
    v18 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v9,
      (unsigned int)byte_1800443B9,
      v2,
      v3,
      (__int64)&v18,
      (__int64)&v17);
  }
  return v8;
}

```

## disassembly

```asm
0x18002f544  mov     rax, rsp
0x18002f547  push    rbp
0x18002f548  push    rbx
0x18002f549  push    rdi
0x18002f54a  push    r15
0x18002f54c  lea     rbp, [rax-5Fh]
0x18002f550  sub     rsp, 0F8h
0x18002f557  movaps  xmmword ptr [rax-38h], xmm6
0x18002f55b  lea     r15, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x18002f562  xor     edx, edx; Val
0x18002f564  movaps  xmmword ptr [rax-48h], xmm7
0x18002f568  mov     rcx, r15; void *
0x18002f56b  movaps  xmmword ptr [rax-58h], xmm8
0x18002f570  mov     [rbp+57h+SecurityDescriptor], 0
0x18002f578  mov     [rbp+57h+SecurityDescriptorSize], 0
0x18002f57f  lea     r8d, [rdx+50h]; Size
0x18002f583  call    memset_0
0x18002f588  lea     r9, [rbp+57h+SecurityDescriptorSize]; SecurityDescriptorSize
0x18002f58c  mov     edx, 1; StringSDRevision
0x18002f591  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18002f595  lea     rcx, StringSecurityDescriptor; "D:(A;;GA;;;SY)"
0x18002f59c  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002f5a2  test    eax, eax
0x18002f5a4  jnz     short loc_18002F5B4
0x18002f5a6  lea     edi, [rax+0Ah]
0x18002f5a9  call    cs:__imp_GetLastError
0x18002f5af  jmp     loc_18002F67F
0x18002f5b4  mov     [rbp+57h+var_A4], 0
0x18002f5bc  xorps   xmm0, xmm0
0x18002f5bf  movdqu  [rbp+57h+var_C0+0Ch], xmm0
0x18002f5c4  mov     [rbp+57h+var_9C], 0
0x18002f5cb  xor     ebx, ebx
0x18002f5cd  movups  xmm7, xmmword ptr [rbp-59h]
0x18002f5d1  mov     qword ptr [rbp+57h+var_C0], 1
0x18002f5d9  movsd   xmm6, [rbp+57h+var_A4+4]
0x18002f5de  mov     dword ptr [rbp+57h+var_C0+8], 0
0x18002f5e5  movups  xmm8, [rbp+57h+var_C0]
0x18002f5ea  mov     qword ptr [rbp+57h+var_D0+8], 101Ch
0x18002f5f2  mov     rax, [rbp+57h+SecurityDescriptor]
0x18002f5f6  xor     r9d, r9d
0x18002f5f9  mov     [rsp+110h+var_E0], rax
0x18002f5fe  xor     r8d, r8d
0x18002f601  mov     edi, ebx
0x18002f603  shl     rdi, 4
0x18002f607  add     rdi, r15
0x18002f60a  mov     dword ptr [rsp+110h+var_E8], 1000h
0x18002f612  mov     rcx, rdi
0x18002f615  mov     [rsp+110h+var_F0], 0
0x18002f61e  lea     edx, [r9+3]
0x18002f622  call    cs:__imp_NtCreateWnfStateName
0x18002f628  test    eax, eax
0x18002f62a  js      short loc_18002F672
0x18002f62c  mov     rax, [rdi]
0x18002f62f  lea     rdx, [rdi+8]
0x18002f633  mov     qword ptr [rbp+57h+var_D0], rax
0x18002f637  lea     rcx, [rbp+57h+var_90]
0x18002f63b  movups  xmm0, [rbp+57h+var_D0]
0x18002f63f  movaps  [rbp+57h+var_80], xmm8
0x18002f644  movaps  [rbp+57h+var_90], xmm0
0x18002f648  movaps  [rbp+57h+var_70], xmm7
0x18002f64c  movsd   [rbp+57h+var_60], xmm6
0x18002f651  call    cs:__imp_CSebCreatePrivateEvent
0x18002f657  test    eax, eax
0x18002f659  js      short loc_18002F668
0x18002f65b  inc     ebx
0x18002f65d  cmp     ebx, 5
0x18002f660  jb      short loc_18002F5F2
0x18002f662  xor     edi, edi
0x18002f664  xor     ebx, ebx
0x18002f666  jmp     short loc_18002F681
0x18002f668  mov     edi, 1Eh
0x18002f66d  movzx   ebx, ax
0x18002f670  jmp     short loc_18002F681
0x18002f672  mov     ecx, eax; Status
0x18002f674  mov     edi, 14h
0x18002f679  call    cs:__imp_RtlNtStatusToDosError
0x18002f67f  mov     ebx, eax
0x18002f681  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18002f685  test    rcx, rcx
0x18002f688  jz      short loc_18002F690
0x18002f68a  call    cs:__imp_LocalFree
0x18002f690  mov     eax, cs:dword_18004C0F0
0x18002f696  cmp     eax, 4
0x18002f699  jbe     short loc_18002F6BF
0x18002f69b  lea     rax, [rbp+57h+arg_8]
0x18002f69f  mov     [rbp+57h+arg_8], edi
0x18002f6a2  mov     [rsp+110h+var_E8], rax
0x18002f6a7  lea     rdx, byte_1800443B9
0x18002f6ae  lea     rax, [rbp+57h+arg_10]
0x18002f6b2  mov     [rbp+57h+arg_10], ebx
0x18002f6b5  mov     [rsp+110h+var_F0], rax
0x18002f6ba  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002f6bf  lea     r11, [rsp+110h+var_18]
0x18002f6c7  mov     eax, ebx
0x18002f6c9  movaps  xmm6, xmmword ptr [r11-18h]
0x18002f6ce  movaps  xmm7, xmmword ptr [r11-28h]
0x18002f6d3  movaps  xmm8, xmmword ptr [r11-38h]
0x18002f6d8  mov     rsp, r11
0x18002f6db  pop     r15
0x18002f6dd  pop     rdi
0x18002f6de  pop     rbx
0x18002f6df  pop     rbp
0x18002f6e0  retn
```
