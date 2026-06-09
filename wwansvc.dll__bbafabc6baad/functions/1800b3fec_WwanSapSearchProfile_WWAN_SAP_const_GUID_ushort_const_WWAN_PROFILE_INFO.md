# WwanSapSearchProfile(WWAN_SAP const *,_GUID *,ushort const *,WWAN_PROFILE_INFO *)

- ea: `0x1800b3fec`
- end: `0x1800b4159`
- name: `?WwanSapSearchProfile@@YAKPEBUWWAN_SAP@@PEAU_GUID@@PEBGPEAUWWAN_PROFILE_INFO@@@Z`
- size: `365`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, struct _GUID *, const unsigned __int16 *, struct WWAN_PROFILE_INFO *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ad440`

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
- `0x1800b3fec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4111`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4111`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b401e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b401e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b403f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b411b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b403f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b411b`

## string_xrefs

- `0x1800b4054`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4130`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`

## pseudocode

```c
__int64 __fastcall WwanSapSearchProfile(
        const struct WWAN_SAP *a1,
        struct _GUID *a2,
        MessageParams *a3,
        struct WWAN_PROFILE_INFO *a4)
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
    __FatalError(
      "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
      0x4B9u,
      "Failure while creating an Event",
      LastError);
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
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(22, v10) )
  {
    if ( v10 )
      MessageParams::`scalar deleting destructor'(v10, v11);
    WwanLog::Error("WwanSapSearchProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v12 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v8, 0xFFFFFFFF) )
    {
      v13 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x4CDu, "WaitForSingleObject", v13);
    }
    v12 = v15;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v12;
}

```

## disassembly

```asm
0x1800b3fec  mov     [rsp-38h+arg_0], rcx
0x1800b3ff1  push    rbp
0x1800b3ff2  push    rbx
0x1800b3ff3  push    rsi
0x1800b3ff4  push    rdi
0x1800b3ff5  push    r12
0x1800b3ff7  push    r14
0x1800b3ff9  push    r15
0x1800b3ffb  mov     rbp, rsp
0x1800b3ffe  sub     rsp, 20h
0x1800b4002  mov     r14, r9
0x1800b4005  mov     r15, r8
0x1800b4008  mov     r12, rdx
0x1800b400b  mov     dword ptr [rbp+arg_0], 0
0x1800b4012  xor     r9d, r9d; lpName
0x1800b4015  xor     r8d, r8d; bInitialState
0x1800b4018  lea     edx, [r9+1]; bManualReset
0x1800b401c  xor     ecx, ecx; lpEventAttributes
0x1800b401e  call    cs:__imp_CreateEventW
0x1800b4024  mov     rdx, rax
0x1800b4027  lea     rcx, [rbp+hHandle]
0x1800b402b  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b4030  nop
0x1800b4031  mov     rbx, [rbp+hHandle]
0x1800b4035  lea     rax, [rbx+1]
0x1800b4039  cmp     rax, 1
0x1800b403d  ja      short loc_1800B4060
0x1800b403f  call    cs:__imp_GetLastError
0x1800b4045  mov     r9d, eax; unsigned int
0x1800b4048  lea     r8, aFailureWhileCr; "Failure while creating an Event"
0x1800b404f  mov     edx, 4B9h; unsigned int
0x1800b4054  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b405b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4060  mov     ecx, 48h ; 'H'; Size
0x1800b4065  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b406a  mov     [rbp+arg_10], rax
0x1800b406e  mov     rcx, rax; this
0x1800b4071  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b4076  mov     rsi, rax
0x1800b4079  lea     rdi, [rax+30h]
0x1800b407d  mov     [rbp+arg_10], rbx
0x1800b4081  lea     rdx, [rbp+arg_10]
0x1800b4085  mov     rcx, rdi
0x1800b4088  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b408d  lea     rax, [rbp+arg_0]
0x1800b4091  mov     [rbp+arg_10], rax
0x1800b4095  lea     rdx, [rbp+arg_10]
0x1800b4099  mov     rcx, rdi
0x1800b409c  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b40a1  mov     [rbp+arg_10], r12
0x1800b40a5  lea     rdx, [rbp+arg_10]
0x1800b40a9  mov     rcx, rdi
0x1800b40ac  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b40b1  mov     [rbp+arg_10], r15
0x1800b40b5  lea     rdx, [rbp+arg_10]
0x1800b40b9  mov     rcx, rdi
0x1800b40bc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b40c1  mov     [rbp+arg_10], r14
0x1800b40c5  lea     rdx, [rbp+arg_10]
0x1800b40c9  mov     rcx, rdi
0x1800b40cc  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b40d1  mov     rdx, rsi
0x1800b40d4  mov     ecx, 16h
0x1800b40d9  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b40de  test    eax, eax
0x1800b40e0  jz      short loc_1800B410B
0x1800b40e2  test    rsi, rsi
0x1800b40e5  jz      short loc_1800B40EF
0x1800b40e7  mov     rcx, rsi; this
0x1800b40ea  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b40ef  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b40f6  xor     edx, edx; struct _GUID *
0x1800b40f8  lea     rcx, aWwansapsearchp; "WwanSapSearchProfile"
0x1800b40ff  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4104  mov     ebx, 1Fh
0x1800b4109  jmp     short loc_1800B413F
0x1800b410b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b410e  mov     rcx, rbx; hHandle
0x1800b4111  call    cs:__imp_WaitForSingleObject
0x1800b4117  test    eax, eax
0x1800b4119  jz      short loc_1800B413C
0x1800b411b  call    cs:__imp_GetLastError
0x1800b4121  mov     r9d, eax; unsigned int
0x1800b4124  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b412b  mov     edx, 4CDh; unsigned int
0x1800b4130  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4137  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b413c  mov     ebx, dword ptr [rbp+arg_0]
0x1800b413f  lea     rcx, [rbp+hHandle]
0x1800b4143  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4148  mov     eax, ebx
0x1800b414a  add     rsp, 20h
0x1800b414e  pop     r15
0x1800b4150  pop     r14
0x1800b4152  pop     r12
0x1800b4154  pop     rdi
0x1800b4155  pop     rsi
0x1800b4156  pop     rbx
0x1800b4157  pop     rbp
0x1800b4158  retn
```
