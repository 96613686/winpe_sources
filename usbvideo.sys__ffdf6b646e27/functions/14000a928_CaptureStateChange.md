# CaptureStateChange

- ea: `0x14000a928`
- end: `0x14000b1f3`
- name: `CaptureStateChange`
- size: `2251`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14000a880`

## callees

- `0x140001160`
- `0x140001544`
- `0x140004bac`
- `0x140009dc8`
- `0x14000a928`
- `0x14000b1fc`
- `0x14000b260`
- `0x14000b34c`
- `0x14000b7fc`
- `0x140015234`
- `0x1400166ac`
- `0x1400188bc`
- `0x14001d0cc`
- `0x140039120`
- `0x14003a3c4`
- `0x140040a70`

## import_xrefs

- `ntoskrnl!KeResetEvent` at `0x14000aaad`
- `ntoskrnl!KeResetEvent` at `0x14000ab48`
- `ntoskrnl!KeResetEvent` at `0x14000aaad`
- `ntoskrnl!KeResetEvent` at `0x14000ab48`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa91`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ab29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000abbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b06d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000aa91`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ab29`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000abbb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b06d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000aaf3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ab8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ac5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000af65`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000aaf3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ab8a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000ac5a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000af65`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000adb5`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b04c`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000adb5`
- `ntoskrnl!KeReleaseSemaphore` at `0x14000b04c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aabf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab07`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000abab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000abd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b089`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000aabf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab07`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000ab5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000abab`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000abd7`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b089`
- `ntoskrnl!KeReleaseMutex` at `0x14000afa2`
- `ntoskrnl!KeReleaseMutex` at `0x14000afa2`
- `ntoskrnl!KeReadStateSemaphore` at `0x14000ad8f`
- `ntoskrnl!KeReadStateSemaphore` at `0x14000b026`
- `ntoskrnl!KeReadStateSemaphore` at `0x14000ad8f`
- `ntoskrnl!KeReadStateSemaphore` at `0x14000b026`
- `ks!KsPinAcquireProcessingMutex` at `0x14000afb6`
- `ks!KsPinAcquireProcessingMutex` at `0x14000afb6`
- `ks!KsPinGetReferenceClockInterface` at `0x14000ace2`
- `ks!KsPinGetReferenceClockInterface` at `0x14000ace2`
- `ks!KsPinGetParentFilter` at `0x14000a980`
- `ks!KsPinGetParentFilter` at `0x14000a980`
- `ks!KsPinReleaseProcessingMutex` at `0x14000afd7`
- `ks!KsPinReleaseProcessingMutex` at `0x14000afd7`

## pseudocode

