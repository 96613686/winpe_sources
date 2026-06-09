# WwanSapAuthChallenge(WWAN_SAP const *,_GUID const *,_WWAN_AUTH_METHOD,ulong,uchar const *,ulong *,ulong *)

- ea: `0x1800b0ca4`
- end: `0x1800b0f1a`
- name: `?WwanSapAuthChallenge@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4_WWAN_AUTH_METHOD@@KPEBEPEAK4@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ac4c0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b0ca4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0ecc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b0ecc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0cda`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b0cda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0cf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0ed6`

## string_xrefs

- `0x1800b0d05`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0eeb`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b0cf9`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapAuthChallenge(
        MessageParams *a1,
        MessageParams *a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7)
{
  MessageParams *v7; // r13
  MessageParams *v8; // r12
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v13; // rax
  MessageParams *v14; // rsi
  char *v15; // rdi
  char **v16; // rdx
  unsigned int **v17; // rdx
  MessageParams **v18; // rdx
  MessageParams **v19; // rdx
  _QWORD *v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  _QWORD *v23; // rdx
  _QWORD *v24; // rdx
  unsigned int v25; // edx
  unsigned int v26; // ebx
  DWORD v27; // eax
  MessageParams *v29; // [rsp+60h] [rbp+40h] BYREF
  char *v30; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v31; // [rsp+70h] [rbp+50h] BYREF

  v7 = (MessageParams *)a4;
  v8 = (MessageParams *)a3;
  v31 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v30 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x584u, "CreateEvent", LastError);
  }
  v29 = (MessageParams *)operator new(0x48u);
  v13 = MessageParams::MessageParams(v29);
  v14 = v13;
  v15 = (char *)v13 + 48;
  v29 = (MessageParams *)EventW;
  v16 = (char **)*((_QWORD *)v13 + 7);
  if ( v16 == *((char ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v16, &v29);
  }
  else
  {
    *v16 = EventW;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v29 = (MessageParams *)&v31;
  v17 = (unsigned int **)*((_QWORD *)v15 + 1);
  if ( v17 == *((unsigned int ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v17, &v29);
  }
  else
  {
    *v17 = &v31;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = a1;
  v18 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v18 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v18, &v29);
  }
  else
  {
    *v18 = a1;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = a2;
  v19 = (MessageParams **)*((_QWORD *)v15 + 1);
  if ( v19 == *((MessageParams ***)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v19, &v29);
  }
  else
  {
    *v19 = a2;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = v8;
  v20 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v20 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v20, &v29);
  }
  else
  {
    *v20 = v8;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v29 = v7;
  v21 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v21 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v21, &v29);
  }
  else
  {
    *v21 = v7;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  v22 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v22 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v22, &a5);
  }
  else
  {
    *v22 = a5;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  a5 = a6;
  v23 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v23 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v23, &a5);
  }
  else
  {
    *v23 = a6;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  a5 = a7;
  v24 = (_QWORD *)*((_QWORD *)v15 + 1);
  if ( v24 == *((_QWORD **)v15 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v15, v24, &a5);
  }
  else
  {
    *v24 = a7;
    *((_QWORD *)v15 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(23, v14) )
  {
    if ( v14 )
      MessageParams::`scalar deleting destructor'(v14, v25);
    WwanLog::Error("WwanSapAuthChallenge", 0, L"Notification dispatcher: Failed to Queue Message");
    v26 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v27 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x59Cu, "WaitForSingleObject", v27);
    }
    v26 = v31;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v30);
  return v26;
}

