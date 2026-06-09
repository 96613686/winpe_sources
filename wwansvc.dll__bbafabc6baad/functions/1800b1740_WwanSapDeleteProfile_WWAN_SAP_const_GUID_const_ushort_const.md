# WwanSapDeleteProfile(WWAN_SAP const *,_GUID const *,ushort const *)

- ea: `0x1800b1740`
- end: `0x1800b189e`
- name: `?WwanSapDeleteProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBG@Z`
- size: `350`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1800ac7a0`

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
- `0x1800b1740`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1854`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1854`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1771`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b185e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1792`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b185e`

## string_xrefs

- `0x1800b17a7`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1873`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b179b`: `CreateEvent`
- `0x1800b183b`: `WwanSapDeleteProfile`

## pseudocode

```c
__int64 __fastcall WwanSapDeleteProfile(const struct WWAN_SAP *a1, const struct _GUID *a2, MessageParams *a3)
{
  HANDLE EventW; // rax
  MessageParams *v6; // rbx
  DWORD LastError; // eax
  MessageParams *v8; // rsi
  unsigned int v9; // edx
  unsigned int v10; // ebx
  DWORD v11; // eax
  unsigned int v13; // [rsp+50h] [rbp+30h] BYREF
  int v14; // [rsp+54h] [rbp+34h]
  HANDLE hHandle; // [rsp+58h] [rbp+38h] BYREF
  MessageParams *v16; // [rsp+60h] [rbp+40h] BYREF

  v14 = HIDWORD(a1);
  v13 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
  v6 = (MessageParams *)hHandle;
  if ( (unsigned __int64)hHandle + 1 <= 1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x430u, "CreateEvent", LastError);
  }
  v16 = (MessageParams *)operator new(0x48u);
  v8 = MessageParams::MessageParams(v16);
  v16 = v6;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)&v13;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = a3;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(14, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v9);
    WwanLog::Error("WwanSapDeleteProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v10 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v6, 0xFFFFFFFF) )
    {
      v11 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x443u, "WaitForSingleObject", v11);
    }
    v10 = v13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v10;
}

```

## disassembly

```asm
0x1800b1740  mov     [rsp-28h+arg_18], rbx
0x1800b1745  mov     [rsp-28h+arg_0], rcx
0x1800b174a  push    rbp
0x1800b174b  push    rsi
0x1800b174c  push    rdi
0x1800b174d  push    r14
0x1800b174f  push    r15
0x1800b1751  mov     rbp, rsp
0x1800b1754  sub     rsp, 20h
0x1800b1758  mov     r14, r8
0x1800b175b  mov     r15, rdx
0x1800b175e  mov     dword ptr [rbp+arg_0], 0
0x1800b1765  xor     r9d, r9d; lpName
0x1800b1768  xor     r8d, r8d; bInitialState
0x1800b176b  lea     edx, [r9+1]; bManualReset
0x1800b176f  xor     ecx, ecx; lpEventAttributes
0x1800b1771  call    cs:__imp_CreateEventW
0x1800b1777  mov     rdx, rax
0x1800b177a  lea     rcx, [rbp+hHandle]
0x1800b177e  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b1783  nop
0x1800b1784  mov     rbx, [rbp+hHandle]
0x1800b1788  lea     rax, [rbx+1]
0x1800b178c  cmp     rax, 1
0x1800b1790  ja      short loc_1800B17B3
0x1800b1792  call    cs:__imp_GetLastError
0x1800b1798  mov     r9d, eax; unsigned int
0x1800b179b  lea     r8, aCreateevent; "CreateEvent"
0x1800b17a2  mov     edx, 430h; unsigned int
0x1800b17a7  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b17ae  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b17b3  mov     ecx, 48h ; 'H'; Size
0x1800b17b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b17bd  mov     [rbp+arg_10], rax
0x1800b17c1  mov     rcx, rax; this
0x1800b17c4  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b17c9  mov     rsi, rax
0x1800b17cc  lea     rdi, [rax+30h]
0x1800b17d0  mov     [rbp+arg_10], rbx
0x1800b17d4  lea     rdx, [rbp+arg_10]
0x1800b17d8  mov     rcx, rdi
0x1800b17db  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b17e0  lea     rax, [rbp+arg_0]
0x1800b17e4  mov     [rbp+arg_10], rax
0x1800b17e8  lea     rdx, [rbp+arg_10]
0x1800b17ec  mov     rcx, rdi
0x1800b17ef  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b17f4  mov     [rbp+arg_10], r15
0x1800b17f8  lea     rdx, [rbp+arg_10]
0x1800b17fc  mov     rcx, rdi
0x1800b17ff  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1804  mov     [rbp+arg_10], r14
0x1800b1808  lea     rdx, [rbp+arg_10]
0x1800b180c  mov     rcx, rdi
0x1800b180f  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b1814  mov     rdx, rsi
0x1800b1817  mov     ecx, 0Eh
0x1800b181c  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1821  test    eax, eax
0x1800b1823  jz      short loc_1800B184E
0x1800b1825  test    rsi, rsi
0x1800b1828  jz      short loc_1800B1832
0x1800b182a  mov     rcx, rsi; this
0x1800b182d  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b1832  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1839  xor     edx, edx; struct _GUID *
0x1800b183b  lea     rcx, aWwansapdeletep; "WwanSapDeleteProfile"
0x1800b1842  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b1847  mov     ebx, 1Fh
0x1800b184c  jmp     short loc_1800B1882
0x1800b184e  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1851  mov     rcx, rbx; hHandle
0x1800b1854  call    cs:__imp_WaitForSingleObject
0x1800b185a  test    eax, eax
0x1800b185c  jz      short loc_1800B187F
0x1800b185e  call    cs:__imp_GetLastError
0x1800b1864  mov     r9d, eax; unsigned int
0x1800b1867  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b186e  mov     edx, 443h; unsigned int
0x1800b1873  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b187a  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b187f  mov     ebx, dword ptr [rbp+arg_0]
0x1800b1882  lea     rcx, [rbp+hHandle]
0x1800b1886  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b188b  mov     eax, ebx
0x1800b188d  mov     rbx, [rsp+20h+arg_18]
0x1800b1892  add     rsp, 20h
0x1800b1896  pop     r15
0x1800b1898  pop     r14
0x1800b189a  pop     rdi
0x1800b189b  pop     rsi
0x1800b189c  pop     rbp
0x1800b189d  retn
```
