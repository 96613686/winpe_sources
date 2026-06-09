# QueueServerInstallEntry

- ea: `0x180008d20`
- end: `0x180009417`
- name: `QueueServerInstallEntry`
- size: `1783`
- prototype: `_BOOL8 __fastcall(int, void *, _WORD *, _WORD *, __int64, __int64, int, unsigned int, int, int)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800083b0`
- `0x180009420`
- `0x180009690`

## callees

- `0x1800010e0`
- `0x180001110`
- `0x180002750`
- `0x180008d20`
- `0x180009bc4`
- `0x18000a210`
- `0x18000a9e0`
- `0x1800106dc`
- `0x18001078c`
- `0x180011d38`
- `0x180011d7c`
- `0x1800120b0`
- `0x180013590`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180008ef4`
- `ntdll!RtlAllocateHeap` at `0x180008fb6`
- `ntdll!RtlAllocateHeap` at `0x180008ef4`
- `ntdll!RtlAllocateHeap` at `0x180008fb6`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180008f9c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009030`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800090cf`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009117`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000915f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800091a2`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180008f9c`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009030`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800090cf`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180009117`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18000915f`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800091a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000938f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b80`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b9e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e20`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000938f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b80`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180018b9e`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008d97`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x180008d97`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000936c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000936c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093a9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800093a9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000926b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000926b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800093ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000937b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009206`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009279`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000937b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800093b6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800091fc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800091fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800093e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800091d0`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009060`
- `api-ms-win-devices-config-l1-1-1!CM_Locate_DevNodeW` at `0x180009060`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Depth` at `0x180009074`
- `api-ms-win-devices-config-l1-1-1!CM_Get_Depth` at `0x180009074`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008dcd`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e09`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e66`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e97`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008dcd`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e09`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e66`
- `DEVRTL!DevRtlWriteTextLog` at `0x180008e97`

## string_xrefs

- `0x180008db8`: `Device installation disabled`
- `0x180008df4`: `Installation deferred (too early)`
- `0x180008e41`: `Nested installation`
- `0x180008e3a`: `Installation`
- `0x180008e82`: `Recursive asynchronous installation requests are not supported!`

## pseudocode

