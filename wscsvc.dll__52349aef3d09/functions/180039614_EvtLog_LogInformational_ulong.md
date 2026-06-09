# EvtLog_LogInformational(ulong)

- ea: `0x180039614`
- end: `0x180039677`
- name: `?EvtLog_LogInformational@@YAXK@Z`
- size: `99`
- prototype: `void __fastcall(DWORD dwEventID)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008e88`
- `0x18001d9e0`
- `0x180036adc`

## callees

- `0x180039614`

## import_xrefs

- `ADVAPI32!RegisterEventSourceW` at `0x180039629`
- `ADVAPI32!RegisterEventSourceW` at `0x180039629`
- `ADVAPI32!DeregisterEventSource` at `0x180039666`
- `ADVAPI32!DeregisterEventSource` at `0x180039666`
- `ADVAPI32!ReportEventW` at `0x18003965d`
- `ADVAPI32!ReportEventW` at `0x18003965d`

## string_xrefs

- `0x180039620`: `SecurityCenter`

## pseudocode

```c
void __fastcall EvtLog_LogInformational(DWORD dwEventID)
{
  HANDLE v2; // rbx

  v2 = RegisterEventSourceW(0, L"SecurityCenter");
  if ( v2 )
  {
    ReportEventW(v2, 4u, 0, dwEventID, 0, 0, 0, 0, 0);
    DeregisterEventSource(v2);
  }
}

```

## disassembly

```asm
0x180039614  mov     [rsp+arg_0], rbx
0x180039619  push    rdi
0x18003961a  sub     rsp, 50h
0x18003961e  mov     edi, ecx
0x180039620  lea     rdx, SourceName; "SecurityCenter"
0x180039627  xor     ecx, ecx; lpUNCServerName
0x180039629  call    cs:__imp_RegisterEventSourceW
0x18003962f  mov     rbx, rax
0x180039632  xor     eax, eax
0x180039634  test    rbx, rbx
0x180039637  jz      short loc_18003966C
0x180039639  mov     [rsp+58h+lpRawData], rax; lpRawData
0x18003963e  lea     edx, [rax+4]; wType
0x180039641  mov     [rsp+58h+lpStrings], rax; lpStrings
0x180039646  xor     r8d, r8d; wCategory
0x180039649  mov     [rsp+58h+dwDataSize], eax; dwDataSize
0x18003964d  mov     r9d, edi; dwEventID
0x180039650  mov     [rsp+58h+wNumStrings], ax; wNumStrings
0x180039655  mov     rcx, rbx; hEventLog
0x180039658  mov     [rsp+58h+lpUserSid], rax; lpUserSid
0x18003965d  call    cs:__imp_ReportEventW
0x180039663  mov     rcx, rbx; hEventLog
0x180039666  call    cs:__imp_DeregisterEventSource
0x18003966c  mov     rbx, [rsp+58h+arg_0]
0x180039671  add     rsp, 50h
0x180039675  pop     rdi
0x180039676  retn
```
