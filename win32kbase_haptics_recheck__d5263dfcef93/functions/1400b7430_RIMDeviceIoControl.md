# RIMDeviceIoControl

- ea: `0x1400b7430`
- end: `0x1400b7b87`
- name: `RIMDeviceIoControl`
- size: `1879`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140181fa0`
- `0x140212b3c`

## callees

- `0x14005a7f0`
- `0x140066bf0`
- `0x140071828`
- `0x1400718f0`
- `0x14009e3c0`
- `0x1400b5d94`
- `0x1400b7430`
- `0x1400b7e20`
- `0x1400d7df0`
- `0x1401aa4fc`
- `0x1402bd054`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400b7986`
- `ntoskrnl!ProbeForRead` at `0x1400b7986`
- `ntoskrnl!KeBugCheckEx` at `0x1400b783d`
- `ntoskrnl!KeBugCheckEx` at `0x1400b783d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b7579`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400b7579`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b7568`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400b7568`
- `ntoskrnl!ProbeForWrite` at `0x1400b79b0`
- `ntoskrnl!ProbeForWrite` at `0x1400b79b0`
- `ntoskrnl!ObfReferenceObject` at `0x1400b7808`
- `ntoskrnl!ObfReferenceObject` at `0x1400b7808`
- `ntoskrnl!KeInitializeEvent` at `0x1400b777f`
- `ntoskrnl!KeInitializeEvent` at `0x1400b777f`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b794c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400b794c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400b775a`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x1400b775a`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b77e2`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x1400b77e2`
- `ntoskrnl!IofCallDriver` at `0x1400b7878`
- `ntoskrnl!IofCallDriver` at `0x1400b7878`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400b7660`
- `ntoskrnl!ZwDeviceIoControlFile` at `0x1400b7660`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400b79f9`
- `ntoskrnl!NtDeviceIoControlFile` at `0x1400b79f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b7676`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b769e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b78aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b7900`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b7676`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b769e`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b78aa`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b7900`
- `WIN32K!W32GetUserSessionState` at `0x1400b749e`
- `WIN32K!W32GetUserSessionState` at `0x1400b76d9`
- `WIN32K!W32GetUserSessionState` at `0x1400b7a9d`
- `WIN32K!W32GetUserSessionState` at `0x1400b7b23`
- `WIN32K!W32GetUserSessionState` at `0x1400b749e`
- `WIN32K!W32GetUserSessionState` at `0x1400b76d9`
- `WIN32K!W32GetUserSessionState` at `0x1400b7a9d`
- `WIN32K!W32GetUserSessionState` at `0x1400b7b23`
- `HAL!KeQueryPerformanceCounter` at `0x1400b784c`
- `HAL!KeQueryPerformanceCounter` at `0x1400b78b8`
- `HAL!KeQueryPerformanceCounter` at `0x1400b784c`
- `HAL!KeQueryPerformanceCounter` at `0x1400b78b8`

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
  NTSTATUS Status; // r15d
  _QWORD *v19; // rdi
  struct _KTHREAD *v20; // rcx
  char *v21; // rbx
  char *v22; // r13
  struct _FILE_OBJECT *v23; // r12
  void *v24; // rcx
  char v25; // bl
  bool v26; // di
  __int64 v27; // rax
  int v28; // r8d
  int v29; // edx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // r15
  PIRP v32; // r15
  PVOID v33; // rdi
  LARGE_INTEGER v34; // rax
  char v35; // di
  bool v36; // r12
  __int64 v37; // rax
  int v38; // r8d
  int v39; // edx
  char v40; // di
  bool v41; // r12
  __int64 v42; // rax
  int v43; // r8d
  int v44; // edx
  PVOID v45; // [rsp+50h] [rbp-98h] BYREF
  PVOID v46; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  char *v48; // [rsp+68h] [rbp-80h]
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
    UserSessionState = W32GetUserSessionState(a1);
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
  v46 = 0;
  Object = 0;
  if ( a12 == 1 )
  {
    ProbeForRead(a4, InputBufferLength, 1u);
    ProbeForWrite(a6, a7, 1u);
  }
  Status = RawInputManagerObjectResolveHandle(v12, 3, 1, &v46);
  if ( Status >= 0 )
  {
    v19 = v46;
    v20 = (struct _KTHREAD *)*((_QWORD *)v46 + 13);
    LODWORD(v45) = v20 == KeGetCurrentThread();
    v21 = 0;
    v48 = 0;
    if ( v20 != KeGetCurrentThread() )
    {
      v21 = (char *)v46 + 96;
      v48 = (char *)v46 + 96;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v19 + 12, 0);
      v19[13] = KeGetCurrentThread();
    }
    if ( *((_BYTE *)v19 + 73) )
    {
      Status = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v40 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v40 = 0;
      }
      v41 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( v40 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v42 = W32GetUserSessionState(WPP_GLOBAL_Control);
        LOBYTE(v43) = v41;
        LOBYTE(v44) = v40;
        WPP_RECORDER_AND_TRACE_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 3),
          v44,
          v43,
          *(_QWORD *)(v42 + 19408),
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
        if ( v21 )
          RIMUnlockExclusive(v21);
        ObfDereferenceObject(v19);
        goto LABEL_27;
      }
      v22 = (char *)Object;
      if ( *((_QWORD *)Object + 34) && (v23 = (struct _FILE_OBJECT *)*((_QWORD *)Object + 35)) != 0 )
      {
        if ( (*((_DWORD *)Object + 58) & 0x1000) != 0 )
        {
          Status = -1073741637;
        }
        else if ( a10 )
        {
          if ( !IoStatusBlock )
          {
            LODWORD(v45) = 0x20000;
            MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 4101);
          }
          v24 = (void *)*((_QWORD *)v22 + 34);
          if ( a12 == 1 )
            NtDeviceIoControlFile(v24, 0, 0, 0, IoStatusBlock, a3, InputBuffer, InputBufferLength, 0, 0);
          else
            ZwDeviceIoControlFile(v24, 0, 0, 0, IoStatusBlock, a3, InputBuffer, InputBufferLength, 0, 0);
        }
        else
        {
          Src = 0;
          memset(&Event, 0, sizeof(Event));
          RelatedDeviceObject = IoGetRelatedDeviceObject(v23);
          DeviceObject = RelatedDeviceObject;
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          v32 = IoBuildDeviceIoControlRequest(
                  a3,
                  RelatedDeviceObject,
                  InputBuffer,
                  InputBufferLength,
                  a6,
                  a7,
                  a11 != 0,
                  &Event,
                  &Src);
          if ( v32 )
          {
            v32->RequestorMode = a12;
            ObfReferenceObject(v23);
            v32->Tail.Overlay.CurrentStackLocation[-1].FileObject = v23;
            if ( (_DWORD)v45 )
              KeBugCheckEx(0x164u, 0x24u, (ULONG_PTR)(v22 + 256), 0, 0);
            PerformanceCounter = KeQueryPerformanceCounter(0);
            RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(
              (RIMDropAndReAcquireSyncLock *)&v45,
              (struct RawInputManagerObject *)v19);
            if ( IofCallDriver(DeviceObject, v32) == 259 )
            {
              while ( KeWaitForSingleObject(&Event, UserRequest, 0, 1u, 0) == 257 )
                ;
            }
            Status = Src.Status;
            v33 = v45;
            if ( v45 )
            {
              RIMLockExclusive((char *)v45 + 96);
              ObfDereferenceObject(v33);
            }
            v34 = KeQueryPerformanceCounter(0);
            RimTelemetry::LogBlockingIoControlRequest(
              "RimDeviceIoControl",
              (struct RIMDEV *const)(v22 + 64),
              (unsigned __int64)(1000 * (v34.QuadPart - PerformanceCounter.QuadPart)) / gliQpcFreq.QuadPart,
              Status,
              a3);
            ObfDereferenceObject(v23);
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
          || (v35 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
        {
          v35 = 0;
        }
        v36 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v35 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v37 = W32GetUserSessionState(&WPP_RECORDER_INITIALIZED);
          LOBYTE(v38) = v36;
          LOBYTE(v39) = v35;
          WPP_RECORDER_AND_TRACE_SF_(
            *((_QWORD *)WPP_GLOBAL_Control + 3),
            v39,
            v38,
            *(_QWORD *)(v37 + 19408),
            3,
            1,
            127,
            (__int64)WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
        }
      }
      ObfDereferenceObject(v22);
    }
    v19 = v46;
    goto LABEL_24;
  }
