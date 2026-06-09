# RIMDeviceIoControl

- ea: `0x140091d60`
- end: `0x1400924b7`
- name: `RIMDeviceIoControl`
- size: `1879`
- prototype: `__int64 __fastcall(__int64, __int64, ULONG, volatile void *, ULONG InputBufferLength, PVOID, ULONG, _DWORD *, struct _IO_STATUS_BLOCK *IoStatusBlock, int, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140184430`
- `0x140212b1c`

## callees

- `0x140049df8`
- `0x140049ec0`
- `0x140062ff0`
- `0x1400682c0`
- `0x1400906c4`
- `0x140091d60`
- `0x140092750`
- `0x1400b2540`
- `0x1400bdb30`
- `0x1401aab9c`
- `0x1402bb054`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400922b6`
- `ntoskrnl!ProbeForRead` at `0x1400922b6`
- `ntoskrnl!KeBugCheckEx` at `0x14009216d`
- `ntoskrnl!KeBugCheckEx` at `0x14009216d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140091ea9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140091ea9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091e98`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140091e98`
- `ntoskrnl!ProbeForWrite` at `0x1400922e0`
- `ntoskrnl!ProbeForWrite` at `0x1400922e0`
- `ntoskrnl!ObfReferenceObject` at `0x140092138`
- `ntoskrnl!ObfReferenceObject` at `0x140092138`
- `ntoskrnl!KeInitializeEvent` at `0x1400920af`
- `ntoskrnl!KeInitializeEvent` at `0x1400920af`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009227c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14009227c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14009208a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14009208a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140092112`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140092112`
- `ntoskrnl!IofCallDriver` at `0x1400921a8`
- `ntoskrnl!IofCallDriver` at `0x1400921a8`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140091f90`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x140091f90`
- `ntoskrnl!NtDeviceIoControlFile` at `0x140092329`
- `ntoskrnl!NtDeviceIoControlFile` at `0x140092329`
- `ntoskrnl!ObfDereferenceObject` at `0x140091fa6`
- `ntoskrnl!ObfDereferenceObject` at `0x140091fce`
- `ntoskrnl!ObfDereferenceObject` at `0x1400921da`
- `ntoskrnl!ObfDereferenceObject` at `0x140092230`
- `ntoskrnl!ObfDereferenceObject` at `0x140091fa6`
- `ntoskrnl!ObfDereferenceObject` at `0x140091fce`
- `ntoskrnl!ObfDereferenceObject` at `0x1400921da`
- `ntoskrnl!ObfDereferenceObject` at `0x140092230`
- `WIN32K!W32GetUserSessionState` at `0x140091dce`
- `WIN32K!W32GetUserSessionState` at `0x140092009`
- `WIN32K!W32GetUserSessionState` at `0x1400923cd`
- `WIN32K!W32GetUserSessionState` at `0x140092453`
- `WIN32K!W32GetUserSessionState` at `0x140091dce`
- `WIN32K!W32GetUserSessionState` at `0x140092009`
- `WIN32K!W32GetUserSessionState` at `0x1400923cd`
- `WIN32K!W32GetUserSessionState` at `0x140092453`
- `HAL!KeQueryPerformanceCounter` at `0x14009217c`
- `HAL!KeQueryPerformanceCounter` at `0x1400921e8`
- `HAL!KeQueryPerformanceCounter` at `0x14009217c`
- `HAL!KeQueryPerformanceCounter` at `0x1400921e8`

## pseudocode

