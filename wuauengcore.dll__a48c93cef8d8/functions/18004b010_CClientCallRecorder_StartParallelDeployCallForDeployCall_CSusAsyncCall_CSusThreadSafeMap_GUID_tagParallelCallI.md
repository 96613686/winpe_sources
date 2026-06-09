# CClientCallRecorder::StartParallelDeployCallForDeployCall(CSusAsyncCall *,CSusThreadSafeMap<_GUID,tagParallelCallInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<tagParallelCallInfo *>> *,bool)

- ea: `0x18004b010`
- end: `0x18004b29b`
- name: `?StartParallelDeployCallForDeployCall@CClientCallRecorder@@QEAAJPEAVCSusAsyncCall@@PEAV?$CSusThreadSafeMap@U_GUID@@PEAUtagParallelCallInfo@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAUtagParallelCallInfo@@@@@@_N@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, service_task`

## callers

- `0x18004b2a4`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x18001bc20`
- `0x18001bdb8`
- `0x18001d850`
- `0x18001da00`
- `0x18003baf4`
- `0x18004b010`
- `0x1800530f8`
- `0x180238984`
- `0x180239110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b129`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1da`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b129`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004b1da`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b14a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b210`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b14a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004b210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b196`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b196`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18004b187`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18004b187`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004b0d3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18004b0d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b267`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b109`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b267`

## string_xrefs

- `0x18004b03f`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004b0e9`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004b225`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`
- `0x18004b24a`: `C:\__w\1\s\src\Client\Engine\Agent\ClientCallRecorder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CClientCallRecorder::StartParallelDeployCallForDeployCall(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  __int64 v8; // rdx
  HANDLE *v10; // rax
  HANDLE *v11; // rbx
  signed int v12; // edi
  __int64 v13; // rdx
  HANDLE Thread; // rsi
  const char *v15; // r9
  signed int LastError; // eax
  unsigned int IndexOf; // eax
  int v18; // esi
  DWORD dwCreationFlags; // [rsp+20h] [rbp-68h]
  HANDLE *v20; // [rsp+30h] [rbp-58h] BYREF
  _OWORD v21[5]; // [rsp+38h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( !a2 )
  {
    v8 = 6275;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)0x80004003LL,
      dwCreationFlags);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v8 = 6276;
    goto LABEL_3;
  }
  v10 = (HANDLE *)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    v10[1] = 0;
    *v10 = 0;
  }
  else
  {
    v11 = 0;
  }
  v12 = v11 == 0 ? 0x8007000E : 0;
  if ( !v11 )
  {
    v13 = 6280;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
      (const char *)(unsigned int)v12,
      dwCreationFlags);
    goto LABEL_34;
  }
  Thread = CreateThread(0, 0, CClientCallRecorder::ParallelDeployProc, (LPVOID)a2, 4u, 0);
  if ( Thread )
  {
    if ( *v11 )
      CloseHandle(*v11);
    *v11 = Thread;
    v11[1] = (HANDLE)a2;
    v20 = v11;
    v21[0] = *(_OWORD *)(a2 + 116);
    EnterCriticalSection((LPCRITICAL_SECTION)a3);
    v12 = CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::Add(
            a3 + 40,
            v21,
            &v20);
    LeaveCriticalSection((LPCRITICAL_SECTION)a3);
    if ( v12 >= 0 )
    {
      v11 = 0;
      v20 = 0;
      if ( *(_QWORD *)(a1 + 448) != -8912 )
        CWorkItemManager::RegisterThreadAndSetCurrentPriority(
          (CWorkItemManager *)(*(_QWORD *)(a1 + 448) + 8912LL),
          Thread,
          a4 != 1);
      if ( ResumeThread(Thread) != -1 )
      {
        v12 = 0;
        goto LABEL_34;
      }
      LastError = GetLastError();
      v12 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v12 = LastError;
      if ( v12 >= 0 )
        v12 = -2147418113;
      if ( *(_QWORD *)(a1 + 448) != -8912 )
        CWorkItemManager::DeregisterThread((CWorkItemManager *)(*(_QWORD *)(a1 + 448) + 8912LL), Thread);
      v21[0] = *(_OWORD *)(a2 + 116);
      EnterCriticalSection((LPCRITICAL_SECTION)a3);
      IndexOf = CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>>::GetIndexOf(
                  a3 + 40,
                  v21);
      v18 = 0;
      if ( IndexOf >= *(_DWORD *)(a3 + 60) )
        v18 = -2145124345;
      else
        CSusArrayList<CSusMap<_GUID,tagParallelCallInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<tagParallelCallInfo *>>::_tagMapEntry,CSusMap<_GUID,tagParallelCallInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<tagParallelCallInfo *>>::CMapEntryOps>::RemoveArraySection(
          a3 + 40,
          IndexOf,
          IndexOf,
          1);
      LeaveCriticalSection((LPCRITICAL_SECTION)a3);
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x18B1,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
          (const char *)(unsigned int)v18,
          dwCreationFlags);
      v13 = 6322;
    }
    else
    {
      v13 = 6298;
    }
    goto LABEL_32;
  }
  v12 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x1894,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\Agent\\ClientCallRecorder.cpp",
          v15);
