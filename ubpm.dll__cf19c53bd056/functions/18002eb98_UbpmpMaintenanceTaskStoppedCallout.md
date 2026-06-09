# UbpmpMaintenanceTaskStoppedCallout

- ea: `0x18002eb98`
- end: `0x18002ecd0`
- name: `UbpmpMaintenanceTaskStoppedCallout`
- size: `312`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003050`
- `0x180007480`
- `0x180007990`
- `0x180008f30`

## callees

- `0x18001f16c`
- `0x1800270c8`
- `0x18002978c`
- `0x18002cd60`
- `0x18002d46c`
- `0x18002db10`
- `0x18002e964`
- `0x18002eb98`
- `0x18002eeec`
- `0x18003488c`
- `0x18003d810`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002ec34`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18002ec34`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStop` at `0x18002ebf8`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStop` at `0x18002ebf8`

## pseudocode

```c
ULONG __fastcall UbpmpMaintenanceTaskStoppedCallout(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v3; // al
  char v4; // bp
  unsigned __int64 v5; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  ULONG result; // eax
  int v17; // [rsp+30h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-40h] BYREF

  v3 = *(_BYTE *)(a1 + 40);
  v4 = a3;
  v5 = (unsigned __int64)v3 << 6;
  SystemTime = 0;
  if ( v3 >= 5u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LOBYTE(a3) = v4;
  UbpmTelemMaintenanceTaskStopped(a1, *(_QWORD *)(a2 + 112), a3);
  if ( *(_QWORD *)((char *)&g_MaintenancePilot + v5 + 104) )
    CrmActivityStop();
  UbpmTelemMaintenanceTaskRundown(1u, a1, *(_BYTE *)(a1 + 40));
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) + 28LL) )
    byte_18004CB31 = 0;
  --*(_DWORD *)((char *)&g_MaintenancePilot + v5 + 124);
  if ( UbpmpMaintenanceTotalTasksRunning()
    || (GetLocalTime(&SystemTime),
        UbpmpReportMaintenanceState(&SystemTime, (const unsigned __int16 *)1, v10, v11),
        UbpmTakeMaintenancePdcReference(0, v12, v13),
        !(unsigned int)UbpmpCheckQueueMaintenanceLauncher()) )
  {
    if ( qword_18004CB48 )
    {
      v15 = *(_QWORD *)(a2 + 16);
      if ( v15 )
      {
        UbpmpSleepStudyStopReportingBlocker(v15, *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
        v14 = 0;
        *(_QWORD *)(a2 + 16) = 0;
      }
      else
      {
        v14 = 30;
      }
    }
    else
    {
      v14 = 20;
    }
  }
  else
  {
    v14 = 10;
  }
  result = dword_18004C0F0;
  if ( (unsigned int)dword_18004C0F0 > 4 )
  {
    v17 = v14;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
             v14,
             (unsigned __int8 *)&word_180044096,
             v8,
             v9,
             (__int64)&v17);
  }
  return result;
}

