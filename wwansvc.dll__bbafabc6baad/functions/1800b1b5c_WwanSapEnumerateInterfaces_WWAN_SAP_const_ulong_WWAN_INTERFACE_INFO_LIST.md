# WwanSapEnumerateInterfaces(WWAN_SAP const *,ulong,WWAN_INTERFACE_INFO_LIST * *)

- ea: `0x1800b1b5c`
- end: `0x1800b1d06`
- name: `?WwanSapEnumerateInterfaces@@YAKPEBUWWAN_SAP@@KPEAPEAUWWAN_INTERFACE_INFO_LIST@@@Z`
- size: `426`
- prototype: `unsigned int __fastcall(const struct WWAN_SAP *, unsigned int, struct WWAN_INTERFACE_INFO_LIST **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1800ac860`

## callees

- `0x180008abc`
- `0x1800119bc`
- `0x180012300`
- `0x1800135e0`
- `0x18005bb50`
- `0x1800712fc`
- `0x18007289c`
- `0x1800893b4`
- `0x1800b1b5c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1cbc`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800b1cbc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1b8d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800b1b8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1cc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1ba3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b1cc6`

## string_xrefs

- `0x1800b1bb8`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1cdb`: `onecoreuap\net\wwan\service\sessionmanager\wwansap.c`
- `0x1800b1bac`: `CreateEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WwanSapEnumerateInterfaces(
        const struct WWAN_SAP *a1,
        unsigned int a2,
        struct WWAN_INTERFACE_INFO_LIST **a3)
{
  MessageParams *v4; // r15
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
  unsigned int v19; // [rsp+58h] [rbp+38h] BYREF
  char *v20; // [rsp+60h] [rbp+40h] BYREF

  v18 = a1;
  v4 = (MessageParams *)a2;
  v19 = 0;
  EventW = (char *)CreateEventW(0, 1, 0, 0);
  v20 = EventW;
  if ( EventW == (char *)-1LL || EventW + 1 == (char *)1 )
  {
    LastError = GetLastError();
    __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x19Cu, "CreateEvent", LastError);
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
  v18 = (MessageParams *)&v19;
  v11 = (unsigned int **)*((_QWORD *)v9 + 1);
  if ( v11 == *((unsigned int ***)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v11, &v18);
  }
  else
  {
    *v11 = &v19;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  v18 = v4;
  v12 = (_QWORD *)*((_QWORD *)v9 + 1);
  if ( v12 == *((_QWORD **)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v12, &v18);
  }
  else
  {
    *v12 = v4;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  v18 = (MessageParams *)a3;
  v13 = (_QWORD *)*((_QWORD *)v9 + 1);
  if ( v13 == *((_QWORD **)v9 + 2) )
  {
    std::vector<void *>::_Emplace_reallocate<void * const &>(v9, v13, &v18);
  }
  else
  {
    *v13 = a3;
    *((_QWORD *)v9 + 1) += 8LL;
  }
  if ( (unsigned int)MessageDispatcher::_EnQueueWwanRPCMessage(1, v8) )
  {
    if ( v8 )
      MessageParams::`scalar deleting destructor'(v8, v14);
    WwanLog::Error("WwanSapEnumerateInterfaces", 0, L"Notification dispatcher: Failed to Queue Message");
    v15 = 31;
  }
  else
  {
    if ( WaitForSingleObject(EventW, 0xFFFFFFFF) )
    {
      v16 = GetLastError();
      __FatalError("onecoreuap\\net\\wwan\\service\\sessionmanager\\wwansap.c", 0x1AFu, "WaitForSingleObject", v16);
    }
    v15 = v19;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>((void **)&v20);
  return v15;
}

