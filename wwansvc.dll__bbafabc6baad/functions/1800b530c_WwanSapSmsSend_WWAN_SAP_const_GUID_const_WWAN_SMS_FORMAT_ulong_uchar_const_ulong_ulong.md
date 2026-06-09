# WwanSapSmsSend(WWAN_SAP const *,_GUID const *,_WWAN_SMS_FORMAT,ulong,uchar const *,ulong *,ulong *)

- ea: `0x1800b530c`
- end: `0x1800b5554`
- name: `?WwanSapSmsSend@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4_WWAN_SMS_FORMAT@@KPEBEPEAK4@Z`
- size: `584`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad8a0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b530c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b550c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b550c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b533e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b533e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5516`

## string_xrefs

- `0x1800b5369`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b552b`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b535d`: `CreateEvent`

## pseudocode

```c
__int64 __fastcall WwanSapSmsSend(
        MessageParams *a1,
        MessageParams *a2,
        unsigned int a3,
        unsigned int a4,
        MessageParams *a5,
        MessageParams *a6,
        MessageParams *a7)
{
  MessageParams *v7; // r12
  MessageParams *v8; // r15
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  char **v15; // rdx
  unsigned int **v16; // rdx
  MessageParams **v17; // rdx
  _QWORD *v18; // rdx
  _QWORD *v19; // rdx
  MessageParams **v20; // rdx
  MessageParams **v21; // rdx
  MessageParams **v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  DWORD v25; // eax
  MessageParams *v27; // [rsp+60h] [rbp+40h] BYREF
  char *v28; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+70h] [rbp+50h] BYREF

  v27 = a1;
  v7 = (MessageParams *)a4;
  v8 = (MessageParams *)a3;
  v29 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x3AEu, "CreateEvent", LastError);
  }
  v27 = (MessageParams *)operator new(0x48u);
  v12 = MessageParams::MessageParams(v27);
  v13 = v12;
  v14 = (char *)v12 + 48;
  v27 = (MessageParams *)EventW;
  v15 = (char **)*((_QWORD *)v12 + 7);
  if ( v15 == *((char ***)v12 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v12 + 48, v15, &v27);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v12 + 7) += 8LL;
  }
  v27 = (MessageParams *)&v29;
  v16 = (unsigned int **)*((_QWORD *)v14 + 1);
  if ( v16 == *((unsigned int ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v16, &v27);
  }
  else
  {
    *v16 = &v29;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a2;
  v17 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v17 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v27);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = v8;
  v18 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v18 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v27);
  }
  else
  {
    *v18 = v8;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = v7;
  v19 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v19 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v19, &v27);
  }
  else
  {
    *v19 = v7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a5;
  v20 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v20 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v20, &v27);
  }
  else
  {
    *v20 = a5;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a6;
  v21 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v21 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v21, &v27);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a7;
  v22 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v22 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v22, &v27);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(11, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapSmsSend", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x3C5u, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b530c  mov     [rsp-38h+arg_0], rcx
0x1800b5311  push    rbp
0x1800b5312  push    rbx
0x1800b5313  push    rsi
0x1800b5314  push    rdi
0x1800b5315  push    r12
0x1800b5317  push    r14
0x1800b5319  push    r15
0x1800b531b  mov     rbp, rsp
0x1800b531e  sub     rsp, 20h
0x1800b5322  mov     r12d, r9d
0x1800b5325  mov     r15d, r8d
0x1800b5328  mov     r14, rdx
0x1800b532b  mov     [rbp+arg_10], 0
0x1800b5332  xor     r9d, r9d; lpName
0x1800b5335  xor     r8d, r8d; bInitialState
0x1800b5338  lea     edx, [r9+1]; bManualReset
0x1800b533c  xor     ecx, ecx; lpEventAttributes
0x1800b533e  call    cs:__imp_CreateEventW
0x1800b5344  mov     rbx, rax
0x1800b5347  mov     [rbp+arg_8], rax
0x1800b534b  inc     rax
0x1800b534e  cmp     rax, 1
0x1800b5352  ja      short loc_1800B5375
0x1800b5354  call    cs:__imp_GetLastError
0x1800b535a  mov     r9d, eax; unsigned int
0x1800b535d  lea     r8, aCreateevent; "CreateEvent"
0x1800b5364  mov     edx, 3AEh; unsigned int
0x1800b5369  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5370  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5375  mov     ecx, 48h ; 'H'; Size
0x1800b537a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b537f  mov     [rbp+arg_0], rax
0x1800b5383  mov     rcx, rax; this
0x1800b5386  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b538b  mov     rsi, rax
0x1800b538e  lea     rdi, [rax+30h]
0x1800b5392  mov     [rbp+arg_0], rbx
0x1800b5396  mov     rdx, [rdi+8]
0x1800b539a  cmp     rdx, [rdi+10h]
0x1800b539e  jz      short loc_1800B53AA
0x1800b53a0  mov     [rdx], rbx
0x1800b53a3  add     qword ptr [rdi+8], 8
0x1800b53a8  jmp     short loc_1800B53B6
0x1800b53aa  lea     r8, [rbp+arg_0]
0x1800b53ae  mov     rcx, rdi
0x1800b53b1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b53b6  lea     rax, [rbp+arg_10]
0x1800b53ba  mov     [rbp+arg_0], rax
0x1800b53be  mov     rdx, [rdi+8]
0x1800b53c2  cmp     rdx, [rdi+10h]
0x1800b53c6  jz      short loc_1800B53D6
0x1800b53c8  lea     rax, [rbp+arg_10]
0x1800b53cc  mov     [rdx], rax
0x1800b53cf  add     qword ptr [rdi+8], 8
0x1800b53d4  jmp     short loc_1800B53E2
0x1800b53d6  lea     r8, [rbp+arg_0]
0x1800b53da  mov     rcx, rdi
0x1800b53dd  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b53e2  mov     [rbp+arg_0], r14
0x1800b53e6  mov     rdx, [rdi+8]
0x1800b53ea  cmp     rdx, [rdi+10h]
0x1800b53ee  jz      short loc_1800B53FA
0x1800b53f0  mov     [rdx], r14
0x1800b53f3  add     qword ptr [rdi+8], 8
0x1800b53f8  jmp     short loc_1800B5406
0x1800b53fa  lea     r8, [rbp+arg_0]
0x1800b53fe  mov     rcx, rdi
0x1800b5401  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5406  mov     rax, r15
0x1800b5409  mov     [rbp+arg_0], rax
0x1800b540d  mov     rdx, [rdi+8]
0x1800b5411  cmp     rdx, [rdi+10h]
0x1800b5415  jz      short loc_1800B5421
0x1800b5417  mov     [rdx], rax
0x1800b541a  add     qword ptr [rdi+8], 8
0x1800b541f  jmp     short loc_1800B542D
0x1800b5421  lea     r8, [rbp+arg_0]
0x1800b5425  mov     rcx, rdi
0x1800b5428  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b542d  mov     rax, r12
0x1800b5430  mov     [rbp+arg_0], rax
0x1800b5434  mov     rdx, [rdi+8]
0x1800b5438  cmp     rdx, [rdi+10h]
0x1800b543c  jz      short loc_1800B5448
0x1800b543e  mov     [rdx], rax
0x1800b5441  add     qword ptr [rdi+8], 8
0x1800b5446  jmp     short loc_1800B5454
0x1800b5448  lea     r8, [rbp+arg_0]
0x1800b544c  mov     rcx, rdi
0x1800b544f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b5454  mov     rax, [rbp+arg_20]
0x1800b5458  mov     [rbp+arg_0], rax
0x1800b545c  mov     rdx, [rdi+8]
0x1800b5460  cmp     rdx, [rdi+10h]
0x1800b5464  jz      short loc_1800B5470
0x1800b5466  mov     [rdx], rax
0x1800b5469  add     qword ptr [rdi+8], 8
0x1800b546e  jmp     short loc_1800B547C
0x1800b5470  lea     r8, [rbp+arg_0]
0x1800b5474  mov     rcx, rdi
0x1800b5477  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b547c  mov     rax, [rbp+arg_28]
0x1800b5480  mov     [rbp+arg_0], rax
0x1800b5484  mov     rdx, [rdi+8]
0x1800b5488  cmp     rdx, [rdi+10h]
0x1800b548c  jz      short loc_1800B5498
0x1800b548e  mov     [rdx], rax
0x1800b5491  add     qword ptr [rdi+8], 8
0x1800b5496  jmp     short loc_1800B54A4
0x1800b5498  lea     r8, [rbp+arg_0]
0x1800b549c  mov     rcx, rdi
0x1800b549f  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b54a4  mov     rax, [rbp+arg_30]
0x1800b54a8  mov     [rbp+arg_0], rax
0x1800b54ac  mov     rdx, [rdi+8]
0x1800b54b0  cmp     rdx, [rdi+10h]
0x1800b54b4  jz      short loc_1800B54C0
0x1800b54b6  mov     [rdx], rax
0x1800b54b9  add     qword ptr [rdi+8], 8
0x1800b54be  jmp     short loc_1800B54CC
0x1800b54c0  lea     r8, [rbp+arg_0]
0x1800b54c4  mov     rcx, rdi
0x1800b54c7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b54cc  mov     rdx, rsi
0x1800b54cf  mov     ecx, 0Bh
0x1800b54d4  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b54d9  test    eax, eax
0x1800b54db  jz      short loc_1800B5506
0x1800b54dd  test    rsi, rsi
0x1800b54e0  jz      short loc_1800B54EA
0x1800b54e2  mov     rcx, rsi; this
0x1800b54e5  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b54ea  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b54f1  xor     edx, edx; struct _GUID *
0x1800b54f3  lea     rcx, aWwansapsmssend; "WwanSapSmsSend"
0x1800b54fa  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b54ff  mov     ebx, 1Fh
0x1800b5504  jmp     short loc_1800B553A
0x1800b5506  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b5509  mov     rcx, rbx; hHandle
0x1800b550c  call    cs:__imp_WaitForSingleObject
0x1800b5512  test    eax, eax
0x1800b5514  jz      short loc_1800B5537
0x1800b5516  call    cs:__imp_GetLastError
0x1800b551c  mov     r9d, eax; unsigned int
0x1800b551f  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b5526  mov     edx, 3C5h; unsigned int
0x1800b552b  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b5532  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b5537  mov     ebx, [rbp+arg_10]
0x1800b553a  lea     rcx, [rbp+arg_8]
0x1800b553e  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b5543  mov     eax, ebx
0x1800b5545  add     rsp, 20h
0x1800b5549  pop     r15
0x1800b554b  pop     r14
0x1800b554d  pop     r12
0x1800b554f  pop     rdi
0x1800b5550  pop     rsi
0x1800b5551  pop     rbx
0x1800b5552  pop     rbp
0x1800b5553  retn
```
