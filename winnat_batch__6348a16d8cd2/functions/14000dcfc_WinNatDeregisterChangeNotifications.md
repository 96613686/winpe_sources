# WinNatDeregisterChangeNotifications

- ea: `0x14000dcfc`
- end: `0x14000dd8d`
- name: `WinNatDeregisterChangeNotifications`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000db20`

## callees

- `0x14000caa0`
- `0x14000dcfc`

## import_xrefs

- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd18`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd45`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd72`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd18`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd45`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd72`

## pseudocode

```c
void WinNatDeregisterChangeNotifications()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9

  if ( qword_140026AF0 && (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2, v3);
  if ( qword_140026B50 && (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v5, v4, v6, v7);
  if ( qword_140026B58 )
  {
    if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v9, v8, v10, v11);
  }
}

```

## disassembly

```asm
0x14000dcfc  sub     rsp, 28h
0x14000dd00  mov     r8, cs:qword_140026AF0
0x14000dd07  test    r8, r8
0x14000dd0a  jz      short loc_14000DD2D
0x14000dd0c  mov     edx, 0Ah
0x14000dd11  lea     rcx, NPI_MS_IPV4_MODULEID
0x14000dd18  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dd1f  nop     dword ptr [rax+rax+00h]
0x14000dd24  test    eax, eax
0x14000dd26  jns     short loc_14000DD2D
0x14000dd28  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dd2d  mov     r8, cs:qword_140026B50
0x14000dd34  test    r8, r8
0x14000dd37  jz      short loc_14000DD5A
0x14000dd39  mov     edx, 7
0x14000dd3e  lea     rcx, NPI_MS_IPV4_MODULEID
0x14000dd45  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dd4c  nop     dword ptr [rax+rax+00h]
0x14000dd51  test    eax, eax
0x14000dd53  jns     short loc_14000DD5A
0x14000dd55  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dd5a  mov     r8, cs:qword_140026B58
0x14000dd61  test    r8, r8
0x14000dd64  jz      short loc_14000DD87
0x14000dd66  mov     edx, 7
0x14000dd6b  lea     rcx, NPI_MS_IPV6_MODULEID
0x14000dd72  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dd79  nop     dword ptr [rax+rax+00h]
0x14000dd7e  test    eax, eax
0x14000dd80  jns     short loc_14000DD87
0x14000dd82  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dd87  add     rsp, 28h
0x14000dd8b  retn
```
