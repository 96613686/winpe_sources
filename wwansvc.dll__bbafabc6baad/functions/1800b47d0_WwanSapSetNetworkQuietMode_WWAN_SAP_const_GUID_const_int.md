# WwanSapSetNetworkQuietMode(WWAN_SAP const *,_GUID const *,int)

- ea: `0x1800b47d0`
- end: `0x1800b497a`
- name: `?WwanSapSetNetworkQuietMode@@YAKPEBUWWAN_SAP@@PEBU_GUID@@H@Z`
- size: `426`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ad5d0`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b47d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4930`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b4930`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b4801`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b4801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b493a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b4817`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b493a`

## string_xrefs

- `0x1800b482c`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b494f`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b4820`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapSetNetworkQuietMode(const struct WWAN_SAP *a1, const struct _GUID *a2, unsigned int a3)
{
  MessageParams *v3; // r15
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v7; // rax
  MessageParams *v8; // rsi
  char *v9; // rdi
  char **v10; // rdx
  unsigned int **v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  unsigned int v14; // edx
  unsigned int v15; // ebx
  DWORD v16; // eax
  MessageParams *v18; // [rsp+50h] [rbp+30h] BYREF
  char *v19; // [rsp+58h] [rbp+38h] BYREF
  unsigned int v20; // [rsp+60h] [rbp+40h] BYREF

  v18 = a1;
  v3 = (MessageParams *)a3;
  v20 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v19 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xAD9u, "CreateEvent", LastError);
  }
  v18 = (MessageParams *)operator new(0x48u);
  v7 = MessageParams::MessageParams(v18);
  v8 = v7;
  v9 = (char *)v7 + 48;
  v18 = (MessageParams *)EventW;
  v10 = (char **)*((_QWORD *)v7 + 7);
  if ( v10 == *((char ***)v7 + 8) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>((char *)v7 + 48, v10, &v18);
  }
  else
  {
    *v10 = EventW;
    *((_QWORD *)v7 + 7) += 8LL;
  }
  v18 = (MessageParams *)&v20;
  v11 = (unsigned int **)*((_QWORD *)v9 + 1);
  if ( v11 == *((unsigned int ***)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v11, &v18);
  }
  else
  {
    *v11 = &v20;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  v18 = (MessageParams *)a2;
  v12 = (_QWORD *)*((_QWORD *)v9 + 1);
  if ( v12 == *((_QWORD **)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v12, &v18);
  }
  else
  {
    *v12 = a2;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  v18 = v3;
  v13 = (_QWORD *)*((_QWORD *)v9 + 1);
  if ( v13 == *((_QWORD **)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v13, &v18);
  }
  else
  {
    *v13 = v3;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(40, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v14);
    WwanLog::Error("WwanSapSetNetworkQuietMode", 0, L"Notification dispatcher: Failed to Queue Message");
    v15 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v16 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0xAECu, "WaitForSingleObject", v16);
    }
    v15 = v20;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v19);
  return v15;
}