```

## disassembly

```asm
0x1800b0ca4  mov     [rsp-38h+arg_18], rbx
0x1800b0ca9  push    rbp
0x1800b0caa  push    rsi
0x1800b0cab  push    rdi
0x1800b0cac  push    r12
0x1800b0cae  push    r13
0x1800b0cb0  push    r14
0x1800b0cb2  push    r15
0x1800b0cb4  mov     rbp, rsp
0x1800b0cb7  sub     rsp, 20h
0x1800b0cbb  mov     r13d, r9d
0x1800b0cbe  mov     r12d, r8d
0x1800b0cc1  mov     r15, rdx
0x1800b0cc4  mov     r14, rcx
0x1800b0cc7  mov     [rbp+arg_10], 0
0x1800b0cce  xor     r9d, r9d; lpName
0x1800b0cd1  xor     r8d, r8d; bInitialState
0x1800b0cd4  lea     edx, [r9+1]; bManualReset
0x1800b0cd8  xor     ecx, ecx; lpEventAttributes
0x1800b0cda  call    cs:__imp_CreateEventW
0x1800b0ce0  mov     rbx, rax
0x1800b0ce3  mov     [rbp+arg_8], rax
0x1800b0ce7  inc     rax
0x1800b0cea  cmp     rax, 1
0x1800b0cee  ja      short loc_1800B0D11
0x1800b0cf0  call    cs:__imp_GetLastError
0x1800b0cf6  mov     r9d, eax; unsigned int
0x1800b0cf9  lea     r8, aCreateevent; "CreateEvent"
0x1800b0d00  mov     edx, 584h; unsigned int
0x1800b0d05  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0d0c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0d11  mov     ecx, 48h ; 'H'; Size
0x1800b0d16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0d1b  mov     [rbp+arg_0], rax
0x1800b0d1f  mov     rcx, rax; this
0x1800b0d22  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b0d27  mov     rsi, rax
0x1800b0d2a  lea     rdi, [rax+30h]
0x1800b0d2e  mov     [rbp+arg_0], rbx
0x1800b0d32  mov     rdx, [rdi+8]
0x1800b0d36  cmp     rdx, [rdi+10h]
0x1800b0d3a  jz      short loc_1800B0D46
0x1800b0d3c  mov     [rdx], rbx
0x1800b0d3f  add     qword ptr [rdi+8], 8
0x1800b0d44  jmp     short loc_1800B0D52
0x1800b0d46  lea     r8, [rbp+arg_0]
0x1800b0d4a  mov     rcx, rdi
0x1800b0d4d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0d52  lea     rax, [rbp+arg_10]
0x1800b0d56  mov     [rbp+arg_0], rax
0x1800b0d5a  mov     rdx, [rdi+8]
0x1800b0d5e  cmp     rdx, [rdi+10h]
0x1800b0d62  jz      short loc_1800B0D72
0x1800b0d64  lea     rax, [rbp+arg_10]
0x1800b0d68  mov     [rdx], rax
0x1800b0d6b  add     qword ptr [rdi+8], 8
0x1800b0d70  jmp     short loc_1800B0D7E
0x1800b0d72  lea     r8, [rbp+arg_0]
0x1800b0d76  mov     rcx, rdi
0x1800b0d79  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0d7e  mov     [rbp+arg_0], r14
0x1800b0d82  mov     rdx, [rdi+8]
0x1800b0d86  cmp     rdx, [rdi+10h]
0x1800b0d8a  jz      short loc_1800B0D96
0x1800b0d8c  mov     [rdx], r14
0x1800b0d8f  add     qword ptr [rdi+8], 8
0x1800b0d94  jmp     short loc_1800B0DA2
0x1800b0d96  lea     r8, [rbp+arg_0]
0x1800b0d9a  mov     rcx, rdi
0x1800b0d9d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0da2  mov     [rbp+arg_0], r15
0x1800b0da6  mov     rdx, [rdi+8]
0x1800b0daa  cmp     rdx, [rdi+10h]
0x1800b0dae  jz      short loc_1800B0DBA
0x1800b0db0  mov     [rdx], r15
0x1800b0db3  add     qword ptr [rdi+8], 8
0x1800b0db8  jmp     short loc_1800B0DC6
0x1800b0dba  lea     r8, [rbp+arg_0]
0x1800b0dbe  mov     rcx, rdi
0x1800b0dc1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0dc6  mov     rax, r12
0x1800b0dc9  mov     [rbp+arg_0], rax
0x1800b0dcd  mov     rdx, [rdi+8]
0x1800b0dd1  cmp     rdx, [rdi+10h]
0x1800b0dd5  jz      short loc_1800B0DE1
0x1800b0dd7  mov     [rdx], rax
0x1800b0dda  add     qword ptr [rdi+8], 8
0x1800b0ddf  jmp     short loc_1800B0DED
0x1800b0de1  lea     r8, [rbp+arg_0]
0x1800b0de5  mov     rcx, rdi
0x1800b0de8  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0ded  mov     rax, r13
0x1800b0df0  mov     [rbp+arg_0], rax
0x1800b0df4  mov     rdx, [rdi+8]
0x1800b0df8  cmp     rdx, [rdi+10h]
0x1800b0dfc  jz      short loc_1800B0E08
0x1800b0dfe  mov     [rdx], rax
0x1800b0e01  add     qword ptr [rdi+8], 8
0x1800b0e06  jmp     short loc_1800B0E14
0x1800b0e08  lea     r8, [rbp+arg_0]
0x1800b0e0c  mov     rcx, rdi
0x1800b0e0f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0e14  mov     rax, [rbp+arg_20]
0x1800b0e18  mov     [rbp+arg_20], rax
0x1800b0e1c  mov     rdx, [rdi+8]
0x1800b0e20  cmp     rdx, [rdi+10h]
0x1800b0e24  jz      short loc_1800B0E30
0x1800b0e26  mov     [rdx], rax
0x1800b0e29  add     qword ptr [rdi+8], 8
0x1800b0e2e  jmp     short loc_1800B0E3C
0x1800b0e30  lea     r8, [rbp+arg_20]
0x1800b0e34  mov     rcx, rdi
0x1800b0e37  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0e3c  mov     rax, [rbp+arg_28]
0x1800b0e40  mov     [rbp+arg_20], rax
0x1800b0e44  mov     rdx, [rdi+8]
0x1800b0e48  cmp     rdx, [rdi+10h]
0x1800b0e4c  jz      short loc_1800B0E58
0x1800b0e4e  mov     [rdx], rax
0x1800b0e51  add     qword ptr [rdi+8], 8
0x1800b0e56  jmp     short loc_1800B0E64
0x1800b0e58  lea     r8, [rbp+arg_20]
0x1800b0e5c  mov     rcx, rdi
0x1800b0e5f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0e64  mov     rax, [rbp+arg_30]
0x1800b0e68  mov     [rbp+arg_20], rax
0x1800b0e6c  mov     rdx, [rdi+8]
0x1800b0e70  cmp     rdx, [rdi+10h]
0x1800b0e74  jz      short loc_1800B0E80
0x1800b0e76  mov     [rdx], rax
0x1800b0e79  add     qword ptr [rdi+8], 8
0x1800b0e7e  jmp     short loc_1800B0E8C
0x1800b0e80  lea     r8, [rbp+arg_20]
0x1800b0e84  mov     rcx, rdi
0x1800b0e87  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b0e8c  mov     rdx, rsi
0x1800b0e8f  mov     ecx, 17h
0x1800b0e94  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b0e99  test    eax, eax
0x1800b0e9b  jz      short loc_1800B0EC6
0x1800b0e9d  test    rsi, rsi
0x1800b0ea0  jz      short loc_1800B0EAA
0x1800b0ea2  mov     rcx, rsi; this
0x1800b0ea5  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b0eaa  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b0eb1  xor     edx, edx; struct _GUID *
0x1800b0eb3  lea     rcx, aWwansapauthcha; "WwanSapAuthChallenge"
0x1800b0eba  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b0ebf  mov     ebx, 1Fh
0x1800b0ec4  jmp     short loc_1800B0EFA
0x1800b0ec6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b0ec9  mov     rcx, rbx; hHandle
0x1800b0ecc  call    cs:__imp_WaitForSingleObject
0x1800b0ed2  test    eax, eax
0x1800b0ed4  jz      short loc_1800B0EF7
0x1800b0ed6  call    cs:__imp_GetLastError
0x1800b0edc  mov     r9d, eax; unsigned int
0x1800b0edf  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b0ee6  mov     edx, 59Ch; unsigned int
0x1800b0eeb  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b0ef2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b0ef7  mov     ebx, [rbp+arg_10]
0x1800b0efa  lea     rcx, [rbp+arg_8]
0x1800b0efe  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b0f03  mov     eax, ebx
0x1800b0f05  mov     rbx, [rsp+20h+arg_18]
0x1800b0f0a  add     rsp, 20h
0x1800b0f0e  pop     r15
0x1800b0f10  pop     r14
0x1800b0f12  pop     r13
0x1800b0f14  pop     r12
0x1800b0f16  pop     rdi
0x1800b0f17  pop     rsi
0x1800b0f18  pop     rbp
0x1800b0f19  retn
```
