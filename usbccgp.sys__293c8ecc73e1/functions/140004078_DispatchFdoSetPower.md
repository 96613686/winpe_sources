# DispatchFdoSetPower

- ea: `0x140004078`
- end: `0x1400044c5`
- name: `DispatchFdoSetPower`
- size: `1101`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140003e88`

## callees

- `0x140004078`
- `0x140005940`
- `0x140006af8`
- `0x140006d40`
- `0x140008eac`
- `0x14000a6cc`
- `0x14000b8cc`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400041ed`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004219`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004219`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000412c`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x14000412c`
- `ntoskrnl!PoCallDriver` at `0x140004147`
- `ntoskrnl!PoCallDriver` at `0x140004299`
- `ntoskrnl!PoCallDriver` at `0x140004147`
- `ntoskrnl!PoCallDriver` at `0x140004299`
- `ntoskrnl!PoSetPowerState` at `0x1400041a0`
- `ntoskrnl!PoSetPowerState` at `0x1400042ca`
- `ntoskrnl!PoSetPowerState` at `0x140004458`
- `ntoskrnl!PoSetPowerState` at `0x1400041a0`
- `ntoskrnl!PoSetPowerState` at `0x1400042ca`
- `ntoskrnl!PoSetPowerState` at `0x140004458`

## pseudocode

```c
__int64 __fastcall DispatchFdoSetPower(char *Context, PIRP Irp, int a3)
{
  unsigned int v5; // edx
  _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  unsigned int Options; // ecx
  unsigned int LowPart; // edx
  _IO_STACK_LOCATION *v9; // rax
  __int64 v10; // rbp
  NTSTATUS v11; // eax
  int v12; // edx
  _QWORD *v14; // r13
  KIRQL v15; // al
  unsigned int v16; // ecx
  char v17; // di
  __int64 v18; // rdx
  _IO_STACK_LOCATION *v19; // rax
  _IO_STACK_LOCATION *v20; // rax

  v5 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options )
  {
    if ( Options == 1 )
    {
      LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
      if ( LowPart == 1 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(LowPart) = 2;
          WPP_RECORDER_SF_qq(
            *((_QWORD *)Context + 171),
            LowPart,
            3,
            49,
            (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
            *((_QWORD *)Context + 4),
            (char)Irp);
        }
      }
      else
      {
        switch ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart )
        {
          case 2u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(LowPart) = 2;
              WPP_RECORDER_SF_qq(
                *((_QWORD *)Context + 171),
                LowPart,
                3,
                50,
                (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
                *((_QWORD *)Context + 4),
                (char)Irp);
            }
            PoSetPowerState(
              *((PDEVICE_OBJECT *)Context + 4),
              CurrentStackLocation->Parameters.Power.Type,
              CurrentStackLocation->Parameters.Power.State);
            *((_DWORD *)Context + 1) = 2;
            break;
          case 3u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(LowPart) = 2;
              WPP_RECORDER_SF_qq(
                *((_QWORD *)Context + 171),
                LowPart,
                3,
                51,
                (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
                *((_QWORD *)Context + 4),
                (char)Irp);
            }
            PoSetPowerState(
              *((PDEVICE_OBJECT *)Context + 4),
              CurrentStackLocation->Parameters.Power.Type,
              CurrentStackLocation->Parameters.Power.State);
            *((_DWORD *)Context + 1) = 3;
            break;
          case 4u:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(LowPart) = 2;
              WPP_RECORDER_SF_qq(
                *((_QWORD *)Context + 171),
                LowPart,
                3,
                52,
                (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
                *((_QWORD *)Context + 4),
                (char)Irp);
            }
            PoSetPowerState(
              *((PDEVICE_OBJECT *)Context + 4),
              CurrentStackLocation->Parameters.Power.Type,
              CurrentStackLocation->Parameters.Power.State);
            *((_DWORD *)Context + 1) = 4;
            break;
          default:
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_qqL(*((_QWORD *)Context + 171), LowPart, a3, 53);
            *((_DWORD *)Context + 1) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
            break;
        }
        *((_DWORD *)Context + 144) = 1;
      }
      v9 = Irp->Tail.Overlay.CurrentStackLocation;
      *(_OWORD *)&v9[-1].MajorFunction = *(_OWORD *)&v9->MajorFunction;
      *(_OWORD *)&v9[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v9->Parameters.NotifyDirectoryEx.CompletionFilter;
      *(_OWORD *)(&v9[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v9->Parameters.SetQuota + 6);
      v9[-1].FileObject = v9->FileObject;
      v9[-1].Control = 0;
      v10 = *((_QWORD *)Context + 171);
      v11 = IoSetCompletionRoutineEx(
              *((PDEVICE_OBJECT *)Context + 4),
              Irp,
              (PIO_COMPLETION_ROUTINE)CompletionFdoDeviceSetPower,
              Context,
              1u,
              1u,
              1u);
      if ( v11 < 0 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v12) = 3;
          WPP_RECORDER_SF_d(v10, v12, 1, 60, (__int64)WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids, v11);
        }
        v20 = Irp->Tail.Overlay.CurrentStackLocation;
        v20[-1].CompletionRoutine = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *, void *))CompletionFdoDeviceSetPower;
        v20[-1].Context = Context;
        v20[-1].Control = -32;
      }
      return (unsigned int)PoCallDriver(*((PDEVICE_OBJECT *)Context + 5), Irp);
    }
  }
  else
  {
    v14 = Context + 1368;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qqL(*v14, 0, a3, 48);
    if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart != 1 )
    {
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 43);
      v16 = *((_DWORD *)Context + 307);
      if ( (v16 & 4) != 0 )
      {
        v16 = v16 & 0xFFFFFFFA | 1;
        *((_DWORD *)Context + 307) = v16;
      }
      if ( (v16 & 1) != 0 )
      {
        v17 = 0;
      }
      else
      {
        v17 = 1;
        *((_DWORD *)Context + 307) = v16 | 1;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)Context + 43, v15);
      if ( v17 )
        DisableIdleTimer(Context, v18, 1347637332);
      LOBYTE(v18) = 1;
      CancelFdoIdleIrp(Context, v18);
    }
    *((_DWORD *)Context + 2) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    v19 = Irp->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v19[-1].MajorFunction = *(_OWORD *)&v19->MajorFunction;
    *(_OWORD *)&v19[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v19->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v19[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v19->Parameters.SetQuota + 6);
    v19[-1].FileObject = v19->FileObject;
    v19[-1].Control = 0;
    SetCompletionRoutine(
      *v14,
      *((struct _DEVICE_OBJECT **)Context + 4),
      Irp,
      (IO_COMPLETION_ROUTINE *)CompletionFdoSystemSetPower,
      Context);
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
    PoCallDriver(*((PDEVICE_OBJECT *)Context + 5), Irp);
    return 259;
  }
  return v5;
}

```

