# DispatchPdoSetPower

- ea: `0x140005fc4`
- end: `0x140006427`
- name: `DispatchPdoSetPower`
- size: `1123`
- prototype: `__int64 __fastcall(PVOID PeekContext)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140003d08`

## callees

- `0x1400059e4`
- `0x140005fc4`
- `0x140006430`
- `0x140006630`
- `0x140006f58`
- `0x140007b3c`
- `0x1400088b4`
- `0x140008eac`
- `0x140009804`
- `0x1400099a8`
- `0x140009f10`
- `0x14000b4bc`
- `0x14000b8cc`
- `0x14000d81c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062ba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400062ba`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062d2`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400062d2`
- `ntoskrnl!PoSetPowerState` at `0x14000608e`
- `ntoskrnl!PoSetPowerState` at `0x140006143`
- `ntoskrnl!PoSetPowerState` at `0x14000608e`
- `ntoskrnl!PoSetPowerState` at `0x140006143`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400063b7`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x1400063b7`

## pseudocode

```c
__int64 __fastcall DispatchPdoSetPower(char *PeekContext, IRP *a2, int a3)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v5; // r14
  unsigned int v6; // ebx
  unsigned int Options; // ecx
  unsigned int LowPart; // edx
  int v10; // eax
  int v11; // edx
  struct _DEVICE_OBJECT *v12; // rcx
  int v14; // eax
  char v15; // r13
  char v16; // al
  KIRQL v17; // al
  char *v18; // rdi
  unsigned int v19; // r9d
  int v20; // edx
  IRP *v21; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v5 = *((_QWORD *)PeekContext + 29);
  v6 = 0;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options )
  {
    if ( Options != 1 )
      return (unsigned int)a2->IoStatus.Status;
    LowPart = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
    if ( LowPart == 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(LowPart) = 4;
        WPP_RECORDER_SF_qq(
          *(_QWORD *)(v5 + 1368),
          LowPart,
          3,
          64,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *((_QWORD *)PeekContext + 28),
          (char)a2);
      }
      SetPdoIdle(v5, (__int64)PeekContext, 2, 0, 1);
      if ( *(_BYTE *)(v5 + 1362) )
      {
        v21 = IoCsqRemoveNextIrp((PIO_CSQ)(PeekContext + 32), PeekContext);
        if ( v21 )
          CancelRemoteWakeNotificationIrp(PeekContext, v21);
      }
      v10 = ParentSetD0(v5, 0, (_DWORD)PeekContext, (_DWORD)a2, (__int64)DispatchPdoSetPower_SetParentD0Completion);
      v6 = v10;
      if ( v10 != 259 )
      {
        if ( v10 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v11) = 4;
          WPP_RECORDER_SF_qq(
            *(_QWORD *)(v5 + 1368),
            v11,
            3,
            65,
            (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
            *((_QWORD *)PeekContext + 28),
            (char)a2);
        }
        v12 = (struct _DEVICE_OBJECT *)*((_QWORD *)PeekContext + 28);
        *((_DWORD *)PeekContext + 4) = 1;
        PoSetPowerState(v12, CurrentStackLocation->Parameters.Power.Type, CurrentStackLocation->Parameters.Power.State);
        CompleteFunctionIdleIrp(PeekContext, 0);
        if ( !*(_BYTE *)(v5 + 1362) )
          return 0;
        v19 = 2;
LABEL_33:
        LockSendSetFeatureControlRequestForFunctionSuspend(v5, (__int64)PeekContext, a2, v19);
        return 259;
      }
    }
    else if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 2
           || CurrentStackLocation->Parameters.Read.ByteOffset.LowPart - 3 <= 1 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qqL(*(_QWORD *)(v5 + 1368), LowPart, a3, 66);
      if ( CurrentStackLocation->Parameters.Read.ByteOffset.LowPart == 4 && !PeekContext[116] )
      {
        CompletePdoWaitWakeIrp(PeekContext, -1073741101);
        if ( !PeekContext[302] )
          CompleteFunctionIdleIrp(PeekContext, -1073741101);
      }
      v14 = *((_DWORD *)PeekContext + 4);
      *((_DWORD *)PeekContext + 28) = 1;
      if ( v14 == 1 )
      {
        *((_DWORD *)PeekContext + 4) = CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
        if ( CurrentStackLocation->Parameters.Create.EaLength - 2 <= 4 )
        {
          v15 = 1;
        }
        else
        {
          v15 = 0;
          if ( !PeekContext[300]
            && (int)AllocateWorker(v5, SetSelectiveSuspendRegistryFlag, PeekContext) < 0
            && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v20) = 4;
            WPP_RECORDER_SF_(
              *(_QWORD *)(v5 + 1368),
              v20,
              3,
              68,
              (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids);
          }
        }
        PoSetPowerState(
          *((PDEVICE_OBJECT *)PeekContext + 28),
          CurrentStackLocation->Parameters.Power.Type,
          CurrentStackLocation->Parameters.Power.State);
        if ( *(_BYTE *)(v5 + 1362) )
        {
          v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 400));
          v18 = (char *)*((_QWORD *)PeekContext + 12);
          KeReleaseSpinLock((PKSPIN_LOCK)(v5 + 400), v17);
          a2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
          v19 = v18 != PeekContext + 96;
          goto LABEL_33;
        }
        v16 = SetPdoIdle(v5, (__int64)PeekContext, 2, 1u, 1);
        if ( !v15 && v16 )
          ResumeIdleTimer(v5);
      }
      else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(LowPart) = 4;
        WPP_RECORDER_SF_qL(
          *(_QWORD *)(v5 + 1368),
          LowPart,
          3,
          67,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *((_QWORD *)PeekContext + 28),
          v14);
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(LowPart) = 4;
        WPP_RECORDER_SF_qD(
          *(_QWORD *)(v5 + 1368),
          LowPart,
          3,
          69,
          (__int64)WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids,
          *((_QWORD *)PeekContext + 28),
          CurrentStackLocation->Parameters.Read.ByteOffset.LowPart);
      }
      return (unsigned int)a2->IoStatus.Status;
    }
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_qqL(*(_QWORD *)(v5 + 1368), (_DWORD)a2, a3, 63);
  }
  return v6;
}

```

