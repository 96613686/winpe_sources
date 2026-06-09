# Wwan2SapCloseAllDeviceServiceCommandSessions(WWAN_SAP *,_GUID const *,ulong *)

- ea: `0x1800aee14`
- end: `0x1800af031`
- name: `?Wwan2SapCloseAllDeviceServiceCommandSessions@@YAKPEAUWWAN_SAP@@PEBU_GUID@@PEAK@Z`
- size: `541`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b148c`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x180014f1c`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x1800893b4`
- `0x1800aee14`
- `0x1800b645c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aee62`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800aee62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aee9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aeeae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aee9d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800aeeae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800aefbd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800aefbd`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aeec0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aeec0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aefc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aefc7`

## string_xrefs

- `0x1800aeef6`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800aefdc`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800aeeea`: `CreateEvent`
- `0x1800aee7e`: `[%p] Failed to get device service SAP for close command session`
- `0x1800aee4e`: `Wwan2SapCloseAllDeviceServiceCommandSessions`
- `0x1800aee87`: `Wwan2SapCloseAllDeviceServiceCommandSessions`
- `0x1800aef9a`: `Wwan2SapCloseAllDeviceServiceCommandSessions`
- `0x1800aefff`: `Wwan2SapCloseAllDeviceServiceCommandSessions`
- `0x1800aeff6`: `[%p] Failed to delete subscription for command session close. Error = %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapCloseAllDeviceServiceCommandSessions(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int *a3)
{
  struct _WWAN_DEVICE_SERVICES_SAP *DeviceServicesSap; // rax
  HANDLE EventW; // rax
  HANDLE v9; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rax
  MessageParams *v12; // r14
  unsigned int v13; // edx
  DWORD v14; // eax
  _QWORD v15[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v16; // [rsp+70h] [rbp+30h] BYREF
  HANDLE hHandle; // [rsp+88h] [rbp+48h] BYREF

  v16 = 0;
  if ( !a1 )
  {
    WwanLog::Error("Wwan2SapCloseAllDeviceServiceCommandSessions", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  DeviceServicesSap = _wwan2SapGetDeviceServicesSap(a1, a2, 0);
  if ( !DeviceServicesSap )
  {
    WwanLog::Info(
      "Wwan2SapCloseAllDeviceServiceCommandSessions",
      0,
      L"[%p] Failed to get device service SAP for close command session",
      a1);
    v16 = 12;
    LeaveCriticalSection((LPCRITICAL_SECTION)a1);
    return v16;
  }
  ++*((_DWORD *)DeviceServicesSap + 8);
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
  v9 = hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x894u, "CreateEvent", LastError);
  }
  v11 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v11);
  v15[0] = v9;
  std::vector<void *>::push_back((char *)v12 + 48, v15);
  v15[0] = &v16;
  std::vector<void *>::push_back((char *)v12 + 48, v15);
  v15[0] = a1;
  std::vector<void *>::push_back((char *)v12 + 48, v15);
  v15[0] = a2;
  std::vector<void *>::push_back((char *)v12 + 48, v15);
  v15[0] = a3;
  std::vector<void *>::push_back((char *)v12 + 48, v15);
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(29, v12) )
  {
    if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
    {
      v14 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x8A8u, "WaitForSingleObject", v14);
    }
    if ( v16 )
      WwanLog::Error(
        "Wwan2SapCloseAllDeviceServiceCommandSessions",
        0,
        L"[%p] Failed to delete subscription for command session close. Error = %d",
        a1,
        v16);
    tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
    return v16;
  }
  if ( v12 )
    MessageParams::`scalar deleting destructor'(v12, v13);
  WwanLog::Error("Wwan2SapCloseAllDeviceServiceCommandSessions", 0, L"Notification dispatcher: Failed to Queue Message");
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return 31;
}

```

## disassembly

