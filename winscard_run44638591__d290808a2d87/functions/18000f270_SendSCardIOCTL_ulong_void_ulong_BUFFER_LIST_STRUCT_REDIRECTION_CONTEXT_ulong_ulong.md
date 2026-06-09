# _SendSCardIOCTL(ulong,void *,ulong,_BUFFER_LIST_STRUCT * *,_REDIRECTION_CONTEXT *,ulong,ulong)

- ea: `0x18000f270`
- end: `0x18000f859`
- name: `?_SendSCardIOCTL@@YAJKPEAXKPEAPEAU_BUFFER_LIST_STRUCT@@PEAU_REDIRECTION_CONTEXT@@KK@Z`
- size: `1513`
- prototype: `__int64 __usercall@<rax>(ULONG IoControlCode@<ecx>, PVOID InputBuffer@<rdx>, ULONG InputBufferLength@<r8d>, struct _BUFFER_LIST_STRUCT **@<r9>, LPCRITICAL_SECTION lpCriticalSection, DWORD dwMilliseconds, unsigned int)`
- caller_count: `26`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000396c`
- `0x18000ebe0`
- `0x1800108f0`
- `0x180011318`
- `0x180012a78`
- `0x18001326c`
- `0x1800170f8`
- `0x180018b48`
- `0x1800190cc`
- `0x180019b80`
- `0x180019f1c`
- `0x18002b490`
- `0x18002b734`
- `0x18002ba08`
- `0x18002bd60`
- `0x18002c15c`
- `0x18002c434`
- `0x18002c704`
- `0x18002c9ac`
- `0x18002cc68`
- `0x18002cf64`
- `0x18002d290`
- `0x18002d5bc`
- `0x18002d8b8`
- `0x18002db5c`
- `0x18002dd0c`

## callees

- `0x180007bc0`
- `0x18000f270`
- `0x18000f860`
- `0x18000f9b0`
- `0x180010394`
- `0x180016d20`
- `0x180019644`
- `0x18001991c`
- `0x18001a78c`
- `0x18001be10`
- `0x18002e314`
- `0x18002e3a4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000f450`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000f84e`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000f450`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000f84e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f363`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000f363`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f55c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f7e8`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f55c`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000f7e8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f437`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f838`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f2fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f437`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f838`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f33d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f579`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f33d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f443`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f4c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f579`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f844`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f326`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f741`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f326`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f741`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f632`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f632`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f495`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000f40f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000f40f`
- `ntdll!NtCancelIoFileEx` at `0x18000f731`
- `ntdll!NtCancelIoFileEx` at `0x18000f731`
- `ntdll!NtDeviceIoControlFile` at `0x18000f3b7`
- `ntdll!NtDeviceIoControlFile` at `0x18000f3b7`

## pseudocode

```c
__int64 __fastcall _SendSCardIOCTL(
        __int64 IoControlCode,
        PVOID InputBuffer,
        ULONG InputBufferLength,
        struct _BUFFER_LIST_STRUCT **a4,
        LPCRITICAL_SECTION lpCriticalSection,
        DWORD dwMilliseconds,
        unsigned int size)
{
  ULONG v10; // r12d
  int v11; // edx
  int v12; // r8d
  int v13; // r9d
  unsigned int RdpdrHandle; // ebp
  __int64 v15; // rcx
  char v16; // bp
  struct _BUFFER_LIST_STRUCT *Buffer; // rax
  struct _BUFFER_LIST_STRUCT *v18; // rcx
  HANDLE v19; // rdx
  __int64 v20; // rcx
  unsigned int Status; // esi
  int v22; // r9d
  DWORD v23; // eax
  int v24; // r8d
  int v25; // r9d
  int v27; // r9d
  int v28; // r9d
  char LastError; // al
  int v30; // r9d
  _QWORD *v31; // rcx
  int v32; // edx
  int v33; // r9d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-88h] BYREF
  __int128 v35; // [rsp+60h] [rbp-78h] BYREF
  HANDLE Handles[2]; // [rsp+70h] [rbp-68h] BYREF
  HANDLE OwningThread; // [rsp+80h] [rbp-58h]

  OwningThread = 0;
  *a4 = 0;
  IoStatusBlock = 0;
  v10 = IoControlCode;
  v35 = 0;
  *(_OWORD *)Handles = 0;
  WppTraceIndent(IoControlCode, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_slD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, v13, v10, size);
  }
  EnterCriticalSection(lpCriticalSection);
  if ( LOBYTE(lpCriticalSection[1].DebugInfo) )
    goto LABEL_23;
  RdpdrHandle = RedirectionContextCreateRdpdrHandle(lpCriticalSection);
  if ( RdpdrHandle )
  {
    LeaveCriticalSection(lpCriticalSection);
    return RdpdrHandle;
  }
  if ( !WaitForSingleObject(lpCriticalSection[1].OwningThread, 0) )
  {
    WppTraceIndent(v15, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
        v27,
        v10);
    }
