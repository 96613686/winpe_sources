# ShutdownService(ulong,uchar)

- ea: `0x180002884`
- end: `0x1800029e2`
- name: `?ShutdownService@@YAXKE@Z`
- size: `350`
- prototype: `void __fastcall(unsigned int, unsigned __int8)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001aa0`
- `0x180002810`

## callees

- `0x18000212c`
- `0x180002884`
- `0x1800029e8`
- `0x180038dec`
- `0x180038f08`
- `0x18003b7b0`
- `0x18003b7d8`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800029a4`
- `ntdll!RtlLeaveCriticalSection` at `0x1800029cc`
- `ntdll!RtlLeaveCriticalSection` at `0x1800029cc`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800028e2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800028ff`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800028e2`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800028ff`
- `ntdll!RtlEnterCriticalSection` at `0x1800028a2`
- `ntdll!RtlEnterCriticalSection` at `0x1800028a2`

## pseudocode

```c
void __fastcall ShutdownService(__int64 a1, char a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax

  if ( a2 )
    RtlEnterCriticalSection(&CriticalSection);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_78b059fac4093813b2646cef9913e025_Traceguids);
  if ( qword_18005F8C8 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    qword_18005F8C8 = 0;
  }
  if ( qword_18005F8B8 )
  {
    RtlUnsubscribeWnfNotificationWaitForCompletion();
    qword_18005F8B8 = 0;
  }
  v3 = StopVaultRpcServer();
  if ( v3 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v3);
  VaultUninitialize();
  if ( hServiceStatus )
  {
    v4 = NotifySCM(1, 0);
    if ( v4 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_78b059fac4093813b2646cef9913e025_Traceguids, v4);
    hServiceStatus = 0;
  }
  if ( hEvent )
  {
    CloseHandle(hEvent);
    hEvent = 0;
  }
  WppCleanupUm();
  byte_18005F5C5 = 0;
  if ( a2 )
    RtlLeaveCriticalSection(&CriticalSection);
}

```

## disassembly

```asm
0x180002884  mov     [rsp+arg_0], rbx
0x180002889  mov     [rsp+arg_8], rbp
0x18000288e  push    rdi
0x18000288f  sub     rsp, 20h
0x180002893  mov     bl, dl
0x180002895  mov     edi, ecx
0x180002897  test    dl, dl
0x180002899  jz      short loc_1800028A8
0x18000289b  lea     rcx, CriticalSection; CriticalSection
0x1800028a2  call    cs:__imp_RtlEnterCriticalSection
0x1800028a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028af  lea     rbp, WPP_GLOBAL_Control
0x1800028b6  cmp     rcx, rbp
0x1800028b9  jz      short loc_1800028D6
0x1800028bb  test    byte ptr [rcx+1Ch], 8
0x1800028bf  jz      short loc_1800028D6
0x1800028c1  mov     rcx, [rcx+10h]
0x1800028c5  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x1800028cc  mov     edx, 1Bh
0x1800028d1  call    WPP_SF_
0x1800028d6  mov     rcx, cs:qword_18005F8C8
0x1800028dd  test    rcx, rcx
0x1800028e0  jz      short loc_1800028F3
0x1800028e2  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800028e8  mov     cs:qword_18005F8C8, 0
0x1800028f3  mov     rcx, cs:qword_18005F8B8
0x1800028fa  test    rcx, rcx
0x1800028fd  jz      short loc_180002910
0x1800028ff  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180002905  mov     cs:qword_18005F8B8, 0
0x180002910  call    ?StopVaultRpcServer@@YAJXZ; StopVaultRpcServer(void)
0x180002915  test    eax, eax
0x180002917  jz      short loc_180002943
0x180002919  mov     rcx, cs:WPP_GLOBAL_Control
0x180002920  cmp     rcx, rbp
0x180002923  jz      short loc_180002943
0x180002925  test    byte ptr [rcx+1Ch], 2
0x180002929  jz      short loc_180002943
0x18000292b  mov     rcx, [rcx+10h]
0x18000292f  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x180002936  mov     edx, 1Ch
0x18000293b  mov     r9d, eax
0x18000293e  call    WPP_SF_d
0x180002943  call    ?VaultUninitialize@@YAXXZ; VaultUninitialize(void)
0x180002948  cmp     cs:hServiceStatus, 0
0x180002950  jz      short loc_180002998
0x180002952  xor     edx, edx
0x180002954  mov     r8d, edi
0x180002957  lea     ecx, [rdx+1]
0x18000295a  call    NotifySCM
0x18000295f  test    eax, eax
0x180002961  jz      short loc_18000298D
0x180002963  mov     rcx, cs:WPP_GLOBAL_Control
0x18000296a  cmp     rcx, rbp
0x18000296d  jz      short loc_18000298D
0x18000296f  test    byte ptr [rcx+1Ch], 1
0x180002973  jz      short loc_18000298D
0x180002975  mov     rcx, [rcx+10h]
0x180002979  lea     r8, WPP_78b059fac4093813b2646cef9913e025_Traceguids
0x180002980  mov     edx, 1Dh
0x180002985  mov     r9d, eax
0x180002988  call    WPP_SF_d
0x18000298d  mov     cs:hServiceStatus, 0
0x180002998  mov     rcx, cs:hEvent; hObject
0x18000299f  test    rcx, rcx
0x1800029a2  jz      short loc_1800029B5
0x1800029a4  call    cs:__imp_CloseHandle
0x1800029aa  mov     cs:hEvent, 0
0x1800029b5  call    WppCleanupUm
0x1800029ba  mov     cs:byte_18005F5C5, 0
0x1800029c1  test    bl, bl
0x1800029c3  jz      short loc_1800029D2
0x1800029c5  lea     rcx, CriticalSection; CriticalSection
0x1800029cc  call    cs:__imp_RtlLeaveCriticalSection
0x1800029d2  mov     rbx, [rsp+28h+arg_0]
0x1800029d7  mov     rbp, [rsp+28h+arg_8]
0x1800029dc  add     rsp, 20h
0x1800029e0  pop     rdi
0x1800029e1  retn
```
