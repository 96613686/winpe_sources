# WwanSapSetProfile(WWAN_SAP const *,_GUID const *,ulong,ushort const *,int,ulong *,WWAN_PROFILE_INVALID_REASON *)

- ea: `0x1800b4980`
- end: `0x1800b4c1f`
- name: `?WwanSapSetProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KPEBGHPEAKPEAW4WWAN_PROFILE_INVALID_REASON@@@Z`
- size: `671`
- prototype: `__int64 __fastcall(const struct WWAN_SAP *, const struct _GUID *, unsigned int, MessageParams *, unsigned int, unsigned int *, enum WWAN_PROFILE_INVALID_REASON *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad620`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b4980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4bd7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4bd7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b49ba`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b49ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4be1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b49ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4be1`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b49f5`
- `RPCRT4!RpcServerInqBindingHandle` at `0x1800b49f5`

## string_xrefs

- `0x1800b49e5`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4a14`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4bf6`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b49d9`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WwanSapSetProfile(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        unsigned int a3,
        MessageParams *a4,
        unsigned int a5,
        unsigned int *a6,
        enum WWAN_PROFILE_INVALID_REASON *a7)
{
  MessageParams *v8; // r12
  MessageParams *EventW; // rbx
  DWORD LastError; // eax
  DWORD v12; // eax
  MessageParams *v13; // rax
  MessageParams *v14; // rsi
  char *v15; // rdi
  MessageParams **v16; // rdx
  unsigned int **v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  MessageParams **v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  RPC_BINDING_HANDLE *v24; // rdx
  unsigned int v25; // edx
  unsigned int v26; // ebx
  DWORD v27; // eax
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+40h] BYREF
  MessageParams *v30; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+50h] BYREF
  MessageParams *v32; // [rsp+78h] [rbp+58h] BYREF

  v8 = (MessageParams *)a3;
  v31 = 0;
  Binding = 0;
  EventW = (MessageParams *)CreateEventW(0, 1, 0, 0);
  v32 = EventW;
  if ( EventW == (MessageParams *)-1LL || (MessageParams *)((char *)EventW + 1) == (MessageParams *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x403u, "CreateEvent", LastError);
  }
  if ( RpcServerInqBindingHandle(&Binding) )
  {
    v12 = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x40Au, "RpcServerInqBindingHandle", v12);
  }
  v30 = (MessageParams *)operator new(0x48u);
  v13 = MessageParams::MessageParams(v30);
  v14 = v13;
  v15 = (char *)v13 + 48;
  v30 = EventW;
  v16 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v16 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v16, &v30);
  }
  else
  {
    *v16 = EventW;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v30 = (MessageParams *)&v31;
  v17 = (unsigned int **)*((_QWORD *)v15 + 1);
  if ( v17 == *((unsigned int ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v17, &v30);
  }
  else
  {
    *v17 = &v31;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v30 = (MessageParams *)a2;
  v18 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v18 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v18, &v30);
  }
  else
  {
    *v18 = a2;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v30 = v8;
  v19 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v19 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v19, &v30);
  }
  else
  {
    *v19 = v8;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v30 = a4;
  v20 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v20 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v20, &v30);
  }
  else
  {
    *v20 = a4;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v30 = (MessageParams *)a5;
  v21 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v21 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v21, &v30);
  }
  else
  {
    *v21 = a5;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v22 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v22 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v22, &a6);
  }
  else
  {
    *v22 = a6;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  a6 = (unsigned int *)a7;
  v23 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v23 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v23, &a6);
  }
  else
  {
    *v23 = a7;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v24 = (RPC_BINDING_HANDLE *)*((_QWORD *)v15 + 1);
  if ( v24 == *((RPC_BINDING_HANDLE **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v24, &Binding);
  }
  else
  {
    *v24 = Binding;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(13, v14) )
  {
    if ( v14 )
      MessageParams::`scalar deleting destructor'(v14, v25);
    WwanLog::Error("WwanSapSetProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v26 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v27 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x422u, "WaitForSingleObject", v27);
    }
    v26 = v31;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v32);
  return v26;
}

```

## disassembly

```asm
0x1800b4980  mov     [rsp-38h+Binding], rcx
0x1800b4985  push    rbp
0x1800b4986  push    rbx
0x1800b4987  push    rsi
0x1800b4988  push    rdi
0x1800b4989  push    r12
0x1800b498b  push    r14
0x1800b498d  push    r15
0x1800b498f  mov     rbp, rsp
0x1800b4992  sub     rsp, 20h
0x1800b4996  mov     r15, r9
0x1800b4999  mov     r12d, r8d
0x1800b499c  mov     r14, rdx
0x1800b499f  mov     [rbp+arg_10], 0
0x1800b49a6  mov     [rbp+Binding], 0
0x1800b49ae  xor     r9d, r9d; lpName
0x1800b49b1  xor     r8d, r8d; bInitialState
0x1800b49b4  lea     edx, [r9+1]; bManualReset
0x1800b49b8  xor     ecx, ecx; lpEventAttributes
0x1800b49ba  call    cs:__imp_CreateEventW
0x1800b49c0  mov     rbx, rax
0x1800b49c3  mov     [rbp+arg_18], rax
0x1800b49c7  inc     rax
0x1800b49ca  cmp     rax, 1
0x1800b49ce  ja      short loc_1800B49F1
0x1800b49d0  call    cs:__imp_GetLastError
0x1800b49d6  mov     r9d, eax; unsigned int
0x1800b49d9  lea     r8, aCreateevent; "CreateEvent"
0x1800b49e0  mov     edx, 403h; unsigned int
0x1800b49e5  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b49ec  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b49f1  lea     rcx, [rbp+Binding]; Binding
0x1800b49f5  call    cs:__imp_RpcServerInqBindingHandle
0x1800b49fb  test    eax, eax
0x1800b49fd  jz      short loc_1800B4A20
0x1800b49ff  call    cs:__imp_GetLastError
0x1800b4a05  mov     r9d, eax; unsigned int
0x1800b4a08  lea     r8, aRpcserverinqbi_0; "RpcServerInqBindingHandle"
0x1800b4a0f  mov     edx, 40Ah; unsigned int
0x1800b4a14  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4a1b  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4a20  mov     ecx, 48h ; 'H'; Size
0x1800b4a25  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4a2a  mov     [rbp+arg_8], rax
0x1800b4a2e  mov     rcx, rax; this
0x1800b4a31  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b4a36  mov     rsi, rax
0x1800b4a39  lea     rdi, [rax+30h]
0x1800b4a3d  mov     [rbp+arg_8], rbx
0x1800b4a41  mov     rdx, [rdi+8]
0x1800b4a45  cmp     rdx, [rdi+10h]
0x1800b4a49  jz      short loc_1800B4A55
0x1800b4a4b  mov     [rdx], rbx
0x1800b4a4e  add     qword ptr [rdi+8], 8
0x1800b4a53  jmp     short loc_1800B4A61
0x1800b4a55  lea     r8, [rbp+arg_8]
0x1800b4a59  mov     rcx, rdi
0x1800b4a5c  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4a61  lea     rax, [rbp+arg_10]
0x1800b4a65  mov     [rbp+arg_8], rax
0x1800b4a69  mov     rdx, [rdi+8]
0x1800b4a6d  cmp     rdx, [rdi+10h]
0x1800b4a71  jz      short loc_1800B4A81
0x1800b4a73  lea     rax, [rbp+arg_10]
0x1800b4a77  mov     [rdx], rax
0x1800b4a7a  add     qword ptr [rdi+8], 8
0x1800b4a7f  jmp     short loc_1800B4A8D
0x1800b4a81  lea     r8, [rbp+arg_8]
0x1800b4a85  mov     rcx, rdi
0x1800b4a88  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4a8d  mov     [rbp+arg_8], r14
0x1800b4a91  mov     rdx, [rdi+8]
0x1800b4a95  cmp     rdx, [rdi+10h]
0x1800b4a99  jz      short loc_1800B4AA5
0x1800b4a9b  mov     [rdx], r14
0x1800b4a9e  add     qword ptr [rdi+8], 8
0x1800b4aa3  jmp     short loc_1800B4AB1
0x1800b4aa5  lea     r8, [rbp+arg_8]
0x1800b4aa9  mov     rcx, rdi
0x1800b4aac  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4ab1  mov     rax, r12
0x1800b4ab4  mov     [rbp+arg_8], rax
0x1800b4ab8  mov     rdx, [rdi+8]
0x1800b4abc  cmp     rdx, [rdi+10h]
0x1800b4ac0  jz      short loc_1800B4ACC
0x1800b4ac2  mov     [rdx], rax
0x1800b4ac5  add     qword ptr [rdi+8], 8
0x1800b4aca  jmp     short loc_1800B4AD8
0x1800b4acc  lea     r8, [rbp+arg_8]
0x1800b4ad0  mov     rcx, rdi
0x1800b4ad3  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4ad8  mov     [rbp+arg_8], r15
0x1800b4adc  mov     rdx, [rdi+8]
0x1800b4ae0  cmp     rdx, [rdi+10h]
0x1800b4ae4  jz      short loc_1800B4AF0
0x1800b4ae6  mov     [rdx], r15
0x1800b4ae9  add     qword ptr [rdi+8], 8
0x1800b4aee  jmp     short loc_1800B4AFC
0x1800b4af0  lea     r8, [rbp+arg_8]
0x1800b4af4  mov     rcx, rdi
0x1800b4af7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4afc  mov     eax, [rbp+arg_20]
0x1800b4aff  mov     [rbp+arg_8], rax
0x1800b4b03  mov     rdx, [rdi+8]
0x1800b4b07  cmp     rdx, [rdi+10h]
0x1800b4b0b  jz      short loc_1800B4B17
0x1800b4b0d  mov     [rdx], rax
0x1800b4b10  add     qword ptr [rdi+8], 8
0x1800b4b15  jmp     short loc_1800B4B23
0x1800b4b17  lea     r8, [rbp+arg_8]
0x1800b4b1b  mov     rcx, rdi
0x1800b4b1e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4b23  mov     rax, [rbp+arg_28]
0x1800b4b27  mov     [rbp+arg_28], rax
0x1800b4b2b  mov     rdx, [rdi+8]
0x1800b4b2f  cmp     rdx, [rdi+10h]
0x1800b4b33  jz      short loc_1800B4B3F
0x1800b4b35  mov     [rdx], rax
0x1800b4b38  add     qword ptr [rdi+8], 8
0x1800b4b3d  jmp     short loc_1800B4B4B
0x1800b4b3f  lea     r8, [rbp+arg_28]
0x1800b4b43  mov     rcx, rdi
0x1800b4b46  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4b4b  mov     rax, [rbp+arg_30]
0x1800b4b4f  mov     [rbp+arg_28], rax
0x1800b4b53  mov     rdx, [rdi+8]
0x1800b4b57  cmp     rdx, [rdi+10h]
0x1800b4b5b  jz      short loc_1800B4B67
0x1800b4b5d  mov     [rdx], rax
0x1800b4b60  add     qword ptr [rdi+8], 8
0x1800b4b65  jmp     short loc_1800B4B73
0x1800b4b67  lea     r8, [rbp+arg_28]
0x1800b4b6b  mov     rcx, rdi
0x1800b4b6e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4b73  mov     rdx, [rdi+8]
0x1800b4b77  cmp     rdx, [rdi+10h]
0x1800b4b7b  jz      short loc_1800B4B8B
0x1800b4b7d  mov     rax, [rbp+Binding]
0x1800b4b81  mov     [rdx], rax
0x1800b4b84  add     qword ptr [rdi+8], 8
0x1800b4b89  jmp     short loc_1800B4B97
0x1800b4b8b  lea     r8, [rbp+Binding]
0x1800b4b8f  mov     rcx, rdi
0x1800b4b92  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4b97  mov     rdx, rsi
0x1800b4b9a  mov     ecx, 0Dh
0x1800b4b9f  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b4ba4  test    eax, eax
0x1800b4ba6  jz      short loc_1800B4BD1
0x1800b4ba8  test    rsi, rsi
0x1800b4bab  jz      short loc_1800B4BB5
0x1800b4bad  mov     rcx, rsi; this
0x1800b4bb0  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b4bb5  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b4bbc  xor     edx, edx; struct _GUID *
0x1800b4bbe  lea     rcx, aWwansapsetprof_0; "WwanSapSetProfile"
0x1800b4bc5  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4bca  mov     ebx, 1Fh
0x1800b4bcf  jmp     short loc_1800B4C05
0x1800b4bd1  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b4bd4  mov     rcx, rbx; hHandle
0x1800b4bd7  call    cs:__imp_WaitForSingleObject
0x1800b4bdd  test    eax, eax
0x1800b4bdf  jz      short loc_1800B4C02
0x1800b4be1  call    cs:__imp_GetLastError
0x1800b4be7  mov     r9d, eax; unsigned int
0x1800b4bea  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b4bf1  mov     edx, 422h; unsigned int
0x1800b4bf6  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4bfd  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4c02  mov     ebx, [rbp+arg_10]
0x1800b4c05  lea     rcx, [rbp+arg_18]
0x1800b4c09  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4c0e  mov     eax, ebx
0x1800b4c10  add     rsp, 20h
0x1800b4c14  pop     r15
0x1800b4c16  pop     r14
0x1800b4c18  pop     r12
0x1800b4c1a  pop     rdi
0x1800b4c1b  pop     rsi
0x1800b4c1c  pop     rbx
0x1800b4c1d  pop     rbp
0x1800b4c1e  retn
```