LABEL_23:
    LeaveCriticalSection(lpCriticalSection);
    return 3221225760LL;
  }
  ++LODWORD(lpCriticalSection[1].LockSemaphore);
  v16 = 1;
  LeaveCriticalSection(lpCriticalSection);
  Buffer = GetBuffer(size);
  *a4 = Buffer;
  if ( !Buffer )
  {
    Status = -1073741801;
    goto LABEL_15;
  }
  Handles[0] = CreateEventW(0, 1, 0, 0);
  v19 = Handles[0];
  if ( !Handles[0] )
  {
    Status = -1073741670;
    goto LABEL_15;
  }
  while ( 1 )
  {
    Status = NtDeviceIoControlFile(
               lpCriticalSection[2].DebugInfo,
               v19,
               0,
               0,
               &IoStatusBlock,
               v10,
               InputBuffer,
               InputBufferLength,
               *((PVOID *)*a4 + 2),
               *((_DWORD *)*a4 + 6));
    if ( Status != 259 )
      goto LABEL_12;
    WppTraceIndent(v20, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
        v22,
        v10);
    }
    Handles[1] = _GetProcessDetachEventHandle();
    if ( !Handles[1] )
    {
      Status = -1073741670;
      goto LABEL_13;
    }
    OwningThread = lpCriticalSection[1].OwningThread;
    v23 = WaitForMultipleObjects(3u, Handles, 0, dwMilliseconds);
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        WppTraceIndent(v20, 2);
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
          goto LABEL_59;
        }
        v32 = 25;
      }
      else
      {
        if ( v23 != 2 )
        {
          if ( v23 == 258 )
          {
            WppTraceIndent(v20, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_sDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
                (_DWORD)WPP_pszIndent,
                dwMilliseconds,
                v10);
            }
          }
          else if ( v23 == -1 )
          {
            WppTraceIndent(v20, 2);
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              LastError = GetLastError();
              WPP_SF_sDD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                28,
                (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
                (_DWORD)WPP_pszIndent,
                LastError,
                v10);
            }
          }
          goto LABEL_59;
        }
        WppTraceIndent(v20, 2);
        v31 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
        {
LABEL_59:
          NtCancelIoFileEx(lpCriticalSection[2].DebugInfo, &IoStatusBlock, &v35);
          WaitForSingleObject(Handles[0], 0xFFFFFFFF);
          goto LABEL_11;
        }
        v32 = 26;
      }
      WPP_SF_sd(v31[2], v32, (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids, v30, v10);
      goto LABEL_59;
    }
LABEL_11:
    Status = IoStatusBlock.Status;
    _InterlockedDecrement(&g_lProcessDetachEventClients);
LABEL_12:
    if ( Status != -1073741789 )
      goto LABEL_13;
    WppTraceIndent(v20, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
        v28,
        v10);
    }
    if ( !(unsigned int)GrowBuffer(*a4) )
      break;
    ResetEvent(Handles[0]);
    v19 = Handles[0];
  }
  Status = -1073741801;
LABEL_13:
  EnterCriticalSection(lpCriticalSection);
  --LODWORD(lpCriticalSection[1].LockSemaphore);
  LeaveCriticalSection(lpCriticalSection);
  v16 = 0;
  WakeAllConditionVariable((PCONDITION_VARIABLE)&lpCriticalSection[1].LockCount);
  if ( Status )
  {
    if ( Status != -1073741667 )
    {
      if ( Status != -1073741536 )
      {
LABEL_73:
        *((_DWORD *)*a4 + 7) = 0;
        goto LABEL_15;
      }
      WppTraceIndent(v18, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          (unsigned int)WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids,
          v33,
          lpCriticalSection[1].SpinCount);
      }
      ResetEvent(*(HANDLE *)&lpCriticalSection[3].LockCount);
    }
    _SetStartedEventToCorrectState((struct _REDIRECTION_CONTEXT *)lpCriticalSection);
    goto LABEL_73;
  }
  v18 = *a4;
  *((_DWORD *)*a4 + 7) = IoStatusBlock.Information;