```

## disassembly

```asm
0x1800b1b5c  mov     [rsp-28h+arg_18], rbx
0x1800b1b61  mov     [rsp-28h+arg_0], rcx
0x1800b1b66  push    rbp
0x1800b1b67  push    rsi
0x1800b1b68  push    rdi
0x1800b1b69  push    r14
0x1800b1b6b  push    r15
0x1800b1b6d  mov     rbp, rsp
0x1800b1b70  sub     rsp, 20h
0x1800b1b74  mov     r14, r8
0x1800b1b77  mov     r15d, edx
0x1800b1b7a  mov     [rbp+arg_8], 0
0x1800b1b81  xor     r9d, r9d; lpName
0x1800b1b84  xor     r8d, r8d; bInitialState
0x1800b1b87  lea     edx, [r9+1]; bManualReset
0x1800b1b8b  xor     ecx, ecx; lpEventAttributes
0x1800b1b8d  call    cs:__imp_CreateEventW
0x1800b1b93  mov     rbx, rax
0x1800b1b96  mov     [rbp+arg_10], rax
0x1800b1b9a  inc     rax
0x1800b1b9d  cmp     rax, 1
0x1800b1ba1  ja      short loc_1800B1BC4
0x1800b1ba3  call    cs:__imp_GetLastError
0x1800b1ba9  mov     r9d, eax; unsigned int
0x1800b1bac  lea     r8, aCreateevent; "CreateEvent"
0x1800b1bb3  mov     edx, 19Ch; unsigned int
0x1800b1bb8  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1bbf  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1bc4  mov     ecx, 48h ; 'H'; Size
0x1800b1bc9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1bce  mov     [rbp+arg_0], rax
0x1800b1bd2  mov     rcx, rax; this
0x1800b1bd5  call    ??0MessageParams@@QEAA@XZ; MessageParams::MessageParams(void)
0x1800b1bda  mov     rsi, rax
0x1800b1bdd  lea     rdi, [rax+30h]
0x1800b1be1  mov     [rbp+arg_0], rbx
0x1800b1be5  mov     rdx, [rdi+8]
0x1800b1be9  cmp     rdx, [rdi+10h]
0x1800b1bed  jz      short loc_1800B1BF9
0x1800b1bef  mov     [rdx], rbx
0x1800b1bf2  add     qword ptr [rdi+8], 8
0x1800b1bf7  jmp     short loc_1800B1C05
0x1800b1bf9  lea     r8, [rbp+arg_0]
0x1800b1bfd  mov     rcx, rdi
0x1800b1c00  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1c05  lea     rax, [rbp+arg_8]
0x1800b1c09  mov     [rbp+arg_0], rax
0x1800b1c0d  mov     rdx, [rdi+8]
0x1800b1c11  cmp     rdx, [rdi+10h]
0x1800b1c15  jz      short loc_1800B1C25
0x1800b1c17  lea     rax, [rbp+arg_8]
0x1800b1c1b  mov     [rdx], rax
0x1800b1c1e  add     qword ptr [rdi+8], 8
0x1800b1c23  jmp     short loc_1800B1C31
0x1800b1c25  lea     r8, [rbp+arg_0]
0x1800b1c29  mov     rcx, rdi
0x1800b1c2c  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1c31  mov     rax, r15
0x1800b1c34  mov     [rbp+arg_0], rax
0x1800b1c38  mov     rdx, [rdi+8]
0x1800b1c3c  cmp     rdx, [rdi+10h]
0x1800b1c40  jz      short loc_1800B1C4C
0x1800b1c42  mov     [rdx], rax
0x1800b1c45  add     qword ptr [rdi+8], 8
0x1800b1c4a  jmp     short loc_1800B1C58
0x1800b1c4c  lea     r8, [rbp+arg_0]
0x1800b1c50  mov     rcx, rdi
0x1800b1c53  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1c58  mov     [rbp+arg_0], r14
0x1800b1c5c  mov     rdx, [rdi+8]
0x1800b1c60  cmp     rdx, [rdi+10h]
0x1800b1c64  jz      short loc_1800B1C70
0x1800b1c66  mov     [rdx], r14
0x1800b1c69  add     qword ptr [rdi+8], 8
0x1800b1c6e  jmp     short loc_1800B1C7C
0x1800b1c70  lea     r8, [rbp+arg_0]
0x1800b1c74  mov     rcx, rdi
0x1800b1c77  call    ??$_Emplace_reallocate@AEBQEAX@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAPEAPEAXQEAPEAXAEBQEAX@Z; std::vector<void *>::_Emplace_reallocate<void * const &>(void * * const,void * const &)
0x1800b1c7c  mov     rdx, rsi
0x1800b1c7f  mov     ecx, 1
0x1800b1c84  call    ?_EnQueueWwanRPCMessage@MessageDispatcher@@SAKW4_OpRPCCode@@PEAUMessageParams@@@Z; MessageDispatcher::_EnQueueWwanRPCMessage(_OpRPCCode,MessageParams *)
0x1800b1c89  test    eax, eax
0x1800b1c8b  jz      short loc_1800B1CB6
0x1800b1c8d  test    rsi, rsi
0x1800b1c90  jz      short loc_1800B1C9A
0x1800b1c92  mov     rcx, rsi; this
0x1800b1c95  call    ??_GMessageParams@@QEAAPEAXI@Z; MessageParams::`scalar deleting destructor'(uint)
0x1800b1c9a  lea     r8, aNotificationDi_8; "Notification dispatcher: Failed to Queu"...
0x1800b1ca1  xor     edx, edx; struct _GUID *
0x1800b1ca3  lea     rcx, aWwansapenumera; "WwanSapEnumerateInterfaces"
0x1800b1caa  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800b1caf  mov     ebx, 1Fh
0x1800b1cb4  jmp     short loc_1800B1CEA
0x1800b1cb6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800b1cb9  mov     rcx, rbx; hHandle
0x1800b1cbc  call    cs:__imp_WaitForSingleObject
0x1800b1cc2  test    eax, eax
0x1800b1cc4  jz      short loc_1800B1CE7
0x1800b1cc6  call    cs:__imp_GetLastError
0x1800b1ccc  mov     r9d, eax; unsigned int
0x1800b1ccf  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800b1cd6  mov     edx, 1AFh; unsigned int
0x1800b1cdb  lea     rcx, aOnecoreuapNetW_10; "onecoreuap\\net\\wwan\\service\\session"...
0x1800b1ce2  call    ?__FatalError@@YAXPEBDK0K@Z; __FatalError(char const *,ulong,char const *,ulong)
0x1800b1ce7  mov     ebx, [rbp+arg_8]
0x1800b1cea  lea     rcx, [rbp+arg_10]
0x1800b1cee  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x1800b1cf3  mov     eax, ebx
0x1800b1cf5  mov     rbx, [rsp+20h+arg_18]
0x1800b1cfa  add     rsp, 20h
0x1800b1cfe  pop     r15
0x1800b1d00  pop     r14
0x1800b1d02  pop     rdi
0x1800b1d03  pop     rsi
0x1800b1d04  pop     rbp
0x1800b1d05  retn
```
