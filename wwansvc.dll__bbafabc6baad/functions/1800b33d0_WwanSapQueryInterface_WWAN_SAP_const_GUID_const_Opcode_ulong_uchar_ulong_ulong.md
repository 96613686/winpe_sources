# WwanSapQueryInterface(WWAN_SAP const *,_GUID const *,Opcode,ulong *,uchar * *,ulong *,ulong *)

- ea: `0x1800b33d0`
- end: `0x1800b367b`
- name: `?WwanSapQueryInterface@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4Opcode@@PEAKPEAPEAE33@Z`
- size: `683`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800ad1e0`

## callees

- `0x180008abc`
- `0x180008b00`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b33d0`
- `0x1800b6264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b362b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b362b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b340a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b340a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3420`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3635`

## string_xrefs

- `0x1800b3435`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b364a`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b3429`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WwanSapQueryInterface(
        __int64 a1,
        MessageParams *a2,
        int a3,
        MessageParams *a4,
        MessageParams *a5,
        MessageParams *a6,
        MessageParams *a7)
{
  MessageParams *v8; // r12
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  unsigned int v14; // ebx
  char **v15; // rdx
  unsigned int **v16; // rdx
  MessageParams **v17; // rdx
  _QWORD *v18; // rdx
  MessageParams **v19; // rdx
  MessageParams **v20; // rdx
  MessageParams **v21; // rdx
  MessageParams **v22; // rdx
  unsigned int v23; // edx
  DWORD v24; // eax
  MessageParams *v26; // [rsp+20h] [rbp-10h] BYREF
  char *v27; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v28; // [rsp+60h] [rbp+30h] BYREF
  int v29; // [rsp+64h] [rbp+34h]

  v29 = HIDWORD(a1);
  v8 = (MessageParams *)a3;
  v28 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v27 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x23Eu, "CreateEvent", LastError);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::GetImpl'::`2'::impl) )
  {
    v12 = (MessageParams *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
    v26 = v12;
    if ( v12 )
      v13 = MessageParams::MessageParams(v12);
    else
      v13 = 0;
    if ( !v13 )
    {
      WwanLog::Error("WwanSapQueryInterface", 0, L"failed to allocate memory");
      v14 = 14;
      goto LABEL_41;
    }
  }
  else
  {
    v26 = (MessageParams *)operator new(0x48u);
    v13 = MessageParams::MessageParams(v26);
  }
  v26 = (MessageParams *)EventW;
  v15 = (char **)*((_QWORD *)v13 + 7);
  if ( v15 == *((char ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v15, &v26);
  }
  else
  {
    *v15 = EventW;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = (MessageParams *)&v28;
  v16 = (unsigned int **)*((_QWORD *)v13 + 7);
  if ( v16 == *((unsigned int ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v16, &v26);
  }
  else
  {
    *v16 = &v28;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = a2;
  v17 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v17 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v17, &v26);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = v8;
  v18 = (_QWORD *)*((_QWORD *)v13 + 7);
  if ( v18 == *((_QWORD **)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v18, &v26);
  }
  else
  {
    *v18 = v8;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = a4;
  v19 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v19 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v19, &v26);
  }
  else
  {
    *v19 = a4;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = a5;
  v20 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v20 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v20, &v26);
  }
  else
  {
    *v20 = a5;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = a6;
  v21 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v21 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v21, &v26);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  v26 = a7;
  v22 = (MessageParams **)*((_QWORD *)v13 + 7);
  if ( v22 == *((MessageParams ***)v13 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v13 + 48, v22, &v26);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v13 + 7) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(3, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapQueryInterface", 0, L"Notification dispatcher: Failed to Queue Message");
    v14 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v24 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x262u, "WaitForSingleObject", v24);
    }
    v14 = v28;
  }
LABEL_41:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v27);
  return v14;
}

