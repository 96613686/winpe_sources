# RIMDeviceIoControl

- ea: `0x1400df980`
- end: `0x1400e00d7`
- name: `RIMDeviceIoControl`
- size: `1879`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1401828c0`
- `0x14021231c`

## callees

- `0x140065730`
- `0x1400729c8`
- `0x140072a90`
- `0x1400951c0`
- `0x1400be6e0`
- `0x1400cad00`
- `0x1400de2e4`
- `0x1400df980`
- `0x1400e0370`
- `0x1401a9f9c`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400dfed6`
- `ntoskrnl!ProbeForRead` at `0x1400dfed6`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfd8d`
- `ntoskrnl!KeBugCheckEx` at `0x1400dfd8d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400dfac9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400dfac9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dfab8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400dfab8`
- `ntoskrnl!ProbeForWrite` at `0x1400dff00`
- `ntoskrnl!ProbeForWrite` at `0x1400dff00`
- `ntoskrnl!ObfReferenceObject` at `0x1400dfd58`
- `ntoskrnl!ObfReferenceObject` at `0x1400dfd58`
- `ntoskrnl!KeInitializeEvent` at `0x1400dfccf`
- `ntoskrnl!KeInitializeEvent` at `0x1400dfccf`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfe9c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400dfe9c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400dfcaa`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400dfcaa`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400dfd32`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400dfd32`
- `ntoskrnl!IofCallDriver` at `0x1400dfdc8`
- `ntoskrnl!IofCallDriver` at `0x1400dfdc8`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400dfbb0`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400dfbb0`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400dff49`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400dff49`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfbc6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfbee`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfdfa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfe50`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfbc6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfbee`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfdfa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400dfe50`
- `WIN32K!W32GetUserSessionState` at `0x1400df9ee`
- `WIN32K!W32GetUserSessionState` at `0x1400dfc29`
- `WIN32K!W32GetUserSessionState` at `0x1400dffed`
- `WIN32K!W32GetUserSessionState` at `0x1400e0073`
- `WIN32K!W32GetUserSessionState` at `0x1400df9ee`
- `WIN32K!W32GetUserSessionState` at `0x1400dfc29`
- `WIN32K!W32GetUserSessionState` at `0x1400dffed`
- `WIN32K!W32GetUserSessionState` at `0x1400e0073`
- `HAL!KeQueryPerformanceCounter` at `0x1400dfd9c`
- `HAL!KeQueryPerformanceCounter` at `0x1400dfe08`
- `HAL!KeQueryPerformanceCounter` at `0x1400dfd9c`
- `HAL!KeQueryPerformanceCounter` at `0x1400dfe08`

## pseudocode

```c
__int64 __fastcall RIMDeviceIoControl(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        volatile void *a4,
        ULONG InputBufferLength,
        PVOID a6,
        ULONG a7,
        _DWORD *a8,
        struct _IO_STATUS_BLOCK *IoStatusBlock,
        int a10,
        int a11,
        int a12)
{
  __int64 v12; // r15
  bool v13; // bl
  bool v14; // di
  __int64 UserSessionState; // rax
  int v16; // r8d
  int v17; // edx
  __int64 v18; // rdx
  __int64 v19; // r8
  NTSTATUS Status; // r15d
  _QWORD *v21; // rdi
  struct _KTHREAD *v22; // rcx
  _BOOL8 v23; // rdx
  char *v24; // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  char *v27; // r13
  struct _FILE_OBJECT *v28; // r12
  void *v29; // rcx
  char v30; // bl
  bool v31; // di
  __int64 v32; // rax
  int v33; // r8d
  int v34; // edx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // r15
  PIRP v37; // r15
  PVOID v38; // rdi
  LARGE_INTEGER v39; // rax
  char v40; // di
  bool v41; // r12
  __int64 v42; // rax
  int v43; // r8d
  int v44; // edx
  char v45; // di
  bool v46; // r12
  __int64 v47; // rax
  int v48; // r8d
  int v49; // edx
  PVOID v50; // [rsp+50h] [rbp-98h] BYREF
  PVOID v51; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  char *v53; // [rsp+68h] [rbp-80h]
  struct _IO_STATUS_BLOCK Src; // [rsp+70h] [rbp-78h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-68h]
  LARGE_INTEGER PerformanceCounter; // [rsp+88h] [rbp-60h]
  struct _KEVENT Event; // [rsp+90h] [rbp-58h] BYREF
  ULONG IoControlCode; // [rsp+100h] [rbp+18h]
  PVOID InputBuffer; // [rsp+108h] [rbp+20h]

  InputBuffer = (PVOID)a4;
  IoControlCode = a3;
  v12 = a1;
  v13 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1, a2, a3);
    LOBYTE(v16) = v14;
    LOBYTE(v17) = v13;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v17,
      v16,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      126,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    a4 = InputBuffer;
    v12 = a1;
  }
  v51 = 0;
  Object = 0;
  if ( a12 == 1 )
  {
    ProbeForRead(a4, InputBufferLength, 1u);
    ProbeForWrite(a6, a7, 1u);
  }
  Status = RawInputManagerObjectResolveHandle(v12, 3, 1, &v51);
  if ( Status >= 0 )
  {
    v21 = v51;
    v22 = (struct _KTHREAD *)*((_QWORD *)v51 + 13);
    v23 = v22 == KeGetCurrentThread();
    LODWORD(v50) = v23;
    v24 = 0;
    v53 = 0;
    if ( v22 != KeGetCurrentThread() )
    {
      v24 = (char *)v51 + 96;
      v53 = (char *)v51 + 96;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v21 + 12, 0);
      v21[13] = KeGetCurrentThread();
    }
    if ( *((_BYTE *)v21 + 73) )
    {
      Status = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v45 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v45 = 0;
      }
      v46 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v45 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v47 = W32GetUserSessionState(WPP_GLOBAL_Control, v23, v19);
        LOBYTE(v48) = v46;
        LOBYTE(v49) = v45;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v49,
          v48,
          *(_QWORD *)(v47 + 19408),
          3,
          1,
          128,
          (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
      }
    }
    else
    {
      Status = RawInputManagerDeviceObjectResolveHandle(a2, 3, 1, &Object);
      if ( Status < 0 )
      {
LABEL_24:
        if ( v24 )
          RIMUnlockExclusive(v24);
        ObfDereferenceObject(v21);
        goto LABEL_27;
      }
      v27 = (char *)Object;
      if ( *((_QWORD *)Object + 34) && (v28 = (struct _FILE_OBJECT *)*((_QWORD *)Object + 35)) != 0 )
      {
        if ( (*((_DWORD *)Object + 58) & 0x1000) != 0 )
        {
          Status = -1073741637;
        }
        else if ( a10 )
        {
          if ( !IoStatusBlock )
          {
            LODWORD(v50) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4101);
          }
          v29 = (void *)*((_QWORD *)v27 + 34);
          if ( a12 == 1 )
            NtDeviceIoControlFile(v29, 0, 0, 0, IoStatusBlock, IoControlCode, InputBuffer, InputBufferLength, 0, 0);
          else
            ZwDeviceIoControlFile(v29, 0, 0, 0, IoStatusBlock, IoControlCode, InputBuffer, InputBufferLength, 0, 0);
        }
        else
        {
          Src = 0;
          memset(&Event, 0, sizeof(Event));
          RelatedDeviceObject = IoGetRelatedDeviceObject(v28);
          DeviceObject = RelatedDeviceObject;
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          v37 = IoBuildDeviceIoControlRequest(
                  IoControlCode,
                  RelatedDeviceObject,
                  InputBuffer,
                  InputBufferLength,
                  a6,
                  a7,
                  a11 != 0,
                  &Event,
                  &Src);
          if ( v37 )
          {
            v37->RequestorMode = a12;
            ObfReferenceObject(v28);
            v37->Tail.Overlay.CurrentStackLocation[-1].FileObject = v28;
            if ( (_DWORD)v50 )
              KeBugCheckEx(0x164u, 0x24u, (ULONG_PTR)(v27 + 256), 0, 0);
            PerformanceCounter = KeQueryPerformanceCounter(0);
            RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(
              (RIMDropAndReAcquireSyncLock *)&v50,
              (struct RawInputManagerObject *)v21);
            if ( IofCallDriver(DeviceObject, v37) == 259 )
            {
              while ( KeWaitForSingleObject(&Event, UserRequest, 0, 1u, 0) == 257 )
                ;
            }
            Status = Src.Status;
            v38 = v50;
            if ( v50 )
            {
              RIMLockExclusive((char *)v50 + 96);
              ObfDereferenceObject(v38);
            }
            v39 = KeQueryPerformanceCounter(0);
            RimTelemetry::LogBlockingIoControlRequest(
              "RimDeviceIoControl",
              (struct RIMDEV *const)(v27 + 64),
              (unsigned __int64)(1000 * (v39.QuadPart - PerformanceCounter.QuadPart)) / gliQpcFreq.QuadPart,
              Status,
              IoControlCode);
            ObfDereferenceObject(v28);
          }
          else
          {
            Status = -1073741668;
          }
          if ( a12 )
            RtlCopyToUser(a8, &Src.Information, 4u);
          else
            *a8 = Src.Information;
        }
      }
      else
      {
        Status = -1073741436;
        if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
          || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
          || (v40 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v40 = 0;
        }
        v41 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v40 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v42 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v25, v26);
          LOBYTE(v43) = v41;
          LOBYTE(v44) = v40;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v44,
            v43,
            *(_QWORD *)(v42 + 19408),
            3,
            1,
            127,
            (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
        }
      }
      ObfDereferenceObject(v27);
    }
    v21 = v51;
    goto LABEL_24;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v30 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v30 = 0;
  }
  v31 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v30 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v32 = W32GetUserSessionState(WPP_GLOBAL_Control, v18, v19);
    LOBYTE(v33) = v31;
    LOBYTE(v34) = v30;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v34,
      v33,
      *(_QWORD *)(v32 + 19408),
      4,
      1,
      129,
      (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400df980  mov     rax, rsp
0x1400df983  mov     [rax+20h], r9
0x1400df987  mov     [rax+18h], r8d
0x1400df98b  mov     [rax+10h], rdx
0x1400df98f  mov     [rax+8], rcx
0x1400df993  push    rbx
0x1400df994  push    rsi
0x1400df995  push    rdi
0x1400df996  push    r12
0x1400df998  push    r13
0x1400df99a  push    r14
0x1400df99c  push    r15
0x1400df99e  sub     rsp, 0B0h
0x1400df9a5  mov     r15, rcx
0x1400df9a8  lea     r12, WPP_GLOBAL_Control
0x1400df9af  mov     r10, cs:WPP_GLOBAL_Control
0x1400df9b6  mov     r14d, 1
0x1400df9bc  cmp     r10, r12
0x1400df9bf  jz      short loc_1400DF9CE
0x1400df9c1  mov     eax, [r10+2Ch]
0x1400df9c5  test    r14b, al
0x1400df9c8  jnz     loc_1400DFEB4
0x1400df9ce  xor     esi, esi
0x1400df9d0  mov     bl, sil
0x1400df9d3  lea     r13, WPP_RECORDER_INITIALIZED
0x1400df9da  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400df9e1  setnz   dil
0x1400df9e5  test    bl, bl
0x1400df9e7  jnz     short loc_1400DF9EE
0x1400df9e9  test    dil, dil
0x1400df9ec  jz      short loc_1400DFA43
0x1400df9ee  call    cs:__imp_W32GetUserSessionState
0x1400df9f5  nop     dword ptr [rax+rax+00h]
0x1400df9fa  mov     r9, [rax+4BD0h]
0x1400dfa01  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400dfa08  mov     qword ptr [rsp+0E8h+InputBufferLength], r15
0x1400dfa0d  mov     word ptr [rsp+0E8h+InputBuffer], 7Eh ; '~'
0x1400dfa14  mov     [rsp+0E8h+IoControlCode], r14d
0x1400dfa19  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x1400dfa1e  mov     r8b, dil
0x1400dfa21  mov     dl, bl
0x1400dfa23  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dfa2a  mov     rcx, [rcx+18h]
0x1400dfa2e  call    WPP_RECORDER_AND_TRACE_SF_
0x1400dfa33  mov     r9, [rsp+0E8h+arg_18]
0x1400dfa3b  mov     r15, [rsp+0E8h+arg_0]
0x1400dfa43  mov     [rsp+0E8h+var_90], rsi
0x1400dfa48  mov     [rsp+0E8h+Object], rsi
0x1400dfa4d  cmp     [rsp+0E8h+arg_58], r14d
0x1400dfa55  jz      loc_1400DFEC9
0x1400dfa5b  lea     r9, [rsp+0E8h+var_90]
0x1400dfa60  mov     r8d, r14d
0x1400dfa63  mov     edx, 3
0x1400dfa68  mov     rcx, r15
0x1400dfa6b  call    RawInputManagerObjectResolveHandle
0x1400dfa70  mov     r15d, eax
0x1400dfa73  test    eax, eax
0x1400dfa75  js      loc_1400DFBFA
0x1400dfa7b  mov     rdi, [rsp+0E8h+var_90]
0x1400dfa80  mov     rcx, [rdi+68h]
0x1400dfa84  mov     rax, gs:188h
0x1400dfa8d  mov     edx, esi
0x1400dfa8f  cmp     rcx, rax
0x1400dfa92  setz    dl
0x1400dfa95  mov     dword ptr [rsp+0E8h+var_98], edx
0x1400dfa99  mov     rbx, rsi
0x1400dfa9c  mov     [rsp+0E8h+var_80], rbx
0x1400dfaa1  mov     rax, gs:188h
0x1400dfaaa  cmp     rcx, rax
0x1400dfaad  jz      short loc_1400DFAE2
0x1400dfaaf  lea     rbx, [rdi+60h]
0x1400dfab3  mov     [rsp+0E8h+var_80], rbx
0x1400dfab8  call    cs:__imp_KeEnterCriticalRegion
0x1400dfabf  nop     dword ptr [rax+rax+00h]
0x1400dfac4  xor     edx, edx
0x1400dfac6  mov     rcx, rbx
0x1400dfac9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400dfad0  nop     dword ptr [rax+rax+00h]
0x1400dfad5  mov     rax, gs:188h
0x1400dfade  mov     [rbx+8], rax
0x1400dfae2  cmp     [rdi+49h], sil
0x1400dfae6  jnz     loc_1400E0038
0x1400dfaec  lea     r9, [rsp+0E8h+Object]
0x1400dfaf1  mov     r8d, r14d
0x1400dfaf4  mov     edx, 3
0x1400dfaf9  mov     rcx, [rsp+0E8h+arg_8]
0x1400dfb01  call    RawInputManagerDeviceObjectResolveHandle
0x1400dfb06  mov     r15d, eax
0x1400dfb09  test    eax, eax
0x1400dfb0b  js      loc_1400DFBDE
0x1400dfb11  mov     r13, [rsp+0E8h+Object]
0x1400dfb16  cmp     [r13+110h], rsi
0x1400dfb1d  jz      loc_1400DFFA7
0x1400dfb23  mov     r12, [r13+118h]
0x1400dfb2a  test    r12, r12
0x1400dfb2d  jz      loc_1400DFFA0
0x1400dfb33  test    dword ptr [r13+0E8h], 1000h
0x1400dfb3e  jnz     loc_1400DFF1B
0x1400dfb44  cmp     [rsp+0E8h+arg_48], esi
0x1400dfb4b  jz      loc_1400DFC8A
0x1400dfb51  mov     rdi, [rsp+0E8h+arg_40]
0x1400dfb59  test    rdi, rdi
0x1400dfb5c  jz      loc_1400DFF26
0x1400dfb62  mov     [rsp+0E8h+OutputBufferLength], esi; OutputBufferLength
0x1400dfb66  mov     eax, [rsp+0E8h+arg_20]
0x1400dfb6d  mov     r8, [rsp+0E8h+arg_18]
0x1400dfb75  mov     ecx, [rsp+0E8h+arg_10]
0x1400dfb7c  xor     r9d, r9d; ApcContext
0x1400dfb7f  xor     edx, edx; Event
0x1400dfb81  mov     [rsp+0E8h+OutputBuffer], rsi; OutputBuffer
0x1400dfb86  mov     [rsp+0E8h+InputBufferLength], eax; InputBufferLength
0x1400dfb8a  mov     [rsp+0E8h+InputBuffer], r8; InputBuffer
0x1400dfb8f  mov     [rsp+0E8h+IoControlCode], ecx; IoControlCode
0x1400dfb93  xor     r8d, r8d; ApcRoutine
0x1400dfb96  mov     [rsp+0E8h+IoStatusBlock], rdi; IoStatusBlock
0x1400dfb9b  mov     rcx, [r13+110h]; FileHandle
0x1400dfba2  cmp     [rsp+0E8h+arg_58], r14d
0x1400dfbaa  jz      loc_1400DFF49
0x1400dfbb0  call    cs:__imp_ZwDeviceIoControlFile
0x1400dfbb7  nop     dword ptr [rax+rax+00h]
0x1400dfbbc  lea     r12, WPP_GLOBAL_Control
0x1400dfbc3  mov     rcx, r13; Object
0x1400dfbc6  call    cs:__imp_ObfDereferenceObject
0x1400dfbcd  nop     dword ptr [rax+rax+00h]
0x1400dfbd2  lea     r13, WPP_RECORDER_INITIALIZED
0x1400dfbd9  mov     rdi, [rsp+0E8h+var_90]
0x1400dfbde  test    rbx, rbx
0x1400dfbe1  jz      short loc_1400DFBEB
0x1400dfbe3  mov     rcx, rbx
0x1400dfbe6  call    RIMUnlockExclusive
0x1400dfbeb  mov     rcx, rdi; Object
0x1400dfbee  call    cs:__imp_ObfDereferenceObject
0x1400dfbf5  nop     dword ptr [rax+rax+00h]
0x1400dfbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dfc01  cmp     rcx, r12
0x1400dfc04  jz      short loc_1400DFC12
0x1400dfc06  mov     eax, [rcx+2Ch]
0x1400dfc09  test    r14b, al
0x1400dfc0c  jnz     loc_1400E00C5
0x1400dfc12  mov     bl, sil
0x1400dfc15  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400dfc1c  setnz   dil
0x1400dfc20  test    bl, bl
0x1400dfc22  jnz     short loc_1400DFC29
0x1400dfc24  test    dil, dil
0x1400dfc27  jz      short loc_1400DFC73
0x1400dfc29  call    cs:__imp_W32GetUserSessionState
0x1400dfc30  nop     dword ptr [rax+rax+00h]
0x1400dfc35  mov     r9, [rax+4BD0h]
0x1400dfc3c  mov     dword ptr [rsp+0E8h+OutputBuffer], r15d
0x1400dfc41  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400dfc48  mov     qword ptr [rsp+0E8h+InputBufferLength], rax
0x1400dfc4d  mov     word ptr [rsp+0E8h+InputBuffer], 81h
0x1400dfc54  mov     [rsp+0E8h+IoControlCode], r14d
0x1400dfc59  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x1400dfc5e  mov     r8b, dil
0x1400dfc61  mov     dl, bl
0x1400dfc63  mov     rcx, cs:WPP_GLOBAL_Control
0x1400dfc6a  mov     rcx, [rcx+18h]
0x1400dfc6e  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400dfc73  mov     eax, r15d
0x1400dfc76  add     rsp, 0B0h
0x1400dfc7d  pop     r15
0x1400dfc7f  pop     r14
0x1400dfc81  pop     r13
0x1400dfc83  pop     r12
0x1400dfc85  pop     rdi
0x1400dfc86  pop     rsi
0x1400dfc87  pop     rbx
0x1400dfc88  retn
0x1400dfc8a  xorps   xmm0, xmm0
0x1400dfc8d  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x1400dfc92  xorps   xmm1, xmm1
0x1400dfc95  xor     eax, eax
0x1400dfc97  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm1
0x1400dfc9f  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x1400dfca7  mov     rcx, r12; FileObject
0x1400dfcaa  call    cs:__imp_IoGetRelatedDeviceObject
0x1400dfcb1  nop     dword ptr [rax+rax+00h]
0x1400dfcb6  mov     r15, rax
0x1400dfcb9  mov     [rsp+0E8h+DeviceObject], rax
0x1400dfcc1  xor     r8d, r8d; State
0x1400dfcc4  mov     edx, r14d; Type
0x1400dfcc7  lea     rcx, [rsp+0E8h+Event]; Event
0x1400dfccf  call    cs:__imp_KeInitializeEvent
0x1400dfcd6  nop     dword ptr [rax+rax+00h]
0x1400dfcdb  cmp     [rsp+0E8h+arg_50], esi
0x1400dfce2  setnz   cl
0x1400dfce5  lea     rax, [rsp+0E8h+Src]
0x1400dfcea  mov     [rsp+0E8h+OutputBuffer], rax; IoStatusBlock
0x1400dfcef  lea     rax, [rsp+0E8h+Event]
0x1400dfcf7  mov     qword ptr [rsp+0E8h+InputBufferLength], rax; Event
0x1400dfcfc  mov     byte ptr [rsp+0E8h+InputBuffer], cl; InternalDeviceIoControl
0x1400dfd00  mov     ecx, [rsp+0E8h+arg_30]
0x1400dfd07  mov     [rsp+0E8h+IoControlCode], ecx; OutputBufferLength
0x1400dfd0b  mov     rax, [rsp+0E8h+arg_28]
0x1400dfd13  mov     [rsp+0E8h+IoStatusBlock], rax; OutputBuffer
0x1400dfd18  mov     r9d, [rsp+0E8h+arg_20]; InputBufferLength
0x1400dfd20  mov     r8, [rsp+0E8h+arg_18]; InputBuffer
0x1400dfd28  mov     rdx, r15; DeviceObject
0x1400dfd2b  mov     ecx, [rsp+0E8h+arg_10]; IoControlCode
0x1400dfd32  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400dfd39  nop     dword ptr [rax+rax+00h]
0x1400dfd3e  mov     r15, rax
0x1400dfd41  test    rax, rax
0x1400dfd44  jz      loc_1400DFE7D
0x1400dfd4a  mov     eax, [rsp+0E8h+arg_58]
0x1400dfd51  mov     [r15+40h], al
0x1400dfd55  mov     rcx, r12; Object
0x1400dfd58  call    cs:__imp_ObfReferenceObject
0x1400dfd5f  nop     dword ptr [rax+rax+00h]
0x1400dfd64  mov     rcx, [r15+0B8h]
0x1400dfd6b  mov     [rcx-18h], r12
0x1400dfd6f  cmp     dword ptr [rsp+0E8h+var_98], esi
0x1400dfd73  jz      short loc_1400DFD9A
0x1400dfd75  lea     r8, [r13+100h]; BugCheckParameter2
0x1400dfd7c  mov     [rsp+0E8h+IoStatusBlock], rsi; BugCheckParameter4
0x1400dfd81  xor     r9d, r9d; BugCheckParameter3
0x1400dfd84  lea     edx, [r9+24h]; BugCheckParameter1
0x1400dfd88  mov     ecx, 164h; BugCheckCode
0x1400dfd8d  call    cs:__imp_KeBugCheckEx
0x1400dfd9a  xor     ecx, ecx; PerformanceFrequency
0x1400dfd9c  call    cs:__imp_KeQueryPerformanceCounter
0x1400dfda3  nop     dword ptr [rax+rax+00h]
0x1400dfda8  mov     [rsp+0E8h+var_60], rax
0x1400dfdb0  mov     rdx, rdi; struct RawInputManagerObject *
0x1400dfdb3  lea     rcx, [rsp+0E8h+var_98]; this
0x1400dfdb8  call    ??0RIMDropAndReAcquireSyncLock@@QEAA@PEAURawInputManagerObject@@@Z; RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(RawInputManagerObject *)
0x1400dfdbd  mov     rdx, r15; Irp
0x1400dfdc0  mov     rcx, [rsp+0E8h+DeviceObject]; DeviceObject
0x1400dfdc8  call    cs:__imp_IofCallDriver
0x1400dfdcf  nop     dword ptr [rax+rax+00h]
0x1400dfdd4  cmp     eax, 103h
0x1400dfdd9  jz      loc_1400DFE85
0x1400dfddf  mov     r15d, dword ptr [rsp+0E8h+Src]
0x1400dfde4  mov     rdi, [rsp+0E8h+var_98]
0x1400dfde9  test    rdi, rdi
0x1400dfdec  jz      short loc_1400DFE06
0x1400dfdee  lea     rcx, [rdi+60h]
0x1400dfdf2  call    RIMLockExclusive
0x1400dfdf7  mov     rcx, rdi; Object
0x1400dfdfa  call    cs:__imp_ObfDereferenceObject
0x1400dfe01  nop     dword ptr [rax+rax+00h]
0x1400dfe06  xor     ecx, ecx; PerformanceFrequency
0x1400dfe08  call    cs:__imp_KeQueryPerformanceCounter
0x1400dfe0f  nop     dword ptr [rax+rax+00h]
0x1400dfe14  sub     rax, [rsp+0E8h+var_60]
0x1400dfe1c  imul    rax, 3E8h
0x1400dfe23  xor     edx, edx
0x1400dfe25  div     qword ptr cs:gliQpcFreq
0x1400dfe2c  mov     r8, rax; unsigned __int64
0x1400dfe2f  mov     eax, [rsp+0E8h+arg_10]
0x1400dfe36  mov     dword ptr [rsp+0E8h+IoStatusBlock], eax; unsigned int
0x1400dfe3a  mov     r9d, r15d; int
0x1400dfe3d  lea     rdx, [r13+40h]; struct RIMDEV *
0x1400dfe41  lea     rcx, aRimdeviceiocon; "RimDeviceIoControl"
0x1400dfe48  call    ?LogBlockingIoControlRequest@RimTelemetry@@SAXPEBDQEAURIMDEV@@_KJK@Z; RimTelemetry::LogBlockingIoControlRequest(char const *,RIMDEV * const,unsigned __int64,long,ulong)
0x1400dfe4d  mov     rcx, r12; Object
0x1400dfe50  call    cs:__imp_ObfDereferenceObject
0x1400dfe57  nop     dword ptr [rax+rax+00h]
0x1400dfe5c  cmp     [rsp+0E8h+arg_58], esi
0x1400dfe63  jnz     loc_1400DFF5A
0x1400dfe69  mov     rcx, [rsp+0E8h+Src.Information]
0x1400dfe6e  mov     rax, [rsp+0E8h+arg_38]
0x1400dfe76  mov     [rax], ecx
0x1400dfe78  jmp     loc_1400DFBBC
0x1400dfe7d  mov     r15d, 0C000009Ch
0x1400dfe83  jmp     short loc_1400DFE5C
0x1400dfe85  mov     [rsp+0E8h+IoStatusBlock], rsi; Timeout
0x1400dfe8a  mov     r9b, r14b; Alertable
0x1400dfe8d  xor     r8d, r8d; WaitMode
0x1400dfe90  lea     edx, [r8+6]; WaitReason
0x1400dfe94  lea     rcx, [rsp+0E8h+Event]; Object
0x1400dfe9c  call    cs:__imp_KeWaitForSingleObject
0x1400dfea3  nop     dword ptr [rax+rax+00h]
0x1400dfea8  cmp     eax, 101h
0x1400dfead  jz      short loc_1400DFE85
0x1400dfeaf  jmp     loc_1400DFDDF
0x1400dfeb4  cmp     byte ptr [r10+29h], 4
0x1400dfeb9  jb      loc_1400DF9CE
0x1400dfebf  mov     bl, r14b
0x1400dfec2  xor     esi, esi
0x1400dfec4  jmp     loc_1400DF9D3
0x1400dfec9  mov     edx, [rsp+0E8h+arg_20]; Length
0x1400dfed0  mov     r8d, r14d; Alignment
0x1400dfed3  mov     rcx, r9; Address
0x1400dfed6  call    cs:__imp_ProbeForRead
0x1400dfedd  nop     dword ptr [rax+rax+00h]
0x1400dfee2  jmp     short loc_1400DFEEE
0x1400dfee4  mov     eax, 0C000000Dh
0x1400dfee9  jmp     loc_1400DFC76
0x1400dfeee  mov     edx, [rsp+0E8h+arg_30]; Length
0x1400dfef5  mov     r8d, r14d; Alignment
0x1400dfef8  mov     rcx, [rsp+0E8h+arg_28]; Address
0x1400dff00  call    cs:__imp_ProbeForWrite
0x1400dff07  nop     dword ptr [rax+rax+00h]
0x1400dff0c  jmp     loc_1400DFA5B
0x1400dff11  mov     eax, 0C000000Dh
0x1400dff16  jmp     loc_1400DFC76
0x1400dff1b  mov     r15d, 0C00000BBh
  ... truncated ...
```