```c
__int64 __fastcall RIMDeviceIoControl(
        __int64 a1,
        __int64 a2,
        ULONG a3,
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
  NTSTATUS Status; // r15d
  _QWORD *v20; // rdi
  struct _KTHREAD *v21; // rcx
  _BOOL8 v22; // rdx
  char *v23; // rbx
  __int64 v24; // rdx
  char *v25; // r13
  struct _FILE_OBJECT *v26; // r12
  void *v27; // rcx
  char v28; // bl
  bool v29; // di
  __int64 v30; // rax
  int v31; // r8d
  int v32; // edx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // r15
  PIRP v35; // r15
  PVOID v36; // rdi
  LARGE_INTEGER v37; // rax
  char v38; // di
  bool v39; // r12
  __int64 v40; // rax
  int v41; // r8d
  int v42; // edx
  char v43; // di
  bool v44; // r12
  __int64 v45; // rax
  int v46; // r8d
  int v47; // edx
  PVOID v48; // [rsp+50h] [rbp-98h] BYREF
  PVOID v49; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  char *v51; // [rsp+68h] [rbp-80h]
  struct _IO_STATUS_BLOCK Src; // [rsp+70h] [rbp-78h] BYREF
  PDEVICE_OBJECT DeviceObject; // [rsp+80h] [rbp-68h]
  LARGE_INTEGER PerformanceCounter; // [rsp+88h] [rbp-60h]
  struct _KEVENT Event; // [rsp+90h] [rbp-58h] BYREF
  PVOID InputBuffer; // [rsp+108h] [rbp+20h]

  InputBuffer = (PVOID)a4;
  v12 = a1;
  v13 = WPP_GLOBAL_Control != (CTouchProcessor *)&WPP_GLOBAL_Control
     && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 4u;
  v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1, a2);
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
  v49 = 0;
  Object = 0;
  if ( a12 == 1 )
  {
    ProbeForRead(a4, InputBufferLength, 1u);
    ProbeForWrite(a6, a7, 1u);
  }
  Status = RawInputManagerObjectResolveHandle(v12, 3, 1, &v49);
  if ( Status >= 0 )
  {
    v20 = v49;
    v21 = (struct _KTHREAD *)*((_QWORD *)v49 + 13);
    v22 = v21 == KeGetCurrentThread();
    LODWORD(v48) = v22;
    v23 = 0;
    v51 = 0;
    if ( v21 != KeGetCurrentThread() )
    {
      v23 = (char *)v49 + 96;
      v51 = (char *)v49 + 96;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v20 + 12, 0);
      v20[13] = KeGetCurrentThread();
    }
    if ( *((_BYTE *)v20 + 73) )
    {
      Status = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v43 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v43 = 0;
      }
      v44 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v43 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v45 = W32GetUserSessionState(WPP_GLOBAL_Control, v22);
        LOBYTE(v46) = v44;
        LOBYTE(v47) = v43;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v47,
          v46,
          *(_QWORD *)(v45 + 19408),
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
        if ( v23 )
          RIMUnlockExclusive(v23);
        ObfDereferenceObject(v20);
        goto LABEL_27;
      }
      v25 = (char *)Object;
      if ( *((_QWORD *)Object + 34) && (v26 = (struct _FILE_OBJECT *)*((_QWORD *)Object + 35)) != 0 )
      {
        if ( (*((_DWORD *)Object + 58) & 0x1000) != 0 )
        {
          Status = -1073741637;
        }
        else if ( a10 )
        {
          if ( !IoStatusBlock )
          {
            LODWORD(v48) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4101);
          }
          v27 = (void *)*((_QWORD *)v25 + 34);
          if ( a12 == 1 )
            NtDeviceIoControlFile(v27, 0, 0, 0, IoStatusBlock, a3, InputBuffer, InputBufferLength, 0, 0);
          else
            ZwDeviceIoControlFile(v27, 0, 0, 0, IoStatusBlock, a3, InputBuffer, InputBufferLength, 0, 0);
        }
        else
        {
          Src = 0;
          memset(&Event, 0, sizeof(Event));
          RelatedDeviceObject = IoGetRelatedDeviceObject(v26);
          DeviceObject = RelatedDeviceObject;
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          v35 = IoBuildDeviceIoControlRequest(
                  a3,
                  RelatedDeviceObject,
                  InputBuffer,
                  InputBufferLength,
                  a6,
                  a7,
                  a11 != 0,
                  &Event,
                  &Src);
          if ( v35 )
          {
            v35->RequestorMode = a12;
            ObfReferenceObject(v26);
            v35->Tail.Overlay.CurrentStackLocation[-1].FileObject = v26;
            if ( (_DWORD)v48 )
              KeBugCheckEx(0x164u, 0x24u, (ULONG_PTR)(v25 + 256), 0, 0);
            PerformanceCounter = KeQueryPerformanceCounter(0);
            RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(
              (RIMDropAndReAcquireSyncLock *)&v48,
              (struct RawInputManagerObject *)v20);
            if ( IofCallDriver(DeviceObject, v35) == 259 )
            {
              while ( KeWaitForSingleObject(&Event, UserRequest, 0, 1u, 0) == 257 )
                ;
            }
            Status = Src.Status;
            v36 = v48;
            if ( v48 )
            {
              RIMLockExclusive((char *)v48 + 96);
              ObfDereferenceObject(v36);
            }
            v37 = KeQueryPerformanceCounter(0);
            RimTelemetry::LogBlockingIoControlRequest(
              "RimDeviceIoControl",
              (struct RIMDEV *const)(v25 + 64),
              (unsigned __int64)(1000 * (v37.QuadPart - PerformanceCounter.QuadPart)) / gliQpcFreq.QuadPart,
              Status,
              a3);
            ObfDereferenceObject(v26);
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
          || (v38 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v38 = 0;
        }
        v39 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v38 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v40 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED, v24);
          LOBYTE(v41) = v39;
          LOBYTE(v42) = v38;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v42,
            v41,
            *(_QWORD *)(v40 + 19408),
            3,
            1,
            127,
            (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
        }
      }
      ObfDereferenceObject(v25);
    }
    v20 = v49;
    goto LABEL_24;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v28 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v28 = 0;
  }
  v29 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v28 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v30 = W32GetUserSessionState(WPP_GLOBAL_Control, v18);
    LOBYTE(v31) = v29;
    LOBYTE(v32) = v28;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v32,
      v31,
      *(_QWORD *)(v30 + 19408),
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
0x140091d60  mov     rax, rsp
0x140091d63  mov     [rax+20h], r9
0x140091d67  mov     [rax+18h], r8d
0x140091d6b  mov     [rax+10h], rdx
0x140091d6f  mov     [rax+8], rcx
0x140091d73  push    rbx
0x140091d74  push    rsi
0x140091d75  push    rdi
0x140091d76  push    r12
0x140091d78  push    r13
0x140091d7a  push    r14
0x140091d7c  push    r15
0x140091d7e  sub     rsp, 0B0h
0x140091d85  mov     r15, rcx
0x140091d88  lea     r12, WPP_GLOBAL_Control
0x140091d8f  mov     r10, cs:WPP_GLOBAL_Control
0x140091d96  mov     r14d, 1
0x140091d9c  cmp     r10, r12
0x140091d9f  jz      short loc_140091DAE
0x140091da1  mov     eax, [r10+2Ch]
0x140091da5  test    r14b, al
0x140091da8  jnz     loc_140092294
0x140091dae  xor     esi, esi
0x140091db0  mov     bl, sil
0x140091db3  lea     r13, WPP_RECORDER_INITIALIZED
0x140091dba  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140091dc1  setnz   dil
0x140091dc5  test    bl, bl
0x140091dc7  jnz     short loc_140091DCE
0x140091dc9  test    dil, dil
0x140091dcc  jz      short loc_140091E23
0x140091dce  call    cs:__imp_W32GetUserSessionState
0x140091dd5  nop     dword ptr [rax+rax+00h]
0x140091dda  mov     r9, [rax+4BD0h]
0x140091de1  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140091de8  mov     qword ptr [rsp+0E8h+InputBufferLength], r15
0x140091ded  mov     word ptr [rsp+0E8h+InputBuffer], 7Eh ; '~'
0x140091df4  mov     [rsp+0E8h+IoControlCode], r14d
0x140091df9  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x140091dfe  mov     r8b, dil
0x140091e01  mov     dl, bl
0x140091e03  mov     rcx, cs:WPP_GLOBAL_Control
0x140091e0a  mov     rcx, [rcx+18h]
0x140091e0e  call    WPP_RECORDER_AND_TRACE_SF_
0x140091e13  mov     r9, [rsp+0E8h+arg_18]
0x140091e1b  mov     r15, [rsp+0E8h+arg_0]
0x140091e23  mov     [rsp+0E8h+var_90], rsi
0x140091e28  mov     [rsp+0E8h+Object], rsi
0x140091e2d  cmp     [rsp+0E8h+arg_58], r14d
0x140091e35  jz      loc_1400922A9
0x140091e3b  lea     r9, [rsp+0E8h+var_90]
0x140091e40  mov     r8d, r14d
0x140091e43  mov     edx, 3
0x140091e48  mov     rcx, r15
0x140091e4b  call    RawInputManagerObjectResolveHandle
0x140091e50  mov     r15d, eax
0x140091e53  test    eax, eax
0x140091e55  js      loc_140091FDA
0x140091e5b  mov     rdi, [rsp+0E8h+var_90]
0x140091e60  mov     rcx, [rdi+68h]
0x140091e64  mov     rax, gs:188h
0x140091e6d  mov     edx, esi
0x140091e6f  cmp     rcx, rax
0x140091e72  setz    dl
0x140091e75  mov     dword ptr [rsp+0E8h+var_98], edx
0x140091e79  mov     rbx, rsi
0x140091e7c  mov     [rsp+0E8h+var_80], rbx
0x140091e81  mov     rax, gs:188h
0x140091e8a  cmp     rcx, rax
0x140091e8d  jz      short loc_140091EC2
0x140091e8f  lea     rbx, [rdi+60h]
0x140091e93  mov     [rsp+0E8h+var_80], rbx
0x140091e98  call    cs:__imp_KeEnterCriticalRegion
0x140091e9f  nop     dword ptr [rax+rax+00h]
0x140091ea4  xor     edx, edx
0x140091ea6  mov     rcx, rbx
0x140091ea9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140091eb0  nop     dword ptr [rax+rax+00h]
0x140091eb5  mov     rax, gs:188h
0x140091ebe  mov     [rbx+8], rax
0x140091ec2  cmp     [rdi+49h], sil
0x140091ec6  jnz     loc_140092418
0x140091ecc  lea     r9, [rsp+0E8h+Object]
0x140091ed1  mov     r8d, r14d
0x140091ed4  mov     edx, 3
0x140091ed9  mov     rcx, [rsp+0E8h+arg_8]
0x140091ee1  call    RawInputManagerDeviceObjectResolveHandle
0x140091ee6  mov     r15d, eax
0x140091ee9  test    eax, eax
0x140091eeb  js      loc_140091FBE
0x140091ef1  mov     r13, [rsp+0E8h+Object]
0x140091ef6  cmp     [r13+110h], rsi
0x140091efd  jz      loc_140092387
0x140091f03  mov     r12, [r13+118h]
0x140091f0a  test    r12, r12
0x140091f0d  jz      loc_140092380
0x140091f13  test    dword ptr [r13+0E8h], 1000h
0x140091f1e  jnz     loc_1400922FB
0x140091f24  cmp     [rsp+0E8h+arg_48], esi
0x140091f2b  jz      loc_14009206A
0x140091f31  mov     rdi, [rsp+0E8h+arg_40]
0x140091f39  test    rdi, rdi
0x140091f3c  jz      loc_140092306
0x140091f42  mov     [rsp+0E8h+OutputBufferLength], esi; OutputBufferLength
0x140091f46  mov     eax, [rsp+0E8h+arg_20]
0x140091f4d  mov     r8, [rsp+0E8h+arg_18]
0x140091f55  mov     ecx, [rsp+0E8h+arg_10]
0x140091f5c  xor     r9d, r9d; ApcContext
0x140091f5f  xor     edx, edx; Event
0x140091f61  mov     [rsp+0E8h+OutputBuffer], rsi; OutputBuffer
0x140091f66  mov     [rsp+0E8h+InputBufferLength], eax; InputBufferLength
0x140091f6a  mov     [rsp+0E8h+InputBuffer], r8; InputBuffer
0x140091f6f  mov     [rsp+0E8h+IoControlCode], ecx; IoControlCode
0x140091f73  xor     r8d, r8d; ApcRoutine
0x140091f76  mov     [rsp+0E8h+IoStatusBlock], rdi; IoStatusBlock
0x140091f7b  mov     rcx, [r13+110h]; FileHandle
0x140091f82  cmp     [rsp+0E8h+arg_58], r14d
0x140091f8a  jz      loc_140092329
0x140091f90  call    cs:__imp_ZwDeviceIoControlFile
0x140091f97  nop     dword ptr [rax+rax+00h]
0x140091f9c  lea     r12, WPP_GLOBAL_Control
0x140091fa3  mov     rcx, r13; Object
0x140091fa6  call    cs:__imp_ObfDereferenceObject
0x140091fad  nop     dword ptr [rax+rax+00h]
0x140091fb2  lea     r13, WPP_RECORDER_INITIALIZED
0x140091fb9  mov     rdi, [rsp+0E8h+var_90]
0x140091fbe  test    rbx, rbx
0x140091fc1  jz      short loc_140091FCB
0x140091fc3  mov     rcx, rbx
0x140091fc6  call    RIMUnlockExclusive
0x140091fcb  mov     rcx, rdi; Object
0x140091fce  call    cs:__imp_ObfDereferenceObject
0x140091fd5  nop     dword ptr [rax+rax+00h]
0x140091fda  mov     rcx, cs:WPP_GLOBAL_Control
0x140091fe1  cmp     rcx, r12
0x140091fe4  jz      short loc_140091FF2
0x140091fe6  mov     eax, [rcx+2Ch]
0x140091fe9  test    r14b, al
0x140091fec  jnz     loc_1400924A5
0x140091ff2  mov     bl, sil
0x140091ff5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140091ffc  setnz   dil
0x140092000  test    bl, bl
0x140092002  jnz     short loc_140092009
0x140092004  test    dil, dil
0x140092007  jz      short loc_140092053
0x140092009  call    cs:__imp_W32GetUserSessionState
0x140092010  nop     dword ptr [rax+rax+00h]
0x140092015  mov     r9, [rax+4BD0h]
0x14009201c  mov     dword ptr [rsp+0E8h+OutputBuffer], r15d
0x140092021  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x140092028  mov     qword ptr [rsp+0E8h+InputBufferLength], rax
0x14009202d  mov     word ptr [rsp+0E8h+InputBuffer], 81h
0x140092034  mov     [rsp+0E8h+IoControlCode], r14d
0x140092039  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x14009203e  mov     r8b, dil
0x140092041  mov     dl, bl
0x140092043  mov     rcx, cs:WPP_GLOBAL_Control
0x14009204a  mov     rcx, [rcx+18h]
0x14009204e  call    WPP_RECORDER_AND_TRACE_SF_d
0x140092053  mov     eax, r15d
0x140092056  add     rsp, 0B0h
0x14009205d  pop     r15
0x14009205f  pop     r14
0x140092061  pop     r13
0x140092063  pop     r12
0x140092065  pop     rdi
0x140092066  pop     rsi
0x140092067  pop     rbx
0x140092068  retn
0x14009206a  xorps   xmm0, xmm0
0x14009206d  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x140092072  xorps   xmm1, xmm1
0x140092075  xor     eax, eax
0x140092077  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm1
0x14009207f  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x140092087  mov     rcx, r12; FileObject
0x14009208a  call    cs:__imp_IoGetRelatedDeviceObject
0x140092091  nop     dword ptr [rax+rax+00h]
0x140092096  mov     r15, rax
0x140092099  mov     [rsp+0E8h+DeviceObject], rax
0x1400920a1  xor     r8d, r8d; State
0x1400920a4  mov     edx, r14d; Type
0x1400920a7  lea     rcx, [rsp+0E8h+Event]; Event
0x1400920af  call    cs:__imp_KeInitializeEvent
0x1400920b6  nop     dword ptr [rax+rax+00h]
0x1400920bb  cmp     [rsp+0E8h+arg_50], esi
0x1400920c2  setnz   cl
0x1400920c5  lea     rax, [rsp+0E8h+Src]
0x1400920ca  mov     [rsp+0E8h+OutputBuffer], rax; IoStatusBlock
0x1400920cf  lea     rax, [rsp+0E8h+Event]
0x1400920d7  mov     qword ptr [rsp+0E8h+InputBufferLength], rax; Event
0x1400920dc  mov     byte ptr [rsp+0E8h+InputBuffer], cl; InternalDeviceIoControl
0x1400920e0  mov     ecx, [rsp+0E8h+arg_30]
0x1400920e7  mov     [rsp+0E8h+IoControlCode], ecx; OutputBufferLength
0x1400920eb  mov     rax, [rsp+0E8h+arg_28]
0x1400920f3  mov     [rsp+0E8h+IoStatusBlock], rax; OutputBuffer
0x1400920f8  mov     r9d, [rsp+0E8h+arg_20]; InputBufferLength
0x140092100  mov     r8, [rsp+0E8h+arg_18]; InputBuffer
0x140092108  mov     rdx, r15; DeviceObject
0x14009210b  mov     ecx, [rsp+0E8h+arg_10]; IoControlCode
0x140092112  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140092119  nop     dword ptr [rax+rax+00h]
0x14009211e  mov     r15, rax
0x140092121  test    rax, rax
0x140092124  jz      loc_14009225D
0x14009212a  mov     eax, [rsp+0E8h+arg_58]
0x140092131  mov     [r15+40h], al
0x140092135  mov     rcx, r12; Object
0x140092138  call    cs:__imp_ObfReferenceObject
0x14009213f  nop     dword ptr [rax+rax+00h]
0x140092144  mov     rcx, [r15+0B8h]
0x14009214b  mov     [rcx-18h], r12
0x14009214f  cmp     dword ptr [rsp+0E8h+var_98], esi
0x140092153  jz      short loc_14009217A
0x140092155  lea     r8, [r13+100h]; BugCheckParameter2
0x14009215c  mov     [rsp+0E8h+IoStatusBlock], rsi; BugCheckParameter4
0x140092161  xor     r9d, r9d; BugCheckParameter3
0x140092164  lea     edx, [r9+24h]; BugCheckParameter1
0x140092168  mov     ecx, 164h; BugCheckCode
0x14009216d  call    cs:__imp_KeBugCheckEx
0x14009217a  xor     ecx, ecx; PerformanceFrequency
0x14009217c  call    cs:__imp_KeQueryPerformanceCounter
0x140092183  nop     dword ptr [rax+rax+00h]
0x140092188  mov     [rsp+0E8h+var_60], rax
0x140092190  mov     rdx, rdi; struct RawInputManagerObject *
0x140092193  lea     rcx, [rsp+0E8h+var_98]; this
0x140092198  call    ??0RIMDropAndReAcquireSyncLock@@QEAA@PEAURawInputManagerObject@@@Z; RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(RawInputManagerObject *)
0x14009219d  mov     rdx, r15; Irp
0x1400921a0  mov     rcx, [rsp+0E8h+DeviceObject]; DeviceObject
0x1400921a8  call    cs:__imp_IofCallDriver
0x1400921af  nop     dword ptr [rax+rax+00h]
0x1400921b4  cmp     eax, 103h
0x1400921b9  jz      loc_140092265
0x1400921bf  mov     r15d, dword ptr [rsp+0E8h+Src]
0x1400921c4  mov     rdi, [rsp+0E8h+var_98]
0x1400921c9  test    rdi, rdi
0x1400921cc  jz      short loc_1400921E6
0x1400921ce  lea     rcx, [rdi+60h]
0x1400921d2  call    RIMLockExclusive
0x1400921d7  mov     rcx, rdi; Object
0x1400921da  call    cs:__imp_ObfDereferenceObject
0x1400921e1  nop     dword ptr [rax+rax+00h]
0x1400921e6  xor     ecx, ecx; PerformanceFrequency
0x1400921e8  call    cs:__imp_KeQueryPerformanceCounter
0x1400921ef  nop     dword ptr [rax+rax+00h]
0x1400921f4  sub     rax, [rsp+0E8h+var_60]
0x1400921fc  imul    rax, 3E8h
0x140092203  xor     edx, edx
0x140092205  div     qword ptr cs:gliQpcFreq
0x14009220c  mov     r8, rax; unsigned __int64
0x14009220f  mov     eax, [rsp+0E8h+arg_10]
0x140092216  mov     dword ptr [rsp+0E8h+IoStatusBlock], eax; unsigned int
0x14009221a  mov     r9d, r15d; int
0x14009221d  lea     rdx, [r13+40h]; struct RIMDEV *
0x140092221  lea     rcx, aRimdeviceiocon; "RimDeviceIoControl"
0x140092228  call    ?LogBlockingIoControlRequest@RimTelemetry@@SAXPEBDQEAURIMDEV@@_KJK@Z; RimTelemetry::LogBlockingIoControlRequest(char const *,RIMDEV * const,unsigned __int64,long,ulong)
0x14009222d  mov     rcx, r12; Object
0x140092230  call    cs:__imp_ObfDereferenceObject
0x140092237  nop     dword ptr [rax+rax+00h]
0x14009223c  cmp     [rsp+0E8h+arg_58], esi
0x140092243  jnz     loc_14009233A
0x140092249  mov     rcx, [rsp+0E8h+Src.Information]
0x14009224e  mov     rax, [rsp+0E8h+arg_38]
0x140092256  mov     [rax], ecx
0x140092258  jmp     loc_140091F9C
0x14009225d  mov     r15d, 0C000009Ch
0x140092263  jmp     short loc_14009223C
0x140092265  mov     [rsp+0E8h+IoStatusBlock], rsi; Timeout
0x14009226a  mov     r9b, r14b; Alertable
0x14009226d  xor     r8d, r8d; WaitMode
0x140092270  lea     edx, [r8+6]; WaitReason
0x140092274  lea     rcx, [rsp+0E8h+Event]; Object
0x14009227c  call    cs:__imp_KeWaitForSingleObject
0x140092283  nop     dword ptr [rax+rax+00h]
0x140092288  cmp     eax, 101h
0x14009228d  jz      short loc_140092265
0x14009228f  jmp     loc_1400921BF
0x140092294  cmp     byte ptr [r10+29h], 4
0x140092299  jb      loc_140091DAE
0x14009229f  mov     bl, r14b
0x1400922a2  xor     esi, esi
0x1400922a4  jmp     loc_140091DB3
0x1400922a9  mov     edx, [rsp+0E8h+arg_20]; Length
0x1400922b0  mov     r8d, r14d; Alignment
0x1400922b3  mov     rcx, r9; Address
0x1400922b6  call    cs:__imp_ProbeForRead
0x1400922bd  nop     dword ptr [rax+rax+00h]
0x1400922c2  jmp     short loc_1400922CE
0x1400922c4  mov     eax, 0C000000Dh
0x1400922c9  jmp     loc_140092056
0x1400922ce  mov     edx, [rsp+0E8h+arg_30]; Length
0x1400922d5  mov     r8d, r14d; Alignment
0x1400922d8  mov     rcx, [rsp+0E8h+arg_28]; Address
0x1400922e0  call    cs:__imp_ProbeForWrite
0x1400922e7  nop     dword ptr [rax+rax+00h]
0x1400922ec  jmp     loc_140091E3B
0x1400922f1  mov     eax, 0C000000Dh
0x1400922f6  jmp     loc_140092056
0x1400922fb  mov     r15d, 0C00000BBh
  ... truncated ...
```
