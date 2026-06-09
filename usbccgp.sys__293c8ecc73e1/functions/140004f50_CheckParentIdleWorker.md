# CheckParentIdleWorker

- ea: `0x140004f50`
- end: `0x1400052af`
- name: `CheckParentIdleWorker`
- size: `863`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x140004f50`
- `0x1400054a0`
- `0x1400055c0`
- `0x140006834`
- `0x140006af8`
- `0x140006d40`
- `0x140007020`
- `0x14000773c`
- `0x1400088b4`
- `0x1400099a8`
- `0x14000eb6c`
- `0x140029f14`
- `0x14002a0b0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005104`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140005104`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005283`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140004f6c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005283`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005033`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400050ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005233`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005033`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400050ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005233`
- `ntoskrnl!KeSetEvent` at `0x14000507e`
- `ntoskrnl!KeSetEvent` at `0x1400050c5`
- `ntoskrnl!KeSetEvent` at `0x140005153`
- `ntoskrnl!KeSetEvent` at `0x14000507e`
- `ntoskrnl!KeSetEvent` at `0x1400050c5`
- `ntoskrnl!KeSetEvent` at `0x140005153`
- `ntoskrnl!KeResetEvent` at `0x140005021`
- `ntoskrnl!KeResetEvent` at `0x140005021`

## string_xrefs

- `0x140005267`: `idleCompleteEvent`

## pseudocode

```c
void __fastcall CheckParentIdleWorker(PDEVICE_OBJECT DeviceObject, char *Context)
{
  KSPIN_LOCK *v2; // rbp
  KIRQL v4; // al
  _DWORD *v5; // r8
  __int64 v6; // rdx
  KIRQL v7; // r12
  int *v8; // rdi
  int *v9; // r13
  int v10; // eax
  int v11; // eax
  __int64 v12; // r8
  int v13; // edx
  int v14; // r9d
  __int64 v15; // rdx
  __int64 v16; // rdx

  v2 = (KSPIN_LOCK *)(Context + 696);
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)Context + 87);
  v5 = (_DWORD *)*((_QWORD *)Context + 16);
  v6 = 0;
  Context[860] = 0;
  v7 = v4;
  while ( (unsigned int)v6 < *v5 )
  {
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v5[2 * v6 + 2] + 64LL) + 304LL) & 0x17) == 0 )
    {
      v8 = (int *)(Context + 688);
LABEL_19:
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_20:
        KeReleaseSpinLock(v2, v7);
        goto LABEL_21;
      }
      v10 = *v8;
      v14 = 22;
LABEL_27:
      LOBYTE(v6) = 4;
      WPP_RECORDER_SF_qL(
        *((_QWORD *)Context + 171),
        v6,
        7,
        v14,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        *((_QWORD *)Context + 82),
        v10);
      goto LABEL_20;
    }
    v6 = (unsigned int)(v6 + 1);
  }
  v8 = (int *)(Context + 688);
  if ( *((_DWORD *)Context + 172) == 1 )
    goto LABEL_19;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_(*((_QWORD *)Context + 171), v6, 7, 19, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
  }
  v9 = (int *)(Context + 688);
  if ( *v8 == 2 )
  {
    KeReleaseSpinLock(v2, v7);
    DisableIdleTimer(Context, v15, 1346586964);
    if ( !Context[1376] )
      WaitForSignal(Context + 960);
    LOBYTE(v16) = 1;
    EnableIdleTimer(Context, v16, 1346586964);
    v7 = KeAcquireSpinLockRaiseToDpc(v2);
  }
  else
  {
    v9 = (int *)(Context + 688);
  }
  v10 = *v9;
  if ( *v9 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_20;
    v14 = 21;
    goto LABEL_27;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 4;
    WPP_RECORDER_SF_(*((_QWORD *)Context + 171), v6, 7, 20, (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 4;
      WPP_RECORDER_SF_qLL(
        *((_QWORD *)Context + 171),
        v13,
        7,
        55,
        (__int64)WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids,
        *((_QWORD *)Context + 4),
        *v8,
        1);
    }
  }
  if ( *v8 == 5 )
  {
    *v8 = 1;
    KeSetEvent((PRKEVENT)(Context + 872), 0, 0);
  }
  *v8 = 1;
  KeResetEvent((PRKEVENT)Context + 40);
  KeReleaseSpinLock(v2, v7);
  if ( Context[442] == 1 || !Context[440] )
    v11 = PretendToSubmitParentIdleIrp(Context, *((_QWORD *)Context + 82));
  else
    v11 = SubmitParentIdleIrp(Context, *((_QWORD *)Context + 82));
  if ( v11 < 0 )
  {
    CancelFdoIdleIrp(Context, 0);
    LOBYTE(v12) = 1;
    ChangeIdleState(Context, 0, v12);
    KeSetEvent((PRKEVENT)Context + 40, 0, 0);
  }
LABEL_21:
  KeSetEvent((PRKEVENT)Context + 32, 0, 0);
  PauseIdleTimer(Context);
  _InterlockedExchange((volatile __int32 *)Context + 246, 0);
  UsbcReleaseRemoveLock(Context, CheckParentIdleWorker);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(Context + 200), CheckParentIdleWorker, 0x20u);
}

```

