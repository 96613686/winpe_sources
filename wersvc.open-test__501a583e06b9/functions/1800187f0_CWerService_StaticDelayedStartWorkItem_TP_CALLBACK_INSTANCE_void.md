# CWerService::StaticDelayedStartWorkItem(_TP_CALLBACK_INSTANCE *,void *)

- ea: `0x1800187f0`
- end: `0x180018871`
- name: `?StaticDelayedStartWorkItem@CWerService@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAX@Z`
- size: `129`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180006a80`
- `0x180013d38`
- `0x1800187f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018865`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180018865`
- `ntdll!NtSetSystemInformation` at `0x18001880a`
- `ntdll!NtSetSystemInformation` at `0x18001880a`

## string_xrefs

- `0x1800187ff`: `\WindowsErrorReportingServicePort`

## pseudocode

```c
void __fastcall CWerService::StaticDelayedStartWorkItem(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context)
{
  NTSTATUS v3; // eax
  __int64 v4; // rcx

  v3 = NtSetSystemInformation(SystemErrorPortInformation, (PVOID)L"\\WindowsErrorReportingServicePort", 0x42u);
  if ( v3 >= 0 )
  {
    if ( Context[43] != (HANDLE)-1LL && (char *)Context[43] + 1 != HANDLE_FLAG_INHERIT )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 145, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids);
      SetEvent(Context[43]);
    }
  }
  else
  {
    MicrosoftTelemetryAssertTriggeredArgs(v4, v3);
  }
}

```

## disassembly

```asm
0x1800187f0  push    rbx
0x1800187f2  sub     rsp, 20h
0x1800187f6  mov     r8d, 42h ; 'B'; SystemInformationLength
0x1800187fc  mov     rbx, rdx
0x1800187ff  lea     rdx, aWindowserrorre; "\\WindowsErrorReportingServicePort"
0x180018806  lea     ecx, [r8+17h]; SystemInformationClass
0x18001880a  call    cs:__imp_NtSetSystemInformation
0x180018810  test    eax, eax
0x180018812  jns     short loc_180018820
0x180018814  mov     edx, eax
0x180018816  add     rsp, 20h
0x18001881a  pop     rbx
0x18001881b  jmp     MicrosoftTelemetryAssertTriggeredArgs
0x180018820  mov     rax, [rbx+158h]
0x180018827  inc     rax
0x18001882a  cmp     rax, 1
0x18001882e  jbe     short loc_18001886B
0x180018830  mov     rcx, cs:WPP_GLOBAL_Control
0x180018837  lea     rax, WPP_GLOBAL_Control
0x18001883e  cmp     rcx, rax
0x180018841  jz      short loc_18001885E
0x180018843  test    byte ptr [rcx+1Ch], 8
0x180018847  jz      short loc_18001885E
0x180018849  mov     rcx, [rcx+10h]
0x18001884d  lea     r8, WPP_fd0c3993e8f0396a73a01b4739c75d44_Traceguids
0x180018854  mov     edx, 91h
0x180018859  call    WPP_SF_
0x18001885e  mov     rcx, [rbx+158h]; hEvent
0x180018865  call    cs:__imp_SetEvent
0x18001886b  add     rsp, 20h
0x18001886f  pop     rbx
0x180018870  retn
```