LABEL_27:
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v25 = 0;
  }
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v27 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v28) = v26;
    LOBYTE(v29) = v25;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v29,
      v28,
      *(_QWORD *)(v27 + 19408),
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
0x1400b7430  mov     rax, rsp
0x1400b7433  mov     [rax+20h], r9
0x1400b7437  mov     [rax+18h], r8d
0x1400b743b  mov     [rax+10h], rdx
0x1400b743f  mov     [rax+8], rcx
0x1400b7443  push    rbx
0x1400b7444  push    rsi
0x1400b7445  push    rdi
0x1400b7446  push    r12
0x1400b7448  push    r13
0x1400b744a  push    r14
0x1400b744c  push    r15
0x1400b744e  sub     rsp, 0B0h
0x1400b7455  mov     r15, rcx
0x1400b7458  lea     r12, WPP_GLOBAL_Control
0x1400b745f  mov     r10, cs:WPP_GLOBAL_Control
0x1400b7466  mov     r14d, 1
0x1400b746c  cmp     r10, r12
0x1400b746f  jz      short loc_1400B747E
0x1400b7471  mov     eax, [r10+2Ch]
0x1400b7475  test    r14b, al
0x1400b7478  jnz     loc_1400B7964
0x1400b747e  xor     esi, esi
0x1400b7480  mov     bl, sil
0x1400b7483  lea     r13, WPP_RECORDER_INITIALIZED
0x1400b748a  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400b7491  setnz   dil
0x1400b7495  test    bl, bl
0x1400b7497  jnz     short loc_1400B749E
0x1400b7499  test    dil, dil
0x1400b749c  jz      short loc_1400B74F3
0x1400b749e  call    cs:__imp_W32GetUserSessionState
0x1400b74a5  nop     dword ptr [rax+rax+00h]
0x1400b74aa  mov     r9, [rax+4BD0h]
0x1400b74b1  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b74b8  mov     qword ptr [rsp+0E8h+InputBufferLength], r15
0x1400b74bd  mov     word ptr [rsp+0E8h+InputBuffer], 7Eh ; '~'
0x1400b74c4  mov     [rsp+0E8h+IoControlCode], r14d
0x1400b74c9  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x1400b74ce  mov     r8b, dil
0x1400b74d1  mov     dl, bl
0x1400b74d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b74da  mov     rcx, [rcx+18h]
0x1400b74de  call    WPP_RECORDER_AND_TRACE_SF_
0x1400b74e3  mov     r9, [rsp+0E8h+arg_18]
0x1400b74eb  mov     r15, [rsp+0E8h+arg_0]
0x1400b74f3  mov     [rsp+0E8h+var_90], rsi
0x1400b74f8  mov     [rsp+0E8h+Object], rsi
0x1400b74fd  cmp     [rsp+0E8h+arg_58], r14d
0x1400b7505  jz      loc_1400B7979
0x1400b750b  lea     r9, [rsp+0E8h+var_90]
0x1400b7510  mov     r8d, r14d
0x1400b7513  mov     edx, 3
0x1400b7518  mov     rcx, r15
0x1400b751b  call    RawInputManagerObjectResolveHandle
0x1400b7520  mov     r15d, eax
0x1400b7523  test    eax, eax
0x1400b7525  js      loc_1400B76AA
0x1400b752b  mov     rdi, [rsp+0E8h+var_90]
0x1400b7530  mov     rcx, [rdi+68h]
0x1400b7534  mov     rax, gs:188h
0x1400b753d  mov     edx, esi
0x1400b753f  cmp     rcx, rax
0x1400b7542  setz    dl
0x1400b7545  mov     dword ptr [rsp+0E8h+var_98], edx
0x1400b7549  mov     rbx, rsi
0x1400b754c  mov     [rsp+0E8h+var_80], rbx
0x1400b7551  mov     rax, gs:188h
0x1400b755a  cmp     rcx, rax
0x1400b755d  jz      short loc_1400B7592
0x1400b755f  lea     rbx, [rdi+60h]
0x1400b7563  mov     [rsp+0E8h+var_80], rbx
0x1400b7568  call    cs:__imp_KeEnterCriticalRegion
0x1400b756f  nop     dword ptr [rax+rax+00h]
0x1400b7574  xor     edx, edx
0x1400b7576  mov     rcx, rbx
0x1400b7579  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400b7580  nop     dword ptr [rax+rax+00h]
0x1400b7585  mov     rax, gs:188h
0x1400b758e  mov     [rbx+8], rax
0x1400b7592  cmp     [rdi+49h], sil
0x1400b7596  jnz     loc_1400B7AE8
0x1400b759c  lea     r9, [rsp+0E8h+Object]
0x1400b75a1  mov     r8d, r14d
0x1400b75a4  mov     edx, 3
0x1400b75a9  mov     rcx, [rsp+0E8h+arg_8]
0x1400b75b1  call    RawInputManagerDeviceObjectResolveHandle
0x1400b75b6  mov     r15d, eax
0x1400b75b9  test    eax, eax
0x1400b75bb  js      loc_1400B768E
0x1400b75c1  mov     r13, [rsp+0E8h+Object]
0x1400b75c6  cmp     [r13+110h], rsi
0x1400b75cd  jz      loc_1400B7A57
0x1400b75d3  mov     r12, [r13+118h]
0x1400b75da  test    r12, r12
0x1400b75dd  jz      loc_1400B7A50
0x1400b75e3  test    dword ptr [r13+0E8h], 1000h
0x1400b75ee  jnz     loc_1400B79CB
0x1400b75f4  cmp     [rsp+0E8h+arg_48], esi
0x1400b75fb  jz      loc_1400B773A
0x1400b7601  mov     rdi, [rsp+0E8h+arg_40]
0x1400b7609  test    rdi, rdi
0x1400b760c  jz      loc_1400B79D6
0x1400b7612  mov     [rsp+0E8h+OutputBufferLength], esi; OutputBufferLength
0x1400b7616  mov     eax, [rsp+0E8h+arg_20]
0x1400b761d  mov     r8, [rsp+0E8h+arg_18]
0x1400b7625  mov     ecx, [rsp+0E8h+arg_10]
0x1400b762c  xor     r9d, r9d; ApcContext
0x1400b762f  xor     edx, edx; Event
0x1400b7631  mov     [rsp+0E8h+OutputBuffer], rsi; OutputBuffer
0x1400b7636  mov     [rsp+0E8h+InputBufferLength], eax; InputBufferLength
0x1400b763a  mov     [rsp+0E8h+InputBuffer], r8; InputBuffer
0x1400b763f  mov     [rsp+0E8h+IoControlCode], ecx; IoControlCode
0x1400b7643  xor     r8d, r8d; ApcRoutine
0x1400b7646  mov     [rsp+0E8h+IoStatusBlock], rdi; IoStatusBlock
0x1400b764b  mov     rcx, [r13+110h]; FileHandle
0x1400b7652  cmp     [rsp+0E8h+arg_58], r14d
0x1400b765a  jz      loc_1400B79F9
0x1400b7660  call    cs:__imp_ZwDeviceIoControlFile
0x1400b7667  nop     dword ptr [rax+rax+00h]
0x1400b766c  lea     r12, WPP_GLOBAL_Control
0x1400b7673  mov     rcx, r13; Object
0x1400b7676  call    cs:__imp_ObfDereferenceObject
0x1400b767d  nop     dword ptr [rax+rax+00h]
0x1400b7682  lea     r13, WPP_RECORDER_INITIALIZED
0x1400b7689  mov     rdi, [rsp+0E8h+var_90]
0x1400b768e  test    rbx, rbx
0x1400b7691  jz      short loc_1400B769B
0x1400b7693  mov     rcx, rbx
0x1400b7696  call    RIMUnlockExclusive
0x1400b769b  mov     rcx, rdi; Object
0x1400b769e  call    cs:__imp_ObfDereferenceObject
0x1400b76a5  nop     dword ptr [rax+rax+00h]
0x1400b76aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b76b1  cmp     rcx, r12
0x1400b76b4  jz      short loc_1400B76C2
0x1400b76b6  mov     eax, [rcx+2Ch]
0x1400b76b9  test    r14b, al
0x1400b76bc  jnz     loc_1400B7B75
0x1400b76c2  mov     bl, sil
0x1400b76c5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400b76cc  setnz   dil
0x1400b76d0  test    bl, bl
0x1400b76d2  jnz     short loc_1400B76D9
0x1400b76d4  test    dil, dil
0x1400b76d7  jz      short loc_1400B7723
0x1400b76d9  call    cs:__imp_W32GetUserSessionState
0x1400b76e0  nop     dword ptr [rax+rax+00h]
0x1400b76e5  mov     r9, [rax+4BD0h]
0x1400b76ec  mov     dword ptr [rsp+0E8h+OutputBuffer], r15d
0x1400b76f1  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b76f8  mov     qword ptr [rsp+0E8h+InputBufferLength], rax
0x1400b76fd  mov     word ptr [rsp+0E8h+InputBuffer], 81h
0x1400b7704  mov     [rsp+0E8h+IoControlCode], r14d
0x1400b7709  mov     byte ptr [rsp+0E8h+IoStatusBlock], 4
0x1400b770e  mov     r8b, dil
0x1400b7711  mov     dl, bl
0x1400b7713  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b771a  mov     rcx, [rcx+18h]
0x1400b771e  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400b7723  mov     eax, r15d
0x1400b7726  add     rsp, 0B0h
0x1400b772d  pop     r15
0x1400b772f  pop     r14
0x1400b7731  pop     r13
0x1400b7733  pop     r12
0x1400b7735  pop     rdi
0x1400b7736  pop     rsi
0x1400b7737  pop     rbx
0x1400b7738  retn
0x1400b773a  xorps   xmm0, xmm0
0x1400b773d  movups  xmmword ptr [rsp+0E8h+Src], xmm0
0x1400b7742  xorps   xmm1, xmm1
0x1400b7745  xor     eax, eax
0x1400b7747  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm1
0x1400b774f  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x1400b7757  mov     rcx, r12; FileObject
0x1400b775a  call    cs:__imp_IoGetRelatedDeviceObject
0x1400b7761  nop     dword ptr [rax+rax+00h]
0x1400b7766  mov     r15, rax
0x1400b7769  mov     [rsp+0E8h+DeviceObject], rax
0x1400b7771  xor     r8d, r8d; State
0x1400b7774  mov     edx, r14d; Type
0x1400b7777  lea     rcx, [rsp+0E8h+Event]; Event
0x1400b777f  call    cs:__imp_KeInitializeEvent
0x1400b7786  nop     dword ptr [rax+rax+00h]
0x1400b778b  cmp     [rsp+0E8h+arg_50], esi
0x1400b7792  setnz   cl
0x1400b7795  lea     rax, [rsp+0E8h+Src]
0x1400b779a  mov     [rsp+0E8h+OutputBuffer], rax; IoStatusBlock
0x1400b779f  lea     rax, [rsp+0E8h+Event]
0x1400b77a7  mov     qword ptr [rsp+0E8h+InputBufferLength], rax; Event
0x1400b77ac  mov     byte ptr [rsp+0E8h+InputBuffer], cl; InternalDeviceIoControl
0x1400b77b0  mov     ecx, [rsp+0E8h+arg_30]
0x1400b77b7  mov     [rsp+0E8h+IoControlCode], ecx; OutputBufferLength
0x1400b77bb  mov     rax, [rsp+0E8h+arg_28]
0x1400b77c3  mov     [rsp+0E8h+IoStatusBlock], rax; OutputBuffer
0x1400b77c8  mov     r9d, [rsp+0E8h+arg_20]; InputBufferLength
0x1400b77d0  mov     r8, [rsp+0E8h+arg_18]; InputBuffer
0x1400b77d8  mov     rdx, r15; DeviceObject
0x1400b77db  mov     ecx, [rsp+0E8h+arg_10]; IoControlCode
0x1400b77e2  call    cs:__imp_IoBuildDeviceIoControlRequest
0x1400b77e9  nop     dword ptr [rax+rax+00h]
0x1400b77ee  mov     r15, rax
0x1400b77f1  test    rax, rax
0x1400b77f4  jz      loc_1400B792D
0x1400b77fa  mov     eax, [rsp+0E8h+arg_58]
0x1400b7801  mov     [r15+40h], al
0x1400b7805  mov     rcx, r12; Object
0x1400b7808  call    cs:__imp_ObfReferenceObject
0x1400b780f  nop     dword ptr [rax+rax+00h]
0x1400b7814  mov     rcx, [r15+0B8h]
0x1400b781b  mov     [rcx-18h], r12
0x1400b781f  cmp     dword ptr [rsp+0E8h+var_98], esi
0x1400b7823  jz      short loc_1400B784A
0x1400b7825  lea     r8, [r13+100h]; BugCheckParameter2
0x1400b782c  mov     [rsp+0E8h+IoStatusBlock], rsi; BugCheckParameter4
0x1400b7831  xor     r9d, r9d; BugCheckParameter3
0x1400b7834  lea     edx, [r9+24h]; BugCheckParameter1
0x1400b7838  mov     ecx, 164h; BugCheckCode
0x1400b783d  call    cs:__imp_KeBugCheckEx
0x1400b784a  xor     ecx, ecx; PerformanceFrequency
0x1400b784c  call    cs:__imp_KeQueryPerformanceCounter
0x1400b7853  nop     dword ptr [rax+rax+00h]
0x1400b7858  mov     [rsp+0E8h+var_60], rax
0x1400b7860  mov     rdx, rdi; struct RawInputManagerObject *
0x1400b7863  lea     rcx, [rsp+0E8h+var_98]; this
0x1400b7868  call    ??0RIMDropAndReAcquireSyncLock@@QEAA@PEAURawInputManagerObject@@@Z; RIMDropAndReAcquireSyncLock::RIMDropAndReAcquireSyncLock(RawInputManagerObject *)
0x1400b786d  mov     rdx, r15; Irp
0x1400b7870  mov     rcx, [rsp+0E8h+DeviceObject]; DeviceObject
0x1400b7878  call    cs:__imp_IofCallDriver
0x1400b787f  nop     dword ptr [rax+rax+00h]
0x1400b7884  cmp     eax, 103h
0x1400b7889  jz      loc_1400B7935
0x1400b788f  mov     r15d, dword ptr [rsp+0E8h+Src]
0x1400b7894  mov     rdi, [rsp+0E8h+var_98]
0x1400b7899  test    rdi, rdi
0x1400b789c  jz      short loc_1400B78B6
0x1400b789e  lea     rcx, [rdi+60h]
0x1400b78a2  call    RIMLockExclusive
0x1400b78a7  mov     rcx, rdi; Object
0x1400b78aa  call    cs:__imp_ObfDereferenceObject
0x1400b78b1  nop     dword ptr [rax+rax+00h]
0x1400b78b6  xor     ecx, ecx; PerformanceFrequency
0x1400b78b8  call    cs:__imp_KeQueryPerformanceCounter
0x1400b78bf  nop     dword ptr [rax+rax+00h]
0x1400b78c4  sub     rax, [rsp+0E8h+var_60]
0x1400b78cc  imul    rax, 3E8h
0x1400b78d3  xor     edx, edx
0x1400b78d5  div     qword ptr cs:gliQpcFreq
0x1400b78dc  mov     r8, rax; unsigned __int64
0x1400b78df  mov     eax, [rsp+0E8h+arg_10]
0x1400b78e6  mov     dword ptr [rsp+0E8h+IoStatusBlock], eax; unsigned int
0x1400b78ea  mov     r9d, r15d; int
0x1400b78ed  lea     rdx, [r13+40h]; struct RIMDEV *
0x1400b78f1  lea     rcx, aRimdeviceiocon; "RimDeviceIoControl"
0x1400b78f8  call    ?LogBlockingIoControlRequest@RimTelemetry@@SAXPEBDQEAURIMDEV@@_KJK@Z; RimTelemetry::LogBlockingIoControlRequest(char const *,RIMDEV * const,unsigned __int64,long,ulong)
0x1400b78fd  mov     rcx, r12; Object
0x1400b7900  call    cs:__imp_ObfDereferenceObject
0x1400b7907  nop     dword ptr [rax+rax+00h]
0x1400b790c  cmp     [rsp+0E8h+arg_58], esi
0x1400b7913  jnz     loc_1400B7A0A
0x1400b7919  mov     rcx, [rsp+0E8h+Src.Information]
0x1400b791e  mov     rax, [rsp+0E8h+arg_38]
0x1400b7926  mov     [rax], ecx
0x1400b7928  jmp     loc_1400B766C
0x1400b792d  mov     r15d, 0C000009Ch
0x1400b7933  jmp     short loc_1400B790C
0x1400b7935  mov     [rsp+0E8h+IoStatusBlock], rsi; Timeout
0x1400b793a  mov     r9b, r14b; Alertable
0x1400b793d  xor     r8d, r8d; WaitMode
0x1400b7940  lea     edx, [r8+6]; WaitReason
0x1400b7944  lea     rcx, [rsp+0E8h+Event]; Object
0x1400b794c  call    cs:__imp_KeWaitForSingleObject
0x1400b7953  nop     dword ptr [rax+rax+00h]
0x1400b7958  cmp     eax, 101h
0x1400b795d  jz      short loc_1400B7935
0x1400b795f  jmp     loc_1400B788F
0x1400b7964  cmp     byte ptr [r10+29h], 4
0x1400b7969  jb      loc_1400B747E
0x1400b796f  mov     bl, r14b
0x1400b7972  xor     esi, esi
0x1400b7974  jmp     loc_1400B7483
0x1400b7979  mov     edx, [rsp+0E8h+arg_20]; Length
0x1400b7980  mov     r8d, r14d; Alignment
0x1400b7983  mov     rcx, r9; Address
0x1400b7986  call    cs:__imp_ProbeForRead
0x1400b798d  nop     dword ptr [rax+rax+00h]
0x1400b7992  jmp     short loc_1400B799E
0x1400b7994  mov     eax, 0C000000Dh
0x1400b7999  jmp     loc_1400B7726
0x1400b799e  mov     edx, [rsp+0E8h+arg_30]; Length
0x1400b79a5  mov     r8d, r14d; Alignment
0x1400b79a8  mov     rcx, [rsp+0E8h+arg_28]; Address
0x1400b79b0  call    cs:__imp_ProbeForWrite
0x1400b79b7  nop     dword ptr [rax+rax+00h]
0x1400b79bc  jmp     loc_1400B750B
0x1400b79c1  mov     eax, 0C000000Dh
0x1400b79c6  jmp     loc_1400B7726
0x1400b79cb  mov     r15d, 0C00000BBh
  ... truncated ...
```
