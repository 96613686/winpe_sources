# CVdsPnPNotificationManager::UnregisterPnPNotifications(void)

- ea: `0x14000f4e0`
- end: `0x14000f5f2`
- name: `?UnregisterPnPNotifications@CVdsPnPNotificationManager@@EEAAXXZ`
- size: `274`
- prototype: `void __fastcall(CVdsPnPNotificationManager *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14000f4e0`
- `0x14001671c`

## import_xrefs

- `USER32!UnregisterDeviceNotification` at `0x14000f50c`
- `USER32!UnregisterDeviceNotification` at `0x14000f524`
- `USER32!UnregisterDeviceNotification` at `0x14000f53c`
- `USER32!UnregisterDeviceNotification` at `0x14000f554`
- `USER32!UnregisterDeviceNotification` at `0x14000f50c`
- `USER32!UnregisterDeviceNotification` at `0x14000f524`
- `USER32!UnregisterDeviceNotification` at `0x14000f53c`
- `USER32!UnregisterDeviceNotification` at `0x14000f554`
- `USER32!PostThreadMessageW` at `0x14000f57f`
- `USER32!PostThreadMessageW` at `0x14000f57f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f591`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000f591`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f5a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000f5a0`
- `vdsutil!VdsTraceEx` at `0x14000f5cb`
- `vdsutil!VdsTraceEx` at `0x14000f5cb`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f4fe`
- `vdsutil!??0CVdsCallTracer@@QEAA@KPEBD@Z` at `0x14000f4fe`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f5e1`
- `vdsutil!??1CVdsCallTracer@@QEAA@XZ` at `0x14000f5e1`

## string_xrefs

- `0x14000f5bf`: `UnregisterPnPNotifications: AuxThread did not exit within timeout; skipping cleanup`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVdsPnPNotificationManager::UnregisterPnPNotifications(HDEVNOTIFY *this)
{
  DWORD v2; // ebx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  CVdsCallTracer::CVdsCallTracer(
    (CVdsCallTracer *)v3,
    0x5Eu,
    "CVdsPnPNotificationManager::UnregisterPnPNotifications()");
  UnregisterDeviceNotification(this[16]);
  this[16] = 0;
  UnregisterDeviceNotification(this[17]);
  this[17] = 0;
  UnregisterDeviceNotification(this[18]);
  this[18] = 0;
  UnregisterDeviceNotification(this[19]);
  this[19] = 0;
  if ( CVdsPnPNotificationManager::m_hAuxThread
    && (PostThreadMessageW(CVdsPnPNotificationManager::m_dwAuxThreadId, 0x12u, 0, 0),
        v2 = WaitForSingleObject(CVdsPnPNotificationManager::m_hAuxThread, 0x3A98u),
        CloseHandle(CVdsPnPNotificationManager::m_hAuxThread),
        CVdsPnPNotificationManager::m_hAuxThread = 0,
        CVdsPnPNotificationManager::m_dwAuxThreadId = 0,
        v2) )
  {
    VdsTraceEx(94, 0, "UnregisterPnPNotifications: AuxThread did not exit within timeout; skipping cleanup");
  }
  else
  {
    CVdsPnPNotificationManager::FreeVolumeEventHandleMap((CVdsPnPNotificationManager *)this);
  }
  CVdsCallTracer::~CVdsCallTracer((CVdsCallTracer *)v3);
}

```

## disassembly

```asm
0x14000f4e0  mov     [rsp+arg_0], rbx
0x14000f4e5  push    rdi
0x14000f4e6  sub     rsp, 30h
0x14000f4ea  mov     rdi, rcx
0x14000f4ed  lea     r8, aCvdspnpnotific_19; "CVdsPnPNotificationManager::UnregisterP"...
0x14000f4f4  mov     edx, 5Eh ; '^'
0x14000f4f9  lea     rcx, [rsp+38h+var_18]
0x14000f4fe  call    cs:__imp_??0CVdsCallTracer@@QEAA@KPEBD@Z; CVdsCallTracer::CVdsCallTracer(ulong,char const *)
0x14000f504  nop
0x14000f505  mov     rcx, [rdi+80h]; Handle
0x14000f50c  call    cs:__imp_UnregisterDeviceNotification
0x14000f512  mov     qword ptr [rdi+80h], 0
0x14000f51d  mov     rcx, [rdi+88h]; Handle
0x14000f524  call    cs:__imp_UnregisterDeviceNotification
0x14000f52a  mov     qword ptr [rdi+88h], 0
0x14000f535  mov     rcx, [rdi+90h]; Handle
0x14000f53c  call    cs:__imp_UnregisterDeviceNotification
0x14000f542  mov     qword ptr [rdi+90h], 0
0x14000f54d  mov     rcx, [rdi+98h]; Handle
0x14000f554  call    cs:__imp_UnregisterDeviceNotification
0x14000f55a  mov     qword ptr [rdi+98h], 0
0x14000f565  cmp     cs:?m_hAuxThread@CVdsPnPNotificationManager@@0PEAXEA, 0; void * CVdsPnPNotificationManager::m_hAuxThread
0x14000f56d  jz      short loc_14000F5D3
0x14000f56f  xor     r9d, r9d; lParam
0x14000f572  xor     r8d, r8d; wParam
0x14000f575  lea     edx, [r9+12h]; Msg
0x14000f579  mov     ecx, cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA; idThread
0x14000f57f  call    cs:__imp_PostThreadMessageW
0x14000f585  mov     edx, 3A98h; dwMilliseconds
0x14000f58a  mov     rcx, cs:?m_hAuxThread@CVdsPnPNotificationManager@@0PEAXEA; hHandle
0x14000f591  call    cs:__imp_WaitForSingleObject
0x14000f597  mov     ebx, eax
0x14000f599  mov     rcx, cs:?m_hAuxThread@CVdsPnPNotificationManager@@0PEAXEA; hObject
0x14000f5a0  call    cs:__imp_CloseHandle
0x14000f5a6  mov     cs:?m_hAuxThread@CVdsPnPNotificationManager@@0PEAXEA, 0; void * CVdsPnPNotificationManager::m_hAuxThread
0x14000f5b1  mov     cs:?m_dwAuxThreadId@CVdsPnPNotificationManager@@0KA, 0; ulong CVdsPnPNotificationManager::m_dwAuxThreadId
0x14000f5bb  test    ebx, ebx
0x14000f5bd  jz      short loc_14000F5D3
0x14000f5bf  lea     r8, aUnregisterpnpn; "UnregisterPnPNotifications: AuxThread d"...
0x14000f5c6  xor     edx, edx
0x14000f5c8  lea     ecx, [rdx+5Eh]
0x14000f5cb  call    cs:__imp_VdsTraceEx
0x14000f5d1  jmp     short loc_14000F5DC
0x14000f5d3  mov     rcx, rdi; this
0x14000f5d6  call    ?FreeVolumeEventHandleMap@CVdsPnPNotificationManager@@AEAAXXZ; CVdsPnPNotificationManager::FreeVolumeEventHandleMap(void)
0x14000f5db  nop
0x14000f5dc  lea     rcx, [rsp+38h+var_18]
0x14000f5e1  call    cs:__imp_??1CVdsCallTracer@@QEAA@XZ; CVdsCallTracer::~CVdsCallTracer(void)
0x14000f5e7  mov     rbx, [rsp+38h+arg_0]
0x14000f5ec  add     rsp, 30h
0x14000f5f0  pop     rdi
0x14000f5f1  retn
```
