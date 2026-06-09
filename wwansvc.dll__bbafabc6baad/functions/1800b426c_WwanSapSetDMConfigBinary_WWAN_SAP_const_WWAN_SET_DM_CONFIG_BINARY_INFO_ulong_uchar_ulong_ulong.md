# WwanSapSetDMConfigBinary(WWAN_SAP const *,WWAN_SET_DM_CONFIG_BINARY_INFO *,ulong,uchar *,ulong *,ulong *)

- ea: `0x1800b426c`
- end: `0x1800b4489`
- name: `?WwanSapSetDMConfigBinary@@YAKPEBUWWAN_SAP@@PEAUWWAN_SET_DM_CONFIG_BINARY_INFO@@KPEAEPEAK3@Z`
- size: `541`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, struct WWAN_SET_DM_CONFIG_BINARY_INFO *, unsigned int, unsigned __int8 *, unsigned int *, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ad4a0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b426c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4441`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4441`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b429e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b429e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b42b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b444b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b42b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b444b`

## string_xrefs

- `0x1800b42c9`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4460`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b42bd`: `CreateEvent`
- `0x1800b4428`: `WwanSapSetDMConfigBinary`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapSetDMConfigBinary(
        const struct WWAN_SAP *a1,
        struct WWAN_SET_DM_CONFIG_BINARY_INFO *a2,
        unsigned int a3,
        MessageParams *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  MessageParams *v7; // r12
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v11; // rax
  MessageParams *v12; // rsi
  char *v13; // rdi
  char **v14; // rdx
  unsigned int **v15; // rdx
  _QWORD *v16; // rdx
  _QWORD *v17; // rdx
  MessageParams **v18; // rdx
  _QWORD *v19; // rdx
  _QWORD *v20; // rdx
  unsigned int v21; // edx
  unsigned int v22; // ebx
  DWORD v23; // eax
  MessageParams *v25; // [rsp+60h] [rbp+40h] BYREF
  char *v26; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v27; // [rsp+70h] [rbp+50h] BYREF

  v25 = a1;
  v7 = (MessageParams *)a3;
  v27 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v26 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xAB5u, "CreateEvent", LastError);
  }
  v25 = (MessageParams *)operator new(0x48u);
  v11 = MessageParams::MessageParams(v25);
  v12 = v11;
  v13 = (char *)v11 + 48;
  v25 = (MessageParams *)EventW;
  v14 = (char **)*((_QWORD *)v11 + 7);
  if ( v14 == *((char ***)v11 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v11 + 48, v14, &v25);
  }
  else
  {
    *v14 = EventW;
    *((_QWORD *)v11 + 7) += 8LL;
  }
  v25 = (MessageParams *)&v27;
  v15 = (unsigned int **)*((_QWORD *)v13 + 1);
  if ( v15 == *((unsigned int ***)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v15, &v25);
  }
  else
  {
    *v15 = &v27;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = a2;
  v16 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v16 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v16, &v25);
  }
  else
  {
    *v16 = a2;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = v7;
  v17 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v17 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v17, &v25);
  }
  else
  {
    *v17 = v7;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = a4;
  v18 = (MessageParams **)*((_QWORD *)v13 + 1);
  if ( v18 == *((MessageParams ***)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v18, &v25);
  }
  else
  {
    *v18 = a4;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = (MessageParams *)a5;
  v19 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v19 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v19, &v25);
  }
  else
  {
    *v19 = a5;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  v25 = (MessageParams *)a6;
  v20 = (_QWORD *)*((_QWORD *)v13 + 1);
  if ( v20 == *((_QWORD **)v13 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v13, v20, &v25);
  }
  else
  {
    *v20 = a6;
    *((_QWORD *)v13 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(42, v12) )
  {
    if ( v12 )
      MessageParams::`scalar deleting destructor'(v12, v21);
    WwanLog::Error("WwanSapSetDMConfigBinary", 0, L"Notification dispatcher: Failed to Queue Message");
    v22 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v23 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xACBu, "WaitForSingleObject", v23);
    }
    v22 = v27;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v26);
  return v22;
}

