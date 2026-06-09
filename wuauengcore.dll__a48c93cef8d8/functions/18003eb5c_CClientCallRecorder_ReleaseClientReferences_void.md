# CClientCallRecorder::ReleaseClientReferences(void)

- ea: `0x18003eb5c`
- end: `0x18003eecb`
- name: `?ReleaseClientReferences@CClientCallRecorder@@QEAAXXZ`
- size: `879`
- prototype: `void __fastcall(CClientCallRecorder *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18003e420`

## callees

- `0x1800107ec`
- `0x18003ddf8`
- `0x18003eb5c`
- `0x1800c8764`
- `0x1800d3524`
- `0x1800d3590`
- `0x1800d3638`
- `0x18012b618`
- `0x180238960`
- `0x180240cc0`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec19`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ec5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ecae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ee00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ec5e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ecae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ed6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ee00`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18003ebf9`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18003ebf9`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003ee8e`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003ee8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18003ec0a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueue` at `0x18003ec0a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CClientCallRecorder::ReleaseClientReferences(CClientCallRecorder *this)
{
  int v2; // r15d
  HRESULT v3; // eax
  int v4; // r14d
  __int64 i; // rax
  CSusAsyncCall *v6; // rdi
  DWORD v7; // eax
  __int64 v8; // rdx
  int v9; // esi
  __int64 v10; // rdx
  __int64 v11; // r8
  DWORD CurrentThreadId; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 j; // rax
  __int64 v18; // rdi
  DWORD v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  int v22; // esi
  __int64 v23; // r8
  DWORD v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // [rsp+38h] [rbp-39h] BYREF
  _BYTE v31[64]; // [rsp+48h] [rbp-29h] BYREF
  HANDLE TimerQueue; // [rsp+88h] [rbp+17h]

  TimerQueue = 0;
  memset(v31, 0, sizeof(v31));
  v2 = 0;
  WUTrace(0, 0, 1, 5, 0, L"WU client releasing client references ");
  if ( !*((_DWORD *)this + 54) && !*((_DWORD *)this + 44) )
    goto LABEL_42;
  CSusAsyncCallList::MarkCallsForDeletion((CClientCallRecorder *)((char *)this + 152));
  v3 = CoEnableCallCancellation(0);
  v4 = ~v3;
  if ( v3 >= 0 )
  {
    TimerQueue = CreateTimerQueue();
    if ( TimerQueue )
      goto LABEL_7;
    GetLastError();
  }
  v2 = 1;
LABEL_7:
  for ( i = *((_QWORD *)this + 20); ; i = *(_QWORD *)(v16 + 8) )
  {
    *((_QWORD *)this + 23) = i;
    if ( !i )
      break;
    v6 = (CSusAsyncCall *)(i - 8);
    if ( i == 8 )
      break;
    UpdateServiceStatus(3u, 0x15F90u);
    if ( v2 || (v7 = GetCurrentThreadId(), (int)CTimerQueueHelper::PutWorkItemOnThreadPool(v31, v8, v7) < 0) )
    {
      WUTrace(0, 0, 1, 5, 0, L"caller might leak reference for SUS callback interface");
      (*(void (__fastcall **)(CSusAsyncCall *, _QWORD))(*(_QWORD *)v6 + 40LL))(v6, 0);
    }
    else
    {
      v30 = 0;
      v9 = 0;
      if ( *((_DWORD *)v6 + 14) != 6 )
        v9 = CSusAsyncCall::SendOOSCallback(v6);
      (*(void (__fastcall **)(CSusAsyncCall *, __int64 *))(*(_QWORD *)v6 + 40LL))(v6, &v30);
      CTimerQueueHelper::RemoveWorkItemFromThreadPool(v31, v10, v11, 0);
      if ( v9 >= 0 )
      {
        CurrentThreadId = GetCurrentThreadId();
        if ( (int)CTimerQueueHelper::PutWorkItemOnThreadPool(v31, v13, CurrentThreadId) >= 0 )
        {
          if ( v30 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
          CTimerQueueHelper::RemoveWorkItemFromThreadPool(v31, v14, v15, 0);
        }
      }
    }
    v16 = *((_QWORD *)this + 23);
    if ( v16 == *((_QWORD *)this + 21) || !v16 )
      break;
  }
  for ( j = *((_QWORD *)this + 25); ; j = *(_QWORD *)(v29 + 8) )
  {
    *((_QWORD *)this + 28) = j;
    v18 = j;
    if ( !j )
      break;
    UpdateServiceStatus(3u, 0x15F90u);
    if ( v2 || (v19 = GetCurrentThreadId(), (int)CTimerQueueHelper::PutWorkItemOnThreadPool(v31, v20, v19) < 0) )
    {
      WUTrace(0, 0, 1, 5, 0, L"caller might leak reference for ISusNotify");
LABEL_36:
      *(_QWORD *)(v18 + 24) = 0;
      goto LABEL_37;
    }
    if ( *(_QWORD *)(v18 + 24) )
    {
      WUTrace(0, 0, 1, 4, 0, L"Sending shutdown notification to client");
      v22 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**(_QWORD **)(v18 + 24) + 24LL))(
              *(_QWORD *)(v18 + 24),
              1,
              0);
      if ( v22 < 0 )
        WUTrace(0, 0, 1, 5, v22, L"ISusNotify::Notify");
      CTimerQueueHelper::RemoveWorkItemFromThreadPool(v31, v21, v23, 0);
      if ( v22 != -2147418110 )
      {
        v24 = GetCurrentThreadId();
        if ( (int)CTimerQueueHelper::PutWorkItemOnThreadPool(v31, v25, v24) >= 0 )
        {
          v28 = *(_QWORD *)(v18 + 24);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          CTimerQueueHelper::RemoveWorkItemFromThreadPool(v31, v26, v27, 0);
        }
      }
      goto LABEL_36;
    }
LABEL_37:
    v29 = *((_QWORD *)this + 28);
    if ( v29 == *((_QWORD *)this + 26) || !v29 )
      break;
  }
  CTimerQueueHelper::Uninit((CTimerQueueHelper *)v31);
  if ( v4 < 0 )
    CoDisableCallCancellation(0);
LABEL_42:
  CTimerQueueHelper::Uninit((CTimerQueueHelper *)v31);
}

```

