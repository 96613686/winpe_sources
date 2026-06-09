# CSusInternalWrapper::Notify(tagNotifyCode,wchar_t const *)

- ea: `0x18004146c`
- end: `0x180041800`
- name: `?Notify@CSusInternalWrapper@@AEAAJW4tagNotifyCode@@PEB_W@Z`
- size: `916`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800071f0`

## callees

- `0x180041410`
- `0x18004146c`
- `0x180090bc8`
- `0x180094274`
- `0x18009b050`
- `0x1800a1960`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800416e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800417d2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800416e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800417d2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800415d1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800415d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041597`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041762`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041597`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180041762`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004163e`
- `api-ms-win-core-synch-l1-1-0!OpenEventW` at `0x18004163e`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800416b3`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800416b3`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800416a1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800416a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041649`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041528`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800415f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041649`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004174c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004174c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041507`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800415c7`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180041507`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800415c7`

## string_xrefs

- `0x180041492`: `Received service shutdown/self-update notification.`
- `0x1800416c2`: `self-update/shutdown event ignored during clean up`
- `0x1800416fc`: `self-update/shutdown event ignored during clean up`
- `0x180041562`: `Wait timed out on ready signal to communicate with the service`
- `0x18004154d`: `Wait on ready signal to communicate with the service or the object shutdown event`
- `0x180041617`: `Wait on clean-up routine completion to handle self-update/shutdown or the object shutdown event`
- `0x18004171d`: `Disallow new connections to the service `
- `0x180041781`: `Unable to notify caller for failure in resuming activities after self-update`

## pseudocode

```c
__int64 __fastcall CSusInternalWrapper::Notify(__int64 a1, int a2, const WCHAR *a3)
{
  int v6; // r14d
  DWORD v7; // eax
  signed int LastError; // eax
  signed int v9; // ebx
  CSusInternalWrapper::CSusCall *v10; // rcx
  __int64 v11; // rax
  DWORD v12; // eax
  DWORD v13; // ecx
  DWORD v14; // eax
  signed int v15; // eax
  HANDLE v16; // rax
  signed int v17; // eax
  HANDLE Thread; // rax
  void *v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  _DWORD *v22; // rcx
  DWORD dwCreationFlags[2]; // [rsp+20h] [rbp-58h]
  DWORD dwCreationFlagsa[2]; // [rsp+20h] [rbp-58h]
  HANDLE Handles; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+38h] [rbp-40h]

  WUTrace(0, 0, 0x10000, 5, 0, L"Received service shutdown/self-update notification.");
  v6 = 0;
  if ( _InterlockedExchange((volatile __int32 *)(a1 + 40), -1) == -1 || a2 )
    return 0;
  Handles = *(HANDLE *)(a1 + 32);
  v27 = *(_QWORD *)(a1 + 16);
  v7 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
  if ( !v7 )
  {
    v9 = -2145124341;
    dwCreationFlags[0] = -2145124341;
    WUTrace(0, 0, 0x10000, 5, *(_QWORD *)dwCreationFlags, L"self-update/shutdown event ignored during clean up");
LABEL_43:
    dwCreationFlags[0] = v9;
    WUTrace(0, 0, 0x10000, 5, *(_QWORD *)dwCreationFlags, L"Disallow new connections to the service ");
    if ( v6 )
    {
      v19 = (void *)_InterlockedExchange64((volatile __int64 *)(a1 + 8), 0);
      if ( v19 )
        CloseHandle(v19);
    }
    v20 = *(_QWORD *)(a1 + 144);
    if ( v20 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(v20 + 96));
      v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 144) + 32LL))(
              *(_QWORD *)(a1 + 144),
              (unsigned int)v9);
      if ( v21 < 0 )
      {
        dwCreationFlagsa[0] = v21;
        WUTrace(
          0,
          0,
          0x10000,
          5,
          *(_QWORD *)dwCreationFlagsa,
          L"Unable to notify caller for failure in resuming activities after self-update");
      }
      v22 = *(_DWORD **)(a1 + 144);
      if ( v22[8] )
      {
        (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v22 + 16LL))(v22);
        *(_DWORD *)(*(_QWORD *)(a1 + 144) + 32LL) = 0;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 144) + 96LL));
    }
    return 0;
  }
  if ( v7 != 1 )
  {
    if ( v7 != 258 )
    {
      if ( v7 == -1 )
      {
        LastError = GetLastError();
        v9 = (unsigned __int16)LastError | 0x80070000;
        if ( LastError <= 0 )
          v9 = LastError;
        if ( v9 >= 0 )
          v9 = -2147418113;
      }
      else
      {
        v9 = -2145120257;
      }
      dwCreationFlags[0] = v9;
      WUTrace(
        0,
        0,
        0x10000,
        5,
        *(_QWORD *)dwCreationFlags,
        L"Wait on ready signal to communicate with the service or the object shutdown event");
      goto LABEL_43;
    }
    WUTrace(0, 0, 0x10000, 5, 0, L"Wait timed out on ready signal to communicate with the service");
  }
  v10 = *(CSusInternalWrapper::CSusCall **)(a1 + 144);
  if ( v10 )
    CSusInternalWrapper::CSusCall::AddRefOnCallForSelfUpdate(v10);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  v11 = *(_QWORD *)(a1 + 24);
  if ( v11 )
  {
    Handles = *(HANDLE *)(a1 + 32);
    v27 = v11;
    v12 = WaitForMultipleObjects(2u, &Handles, 0, 0xFFFFFFFF);
  }
  else
  {
    v12 = WaitForSingleObject(*(HANDLE *)(a1 + 32), 0);
  }
  v13 = v12;
  if ( v12 )
  {
    v14 = v12 - 1;
    if ( !v14 || v14 == 257 )
    {
      SafeCloseHandleNull((void **)(a1 + 24));
      v16 = OpenEventW(0x100000u, 0, a3);
      if ( v16
        && (Handles = (HANDLE)_InterlockedExchange64((volatile __int64 *)(a1 + 8), (__int64)v16),
            SafeCloseHandleNull(&Handles),
            v6 = 1,
            Thread = CreateThread(0, 0, CSusInternalWrapper::CleanUpWorker, (LPVOID)a1, 0, 0),
            (*(_QWORD *)(a1 + 24) = Thread) != 0) )
      {
        ResetEvent(*(HANDLE *)(a1 + 16));
        v9 = 0;
      }
      else
      {
        v17 = GetLastError();
        v9 = (unsigned __int16)v17 | 0x80070000;
        if ( v17 <= 0 )
          v9 = v17;
        if ( v9 >= 0 )
          v9 = -2147418113;
      }
    }
    else
    {
      if ( v13 == -1 )
      {
        v15 = GetLastError();
        v9 = (unsigned __int16)v15 | 0x80070000;
        if ( v15 <= 0 )
          v9 = v15;
        if ( v9 >= 0 )
          v9 = -2147418113;
      }
      else
      {
        v9 = -2145120257;
      }
      dwCreationFlags[0] = v9;
      WUTrace(
        0,
        0,
        0x10000,
        5,
        *(_QWORD *)dwCreationFlags,
        L"Wait on clean-up routine completion to handle self-update/shutdown or the object shutdown event");
    }
  }
  else
  {
    v9 = -2145124341;
    dwCreationFlags[0] = -2145124341;
    WUTrace(0, 0, 0x10000, 5, *(_QWORD *)dwCreationFlags, L"self-update/shutdown event ignored during clean up");
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 96));
  if ( v9 < 0 )
    goto LABEL_43;
  return 0;
}

