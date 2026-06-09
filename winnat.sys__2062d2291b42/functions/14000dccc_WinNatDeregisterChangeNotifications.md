# WinNatDeregisterChangeNotifications

- ea: `0x14000dccc`
- end: `0x14000dd5d`
- name: `WinNatDeregisterChangeNotifications`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000daf0`

## callees

- `0x14000caa0`
- `0x14000dccc`

## import_xrefs

- `NETIO!NsiDeregisterChangeNotification` at `0x14000dce8`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd15`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd42`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dce8`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd15`
- `NETIO!NsiDeregisterChangeNotification` at `0x14000dd42`

## pseudocode

```c
void WinNatDeregisterChangeNotifications()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8

  if ( qword_140027AF0 && (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 10) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v1, v0, v2);
  if ( qword_140027B50 && (int)NsiDeregisterChangeNotification(&NPI_MS_IPV4_MODULEID, 7) < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v4, v3, v5);
  if ( qword_140027B58 )
  {
    if ( (int)NsiDeregisterChangeNotification(&NPI_MS_IPV6_MODULEID, 7) < 0 )
      MicrosoftTelemetryAssertTriggeredNoArgsKM(v7, v6, v8);
  }
}

```

## disassembly

```asm
0x14000dccc  sub     rsp, 28h
0x14000dcd0  mov     r8, cs:qword_140027AF0
0x14000dcd7  test    r8, r8
0x14000dcda  jz      short loc_14000DCFD
0x14000dcdc  mov     edx, 0Ah
0x14000dce1  lea     rcx, NPI_MS_IPV4_MODULEID
0x14000dce8  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dcef  nop     dword ptr [rax+rax+00h]
0x14000dcf4  test    eax, eax
0x14000dcf6  jns     short loc_14000DCFD
0x14000dcf8  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dcfd  mov     r8, cs:qword_140027B50
0x14000dd04  test    r8, r8
0x14000dd07  jz      short loc_14000DD2A
0x14000dd09  mov     edx, 7
0x14000dd0e  lea     rcx, NPI_MS_IPV4_MODULEID
0x14000dd15  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dd1c  nop     dword ptr [rax+rax+00h]
0x14000dd21  test    eax, eax
0x14000dd23  jns     short loc_14000DD2A
0x14000dd25  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dd2a  mov     r8, cs:qword_140027B58
0x14000dd31  test    r8, r8
0x14000dd34  jz      short loc_14000DD57
0x14000dd36  mov     edx, 7
0x14000dd3b  lea     rcx, NPI_MS_IPV6_MODULEID
0x14000dd42  call    cs:__imp_NsiDeregisterChangeNotification
0x14000dd49  nop     dword ptr [rax+rax+00h]
0x14000dd4e  test    eax, eax
0x14000dd50  jns     short loc_14000DD57
0x14000dd52  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14000dd57  add     rsp, 28h
0x14000dd5b  retn
```