```

## disassembly

```asm
0x1800b47d0  mov     [rsp-28h+arg_18], rbx
0x1800b47d5  mov     [rsp-28h+arg_0], rcx
0x1800b47da  push    rbp
0x1800b47db  push    rsi
0x1800b47dc  push    rdi
0x1800b47dd  push    r14
0x1800b47df  push    r15
0x1800b47e1  mov     rbp, rsp
0x1800b47e4  sub     rsp, 20h
0x1800b47e8  mov     r15d, r8d
0x1800b47eb  mov     r14, rdx
0x1800b47ee  mov     [rbp+arg_10], 0
0x1800b47f5  xor     r9d, r9d; lpName
0x1800b47f8  xor     r8d, r8d; bInitialState
0x1800b47fb  lea     edx, [r9+1]; bManualReset
0x1800b47ff  xor     ecx, ecx; lpEventAttributes
0x1800b4801  call    cs:__imp_CreateEventW
0x1800b4807  mov     rbx, rax
0x1800b480a  mov     [rbp+arg_8], rax
0x1800b480e  inc     rax
0x1800b4811  cmp     rax, 1
0x1800b4815  ja      short loc_1800B4838
0x1800b4817  call    cs:__imp_GetLastError
0x1800b481d  mov     r9d, eax; unsigned int
0x1800b4820  lea     r8, aCreateevent; "CreateEvent"
0x1800b4827  mov     edx, 0AD9h; unsigned int
0x1800b482c  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4833  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b4838  mov     ecx, 48h ; 'H'; Size
0x1800b483d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b4842  mov     [rbp+arg_0], rax
0x1800b4846  mov     rcx, rax; this
0x1800b4849  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b484e  mov     rsi, rax
0x1800b4851  lea     rdi, [rax+30h]
0x1800b4855  mov     [rbp+arg_0], rbx
0x1800b4859  mov     rdx, [rdi+8]
0x1800b485d  cmp     rdx, [rdi+10h]
0x1800b4861  jz      short loc_1800B486D
0x1800b4863  mov     [rdx], rbx
0x1800b4866  add     qword ptr [rdi+8], 8
0x1800b486b  jmp     short loc_1800B4879
0x1800b486d  lea     r8, [rbp+arg_0]
0x1800b4871  mov     rcx, rdi
0x1800b4874  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b4879  lea     rax, [rbp+arg_10]
0x1800b487d  mov     [rbp+arg_0], rax
0x1800b4881  mov     rdx, [rdi+8]
0x1800b4885  cmp     rdx, [rdi+10h]
0x1800b4889  jz      short loc_1800B4899
0x1800b488b  lea     rax, [rbp+arg_10]
0x1800b488f  mov     [rdx], rax
0x1800b4892  add     qword ptr [rdi+8], 8
0x1800b4897  jmp     short loc_1800B48A5
0x1800b4899  lea     r8, [rbp+arg_0]
0x1800b489d  mov     rcx, rdi
0x1800b48a0  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b48a5  mov     [rbp+arg_0], r14
0x1800b48a9  mov     rdx, [rdi+8]
0x1800b48ad  cmp     rdx, [rdi+10h]
0x1800b48b1  jz      short loc_1800B48BD
0x1800b48b3  mov     [rdx], r14
0x1800b48b6  add     qword ptr [rdi+8], 8
0x1800b48bb  jmp     short loc_1800B48C9
0x1800b48bd  lea     r8, [rbp+arg_0]
0x1800b48c1  mov     rcx, rdi
0x1800b48c4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b48c9  mov     rax, r15
0x1800b48cc  mov     [rbp+arg_0], rax
0x1800b48d0  mov     rdx, [rdi+8]
0x1800b48d4  cmp     rdx, [rdi+10h]
0x1800b48d8  jz      short loc_1800B48E4
0x1800b48da  mov     [rdx], rax
0x1800b48dd  add     qword ptr [rdi+8], 8
0x1800b48e2  jmp     short loc_1800B48F0
0x1800b48e4  lea     r8, [rbp+arg_0]
0x1800b48e8  mov     rcx, rdi
0x1800b48eb  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b48f0  mov     rdx, rsi
0x1800b48f3  mov     ecx, 28h ; '('
0x1800b48f8  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b48fd  test    eax, eax
0x1800b48ff  jz      short loc_1800B492A
0x1800b4901  test    rsi, rsi
0x1800b4904  jz      short loc_1800B490E
0x1800b4906  mov     rcx, rsi; this
0x1800b4909  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b490e  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b4915  xor     edx, edx; struct _GUID *
0x1800b4917  lea     rcx, aWwansapsetnetw; "WwanSapSetNetworkQuietMode"
0x1800b491e  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b4923  mov     ebx, 1Fh
0x1800b4928  jmp     short loc_1800B495E
0x1800b492a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b492d  mov     rcx, rbx; hHandle
0x1800b4930  call    cs:__imp_WaitForSingleObject
0x1800b4936  test    eax, eax
0x1800b4938  jz      short loc_1800B495B
0x1800b493a  call    cs:__imp_GetLastError
0x1800b4940  mov     r9d, eax; unsigned int
0x1800b4943  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b494a  mov     edx, 0AECh; unsigned int
0x1800b494f  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b4956  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b495b  mov     ebx, [rbp+arg_10]
0x1800b495e  lea     rcx, [rbp+arg_8]
0x1800b4962  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b4967  mov     eax, ebx
0x1800b4969  mov     rbx, [rsp+20h+arg_18]
0x1800b496e  add     rsp, 20h
0x1800b4972  pop     r15
0x1800b4974  pop     r14
0x1800b4976  pop     rdi
0x1800b4977  pop     rsi
0x1800b4978  pop     rbp
0x1800b4979  retn
```