```

## disassembly

```asm
0x18002eb98  push    rbx
0x18002eb9a  push    rbp
0x18002eb9b  push    rsi
0x18002eb9c  push    rdi
0x18002eb9d  push    r14
0x18002eb9f  sub     rsp, 50h
0x18002eba3  mov     rax, cs:__security_cookie
0x18002ebaa  xor     rax, rsp
0x18002ebad  mov     [rsp+78h+var_30], rax
0x18002ebb2  movzx   eax, byte ptr [rcx+28h]
0x18002ebb6  xorps   xmm0, xmm0
0x18002ebb9  mov     edi, eax
0x18002ebbb  mov     bpl, r8b
0x18002ebbe  shl     rdi, 6
0x18002ebc2  mov     rsi, rdx
0x18002ebc5  mov     rbx, rcx
0x18002ebc8  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x18002ebcd  cmp     al, 5
0x18002ebcf  jb      short loc_18002EBD6
0x18002ebd1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18002ebd6  mov     rdx, [rsi+70h]
0x18002ebda  mov     r8b, bpl
0x18002ebdd  mov     rcx, rbx
0x18002ebe0  call    UbpmTelemMaintenanceTaskStopped
0x18002ebe5  lea     r14, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002ebec  xor     ebp, ebp
0x18002ebee  mov     rcx, [rdi+r14+68h]
0x18002ebf3  test    rcx, rcx
0x18002ebf6  jz      short loc_18002EBFE
0x18002ebf8  call    cs:__imp_CrmActivityStop
0x18002ebfe  mov     r8b, [rbx+28h]
0x18002ec02  mov     rdx, rbx
0x18002ec05  mov     cl, 1
0x18002ec07  call    UbpmTelemMaintenanceTaskRundown
0x18002ec0c  mov     rax, [rbx+18h]
0x18002ec10  mov     rcx, [rax+30h]
0x18002ec14  cmp     [rcx+1Ch], bpl
0x18002ec18  jz      short loc_18002EC21
0x18002ec1a  mov     cs:byte_18004CB31, bpl
0x18002ec21  dec     dword ptr [rdi+r14+7Ch]
0x18002ec26  call    ?UbpmpMaintenanceTotalTasksRunning@@YAKXZ; UbpmpMaintenanceTotalTasksRunning(void)
0x18002ec2b  test    eax, eax
0x18002ec2d  jnz     short loc_18002EC60
0x18002ec2f  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x18002ec34  call    cs:__imp_GetLocalTime
0x18002ec3a  mov     edx, 1; unsigned int
0x18002ec3f  lea     rcx, [rsp+78h+SystemTime]; lpTime
0x18002ec44  call    ?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z; UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)
0x18002ec49  xor     ecx, ecx; unsigned __int8
0x18002ec4b  call    ?UbpmTakeMaintenancePdcReference@@YAXE@Z; UbpmTakeMaintenancePdcReference(uchar)
0x18002ec50  call    UbpmpCheckQueueMaintenanceLauncher
0x18002ec55  test    eax, eax
0x18002ec57  jz      short loc_18002EC60
0x18002ec59  mov     ecx, 0Ah
0x18002ec5e  jmp     short loc_18002EC93
0x18002ec60  cmp     cs:qword_18004CB48, rbp
0x18002ec67  jnz     short loc_18002EC70
0x18002ec69  mov     ecx, 14h
0x18002ec6e  jmp     short loc_18002EC93
0x18002ec70  mov     rcx, [rsi+10h]
0x18002ec74  test    rcx, rcx
0x18002ec77  jnz     short loc_18002EC80
0x18002ec79  mov     ecx, 1Eh
0x18002ec7e  jmp     short loc_18002EC93
0x18002ec80  mov     rdx, [rbx+18h]
0x18002ec84  mov     rdx, [rdx+8]
0x18002ec88  call    UbpmpSleepStudyStopReportingBlocker
0x18002ec8d  mov     ecx, ebp
0x18002ec8f  mov     [rsi+10h], rbp
0x18002ec93  mov     eax, cs:dword_18004C0F0
0x18002ec99  cmp     eax, 4
0x18002ec9c  jbe     short loc_18002ECB8
0x18002ec9e  lea     rax, [rsp+78h+var_48]
0x18002eca3  mov     [rsp+78h+var_48], ecx
0x18002eca7  lea     rdx, word_180044096
0x18002ecae  mov     [rsp+78h+var_58], rax
0x18002ecb3  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002ecb8  mov     rcx, [rsp+78h+var_30]
0x18002ecbd  xor     rcx, rsp; StackCookie
0x18002ecc0  call    __security_check_cookie
0x18002ecc5  add     rsp, 50h
0x18002ecc9  pop     r14
0x18002eccb  pop     rdi
0x18002eccc  pop     rsi
0x18002eccd  pop     rbp
0x18002ecce  pop     rbx
0x18002eccf  retn
```