```

## disassembly

```asm
0x1800b426c  mov     [rsp-38h+arg_0], rcx
0x1800b4271  push    rbp
0x1800b4272  push    rbx
0x1800b4273  push    rsi
0x1800b4274  push    rdi
0x1800b4275  push    r12
0x1800b4277  push    r14
0x1800b4279  push    r15
0x1800b427b  mov     rbp, rsp
0x1800b427e  sub     rsp, 20h
0x1800b4282  mov     r15, r9
0x1800b4285  mov     r12d, r8d
0x1800b4288  mov     r14, rdx
0x1800b428b  mov     [rbp+arg_10], 0
0x1800b4292  xor     r9d, r9d; lpName
0x1800b4295  xor     r8d, r8d; bInitialState
0x1800b4298  lea     edx, [r9+1]; bManualReset
0x1800b429c  xor     ecx, ecx; lpEventAttributes
0x1800b429e  call    cs:__imp_CreateEventW
0x1800b42a4  mov     rbx, rax
0x1800b42a7  mov     [rbp+arg_8], rax
0x1800b42ab  inc     rax
0x1800b42ae  cmp     rax, 1
0x1800b42b2  ja      short loc_1800B42D5
0x1800b42b4  call    cs:__imp_GetLastError
0x1800b42ba  mov     r9d, eax; unsigned int
0x1800b42bd  lea     r8, aCreateevent; "CreateEvent"
0x1800b42c4  mov     edx, 0AB5h; unsigned int
0x1800b42c9  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b42d0  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b42d5  mov     ecx, 48h ; 'H'; Size
0x1800b42da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b42df  mov     [rbp+arg_0], rax
0x1800b42e3  mov     rcx, rax; this
0x1800b42e6  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b42eb  mov     rsi, rax
0x1800b42ee  lea     rdi, [rax+30h]
0x1800b42f2  mov     [rbp+arg_0], rbx
0x1800b42f6  mov     rdx, [rdi+8]
0x1800b42fa  cmp     rdx, [rdi+10h]
0x1800b42fe  jz      short loc_1800B430A
0x1800b4300  mov     [rdx], rbx
0x1800b4303  add     qword ptr [rdi+8], 8
0x1800b4308  jmp     short loc_1800B4316
0x1800b430a  lea     r8, [rbp+arg_0]
0x1800b430e  mov     rcx, rdi
0x1800b4311  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4316  lea     rax, [rbp+arg_10]
0x1800b431a  mov     [rbp+arg_0], rax
0x1800b431e  mov     rdx, [rdi+8]
0x1800b4322  cmp     rdx, [rdi+10h]
0x1800b4326  jz      short loc_1800B4336
0x1800b4328  lea     rax, [rbp+arg_10]
0x1800b432c  mov     [rdx], rax
0x1800b432f  add     qword ptr [rdi+8], 8
0x1800b4334  jmp     short loc_1800B4342
0x1800b4336  lea     r8, [rbp+arg_0]
0x1800b433a  mov     rcx, rdi
0x1800b433d  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4342  mov     [rbp+arg_0], r14
0x1800b4346  mov     rdx, [rdi+8]
0x1800b434a  cmp     rdx, [rdi+10h]
0x1800b434e  jz      short loc_1800B435A
0x1800b4350  mov     [rdx], r14
0x1800b4353  add     qword ptr [rdi+8], 8
0x1800b4358  jmp     short loc_1800B4366
0x1800b435a  lea     r8, [rbp+arg_0]
0x1800b435e  mov     rcx, rdi
0x1800b4361  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4366  mov     rax, r12
0x1800b4369  mov     [rbp+arg_0], rax
0x1800b436d  mov     rdx, [rdi+8]
0x1800b4371  cmp     rdx, [rdi+10h]
0x1800b4375  jz      short loc_1800B4381
0x1800b4377  mov     [rdx], rax
0x1800b437a  add     qword ptr [rdi+8], 8
0x1800b437f  jmp     short loc_1800B438D
0x1800b4381  lea     r8, [rbp+arg_0]
0x1800b4385  mov     rcx, rdi
0x1800b4388  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b438d  mov     [rbp+arg_0], r15
0x1800b4391  mov     rdx, [rdi+8]
0x1800b4395  cmp     rdx, [rdi+10h]
0x1800b4399  jz      short loc_1800B43A5
0x1800b439b  mov     [rdx], r15
0x1800b439e  add     qword ptr [rdi+8], 8
0x1800b43a3  jmp     short loc_1800B43B1
0x1800b43a5  lea     r8, [rbp+arg_0]
0x1800b43a9  mov     rcx, rdi
0x1800b43ac  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b43b1  mov     rax, [rbp+arg_20]
0x1800b43b5  mov     [rbp+arg_0], rax
0x1800b43b9  mov     rdx, [rdi+8]
0x1800b43bd  cmp     rdx, [rdi+10h]
0x1800b43c1  jz      short loc_1800B43CD
0x1800b43c3  mov     [rdx], rax
0x1800b43c6  add     qword ptr [rdi+8], 8
0x1800b43cb  jmp     short loc_1800B43D9
0x1800b43cd  lea     r8, [rbp+arg_0]
0x1800b43d1  mov     rcx, rdi
0x1800b43d4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b43d9  mov     rax, [rbp+arg_28]
0x1800b43dd  mov     [rbp+arg_0], rax
0x1800b43e1  mov     rdx, [rdi+8]
0x1800b43e5  cmp     rdx, [rdi+10h]
0x1800b43e9  jz      short loc_1800B43F5
0x1800b43eb  mov     [rdx], rax
0x1800b43ee  add     qword ptr [rdi+8], 8
0x1800b43f3  jmp     short loc_1800B4401
0x1800b43f5  lea     r8, [rbp+arg_0]
0x1800b43f9  mov     rcx, rdi
0x1800b43fc  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4401  mov     rdx, rsi
0x1800b4404  mov     ecx, 2Ah ; '*'
0x1800b4409  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b440e  test    eax, eax
0x1800b4410  jz      short loc_1800B443B
0x1800b4412  test    rsi, rsi
0x1800b4415  jz      short loc_1800B441F
0x1800b4417  mov     rcx, rsi; this
0x1800b441a  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b441f  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b4426  xor     edx, edx; struct _GUID *
0x1800b4428  lea     rcx, aWwansapsetdmco_0; "WwanSapSetDMConfigBinary"
0x1800b442f  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4434  mov     ebx, 1Fh
0x1800b4439  jmp     short loc_1800B446F
0x1800b443b  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b443e  mov     rcx, rbx; hHandle
0x1800b4441  call    cs:__imp_WaitForSingleObject
0x1800b4447  test    eax, eax
0x1800b4449  jz      short loc_1800B446C
0x1800b444b  call    cs:__imp_GetLastError
0x1800b4451  mov     r9d, eax; unsigned int
0x1800b4454  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b445b  mov     edx, 0ACBh; unsigned int
0x1800b4460  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4467  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b446c  mov     ebx, [rbp+arg_10]
0x1800b446f  lea     rcx, [rbp+arg_8]
0x1800b4473  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4478  mov     eax, ebx
0x1800b447a  add     rsp, 20h
0x1800b447e  pop     r15
0x1800b4480  pop     r14
0x1800b4482  pop     r12
0x1800b4484  pop     rdi
0x1800b4485  pop     rsi
0x1800b4486  pop     rbx
0x1800b4487  pop     rbp
0x1800b4488  retn
```
