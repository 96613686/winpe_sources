# WwanSapQueryInterfaceEx(WWAN_SAP const *,_GUID const *,Opcode,ulong,uchar const *,ulong *,ulong *,uchar * *)

- ea: `0x1800b3684`
- end: `0x1800b395a`
- name: `?WwanSapQueryInterfaceEx@@YAKPEBUWWAN_SAP@@PEBU_GUID@@W4Opcode@@KPEBEPEAK4PEAPEAE@Z`
- size: `726`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update`

## callers

- `0x1800ad240`

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
- `0x1800b3684`
- `0x1800b6264`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b390a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b390a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b36be`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b36be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b36d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b36d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3914`

## string_xrefs

- `0x1800b36e9`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b3929`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b36dd`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WwanSapQueryInterfaceEx(
        __int64 a1,
        MessageParams *a2,
        int a3,
        unsigned int a4,
        MessageParams *a5,
        MessageParams *a6,
        MessageParams *a7,
        MessageParams *a8)
{
  MessageParams *v8; // r12
  MessageParams *v9; // r15
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v13; // rax
  MessageParams *v14; // rsi
  unsigned int v15; // ebx
  char **v16; // rdx
  unsigned int **v17; // rdx
  MessageParams **v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  MessageParams **v21; // rdx
  MessageParams **v22; // rdx
  MessageParams **v23; // rdx
  MessageParams **v24; // rdx
  unsigned int v25; // edx
  DWORD v26; // eax
  MessageParams *v28; // [rsp+20h] [rbp-10h] BYREF
  char *v29; // [rsp+28h] [rbp-8h] BYREF
  unsigned int v30; // [rsp+60h] [rbp+30h] BYREF
  int v31; // [rsp+64h] [rbp+34h]

  v31 = HIDWORD(a1);
  v8 = (MessageParams *)a4;
  v9 = (MessageParams *)a3;
  v30 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v29 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x205u, "CreateEvent", LastError);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::GetImpl'::`2'::impl) )
  {
    v13 = (MessageParams *)operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
    v28 = v13;
    if ( v13 )
      v14 = MessageParams::MessageParams(v13);
    else
      v14 = 0;
    if ( !v14 )
    {
      WwanLog::Error("WwanSapQueryInterfaceEx", 0, L"failed to allocate memory");
      v15 = 14;
      goto LABEL_44;
    }
  }
  else
  {
    v28 = (MessageParams *)operator new(0x48u);
    v14 = MessageParams::MessageParams(v28);
  }
  v28 = (MessageParams *)EventW;
  v16 = (char **)*((_QWORD *)v14 + 7);
  if ( v16 == *((char ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v16, &v28);
  }
  else
  {
    *v16 = EventW;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = (MessageParams *)&v30;
  v17 = (unsigned int **)*((_QWORD *)v14 + 7);
  if ( v17 == *((unsigned int ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v17, &v28);
  }
  else
  {
    *v17 = &v30;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = a2;
  v18 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v18 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v18, &v28);
  }
  else
  {
    *v18 = a2;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = v9;
  v19 = (_QWORD *)*((_QWORD *)v14 + 7);
  if ( v19 == *((_QWORD **)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v19, &v28);
  }
  else
  {
    *v19 = v9;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = v8;
  v20 = (_QWORD *)*((_QWORD *)v14 + 7);
  if ( v20 == *((_QWORD **)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v20, &v28);
  }
  else
  {
    *v20 = v8;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = a5;
  v21 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v21 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v21, &v28);
  }
  else
  {
    *v21 = a5;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = a6;
  v22 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v22 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v22, &v28);
  }
  else
  {
    *v22 = a6;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = a7;
  v23 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v23 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v23, &v28);
  }
  else
  {
    *v23 = a7;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  v28 = a8;
  v24 = (MessageParams **)*((_QWORD *)v14 + 7);
  if ( v24 == *((MessageParams ***)v14 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v14 + 48, v24, &v28);
  }
  else
  {
    *v24 = a8;
    *((_QWORD *)v14 + 7) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(49, v14) )
  {
    if ( v14 )
      MessageParams::`scalar deleting destructor'(v14, v25);
    WwanLog::Error("WwanSapQueryInterfaceEx", 0, L"Notification dispatcher: Failed to Queue Message");
    v15 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v26 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x22Au, "WaitForSingleObject", v26);
    }
    v15 = v30;
  }
LABEL_44:
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v29);
  return v15;
}

```

## disassembly

```asm
0x1800b3684  mov     [rsp-28h+arg_8], rbx
0x1800b3689  mov     [rsp-28h+arg_10], rsi
0x1800b368e  mov     [rsp-28h+arg_0], rcx
0x1800b3693  push    rbp
0x1800b3694  push    rdi
0x1800b3695  push    r12
0x1800b3697  push    r14
0x1800b3699  push    r15
0x1800b369b  mov     rbp, rsp
0x1800b369e  sub     rsp, 30h
0x1800b36a2  mov     r12d, r9d
0x1800b36a5  movsxd  r15, r8d
0x1800b36a8  mov     r14, rdx
0x1800b36ab  mov     dword ptr [rbp+arg_0], 0
0x1800b36b2  xor     r9d, r9d; lpName
0x1800b36b5  xor     r8d, r8d; bInitialState
0x1800b36b8  lea     edx, [r9+1]; bManualReset
0x1800b36bc  xor     ecx, ecx; lpEventAttributes
0x1800b36be  call    cs:__imp_CreateEventW
0x1800b36c4  mov     rbx, rax
0x1800b36c7  mov     [rbp+var_8], rax
0x1800b36cb  inc     rax
0x1800b36ce  cmp     rax, 1
0x1800b36d2  ja      short loc_1800B36F5
0x1800b36d4  call    cs:__imp_GetLastError
0x1800b36da  mov     r9d, eax; unsigned int
0x1800b36dd  lea     r8, aCreateevent; "CreateEvent"
0x1800b36e4  mov     edx, 205h; unsigned int
0x1800b36e9  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b36f0  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b36f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX> `wil::Feature<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::GetImpl(void)'::`2'::impl
0x1800b36fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WwanSapQueryInterface_BadAlloc_BUGFIX>::__private_IsEnabled(void)
0x1800b3701  mov     ecx, 48h ; 'H'; Size
0x1800b3706  test    al, al
0x1800b3708  jz      short loc_1800B3750
0x1800b370a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b3711  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b3716  mov     [rbp+var_10], rax
0x1800b371a  test    rax, rax
0x1800b371d  jz      short loc_1800B372C
0x1800b371f  mov     rcx, rax; this
0x1800b3722  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b3727  mov     rsi, rax
0x1800b372a  jmp     short loc_1800B372E
0x1800b372c  xor     esi, esi
0x1800b372e  test    rsi, rsi
0x1800b3731  jnz     short loc_1800B3764
0x1800b3733  lea     r8, aFailedToAlloca; "failed to allocate memory"
0x1800b373a  xor     edx, edx; struct _GUID *
0x1800b373c  lea     rcx, aWwansapqueryin; "WwanSapQueryInterfaceEx"
0x1800b3743  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b3748  lea     ebx, [rsi+0Eh]
0x1800b374b  jmp     loc_1800B3938
0x1800b3750  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b3755  mov     [rbp+var_10], rax
0x1800b3759  mov     rcx, rax; this
0x1800b375c  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b3761  mov     rsi, rax
0x1800b3764  lea     rdi, [rsi+30h]
0x1800b3768  mov     [rbp+var_10], rbx
0x1800b376c  mov     rdx, [rdi+8]
0x1800b3770  cmp     rdx, [rdi+10h]
0x1800b3774  jz      short loc_1800B3780
0x1800b3776  mov     [rdx], rbx
0x1800b3779  add     qword ptr [rdi+8], 8
0x1800b377e  jmp     short loc_1800B378C
0x1800b3780  lea     r8, [rbp+var_10]
0x1800b3784  mov     rcx, rdi
0x1800b3787  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b378c  lea     rax, [rbp+arg_0]
0x1800b3790  mov     [rbp+var_10], rax
0x1800b3794  mov     rdx, [rdi+8]
0x1800b3798  cmp     rdx, [rdi+10h]
0x1800b379c  jz      short loc_1800B37AC
0x1800b379e  lea     rax, [rbp+arg_0]
0x1800b37a2  mov     [rdx], rax
0x1800b37a5  add     qword ptr [rdi+8], 8
0x1800b37aa  jmp     short loc_1800B37B8
0x1800b37ac  lea     r8, [rbp+var_10]
0x1800b37b0  mov     rcx, rdi
0x1800b37b3  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b37b8  mov     [rbp+var_10], r14
0x1800b37bc  mov     rdx, [rdi+8]
0x1800b37c0  cmp     rdx, [rdi+10h]
0x1800b37c4  jz      short loc_1800B37D0
0x1800b37c6  mov     [rdx], r14
0x1800b37c9  add     qword ptr [rdi+8], 8
0x1800b37ce  jmp     short loc_1800B37DC
0x1800b37d0  lea     r8, [rbp+var_10]
0x1800b37d4  mov     rcx, rdi
0x1800b37d7  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b37dc  mov     rax, r15
0x1800b37df  mov     [rbp+var_10], rax
0x1800b37e3  mov     rdx, [rdi+8]
0x1800b37e7  cmp     rdx, [rdi+10h]
0x1800b37eb  jz      short loc_1800B37F7
0x1800b37ed  mov     [rdx], rax
0x1800b37f0  add     qword ptr [rdi+8], 8
0x1800b37f5  jmp     short loc_1800B3803
0x1800b37f7  lea     r8, [rbp+var_10]
0x1800b37fb  mov     rcx, rdi
0x1800b37fe  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3803  mov     rax, r12
0x1800b3806  mov     [rbp+var_10], rax
0x1800b380a  mov     rdx, [rdi+8]
0x1800b380e  cmp     rdx, [rdi+10h]
0x1800b3812  jz      short loc_1800B381E
0x1800b3814  mov     [rdx], rax
0x1800b3817  add     qword ptr [rdi+8], 8
0x1800b381c  jmp     short loc_1800B382A
0x1800b381e  lea     r8, [rbp+var_10]
0x1800b3822  mov     rcx, rdi
0x1800b3825  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b382a  mov     rax, [rbp+arg_20]
0x1800b382e  mov     [rbp+var_10], rax
0x1800b3832  mov     rdx, [rdi+8]
0x1800b3836  cmp     rdx, [rdi+10h]
0x1800b383a  jz      short loc_1800B3846
0x1800b383c  mov     [rdx], rax
0x1800b383f  add     qword ptr [rdi+8], 8
0x1800b3844  jmp     short loc_1800B3852
0x1800b3846  lea     r8, [rbp+var_10]
0x1800b384a  mov     rcx, rdi
0x1800b384d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b3852  mov     rax, [rbp+arg_28]
0x1800b3856  mov     [rbp+var_10], rax
0x1800b385a  mov     rdx, [rdi+8]
0x1800b385e  cmp     rdx, [rdi+10h]
0x1800b3862  jz      short loc_1800B386E
0x1800b3864  mov     [rdx], rax
0x1800b3867  add     qword ptr [rdi+8], 8
0x1800b386c  jmp     short loc_1800B387A
0x1800b386e  lea     r8, [rbp+var_10]
0x1800b3872  mov     rcx, rdi
0x1800b3875  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b387a  mov     rax, [rbp+arg_30]
0x1800b387e  mov     [rbp+var_10], rax
0x1800b3882  mov     rdx, [rdi+8]
0x1800b3886  cmp     rdx, [rdi+10h]
0x1800b388a  jz      short loc_1800B3896
0x1800b388c  mov     [rdx], rax
0x1800b388f  add     qword ptr [rdi+8], 8
0x1800b3894  jmp     short loc_1800B38A2
0x1800b3896  lea     r8, [rbp+var_10]
0x1800b389a  mov     rcx, rdi
0x1800b389d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b38a2  mov     rax, [rbp+arg_38]
0x1800b38a6  mov     [rbp+var_10], rax
0x1800b38aa  mov     rdx, [rdi+8]
0x1800b38ae  cmp     rdx, [rdi+10h]
0x1800b38b2  jz      short loc_1800B38BE
0x1800b38b4  mov     [rdx], rax
0x1800b38b7  add     qword ptr [rdi+8], 8
0x1800b38bc  jmp     short loc_1800B38CA
0x1800b38be  lea     r8, [rbp+var_10]
0x1800b38c2  mov     rcx, rdi
0x1800b38c5  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b38ca  mov     rdx, rsi
0x1800b38cd  mov     ecx, 31h ; '1'
0x1800b38d2  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b38d7  test    eax, eax
0x1800b38d9  jz      short loc_1800B3904
0x1800b38db  test    rsi, rsi
0x1800b38de  jz      short loc_1800B38E8
0x1800b38e0  mov     rcx, rsi; this
0x1800b38e3  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b38e8  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b38ef  xor     edx, edx; struct _GUID *
0x1800b38f1  lea     rcx, aWwansapqueryin; "WwanSapQueryInterfaceEx"
0x1800b38f8  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b38fd  mov     ebx, 1Fh
0x1800b3902  jmp     short loc_1800B3938
0x1800b3904  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b3907  mov     rcx, rbx; hHandle
0x1800b390a  call    cs:__imp_WaitForSingleObject
0x1800b3910  test    eax, eax
0x1800b3912  jz      short loc_1800B3935
0x1800b3914  call    cs:__imp_GetLastError
0x1800b391a  mov     r9d, eax; unsigned int
0x1800b391d  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b3924  mov     edx, 22Ah; unsigned int
0x1800b3929  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b3930  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b3935  mov     ebx, dword ptr [rbp+arg_0]
0x1800b3938  lea     rcx, [rbp+var_8]
0x1800b393c  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b3941  mov     eax, ebx
0x1800b3943  mov     rbx, [rsp+30h+arg_8]
0x1800b3948  mov     rsi, [rsp+30h+arg_10]
0x1800b394d  add     rsp, 30h
0x1800b3951  pop     r15
0x1800b3953  pop     r14
0x1800b3955  pop     r12
0x1800b3957  pop     rdi
0x1800b3958  pop     rbp
0x1800b3959  retn
```
