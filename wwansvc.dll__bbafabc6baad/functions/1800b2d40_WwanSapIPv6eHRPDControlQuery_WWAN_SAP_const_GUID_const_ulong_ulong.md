# WwanSapIPv6eHRPDControlQuery(WWAN_SAP const *,_GUID const *,ulong *,ulong *)

- ea: `0x1800b2d40`
- end: `0x1800b2ead`
- name: `?WwanSapIPv6eHRPDControlQuery@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAK2@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800acee0`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x1800893b4`
- `0x1800b2d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2e65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2e65`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2d72`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2d72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2d93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2e6f`

## string_xrefs

- `0x1800b2da8`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2e84`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2d9c`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall WwanSapIPv6eHRPDControlQuery(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        MessageParams *a4)
{
  HANDLE EventW; // rax
  MessageParams *v8; // rbx
  DWORD LastError; // eax
  MessageParams *v10; // rsi
  unsigned int v11; // edx
  unsigned int v12; // ebx
  DWORD v13; // eax
  unsigned int v15; // [rsp+60h] [rbp+40h] BYREF
  int v16; // [rsp+64h] [rbp+44h]
  HANDLE hHandle; // [rsp+68h] [rbp+48h] BYREF
  MessageParams *v18; // [rsp+70h] [rbp+50h] BYREF

  v16 = HIDWORD(a1);
  v15 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
  v8 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB27u, "CreateEvent", LastError);
  }
  v18 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v18);
  v18 = v8;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)&v15;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a3;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  v18 = a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(44, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapIPv6eHRPDControlQuery", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xB3Bu, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b2d40  mov     [rsp-38h+arg_0], rcx
0x1800b2d45  push    rbp
0x1800b2d46  push    rbx
0x1800b2d47  push    rsi
0x1800b2d48  push    rdi
0x1800b2d49  push    r12
0x1800b2d4b  push    r14
0x1800b2d4d  push    r15
0x1800b2d4f  mov     rbp, rsp
0x1800b2d52  sub     rsp, 20h
0x1800b2d56  mov     r14, r9
0x1800b2d59  mov     r15, r8
0x1800b2d5c  mov     r12, rdx
0x1800b2d5f  mov     dword ptr [rbp+arg_0], 0
0x1800b2d66  xor     r9d, r9d; lpName
0x1800b2d69  xor     r8d, r8d; bInitialState
0x1800b2d6c  lea     edx, [r9+1]; bManualReset
0x1800b2d70  xor     ecx, ecx; lpEventAttributes
0x1800b2d72  call    cs:__imp_CreateEventW
0x1800b2d78  mov     rdx, rax
0x1800b2d7b  lea     rcx, [rbp+hHandle]
0x1800b2d7f  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2d84  nop
0x1800b2d85  mov     rbx, [rbp+hHandle]
0x1800b2d89  lea     rax, [rbx+1]
0x1800b2d8d  cmp     rax, 1
0x1800b2d91  ja      short loc_1800B2DB4
0x1800b2d93  call    cs:__imp_GetLastError
0x1800b2d99  mov     r9d, eax; unsigned int
0x1800b2d9c  lea     r8, aCreateevent; "CreateEvent"
0x1800b2da3  mov     edx, 0B27h; unsigned int
0x1800b2da8  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2daf  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2db4  mov     ecx, 48h ; 'H'; Size
0x1800b2db9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2dbe  mov     [rbp+arg_10], rax
0x1800b2dc2  mov     rcx, rax; this
0x1800b2dc5  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b2dca  mov     rsi, rax
0x1800b2dcd  lea     rdi, [rax+30h]
0x1800b2dd1  mov     [rbp+arg_10], rbx
0x1800b2dd5  lea     rdx, [rbp+arg_10]
0x1800b2dd9  mov     rcx, rdi
0x1800b2ddc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2de1  lea     rax, [rbp+arg_0]
0x1800b2de5  mov     [rbp+arg_10], rax
0x1800b2de9  lea     rdx, [rbp+arg_10]
0x1800b2ded  mov     rcx, rdi
0x1800b2df0  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2df5  mov     [rbp+arg_10], r12
0x1800b2df9  lea     rdx, [rbp+arg_10]
0x1800b2dfd  mov     rcx, rdi
0x1800b2e00  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2e05  mov     [rbp+arg_10], r15
0x1800b2e09  lea     rdx, [rbp+arg_10]
0x1800b2e0d  mov     rcx, rdi
0x1800b2e10  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2e15  mov     [rbp+arg_10], r14
0x1800b2e19  lea     rdx, [rbp+arg_10]
0x1800b2e1d  mov     rcx, rdi
0x1800b2e20  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2e25  mov     rdx, rsi
0x1800b2e28  mov     ecx, 2Ch ; ','
0x1800b2e2d  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b2e32  test    eax, eax
0x1800b2e34  jz      short loc_1800B2E5F
0x1800b2e36  test    rsi, rsi
0x1800b2e39  jz      short loc_1800B2E43
0x1800b2e3b  mov     rcx, rsi; this
0x1800b2e3e  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b2e43  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b2e4a  xor     edx, edx; struct _GUID *
0x1800b2e4c  lea     rcx, aWwansapipv6ehr; "WwanSapIPv6eHRPDControlQuery"
0x1800b2e53  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b2e58  mov     ebx, 1Fh
0x1800b2e5d  jmp     short loc_1800B2E93
0x1800b2e5f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2e62  mov     rcx, rbx; hHandle
0x1800b2e65  call    cs:__imp_WaitForSingleObject
0x1800b2e6b  test    eax, eax
0x1800b2e6d  jz      short loc_1800B2E90
0x1800b2e6f  call    cs:__imp_GetLastError
0x1800b2e75  mov     r9d, eax; unsigned int
0x1800b2e78  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2e7f  mov     edx, 0B3Bh; unsigned int
0x1800b2e84  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2e8b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2e90  mov     ebx, dword ptr [rbp+arg_0]
0x1800b2e93  lea     rcx, [rbp+hHandle]
0x1800b2e97  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b2e9c  mov     eax, ebx
0x1800b2e9e  add     rsp, 20h
0x1800b2ea2  pop     r15
0x1800b2ea4  pop     r14
0x1800b2ea6  pop     r12
0x1800b2ea8  pop     rdi
0x1800b2ea9  pop     rsi
0x1800b2eaa  pop     rbx
0x1800b2eab  pop     rbp
0x1800b2eac  retn
```
