# Wwan2SapQueryDeviceServiceSupportedCommands(WWAN_SAP *,_GUID const *,_GUID const *,ulong *)

- ea: `0x1800afee0`
- end: `0x1800b00ce`
- name: `?Wwan2SapQueryDeviceServiceSupportedCommands@@YAKPEAUWWAN_SAP@@PEBU_GUID@@1PEAK@Z`
- size: `494`
- prototype: `unsigned int __fastcall(struct WWAN_SAP *, const struct _GUID *, const struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800ac180`

## callees

- `0x180008abc`
- `0x180010e94`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x18007289c`
- `0x18007cb94`
- `0x180089388`
- `0x1800893b4`
- `0x1800afee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0085`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0085`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aff3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800aff3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b008f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aff8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b008f`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800aff84`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800aff84`

## string_xrefs

- `0x1800aff74`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800affa3`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b00a4`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800aff68`: `CreateEvent`
- `0x1800aff20`: `Wwan2SapQueryDeviceServiceSupportedCommands`
- `0x1800b0065`: `Wwan2SapQueryDeviceServiceSupportedCommands`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Wwan2SapQueryDeviceServiceSupportedCommands(
        struct WWAN_SAP *a1,
        const struct _GUID *a2,
        const struct _GUID *a3,
        MessageParams *a4)
{
  HANDLE EventW; // rax
  MessageParams *v10; // rbx
  DWORD LastError; // eax
  DWORD v12; // eax
  MessageParams *v13; // rsi
  unsigned int v14; // edx
  DWORD v15; // eax
  HANDLE hHandle; // [rsp+20h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+28h] [rbp-20h] BYREF
  MessageParams *v18[3]; // [rsp+30h] [rbp-18h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+48h] BYREF

  v19 = 0;
  Binding = 0;
  if ( a1 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>((__int64)&hHandle, (__int64)EventW);
    v10 = (MessageParams *)hHandle;
    if ( (unsigned __int64)hHandle + 1 <= 1 )
    {
      LastError = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x90Du, "CreateEvent", LastError);
    }
    if ( RpcServerInqBindingHandle(&Binding) )
    {
      v12 = GetLastError();
      __FatalError(
        "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
        0x914u,
        "RpcServerInqBindingHandle",
        v12);
    }
    v18[0] = (MessageParams *)operator new(0x48u);
    v13 = MessageParams::MessageParams(v18[0]);
    v18[0] = v10;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    v18[0] = (MessageParams *)&v19;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    v18[0] = a1;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    v18[0] = (MessageParams *)a2;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    v18[0] = (MessageParams *)a3;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    v18[0] = a4;
    std::vector<void *>::push_back((char *)v13 + 48, v18);
    std::vector<void *>::_Emplace_one_at_back<void * const &>((char *)v13 + 48, &Binding);
    if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(31, v13) )
    {
      if ( v13 )
        MessageParams::`scalar deleting destructor'(v13, v14);
      WwanLog::Error(
        "Wwan2SapQueryDeviceServiceSupportedCommands",
        0,
        L"Notification dispatcher: Failed to Queue Message");
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
      return 31;
    }
    else
    {
      if ( WaitForSingleObject(v10, 0xFFFFFFFF) )
      {
        v15 = GetLastError();
        __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x92Au, "WaitForSingleObject", v15);
      }
      tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hHandle);
      return v19;
    }
  }
  else
  {
    WwanLog::Error("Wwan2SapQueryDeviceServiceSupportedCommands", 0, L"[%p] Invalid parameters", 0);
    return 87;
  }
}

```

## disassembly

```asm
0x1800afee0  push    rbp
0x1800afee2  push    rbx
0x1800afee3  push    rsi
0x1800afee4  push    rdi
0x1800afee5  push    r12
0x1800afee7  push    r13
0x1800afee9  push    r14
0x1800afeeb  push    r15
0x1800afeed  mov     rbp, rsp
0x1800afef0  sub     rsp, 48h
0x1800afef4  mov     r15, r9
0x1800afef7  mov     r12, r8
0x1800afefa  mov     r13, rdx
0x1800afefd  mov     r14, rcx
0x1800aff00  mov     [rbp+arg_0], 0
0x1800aff07  mov     [rbp+Binding], 0
0x1800aff0f  xor     r9d, r9d; lpName
0x1800aff12  test    rcx, rcx
0x1800aff15  jnz     short loc_1800AFF35
0x1800aff17  lea     r8, aPInvalidParame; "[%p] Invalid parameters"
0x1800aff1e  xor     edx, edx; struct _GUID *
0x1800aff20  lea     rcx, aWwan2sapqueryd; "Wwan2SapQueryDeviceServiceSupportedComm"...
0x1800aff27  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800aff2c  lea     eax, [r14+57h]
0x1800aff30  jmp     loc_1800B00BD
0x1800aff35  xor     r8d, r8d; bInitialState
0x1800aff38  lea     edx, [r8+1]; bManualReset
0x1800aff3c  xor     ecx, ecx; lpEventAttributes
0x1800aff3e  call    cs:__imp_CreateEventW
0x1800aff44  mov     rdx, rax
0x1800aff47  lea     rcx, [rbp+hHandle]
0x1800aff4b  call    ??$?0U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@$0A@@?$unique_ptr@U_WWAN_SET_LTE_ATTACH@@U?$default_delete@U_WWAN_SET_LTE_ATTACH@@@std@@@std@@QEAA@PEAU_WWAN_SET_LTE_ATTACH@@@Z; std::unique_ptr<_WWAN_SET_LTE_ATTACH>::unique_ptr<_WWAN_SET_LTE_ATTACH>(_WWAN_SET_LTE_ATTACH *)
0x1800aff50  nop
0x1800aff51  mov     rbx, [rbp+hHandle]
0x1800aff55  lea     rax, [rbx+1]
0x1800aff59  cmp     rax, 1
0x1800aff5d  ja      short loc_1800AFF80
0x1800aff5f  call    cs:__imp_GetLastError
0x1800aff65  mov     r9d, eax; unsigned int
0x1800aff68  lea     r8, aCreateevent; "CreateEvent"
0x1800aff6f  mov     edx, 90Dh; unsigned int
0x1800aff74  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800aff7b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800aff80  lea     rcx, [rbp+Binding]; Binding
0x1800aff84  call    cs:__imp_RpcServerInqBindingHandle
0x1800aff8a  test    eax, eax
0x1800aff8c  jz      short loc_1800AFFAF
0x1800aff8e  call    cs:__imp_GetLastError
0x1800aff94  mov     r9d, eax; unsigned int
0x1800aff97  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800aff9e  mov     edx, 914h; unsigned int
0x1800affa3  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800affaa  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800affaf  mov     ecx, 48h ; 'H'; Size
0x1800affb4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800affb9  mov     [rbp+var_18], rax
0x1800affbd  mov     rcx, rax; this
0x1800affc0  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800affc5  mov     rsi, rax
0x1800affc8  lea     rdi, [rax+30h]
0x1800affcc  mov     [rbp+var_18], rbx
0x1800affd0  lea     rdx, [rbp+var_18]
0x1800affd4  mov     rcx, rdi
0x1800affd7  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800affdc  lea     rax, [rbp+arg_0]
0x1800affe0  mov     [rbp+var_18], rax
0x1800affe4  lea     rdx, [rbp+var_18]
0x1800affe8  mov     rcx, rdi
0x1800affeb  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800afff0  mov     [rbp+var_18], r14
0x1800afff4  lea     rdx, [rbp+var_18]
0x1800afff8  mov     rcx, rdi
0x1800afffb  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0000  mov     [rbp+var_18], r13
0x1800b0004  lea     rdx, [rbp+var_18]
0x1800b0008  mov     rcx, rdi
0x1800b000b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0010  mov     [rbp+var_18], r12
0x1800b0014  lea     rdx, [rbp+var_18]
0x1800b0018  mov     rcx, rdi
0x1800b001b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0020  mov     [rbp+var_18], r15
0x1800b0024  lea     rdx, [rbp+var_18]
0x1800b0028  mov     rcx, rdi
0x1800b002b  call    ?push_back@?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAAX$$QEAPEAX@Z; std::vector<void *>::push_back(void * &&)
0x1800b0030  lea     rdx, [rbp+Binding]
0x1800b0034  mov     rcx, rdi
0x1800b0037  call    ??$_Emplace_one_at_back@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAAEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_one_at_back<void * const &>(void * const &)
0x1800b003c  mov     rdx, rsi
0x1800b003f  mov     edi, 1Fh
0x1800b0044  mov     ecx, edi
0x1800b0046  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b004b  test    eax, eax
0x1800b004d  jz      short loc_1800B007F
0x1800b004f  test    rsi, rsi
0x1800b0052  jz      short loc_1800B005C
0x1800b0054  mov     rcx, rsi; this
0x1800b0057  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b005c  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b0063  xor     edx, edx; struct _GUID *
0x1800b0065  lea     rcx, aWwan2sapqueryd; "Wwan2SapQueryDeviceServiceSupportedComm"...
0x1800b006c  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0071  nop
0x1800b0072  lea     rcx, [rbp+hHandle]
0x1800b0076  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b007b  mov     eax, edi
0x1800b007d  jmp     short loc_1800B00BD
0x1800b007f  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0082  mov     rcx, rbx; hHandle
0x1800b0085  call    cs:__imp_WaitForSingleObject
0x1800b008b  test    eax, eax
0x1800b008d  jz      short loc_1800B00B1
0x1800b008f  call    cs:__imp_GetLastError
0x1800b0095  mov     r9d, eax; unsigned int
0x1800b0098  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b009f  mov     edx, 92Ah; unsigned int
0x1800b00a4  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b00ab  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b00b0  nop
0x1800b00b1  lea     rcx, [rbp+hHandle]
0x1800b00b5  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b00ba  mov     eax, [rbp+arg_0]
0x1800b00bd  add     rsp, 48h
0x1800b00c1  pop     r15
0x1800b00c3  pop     r14
0x1800b00c5  pop     r13
0x1800b00c7  pop     r12
0x1800b00c9  pop     rdi
0x1800b00ca  pop     rsi
0x1800b00cb  pop     rbx
0x1800b00cc  pop     rbp
0x1800b00cd  retn
```
