# WwanSapSetDMConfigProfile(WWAN_SAP const *,_GUID const *,ushort const *,int,WWAN_PROFILE_INVALID_REASON *)

- ea: `0x1800b4490`
- end: `0x1800b4685`
- name: `?WwanSapSetDMConfigProfile@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGHPEAW4WWAN_PROFILE_INVALID_REASON@@@Z`
- size: `501`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, int, enum WWAN_PROFILE_INVALID_REASON *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x1800ad4f0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b4490`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b463d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b463d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b44c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b44c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b44d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b44d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4647`

## string_xrefs

- `0x1800b44ed`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b465c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b44e1`: `CreateEvent`
- `0x1800b4624`: `WwanSapSetDMConfigProfile`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapSetDMConfigProfile(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        unsigned int a4,
        enum WWAN_PROFILE_INVALID_REASON *a5)
{
  MessageParams *v5; // r12
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v10; // rax
  MessageParams *v11; // rsi
  char *v12; // rdi
  char **v13; // rdx
  unsigned int **v14; // rdx
  _QWORD *v15; // rdx
  MessageParams **v16; // rdx
  _QWORD *v17; // rdx
  _QWORD *v18; // rdx
  unsigned int v19; // edx
  unsigned int v20; // ebx
  DWORD v21; // eax
  MessageParams *v23; // [rsp+60h] [rbp+40h] BYREF
  char *v24; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v25; // [rsp+78h] [rbp+58h] BYREF

  v23 = a1;
  v5 = (MessageParams *)a4;
  v25 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v24 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA48u, "CreateEvent", LastError);
  }
  v23 = (MessageParams *)operator new(0x48u);
  v10 = MessageParams::MessageParams(v23);
  v11 = v10;
  v12 = (char *)v10 + 48;
  v23 = (MessageParams *)EventW;
  v13 = (char **)*((_QWORD *)v10 + 7);
  if ( v13 == *((char ***)v10 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v10 + 48, v13, &v23);
  }
  else
  {
    *v13 = EventW;
    *((_QWORD *)v10 + 7) += 8LL;
  }
  v23 = (MessageParams *)&v25;
  v14 = (unsigned int **)*((_QWORD *)v12 + 1);
  if ( v14 == *((unsigned int ***)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v14, &v23);
  }
  else
  {
    *v14 = &v25;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v23 = (MessageParams *)a2;
  v15 = (_QWORD *)*((_QWORD *)v12 + 1);
  if ( v15 == *((_QWORD **)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v15, &v23);
  }
  else
  {
    *v15 = a2;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v23 = a3;
  v16 = (MessageParams **)*((_QWORD *)v12 + 1);
  if ( v16 == *((MessageParams ***)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v16, &v23);
  }
  else
  {
    *v16 = a3;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v23 = v5;
  v17 = (_QWORD *)*((_QWORD *)v12 + 1);
  if ( v17 == *((_QWORD **)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v17, &v23);
  }
  else
  {
    *v17 = v5;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  v23 = a5;
  v18 = (_QWORD *)*((_QWORD *)v12 + 1);
  if ( v18 == *((_QWORD **)v12 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v12, v18, &v23);
  }
  else
  {
    *v18 = a5;
    *((_QWORD *)v12 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(38, v11) )
  {
    if ( v11 )
      MessageParams::`scalar deleting destructor'(v11, v19);
    WwanLog::Error("WwanSapSetDMConfigProfile", 0, L"Notification dispatcher: Failed to Queue Message");
    v20 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v21 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xA5Du, "WaitForSingleObject", v21);
    }
    v20 = v25;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v24);
  return v20;
}

