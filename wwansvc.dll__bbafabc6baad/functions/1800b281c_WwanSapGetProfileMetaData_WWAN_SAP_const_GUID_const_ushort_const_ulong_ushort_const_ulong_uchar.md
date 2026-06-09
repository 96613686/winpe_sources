# WwanSapGetProfileMetaData(WWAN_SAP const *,_GUID const *,ushort const *,ulong,ushort const *,ulong *,uchar * *)

- ea: `0x1800b281c`
- end: `0x1800b2a61`
- name: `?WwanSapGetProfileMetaData@@YAKPEBUWWAN_SAP@@PEBU_GUID@@PEBGK2PEAKPEAPEAE@Z`
- size: `581`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, const struct _GUID *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800acd60`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b281c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2a19`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b2a19`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b284e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b284e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b2a23`

## string_xrefs

- `0x1800b2879`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b2a38`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapGetProfileMetaData(
        const struct WWAN_SAP *a1,
        const struct _GUID *a2,
        MessageParams *a3,
        unsigned int a4,
        MessageParams *a5,
        unsigned int *a6,
        unsigned __int8 **a7)
{
  MessageParams *v7; // r12
  char *EventW; // rbx
  DWORD LastError; // eax
  MessageParams *v12; // rax
  MessageParams *v13; // rsi
  char *v14; // rdi
  char **v15; // rdx
  unsigned int **v16; // rdx
  _QWORD *v17; // rdx
  MessageParams **v18; // rdx
  _QWORD *v19; // rdx
  MessageParams **v20; // rdx
  _QWORD *v21; // rdx
  _QWORD *v22; // rdx
  unsigned int v23; // edx
  unsigned int v24; // ebx
  DWORD v25; // eax
  MessageParams *v27; // [rsp+60h] [rbp+40h] BYREF
  char *v28; // [rsp+68h] [rbp+48h] BYREF
  unsigned int v29; // [rsp+78h] [rbp+58h] BYREF

  v27 = a1;
  v7 = (MessageParams *)a4;
  v29 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v28 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError(
      "onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c",
      0x52Du,
      "Failure while creating an Event",
      LastError);
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
  v27 = (MessageParams *)a2;
  v17 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v17 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v17, &v27);
  }
  else
  {
    *v17 = a2;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = a3;
  v18 = (MessageParams **)*((_QWORD *)v14 + 1);
  if ( v18 == *((MessageParams ***)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v18, &v27);
  }
  else
  {
    *v18 = a3;
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
  v27 = (MessageParams *)a6;
  v21 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v21 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v21, &v27);
  }
  else
  {
    *v21 = a6;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  v27 = (MessageParams *)a7;
  v22 = (_QWORD *)*((_QWORD *)v14 + 1);
  if ( v22 == *((_QWORD **)v14 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v14, v22, &v27);
  }
  else
  {
    *v22 = a7;
    *((_QWORD *)v14 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(19, v13) )
  {
    if ( v13 )
      MessageParams::`scalar deleting destructor'(v13, v23);
    WwanLog::Error("WwanSapGetProfileMetaData", 0, L"Notification dispatcher: Failed to Queue Message");
    v24 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v25 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x544u, "WaitForSingleObject", v25);
    }
    v24 = v29;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v28);
  return v24;
}

