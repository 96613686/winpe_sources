# WwanSapGetDMConfigProfileList(WWAN_SAP const *,_GUID const *,WWAN_PROFILE_INFO_LIST * *)

- ea: `0x1800b1ff4`
- end: `0x1800b2152`
- name: `?WwanSapGetDMConfigProfileList@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEAPEAUWWAN_PROFILE_INFO_LIST@@@Z`
- size: `350`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, struct WWAN_PROFILE_INFO_LIST **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ac960`

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
- `0x1800b1ff4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2108`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2108`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2025`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b2025`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2112`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2046`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2112`

## string_xrefs

- `0x1800b205b`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2127`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b204f`: `CreateEvent`
- `0x1800b20ef`: `WwanSapGetDMConfigProfileList`

## pseudocode

```c
__int64 __fastcall WwanSapGetDMConfigProfileList(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        struct WWAN_PROFILE_INFO_LIST **a3)
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
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA00u, "CreateEvent", LastError);
  }
  v16 = (MessageParams *)operator new(0x48u);
  v8 = MessageParams::MessageParams(v16);
  v16 = v6;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)&v13;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a2;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  v16 = (MessageParams *)a3;
  std::vector<void *>::push_back((char *)v8 + 48, &v16);
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(36, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v9);
    WwanLog::Error("WwanSapGetDMConfigProfileList", 0, L"Notification dispatcher: Failed to Queue Message");
    v10 = 31;
  }
  else
  {
    if ( WaitForSingleObject(v6, 0xFFFFFFFF) )
    {
      v11 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA13u, "WaitForSingleObject", v11);
    }
    v10 = v13;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
  return v10;
}

```

## disassembly

```asm
0x1800b1ff4  mov     [rsp-28h+arg_18], rbx
0x1800b1ff9  mov     [rsp-28h+arg_0], rcx
0x1800b1ffe  push    rbp
0x1800b1fff  push    rsi
0x1800b2000  push    rdi
0x1800b2001  push    r14
0x1800b2003  push    r15
0x1800b2005  mov     rbp, rsp
0x1800b2008  sub     rsp, 20h
0x1800b200c  mov     r14, r8
0x1800b200f  mov     r15, rdx
0x1800b2012  mov     dword ptr [rbp+arg_0], 0
0x1800b2019  xor     r9d, r9d; lpName
0x1800b201c  xor     r8d, r8d; bInitialState
0x1800b201f  lea     edx, [r9+1]; bManualReset
0x1800b2023  xor     ecx, ecx; lpEventAttributes
0x1800b2025  call    cs:__imp_CreateEventW
0x1800b202b  mov     rdx, rax
0x1800b202e  lea     rcx, [rbp+hHandle]
0x1800b2032  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800b2037  nop
0x1800b2038  mov     rbx, [rbp+hHandle]
0x1800b203c  lea     rax, [rbx+1]
0x1800b2040  cmp     rax, 1
0x1800b2044  ja      short loc_1800B2067
0x1800b2046  call    cs:__imp_GetLastError
0x1800b204c  mov     r9d, eax; unsigned int
0x1800b204f  lea     r8, aCreateevent; "CreateEvent"
0x1800b2056  mov     edx, 0A00h; unsigned int
0x1800b205b  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2062  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2067  mov     ecx, 48h ; 'H'; Size
0x1800b206c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b2071  mov     [rbp+arg_10], rax
0x1800b2075  mov     rcx, rax; this
0x1800b2078  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b207d  mov     rsi, rax
0x1800b2080  lea     rdi, [rax+30h]
0x1800b2084  mov     [rbp+arg_10], rbx
0x1800b2088  lea     rdx, [rbp+arg_10]
0x1800b208c  mov     rcx, rdi
0x1800b208f  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b2094  lea     rax, [rbp+arg_0]
0x1800b2098  mov     [rbp+arg_10], rax
0x1800b209c  lea     rdx, [rbp+arg_10]
0x1800b20a0  mov     rcx, rdi
0x1800b20a3  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b20a8  mov     [rbp+arg_10], r15
0x1800b20ac  lea     rdx, [rbp+arg_10]
0x1800b20b0  mov     rcx, rdi
0x1800b20b3  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b20b8  mov     [rbp+arg_10], r14
0x1800b20bc  lea     rdx, [rbp+arg_10]
0x1800b20c0  mov     rcx, rdi
0x1800b20c3  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b20c8  mov     rdx, rsi
0x1800b20cb  mov     ecx, 24h ; '$'
0x1800b20d0  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b20d5  test    eax, eax
0x1800b20d7  jz      short loc_1800B2102
0x1800b20d9  test    rsi, rsi
0x1800b20dc  jz      short loc_1800B20E6
0x1800b20de  mov     rcx, rsi; this
0x1800b20e1  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b20e6  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b20ed  xor     edx, edx; struct _GUID *
0x1800b20ef  lea     rcx, aWwansapgetdmco_1; "WwanSapGetDMConfigProfileList"
0x1800b20f6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b20fb  mov     ebx, 1Fh
0x1800b2100  jmp     short loc_1800B2136
0x1800b2102  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2105  mov     rcx, rbx; hHandle
0x1800b2108  call    cs:__imp_WaitForSingleObject
0x1800b210e  test    eax, eax
0x1800b2110  jz      short loc_1800B2133
0x1800b2112  call    cs:__imp_GetLastError
0x1800b2118  mov     r9d, eax; unsigned int
0x1800b211b  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2122  mov     edx, 0A13h; unsigned int
0x1800b2127  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b212e  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2133  mov     ebx, dword ptr [rbp+arg_0]
0x1800b2136  lea     rcx, [rbp+hHandle]
0x1800b213a  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b213f  mov     eax, ebx
0x1800b2141  mov     rbx, [rsp+20h+arg_18]
0x1800b2146  add     rsp, 20h
0x1800b214a  pop     r15
0x1800b214c  pop     r14
0x1800b214e  pop     rdi
0x1800b214f  pop     rsi
0x1800b2150  pop     rbp
0x1800b2151  retn
```