```c
_BOOL8 __fastcall QueueServerInstallEntry(
        int a1,
        void *a2,
        _WORD *a3,
        _WORD *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int a8,
        int a9,
        int a10)
{
  __int64 v12; // r14
  HANDLE EventW; // r12
  DWORD v14; // r15d
  __int64 v15; // r13
  int v16; // r12d
  const wchar_t *v17; // rax
  _OWORD *Heap; // rax
  __int64 v19; // rcx
  _WORD *v20; // rax
  NTSTATUS v21; // edx
  __int64 v22; // rbx
  _WORD *v23; // rdx
  ULONG LastError; // eax
  __int64 v25; // rcx
  _WORD *v26; // rcx
  NTSTATUS v27; // ecx
  _DWORD *v28; // rsi
  WCHAR *v29; // rdx
  __int64 v30; // rcx
  _WORD *v31; // rax
  NTSTATUS v32; // edx
  __int64 v33; // rbx
  PVOID v34; // rax
  NTSTATUS v35; // eax
  NTSTATUS v36; // ecx
  __int64 v37; // rbx
  PVOID v38; // rax
  HANDLE CurrentProcess; // rbx
  HANDLE v40; // rax
  int v41; // ebx
  ULONG *v42; // rax
  __int64 i; // rcx
  _QWORD *v44; // rax
  int v45; // edx
  __int64 v46; // rcx
  DWORD v47; // ecx
  DEVNODE pdnDevInst; // [rsp+40h] [rbp-58h] BYREF
  ULONG v50; // [rsp+44h] [rbp-54h] BYREF
  int v51; // [rsp+48h] [rbp-50h]
  int v52; // [rsp+4Ch] [rbp-4Ch]
  void *v53; // [rsp+50h] [rbp-48h]
  __int64 v54; // [rsp+58h] [rbp-40h] BYREF
  HANDLE TargetHandle[2]; // [rsp+60h] [rbp-38h] BYREF

  v12 = 0;
  v50 = 0;
  EventW = 0;
  v53 = 0;
  TargetHandle[0] = 0;
  if ( (a9 & 1) != 0 && !a2 )
  {
    v14 = 13;
    goto LABEL_109;
  }
  WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
  v15 = a6;
  if ( ServerInstallProcessingEnabled )
    goto LABEL_10;
  if ( !ServerInstallQueuingEnabled )
  {
    DevRtlWriteTextLog(a6, 0x2000000, 2, "Device installation disabled");
LABEL_10:
    v16 = a10;
    goto LABEL_11;
  }
  v16 = a10;
  if ( (a10 & 1) == 0 )
  {
    v16 = a10 | 1;
    if ( a6 )
      DevRtlWriteTextLog(a6, 0x2000000, 4, "Installation deferred (too early)");
  }
LABEL_11:
  ReleaseMutex(hMutex);
  v51 = v16 & 1;
  if ( (v16 & 1) != 0 && (a9 & 1) != 0 )
  {
    v17 = L"Nested installation";
    if ( (v16 & 2) == 0 )
      v17 = L"Installation";
    DevRtlWriteTextLog(a6, 0x2000000, 4, "%ws will be processed asynchronously", v17);
  }
  if ( (v16 & 2) != 0 && (unsigned int)IsActiveServerEntryNested(a8) )
  {
    DevRtlWriteTextLog(a6, 0x2000000, 1, "Recursive asynchronous installation requests are not supported!");
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids, a3);
    v14 = 50;
    EventW = v53;
    goto LABEL_109;
  }
  v14 = 8;
  Heap = RtlAllocateHeap(PnpHeapHandle, 8u, 0x70u);
  v12 = (__int64)Heap;
  if ( !Heap )
  {
    EventW = v53;
    goto LABEL_109;
  }
  *(_OWORD *)((char *)Heap + 20) = 0;
  *(_OWORD *)((char *)Heap + 36) = 0;
  *(_OWORD *)((char *)Heap + 52) = 0;
  *(_OWORD *)((char *)Heap + 68) = 0;
  *(_OWORD *)((char *)Heap + 84) = 0;
  Heap[6] = 0;
  *((_QWORD *)Heap + 1) = Heap;
  *(_QWORD *)Heap = Heap;
  *((_DWORD *)Heap + 4) = a1;
  if ( !a3 )
  {
    v21 = -1073741811;
LABEL_34:
    LastError = RtlNtStatusToDosErrorNoTeb(v21);
    EventW = v53;
LABEL_108:
    v14 = LastError;
    goto LABEL_109;
  }
  v19 = 200;
  v20 = a3;
  v21 = 0;
  do
  {
    if ( !*v20 )
      break;
    ++v20;
    --v19;
  }
  while ( v19 );
  if ( !v19 )
    v21 = -1073741811;
  if ( v21 < 0 )
    goto LABEL_34;
  v22 = 200 - v19 + 1;
  v54 = v22;
  if ( (unsigned __int64)(2 * v22) <= 0xF42400 )
    v23 = RtlAllocateHeap(PnpHeapHandle, 8u, 2 * v22);
  else
    v23 = 0;
  *(_QWORD *)(v12 + 32) = v23;
  if ( !v23 )
  {
    EventW = v53;
    goto LABEL_109;
  }
  v25 = 2147483646;
  if ( (unsigned __int64)(v22 - 1) > 0x7FFFFFFE )
  {
    v27 = -1073741811;
    if ( v22 )
      *v23 = 0;
  }
  else
  {
    do
    {
      if ( !v25 )
        break;
      if ( !*a3 )
        break;
      *v23++ = *a3++;
      --v25;
      --v22;
    }
    while ( v22 );
    v26 = v23 - 1;
    if ( v22 )
      v26 = v23;
    *v26 = 0;
    v27 = -2147483643;
    if ( v22 )
      v27 = 0;
  }
  if ( v27 < 0 )
  {
    LastError = RtlNtStatusToDosErrorNoTeb(v27);
    EventW = v53;
    goto LABEL_108;
  }
  pdnDevInst = 0;
  v28 = (_DWORD *)(v12 + 40);
  if ( v12 == -40
    || (v29 = *(WCHAR **)(v12 + 32), *v28 = 0, CM_Locate_DevNodeW(&pdnDevInst, v29, 5u))
    || CM_Get_Depth((PULONG)(v12 + 40), pdnDevInst, 0) )
  {
    *v28 = -1;
  }
  if ( a4 )
  {
    v30 = 260;
    v31 = a4;
    v32 = 0;
    do
    {
      if ( !*v31 )
        break;
      ++v31;
      --v30;
    }
    while ( v30 );
    if ( !v30 )
      v32 = -1073741811;
    if ( v32 < 0 )
    {
      LastError = RtlNtStatusToDosErrorNoTeb(v32);
      EventW = v53;
      goto LABEL_108;
    }
    v33 = 260 - v30 + 1;
    v54 = v33;
    v34 = PnpHeapAlloc(2 * v33);
    *(_QWORD *)(v12 + 48) = v34;
    if ( !v34 )
    {
      EventW = v53;
      goto LABEL_109;
    }
    v35 = RtlStringCchCopyW(v34, v33, a4);
    if ( v35 < 0 )
    {
LABEL_66:
      LastError = RtlNtStatusToDosErrorNoTeb(v35);
      EventW = v53;
      goto LABEL_108;
    }
  }
  else
  {
    *(_QWORD *)(v12 + 48) = 0;
  }
  if ( a5 )
  {
    v36 = RtlStringLengthWorkerW(a5, 0x7FFF, &v54);
    if ( v36 < 0 )
    {
      LastError = RtlNtStatusToDosErrorNoTeb(v36);
      EventW = v53;
      goto LABEL_108;
    }
    v37 = v54 + 1;
    v38 = PnpHeapAlloc(2 * (v54 + 1));
    *(_QWORD *)(v12 + 56) = v38;
    if ( !v38 )
    {
      EventW = v53;
      goto LABEL_109;
    }
    v35 = RtlStringCchCopyW(v38, v37, a5);
    if ( v35 < 0 )
      goto LABEL_66;
  }
  else
  {
    *(_QWORD *)(v12 + 56) = 0;
  }
  if ( a2 )
  {
    CurrentProcess = GetCurrentProcess();
    v40 = GetCurrentProcess();
    if ( !DuplicateHandle(v40, a2, CurrentProcess, TargetHandle, 0, 0, 2u) )
    {
      LastError = GetLastError();
      TargetHandle[0] = 0;
      EventW = v53;
      goto LABEL_108;
    }
    *(HANDLE *)(v12 + 24) = TargetHandle[0];
  }
  else
  {
    *(_QWORD *)(v12 + 24) = 0;
  }
  *(_DWORD *)(v12 + 80) = a9;
  *(_DWORD *)(v12 + 84) = v16;
  *(_DWORD *)(v12 + 88) = a7;
  v41 = v51;
  if ( v51 )
  {
    v15 = 0;
    v42 = 0;
    EventW = 0;
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
LABEL_84:
      LastError = GetLastError();
      goto LABEL_108;
    }
    v42 = &v50;
  }
  v14 = 0;
  *(_QWORD *)(v12 + 96) = EventW;
  *(_QWORD *)(v12 + 72) = v42;
  *(_QWORD *)(v12 + 64) = v15;
  *(_DWORD *)(v12 + 104) = 0;
  pSetupBeginSynchronizedAccess(&Handles);
  if ( ServerInstallQueuingEnabled )
  {
    for ( i = qword_1800239C8;
          (PVOID *)i != &ServerInstallList && *(_DWORD *)(i + 40) > *v28 && *(_DWORD *)(i + 16) == 1;
          i = *(_QWORD *)(i + 8) )
    {
      ;
    }
    v44 = *(_QWORD **)i;
    if ( *(_QWORD *)(*(_QWORD *)i + 8LL) != i )
      __fastfail(3u);
    *(_QWORD *)v12 = v44;
    *(_QWORD *)(v12 + 8) = i;
    v44[1] = v12;
    *(_QWORD *)i = v12;
    IncrementOutstandingInstallsCounter();
    v45 = -1;
    if ( ServerInstallBatchTotal + 1 >= (unsigned int)ServerInstallBatchTotal )
      v45 = ServerInstallBatchTotal + 1;
    ServerInstallBatchTotal = v45;
    ServerInstallUpdateStatus();
    if ( (Microsoft_Windows_UserPnpEnableBits & 1) != 0 )
      McTemplateU0z_EtwEventWriteTransfer(v46, (int)INSTALLQ_NEW_ENTRY, *(const wchar_t **)(v12 + 32));
    if ( (unsigned int)IsDeviceSpecial(v12) )
      ++ServerInstallSpecialDeviceCount;
    v12 = 0;
    TargetHandle[1] = 0;
    ++ServerInstallListSize;
    SetEvent(hObject);
    if ( !(unsigned int)QueueServerInstallWorkItem() )
    {
      v14 = GetLastError();
      v52 = v14;
    }
  }
  else
  {
    v14 = -536870330;
    v52 = -536870330;
  }
  ReleaseMutex(hMutex);
  if ( !v14 && !v41 )
  {
    v47 = WaitForSingleObjectEx(EventW, 0xFFFFFFFF, 0);
    if ( v47 != -1 )
    {
      LastError = v50;
      if ( v47 )
        LastError = 13;
      goto LABEL_108;
    }
    goto LABEL_84;
  }
LABEL_109:
  if ( v12 )
    FreeServerInstallEntry((_QWORD *)v12);
  if ( EventW )
    CloseHandle(EventW);
  SetLastError(v14);
  return v14 == 0;
}

```