```

## disassembly

```asm
0x18004146c  mov     r11, rsp
0x18004146f  mov     [r11+10h], rbx
0x180041473  mov     [r11+20h], rbp
0x180041477  push    rsi
0x180041478  push    rdi
0x180041479  push    r12
0x18004147b  push    r13
0x18004147d  push    r14
0x18004147f  sub     rsp, 50h
0x180041483  mov     rax, cs:__security_cookie
0x18004148a  xor     rax, rsp
0x18004148d  mov     [rsp+78h+var_38], rax
0x180041492  lea     rax, aReceivedServic; "Received service shutdown/self-update n"...
0x180041499  mov     rbp, r8
0x18004149c  mov     ebx, edx
0x18004149e  mov     [r11-50h], rax
0x1800414a2  mov     rdi, rcx
0x1800414a5  mov     qword ptr [r11-58h], 0
0x1800414ad  mov     r12d, 5
0x1800414b3  mov     r13d, 10000h
0x1800414b9  mov     r9d, r12d
0x1800414bc  mov     r8d, r13d
0x1800414bf  xor     edx, edx
0x1800414c1  xor     ecx, ecx
0x1800414c3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800414c8  or      eax, 0FFFFFFFFh
0x1800414cb  xor     r14d, r14d
0x1800414ce  xchg    eax, [rdi+28h]
0x1800414d1  cmp     eax, 0FFFFFFFFh
0x1800414d4  jz      loc_1800417D8
0x1800414da  test    ebx, ebx
0x1800414dc  jnz     loc_1800417D8
0x1800414e2  mov     rax, [rdi+20h]
0x1800414e6  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800414eb  mov     [rsp+78h+Handles], rax
0x1800414f0  lea     ecx, [r12-3]; nCount
0x1800414f5  mov     rax, [rdi+10h]
0x1800414f9  or      ebx, 0FFFFFFFFh
0x1800414fc  mov     r9d, ebx; dwMilliseconds
0x1800414ff  mov     [rsp+78h+var_40], rax
0x180041504  xor     r8d, r8d; bWaitAll
0x180041507  call    cs:__imp_WaitForMultipleObjects
0x18004150d  mov     ecx, eax
0x18004150f  test    eax, eax
0x180041511  jz      loc_1800416F7
0x180041517  sub     ecx, 1
0x18004151a  jz      short loc_180041582
0x18004151c  cmp     ecx, 101h
0x180041522  jz      short loc_180041562
0x180041524  cmp     eax, ebx
0x180041526  jnz     short loc_180041548
0x180041528  call    cs:__imp_GetLastError
0x18004152e  movzx   ebx, ax
0x180041531  or      ebx, 80070000h
0x180041537  test    eax, eax
0x180041539  cmovle  ebx, eax
0x18004153c  mov     eax, 8000FFFFh
0x180041541  test    ebx, ebx
0x180041543  cmovns  ebx, eax
0x180041546  jmp     short loc_18004154D
0x180041548  mov     ebx, 80240FFFh
0x18004154d  lea     rax, aWaitOnReadySig; "Wait on ready signal to communicate wit"...
0x180041554  mov     [rsp+78h+lpThreadId], rax
0x180041559  mov     [rsp+78h+dwCreationFlags], ebx
0x18004155d  jmp     loc_18004170E
0x180041562  lea     rax, aWaitTimedOutOn; "Wait timed out on ready signal to commu"...
0x180041569  mov     r9d, r12d
0x18004156c  mov     [rsp+78h+lpThreadId], rax
0x180041571  mov     r8d, r13d
0x180041574  xor     edx, edx
0x180041576  mov     qword ptr [rsp+78h+dwCreationFlags], r14
0x18004157b  xor     ecx, ecx
0x18004157d  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180041582  mov     rcx, [rdi+90h]; this
0x180041589  test    rcx, rcx
0x18004158c  jz      short loc_180041593
0x18004158e  call    ?AddRefOnCallForSelfUpdate@CSusCall@CSusInternalWrapper@@QEAAXXZ; CSusInternalWrapper::CSusCall::AddRefOnCallForSelfUpdate(void)
0x180041593  lea     rcx, [rdi+60h]; lpCriticalSection
0x180041597  call    cs:__imp_EnterCriticalSection
0x18004159d  mov     rcx, [rdi+20h]; hHandle
0x1800415a1  lea     rbx, [rdi+18h]
0x1800415a5  mov     rax, [rbx]
0x1800415a8  test    rax, rax
0x1800415ab  jz      short loc_1800415CF
0x1800415ad  xor     r8d, r8d; bWaitAll
0x1800415b0  mov     [rsp+78h+Handles], rcx
0x1800415b5  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800415b9  mov     [rsp+78h+var_40], rax
0x1800415be  lea     rdx, [rsp+78h+Handles]; lpHandles
0x1800415c3  lea     ecx, [r8+2]; nCount
0x1800415c7  call    cs:__imp_WaitForMultipleObjects
0x1800415cd  jmp     short loc_1800415D7
0x1800415cf  xor     edx, edx; dwMilliseconds
0x1800415d1  call    cs:__imp_WaitForSingleObject
0x1800415d7  mov     ecx, eax
0x1800415d9  test    eax, eax
0x1800415db  jz      loc_1800416BD
0x1800415e1  sub     eax, 1
0x1800415e4  jz      short loc_18004162C
0x1800415e6  cmp     eax, 101h
0x1800415eb  jz      short loc_18004162C
0x1800415ed  cmp     ecx, 0FFFFFFFFh
0x1800415f0  jnz     short loc_180041612
0x1800415f2  call    cs:__imp_GetLastError
0x1800415f8  movzx   ebx, ax
0x1800415fb  or      ebx, 80070000h
0x180041601  test    eax, eax
0x180041603  cmovle  ebx, eax
0x180041606  mov     eax, 8000FFFFh
0x18004160b  test    ebx, ebx
0x18004160d  cmovns  ebx, eax
0x180041610  jmp     short loc_180041617
0x180041612  mov     ebx, 80240FFFh
0x180041617  lea     rax, aWaitOnCleanUpR; "Wait on clean-up routine completion to "...
0x18004161e  mov     [rsp+78h+lpThreadId], rax
0x180041623  mov     [rsp+78h+dwCreationFlags], ebx
0x180041627  jmp     loc_1800416D4
0x18004162c  mov     rcx, rbx; void **
0x18004162f  call    ?SafeCloseHandleNull@@YAXAEAPEAX@Z; SafeCloseHandleNull(void * &)
0x180041634  mov     r8, rbp; lpName
0x180041637  xor     edx, edx; bInheritHandle
0x180041639  mov     ecx, 100000h; dwDesiredAccess
0x18004163e  call    cs:__imp_OpenEventW
0x180041644  test    rax, rax
0x180041647  jnz     short loc_180041669
0x180041649  call    cs:__imp_GetLastError
0x18004164f  movzx   ebx, ax
0x180041652  or      ebx, 80070000h
0x180041658  test    eax, eax
0x18004165a  cmovle  ebx, eax
0x18004165d  mov     eax, 8000FFFFh
0x180041662  test    ebx, ebx
0x180041664  cmovns  ebx, eax
0x180041667  jmp     short loc_1800416E3
0x180041669  xchg    rax, [rdi+8]
0x18004166d  lea     rcx, [rsp+78h+Handles]; void **
0x180041672  mov     [rsp+78h+Handles], rax
0x180041677  call    ?SafeCloseHandleNull@@YAXAEAPEAX@Z; SafeCloseHandleNull(void * &)
0x18004167c  mov     r9, rdi; lpParameter
0x18004167f  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x180041688  lea     r8, ?CleanUpWorker@CSusInternalWrapper@@CAKPEAX@Z; lpStartAddress
0x18004168f  mov     [rsp+78h+dwCreationFlags], 0; dwCreationFlags
0x180041697  xor     edx, edx; dwStackSize
0x180041699  xor     ecx, ecx; lpThreadAttributes
0x18004169b  mov     r14d, 1
0x1800416a1  call    cs:__imp_CreateThread
0x1800416a7  mov     [rbx], rax
0x1800416aa  test    rax, rax
0x1800416ad  jz      short loc_180041649
0x1800416af  mov     rcx, [rdi+10h]; hEvent
0x1800416b3  call    cs:__imp_ResetEvent
0x1800416b9  xor     ebx, ebx
0x1800416bb  jmp     short loc_1800416E3
0x1800416bd  mov     eax, 8024000Bh
0x1800416c2  lea     rdx, aSelfUpdateShut; "self-update/shutdown event ignored duri"...
0x1800416c9  mov     [rsp+78h+lpThreadId], rdx
0x1800416ce  mov     ebx, eax
0x1800416d0  mov     [rsp+78h+dwCreationFlags], eax
0x1800416d4  mov     r9d, r12d
0x1800416d7  mov     r8d, r13d
0x1800416da  xor     edx, edx
0x1800416dc  xor     ecx, ecx
0x1800416de  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800416e3  lea     rcx, [rdi+60h]; lpCriticalSection
0x1800416e7  call    cs:__imp_LeaveCriticalSection
0x1800416ed  test    ebx, ebx
0x1800416ef  jns     loc_1800417D8
0x1800416f5  jmp     short loc_18004171D
0x1800416f7  mov     eax, 8024000Bh
0x1800416fc  lea     rdx, aSelfUpdateShut; "self-update/shutdown event ignored duri"...
0x180041703  mov     [rsp+78h+lpThreadId], rdx
0x180041708  mov     ebx, eax
0x18004170a  mov     [rsp+78h+dwCreationFlags], eax
0x18004170e  mov     r9d, r12d
0x180041711  mov     r8d, r13d
0x180041714  xor     edx, edx
0x180041716  xor     ecx, ecx
0x180041718  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004171d  lea     rax, aDisallowNewCon; "Disallow new connections to the service"...
0x180041724  mov     r9d, r12d
0x180041727  mov     [rsp+78h+lpThreadId], rax
0x18004172c  mov     r8d, r13d
0x18004172f  xor     edx, edx
0x180041731  mov     [rsp+78h+dwCreationFlags], ebx
0x180041735  xor     ecx, ecx
0x180041737  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18004173c  test    r14d, r14d
0x18004173f  jz      short loc_180041752
0x180041741  xor     ecx, ecx
0x180041743  xchg    rcx, [rdi+8]; hObject
0x180041747  test    rcx, rcx
0x18004174a  jz      short loc_180041752
0x18004174c  call    cs:__imp_CloseHandle
0x180041752  mov     rcx, [rdi+90h]
0x180041759  test    rcx, rcx
0x18004175c  jz      short loc_1800417D8
0x18004175e  add     rcx, 60h ; '`'; lpCriticalSection
0x180041762  call    cs:__imp_EnterCriticalSection
0x180041768  mov     rcx, [rdi+90h]
0x18004176f  mov     edx, ebx
0x180041771  mov     rax, [rcx]
0x180041774  mov     rax, [rax+20h]
0x180041778  call    _guard_dispatch_icall
0x18004177d  test    eax, eax
0x18004177f  jns     short loc_1800417A0
0x180041781  lea     rcx, aUnableToNotify; "Unable to notify caller for failure in "...
0x180041788  mov     r9d, r12d
0x18004178b  mov     [rsp+78h+lpThreadId], rcx
0x180041790  mov     r8d, r13d
0x180041793  xor     ecx, ecx
0x180041795  mov     [rsp+78h+dwCreationFlags], eax
0x180041799  xor     edx, edx
0x18004179b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800417a0  mov     rcx, [rdi+90h]
0x1800417a7  cmp     dword ptr [rcx+20h], 0
0x1800417ab  jz      short loc_1800417C7
0x1800417ad  mov     rax, [rcx]
0x1800417b0  mov     rax, [rax+10h]
0x1800417b4  call    _guard_dispatch_icall
0x1800417b9  mov     rax, [rdi+90h]
0x1800417c0  mov     dword ptr [rax+20h], 0
0x1800417c7  mov     rcx, [rdi+90h]
0x1800417ce  add     rcx, 60h ; '`'; lpCriticalSection
0x1800417d2  call    cs:__imp_LeaveCriticalSection
0x1800417d8  xor     eax, eax
0x1800417da  mov     rcx, [rsp+78h+var_38]
0x1800417df  xor     rcx, rsp; StackCookie
0x1800417e2  call    __security_check_cookie
0x1800417e7  lea     r11, [rsp+78h+var_28]
0x1800417ec  mov     rbx, [r11+38h]
0x1800417f0  mov     rbp, [r11+48h]
0x1800417f4  mov     rsp, r11
0x1800417f7  pop     r14
0x1800417f9  pop     r13
0x1800417fb  pop     r12
0x1800417fd  pop     rdi
0x1800417fe  pop     rsi
0x1800417ff  retn
```