## disassembly

```asm
0x140005fc4  push    rbx
0x140005fc6  push    rbp
0x140005fc7  push    rsi
0x140005fc8  push    rdi
0x140005fc9  push    r12
0x140005fcb  push    r13
0x140005fcd  push    r14
0x140005fcf  push    r15
0x140005fd1  sub     rsp, 48h
0x140005fd5  mov     rsi, [rdx+0B8h]
0x140005fdc  mov     rbp, rcx
0x140005fdf  mov     r14, [rcx+0E8h]
0x140005fe6  xor     ebx, ebx
0x140005fe8  mov     r15, rdx
0x140005feb  mov     ecx, [rsi+10h]
0x140005fee  test    ecx, ecx
0x140005ff0  jz      loc_140006193
0x140005ff6  cmp     ecx, 1
0x140005ff9  jnz     loc_14000630B
0x140005fff  mov     edx, [rsi+18h]
0x140006002  mov     ecx, edx
0x140006004  sub     ecx, 1
0x140006007  jnz     loc_1400060C8
0x14000600d  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140006014  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14000601b  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140006022  jnz     loc_140006224
0x140006028  xor     r9d, r9d
0x14000602b  mov     byte ptr [rsp+88h+var_68], 1
0x140006030  mov     rdx, rbp
0x140006033  mov     rcx, r14
0x140006036  lea     r8d, [r9+2]
0x14000603a  call    SetPdoIdle
0x14000603f  cmp     [r14+552h], bl
0x140006046  jnz     loc_1400063B0
0x14000604c  lea     rax, DispatchPdoSetPower_SetParentD0Completion
0x140006053  mov     r9, r15
0x140006056  mov     r8, rbp
0x140006059  mov     [rsp+88h+var_68], rax
0x14000605e  xor     edx, edx
0x140006060  mov     rcx, r14
0x140006063  call    ParentSetD0
0x140006068  mov     ebx, eax
0x14000606a  cmp     eax, 103h
0x14000606f  jz      short loc_1400060B4
0x140006071  test    eax, eax
0x140006073  js      loc_1400063DC
0x140006079  mov     rcx, [rbp+0E0h]; DeviceObject
0x140006080  mov     dword ptr [rbp+10h], 1
0x140006087  mov     r8d, [rsi+18h]; State
0x14000608b  mov     edx, [rsi+10h]; Type
0x14000608e  call    cs:__imp_PoSetPowerState
0x140006095  nop     dword ptr [rax+rax+00h]
0x14000609a  xor     edx, edx
0x14000609c  mov     rcx, rbp; PeekContext
0x14000609f  call    CompleteFunctionIdleIrp
0x1400060a4  cmp     byte ptr [r14+552h], 0
0x1400060ac  jnz     loc_14000641C
0x1400060b2  xor     ebx, ebx
0x1400060b4  mov     eax, ebx
0x1400060b6  add     rsp, 48h
0x1400060ba  pop     r15
0x1400060bc  pop     r14
0x1400060be  pop     r13
0x1400060c0  pop     r12
0x1400060c2  pop     rdi
0x1400060c3  pop     rsi
0x1400060c4  pop     rbp
0x1400060c5  pop     rbx
0x1400060c6  retn
0x1400060c8  sub     ecx, 1
0x1400060cb  jz      short loc_1400060DB
0x1400060cd  sub     ecx, 1
0x1400060d0  jz      short loc_1400060DB
0x1400060d2  cmp     ecx, 1
0x1400060d5  jnz     loc_140006313
0x1400060db  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400060e2  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400060e9  jnz     loc_140006284
0x1400060ef  cmp     dword ptr [rsi+18h], 4
0x1400060f3  jnz     short loc_1400060FE
0x1400060f5  cmp     [rbp+74h], bl
0x1400060f8  jz      loc_140006257
0x1400060fe  mov     eax, [rbp+10h]
0x140006101  mov     dword ptr [rbp+70h], 1
0x140006108  cmp     eax, 1
0x14000610b  jnz     loc_1400061D6
0x140006111  mov     eax, [rsi+18h]
0x140006114  mov     [rbp+10h], eax
0x140006117  mov     eax, [rsi+20h]
0x14000611a  sub     eax, 2
0x14000611d  cmp     eax, 4
0x140006120  jbe     loc_14000621C
0x140006126  mov     r13b, bl
0x140006129  cmp     [rbp+12Ch], bl
0x14000612f  jz      loc_140006360
0x140006135  mov     r8d, [rsi+18h]; State
0x140006139  mov     edx, [rsi+10h]; Type
0x14000613c  mov     rcx, [rbp+0E0h]; DeviceObject
0x140006143  call    cs:__imp_PoSetPowerState
0x14000614a  nop     dword ptr [rax+rax+00h]
0x14000614f  cmp     [r14+552h], bl
0x140006156  jnz     loc_1400062B0
0x14000615c  mov     r9b, 1
0x14000615f  mov     byte ptr [rsp+88h+var_68], 1
0x140006164  mov     r8d, 2
0x14000616a  mov     rdx, rbp
0x14000616d  mov     rcx, r14
0x140006170  call    SetPdoIdle
0x140006175  test    r13b, r13b
0x140006178  jnz     loc_1400060B4
0x14000617e  test    al, al
0x140006180  jz      loc_1400060B4
0x140006186  mov     rcx, r14
0x140006189  call    ResumeIdleTimer
0x14000618e  jmp     loc_1400060B4
0x140006193  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000619a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400061a1  jz      loc_1400060B4
0x1400061a7  mov     eax, [rsi+18h]
0x1400061aa  mov     r9d, 3Fh ; '?'
0x1400061b0  mov     rcx, [r14+558h]
0x1400061b7  mov     [rsp+88h+var_50], eax
0x1400061bb  mov     rax, [rbp+0E0h]
0x1400061c2  mov     [rsp+88h+var_58], r15
0x1400061c7  mov     [rsp+88h+var_60], rax
0x1400061cc  call    WPP_RECORDER_SF_qqL
0x1400061d1  jmp     loc_1400060B4
0x1400061d6  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400061dd  jz      loc_1400060B4
0x1400061e3  mov     rcx, [r14+558h]
0x1400061ea  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x1400061f1  mov     dword ptr [rsp+88h+var_58], eax
0x1400061f5  mov     r9d, 43h ; 'C'
0x1400061fb  mov     rax, [rbp+0E0h]
0x140006202  mov     dl, 4
0x140006204  mov     [rsp+88h+var_60], rax
0x140006209  mov     [rsp+88h+var_68], r12
0x14000620e  lea     r8d, [r9-40h]
0x140006212  call    WPP_RECORDER_SF_qL
0x140006217  jmp     loc_1400060B4
0x14000621c  mov     r13b, 1
0x14000621f  jmp     loc_140006135
0x140006224  mov     rax, [rbp+0E0h]
0x14000622b  mov     r9d, 40h ; '@'
0x140006231  mov     rcx, [r14+558h]
0x140006238  mov     dl, 4
0x14000623a  mov     [rsp+88h+var_58], r15
0x14000623f  mov     [rsp+88h+var_60], rax
0x140006244  lea     r8d, [r9-3Dh]
0x140006248  mov     [rsp+88h+var_68], r12
0x14000624d  call    WPP_RECORDER_SF_qq
0x140006252  jmp     loc_140006028
0x140006257  mov     r12d, 0C00002D3h
0x14000625d  mov     rcx, rbp; PeekContext
0x140006260  mov     edx, r12d
0x140006263  call    CompletePdoWaitWakeIrp
0x140006268  cmp     [rbp+12Eh], bl
0x14000626e  jnz     loc_1400060FE
0x140006274  mov     edx, r12d
0x140006277  mov     rcx, rbp; PeekContext
0x14000627a  call    CompleteFunctionIdleIrp
0x14000627f  jmp     loc_1400060FE
0x140006284  mov     rax, [rbp+0E0h]
0x14000628b  mov     r9d, 42h ; 'B'
0x140006291  mov     rcx, [r14+558h]
0x140006298  mov     [rsp+88h+var_50], edx
0x14000629c  mov     [rsp+88h+var_58], r15
0x1400062a1  mov     [rsp+88h+var_60], rax
0x1400062a6  call    WPP_RECORDER_SF_qqL
0x1400062ab  jmp     loc_1400060EF
0x1400062b0  lea     rbx, [r14+190h]
0x1400062b7  mov     rcx, rbx; SpinLock
0x1400062ba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400062c1  nop     dword ptr [rax+rax+00h]
0x1400062c6  lea     rsi, [rbp+60h]
0x1400062ca  mov     rcx, rbx; SpinLock
0x1400062cd  mov     rdi, [rsi]
0x1400062d0  mov     dl, al; NewIrql
0x1400062d2  call    cs:__imp_KeReleaseSpinLock
0x1400062d9  nop     dword ptr [rax+rax+00h]
0x1400062de  mov     rax, [r15+0B8h]
0x1400062e5  xor     r9d, r9d
0x1400062e8  or      byte ptr [rax+3], 1
0x1400062ec  cmp     rdi, rsi
0x1400062ef  setnz   r9b
0x1400062f3  mov     r8, r15
0x1400062f6  mov     rdx, rbp
0x1400062f9  mov     rcx, r14
0x1400062fc  call    LockSendSetFeatureControlRequestForFunctionSuspend
0x140006301  mov     ebx, 103h
0x140006306  jmp     loc_1400060B4
0x14000630b  mov     ebx, [rdx+30h]
0x14000630e  jmp     loc_1400060B4
0x140006313  lea     rdi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000631a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140006321  jz      short loc_140006357
0x140006323  mov     rax, [rbp+0E0h]
0x14000632a  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140006331  mov     rcx, [r14+558h]
0x140006338  mov     r9d, 45h ; 'E'
0x14000633e  mov     dword ptr [rsp+88h+var_58], edx
0x140006342  mov     dl, 4
0x140006344  mov     [rsp+88h+var_60], rax
0x140006349  mov     [rsp+88h+var_68], r12
0x14000634e  lea     r8d, [r9-42h]
0x140006352  call    WPP_RECORDER_SF_qD
0x140006357  mov     ebx, [r15+30h]
0x14000635b  jmp     loc_1400060B4
0x140006360  mov     r8, rbp
0x140006363  lea     rdx, SetSelectiveSuspendRegistryFlag
0x14000636a  mov     rcx, r14
0x14000636d  call    AllocateWorker
0x140006372  test    eax, eax
0x140006374  jns     loc_140006135
0x14000637a  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x140006381  jz      loc_140006135
0x140006387  mov     rcx, [r14+558h]
0x14000638e  lea     r12, WPP_6d8a51a08a9b3edb1d37cbc5358a5e6d_Traceguids
0x140006395  mov     r9d, 44h ; 'D'
0x14000639b  mov     [rsp+88h+var_68], r12
0x1400063a0  mov     dl, 4
0x1400063a2  lea     r8d, [r9-41h]
0x1400063a6  call    WPP_RECORDER_SF_
0x1400063ab  jmp     loc_140006135
0x1400063b0  lea     rcx, [rbp+20h]; Csq
0x1400063b4  mov     rdx, rbp; PeekContext
0x1400063b7  call    cs:__imp_IoCsqRemoveNextIrp
0x1400063be  nop     dword ptr [rax+rax+00h]
0x1400063c3  test    rax, rax
0x1400063c6  jz      loc_14000604C
0x1400063cc  mov     rdx, rax
0x1400063cf  mov     rcx, rbp
0x1400063d2  call    CancelRemoteWakeNotificationIrp
0x1400063d7  jmp     loc_14000604C
0x1400063dc  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x1400063e3  jz      loc_140006079
0x1400063e9  mov     rax, [rbp+0E0h]
0x1400063f0  mov     r9d, 41h ; 'A'
0x1400063f6  mov     rcx, [r14+558h]
0x1400063fd  mov     dl, 4
0x1400063ff  mov     [rsp+88h+var_58], r15
0x140006404  mov     [rsp+88h+var_60], rax
0x140006409  lea     r8d, [r9-3Eh]
0x14000640d  mov     [rsp+88h+var_68], r12
0x140006412  call    WPP_RECORDER_SF_qq
0x140006417  jmp     loc_140006079
0x14000641c  mov     r9d, 2
0x140006422  jmp     loc_1400062F3
```