```c
__int64 __fastcall CaptureStateChange(PKSPIN Pin, unsigned int a2, __int64 a3)
{
  _QWORD *Context; // rsi
  unsigned int v4; // ebx
  __int64 v7; // r15
  PKSFILTER ParentFilter; // rax
  __int64 v9; // rdx
  __int64 *v10; // rbp
  __int64 v11; // rbp
  unsigned int SetInterfaceControl; // r14d
  __int64 result; // rax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  unsigned int started; // eax
  char *v19; // rbx
  KIRQL v20; // al
  KIRQL v21; // r13
  char *v22; // rbx
  KIRQL v23; // al
  KIRQL v24; // r15
  KIRQL v25; // bl
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  void *v28; // rcx
  int v29; // edx
  int v30; // r8d
  int v31; // r9d
  int v32; // ebx
  __int64 v33; // rcx
  signed __int32 v34; // eax
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // rbx
  __int64 v38; // r13
  char v39; // cl
  _DWORD *v40; // rax
  __int64 v41; // rcx
  KIRQL v42; // bl
  int v43; // eax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  SIZE_T NumberOfBytes; // [rsp+28h] [rbp-50h]
  union _LARGE_INTEGER Timeout; // [rsp+80h] [rbp+8h] BYREF

  Context = Pin->Context;
  v4 = a3;
  v7 = Context[12];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_ddq(WPP_GLOBAL_Control->AttachedDevice, 60, a3, a2, a3, Pin);
  ParentFilter = KsPinGetParentFilter(Pin);
  if ( ParentFilter )
  {
    v10 = (__int64 *)ParentFilter->Context;
    if ( v10 )
    {
      v11 = *v10;
      if ( v11 )
      {
        SetInterfaceControl = 0;
        if ( a2 == v4 )
          return SetInterfaceControl;
        LOBYTE(v9) = *((_BYTE *)Context + 177);
        result = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(*(_QWORD *)Context[49] + 120LL))(
                   Context[49],
                   v9,
                   a2,
                   v4);
        SetInterfaceControl = result;
        if ( (int)result < 0 )
          return result;
        if ( v4 )
        {
          v14 = v4 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              if ( v15 == 1 )
              {
                started = CaptureStartTransfer(Context);
                SetInterfaceControl = started;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  WPP_SF_qqD(
                    WPP_GLOBAL_Control->AttachedDevice,
                    73,
                    WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                    v11,
                    Context,
                    started);
                return SetInterfaceControl;
              }
              v16 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                v17 = 74;
LABEL_106:
                WPP_SF_qq(v16->AttachedDevice, v17, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v11, Context);
              }
              return SetInterfaceControl;
            }
            if ( a2 == 3 )
            {
              *(_QWORD *)(v7 + 160) = MEMORY[0xFFFFF78000000014];
              *(_DWORD *)(v7 + 12) = 1;
            }
            if ( *(_DWORD *)v7 )
            {
              *(_DWORD *)v7 = 0;
              v19 = (char *)Pin->Context;
              v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v19 + 15);
              v21 = v20;
              if ( *((_DWORD *)v19 + 9) )
              {
                KeResetEvent((PRKEVENT)(v19 + 128));
                KeReleaseSpinLock((PKSPIN_LOCK)v19 + 15, v21);
                Timeout.QuadPart = -20000000;
                KeWaitForSingleObject(v19 + 128, Executive, 0, 0, &Timeout);
              }
              else
              {
                KeReleaseSpinLock((PKSPIN_LOCK)v19 + 15, v20);
              }
              AbortUSBPipe(Context, 1);
              v22 = (char *)Pin->Context;
              v23 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v22 + 15);
              v24 = v23;
              if ( *((_DWORD *)v22 + 9) )
              {
                KeResetEvent((PRKEVENT)(v22 + 128));
                KeReleaseSpinLock((PKSPIN_LOCK)v22 + 15, v24);
                Timeout.QuadPart = -20000000;
                while ( KeWaitForSingleObject(v22 + 128, Executive, 0, 0, &Timeout) == 258 && *((_DWORD *)v22 + 9) )
                  ;
              }
              else
              {
                KeReleaseSpinLock((PKSPIN_LOCK)v22 + 15, v23);
              }
            }
            v25 = KeAcquireSpinLockRaiseToDpc(Context + 15);
            CaptureInitializePinContext(Context);
            KeReleaseSpinLock(Context + 15, v25);
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              return SetInterfaceControl;
            v27 = 72;
LABEL_61:
            WPP_SF_qqD(
              v26->AttachedDevice,
              v27,
              WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
              v11,
              Context,
              SetInterfaceControl);
            return SetInterfaceControl;
          }
          if ( a2 )
          {
LABEL_58:
            v26 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
              return SetInterfaceControl;
            v27 = 71;
            goto LABEL_61;
          }
          *(_DWORD *)(v7 + 12) = 0;
          *(_QWORD *)(v7 + 96) = 0;
          *(_BYTE *)(v7 + 136) = 1;
          *(_QWORD *)(v7 + 104) = 0;
          *(_QWORD *)(v7 + 112) = 0;
          v28 = (void *)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id);
          Timeout.QuadPart = 0;
          if ( KeWaitForSingleObject(v28, Executive, 0, 0, &Timeout) )
            return 3221225626LL;
          if ( *((_BYTE *)Context + 440) )
          {
            v32 = SetSecureCommonPinContext(Context);
            if ( v32 < 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                WPP_SF_qqD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  67,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  v11,
                  Context,
                  v32);
              return (unsigned int)v32;
            }
          }
          if ( !*(_QWORD *)(v7 + 368) && KsPinGetReferenceClockInterface(Pin, (PIKSREFERENCECLOCK *)(v7 + 368)) < 0 )
            *(_QWORD *)(v7 + 368) = 0;
          if ( *((_DWORD *)Context + 95) )
          {
            LOBYTE(v31) = *((_BYTE *)Context + 177);
            LOBYTE(v30) = 2;
            LODWORD(NumberOfBytes) = *((_DWORD *)Context + 45);
            LOBYTE(v29) = 1;
            SetInterfaceControl = GetSetInterfaceControl(Context[53], v29, v30, v31, Context + 23, NumberOfBytes);
            if ( (SetInterfaceControl & 0x80000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  68,
                  WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                  v11,
                  Context);
              goto LABEL_51;
            }
            SetInterfaceControl = SelectInterface(*(PVOID *)Context[2]);
          }
          else
          {
            SetInterfaceControl = SelectVideoInterfaceIsoch(Context);
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_qqD(
                WPP_GLOBAL_Control->AttachedDevice,
                69,
                WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                v11,
                Context,
                SetInterfaceControl);
          }
          if ( (SetInterfaceControl & 0x80000000) == 0 )
          {
            *((_BYTE *)Context + 384) = 1;
LABEL_55:
            v34 = _InterlockedIncrement((volatile signed __int32 *)(v11 + 848));
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
              return SetInterfaceControl;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              WPP_SF_qqD(
                WPP_GLOBAL_Control->AttachedDevice,
                70,
                WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
                v11,
                Context,
                v34);
            goto LABEL_58;
          }
LABEL_51:
          SelectZeroBandwidthInterface(*Context, Pin->Id);
          if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id)) )
            KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id), 0, 1, 0);
          v33 = *(_QWORD *)(v7 + 368);
          if ( v33 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
            *(_QWORD *)(v7 + 368) = 0;
          }
          goto LABEL_55;
        }
        v35 = *(_QWORD *)(v11 + 744);
        v36 = 136LL * Pin->Id;
        LOBYTE(Timeout.LowPart) = 0;
        v37 = *(_QWORD *)(v36 + v35 + 24);
        if ( v37 )
        {
          v38 = *(_QWORD *)(v37 + 16);
          v39 = *(_BYTE *)(v38 + 377);
          v40 = *(_DWORD **)(v38 + 96);
          if ( v39 == 3 )
          {
            if ( *v40 )
            {
              *v40 = 0;
              AbortUSBPipe(v38, 0);
              USBVideoPinWaitForStarvation(v37, 0);
              LOBYTE(Timeout.LowPart) = 1;
            }
          }
          else if ( v39 == 2 && *v40 )
          {
            KeWaitForSingleObject((PVOID)(v35 + v36 + 64), Executive, 0, 0, 0);
            *(_QWORD *)(136LL * Pin->Id + *(_QWORD *)(v11 + 744) + 32) = 0;
            KeReleaseMutex((PRKMUTEX)(*(_QWORD *)(v11 + 744) + 136LL * Pin->Id + 64), 0);
          }
        }
        else
        {
          v38 = 0;
        }
        KsPinAcquireProcessingMutex(Pin);
        SelectZeroBandwidthInterface(*Context, Pin->Id);
        *((_BYTE *)Context + 384) = 0;
        KsPinReleaseProcessingMutex(Pin);
        if ( LOBYTE(Timeout.LowPart) )
          CaptureStartTransfer(v38);
        v41 = *(_QWORD *)(v7 + 368);
        if ( v41 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
          *(_QWORD *)(v7 + 368) = 0;
        }
        if ( !KeReadStateSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id)) )
          KeReleaseSemaphore((PRKSEMAPHORE)(*(_QWORD *)(v11 + 752) + 32LL * Pin->Id), 0, 1, 0);
        if ( *(_DWORD *)v7 )
          AbortUSBPipe(Context, 1);
        v42 = KeAcquireSpinLockRaiseToDpc(Context + 15);
        CaptureInitializePinContext(Context);
        KeReleaseSpinLock(Context + 15, v42);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_qqD(
            WPP_GLOBAL_Control->AttachedDevice,
            62,
            WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
            v11,
            Context,
            SetInterfaceControl);
        v43 = _InterlockedDecrement((volatile signed __int32 *)(v11 + 848));
        if ( v43 >= 0 )
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            v45 = 64;
            goto LABEL_95;
          }
        }
        else
        {
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            v45 = 63;
LABEL_95:
            WPP_SF_qqD(v44->AttachedDevice, v45, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, v11, Context, v43);
          }
        }
        if ( !*((_BYTE *)Context + 440) )
          return SetInterfaceControl;
        if ( (int)ClearSecureCommonPinContext(Context) < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qq(
            WPP_GLOBAL_Control->AttachedDevice,
            65,
            WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids,
            v11,
            Context);
        }
        if ( !v38 )
          return SetInterfaceControl;
        if ( (int)ClearSecureCommonPinContext(v38) >= 0 )
          return SetInterfaceControl;
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          return SetInterfaceControl;
        v17 = 66;
        goto LABEL_106;
      }
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids);
  return 3221225485LL;
}

```