```

## disassembly

```asm
0x1800b281c  mov     [rsp-38h+arg_0], rcx
0x1800b2821  push    rbp
0x1800b2822  push    rbx
0x1800b2823  push    rsi
0x1800b2824  push    rdi
0x1800b2825  push    r12
0x1800b2827  push    r14
0x1800b2829  push    r15
0x1800b282b  mov     rbp, rsp
0x1800b282e  sub     rsp, 20h
0x1800b2832  mov     r12d, r9d
0x1800b2835  mov     r15, r8
0x1800b2838  mov     r14, rdx
0x1800b283b  mov     [rbp+arg_18], 0
0x1800b2842  xor     r9d, r9d; lpName
0x1800b2845  xor     r8d, r8d; bInitialState
0x1800b2848  lea     edx, [r9+1]; bManualReset
0x1800b284c  xor     ecx, ecx; lpEventAttributes
0x1800b284e  call    cs:__imp_CreateEventW
0x1800b2854  mov     rbx, rax
0x1800b2857  mov     [rbp+arg_8], rax
0x1800b285b  inc     rax
0x1800b285e  cmp     rax, 1
0x1800b2862  ja      short loc_1800B2885
0x1800b2864  call    cs:__imp_GetLastError
0x1800b286a  mov     r9d, eax; unsigned int
0x1800b286d  lea     r8, aFailureWhileCr; "Failure while creating an Event"
0x1800b2874  mov     edx, 52Dh; unsigned int
0x1800b2879  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2880  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2885  mov     ecx, 48h ; 'H'; Size
0x1800b288a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b288f  mov     [rbp+arg_0], rax
0x1800b2893  mov     rcx, rax; this
0x1800b2896  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b289b  mov     rsi, rax
0x1800b289e  lea     rdi, [rax+30h]
0x1800b28a2  mov     [rbp+arg_0], rbx
0x1800b28a6  mov     rdx, [rdi+8]
0x1800b28aa  cmp     rdx, [rdi+10h]
0x1800b28ae  jz      short loc_1800B28BA
0x1800b28b0  mov     [rdx], rbx
0x1800b28b3  add     qword ptr [rdi+8], 8
0x1800b28b8  jmp     short loc_1800B28C6
0x1800b28ba  lea     r8, [rbp+arg_0]
0x1800b28be  mov     rcx, rdi
0x1800b28c1  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b28c6  lea     rax, [rbp+arg_18]
0x1800b28ca  mov     [rbp+arg_0], rax
0x1800b28ce  mov     rdx, [rdi+8]
0x1800b28d2  cmp     rdx, [rdi+10h]
0x1800b28d6  jz      short loc_1800B28E6
0x1800b28d8  lea     rax, [rbp+arg_18]
0x1800b28dc  mov     [rdx], rax
0x1800b28df  add     qword ptr [rdi+8], 8
0x1800b28e4  jmp     short loc_1800B28F2
0x1800b28e6  lea     r8, [rbp+arg_0]
0x1800b28ea  mov     rcx, rdi
0x1800b28ed  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b28f2  mov     [rbp+arg_0], r14
0x1800b28f6  mov     rdx, [rdi+8]
0x1800b28fa  cmp     rdx, [rdi+10h]
0x1800b28fe  jz      short loc_1800B290A
0x1800b2900  mov     [rdx], r14
0x1800b2903  add     qword ptr [rdi+8], 8
0x1800b2908  jmp     short loc_1800B2916
0x1800b290a  lea     r8, [rbp+arg_0]
0x1800b290e  mov     rcx, rdi
0x1800b2911  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2916  mov     [rbp+arg_0], r15
0x1800b291a  mov     rdx, [rdi+8]
0x1800b291e  cmp     rdx, [rdi+10h]
0x1800b2922  jz      short loc_1800B292E
0x1800b2924  mov     [rdx], r15
0x1800b2927  add     qword ptr [rdi+8], 8
0x1800b292c  jmp     short loc_1800B293A
0x1800b292e  lea     r8, [rbp+arg_0]
0x1800b2932  mov     rcx, rdi
0x1800b2935  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b293a  mov     rax, r12
0x1800b293d  mov     [rbp+arg_0], rax
0x1800b2941  mov     rdx, [rdi+8]
0x1800b2945  cmp     rdx, [rdi+10h]
0x1800b2949  jz      short loc_1800B2955
0x1800b294b  mov     [rdx], rax
0x1800b294e  add     qword ptr [rdi+8], 8
0x1800b2953  jmp     short loc_1800B2961
0x1800b2955  lea     r8, [rbp+arg_0]
0x1800b2959  mov     rcx, rdi
0x1800b295c  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2961  mov     rax, [rbp+arg_20]
0x1800b2965  mov     [rbp+arg_0], rax
0x1800b2969  mov     rdx, [rdi+8]
0x1800b296d  cmp     rdx, [rdi+10h]
0x1800b2971  jz      short loc_1800B297D
0x1800b2973  mov     [rdx], rax
0x1800b2976  add     qword ptr [rdi+8], 8
0x1800b297b  jmp     short loc_1800B2989
0x1800b297d  lea     r8, [rbp+arg_0]
0x1800b2981  mov     rcx, rdi
0x1800b2984  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b2989  mov     rax, [rbp+arg_28]
0x1800b298d  mov     [rbp+arg_0], rax
0x1800b2991  mov     rdx, [rdi+8]
0x1800b2995  cmp     rdx, [rdi+10h]
0x1800b2999  jz      short loc_1800B29A5
0x1800b299b  mov     [rdx], rax
0x1800b299e  add     qword ptr [rdi+8], 8
0x1800b29a3  jmp     short loc_1800B29B1
0x1800b29a5  lea     r8, [rbp+arg_0]
0x1800b29a9  mov     rcx, rdi
0x1800b29ac  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b29b1  mov     rax, [rbp+arg_30]
0x1800b29b5  mov     [rbp+arg_0], rax
0x1800b29b9  mov     rdx, [rdi+8]
0x1800b29bd  cmp     rdx, [rdi+10h]
0x1800b29c1  jz      short loc_1800B29CD
0x1800b29c3  mov     [rdx], rax
0x1800b29c6  add     qword ptr [rdi+8], 8
0x1800b29cb  jmp     short loc_1800B29D9
0x1800b29cd  lea     r8, [rbp+arg_0]
0x1800b29d1  mov     rcx, rdi
0x1800b29d4  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b29d9  mov     rdx, rsi
0x1800b29dc  mov     ecx, 13h
0x1800b29e1  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b29e6  test    eax, eax
0x1800b29e8  jz      short loc_1800B2A13
0x1800b29ea  test    rsi, rsi
0x1800b29ed  jz      short loc_1800B29F7
0x1800b29ef  mov     rcx, rsi; this
0x1800b29f2  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b29f7  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b29fe  xor     edx, edx; struct _GUID *
0x1800b2a00  lea     rcx, aWwansapgetprof_1; "WwanSapGetProfileMetaData"
0x1800b2a07  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b2a0c  mov     ebx, 1Fh
0x1800b2a11  jmp     short loc_1800B2A47
0x1800b2a13  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b2a16  mov     rcx, rbx; hHandle
0x1800b2a19  call    cs:__imp_WaitForSingleObject
0x1800b2a1f  test    eax, eax
0x1800b2a21  jz      short loc_1800B2A44
0x1800b2a23  call    cs:__imp_GetLastError
0x1800b2a29  mov     r9d, eax; unsigned int
0x1800b2a2c  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b2a33  mov     edx, 544h; unsigned int
0x1800b2a38  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b2a3f  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b2a44  mov     ebx, [rbp+arg_18]
0x1800b2a47  lea     rcx, [rbp+arg_8]
0x1800b2a4b  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b2a50  mov     eax, ebx
0x1800b2a52  add     rsp, 20h
0x1800b2a56  pop     r15
0x1800b2a58  pop     r14
0x1800b2a5a  pop     r12
0x1800b2a5c  pop     rdi
0x1800b2a5d  pop     rsi
0x1800b2a5e  pop     rbx
0x1800b2a5f  pop     rbp
0x1800b2a60  retn
```