```

## disassembly

```asm
0x1800b33d0  mov     [rsp-28h+arg_8], rbx
0x1800b33d5  mov     [rsp-28h+arg_10], rsi
0x1800b33da  mov     [rsp-28h+arg_0], rcx
0x1800b33df  push    rbp
0x1800b33e0  push    rdi
0x1800b33e1  push    r12
0x1800b33e3  push    r14
0x1800b33e5  push    r15
0x1800b33e7  mov     rbp, rsp
0x1800b33ea  sub     rsp, 30h
0x1800b33ee  mov     r15, r9
0x1800b33f1  movsxd  r12, r8d
0x1800b33f4  mov     r14, rdx
0x1800b33f7  mov     dword ptr [rbp+arg_0], 0
0x1800b33fe  xor     r9d, r9d; lpName
0x1800b3401  xor     r8d, r8d; bInitialState
0x1800b3404  lea     edx, [r9+1]; bManualReset
0x1800b3408  xor     ecx, ecx; lpEventAttributes
0x1800b340a  call    cs:__imp_CreateEventW
0x1800b3410  mov     rbx, rax
0x1800b3413  mov     [rbp+var_8], rax
0x1800b3417  inc     rax
0x1800b341a  cmp     rax, 1
0x1800b341e  ja      short loc_1800B3441
0x1800b3420  call    cs:__imp_GetLastError
0x1800b3426  mov     r9d, eax; unsigned int
0x1800b3429  lea     r8, aCreateevent; "CreateEvent"
0x1800b3430  mov     edx, 23Eh; unsigned int
0x1800b3435  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b343c  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3441  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX> `wil::Feature<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::GetImpl(void)'::`2'::impl
0x1800b3448  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::__private_IsEnabled(void)
0x1800b344d  mov     ecx, 48h ; 'H'; Size
0x1800b3452  test    al, al
0x1800b3454  jz      short loc_1800B349C
0x1800b3456  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b345d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b3462  mov     [rbp+var_10], rax
0x1800b3466  test    rax, rax
0x1800b3469  jz      short loc_1800B3478
0x1800b346b  mov     rcx, rax; this
0x1800b346e  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b3473  mov     rsi, rax
0x1800b3476  jmp     short loc_1800B347A
0x1800b3478  xor     esi, esi
0x1800b347a  test    rsi, rsi
0x1800b347d  jnz     short loc_1800B34B0
0x1800b347f  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800b3486  xor     edx, edx; struct _GUID *
0x1800b3488  lea     rcx, aWwansapqueryin_0; "WwanSapQueryInterface"
0x1800b348f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b3494  lea     ebx, [rsi+0Eh]
0x1800b3497  jmp     loc_1800B3659
0x1800b349c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b34a1  mov     [rbp+var_10], rax
0x1800b34a5  mov     rcx, rax; this
0x1800b34a8  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b34ad  mov     rsi, rax
0x1800b34b0  lea     rdi, [rsi+30h]
0x1800b34b4  mov     [rbp+var_10], rbx
0x1800b34b8  mov     rdx, [rdi+8]
0x1800b34bc  cmp     rdx, [rdi+10h]
0x1800b34c0  jz      short loc_1800B34CC
0x1800b34c2  mov     [rdx], rbx
0x1800b34c5  add     qword ptr [rdi+8], 8
0x1800b34ca  jmp     short loc_1800B34D8
0x1800b34cc  lea     r8, [rbp+var_10]
0x1800b34d0  mov     rcx, rdi
0x1800b34d3  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b34d8  lea     rax, [rbp+arg_0]
0x1800b34dc  mov     [rbp+var_10], rax
0x1800b34e0  mov     rdx, [rdi+8]
0x1800b34e4  cmp     rdx, [rdi+10h]
0x1800b34e8  jz      short loc_1800B34F8
0x1800b34ea  lea     rax, [rbp+arg_0]
0x1800b34ee  mov     [rdx], rax
0x1800b34f1  add     qword ptr [rdi+8], 8
0x1800b34f6  jmp     short loc_1800B3504
0x1800b34f8  lea     r8, [rbp+var_10]
0x1800b34fc  mov     rcx, rdi
0x1800b34ff  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3504  mov     [rbp+var_10], r14
0x1800b3508  mov     rdx, [rdi+8]
0x1800b350c  cmp     rdx, [rdi+10h]
0x1800b3510  jz      short loc_1800B351C
0x1800b3512  mov     [rdx], r14
0x1800b3515  add     qword ptr [rdi+8], 8
0x1800b351a  jmp     short loc_1800B3528
0x1800b351c  lea     r8, [rbp+var_10]
0x1800b3520  mov     rcx, rdi
0x1800b3523  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3528  mov     rax, r12
0x1800b352b  mov     [rbp+var_10], rax
0x1800b352f  mov     rdx, [rdi+8]
0x1800b3533  cmp     rdx, [rdi+10h]
0x1800b3537  jz      short loc_1800B3543
0x1800b3539  mov     [rdx], rax
0x1800b353c  add     qword ptr [rdi+8], 8
0x1800b3541  jmp     short loc_1800B354F
0x1800b3543  lea     r8, [rbp+var_10]
0x1800b3547  mov     rcx, rdi
0x1800b354a  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b354f  mov     [rbp+var_10], r15
0x1800b3553  mov     rdx, [rdi+8]
0x1800b3557  cmp     rdx, [rdi+10h]
0x1800b355b  jz      short loc_1800B3567
0x1800b355d  mov     [rdx], r15
0x1800b3560  add     qword ptr [rdi+8], 8
0x1800b3565  jmp     short loc_1800B3573
0x1800b3567  lea     r8, [rbp+var_10]
0x1800b356b  mov     rcx, rdi
0x1800b356e  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3573  mov     rax, [rbp+arg_20]
0x1800b3577  mov     [rbp+var_10], rax
0x1800b357b  mov     rdx, [rdi+8]
0x1800b357f  cmp     rdx, [rdi+10h]
0x1800b3583  jz      short loc_1800B358F
0x1800b3585  mov     [rdx], rax
0x1800b3588  add     qword ptr [rdi+8], 8
0x1800b358d  jmp     short loc_1800B359B
0x1800b358f  lea     r8, [rbp+var_10]
0x1800b3593  mov     rcx, rdi
0x1800b3596  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b359b  mov     rax, [rbp+arg_28]
0x1800b359f  mov     [rbp+var_10], rax
0x1800b35a3  mov     rdx, [rdi+8]
0x1800b35a7  cmp     rdx, [rdi+10h]
0x1800b35ab  jz      short loc_1800B35B7
0x1800b35ad  mov     [rdx], rax
0x1800b35b0  add     qword ptr [rdi+8], 8
0x1800b35b5  jmp     short loc_1800B35C3
0x1800b35b7  lea     r8, [rbp+var_10]
0x1800b35bb  mov     rcx, rdi
0x1800b35be  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b35c3  mov     rax, [rbp+arg_30]
0x1800b35c7  mov     [rbp+var_10], rax
0x1800b35cb  mov     rdx, [rdi+8]
0x1800b35cf  cmp     rdx, [rdi+10h]
0x1800b35d3  jz      short loc_1800B35DF
0x1800b35d5  mov     [rdx], rax
0x1800b35d8  add     qword ptr [rdi+8], 8
0x1800b35dd  jmp     short loc_1800B35EB
0x1800b35df  lea     r8, [rbp+var_10]
0x1800b35e3  mov     rcx, rdi
0x1800b35e6  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b35eb  mov     rdx, rsi
0x1800b35ee  mov     ecx, 3
0x1800b35f3  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b35f8  test    eax, eax
0x1800b35fa  jz      short loc_1800B3625
0x1800b35fc  test    rsi, rsi
0x1800b35ff  jz      short loc_1800B3609
0x1800b3601  mov     rcx, rsi; this
0x1800b3604  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b3609  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b3610  xor     edx, edx; struct _GUID *
0x1800b3612  lea     rcx, aWwansapqueryin_0; "WwanSapQueryInterface"
0x1800b3619  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b361e  mov     ebx, 1Fh
0x1800b3623  jmp     short loc_1800B3659
0x1800b3625  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b3628  mov     rcx, rbx; hHandle
0x1800b362b  call    cs:__imp_WaitForSingleObject
0x1800b3631  test    eax, eax
0x1800b3633  jz      short loc_1800B3656
0x1800b3635  call    cs:__imp_GetLastError
0x1800b363b  mov     r9d, eax; unsigned int
0x1800b363e  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b3645  mov     edx, 262h; unsigned int
0x1800b364a  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b3651  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3656  mov     ebx, dword ptr [rbp+arg_0]
0x1800b3659  lea     rcx, [rbp+var_8]
0x1800b365d  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b3662  mov     eax, ebx
0x1800b3664  mov     rbx, [rsp+30h+arg_8]
0x1800b3669  mov     rsi, [rsp+30h+arg_10]
0x1800b366e  add     rsp, 30h
0x1800b3672  pop     r15
0x1800b3674  pop     r14
0x1800b3676  pop     r12
0x1800b3678  pop     rdi
0x1800b3679  pop     rbp
0x1800b367a  retn
```