```asm
0x1800aee14  mov     [rsp-28h+arg_8], rbx
0x1800aee19  mov     [rsp-28h+arg_10], rsi
0x1800aee1e  push    rbp
0x1800aee1f  push    rdi
0x1800aee20  push    r12
0x1800aee22  push    r14
0x1800aee24  push    r15
0x1800aee26  mov     rbp, rsp
0x1800aee29  sub     rsp, 40h
0x1800aee2d  mov     r12, r8
0x1800aee30  mov     r15, rdx
0x1800aee33  mov     rsi, rcx
0x1800aee36  mov     [rbp+arg_0], 0
0x1800aee3d  test    rcx, rcx
0x1800aee40  jnz     short loc_1800AEE62
0x1800aee42  xor     r9d, r9d
0x1800aee45  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800aee4c  xor     edx, edx; struct _GUID *
0x1800aee4e  lea     rcx, aWwan2sapclosea; "Wwan2SapCloseAllDeviceServiceCommandSes"...
0x1800aee55  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800aee5a  lea     eax, [rsi+57h]
0x1800aee5d  jmp     loc_1800AF018
0x1800aee62  call    cs:__imp_EnterCriticalSection
0x1800aee68  xor     r8d, r8d; int
0x1800aee6b  mov     rdx, r15; struct _GUID *
0x1800aee6e  mov     rcx, rsi; struct WWAN_SAP *
0x1800aee71  call    ?_wwan2SapGetDeviceServicesSap@@YAPEAU_WWAN_DEVICE_SERVICES_SAP@@PEAUWWAN_SAP@@PEBU_GUID@@H@Z; _wwan2SapGetDeviceServicesSap(WWAN_SAP *,_GUID const *,int)
0x1800aee76  test    rax, rax
0x1800aee79  jnz     short loc_1800AEEA8
0x1800aee7b  mov     r9, rsi
0x1800aee7e  lea     r8, aPFailedToGetDe; "[%p] Failed to get device service SAP f"...
0x1800aee85  xor     edx, edx; struct _GUID *
0x1800aee87  lea     rcx, aWwan2sapclosea; "Wwan2SapCloseAllDeviceServiceCommandSes"...
0x1800aee8e  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800aee93  mov     [rbp+arg_0], 0Ch
0x1800aee9a  mov     rcx, rsi; lpCriticalSection
0x1800aee9d  call    cs:__imp_LeaveCriticalSection
0x1800aeea3  jmp     loc_1800AF015
0x1800aeea8  inc     dword ptr [rax+20h]
0x1800aeeab  mov     rcx, rsi; lpCriticalSection
0x1800aeeae  call    cs:__imp_LeaveCriticalSection
0x1800aeeb4  xor     r9d, r9d; lpName
0x1800aeeb7  xor     r8d, r8d; bInitialState
0x1800aeeba  lea     edx, [r9+1]; bManualReset
0x1800aeebe  xor     ecx, ecx; lpEventAttributes
0x1800aeec0  call    cs:__imp_CreateEventW
0x1800aeec6  mov     rdx, rax
0x1800aeec9  lea     rcx, [rbp+hHandle]
0x1800aeecd  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800aeed2  nop
0x1800aeed3  mov     rbx, [rbp+hHandle]
0x1800aeed7  lea     rax, [rbx+1]
0x1800aeedb  cmp     rax, 1
0x1800aeedf  ja      short loc_1800AEF02
0x1800aeee1  call    cs:__imp_GetLastError
0x1800aeee7  mov     r9d, eax; unsigned int
0x1800aeeea  lea     r8, aCreateevent; "CreateEvent"
0x1800aeef1  mov     edx, 894h; unsigned int
0x1800aeef6  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800aeefd  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800aef02  mov     ecx, 48h ; 'H'; Size
0x1800aef07  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800aef0c  mov     [rbp+var_10], rax
0x1800aef10  mov     rcx, rax; this
0x1800aef13  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800aef18  mov     r14, rax
0x1800aef1b  lea     rdi, [rax+30h]
0x1800aef1f  mov     [rbp+var_10], rbx
0x1800aef23  lea     rdx, [rbp+var_10]
0x1800aef27  mov     rcx, rdi
0x1800aef2a  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800aef2f  lea     rax, [rbp+arg_0]
0x1800aef33  mov     [rbp+var_10], rax
0x1800aef37  lea     rdx, [rbp+var_10]
0x1800aef3b  mov     rcx, rdi
0x1800aef3e  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800aef43  mov     [rbp+var_10], rsi
0x1800aef47  lea     rdx, [rbp+var_10]
0x1800aef4b  mov     rcx, rdi
0x1800aef4e  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800aef53  mov     [rbp+var_10], r15
0x1800aef57  lea     rdx, [rbp+var_10]
0x1800aef5b  mov     rcx, rdi
0x1800aef5e  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800aef63  mov     [rbp+var_10], r12
0x1800aef67  lea     rdx, [rbp+var_10]
0x1800aef6b  mov     rcx, rdi
0x1800aef6e  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800aef73  mov     rdx, r14
0x1800aef76  mov     ecx, 1Dh
0x1800aef7b  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800aef80  test    eax, eax
0x1800aef82  jz      short loc_1800AEFB7
0x1800aef84  test    r14, r14
0x1800aef87  jz      short loc_1800AEF91
0x1800aef89  mov     rcx, r14; this
0x1800aef8c  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800aef91  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800aef98  xor     edx, edx; struct _GUID *
0x1800aef9a  lea     rcx, aWwan2sapclosea; "Wwan2SapCloseAllDeviceServiceCommandSes"...
0x1800aefa1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800aefa6  nop
0x1800aefa7  lea     rcx, [rbp+hHandle]
0x1800aefab  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800aefb0  mov     eax, 1Fh
0x1800aefb5  jmp     short loc_1800AF018
0x1800aefb7  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800aefba  mov     rcx, rbx; hHandle
0x1800aefbd  call    cs:__imp_WaitForSingleObject
0x1800aefc3  test    eax, eax
0x1800aefc5  jz      short loc_1800AEFE8
0x1800aefc7  call    cs:__imp_GetLastError
0x1800aefcd  mov     r9d, eax; unsigned int
0x1800aefd0  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800aefd7  mov     edx, 8A8h; unsigned int
0x1800aefdc  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800aefe3  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800aefe8  mov     eax, [rbp+arg_0]
0x1800aefeb  test    eax, eax
0x1800aefed  jz      short loc_1800AF00C
0x1800aefef  mov     [rsp+40h+var_20], eax
0x1800aeff3  mov     r9, rsi
0x1800aeff6  lea     r8, aPFailedToDelet; "[%p] Failed to delete subscription for "...
0x1800aeffd  xor     edx, edx; struct _GUID *
0x1800aefff  lea     rcx, aWwan2sapclosea; "Wwan2SapCloseAllDeviceServiceCommandSes"...
0x1800af006  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800af00b  nop
0x1800af00c  lea     rcx, [rbp+hHandle]
0x1800af010  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800af015  mov     eax, [rbp+arg_0]
0x1800af018  lea     r11, [rsp+40h+var_s0]
0x1800af01d  mov     rbx, [r11+38h]
0x1800af021  mov     rsi, [r11+40h]
0x1800af025  mov     rsp, r11
0x1800af028  pop     r15
0x1800af02a  pop     r14
0x1800af02c  pop     r12
0x1800af02e  pop     rdi
0x1800af02f  pop     rbp
0x1800af030  retn
```