```

## disassembly

```asm
0x1800b4490  mov     [rsp-38h+arg_0], rcx
0x1800b4495  push    rbp
0x1800b4496  push    rbx
0x1800b4497  push    rsi
0x1800b4498  push    rdi
0x1800b4499  push    r12
0x1800b449b  push    r14
0x1800b449d  push    r15
0x1800b449f  mov     rbp, rsp
0x1800b44a2  sub     rsp, 20h
0x1800b44a6  mov     r12d, r9d
0x1800b44a9  mov     r15, r8
0x1800b44ac  mov     r14, rdx
0x1800b44af  mov     [rbp+arg_18], 0
0x1800b44b6  xor     r9d, r9d; lpName
0x1800b44b9  xor     r8d, r8d; bInitialState
0x1800b44bc  lea     edx, [r9+1]; bManualReset
0x1800b44c0  xor     ecx, ecx; lpEventAttributes
0x1800b44c2  call    cs:__imp_CreateEventW
0x1800b44c8  mov     rbx, rax
0x1800b44cb  mov     [rbp+arg_8], rax
0x1800b44cf  inc     rax
0x1800b44d2  cmp     rax, 1
0x1800b44d6  ja      short loc_1800B44F9
0x1800b44d8  call    cs:__imp_GetLastError
0x1800b44de  mov     r9d, eax; unsigned int
0x1800b44e1  lea     r8, aCreateevent; "CreateEvent"
0x1800b44e8  mov     edx, 0A48h; unsigned int
0x1800b44ed  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b44f4  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b44f9  mov     ecx, 48h ; 'H'; Size
0x1800b44fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4503  mov     [rbp+arg_0], rax
0x1800b4507  mov     rcx, rax; this
0x1800b450a  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b450f  mov     rsi, rax
0x1800b4512  lea     rdi, [rax+30h]
0x1800b4516  mov     [rbp+arg_0], rbx
0x1800b451a  mov     rdx, [rdi+8]
0x1800b451e  cmp     rdx, [rdi+10h]
0x1800b4522  jz      short loc_1800B452E
0x1800b4524  mov     [rdx], rbx
0x1800b4527  add     qword ptr [rdi+8], 8
0x1800b452c  jmp     short loc_1800B453A
0x1800b452e  lea     r8, [rbp+arg_0]
0x1800b4532  mov     rcx, rdi
0x1800b4535  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b453a  lea     rax, [rbp+arg_18]
0x1800b453e  mov     [rbp+arg_0], rax
0x1800b4542  mov     rdx, [rdi+8]
0x1800b4546  cmp     rdx, [rdi+10h]
0x1800b454a  jz      short loc_1800B455A
0x1800b454c  lea     rax, [rbp+arg_18]
0x1800b4550  mov     [rdx], rax
0x1800b4553  add     qword ptr [rdi+8], 8
0x1800b4558  jmp     short loc_1800B4566
0x1800b455a  lea     r8, [rbp+arg_0]
0x1800b455e  mov     rcx, rdi
0x1800b4561  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4566  mov     [rbp+arg_0], r14
0x1800b456a  mov     rdx, [rdi+8]
0x1800b456e  cmp     rdx, [rdi+10h]
0x1800b4572  jz      short loc_1800B457E
0x1800b4574  mov     [rdx], r14
0x1800b4577  add     qword ptr [rdi+8], 8
0x1800b457c  jmp     short loc_1800B458A
0x1800b457e  lea     r8, [rbp+arg_0]
0x1800b4582  mov     rcx, rdi
0x1800b4585  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b458a  mov     [rbp+arg_0], r15
0x1800b458e  mov     rdx, [rdi+8]
0x1800b4592  cmp     rdx, [rdi+10h]
0x1800b4596  jz      short loc_1800B45A2
0x1800b4598  mov     [rdx], r15
0x1800b459b  add     qword ptr [rdi+8], 8
0x1800b45a0  jmp     short loc_1800B45AE
0x1800b45a2  lea     r8, [rbp+arg_0]
0x1800b45a6  mov     rcx, rdi
0x1800b45a9  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b45ae  mov     rax, r12
0x1800b45b1  mov     [rbp+arg_0], rax
0x1800b45b5  mov     rdx, [rdi+8]
0x1800b45b9  cmp     rdx, [rdi+10h]
0x1800b45bd  jz      short loc_1800B45C9
0x1800b45bf  mov     [rdx], rax
0x1800b45c2  add     qword ptr [rdi+8], 8
0x1800b45c7  jmp     short loc_1800B45D5
0x1800b45c9  lea     r8, [rbp+arg_0]
0x1800b45cd  mov     rcx, rdi
0x1800b45d0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b45d5  mov     rax, [rbp+arg_20]
0x1800b45d9  mov     [rbp+arg_0], rax
0x1800b45dd  mov     rdx, [rdi+8]
0x1800b45e1  cmp     rdx, [rdi+10h]
0x1800b45e5  jz      short loc_1800B45F1
0x1800b45e7  mov     [rdx], rax
0x1800b45ea  add     qword ptr [rdi+8], 8
0x1800b45ef  jmp     short loc_1800B45FD
0x1800b45f1  lea     r8, [rbp+arg_0]
0x1800b45f5  mov     rcx, rdi
0x1800b45f8  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b45fd  mov     rdx, rsi
0x1800b4600  mov     ecx, 26h ; '&'
0x1800b4605  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b460a  test    eax, eax
0x1800b460c  jz      short loc_1800B4637
0x1800b460e  test    rsi, rsi
0x1800b4611  jz      short loc_1800B461B
0x1800b4613  mov     rcx, rsi; this
0x1800b4616  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b461b  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b4622  xor     edx, edx; struct _GUID *
0x1800b4624  lea     rcx, aWwansapsetdmco; "WwanSapSetDMConfigProfile"
0x1800b462b  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4630  mov     ebx, 1Fh
0x1800b4635  jmp     short loc_1800B466B
0x1800b4637  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b463a  mov     rcx, rbx; hHandle
0x1800b463d  call    cs:__imp_WaitForSingleObject
0x1800b4643  test    eax, eax
0x1800b4645  jz      short loc_1800B4668
0x1800b4647  call    cs:__imp_GetLastError
0x1800b464d  mov     r9d, eax; unsigned int
0x1800b4650  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b4657  mov     edx, 0A5Dh; unsigned int
0x1800b465c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4663  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4668  mov     ebx, [rbp+arg_18]
0x1800b466b  lea     rcx, [rbp+arg_8]
0x1800b466f  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4674  mov     eax, ebx
0x1800b4676  add     rsp, 20h
0x1800b467a  pop     r15
0x1800b467c  pop     r14
0x1800b467e  pop     r12
0x1800b4680  pop     rdi
0x1800b4681  pop     rsi
0x1800b4682  pop     rbx
0x1800b4683  pop     rbp
0x1800b4684  retn
```