## disassembly

```asm
0x180008d20  mov     [rsp+arg_0], rbx
0x180008d25  mov     [rsp+arg_10], rsi
0x180008d2a  mov     [rsp+arg_18], r9
0x180008d2f  mov     [rsp+hSourceHandle], rdx
0x180008d34  push    rdi
0x180008d35  push    r12
0x180008d37  push    r13
0x180008d39  push    r14
0x180008d3b  push    r15
0x180008d3d  sub     rsp, 70h
0x180008d41  mov     rsi, r8
0x180008d44  mov     rax, rdx
0x180008d47  mov     edi, ecx
0x180008d49  xor     r9d, r9d
0x180008d4c  mov     r14d, r9d
0x180008d4f  mov     [rsp+98h+var_54], r9d
0x180008d54  mov     r12d, r9d
0x180008d57  mov     [rsp+98h+var_48], r9
0x180008d5c  mov     [rsp+98h+TargetHandle], r9
0x180008d61  mov     ebx, [rsp+98h+arg_40]
0x180008d68  and     ebx, 1
0x180008d6b  jz      short loc_180008D7D
0x180008d6d  test    rdx, rdx
0x180008d70  jnz     short loc_180008D7D
0x180008d72  mov     r15d, 0Dh
0x180008d78  jmp     loc_1800093D1
0x180008d7d  mov     [rsp+98h+bAlertable], r9d; bAlertable
0x180008d82  mov     r9d, 0FFFFFFFFh; dwMilliseconds
0x180008d88  xor     r8d, r8d; bWaitAll
0x180008d8b  lea     rdx, Handles; lpHandles
0x180008d92  mov     ecx, 2; nCount
0x180008d97  call    cs:__imp_WaitForMultipleObjectsEx
0x180008d9d  nop
0x180008d9e  mov     r13, [rsp+98h+arg_28]
0x180008da6  cmp     cs:ServerInstallProcessingEnabled, 0
0x180008dad  jnz     short loc_180008E11
0x180008daf  cmp     cs:ServerInstallQueuingEnabled, 0
0x180008db6  jnz     short loc_180008DD5
0x180008db8  lea     r9, aDeviceInstalla; "Device installation disabled"
0x180008dbf  mov     edx, 2000000h
0x180008dc4  mov     r8d, 2
0x180008dca  mov     rcx, r13
0x180008dcd  call    cs:__imp_DevRtlWriteTextLog
0x180008dd3  jmp     short loc_180008E11
0x180008dd5  mov     r12d, [rsp+98h+arg_48]
0x180008ddd  test    r12b, 1
0x180008de1  jnz     short loc_180008E19
0x180008de3  or      r12d, 1
0x180008de7  mov     [rsp+98h+arg_48], r12d
0x180008def  test    r13, r13
0x180008df2  jz      short loc_180008E19
0x180008df4  lea     r9, aInstallationDe; "Installation deferred (too early)"
0x180008dfb  mov     edx, 2000000h
0x180008e00  mov     r8d, 4
0x180008e06  mov     rcx, r13
0x180008e09  call    cs:__imp_DevRtlWriteTextLog
0x180008e0f  jmp     short loc_180008E19
0x180008e11  mov     r12d, [rsp+98h+arg_48]
0x180008e19  mov     rcx, cs:hMutex; hMutex
0x180008e20  call    cs:__imp_ReleaseMutex
0x180008e26  mov     eax, r12d
0x180008e29  and     eax, 1
0x180008e2c  mov     [rsp+98h+var_50], eax
0x180008e30  jz      short loc_180008E6C
0x180008e32  test    ebx, ebx
0x180008e34  jz      short loc_180008E6C
0x180008e36  test    r12b, 2
0x180008e3a  lea     rcx, aInstallation; "Installation"
0x180008e41  lea     rax, aNestedInstalla; "Nested installation"
0x180008e48  cmovz   rax, rcx
0x180008e4c  mov     qword ptr [rsp+98h+bAlertable], rax
0x180008e51  lea     r9, aWsWillBeProces; "%ws will be processed asynchronously"
0x180008e58  mov     edx, 2000000h
0x180008e5d  mov     r8d, 4
0x180008e63  mov     rcx, r13
0x180008e66  call    cs:__imp_DevRtlWriteTextLog
0x180008e6c  test    r12b, 2
0x180008e70  jz      short loc_180008EDE
0x180008e72  mov     ecx, [rsp+98h+arg_38]
0x180008e79  call    IsActiveServerEntryNested
0x180008e7e  test    eax, eax
0x180008e80  jz      short loc_180008EDE
0x180008e82  lea     r9, aRecursiveAsync; "Recursive asynchronous installation req"...
0x180008e89  mov     edx, 2000000h
0x180008e8e  mov     r8d, 1
0x180008e94  mov     rcx, r13
0x180008e97  call    cs:__imp_DevRtlWriteTextLog
0x180008e9d  lea     rax, WPP_GLOBAL_Control
0x180008ea4  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eab  cmp     rcx, rax
0x180008eae  jz      short loc_180008ECE
0x180008eb0  test    byte ptr [rcx+1Ch], 1
0x180008eb4  jz      short loc_180008ECE
0x180008eb6  mov     edx, 35h ; '5'
0x180008ebb  mov     r9, rsi
0x180008ebe  lea     r8, WPP_f291e930712a394bf89cc8c0b8336be0_Traceguids
0x180008ec5  mov     rcx, [rcx+10h]
0x180008ec9  call    WPP_SF_S
0x180008ece  mov     r15d, 32h ; '2'
0x180008ed4  mov     r12, [rsp+98h+var_48]
0x180008ed9  jmp     loc_1800093D1
0x180008ede  mov     r8d, 70h ; 'p'; Size
0x180008ee4  mov     r15d, 8
0x180008eea  mov     edx, r15d; Flags
0x180008eed  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180008ef4  call    cs:__imp_RtlAllocateHeap
0x180008efa  mov     r14, rax
0x180008efd  test    rax, rax
0x180008f00  jnz     short loc_180008F0C
0x180008f02  mov     r12, [rsp+98h+var_48]
0x180008f07  jmp     loc_1800093D1
0x180008f0c  xorps   xmm0, xmm0
0x180008f0f  movups  xmmword ptr [r14+14h], xmm0
0x180008f14  movups  xmmword ptr [r14+24h], xmm0
0x180008f19  movups  xmmword ptr [r14+34h], xmm0
0x180008f1e  movups  xmmword ptr [r14+44h], xmm0
0x180008f23  movups  xmmword ptr [r14+54h], xmm0
0x180008f28  movups  xmmword ptr [r14+60h], xmm0
0x180008f2d  mov     [r14+8], r14
0x180008f31  mov     [r14], r14
0x180008f34  mov     [r14+10h], edi
0x180008f38  xor     r9d, r9d
0x180008f3b  test    rsi, rsi
0x180008f3e  jz      short loc_180008F8E
0x180008f40  mov     ebx, 0C8h
0x180008f45  mov     ecx, ebx
0x180008f47  mov     rax, rsi
0x180008f4a  mov     edx, r9d
0x180008f4d  nop     dword ptr [rax]
0x180008f50  cmp     [rax], dx
0x180008f53  jz      short loc_180008F5F
0x180008f55  add     rax, 2
0x180008f59  sub     rcx, 1
0x180008f5d  jnz     short loc_180008F50
0x180008f5f  test    rcx, rcx
0x180008f62  jnz     short loc_180008F69
0x180008f64  mov     edx, 0C000000Dh
0x180008f69  sub     rbx, rcx
0x180008f6c  test    edx, edx
0x180008f6e  cmovs   rbx, r9
0x180008f72  js      short loc_180008F93
0x180008f74  inc     rbx
0x180008f77  mov     [rsp+98h+var_40], rbx
0x180008f7c  lea     r8, [rbx+rbx]; Size
0x180008f80  cmp     r8, 0F42400h
0x180008f87  jbe     short loc_180008FAC
0x180008f89  mov     rdx, r9
0x180008f8c  jmp     short loc_180008FC2
0x180008f8e  mov     edx, 0C000000Dh
0x180008f93  mov     rbx, r9
0x180008f96  test    edx, edx
0x180008f98  jns     short loc_180008F74
0x180008f9a  mov     ecx, edx; Status
0x180008f9c  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180008fa2  mov     r12, [rsp+98h+var_48]
0x180008fa7  jmp     loc_1800093CE
0x180008fac  mov     edx, r15d; Flags
0x180008faf  mov     rcx, cs:PnpHeapHandle; HeapHandle
0x180008fb6  call    cs:__imp_RtlAllocateHeap
0x180008fbc  mov     rdx, rax
0x180008fbf  xor     r9d, r9d
0x180008fc2  mov     [r14+20h], rdx
0x180008fc6  test    rdx, rdx
0x180008fc9  jnz     short loc_180008FD5
0x180008fcb  mov     r12, [rsp+98h+var_48]
0x180008fd0  jmp     loc_1800093D1
0x180008fd5  lea     rax, [rbx-1]
0x180008fd9  mov     ecx, 7FFFFFFEh
0x180008fde  cmp     rax, rcx
0x180008fe1  ja      short loc_18000901E
0x180008fe3  test    rcx, rcx
0x180008fe6  jz      short loc_180009004
0x180008fe8  movzx   eax, word ptr [rsi]
0x180008feb  test    ax, ax
0x180008fee  jz      short loc_180009004
0x180008ff0  mov     [rdx], ax
0x180008ff3  add     rdx, 2
0x180008ff7  add     rsi, 2
0x180008ffb  dec     rcx
0x180008ffe  sub     rbx, 1
0x180009002  jnz     short loc_180008FE3
0x180009004  lea     rcx, [rdx-2]
0x180009008  test    rbx, rbx
0x18000900b  cmovnz  rcx, rdx
0x18000900f  mov     [rcx], r9w
0x180009013  mov     ecx, 80000005h
0x180009018  cmovnz  ecx, r9d
0x18000901c  jmp     short loc_18000902C
0x18000901e  mov     ecx, 0C000000Dh; Status
0x180009023  test    rbx, rbx
0x180009026  jz      short loc_18000902C
0x180009028  mov     [rdx], r9w
0x18000902c  test    ecx, ecx
0x18000902e  jns     short loc_180009040
0x180009030  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009036  mov     r12, [rsp+98h+var_48]
0x18000903b  jmp     loc_1800093CE
0x180009040  mov     [rsp+98h+pdnDevInst], r9d
0x180009045  lea     rsi, [r14+28h]
0x180009049  test    rsi, rsi
0x18000904c  jz      short loc_18000907E
0x18000904e  mov     rdx, [r14+20h]; pDeviceID
0x180009052  mov     [rsi], r9d
0x180009055  mov     r8d, 5; ulFlags
0x18000905b  lea     rcx, [rsp+98h+pdnDevInst]; pdnDevInst
0x180009060  call    cs:__imp_CM_Locate_DevNodeW
0x180009066  test    eax, eax
0x180009068  jnz     short loc_18000907E
0x18000906a  xor     r8d, r8d; ulFlags
0x18000906d  mov     edx, [rsp+98h+pdnDevInst]; dnDevInst
0x180009071  mov     rcx, rsi; pulDepth
0x180009074  call    cs:__imp_CM_Get_Depth
0x18000907a  test    eax, eax
0x18000907c  jz      short loc_180009084
0x18000907e  mov     dword ptr [rsi], 0FFFFFFFFh
0x180009084  mov     rdi, [rsp+98h+arg_18]
0x18000908c  test    rdi, rdi
0x18000908f  jz      loc_180009127
0x180009095  mov     ebx, 104h
0x18000909a  mov     ecx, ebx
0x18000909c  mov     rax, rdi
0x18000909f  xor     edx, edx
0x1800090a1  cmp     [rax], dx
0x1800090a4  jz      short loc_1800090B0
0x1800090a6  add     rax, 2
0x1800090aa  sub     rcx, 1
0x1800090ae  jnz     short loc_1800090A1
0x1800090b0  test    rcx, rcx
0x1800090b3  jnz     short loc_1800090BA
0x1800090b5  mov     edx, 0C000000Dh
0x1800090ba  sub     rbx, rcx
0x1800090bd  xor     eax, eax
0x1800090bf  test    edx, edx
0x1800090c1  cmovs   rbx, rax
0x1800090c5  jns     short loc_1800090DF
0x1800090c7  xor     ebx, ebx
0x1800090c9  test    edx, edx
0x1800090cb  jns     short loc_1800090DF
0x1800090cd  mov     ecx, edx; Status
0x1800090cf  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800090d5  mov     r12, [rsp+98h+var_48]
0x1800090da  jmp     loc_1800093CE
0x1800090df  inc     rbx
0x1800090e2  mov     [rsp+98h+var_40], rbx
0x1800090e7  lea     rcx, [rbx+rbx]
0x1800090eb  call    PnpHeapAlloc
0x1800090f0  mov     [r14+30h], rax
0x1800090f4  test    rax, rax
0x1800090f7  jnz     short loc_180009103
0x1800090f9  mov     r12, [rsp+98h+var_48]
0x1800090fe  jmp     loc_1800093D1
0x180009103  mov     r8, rdi
0x180009106  mov     rdx, rbx
0x180009109  mov     rcx, rax
0x18000910c  call    RtlStringCchCopyW
0x180009111  test    eax, eax
0x180009113  jns     short loc_18000912F
0x180009115  mov     ecx, eax; Status
0x180009117  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18000911d  mov     r12, [rsp+98h+var_48]
0x180009122  jmp     loc_1800093CE
0x180009127  mov     qword ptr [r14+30h], 0
0x18000912f  mov     rdi, [rsp+98h+arg_20]
0x180009137  test    rdi, rdi
0x18000913a  jz      short loc_1800091B2
0x18000913c  lea     r8, [rsp+98h+var_40]
0x180009141  mov     edx, 7FFFh
0x180009146  mov     rcx, rdi
0x180009149  call    RtlStringLengthWorkerW
0x18000914e  mov     ecx, eax; Status
0x180009150  mov     rbx, [rsp+98h+var_40]
0x180009155  xor     eax, eax
0x180009157  test    ecx, ecx
0x180009159  cmovs   rbx, rax
0x18000915d  jns     short loc_18000916F
0x18000915f  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180009165  mov     r12, [rsp+98h+var_48]
0x18000916a  jmp     loc_1800093CE
0x18000916f  inc     rbx
0x180009172  lea     rcx, [rbx+rbx]
0x180009176  call    PnpHeapAlloc
0x18000917b  mov     [r14+38h], rax
0x18000917f  test    rax, rax
0x180009182  jnz     short loc_18000918E
0x180009184  mov     r12, [rsp+98h+var_48]
0x180009189  jmp     loc_1800093D1
0x18000918e  mov     r8, rdi
0x180009191  mov     rdx, rbx
0x180009194  mov     rcx, rax
0x180009197  call    RtlStringCchCopyW
0x18000919c  test    eax, eax
0x18000919e  jns     short loc_1800091BA
0x1800091a0  mov     ecx, eax; Status
0x1800091a2  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800091a8  mov     r12, [rsp+98h+var_48]
0x1800091ad  jmp     loc_1800093CE
0x1800091b2  mov     qword ptr [r14+38h], 0
0x1800091ba  mov     rdi, [rsp+98h+hSourceHandle]
0x1800091c2  test    rdi, rdi
0x1800091c5  jz      short loc_18000922A
  ... truncated ...
```