LABEL_34:
  if ( v11 )
  {
    if ( *v11 )
    {
      CloseHandle(*v11);
      *v11 = 0;
    }
    operator delete(v11, (const struct std::nothrow_t *)0x10);
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18004b010  mov     [rsp+arg_18], rbx
0x18004b015  push    rbp
0x18004b016  push    rsi
0x18004b017  push    rdi
0x18004b018  push    r12
0x18004b01a  push    r13
0x18004b01c  push    r14
0x18004b01e  push    r15
0x18004b020  sub     rsp, 50h
0x18004b024  mov     r12b, r9b
0x18004b027  mov     rbp, r8
0x18004b02a  mov     r14, rdx
0x18004b02d  mov     r13, rcx
0x18004b030  test    rdx, rdx
0x18004b033  jnz     short loc_18004B05D
0x18004b035  mov     edx, 1883h; void *
0x18004b03a  mov     ebx, 80004003h
0x18004b03f  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004b046  mov     r9d, ebx; char *
0x18004b049  mov     rcx, [rsp+88h]; this
0x18004b051  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b056  mov     eax, ebx
0x18004b058  jmp     loc_18004B283
0x18004b05d  test    rbp, rbp
0x18004b060  jnz     short loc_18004B069
0x18004b062  mov     edx, 1884h
0x18004b067  jmp     short loc_18004B03A
0x18004b069  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004b070  mov     ecx, 10h; unsigned __int64
0x18004b075  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004b07a  mov     rbx, rax
0x18004b07d  test    rax, rax
0x18004b080  jz      short loc_18004B093
0x18004b082  mov     qword ptr [rax+8], 0
0x18004b08a  mov     qword ptr [rax], 0
0x18004b091  jmp     short loc_18004B095
0x18004b093  xor     ebx, ebx
0x18004b095  mov     rax, rbx
0x18004b098  neg     rax
0x18004b09b  sbb     edi, edi
0x18004b09d  not     edi
0x18004b09f  and     edi, 8007000Eh
0x18004b0a5  test    rbx, rbx
0x18004b0a8  jnz     short loc_18004B0B4
0x18004b0aa  mov     edx, 1888h
0x18004b0af  jmp     loc_18004B23F
0x18004b0b4  mov     [rsp+88h+lpThreadId], 0; lpThreadId
0x18004b0bd  mov     [rsp+88h+dwCreationFlags], 4; int
0x18004b0c5  mov     r9, r14; lpParameter
0x18004b0c8  lea     r8, ?ParallelDeployProc@CClientCallRecorder@@CAKPEAX@Z; lpStartAddress
0x18004b0cf  xor     edx, edx; dwStackSize
0x18004b0d1  xor     ecx, ecx; lpThreadAttributes
0x18004b0d3  call    cs:__imp_CreateThread
0x18004b0d9  mov     rsi, rax
0x18004b0dc  test    rax, rax
0x18004b0df  jnz     short loc_18004B101
0x18004b0e1  mov     rcx, [rsp+88h]; this
0x18004b0e9  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004b0f0  mov     edx, 1894h; void *
0x18004b0f5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004b0fa  mov     edi, eax
0x18004b0fc  jmp     loc_18004B25A
0x18004b101  mov     rcx, [rbx]; hObject
0x18004b104  test    rcx, rcx
0x18004b107  jz      short loc_18004B10F
0x18004b109  call    cs:__imp_CloseHandle
0x18004b10f  mov     [rbx], rsi
0x18004b112  mov     [rbx+8], r14
0x18004b116  mov     [rsp+88h+var_58], rbx
0x18004b11b  movups  xmm0, xmmword ptr [r14+74h]
0x18004b120  movdqu  [rsp+88h+var_50], xmm0
0x18004b126  mov     rcx, rbp; lpCriticalSection
0x18004b129  call    cs:__imp_EnterCriticalSection
0x18004b12f  lea     r15, [rbp+28h]
0x18004b133  lea     r8, [rsp+88h+var_58]
0x18004b138  lea     rdx, [rsp+88h+var_50]
0x18004b13d  mov     rcx, r15
0x18004b140  call    ?Add@?$CSusMap@U_GUID@@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@@@@QEAAJAEBU_GUID@@AEBQEAV?$CSusSortedArrayList@U_GUID@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@@@@Z; CSusMap<_GUID,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> *>>::Add(_GUID const &,CSusSortedArrayList<_GUID,CSusSortedArrayListItemOpsBasic<_GUID>> * const &)
0x18004b145  mov     edi, eax
0x18004b147  mov     rcx, rbp; lpCriticalSection
0x18004b14a  call    cs:__imp_LeaveCriticalSection
0x18004b150  test    edi, edi
0x18004b152  jns     short loc_18004B15E
0x18004b154  mov     edx, 189Ah
0x18004b159  jmp     loc_18004B23F
0x18004b15e  xor     ebx, ebx
0x18004b160  mov     [rsp+88h+var_58], rbx
0x18004b165  mov     rcx, [r13+1C0h]
0x18004b16c  add     rcx, 22D0h; this
0x18004b173  jz      short loc_18004B184
0x18004b175  xor     r12b, 1
0x18004b179  mov     r8b, r12b; bool
0x18004b17c  mov     rdx, rsi; void *
0x18004b17f  call    ?RegisterThreadAndSetCurrentPriority@CWorkItemManager@@QEAAJPEAX_N@Z; CWorkItemManager::RegisterThreadAndSetCurrentPriority(void *,bool)
0x18004b184  mov     rcx, rsi; hThread
0x18004b187  call    cs:__imp_ResumeThread
0x18004b18d  cmp     eax, 0FFFFFFFFh
0x18004b190  jnz     loc_18004B258
0x18004b196  call    cs:__imp_GetLastError
0x18004b19c  movzx   edi, ax
0x18004b19f  or      edi, 80070000h
0x18004b1a5  test    eax, eax
0x18004b1a7  cmovle  edi, eax
0x18004b1aa  mov     eax, 8000FFFFh
0x18004b1af  test    edi, edi
0x18004b1b1  cmovns  edi, eax
0x18004b1b4  mov     rcx, [r13+1C0h]
0x18004b1bb  add     rcx, 22D0h; this
0x18004b1c2  jz      short loc_18004B1CC
0x18004b1c4  mov     rdx, rsi; void *
0x18004b1c7  call    ?DeregisterThread@CWorkItemManager@@QEAAJPEAX@Z; CWorkItemManager::DeregisterThread(void *)
0x18004b1cc  movups  xmm0, xmmword ptr [r14+74h]
0x18004b1d1  movdqu  [rsp+88h+var_50], xmm0
0x18004b1d7  mov     rcx, rbp; lpCriticalSection
0x18004b1da  call    cs:__imp_EnterCriticalSection
0x18004b1e0  lea     rdx, [rsp+88h+var_50]
0x18004b1e5  mov     rcx, r15
0x18004b1e8  call    ?GetIndexOf@?$CSusMap@U_GUID@@PEAVDownloadHeartbeatBundle@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAVDownloadHeartbeatBundle@@@@@@QEBAKAEBU_GUID@@@Z; CSusMap<_GUID,DownloadHeartbeatBundle *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<DownloadHeartbeatBundle *>>::GetIndexOf(_GUID const &)
0x18004b1ed  xor     esi, esi
0x18004b1ef  cmp     eax, [r15+14h]
0x18004b1f3  jnb     short loc_18004B208
0x18004b1f5  lea     r9d, [rsi+1]
0x18004b1f9  mov     r8d, eax
0x18004b1fc  mov     edx, eax
0x18004b1fe  mov     rcx, r15
0x18004b201  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@U_GUID@@PEAUtagParallelCallInfo@@V?$CSusSortedArrayListItemOpsBasic@U_GUID@@@@V?$CSusArrayListItemOpDelete@PEAUtagParallelCallInfo@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<_GUID,tagParallelCallInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<tagParallelCallInfo *>>::_tagMapEntry,CSusMap<_GUID,tagParallelCallInfo *,CSusSortedArrayListItemOpsBasic<_GUID>,CSusArrayListItemOpDelete<tagParallelCallInfo *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18004b206  jmp     short loc_18004B20D
0x18004b208  mov     esi, 80240007h
0x18004b20d  mov     rcx, rbp; lpCriticalSection
0x18004b210  call    cs:__imp_LeaveCriticalSection
0x18004b216  mov     rcx, [rsp+88h]; this
0x18004b21e  test    esi, esi
0x18004b220  jns     short loc_18004B236
0x18004b222  mov     r9d, esi; char *
0x18004b225  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004b22c  mov     edx, 18B1h; void *
0x18004b231  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004b236  test    edi, edi
0x18004b238  jns     short loc_18004B25A
0x18004b23a  mov     edx, 18B2h; void *
0x18004b23f  mov     rcx, [rsp+88h]; this
0x18004b247  mov     r9d, edi; char *
0x18004b24a  lea     r8, aCW1SSrcClientE_27; "C:\\__w\\1\\s\\src\\Client\\Engine\\Age"...
0x18004b251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b256  jmp     short loc_18004B25A
0x18004b258  xor     edi, edi
0x18004b25a  test    rbx, rbx
0x18004b25d  jz      short loc_18004B281
0x18004b25f  mov     rcx, [rbx]; hObject
0x18004b262  test    rcx, rcx
0x18004b265  jz      short loc_18004B274
0x18004b267  call    cs:__imp_CloseHandle
0x18004b26d  mov     qword ptr [rbx], 0
0x18004b274  mov     edx, 10h; struct std::nothrow_t *
0x18004b279  mov     rcx, rbx; void *
0x18004b27c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18004b281  mov     eax, edi
0x18004b283  mov     rbx, [rsp+88h+arg_18]
0x18004b28b  add     rsp, 50h
0x18004b28f  pop     r15
0x18004b291  pop     r14
0x18004b293  pop     r13
0x18004b295  pop     r12
0x18004b297  pop     rdi
0x18004b298  pop     rsi
0x18004b299  pop     rbp
0x18004b29a  retn
```
