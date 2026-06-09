# WwanSapUiccSendApdu(WWAN_SAP const *,_GUID const *,ulong,_WWAN_UICC_SECURE_MESSAGING,_WWAN_UICC_CLASS_BYTE_TYPE,ulong,uchar const *,ulong,ulong *)

- ea: `0x1800b5a78`
- end: `0x1800b5d10`
- name: `?WwanSapUiccSendApdu@@YAKPEBUWWAN_SAP@@PEBU_GUID@@KW4_WWAN_UICC_SECURE_MESSAGING@@W4_WWAN_UICC_CLASS_BYTE_TYPE@@KPEBEKPEAK@Z`
- size: `664`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad9c0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b5a78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5cc8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b5cc8`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5aaa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b5aaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5cd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5ac0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5cd2`

## string_xrefs

- `0x1800b5ad5`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5ce7`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b5ac9`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapUiccSendApdu(
        MessageParams *a1,
        MessageParams *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        MessageParams *a7,
        unsigned int a8,
        MessageParams *a9)
{
  unsigned __int64 v9; // r12
  unsigned __int64 v10; // r15
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v14; // rax
  MessageParams *v15; // rsi
  char *v16; // rdi
  char **v17; // rdx
  unsigned int **v18; // rdx
  MessageParams **v19; // rdx
  unsigned __int64 *v20; // rdx
  unsigned __int64 *v21; // rdx
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  MessageParams **v24; // rdx
  _QWORD *v25; // rdx
  MessageParams **v26; // rdx
  unsigned int v27; // edx
  unsigned int v28; // ebx
  DWORD v29; // eax
  unsigned __int64 v31; // [rsp+60h] [rbp+40h] BYREF
  char *v32; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v33; // [rsp+70h] [rbp+50h] BYREF

  v31 = (unsigned __int64)a1;
  v9 = a4;
  v10 = a3;
  v33 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v32 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xBB5u, "CreateEvent", LastError);
  }
  v31 = (unsigned __int64)operator new(0x48u);
  v14 = MessageParams::MessageParams((MessageParams *)v31);
  v15 = v14;
  v16 = (char *)v14 + 48;
  v31 = (unsigned __int64)EventW;
  v17 = (char **)*((_QWORD *)v14 + 7);
  if ( v17 == *((char ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v17, &v31);
  }
  else
  {
    *v17 = EventW;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v31 = (unsigned __int64)&v33;
  v18 = (unsigned int **)*((_QWORD *)v16 + 1);
  if ( v18 == *((unsigned int ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v18, &v31);
  }
  else
  {
    *v18 = &v33;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = (unsigned __int64)a2;
  v19 = (MessageParams **)*((_QWORD *)v16 + 1);
  if ( v19 == *((MessageParams ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v19, &v31);
  }
  else
  {
    *v19 = a2;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = v10;
  v20 = (unsigned __int64 *)*((_QWORD *)v16 + 1);
  if ( v20 == *((unsigned __int64 **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v20, &v31);
  }
  else
  {
    *v20 = v10;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = v9;
  v21 = (unsigned __int64 *)*((_QWORD *)v16 + 1);
  if ( v21 == *((unsigned __int64 **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v21, &v31);
  }
  else
  {
    *v21 = v9;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = a5;
  v22 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v22 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v22, &v31);
  }
  else
  {
    *v22 = a5;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = a6;
  v23 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v23 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v23, &v31);
  }
  else
  {
    *v23 = a6;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = (unsigned __int64)a7;
  v24 = (MessageParams **)*((_QWORD *)v16 + 1);
  if ( v24 == *((MessageParams ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v24, &v31);
  }
  else
  {
    *v24 = a7;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = a8;
  v25 = (_QWORD *)*((_QWORD *)v16 + 1);
  if ( v25 == *((_QWORD **)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v25, &v31);
  }
  else
  {
    *v25 = a8;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  v31 = (unsigned __int64)a9;
  v26 = (MessageParams **)*((_QWORD *)v16 + 1);
  if ( v26 == *((MessageParams ***)v16 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v16, v26, &v31);
  }
  else
  {
    *v26 = a9;
    *((_QWORD *)v16 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(47, v15) )
  {
    if ( v15 )
      MessageParams::`scalar deleting destructor'(v15, v27);
    WwanLog::Error("WwanSapUiccSendApdu", 0, L"Notification dispatcher: Failed to Queue Message");
    v28 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v29 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xBCEu, "WaitForSingleObject", v29);
    }
    v28 = v33;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v32);
  return v28;
}

```

## disassembly

```asm
0x1800b5a78  mov     [rsp-38h+arg_0], rcx
0x1800b5a7d  push    rbp
0x1800b5a7e  push    rbx
0x1800b5a7f  push    rsi
0x1800b5a80  push    rdi
0x1800b5a81  push    r12
0x1800b5a83  push    r14
0x1800b5a85  push    r15
0x1800b5a87  mov     rbp, rsp
0x1800b5a8a  sub     rsp, 20h
0x1800b5a8e  mov     r12d, r9d
0x1800b5a91  mov     r15d, r8d
0x1800b5a94  mov     r14, rdx
0x1800b5a97  mov     [rbp+arg_10], 0
0x1800b5a9e  xor     r9d, r9d; lpName
0x1800b5aa1  xor     r8d, r8d; bInitialState
0x1800b5aa4  lea     edx, [r9+1]; bManualReset
0x1800b5aa8  xor     ecx, ecx; lpEventAttributes
0x1800b5aaa  call    cs:__imp_CreateEventW
0x1800b5ab0  mov     rbx, rax
0x1800b5ab3  mov     [rbp+arg_8], rax
0x1800b5ab7  inc     rax
0x1800b5aba  cmp     rax, 1
0x1800b5abe  ja      short loc_1800B5AE1
0x1800b5ac0  call    cs:__imp_GetLastError
0x1800b5ac6  mov     r9d, eax; unsigned int
0x1800b5ac9  lea     r8, aCreateevent; "CreateEvent"
0x1800b5ad0  mov     edx, 0BB5h; unsigned int
0x1800b5ad5  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5adc  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5ae1  mov     ecx, 48h ; 'H'; Size
0x1800b5ae6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b5aeb  mov     [rbp+arg_0], rax
0x1800b5aef  mov     rcx, rax; this
0x1800b5af2  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b5af7  mov     rsi, rax
0x1800b5afa  lea     rdi, [rax+30h]
0x1800b5afe  mov     [rbp+arg_0], rbx
0x1800b5b02  mov     rdx, [rdi+8]
0x1800b5b06  cmp     rdx, [rdi+10h]
0x1800b5b0a  jz      short loc_1800B5B16
0x1800b5b0c  mov     [rdx], rbx
0x1800b5b0f  add     qword ptr [rdi+8], 8
0x1800b5b14  jmp     short loc_1800B5B22
0x1800b5b16  lea     r8, [rbp+arg_0]
0x1800b5b1a  mov     rcx, rdi
0x1800b5b1d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5b22  lea     rax, [rbp+arg_10]
0x1800b5b26  mov     [rbp+arg_0], rax
0x1800b5b2a  mov     rdx, [rdi+8]
0x1800b5b2e  cmp     rdx, [rdi+10h]
0x1800b5b32  jz      short loc_1800B5B42
0x1800b5b34  lea     rax, [rbp+arg_10]
0x1800b5b38  mov     [rdx], rax
0x1800b5b3b  add     qword ptr [rdi+8], 8
0x1800b5b40  jmp     short loc_1800B5B4E
0x1800b5b42  lea     r8, [rbp+arg_0]
0x1800b5b46  mov     rcx, rdi
0x1800b5b49  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5b4e  mov     [rbp+arg_0], r14
0x1800b5b52  mov     rdx, [rdi+8]
0x1800b5b56  cmp     rdx, [rdi+10h]
0x1800b5b5a  jz      short loc_1800B5B66
0x1800b5b5c  mov     [rdx], r14
0x1800b5b5f  add     qword ptr [rdi+8], 8
0x1800b5b64  jmp     short loc_1800B5B72
0x1800b5b66  lea     r8, [rbp+arg_0]
0x1800b5b6a  mov     rcx, rdi
0x1800b5b6d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5b72  mov     rax, r15
0x1800b5b75  mov     [rbp+arg_0], rax
0x1800b5b79  mov     rdx, [rdi+8]
0x1800b5b7d  cmp     rdx, [rdi+10h]
0x1800b5b81  jz      short loc_1800B5B8D
0x1800b5b83  mov     [rdx], rax
0x1800b5b86  add     qword ptr [rdi+8], 8
0x1800b5b8b  jmp     short loc_1800B5B99
0x1800b5b8d  lea     r8, [rbp+arg_0]
0x1800b5b91  mov     rcx, rdi
0x1800b5b94  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5b99  mov     rax, r12
0x1800b5b9c  mov     [rbp+arg_0], rax
0x1800b5ba0  mov     rdx, [rdi+8]
0x1800b5ba4  cmp     rdx, [rdi+10h]
0x1800b5ba8  jz      short loc_1800B5BB4
0x1800b5baa  mov     [rdx], rax
0x1800b5bad  add     qword ptr [rdi+8], 8
0x1800b5bb2  jmp     short loc_1800B5BC0
0x1800b5bb4  lea     r8, [rbp+arg_0]
0x1800b5bb8  mov     rcx, rdi
0x1800b5bbb  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5bc0  mov     eax, [rbp+arg_20]
0x1800b5bc3  mov     [rbp+arg_0], rax
0x1800b5bc7  mov     rdx, [rdi+8]
0x1800b5bcb  cmp     rdx, [rdi+10h]
0x1800b5bcf  jz      short loc_1800B5BDB
0x1800b5bd1  mov     [rdx], rax
0x1800b5bd4  add     qword ptr [rdi+8], 8
0x1800b5bd9  jmp     short loc_1800B5BE7
0x1800b5bdb  lea     r8, [rbp+arg_0]
0x1800b5bdf  mov     rcx, rdi
0x1800b5be2  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5be7  mov     eax, [rbp+arg_28]
0x1800b5bea  mov     [rbp+arg_0], rax
0x1800b5bee  mov     rdx, [rdi+8]
0x1800b5bf2  cmp     rdx, [rdi+10h]
0x1800b5bf6  jz      short loc_1800B5C02
0x1800b5bf8  mov     [rdx], rax
0x1800b5bfb  add     qword ptr [rdi+8], 8
0x1800b5c00  jmp     short loc_1800B5C0E
0x1800b5c02  lea     r8, [rbp+arg_0]
0x1800b5c06  mov     rcx, rdi
0x1800b5c09  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5c0e  mov     rax, [rbp+arg_30]
0x1800b5c12  mov     [rbp+arg_0], rax
0x1800b5c16  mov     rdx, [rdi+8]
0x1800b5c1a  cmp     rdx, [rdi+10h]
0x1800b5c1e  jz      short loc_1800B5C2A
0x1800b5c20  mov     [rdx], rax
0x1800b5c23  add     qword ptr [rdi+8], 8
0x1800b5c28  jmp     short loc_1800B5C36
0x1800b5c2a  lea     r8, [rbp+arg_0]
0x1800b5c2e  mov     rcx, rdi
0x1800b5c31  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5c36  mov     eax, [rbp+arg_38]
0x1800b5c39  mov     [rbp+arg_0], rax
0x1800b5c3d  mov     rdx, [rdi+8]
0x1800b5c41  cmp     rdx, [rdi+10h]
0x1800b5c45  jz      short loc_1800B5C51
0x1800b5c47  mov     [rdx], rax
0x1800b5c4a  add     qword ptr [rdi+8], 8
0x1800b5c4f  jmp     short loc_1800B5C5D
0x1800b5c51  lea     r8, [rbp+arg_0]
0x1800b5c55  mov     rcx, rdi
0x1800b5c58  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5c5d  mov     rax, [rbp+arg_40]
0x1800b5c64  mov     [rbp+arg_0], rax
0x1800b5c68  mov     rdx, [rdi+8]
0x1800b5c6c  cmp     rdx, [rdi+10h]
0x1800b5c70  jz      short loc_1800B5C7C
0x1800b5c72  mov     [rdx], rax
0x1800b5c75  add     qword ptr [rdi+8], 8
0x1800b5c7a  jmp     short loc_1800B5C88
0x1800b5c7c  lea     r8, [rbp+arg_0]
0x1800b5c80  mov     rcx, rdi
0x1800b5c83  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5c88  mov     rdx, rsi
0x1800b5c8b  mov     ecx, 2Fh ; '/'
0x1800b5c90  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b5c95  test    eax, eax
0x1800b5c97  jz      short loc_1800B5CC2
0x1800b5c99  test    rsi, rsi
0x1800b5c9c  jz      short loc_1800B5CA6
0x1800b5c9e  mov     rcx, rsi; this
0x1800b5ca1  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b5ca6  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b5cad  xor     edx, edx; struct _GUID *
0x1800b5caf  lea     rcx, aWwansapuiccsen; "WwanSapUiccSendApdu"
0x1800b5cb6  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b5cbb  mov     ebx, 1Fh
0x1800b5cc0  jmp     short loc_1800B5CF6
0x1800b5cc2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5cc5  mov     rcx, rbx; hHandle
0x1800b5cc8  call    cs:__imp_WaitForSingleObject
0x1800b5cce  test    eax, eax
0x1800b5cd0  jz      short loc_1800B5CF3
0x1800b5cd2  call    cs:__imp_GetLastError
0x1800b5cd8  mov     r9d, eax; unsigned int
0x1800b5cdb  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b5ce2  mov     edx, 0BCEh; unsigned int
0x1800b5ce7  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5cee  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5cf3  mov     ebx, [rbp+arg_10]
0x1800b5cf6  lea     rcx, [rbp+arg_8]
0x1800b5cfa  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b5cff  mov     eax, ebx
0x1800b5d01  add     rsp, 20h
0x1800b5d05  pop     r15
0x1800b5d07  pop     r14
0x1800b5d09  pop     r12
0x1800b5d0b  pop     rdi
0x1800b5d0c  pop     rsi
0x1800b5d0d  pop     rbx
0x1800b5d0e  pop     rbp
0x1800b5d0f  retn
```