## disassembly

```asm
0x140004078  push    rbx
0x14000407a  push    rbp
0x14000407b  push    rsi
0x14000407c  push    rdi
0x14000407d  push    r12
0x14000407f  push    r13
0x140004081  push    r14
0x140004083  push    r15
0x140004085  sub     rsp, 48h
0x140004089  mov     r14, rdx
0x14000408c  mov     rbx, rcx
0x14000408f  xor     edx, edx
0x140004091  mov     rbp, [r14+0B8h]
0x140004098  mov     ecx, [rbp+10h]
0x14000409b  test    ecx, ecx
0x14000409d  jz      loc_1400041BE
0x1400040a3  cmp     ecx, 1
0x1400040a6  jnz     loc_140004155
0x1400040ac  mov     edx, [rbp+18h]
0x1400040af  mov     esi, 1
0x1400040b4  mov     ecx, edx
0x1400040b6  lea     r15d, [rsi+2]
0x1400040ba  sub     ecx, esi
0x1400040bc  jnz     loc_140004169
0x1400040c2  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400040c9  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400040d0  jnz     loc_14000435B
0x1400040d6  mov     rax, [r14+0B8h]
0x1400040dd  lea     r12, CompletionFdoDeviceSetPower
0x1400040e4  mov     [rsp+88h+InvokeOnCancel], sil; InvokeOnCancel
0x1400040e9  mov     r9, rbx; Context
0x1400040ec  mov     [rsp+88h+InvokeOnError], sil; InvokeOnError
0x1400040f1  mov     r8, r12; CompletionRoutine
0x1400040f4  mov     rdx, r14; Irp
0x1400040f7  mov     [rsp+88h+InvokeOnSuccess], sil; InvokeOnSuccess
0x1400040fc  movups  xmm0, xmmword ptr [rax]
0x1400040ff  movups  xmmword ptr [rax-48h], xmm0
0x140004103  movups  xmm1, xmmword ptr [rax+10h]
0x140004107  movups  xmmword ptr [rax-38h], xmm1
0x14000410b  movups  xmm0, xmmword ptr [rax+20h]
0x14000410f  movups  xmmword ptr [rax-28h], xmm0
0x140004113  movsd   xmm1, qword ptr [rax+30h]
0x140004118  movsd   qword ptr [rax-18h], xmm1
0x14000411d  mov     byte ptr [rax-45h], 0
0x140004121  mov     rcx, [rbx+20h]; DeviceObject
0x140004125  mov     rbp, [rbx+558h]
0x14000412c  call    cs:__imp_IoSetCompletionRoutineEx
0x140004133  nop     dword ptr [rax+rax+00h]
0x140004138  test    eax, eax
0x14000413a  js      loc_140004470
0x140004140  mov     rcx, [rbx+28h]; DeviceObject
0x140004144  mov     rdx, r14; Irp
0x140004147  call    cs:__imp_PoCallDriver
0x14000414e  nop     dword ptr [rax+rax+00h]
0x140004153  mov     edx, eax
0x140004155  mov     eax, edx
0x140004157  add     rsp, 48h
0x14000415b  pop     r15
0x14000415d  pop     r14
0x14000415f  pop     r13
0x140004161  pop     r12
0x140004163  pop     rdi
0x140004164  pop     rsi
0x140004165  pop     rbp
0x140004166  pop     rbx
0x140004167  retn
0x140004169  sub     ecx, esi
0x14000416b  jz      loc_14000440C
0x140004171  sub     ecx, esi
0x140004173  jz      loc_1400042AF
0x140004179  cmp     ecx, esi
0x14000417b  jnz     loc_1400043CD
0x140004181  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004188  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000418f  jnz     loc_1400042DF
0x140004195  mov     r8d, [rbp+18h]; State
0x140004199  mov     edx, [rbp+10h]; Type
0x14000419c  mov     rcx, [rbx+20h]; DeviceObject
0x1400041a0  call    cs:__imp_PoSetPowerState
0x1400041a7  nop     dword ptr [rax+rax+00h]
0x1400041ac  mov     dword ptr [rbx+4], 4
0x1400041b3  mov     [rbx+240h], esi
0x1400041b9  jmp     loc_1400040D6
0x1400041be  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400041c5  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400041cc  lea     r13, [rbx+558h]
0x1400041d3  jnz     loc_140004391
0x1400041d9  mov     esi, 1
0x1400041de  cmp     [rbp+18h], esi
0x1400041e1  jz      short loc_140004239
0x1400041e3  lea     r15, [rbx+158h]
0x1400041ea  mov     rcx, r15; SpinLock
0x1400041ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400041f4  nop     dword ptr [rax+rax+00h]
0x1400041f9  mov     ecx, [rbx+4CCh]
0x1400041ff  test    cl, 4
0x140004202  jnz     loc_1400044B5
0x140004208  test    sil, cl
0x14000420b  jz      loc_140004315
0x140004211  xor     dil, dil
0x140004214  mov     dl, al; NewIrql
0x140004216  mov     rcx, r15; SpinLock
0x140004219  call    cs:__imp_KeReleaseSpinLock
0x140004220  nop     dword ptr [rax+rax+00h]
0x140004225  test    dil, dil
0x140004228  jnz     loc_1400043BA
0x14000422e  mov     dl, sil
0x140004231  mov     rcx, rbx
0x140004234  call    CancelFdoIdleIrp
0x140004239  mov     eax, [rbp+18h]
0x14000423c  lea     r9, CompletionFdoSystemSetPower
0x140004243  mov     [rbx+8], eax
0x140004246  mov     r8, r14
0x140004249  mov     rax, [r14+0B8h]
0x140004250  mov     qword ptr [rsp+88h+InvokeOnSuccess], rbx
0x140004255  movups  xmm0, xmmword ptr [rax]
0x140004258  movups  xmmword ptr [rax-48h], xmm0
0x14000425c  movups  xmm1, xmmword ptr [rax+10h]
0x140004260  movups  xmmword ptr [rax-38h], xmm1
0x140004264  movups  xmm0, xmmword ptr [rax+20h]
0x140004268  movups  xmmword ptr [rax-28h], xmm0
0x14000426c  movsd   xmm1, qword ptr [rax+30h]
0x140004271  movsd   qword ptr [rax-18h], xmm1
0x140004276  mov     byte ptr [rax-45h], 0
0x14000427a  mov     rdx, [rbx+20h]
0x14000427e  mov     rcx, [r13+0]
0x140004282  call    SetCompletionRoutine
0x140004287  mov     rax, [r14+0B8h]
0x14000428e  mov     rdx, r14; Irp
0x140004291  or      [rax+3], sil
0x140004295  mov     rcx, [rbx+28h]; DeviceObject
0x140004299  call    cs:__imp_PoCallDriver
0x1400042a0  nop     dword ptr [rax+rax+00h]
0x1400042a5  mov     edx, 103h
0x1400042aa  jmp     loc_140004155
0x1400042af  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400042b6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400042bd  jnz     short loc_140004325
0x1400042bf  mov     r8d, [rbp+18h]; State
0x1400042c3  mov     edx, [rbp+10h]; Type
0x1400042c6  mov     rcx, [rbx+20h]; DeviceObject
0x1400042ca  call    cs:__imp_PoSetPowerState
0x1400042d1  nop     dword ptr [rax+rax+00h]
0x1400042d6  mov     [rbx+4], r15d
0x1400042da  jmp     loc_1400041B3
0x1400042df  mov     rax, [rbx+20h]
0x1400042e3  mov     r9d, 34h ; '4'
0x1400042e9  mov     rcx, [rbx+558h]
0x1400042f0  mov     r8d, r15d
0x1400042f3  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x1400042f8  mov     dl, 2
0x1400042fa  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x1400042ff  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140004306  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x14000430b  call    WPP_RECORDER_SF_qq
0x140004310  jmp     loc_140004195
0x140004315  or      ecx, esi
0x140004317  mov     dil, sil
0x14000431a  mov     [rbx+4CCh], ecx
0x140004320  jmp     loc_140004214
0x140004325  mov     rax, [rbx+20h]
0x140004329  mov     r9d, 33h ; '3'
0x14000432f  mov     rcx, [rbx+558h]
0x140004336  mov     r8d, r15d
0x140004339  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x14000433e  mov     dl, 2
0x140004340  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x140004345  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x14000434c  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x140004351  call    WPP_RECORDER_SF_qq
0x140004356  jmp     loc_1400042BF
0x14000435b  mov     rax, [rbx+20h]
0x14000435f  mov     r9d, 31h ; '1'
0x140004365  mov     rcx, [rbx+558h]
0x14000436c  mov     r8d, r15d
0x14000436f  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x140004374  mov     dl, 2
0x140004376  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x14000437b  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140004382  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x140004387  call    WPP_RECORDER_SF_qq
0x14000438c  jmp     loc_1400040D6
0x140004391  mov     eax, [rbp+18h]
0x140004394  mov     r9d, 30h ; '0'
0x14000439a  mov     rcx, [r13+0]
0x14000439e  mov     [rsp+88h+var_50], eax
0x1400043a2  mov     rax, [rbx+20h]
0x1400043a6  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x1400043ab  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x1400043b0  call    WPP_RECORDER_SF_qqL
0x1400043b5  jmp     loc_1400041D9
0x1400043ba  mov     r8d, 50535054h
0x1400043c0  mov     rcx, rbx
0x1400043c3  call    DisableIdleTimer
0x1400043c8  jmp     loc_14000422E
0x1400043cd  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400043d4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400043db  jz      short loc_140004401
0x1400043dd  mov     rax, [rbx+20h]
0x1400043e1  mov     r9d, 35h ; '5'
0x1400043e7  mov     rcx, [rbx+558h]
0x1400043ee  mov     [rsp+88h+var_50], edx
0x1400043f2  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x1400043f7  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x1400043fc  call    WPP_RECORDER_SF_qqL
0x140004401  mov     eax, [rbp+18h]
0x140004404  mov     [rbx+4], eax
0x140004407  jmp     loc_1400041B3
0x14000440c  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004413  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000441a  jz      short loc_14000444D
0x14000441c  mov     rax, [rbx+20h]
0x140004420  mov     r9d, 32h ; '2'
0x140004426  mov     rcx, [rbx+558h]
0x14000442d  mov     r8d, r15d
0x140004430  mov     qword ptr [rsp+88h+InvokeOnCancel], r14
0x140004435  mov     dl, 2
0x140004437  mov     qword ptr [rsp+88h+InvokeOnError], rax
0x14000443c  lea     rax, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140004443  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x140004448  call    WPP_RECORDER_SF_qq
0x14000444d  mov     r8d, [rbp+18h]; State
0x140004451  mov     edx, [rbp+10h]; Type
0x140004454  mov     rcx, [rbx+20h]; DeviceObject
0x140004458  call    cs:__imp_PoSetPowerState
0x14000445f  nop     dword ptr [rax+rax+00h]
0x140004464  mov     dword ptr [rbx+4], 2
0x14000446b  jmp     loc_1400041B3
0x140004470  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140004477  jz      short loc_14000449D
0x140004479  mov     dword ptr [rsp+88h+InvokeOnError], eax
0x14000447d  mov     r9d, 3Ch ; '<'
0x140004483  lea     rax, WPP_fab633abdc7a3ad3d24321d85aef32e1_Traceguids
0x14000448a  mov     r8d, esi
0x14000448d  mov     dl, r15b
0x140004490  mov     qword ptr [rsp+88h+InvokeOnSuccess], rax
0x140004495  mov     rcx, rbp
0x140004498  call    WPP_RECORDER_SF_d
0x14000449d  mov     rax, [r14+0B8h]
0x1400044a4  mov     [rax-10h], r12
0x1400044a8  mov     [rax-8], rbx
0x1400044ac  mov     byte ptr [rax-45h], 0E0h
0x1400044b0  jmp     loc_140004140
0x1400044b5  and     ecx, 0FFFFFFFBh
0x1400044b8  or      ecx, esi
0x1400044ba  mov     [rbx+4CCh], ecx
0x1400044c0  jmp     loc_140004208
```