## disassembly

```asm
0x140004f50  push    rbx
0x140004f52  push    rbp
0x140004f53  push    rsi
0x140004f54  push    rdi
0x140004f55  push    r12
0x140004f57  push    r13
0x140004f59  push    r15
0x140004f5b  sub     rsp, 40h
0x140004f5f  lea     rbp, [rdx+2B8h]
0x140004f66  mov     rbx, rdx
0x140004f69  mov     rcx, rbp; SpinLock
0x140004f6c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140004f73  nop     dword ptr [rax+rax+00h]
0x140004f78  mov     r8, [rbx+80h]
0x140004f7f  xor     edx, edx
0x140004f81  mov     byte ptr [rbx+35Ch], 0
0x140004f88  mov     r12b, al
0x140004f8b  mov     r9d, [r8]
0x140004f8e  cmp     edx, r9d
0x140004f91  jnb     short loc_140004FAE
0x140004f93  mov     rax, [r8+rdx*8+8]
0x140004f98  mov     rcx, [rax+40h]
0x140004f9c  mov     eax, [rcx+130h]
0x140004fa2  test    al, 17h
0x140004fa4  jz      loc_14000508C
0x140004faa  inc     edx
0x140004fac  jmp     short loc_140004F8E
0x140004fae  lea     rdi, [rbx+2B0h]
0x140004fb5  cmp     dword ptr [rdi], 1
0x140004fb8  jz      loc_140005093
0x140004fbe  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004fc5  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140004fcc  lea     r15, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x140004fd3  jnz     loc_1400051C7
0x140004fd9  mov     r13, rdi
0x140004fdc  cmp     dword ptr [rdi], 2
0x140004fdf  jz      loc_14000522D
0x140004fe5  mov     r13, rdi
0x140004fe8  mov     eax, [r13+0]
0x140004fec  test    eax, eax
0x140004fee  jnz     loc_140005297
0x140004ff4  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140004ffb  jnz     loc_140005164
0x140005001  mov     ecx, [rdi]
0x140005003  sub     ecx, 4
0x140005006  jz      short loc_140005011
0x140005008  cmp     ecx, 1
0x14000500b  jz      loc_140005141
0x140005011  mov     dword ptr [rdi], 1
0x140005017  lea     rdi, [rbx+3C0h]
0x14000501e  mov     rcx, rdi; Event
0x140005021  call    cs:__imp_KeResetEvent
0x140005028  nop     dword ptr [rax+rax+00h]
0x14000502d  mov     dl, r12b; NewIrql
0x140005030  mov     rcx, rbp; SpinLock
0x140005033  call    cs:__imp_KeReleaseSpinLock
0x14000503a  nop     dword ptr [rax+rax+00h]
0x14000503f  cmp     byte ptr [rbx+1BAh], 1
0x140005046  jnz     loc_140005120
0x14000504c  mov     rdx, [rbx+290h]
0x140005053  mov     rcx, rbx
0x140005056  call    PretendToSubmitParentIdleIrp
0x14000505b  test    eax, eax
0x14000505d  jns     short loc_1400050B9
0x14000505f  xor     edx, edx
0x140005061  mov     rcx, rbx
0x140005064  call    CancelFdoIdleIrp
0x140005069  mov     r8b, 1
0x14000506c  xor     edx, edx
0x14000506e  mov     rcx, rbx
0x140005071  call    ChangeIdleState
0x140005076  xor     r8d, r8d; Wait
0x140005079  xor     edx, edx; Increment
0x14000507b  mov     rcx, rdi; Event
0x14000507e  call    cs:__imp_KeSetEvent
0x140005085  nop     dword ptr [rax+rax+00h]
0x14000508a  jmp     short loc_1400050B9
0x14000508c  lea     rdi, [rbx+2B0h]
0x140005093  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000509a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400050a1  jnz     loc_1400051F0
0x1400050a7  mov     dl, r12b; NewIrql
0x1400050aa  mov     rcx, rbp; SpinLock
0x1400050ad  call    cs:__imp_KeReleaseSpinLock
0x1400050b4  nop     dword ptr [rax+rax+00h]
0x1400050b9  lea     rcx, [rbx+300h]; Event
0x1400050c0  xor     r8d, r8d; Wait
0x1400050c3  xor     edx, edx; Increment
0x1400050c5  call    cs:__imp_KeSetEvent
0x1400050cc  nop     dword ptr [rax+rax+00h]
0x1400050d1  mov     rcx, rbx
0x1400050d4  call    PauseIdleTimer
0x1400050d9  xor     eax, eax
0x1400050db  lea     rdx, CheckParentIdleWorker
0x1400050e2  xchg    eax, [rbx+3D8h]
0x1400050e8  mov     rcx, rbx
0x1400050eb  call    UsbcReleaseRemoveLock
0x1400050f0  lea     rcx, [rbx+0C8h]; RemoveLock
0x1400050f7  mov     r8d, 20h ; ' '; RemlockSize
0x1400050fd  lea     rdx, CheckParentIdleWorker; Tag
0x140005104  call    cs:__imp_IoReleaseRemoveLockEx
0x14000510b  nop     dword ptr [rax+rax+00h]
0x140005110  add     rsp, 40h
0x140005114  pop     r15
0x140005116  pop     r13
0x140005118  pop     r12
0x14000511a  pop     rdi
0x14000511b  pop     rsi
0x14000511c  pop     rbp
0x14000511d  pop     rbx
0x14000511e  retn
0x140005120  cmp     byte ptr [rbx+1B8h], 0
0x140005127  jz      loc_14000504C
0x14000512d  mov     rdx, [rbx+290h]
0x140005134  mov     rcx, rbx
0x140005137  call    SubmitParentIdleIrp
0x14000513c  jmp     loc_14000505B
0x140005141  lea     rcx, [rbx+368h]; Event
0x140005148  mov     dword ptr [rdi], 1
0x14000514e  xor     r8d, r8d; Wait
0x140005151  xor     edx, edx; Increment
0x140005153  call    cs:__imp_KeSetEvent
0x14000515a  nop     dword ptr [rax+rax+00h]
0x14000515f  jmp     loc_140005011
0x140005164  mov     rcx, [rbx+558h]
0x14000516b  mov     r9d, 14h
0x140005171  mov     dl, 4
0x140005173  mov     [rsp+78h+var_58], r15
0x140005178  lea     r8d, [r9-0Dh]
0x14000517c  call    WPP_RECORDER_SF_
0x140005181  mov     eax, [rdi]
0x140005183  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000518a  jz      loc_140005001
0x140005190  mov     rcx, [rbx+558h]
0x140005197  mov     r9d, 37h ; '7'
0x14000519d  mov     [rsp+78h+var_40], 1
0x1400051a5  mov     dl, 4
0x1400051a7  mov     [rsp+78h+var_48], eax
0x1400051ab  mov     rax, [rbx+20h]
0x1400051af  mov     [rsp+78h+var_50], rax
0x1400051b4  lea     r8d, [r9-30h]
0x1400051b8  mov     [rsp+78h+var_58], r15
0x1400051bd  call    WPP_RECORDER_SF_qLL
0x1400051c2  jmp     loc_140005001
0x1400051c7  mov     rcx, [rbx+558h]
0x1400051ce  mov     r9d, 13h
0x1400051d4  mov     dl, 4
0x1400051d6  mov     [rsp+78h+var_58], r15
0x1400051db  lea     r8d, [r9-0Ch]
0x1400051df  call    WPP_RECORDER_SF_
0x1400051e4  lea     r13, [rbx+2B0h]
0x1400051eb  jmp     loc_140004FDC
0x1400051f0  mov     eax, [rdi]
0x1400051f2  lea     r15, WPP_dd1e712d547938a03f2007c63d036cf9_Traceguids
0x1400051f9  mov     r9d, 16h
0x1400051ff  mov     rcx, [rbx+558h]
0x140005206  mov     r8d, 7
0x14000520c  mov     [rsp+78h+var_48], eax
0x140005210  mov     dl, 4
0x140005212  mov     rax, [rbx+290h]
0x140005219  mov     [rsp+78h+var_50], rax
0x14000521e  mov     [rsp+78h+var_58], r15
0x140005223  call    WPP_RECORDER_SF_qL
0x140005228  jmp     loc_1400050A7
0x14000522d  mov     dl, r12b; NewIrql
0x140005230  mov     rcx, rbp; SpinLock
0x140005233  call    cs:__imp_KeReleaseSpinLock
0x14000523a  nop     dword ptr [rax+rax+00h]
0x14000523f  mov     r12d, 50434954h
0x140005245  mov     rcx, rbx
0x140005248  mov     r8d, r12d
0x14000524b  call    DisableIdleTimer
0x140005250  cmp     byte ptr [rbx+560h], 0
0x140005257  jnz     short loc_140005273
0x140005259  mov     r8, [rbx+558h]
0x140005260  lea     rcx, [rbx+3C0h]; Object
0x140005267  lea     rdx, aIdlecompleteev; "idleCompleteEvent"
0x14000526e  call    WaitForSignal
0x140005273  mov     r8d, r12d
0x140005276  mov     dl, 1
0x140005278  mov     rcx, rbx
0x14000527b  call    EnableIdleTimer
0x140005280  mov     rcx, rbp; SpinLock
0x140005283  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000528a  nop     dword ptr [rax+rax+00h]
0x14000528f  mov     r12b, al
0x140005292  jmp     loc_140004FE8
0x140005297  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14000529e  jz      loc_1400050A7
0x1400052a4  mov     r9d, 15h
0x1400052aa  jmp     loc_1400051FF
```
