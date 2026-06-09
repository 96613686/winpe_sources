# WwanSapUssdRequest(WWAN_SAP *,_GUID const *,_WWAN_USSD_REQUEST *,ulong *)

- ea: `0x1800b5f3c`
- end: `0x1800b61ce`
- name: `?WwanSapUssdRequest@@YAKPEAUWWAN_SAP@@PEBU_GUID@@PEAU_WWAN_USSD_REQUEST@@PEAK@Z`
- size: `658`
- prototype: `unsigned int __fastcall(LPCRITICAL_SECTION, const struct _GUID *, struct _WWAN_USSD_REQUEST *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x1800ada80`

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
- `0x1800aaeec`
- `0x1800ab1b8`
- `0x1800aead4`
- `0x1800b5f3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b60b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b6155`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b60b1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b6155`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5f74`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5f74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b60bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b615f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5f95`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b60bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b615f`

## string_xrefs

- `0x1800b5faa`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b60d0`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b6174`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5f9e`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WwanSapUssdRequest(
        MessageParams *a1,
        const struct _GUID *a2,
        struct _WWAN_USSD_REQUEST *a3,
        MessageParams *a4)
{
  HANDLE EventW; // rax
  MessageParams *v9; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rdi
  MessageParams *v12; // rsi
  unsigned int v13; // edx
  unsigned int v14; // edx
  DWORD v15; // eax
  unsigned int v16; // ebx
  DWORD v17; // eax
  unsigned int v19; // [rsp+80h] [rbp+48h] BYREF
  int v20; // [rsp+88h] [rbp+50h] BYREF
  HANDLE hHandle; // [rsp+90h] [rbp+58h] BYREF
  MessageParams *v22; // [rsp+98h] [rbp+60h] BYREF

  v19 = 0;
  v20 = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
  v9 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x5ABu, "CreateEvent", LastError);
  }
  v22 = (MessageParams *)operator new(0x48u);
  v11 = MessageParams::MessageParams(v22);
  v22 = v9;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = (MessageParams *)&v19;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = a1;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = a3;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = (MessageParams *)&v20;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = a4;
  std::vector<void *>::push_back((char *)v11 + 48, &v22);
  v22 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v22);
  if ( (char *)v12 + 48 != (char *)v11 + 48 )
    std::vector<void *>::_Assign_counted_range<void * *>(
      (char *)v12 + 48,
      *((_QWORD *)v11 + 6),
      (__int64)(*((_QWORD *)v11 + 7) - *((_QWORD *)v11 + 6)) >> 3);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(25, v12) )
  {
    if ( v12 )
      MessageParams::`scalar deleting destructor'(v12, v13);
    goto LABEL_13;
  }
  if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
  {
    v15 = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x5C5u, "WaitForSingleObject", v15);
  }
  if ( v19 || (v19 = WwanSapMgrValidateSessionOwnership(&g_sapMgr1, (LPCRITICAL_SECTION)a1, 0, v20)) != 0 )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v14);
    goto LABEL_23;
  }
  if ( !(unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(24, v11) )
  {
    if ( WaitForSingleObject(v9, 0xFFFFFFFF) )
    {
      v17 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x5DBu, "WaitForSingleObject", v17);
    }
    if ( v19 && v20 == 1 )
      checkSessionOwnershipSap((LPCRITICAL_SECTION)a1, 1);
LABEL_23:
    v16 = v19;
    goto LABEL_24;
  }
LABEL_13:
  if ( v11 )
    MessageParams::`scalar deleting destructor'(v11, v13);
  WwanLog::Error("WwanSapUssdRequest", 0, L"Notification dispatcher: Failed to Queue Message");
  v16 = 31;
LABEL_24:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v16;
}

```

## disassembly