## disassembly

```asm
0x14000a928  push    rbx
0x14000a92a  push    rbp
0x14000a92b  push    rsi
0x14000a92c  push    rdi
0x14000a92d  push    r12
0x14000a92f  push    r13
0x14000a931  push    r14
0x14000a933  push    r15
0x14000a935  sub     rsp, 38h
0x14000a939  mov     rsi, [rcx+10h]
0x14000a93d  mov     ebx, r8d
0x14000a940  mov     r13d, edx
0x14000a943  mov     rdi, rcx
0x14000a946  mov     r15, [rsi+60h]
0x14000a94a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a951  lea     r12, WPP_GLOBAL_Control
0x14000a958  cmp     rcx, r12
0x14000a95b  jz      short loc_14000A97D
0x14000a95d  cmp     byte ptr [rcx+29h], 4
0x14000a961  jb      short loc_14000A97D
0x14000a963  mov     rcx, [rcx+18h]
0x14000a967  mov     edx, 3Ch ; '<'
0x14000a96c  mov     [rsp+78h+NumberOfBytes], rdi
0x14000a971  mov     r9d, r13d
0x14000a974  mov     dword ptr [rsp+78h+Timeout], ebx
0x14000a978  call    WPP_SF_ddq
0x14000a97d  mov     rcx, rdi; Pin
0x14000a980  call    cs:__imp_KsPinGetParentFilter
0x14000a987  nop     dword ptr [rax+rax+00h]
0x14000a98c  test    rax, rax
0x14000a98f  jz      loc_14000B1B5
0x14000a995  mov     rbp, [rax+10h]
0x14000a999  test    rbp, rbp
0x14000a99c  jz      loc_14000B1B5
0x14000a9a2  mov     rbp, [rbp+0]
0x14000a9a6  test    rbp, rbp
0x14000a9a9  jz      loc_14000B1B5
0x14000a9af  xor     r14d, r14d
0x14000a9b2  cmp     r13d, ebx
0x14000a9b5  jz      loc_14000B1B0
0x14000a9bb  mov     rcx, [rsi+188h]
0x14000a9c2  mov     r9d, ebx
0x14000a9c5  mov     dl, [rsi+0B1h]
0x14000a9cb  mov     r8d, r13d
0x14000a9ce  mov     rax, [rcx]
0x14000a9d1  mov     rax, [rax+78h]
0x14000a9d5  call    _guard_dispatch_icall
0x14000a9da  xor     r9d, r9d; Alertable
0x14000a9dd  mov     r14d, eax
0x14000a9e0  test    eax, eax
0x14000a9e2  js      loc_14000B1E1
0x14000a9e8  test    ebx, ebx
0x14000a9ea  jz      loc_14000AEDF
0x14000a9f0  sub     ebx, 1
0x14000a9f3  jz      loc_14000AC0E
0x14000a9f9  sub     ebx, 1
0x14000a9fc  jz      short loc_14000AA59
0x14000a9fe  cmp     ebx, 1
0x14000aa01  jz      short loc_14000AA26
0x14000aa03  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa0a  cmp     rcx, r12
0x14000aa0d  jz      loc_14000B1B0
0x14000aa13  cmp     byte ptr [rcx+29h], 4
0x14000aa17  jb      loc_14000B1B0
0x14000aa1d  lea     edx, [r9+4Ah]
0x14000aa21  jmp     loc_14000B198
0x14000aa26  mov     rcx, rsi
0x14000aa29  call    CaptureStartTransfer
0x14000aa2e  mov     r14d, eax
0x14000aa31  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa38  cmp     rcx, r12
0x14000aa3b  jz      loc_14000B1B0
0x14000aa41  cmp     byte ptr [rcx+29h], 4
0x14000aa45  jb      loc_14000B1B0
0x14000aa4b  mov     edx, 49h ; 'I'
0x14000aa50  mov     dword ptr [rsp+78h+NumberOfBytes], eax
0x14000aa54  jmp     loc_14000AE50
0x14000aa59  mov     r12d, 1
0x14000aa5f  cmp     r13d, 3
0x14000aa63  jnz     short loc_14000AA7A
0x14000aa65  mov     rax, ds:0FFFFF78000000014h
0x14000aa6f  mov     [r15+0A0h], rax
0x14000aa76  mov     [r15+0Ch], r12d
0x14000aa7a  cmp     [r15], r9d
0x14000aa7d  jz      loc_14000ABB7
0x14000aa83  mov     [r15], r9d
0x14000aa86  mov     rbx, [rdi+10h]
0x14000aa8a  lea     r15, [rbx+78h]
0x14000aa8e  mov     rcx, r15; SpinLock
0x14000aa91  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000aa98  nop     dword ptr [rax+rax+00h]
0x14000aa9d  cmp     dword ptr [rbx+24h], 0
0x14000aaa1  mov     r13b, al
0x14000aaa4  jz      short loc_14000AB01
0x14000aaa6  lea     rcx, [rbx+80h]; Event
0x14000aaad  call    cs:__imp_KeResetEvent
0x14000aab4  nop     dword ptr [rax+rax+00h]
0x14000aab9  mov     dl, r13b; NewIrql
0x14000aabc  mov     rcx, r15; SpinLock
0x14000aabf  call    cs:__imp_KeReleaseSpinLock
0x14000aac6  nop     dword ptr [rax+rax+00h]
0x14000aacb  lea     rax, [rsp+78h+arg_0]
0x14000aad3  mov     qword ptr [rsp+78h+arg_0], 0FFFFFFFFFECED300h
0x14000aadf  xor     r9d, r9d; Alertable
0x14000aae2  mov     [rsp+78h+Timeout], rax; Timeout
0x14000aae7  xor     r8d, r8d; WaitMode
0x14000aaea  lea     rcx, [rbx+80h]; Object
0x14000aaf1  xor     edx, edx; WaitReason
0x14000aaf3  call    cs:__imp_KeWaitForSingleObject
0x14000aafa  nop     dword ptr [rax+rax+00h]
0x14000aaff  jmp     short loc_14000AB13
0x14000ab01  mov     dl, r13b; NewIrql
0x14000ab04  mov     rcx, r15; SpinLock
0x14000ab07  call    cs:__imp_KeReleaseSpinLock
0x14000ab0e  nop     dword ptr [rax+rax+00h]
0x14000ab13  mov     edx, r12d
0x14000ab16  mov     rcx, rsi
0x14000ab19  call    AbortUSBPipe
0x14000ab1e  mov     rbx, [rdi+10h]
0x14000ab22  lea     rdi, [rbx+78h]
0x14000ab26  mov     rcx, rdi; SpinLock
0x14000ab29  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ab30  nop     dword ptr [rax+rax+00h]
0x14000ab35  cmp     dword ptr [rbx+24h], 0
0x14000ab39  mov     r15b, al
0x14000ab3c  jz      short loc_14000ABA5
0x14000ab3e  lea     r12, [rbx+80h]
0x14000ab45  mov     rcx, r12; Event
0x14000ab48  call    cs:__imp_KeResetEvent
0x14000ab4f  nop     dword ptr [rax+rax+00h]
0x14000ab54  mov     dl, r15b; NewIrql
0x14000ab57  mov     rcx, rdi; SpinLock
0x14000ab5a  call    cs:__imp_KeReleaseSpinLock
0x14000ab61  nop     dword ptr [rax+rax+00h]
0x14000ab66  mov     qword ptr [rsp+78h+arg_0], 0FFFFFFFFFECED300h
0x14000ab72  lea     rax, [rsp+78h+arg_0]
0x14000ab7a  xor     r9d, r9d; Alertable
0x14000ab7d  xor     r8d, r8d; WaitMode
0x14000ab80  mov     [rsp+78h+Timeout], rax; Timeout
0x14000ab85  xor     edx, edx; WaitReason
0x14000ab87  mov     rcx, r12; Object
0x14000ab8a  call    cs:__imp_KeWaitForSingleObject
0x14000ab91  nop     dword ptr [rax+rax+00h]
0x14000ab96  cmp     eax, 102h
0x14000ab9b  jnz     short loc_14000ABB7
0x14000ab9d  cmp     dword ptr [rbx+24h], 0
0x14000aba1  jnz     short loc_14000AB72
0x14000aba3  jmp     short loc_14000ABB7
0x14000aba5  mov     dl, r15b; NewIrql
0x14000aba8  mov     rcx, rdi; SpinLock
0x14000abab  call    cs:__imp_KeReleaseSpinLock
0x14000abb2  nop     dword ptr [rax+rax+00h]
0x14000abb7  lea     rcx, [rsi+78h]; SpinLock
0x14000abbb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000abc2  nop     dword ptr [rax+rax+00h]
0x14000abc7  mov     rcx, rsi
0x14000abca  mov     bl, al
0x14000abcc  call    CaptureInitializePinContext
0x14000abd1  mov     dl, bl; NewIrql
0x14000abd3  lea     rcx, [rsi+78h]; SpinLock
0x14000abd7  call    cs:__imp_KeReleaseSpinLock
0x14000abde  nop     dword ptr [rax+rax+00h]
0x14000abe3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000abea  lea     rax, WPP_GLOBAL_Control
0x14000abf1  cmp     rcx, rax
0x14000abf4  jz      loc_14000B1B0
0x14000abfa  cmp     byte ptr [rcx+29h], 4
0x14000abfe  jb      loc_14000B1B0
0x14000ac04  mov     edx, 48h ; 'H'
0x14000ac09  jmp     loc_14000AE4B
0x14000ac0e  test    r13d, r13d
0x14000ac11  jnz     loc_14000AE2C
0x14000ac17  mov     [r15+0Ch], r9d
0x14000ac1b  lea     rax, [rsp+78h+arg_0]
0x14000ac23  mov     [r15+60h], r9
0x14000ac27  lea     r12d, [r13+1]
0x14000ac2b  mov     [r15+88h], r12b
0x14000ac32  xor     r8d, r8d; WaitMode
0x14000ac35  mov     [r15+68h], r9
0x14000ac39  xor     edx, edx; WaitReason
0x14000ac3b  mov     [r15+70h], r9
0x14000ac3f  mov     ecx, [rdi+18h]
0x14000ac42  shl     rcx, 5
0x14000ac46  add     rcx, [rbp+2F0h]; Object
0x14000ac4d  mov     qword ptr [rsp+78h+arg_0], r9
0x14000ac55  mov     [rsp+78h+Timeout], rax; Timeout
0x14000ac5a  call    cs:__imp_KeWaitForSingleObject
0x14000ac61  nop     dword ptr [rax+rax+00h]
0x14000ac66  xor     r13d, r13d
0x14000ac69  test    eax, eax
0x14000ac6b  jz      short loc_14000AC77
0x14000ac6d  mov     eax, 0C000009Ah
0x14000ac72  jmp     loc_14000B1E1
0x14000ac77  cmp     [rsi+1B8h], r13b
0x14000ac7e  jz      short loc_14000ACCF
0x14000ac80  mov     rcx, rsi
0x14000ac83  call    SetSecureCommonPinContext
0x14000ac88  mov     ebx, eax
0x14000ac8a  test    eax, eax
0x14000ac8c  jns     short loc_14000ACCF
0x14000ac8e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac95  lea     rax, WPP_GLOBAL_Control
0x14000ac9c  cmp     rcx, rax
0x14000ac9f  jz      short loc_14000ACC8
0x14000aca1  cmp     byte ptr [rcx+29h], 4
0x14000aca5  jb      short loc_14000ACC8
0x14000aca7  mov     rcx, [rcx+18h]
0x14000acab  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000acb2  mov     edx, 43h ; 'C'
0x14000acb7  mov     dword ptr [rsp+78h+NumberOfBytes], ebx
0x14000acbb  mov     r9, rbp
0x14000acbe  mov     [rsp+78h+Timeout], rsi
0x14000acc3  call    WPP_SF_qqD
0x14000acc8  mov     eax, ebx
0x14000acca  jmp     loc_14000B1E1
0x14000accf  cmp     [r15+170h], r13
0x14000acd6  jnz     short loc_14000ACF9
0x14000acd8  lea     rdx, [r15+170h]; Interface
0x14000acdf  mov     rcx, rdi; Pin
0x14000ace2  call    cs:__imp_KsPinGetReferenceClockInterface
0x14000ace9  nop     dword ptr [rax+rax+00h]
0x14000acee  test    eax, eax
0x14000acf0  jns     short loc_14000ACF9
0x14000acf2  mov     [r15+170h], r13
0x14000acf9  cmp     [rsi+17Ch], r13d
0x14000ad00  jz      loc_14000AE84
0x14000ad06  mov     eax, [rsi+0B4h]
0x14000ad0c  lea     rcx, [rsi+0B8h]
0x14000ad13  mov     r9b, [rsi+0B1h]; int
0x14000ad1a  mov     r8b, 2; int
0x14000ad1d  mov     dword ptr [rsp+78h+NumberOfBytes], eax; NumberOfBytes
0x14000ad21  mov     dl, r12b; int
0x14000ad24  mov     [rsp+78h+Timeout], rcx; Src
0x14000ad29  mov     rcx, [rsi+1A8h]; int
0x14000ad30  call    GetSetInterfaceControl
0x14000ad35  mov     r14d, eax
0x14000ad38  test    eax, eax
0x14000ad3a  jns     loc_14000AE6D
0x14000ad40  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad47  lea     rax, WPP_GLOBAL_Control
0x14000ad4e  cmp     rcx, rax
0x14000ad51  jz      short loc_14000AD76
0x14000ad53  cmp     byte ptr [rcx+29h], 3
0x14000ad57  jb      short loc_14000AD76
0x14000ad59  mov     rcx, [rcx+18h]
0x14000ad5d  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000ad64  mov     edx, 44h ; 'D'
0x14000ad69  mov     [rsp+78h+Timeout], rsi
0x14000ad6e  mov     r9, rbp
0x14000ad71  call    WPP_SF_qq
0x14000ad76  mov     edx, [rdi+18h]
0x14000ad79  mov     rcx, [rsi]
0x14000ad7c  call    SelectZeroBandwidthInterface
0x14000ad81  mov     ecx, [rdi+18h]
0x14000ad84  shl     rcx, 5
0x14000ad88  add     rcx, [rbp+2F0h]; Semaphore
0x14000ad8f  call    cs:__imp_KeReadStateSemaphore
0x14000ad96  nop     dword ptr [rax+rax+00h]
0x14000ad9b  test    eax, eax
0x14000ad9d  jnz     short loc_14000ADC1
0x14000ad9f  mov     ecx, [rdi+18h]
0x14000ada2  xor     r9d, r9d; Wait
0x14000ada5  shl     rcx, 5
0x14000ada9  mov     r8d, r12d; Adjustment
0x14000adac  add     rcx, [rbp+2F0h]; Semaphore
0x14000adb3  xor     edx, edx; Increment
0x14000adb5  call    cs:__imp_KeReleaseSemaphore
0x14000adbc  nop     dword ptr [rax+rax+00h]
0x14000adc1  mov     rcx, [r15+170h]
0x14000adc8  test    rcx, rcx
0x14000adcb  jz      short loc_14000ADE0
0x14000adcd  mov     rax, [rcx]
0x14000add0  mov     rax, [rax+10h]
0x14000add4  call    _guard_dispatch_icall
0x14000add9  mov     [r15+170h], r13
0x14000ade0  mov     eax, r12d
0x14000ade3  lock xadd [rbp+350h], eax
0x14000adeb  add     eax, r12d
0x14000adee  mov     rcx, cs:WPP_GLOBAL_Control
0x14000adf5  lea     r12, WPP_GLOBAL_Control
0x14000adfc  cmp     rcx, r12
0x14000adff  jz      loc_14000B1B0
0x14000ae05  cmp     byte ptr [rcx+29h], 3
0x14000ae09  jb      short loc_14000AE2C
0x14000ae0b  mov     rcx, [rcx+18h]
0x14000ae0f  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x14000ae16  mov     dword ptr [rsp+78h+NumberOfBytes], eax
0x14000ae1a  mov     edx, 46h ; 'F'
0x14000ae1f  mov     r9, rbp
0x14000ae22  mov     [rsp+78h+Timeout], rsi
0x14000ae27  call    WPP_SF_qqD
0x14000ae2c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ae33  cmp     rcx, r12
0x14000ae36  jz      loc_14000B1B0
0x14000ae3c  cmp     byte ptr [rcx+29h], 4
0x14000ae40  jb      loc_14000B1B0
0x14000ae46  mov     edx, 47h ; 'G'
0x14000ae4b  mov     dword ptr [rsp+78h+NumberOfBytes], r14d
0x14000ae50  mov     rcx, [rcx+18h]
0x14000ae54  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
  ... truncated ...
```