LABEL_15:
  WppTraceIndent(v18, 2);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_sld(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v24, v25, v10, Status);
  }
  if ( v16 )
  {
    EnterCriticalSection(lpCriticalSection);
    --LODWORD(lpCriticalSection[1].LockSemaphore);
    LeaveCriticalSection(lpCriticalSection);
    WakeAllConditionVariable((PCONDITION_VARIABLE)&lpCriticalSection[1].LockCount);
  }
  if ( Handles[0] )
    CloseHandle(Handles[0]);
  return Status;
}

```

## disassembly

```asm
0x18000f270  push    rbx
0x18000f272  push    rsi
0x18000f273  push    rdi
0x18000f274  push    r12
0x18000f276  push    r13
0x18000f278  push    r14
0x18000f27a  push    r15
0x18000f27c  sub     rsp, 0A0h
0x18000f283  mov     rax, cs:__security_cookie
0x18000f28a  xor     rax, rsp
0x18000f28d  mov     [rsp+0D8h+var_50], rax
0x18000f295  mov     rbx, [rsp+0D8h+lpCriticalSection]
0x18000f29d  xorps   xmm0, xmm0
0x18000f2a0  mov     esi, dword ptr [rsp+0D8h+size]
0x18000f2a7  xor     eax, eax
0x18000f2a9  mov     r14, rdx
0x18000f2ac  mov     [rsp+0D8h+var_58], rax
0x18000f2b4  xorps   xmm1, xmm1
0x18000f2b7  mov     [r9], rax
0x18000f2ba  mov     edx, 2
0x18000f2bf  mov     rdi, r9
0x18000f2c2  movups  xmmword ptr [rsp+0D8h+var_88], xmm0
0x18000f2c7  mov     r15d, r8d
0x18000f2ca  mov     r12d, ecx
0x18000f2cd  movups  [rsp+0D8h+var_78], xmm1
0x18000f2d2  movups  xmmword ptr [rsp+0D8h+Handles], xmm0
0x18000f2d7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f2e3  lea     r13, WPP_GLOBAL_Control
0x18000f2ea  cmp     rcx, r13
0x18000f2ed  jnz     loc_18000F502
0x18000f2f3  mov     rcx, rbx; lpCriticalSection
0x18000f2f6  mov     [rsp+0D8h+var_40], rbp
0x18000f2fe  call    cs:__imp_EnterCriticalSection
0x18000f304  cmp     byte ptr [rbx+28h], 0
0x18000f308  jnz     loc_18000F4BF
0x18000f30e  mov     rcx, rbx; lpCriticalSection
0x18000f311  call    ?RedirectionContextCreateRdpdrHandle@@YAJPEAU_REDIRECTION_CONTEXT@@@Z; RedirectionContextCreateRdpdrHandle(_REDIRECTION_CONTEXT *)
0x18000f316  mov     ebp, eax
0x18000f318  test    eax, eax
0x18000f31a  jnz     loc_18000F576
0x18000f320  mov     rcx, [rbx+38h]; hHandle
0x18000f324  xor     edx, edx; dwMilliseconds
0x18000f326  call    cs:__imp_WaitForSingleObject
0x18000f32c  test    eax, eax
0x18000f32e  jz      loc_18000F49F
0x18000f334  inc     dword ptr [rbx+40h]
0x18000f337  mov     rcx, rbx; lpCriticalSection
0x18000f33a  mov     bpl, 1
0x18000f33d  call    cs:__imp_LeaveCriticalSection
0x18000f343  mov     ecx, esi; size
0x18000f345  call    ?GetBuffer@@YAPEAU_BUFFER_LIST_STRUCT@@K@Z; GetBuffer(ulong)
0x18000f34a  mov     [rdi], rax
0x18000f34d  test    rax, rax
0x18000f350  jz      loc_18000F4F8
0x18000f356  xor     r9d, r9d; lpName
0x18000f359  xor     r8d, r8d; bInitialState
0x18000f35c  mov     edx, 1; bManualReset
0x18000f361  xor     ecx, ecx; lpEventAttributes
0x18000f363  call    cs:__imp_CreateEventW
0x18000f369  mov     [rsp+0D8h+Handles], rax
0x18000f36e  mov     rdx, rax; Event
0x18000f371  test    rax, rax
0x18000f374  jz      loc_18000F56C
0x18000f37a  mov     ebp, [rsp+0D8h+dwMilliseconds]
0x18000f381  mov     rcx, [rdi]
0x18000f384  xor     r9d, r9d; ApcContext
0x18000f387  xor     r8d, r8d; ApcRoutine
0x18000f38a  mov     eax, [rcx+18h]
0x18000f38d  mov     [rsp+0D8h+OutputBufferLength], eax; OutputBufferLength
0x18000f391  mov     rax, [rcx+10h]
0x18000f395  mov     rcx, [rbx+50h]; FileHandle
0x18000f399  mov     [rsp+0D8h+OutputBuffer], rax; OutputBuffer
0x18000f39e  lea     rax, [rsp+0D8h+var_88]
0x18000f3a3  mov     [rsp+0D8h+InputBufferLength], r15d; InputBufferLength
0x18000f3a8  mov     [rsp+0D8h+InputBuffer], r14; InputBuffer
0x18000f3ad  mov     [rsp+0D8h+IoControlCode], r12d; IoControlCode
0x18000f3b2  mov     [rsp+0D8h+IoStatusBlock], rax; IoStatusBlock
0x18000f3b7  call    cs:__imp_NtDeviceIoControlFile
0x18000f3bd  mov     esi, eax
0x18000f3bf  cmp     eax, 103h
0x18000f3c4  jnz     short loc_18000F428
0x18000f3c6  mov     edx, 2
0x18000f3cb  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f3d0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f3d7  cmp     rcx, r13
0x18000f3da  jnz     loc_18000F5AF
0x18000f3e0  call    ?_GetProcessDetachEventHandle@@YAPEAXXZ; _GetProcessDetachEventHandle(void)
0x18000f3e5  mov     [rsp+0D8h+Handles+8], rax
0x18000f3ea  test    rax, rax
0x18000f3ed  jz      loc_18000F77F
0x18000f3f3  mov     rax, [rbx+38h]
0x18000f3f7  lea     rdx, [rsp+0D8h+Handles]; lpHandles
0x18000f3fc  mov     r9d, ebp; dwMilliseconds
0x18000f3ff  mov     [rsp+0D8h+var_58], rax
0x18000f407  xor     r8d, r8d; bWaitAll
0x18000f40a  mov     ecx, 3; nCount
0x18000f40f  call    cs:__imp_WaitForMultipleObjects
0x18000f415  test    eax, eax
0x18000f417  jnz     loc_18000F5E2
0x18000f41d  mov     esi, dword ptr [rsp+0D8h+var_88]
0x18000f421  lock dec cs:?g_lProcessDetachEventClients@@3JA; long g_lProcessDetachEventClients
0x18000f428  cmp     esi, 0C0000023h
0x18000f42e  jz      loc_18000F52D
0x18000f434  mov     rcx, rbx; lpCriticalSection
0x18000f437  call    cs:__imp_EnterCriticalSection
0x18000f43d  dec     dword ptr [rbx+40h]
0x18000f440  mov     rcx, rbx; lpCriticalSection
0x18000f443  call    cs:__imp_LeaveCriticalSection
0x18000f449  lea     rcx, [rbx+30h]; ConditionVariable
0x18000f44d  xor     bpl, bpl
0x18000f450  call    cs:__imp_WakeAllConditionVariable
0x18000f456  test    esi, esi
0x18000f458  jnz     loc_18000F793
0x18000f45e  mov     rcx, [rdi]
0x18000f461  mov     eax, dword ptr [rsp+0D8h+var_88.Information]
0x18000f465  mov     [rcx+1Ch], eax
0x18000f468  mov     edx, 2
0x18000f46d  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f472  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f479  cmp     rcx, r13
0x18000f47c  jnz     loc_18000F805
0x18000f482  test    bpl, bpl
0x18000f485  jnz     loc_18000F835
0x18000f48b  mov     rcx, [rsp+0D8h+Handles]; hObject
0x18000f490  test    rcx, rcx
0x18000f493  jz      short loc_18000F49B
0x18000f495  call    cs:__imp_CloseHandle
0x18000f49b  mov     eax, esi
0x18000f49d  jmp     short loc_18000F4CD
0x18000f49f  mov     edx, 2
0x18000f4a4  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f4a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f4b0  cmp     rcx, r13
0x18000f4b3  jz      short loc_18000F4BF
0x18000f4b5  test    byte ptr [rcx+1Ch], 8
0x18000f4b9  jnz     loc_18000F586
0x18000f4bf  mov     rcx, rbx; lpCriticalSection
0x18000f4c2  call    cs:__imp_LeaveCriticalSection
0x18000f4c8  mov     eax, 0C0000120h
0x18000f4cd  mov     rbp, [rsp+0D8h+var_40]
0x18000f4d5  mov     rcx, [rsp+0D8h+var_50]
0x18000f4dd  xor     rcx, rsp; StackCookie
0x18000f4e0  call    __security_check_cookie
0x18000f4e5  add     rsp, 0A0h
0x18000f4ec  pop     r15
0x18000f4ee  pop     r14
0x18000f4f0  pop     r13
0x18000f4f2  pop     r12
0x18000f4f4  pop     rdi
0x18000f4f5  pop     rsi
0x18000f4f6  pop     rbx
0x18000f4f7  retn
0x18000f4f8  mov     esi, 0C0000017h
0x18000f4fd  jmp     loc_18000F468
0x18000f502  test    byte ptr [rcx+1Ch], 8
0x18000f506  jz      loc_18000F2F3
0x18000f50c  cmp     byte ptr [rcx+19h], 4
0x18000f510  jb      loc_18000F2F3
0x18000f516  mov     rcx, [rcx+10h]
0x18000f51a  mov     [rsp+0D8h+IoControlCode], esi
0x18000f51e  mov     dword ptr [rsp+0D8h+IoStatusBlock], r12d
0x18000f523  call    WPP_SF_slD
0x18000f528  jmp     loc_18000F2F3
0x18000f52d  mov     edx, 2
0x18000f532  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f537  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f53e  cmp     rcx, r13
0x18000f541  jnz     loc_18000F74C
0x18000f547  mov     rcx, [rdi]; struct _BUFFER_LIST_STRUCT *
0x18000f54a  call    ?GrowBuffer@@YAHPEAU_BUFFER_LIST_STRUCT@@@Z; GrowBuffer(_BUFFER_LIST_STRUCT *)
0x18000f54f  test    eax, eax
0x18000f551  jz      loc_18000F789
0x18000f557  mov     rcx, [rsp+0D8h+Handles]; hEvent
0x18000f55c  call    cs:__imp_ResetEvent
0x18000f562  mov     rdx, [rsp+0D8h+Handles]
0x18000f567  jmp     loc_18000F381
0x18000f56c  mov     esi, 0C000009Ah
0x18000f571  jmp     loc_18000F468
0x18000f576  mov     rcx, rbx; lpCriticalSection
0x18000f579  call    cs:__imp_LeaveCriticalSection
0x18000f57f  mov     eax, ebp
0x18000f581  jmp     loc_18000F4CD
0x18000f586  cmp     byte ptr [rcx+19h], 4
0x18000f58a  jb      loc_18000F4BF
0x18000f590  mov     rcx, [rcx+10h]
0x18000f594  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f59b  mov     edx, 17h
0x18000f5a0  mov     dword ptr [rsp+0D8h+IoStatusBlock], r12d
0x18000f5a5  call    WPP_SF_sd
0x18000f5aa  jmp     loc_18000F4BF
0x18000f5af  test    byte ptr [rcx+1Ch], 8
0x18000f5b3  jz      loc_18000F3E0
0x18000f5b9  cmp     byte ptr [rcx+19h], 4
0x18000f5bd  jb      loc_18000F3E0
0x18000f5c3  mov     rcx, [rcx+10h]
0x18000f5c7  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f5ce  mov     edx, 18h
0x18000f5d3  mov     dword ptr [rsp+0D8h+IoStatusBlock], r12d
0x18000f5d8  call    WPP_SF_sd
0x18000f5dd  jmp     loc_18000F3E0
0x18000f5e2  cmp     eax, 1
0x18000f5e5  jz      loc_18000F6E7
0x18000f5eb  cmp     eax, 2
0x18000f5ee  jz      loc_18000F6BE
0x18000f5f4  cmp     eax, 102h
0x18000f5f9  jz      short loc_18000F669
0x18000f5fb  cmp     eax, 0FFFFFFFFh
0x18000f5fe  jnz     loc_18000F723
0x18000f604  mov     edx, 2
0x18000f609  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f60e  mov     rax, cs:WPP_GLOBAL_Control
0x18000f615  cmp     rax, r13
0x18000f618  jz      loc_18000F723
0x18000f61e  test    byte ptr [rax+1Ch], 8
0x18000f622  jz      loc_18000F723
0x18000f628  cmp     byte ptr [rax+19h], 4
0x18000f62c  jb      loc_18000F723
0x18000f632  call    cs:__imp_GetLastError
0x18000f638  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f63f  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f646  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f64d  mov     edx, 1Ch
0x18000f652  mov     [rsp+0D8h+IoControlCode], r12d
0x18000f657  mov     dword ptr [rsp+0D8h+IoStatusBlock], eax
0x18000f65b  mov     rcx, [rcx+10h]
0x18000f65f  call    WPP_SF_sDD
0x18000f664  jmp     loc_18000F723
0x18000f669  mov     edx, 2
0x18000f66e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f673  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f67a  cmp     rcx, r13
0x18000f67d  jz      loc_18000F723
0x18000f683  test    byte ptr [rcx+1Ch], 8
0x18000f687  jz      loc_18000F723
0x18000f68d  cmp     byte ptr [rcx+19h], 4
0x18000f691  jb      loc_18000F723
0x18000f697  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000f69e  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f6a5  mov     rcx, [rcx+10h]
0x18000f6a9  mov     edx, 1Bh
0x18000f6ae  mov     [rsp+0D8h+IoControlCode], r12d
0x18000f6b3  mov     dword ptr [rsp+0D8h+IoStatusBlock], ebp
0x18000f6b7  call    WPP_SF_sDD
0x18000f6bc  jmp     short loc_18000F723
0x18000f6be  mov     edx, 2
0x18000f6c3  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6cf  cmp     rcx, r13
0x18000f6d2  jz      short loc_18000F723
0x18000f6d4  test    byte ptr [rcx+1Ch], 8
0x18000f6d8  jz      short loc_18000F723
0x18000f6da  cmp     byte ptr [rcx+19h], 4
0x18000f6de  jb      short loc_18000F723
0x18000f6e0  mov     edx, 1Ah
0x18000f6e5  jmp     short loc_18000F70E
0x18000f6e7  mov     edx, 2
0x18000f6ec  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f6f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f6f8  cmp     rcx, r13
0x18000f6fb  jz      short loc_18000F723
0x18000f6fd  test    byte ptr [rcx+1Ch], 8
0x18000f701  jz      short loc_18000F723
0x18000f703  cmp     byte ptr [rcx+19h], 4
0x18000f707  jb      short loc_18000F723
0x18000f709  mov     edx, 19h
0x18000f70e  mov     rcx, [rcx+10h]
0x18000f712  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f719  mov     dword ptr [rsp+0D8h+IoStatusBlock], r12d
0x18000f71e  call    WPP_SF_sd
0x18000f723  mov     rcx, [rbx+50h]
0x18000f727  lea     r8, [rsp+0D8h+var_78]
0x18000f72c  lea     rdx, [rsp+0D8h+var_88]
0x18000f731  call    cs:__imp_NtCancelIoFileEx
0x18000f737  mov     rcx, [rsp+0D8h+Handles]; hHandle
0x18000f73c  mov     edx, 0FFFFFFFFh; dwMilliseconds
0x18000f741  call    cs:__imp_WaitForSingleObject
0x18000f747  jmp     loc_18000F41D
0x18000f74c  test    byte ptr [rcx+1Ch], 8
0x18000f750  jz      loc_18000F547
0x18000f756  cmp     byte ptr [rcx+19h], 4
0x18000f75a  jb      loc_18000F547
0x18000f760  mov     rcx, [rcx+10h]
0x18000f764  lea     r8, WPP_2af0b27572d33e35ea5753758eafaaae_Traceguids
0x18000f76b  mov     edx, 1Dh
0x18000f770  mov     dword ptr [rsp+0D8h+IoStatusBlock], r12d
0x18000f775  call    WPP_SF_sd
0x18000f77a  jmp     loc_18000F547
0x18000f77f  mov     esi, 0C000009Ah
0x18000f784  jmp     loc_18000F434
0x18000f789  mov     esi, 0C0000017h
0x18000f78e  jmp     loc_18000F434
0x18000f793  cmp     esi, 0C000009Dh
0x18000f799  jz      short loc_18000F7EE
0x18000f79b  cmp     esi, 0C0000120h
0x18000f7a1  jnz     short loc_18000F7F6
0x18000f7a3  mov     edx, 2
0x18000f7a8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000f7ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18000f7b4  cmp     rcx, r13
  ... truncated ...
```