```asm
0x1800b5f3c  push    rbp
0x1800b5f3e  push    rbx
0x1800b5f3f  push    rsi
0x1800b5f40  push    rdi
0x1800b5f41  push    r12
0x1800b5f43  push    r13
0x1800b5f45  push    r14
0x1800b5f47  push    r15
0x1800b5f49  mov     rbp, rsp
0x1800b5f4c  sub     rsp, 38h
0x1800b5f50  mov     rsi, r9
0x1800b5f53  mov     r13, r8
0x1800b5f56  mov     r15, rdx
0x1800b5f59  mov     r12, rcx
0x1800b5f5c  mov     [rbp+arg_0], 0
0x1800b5f63  mov     [rbp+arg_8], 0
0x1800b5f6a  xor     r9d, r9d; lpName
0x1800b5f6d  xor     r8d, r8d; bInitialState
0x1800b5f70  xor     edx, edx; bManualReset
0x1800b5f72  xor     ecx, ecx; lpEventAttributes
0x1800b5f74  call    cs:__imp_CreateEventW
0x1800b5f7a  mov     rdx, rax
0x1800b5f7d  lea     rcx, [rbp+hHandle]
0x1800b5f81  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b5f86  nop
0x1800b5f87  mov     rbx, [rbp+hHandle]
0x1800b5f8b  lea     rax, [rbx+1]
0x1800b5f8f  cmp     rax, 1
0x1800b5f93  ja      short loc_1800B5FB6
0x1800b5f95  call    cs:__imp_GetLastError
0x1800b5f9b  mov     r9d, eax; unsigned int
0x1800b5f9e  lea     r8, aCreateevent; "CreateEvent"
0x1800b5fa5  mov     edx, 5ABh; unsigned int
0x1800b5faa  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5fb1  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5fb6  mov     ecx, 48h ; 'H'; Size
0x1800b5fbb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5fc0  mov     [rbp+arg_18], rax
0x1800b5fc4  mov     rcx, rax; this
0x1800b5fc7  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b5fcc  mov     rdi, rax
0x1800b5fcf  lea     r14, [rax+30h]
0x1800b5fd3  mov     [rbp+arg_18], rbx
0x1800b5fd7  lea     rdx, [rbp+arg_18]
0x1800b5fdb  mov     rcx, r14
0x1800b5fde  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5fe3  lea     rax, [rbp+arg_0]
0x1800b5fe7  mov     [rbp+arg_18], rax
0x1800b5feb  lea     rdx, [rbp+arg_18]
0x1800b5fef  mov     rcx, r14
0x1800b5ff2  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b5ff7  mov     [rbp+arg_18], r12
0x1800b5ffb  lea     rdx, [rbp+arg_18]
0x1800b5fff  mov     rcx, r14
0x1800b6002  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b6007  mov     [rbp+arg_18], r15
0x1800b600b  lea     rdx, [rbp+arg_18]
0x1800b600f  mov     rcx, r14
0x1800b6012  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b6017  mov     [rbp+arg_18], r13
0x1800b601b  lea     rdx, [rbp+arg_18]
0x1800b601f  mov     rcx, r14
0x1800b6022  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b6027  lea     rax, [rbp+arg_8]
0x1800b602b  mov     [rbp+arg_18], rax
0x1800b602f  lea     rdx, [rbp+arg_18]
0x1800b6033  mov     rcx, r14
0x1800b6036  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b603b  mov     [rbp+arg_18], rsi
0x1800b603f  lea     rdx, [rbp+arg_18]
0x1800b6043  mov     rcx, r14
0x1800b6046  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b604b  mov     ecx, 48h ; 'H'; Size
0x1800b6050  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b6055  mov     [rbp+arg_18], rax
0x1800b6059  mov     rcx, rax; this
0x1800b605c  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b6061  mov     rsi, rax
0x1800b6064  lea     rcx, [rax+30h]
0x1800b6068  cmp     rcx, r14
0x1800b606b  jz      short loc_1800B6080
0x1800b606d  mov     r8, [r14+8]
0x1800b6071  sub     r8, [r14]
0x1800b6074  sar     r8, 3
0x1800b6078  mov     rdx, [r14]
0x1800b607b  call    ??$_Assign_counted_range@PEAPEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXPEAPEAX_K@Z; std::vector<void *>::_Assign_counted_range<void * *>(void * *,unsigned __int64)
0x1800b6080  mov     rdx, rsi
0x1800b6083  mov     ecx, 19h
0x1800b6088  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b608d  xor     r14d, r14d
0x1800b6090  test    eax, eax
0x1800b6092  jz      short loc_1800B60A7
0x1800b6094  test    rsi, rsi
0x1800b6097  jz      loc_1800B6126
0x1800b609d  mov     rcx, rsi; this
0x1800b60a0  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b60a5  jmp     short loc_1800B6126
0x1800b60a7  or      r13d, 0FFFFFFFFh
0x1800b60ab  mov     edx, r13d; dwMilliseconds
0x1800b60ae  mov     rcx, rbx; hHandle
0x1800b60b1  call    cs:__imp_WaitForSingleObject
0x1800b60b7  test    eax, eax
0x1800b60b9  jz      short loc_1800B60DC
0x1800b60bb  call    cs:__imp_GetLastError
0x1800b60c1  mov     r9d, eax; unsigned int
0x1800b60c4  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b60cb  mov     edx, 5C5h; unsigned int
0x1800b60d0  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b60d7  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b60dc  cmp     [rbp+arg_0], r14d
0x1800b60e0  jnz     loc_1800B61A2
0x1800b60e6  mov     eax, [rbp+arg_8]
0x1800b60e9  mov     [rsp+38h+var_10], eax; int
0x1800b60ed  mov     [rsp+38h+var_18], r14d; int
0x1800b60f2  mov     esi, 1
0x1800b60f7  mov     r9d, esi
0x1800b60fa  mov     r8, r15
0x1800b60fd  mov     rdx, r12; LPCRITICAL_SECTION
0x1800b6100  lea     rcx, ?g_sapMgr1@@3U_WWAN_SAP_MGR@@A; lpCriticalSection
0x1800b6107  call    _WwanSapMgrValidateSessionOwnership
0x1800b610c  mov     [rbp+arg_0], eax
0x1800b610f  test    eax, eax
0x1800b6111  jnz     loc_1800B61A2
0x1800b6117  mov     rdx, rdi
0x1800b611a  lea     ecx, [rsi+17h]
0x1800b611d  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b6122  test    eax, eax
0x1800b6124  jz      short loc_1800B614F
0x1800b6126  test    rdi, rdi
0x1800b6129  jz      short loc_1800B6133
0x1800b612b  mov     rcx, rdi; this
0x1800b612e  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b6133  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b613a  xor     edx, edx; struct _GUID *
0x1800b613c  lea     rcx, aWwansapussdreq; "WwanSapUssdRequest"
0x1800b6143  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b6148  mov     ebx, 1Fh
0x1800b614d  jmp     short loc_1800B61B2
0x1800b614f  mov     edx, r13d; dwMilliseconds
0x1800b6152  mov     rcx, rbx; hHandle
0x1800b6155  call    cs:__imp_WaitForSingleObject
0x1800b615b  test    eax, eax
0x1800b615d  jz      short loc_1800B6180
0x1800b615f  call    cs:__imp_GetLastError
0x1800b6165  mov     r9d, eax; unsigned int
0x1800b6168  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b616f  mov     edx, 5DBh; unsigned int
0x1800b6174  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b617b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b6180  cmp     [rbp+arg_0], r14d
0x1800b6184  jz      short loc_1800B61AF
0x1800b6186  cmp     [rbp+arg_8], esi
0x1800b6189  jnz     short loc_1800B61AF
0x1800b618b  mov     [rsp+38h+var_18], esi; int
0x1800b618f  xor     r9d, r9d
0x1800b6192  mov     r8d, esi
0x1800b6195  mov     rdx, r15
0x1800b6198  mov     rcx, r12; lpCriticalSection
0x1800b619b  call    _checkSessionOwnershipSap
0x1800b61a0  jmp     short loc_1800B61AF
0x1800b61a2  test    rdi, rdi
0x1800b61a5  jz      short loc_1800B61AF
0x1800b61a7  mov     rcx, rdi; this
0x1800b61aa  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b61af  mov     ebx, [rbp+arg_0]
0x1800b61b2  lea     rcx, [rbp+hHandle]
0x1800b61b6  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b61bb  mov     eax, ebx
0x1800b61bd  add     rsp, 38h
0x1800b61c1  pop     r15
0x1800b61c3  pop     r14
0x1800b61c5  pop     r13
0x1800b61c7  pop     r12
0x1800b61c9  pop     rdi
0x1800b61ca  pop     rsi
0x1800b61cb  pop     rbx
0x1800b61cc  pop     rbp
0x1800b61cd  retn
```
