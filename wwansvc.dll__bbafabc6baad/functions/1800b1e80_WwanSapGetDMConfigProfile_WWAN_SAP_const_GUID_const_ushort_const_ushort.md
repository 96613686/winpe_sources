# WwanSapGetDMConfigProfile(WWAN_SAP const *,_GUID const *,ushort const *,ushort * *)

- ea: `0x1800b1e80`
- end: `0x1800b1fed`
- name: `?WwanSapGetDMConfigProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGPEAPEAG@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ac900`

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
- `0x1800b1e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1fa5`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1fa5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1eb2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1eb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1ed3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1faf`

## string_xrefs

- `0x1800b1ee8`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1fc4`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1edc`: `CreateEvent`
- `0x1800b1f8c`: `WwanSapGetDMConfigProfile`

## pseudocode

```c
__int64 __fastcall WwanSapGetDMConfigProfile(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        unsigned __int16 **a4)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA21u, "CreateEvent", LastError);
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
  v18 = (MessageParams *)a4;
  std::vector<void *>::push_back((char *)v10 + 48, &v18);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(37, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapGetDMConfigProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA35u, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b1e80  mov     [rsp-38h+arg_0], rcx
0x1800b1e85  push    rbp
0x1800b1e86  push    rbx
0x1800b1e87  push    rsi
0x1800b1e88  push    rdi
0x1800b1e89  push    r12
0x1800b1e8b  push    r14
0x1800b1e8d  push    r15
0x1800b1e8f  mov     rbp, rsp
0x1800b1e92  sub     rsp, 20h
0x1800b1e96  mov     r14, r9
0x1800b1e99  mov     r15, r8
0x1800b1e9c  mov     r12, rdx
0x1800b1e9f  mov     dword ptr [rbp+arg_0], 0
0x1800b1ea6  xor     r9d, r9d; lpName
0x1800b1ea9  xor     r8d, r8d; bInitialState
0x1800b1eac  lea     edx, [r9+1]; bManualReset
0x1800b1eb0  xor     ecx, ecx; lpEventAttributes
0x1800b1eb2  call    cs:__imp_CreateEventW
0x1800b1eb8  mov     rdx, rax
0x1800b1ebb  lea     rcx, [rbp+hHandle]
0x1800b1ebf  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b1ec4  nop
0x1800b1ec5  mov     rbx, [rbp+hHandle]
0x1800b1ec9  lea     rax, [rbx+1]
0x1800b1ecd  cmp     rax, 1
0x1800b1ed1  ja      short loc_1800B1EF4
0x1800b1ed3  call    cs:__imp_GetLastError
0x1800b1ed9  mov     r9d, eax; unsigned int
0x1800b1edc  lea     r8, aCreateevent; "CreateEvent"
0x1800b1ee3  mov     edx, 0A21h; unsigned int
0x1800b1ee8  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1eef  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1ef4  mov     ecx, 48h ; 'H'; Size
0x1800b1ef9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1efe  mov     [rbp+arg_10], rax
0x1800b1f02  mov     rcx, rax; this
0x1800b1f05  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b1f0a  mov     rsi, rax
0x1800b1f0d  lea     rdi, [rax+30h]
0x1800b1f11  mov     [rbp+arg_10], rbx
0x1800b1f15  lea     rdx, [rbp+arg_10]
0x1800b1f19  mov     rcx, rdi
0x1800b1f1c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1f21  lea     rax, [rbp+arg_0]
0x1800b1f25  mov     [rbp+arg_10], rax
0x1800b1f29  lea     rdx, [rbp+arg_10]
0x1800b1f2d  mov     rcx, rdi
0x1800b1f30  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1f35  mov     [rbp+arg_10], r12
0x1800b1f39  lea     rdx, [rbp+arg_10]
0x1800b1f3d  mov     rcx, rdi
0x1800b1f40  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1f45  mov     [rbp+arg_10], r15
0x1800b1f49  lea     rdx, [rbp+arg_10]
0x1800b1f4d  mov     rcx, rdi
0x1800b1f50  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1f55  mov     [rbp+arg_10], r14
0x1800b1f59  lea     rdx, [rbp+arg_10]
0x1800b1f5d  mov     rcx, rdi
0x1800b1f60  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1f65  mov     rdx, rsi
0x1800b1f68  mov     ecx, 25h ; '%'
0x1800b1f6d  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1f72  test    eax, eax
0x1800b1f74  jz      short loc_1800B1F9F
0x1800b1f76  test    rsi, rsi
0x1800b1f79  jz      short loc_1800B1F83
0x1800b1f7b  mov     rcx, rsi; this
0x1800b1f7e  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b1f83  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1f8a  xor     edx, edx; struct _GUID *
0x1800b1f8c  lea     rcx, aWwansapgetdmco_0; "WwanSapGetDMConfigProfile"
0x1800b1f93  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b1f98  mov     ebx, 1Fh
0x1800b1f9d  jmp     short loc_1800B1FD3
0x1800b1f9f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1fa2  mov     rcx, rbx; hHandle
0x1800b1fa5  call    cs:__imp_WaitForSingleObject
0x1800b1fab  test    eax, eax
0x1800b1fad  jz      short loc_1800B1FD0
0x1800b1faf  call    cs:__imp_GetLastError
0x1800b1fb5  mov     r9d, eax; unsigned int
0x1800b1fb8  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b1fbf  mov     edx, 0A35h; unsigned int
0x1800b1fc4  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1fcb  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1fd0  mov     ebx, dword ptr [rbp+arg_0]
0x1800b1fd3  lea     rcx, [rbp+hHandle]
0x1800b1fd7  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1fdc  mov     eax, ebx
0x1800b1fde  add     rsp, 20h
0x1800b1fe2  pop     r15
0x1800b1fe4  pop     r14
0x1800b1fe6  pop     r12
0x1800b1fe8  pop     rdi
0x1800b1fe9  pop     rsi
0x1800b1fea  pop     rbx
0x1800b1feb  pop     rbp
0x1800b1fec  retn
```