## disassembly

```asm
0x18003eb5c  mov     rax, rsp
0x18003eb5f  mov     [rax+10h], rbx
0x18003eb63  mov     [rax+18h], rsi
0x18003eb67  mov     [rax+20h], rdi
0x18003eb6b  push    rbp
0x18003eb6c  push    r12
0x18003eb6e  push    r13
0x18003eb70  push    r14
0x18003eb72  push    r15
0x18003eb74  lea     rbp, [rax-5Fh]
0x18003eb78  sub     rsp, 0A0h
0x18003eb7f  mov     rax, cs:__security_cookie
0x18003eb86  xor     rax, rsp
0x18003eb89  mov     [rbp+57h+var_30], rax
0x18003eb8d  mov     rbx, rcx
0x18003eb90  xor     r12d, r12d
0x18003eb93  mov     [rbp+57h+var_40], r12
0x18003eb97  xor     edx, edx; Val
0x18003eb99  lea     r8d, [r12+40h]; Size
0x18003eb9e  lea     rcx, [rbp+57h+var_80]; void *
0x18003eba2  call    memset
0x18003eba7  nop
0x18003eba8  mov     r15d, r12d
0x18003ebab  lea     rax, aWuClientReleas; "WU client releasing client references "
0x18003ebb2  mov     [rsp+0C0h+var_98], rax
0x18003ebb7  mov     [rsp+0C0h+var_A0], r12
0x18003ebbc  lea     r9d, [r12+5]
0x18003ebc1  lea     r13d, [r12+1]
0x18003ebc6  mov     r8d, r13d
0x18003ebc9  xor     edx, edx
0x18003ebcb  xor     ecx, ecx
0x18003ebcd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ebd2  cmp     [rbx+0D8h], r12d
0x18003ebd9  jnz     short loc_18003EBE8
0x18003ebdb  cmp     [rbx+0B0h], r12d
0x18003ebe2  jz      loc_18003EE95
0x18003ebe8  mov     rcx, rbx
0x18003ebeb  add     rcx, 98h; this
0x18003ebf2  call    ?MarkCallsForDeletion@CSusAsyncCallList@@QEAAXXZ; CSusAsyncCallList::MarkCallsForDeletion(void)
0x18003ebf7  xor     ecx, ecx; pReserved
0x18003ebf9  call    cs:__imp_CoEnableCallCancellation
0x18003ebff  mov     r14d, eax
0x18003ec02  not     r14d
0x18003ec05  test    r14d, r14d
0x18003ec08  jns     short loc_18003EC1F
0x18003ec0a  call    cs:__imp_CreateTimerQueue
0x18003ec10  mov     [rbp+57h+var_40], rax
0x18003ec14  test    rax, rax
0x18003ec17  jnz     short loc_18003EC22
0x18003ec19  call    cs:__imp_GetLastError
0x18003ec1f  mov     r15d, r13d
0x18003ec22  mov     rax, [rbx+0A0h]
0x18003ec29  mov     [rbx+0B8h], rax
0x18003ec30  mov     rdi, rax
0x18003ec33  test    rax, rax
0x18003ec36  jz      loc_18003ED39
0x18003ec3c  add     rdi, 0FFFFFFFFFFFFFFF8h
0x18003ec40  jz      loc_18003ED39
0x18003ec46  mov     edx, 15F90h; unsigned int
0x18003ec4b  mov     ecx, 3; unsigned int
0x18003ec50  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x18003ec55  test    r15d, r15d
0x18003ec58  jnz     loc_18003ECE7
0x18003ec5e  call    cs:__imp_GetCurrentThreadId
0x18003ec64  mov     r8d, eax
0x18003ec67  lea     rcx, [rbp+57h+var_80]
0x18003ec6b  call    ?PutWorkItemOnThreadPool@CTimerQueueHelper@@QEAAJP6AXPEAXE@Z0W4tagWorkItemType@@K@Z; CTimerQueueHelper::PutWorkItemOnThreadPool(void (*)(void *,uchar),void *,tagWorkItemType,ulong)
0x18003ec70  test    eax, eax
0x18003ec72  js      short loc_18003ECE7
0x18003ec74  mov     [rbp+57h+var_90], r12
0x18003ec78  mov     esi, r12d
0x18003ec7b  cmp     dword ptr [rdi+38h], 6
0x18003ec7f  jz      short loc_18003EC8B
0x18003ec81  mov     rcx, rdi; this
0x18003ec84  call    ?SendOOSCallback@CSusAsyncCall@@QEAAJXZ; CSusAsyncCall::SendOOSCallback(void)
0x18003ec89  mov     esi, eax
0x18003ec8b  mov     rdx, [rdi]
0x18003ec8e  mov     rax, [rdx+28h]
0x18003ec92  lea     rdx, [rbp+57h+var_90]
0x18003ec96  mov     rcx, rdi
0x18003ec99  call    _guard_dispatch_icall
0x18003ec9e  xor     r9d, r9d
0x18003eca1  lea     rcx, [rbp+57h+var_80]
0x18003eca5  call    ?RemoveWorkItemFromThreadPool@CTimerQueueHelper@@QEAAXPEAXHW4tagWorkItemType@@@Z; CTimerQueueHelper::RemoveWorkItemFromThreadPool(void *,int,tagWorkItemType)
0x18003ecaa  test    esi, esi
0x18003ecac  js      short loc_18003ED1B
0x18003ecae  call    cs:__imp_GetCurrentThreadId
0x18003ecb4  mov     r8d, eax
0x18003ecb7  lea     rcx, [rbp+57h+var_80]
0x18003ecbb  call    ?PutWorkItemOnThreadPool@CTimerQueueHelper@@QEAAJP6AXPEAXE@Z0W4tagWorkItemType@@K@Z; CTimerQueueHelper::PutWorkItemOnThreadPool(void (*)(void *,uchar),void *,tagWorkItemType,ulong)
0x18003ecc0  test    eax, eax
0x18003ecc2  js      short loc_18003ED1B
0x18003ecc4  mov     rcx, [rbp+57h+var_90]
0x18003ecc8  test    rcx, rcx
0x18003eccb  jz      short loc_18003ECD9
0x18003eccd  mov     rax, [rcx]
0x18003ecd0  mov     rax, [rax+10h]
0x18003ecd4  call    _guard_dispatch_icall
0x18003ecd9  xor     r9d, r9d
0x18003ecdc  lea     rcx, [rbp+57h+var_80]
0x18003ece0  call    ?RemoveWorkItemFromThreadPool@CTimerQueueHelper@@QEAAXPEAXHW4tagWorkItemType@@@Z; CTimerQueueHelper::RemoveWorkItemFromThreadPool(void *,int,tagWorkItemType)
0x18003ece5  jmp     short loc_18003ED1B
0x18003ece7  lea     rax, aCallerMightLea_0; "caller might leak reference for SUS cal"...
0x18003ecee  mov     [rsp+0C0h+var_98], rax
0x18003ecf3  mov     [rsp+0C0h+var_A0], r12
0x18003ecf8  mov     r9d, 5
0x18003ecfe  mov     r8d, r13d
0x18003ed01  xor     edx, edx
0x18003ed03  xor     ecx, ecx
0x18003ed05  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ed0a  mov     rax, [rdi]
0x18003ed0d  xor     edx, edx
0x18003ed0f  mov     rcx, rdi
0x18003ed12  mov     rax, [rax+28h]
0x18003ed16  call    _guard_dispatch_icall
0x18003ed1b  mov     rax, [rbx+0B8h]
0x18003ed22  cmp     rax, [rbx+0A8h]
0x18003ed29  jz      short loc_18003ED39
0x18003ed2b  test    rax, rax
0x18003ed2e  jz      short loc_18003ED39
0x18003ed30  mov     rax, [rax+8]
0x18003ed34  jmp     loc_18003EC29
0x18003ed39  mov     rax, [rbx+0C8h]
0x18003ed40  mov     [rbx+0E0h], rax
0x18003ed47  mov     rdi, rax
0x18003ed4a  test    rax, rax
0x18003ed4d  jz      loc_18003EE7E
0x18003ed53  mov     edx, 15F90h; unsigned int
0x18003ed58  mov     ecx, 3; unsigned int
0x18003ed5d  call    ?UpdateServiceStatus@@YAXKK@Z; UpdateServiceStatus(ulong,ulong)
0x18003ed62  test    r15d, r15d
0x18003ed65  jnz     loc_18003EE39
0x18003ed6b  call    cs:__imp_GetCurrentThreadId
0x18003ed71  mov     r8d, eax
0x18003ed74  lea     rcx, [rbp+57h+var_80]
0x18003ed78  call    ?PutWorkItemOnThreadPool@CTimerQueueHelper@@QEAAJP6AXPEAXE@Z0W4tagWorkItemType@@K@Z; CTimerQueueHelper::PutWorkItemOnThreadPool(void (*)(void *,uchar),void *,tagWorkItemType,ulong)
0x18003ed7d  test    eax, eax
0x18003ed7f  js      loc_18003EE39
0x18003ed85  cmp     [rdi+18h], r12
0x18003ed89  jz      loc_18003EE60
0x18003ed8f  lea     rax, aSendingShutdow; "Sending shutdown notification to client"
0x18003ed96  mov     [rsp+0C0h+var_98], rax
0x18003ed9b  mov     [rsp+0C0h+var_A0], r12
0x18003eda0  lea     r9d, [r15+4]
0x18003eda4  mov     r8d, r13d
0x18003eda7  xor     edx, edx
0x18003eda9  xor     ecx, ecx
0x18003edab  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003edb0  mov     rcx, [rdi+18h]
0x18003edb4  mov     rax, [rcx]
0x18003edb7  xor     r8d, r8d
0x18003edba  mov     edx, r13d
0x18003edbd  mov     rax, [rax+18h]
0x18003edc1  call    _guard_dispatch_icall
0x18003edc6  mov     esi, eax
0x18003edc8  test    eax, eax
0x18003edca  jns     short loc_18003EDEC
0x18003edcc  lea     rax, aIsusnotifyNoti; "ISusNotify::Notify"
0x18003edd3  mov     [rsp+0C0h+var_98], rax
0x18003edd8  mov     dword ptr [rsp+0C0h+var_A0], esi
0x18003eddc  lea     r9d, [r15+5]
0x18003ede0  mov     r8d, r13d
0x18003ede3  xor     edx, edx
0x18003ede5  xor     ecx, ecx
0x18003ede7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003edec  xor     r9d, r9d
0x18003edef  lea     rcx, [rbp+57h+var_80]
0x18003edf3  call    ?RemoveWorkItemFromThreadPool@CTimerQueueHelper@@QEAAXPEAXHW4tagWorkItemType@@@Z; CTimerQueueHelper::RemoveWorkItemFromThreadPool(void *,int,tagWorkItemType)
0x18003edf8  cmp     esi, 80010002h
0x18003edfe  jz      short loc_18003EE5C
0x18003ee00  call    cs:__imp_GetCurrentThreadId
0x18003ee06  mov     r8d, eax
0x18003ee09  lea     rcx, [rbp+57h+var_80]
0x18003ee0d  call    ?PutWorkItemOnThreadPool@CTimerQueueHelper@@QEAAJP6AXPEAXE@Z0W4tagWorkItemType@@K@Z; CTimerQueueHelper::PutWorkItemOnThreadPool(void (*)(void *,uchar),void *,tagWorkItemType,ulong)
0x18003ee12  test    eax, eax
0x18003ee14  js      short loc_18003EE5C
0x18003ee16  mov     rcx, [rdi+18h]
0x18003ee1a  test    rcx, rcx
0x18003ee1d  jz      short loc_18003EE2B
0x18003ee1f  mov     rax, [rcx]
0x18003ee22  mov     rax, [rax+10h]
0x18003ee26  call    _guard_dispatch_icall
0x18003ee2b  xor     r9d, r9d
0x18003ee2e  lea     rcx, [rbp+57h+var_80]
0x18003ee32  call    ?RemoveWorkItemFromThreadPool@CTimerQueueHelper@@QEAAXPEAXHW4tagWorkItemType@@@Z; CTimerQueueHelper::RemoveWorkItemFromThreadPool(void *,int,tagWorkItemType)
0x18003ee37  jmp     short loc_18003EE5C
0x18003ee39  lea     rax, aCallerMightLea; "caller might leak reference for ISusNot"...
0x18003ee40  mov     [rsp+0C0h+var_98], rax
0x18003ee45  mov     [rsp+0C0h+var_A0], r12
0x18003ee4a  mov     r9d, 5
0x18003ee50  mov     r8d, r13d
0x18003ee53  xor     edx, edx
0x18003ee55  xor     ecx, ecx
0x18003ee57  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18003ee5c  mov     [rdi+18h], r12
0x18003ee60  mov     rax, [rbx+0E0h]
0x18003ee67  cmp     rax, [rbx+0D0h]
0x18003ee6e  jz      short loc_18003EE7E
0x18003ee70  test    rax, rax
0x18003ee73  jz      short loc_18003EE7E
0x18003ee75  mov     rax, [rax+8]
0x18003ee79  jmp     loc_18003ED40
0x18003ee7e  lea     rcx, [rbp+57h+var_80]; this
0x18003ee82  call    ?Uninit@CTimerQueueHelper@@QEAAXXZ; CTimerQueueHelper::Uninit(void)
0x18003ee87  test    r14d, r14d
0x18003ee8a  jns     short loc_18003EE95
0x18003ee8c  xor     ecx, ecx; pReserved
0x18003ee8e  call    cs:__imp_CoDisableCallCancellation
0x18003ee94  nop
0x18003ee95  lea     rcx, [rbp+57h+var_80]; this
0x18003ee99  call    ?Uninit@CTimerQueueHelper@@QEAAXXZ; CTimerQueueHelper::Uninit(void)
0x18003ee9e  mov     rcx, [rbp+57h+var_30]
0x18003eea2  xor     rcx, rsp; StackCookie
0x18003eea5  call    __security_check_cookie
0x18003eeaa  lea     r11, [rsp+0C0h+var_20]
0x18003eeb2  mov     rbx, [r11+38h]
0x18003eeb6  mov     rsi, [r11+40h]
0x18003eeba  mov     rdi, [r11+48h]
0x18003eebe  mov     rsp, r11
0x18003eec1  pop     r15
0x18003eec3  pop     r14
0x18003eec5  pop     r13
0x18003eec7  pop     r12
0x18003eec9  pop     rbp
0x18003eeca  retn
```
