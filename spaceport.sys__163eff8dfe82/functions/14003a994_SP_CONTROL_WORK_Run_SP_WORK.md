# SP_CONTROL_WORK::Run(SP_WORK *)

- ea: `0x14003a994`
- end: `0x14003ae2c`
- name: `?Run@SP_CONTROL_WORK@@QEAAJPEAVSP_WORK@@@Z`
- size: `1176`
- prototype: `__int64 __fastcall(SP_CONTROL_WORK *__hidden this, struct SP_WORK *)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400aa964`
- `0x1400ab0f4`
- `0x1400abfe0`
- `0x1400ac334`
- `0x1400ac558`
- `0x1400ac6e4`
- `0x1400ac920`
- `0x1400b07fc`

## callees

- `0x14002ae44`
- `0x14002ce90`
- `0x14002e43c`
- `0x14003a994`
- `0x140068110`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003aad3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003acd1`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003aad3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003acd1`
- `ntoskrnl!KeResetEvent` at `0x14003ad4c`
- `ntoskrnl!KeResetEvent` at `0x14003ad5c`
- `ntoskrnl!KeResetEvent` at `0x14003ad4c`
- `ntoskrnl!KeResetEvent` at `0x14003ad5c`
- `ntoskrnl!KeReadStateEvent` at `0x14003aa2b`
- `ntoskrnl!KeReadStateEvent` at `0x14003aaa6`
- `ntoskrnl!KeReadStateEvent` at `0x14003aa2b`
- `ntoskrnl!KeReadStateEvent` at `0x14003aaa6`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003ab85`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003ab85`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003abe6`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ac92`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003abe6`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ac92`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003ab23`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003ab23`
- `ntoskrnl!IofCompleteRequest` at `0x14003ab4b`
- `ntoskrnl!IofCompleteRequest` at `0x14003ab4b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab5b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ad02`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ab5b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ad02`

## pseudocode

```c
__int64 __fastcall SP_CONTROL_WORK::Run(KSPIN_LOCK *this, struct SP_WORK *a2)
{
  struct _KEVENT *v4; // rcx
  char *v5; // rsi
  __int64 v6; // rcx
  KSPIN_LOCK *v7; // r12
  int v8; // ecx
  SP_CONTROL_WORK **v9; // rcx
  PIRP v10; // rax
  IRP *v11; // r14
  __int64 v12; // r15
  NTSTATUS v13; // eax
  int v14; // ebx
  ULONG v15; // r10d
  NTSTATUS v16; // eax
  struct SP_WORK *v17; // rcx
  struct SP_WORK **v18; // rax
  int v19; // ebx
  ULONG DeviceType; // ecx
  const char *v21; // r9
  union _LARGE_INTEGER Timeout; // [rsp+40h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+48h] [rbp-38h] BYREF
  PVOID Object[2]; // [rsp+60h] [rbp-20h] BYREF
  __int64 v26; // [rsp+70h] [rbp-10h]

  memset(&LockHandle, 0, sizeof(LockHandle));
  v26 = 0;
  Timeout.QuadPart = 0;
  *(_OWORD *)Object = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids);
  }
  if ( !*((_BYTE *)a2 + 80) )
    goto LABEL_13;
  v4 = (struct _KEVENT *)*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 365);
  if ( !v4 || !KeReadStateEvent(v4) )
  {
    v6 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 366);
    if ( !v6 )
      goto LABEL_13;
    if ( MEMORY[0xFFFFF78000000008] - v6 >= 300000000 )
      *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 366) = 0;
    if ( !*((_QWORD *)WPP_MAIN_CB.DeviceExtension + 366) )
    {
LABEL_13:
      v5 = (char *)a2 + 16;
      if ( KeReadStateEvent((PRKEVENT)((char *)WPP_MAIN_CB.DeviceExtension + 2936)) )
      {
        *(_DWORD *)(*(_QWORD *)v5 + 88LL) = -1073741077;
        goto LABEL_42;
      }
      v7 = this + 16;
      KeAcquireInStackQueuedSpinLock(this + 16, &LockHandle);
      v8 = *((_DWORD *)this + 30);
      *((_DWORD *)this + 30) = v8 + 1;
      *(_DWORD *)(*(_QWORD *)v5 + 8LL) = v8;
      *(_DWORD *)(*(_QWORD *)v5 + 88LL) = 259;
      *(_DWORD *)(*(_QWORD *)v5 + 92LL) = 0;
      v9 = (SP_CONTROL_WORK **)this[12];
      if ( *v9 != (SP_CONTROL_WORK *)(this + 11) )
        goto LABEL_56;
      *((_QWORD *)a2 + 1) = v9;
      *(_QWORD *)a2 = this + 11;
      *v9 = a2;
      this[12] = (KSPIN_LOCK)a2;
      v10 = IoCsqRemoveNextIrp((PIO_CSQ)this, 0);
      v11 = v10;
      if ( v10 )
      {
        v10->IoStatus.Status = SP_CONTROL_WORK::GetInternal((SP_CONTROL_WORK *)this, v10);
        IofCompleteRequest(v11, 0);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      ZwUpdateWnfStateData(&WNF_SPAC_SPACEPORT_WORK_REQUESTED, 0, 0, 0, 0, 0, 0);
      Timeout.QuadPart = -150000000;
      Object[0] = (char *)a2 + 32;
      Object[1] = (char *)WPP_MAIN_CB.DeviceExtension + 2936;
      v12 = MEMORY[0xFFFFF78000000008];
      v13 = KeWaitForMultipleObjects(2u, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
      v14 = v13;
      if ( v13 == 1 )
      {
        v14 = -1073741077;
      }
      else if ( v13 != 258 )
      {
        if ( v13 != -1073741077 )
        {
          Timeout.QuadPart = *((_QWORD *)a2 + 3) - v12 + MEMORY[0xFFFFF78000000008];
          if ( Timeout.QuadPart >= 0 )
          {
            v14 = 258;
            goto LABEL_34;
          }
          v15 = 2;
          Object[0] = (char *)a2 + 56;
          if ( *((_BYTE *)a2 + 80) && *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 365) )
          {
            v26 = *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 365);
            v15 = 3;
          }
          v16 = KeWaitForMultipleObjects(v15, Object, WaitAny, Executive, 0, 0, &Timeout, 0);
          v14 = v16;
          switch ( v16 )
          {
            case 1:
              v14 = -1073741077;
              goto LABEL_34;
            case 2:
              v14 = -1072496628;
              goto LABEL_34;
            case 258:
              goto LABEL_34;
          }
        }
        if ( v14 != -1072496628 && v14 != -1073741077 )
        {
LABEL_41:
          KeResetEvent((PRKEVENT)((char *)a2 + 32));
          KeResetEvent((PRKEVENT)((char *)a2 + 56));
          goto LABEL_42;
        }
      }
LABEL_34:
      KeAcquireInStackQueuedSpinLock(v7, &LockHandle);
      v17 = *(struct SP_WORK **)a2;
      if ( *(struct SP_WORK **)(*(_QWORD *)a2 + 8LL) == a2 )
      {
        v18 = (struct SP_WORK **)*((_QWORD *)a2 + 1);
        if ( *v18 == a2 )
        {
          *v18 = v17;
          *((_QWORD *)v17 + 1) = v18;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
          if ( v14 == 258 )
          {
            if ( *((_BYTE *)a2 + 80) )
              *((_QWORD *)WPP_MAIN_CB.DeviceExtension + 366) = MEMORY[0xFFFFF78000000008];
            *(_DWORD *)(*(_QWORD *)v5 + 88LL) = -1073741643;
          }
          else
          {
            *(_DWORD *)(*(_QWORD *)v5 + 88LL) = v14;
          }
          goto LABEL_41;
        }
      }
LABEL_56:
      __fastfail(3u);
    }
  }
  v5 = (char *)a2 + 16;
  *(_DWORD *)(*((_QWORD *)a2 + 2) + 88LL) = -1072496628;
LABEL_42:
  v19 = *(_DWORD *)(*(_QWORD *)v5 + 88LL);
  if ( v19 >= 0 || v19 == -2147483643 || v19 == -1073741789 )
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 3 )
    {
      DeviceType = 3;
      WPP_MAIN_CB.DeviceType = 3;
    }
    v21 = "Exit ";
  }
  else
  {
    DeviceType = WPP_MAIN_CB.DeviceType;
    if ( WPP_MAIN_CB.DeviceType != 1 )
    {
      DeviceType = 1;
      WPP_MAIN_CB.DeviceType = 1;
    }
    v21 = "Error";
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= DeviceType )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      88,
      (unsigned int)WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids,
      (_DWORD)v21,
      v19);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x14003a994  mov     [rsp-38h+arg_10], rbx
0x14003a999  push    rbp
0x14003a99a  push    rsi
0x14003a99b  push    rdi
0x14003a99c  push    r12
0x14003a99e  push    r13
0x14003a9a0  push    r14
0x14003a9a2  push    r15
0x14003a9a4  mov     rbp, rsp
0x14003a9a7  sub     rsp, 80h
0x14003a9ae  mov     rax, cs:__security_cookie
0x14003a9b5  xor     rax, rsp
0x14003a9b8  mov     [rbp+var_8], rax
0x14003a9bc  xor     r15d, r15d
0x14003a9bf  xorps   xmm0, xmm0
0x14003a9c2  xor     eax, eax
0x14003a9c4  mov     [rbp+LockHandle.LockQueue.Next], r15
0x14003a9c8  mov     [rbp+var_10], rax
0x14003a9cc  mov     rdi, rdx
0x14003a9cf  mov     rbx, rcx
0x14003a9d2  mov     qword ptr [rbp+var_40], r15
0x14003a9d6  movups  xmmword ptr [rbp+LockHandle.LockQueue.Lock], xmm0
0x14003a9da  movups  xmmword ptr [rbp+Object], xmm0
0x14003a9de  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a9e5  lea     r14, WPP_GLOBAL_Control
0x14003a9ec  cmp     rcx, r14
0x14003a9ef  jz      short loc_14003AA12
0x14003a9f1  mov     eax, [rcx+2Ch]
0x14003a9f4  test    al, 1
0x14003a9f6  jz      short loc_14003AA12
0x14003a9f8  cmp     byte ptr [rcx+29h], 3
0x14003a9fc  jb      short loc_14003AA12
0x14003a9fe  mov     rcx, [rcx+18h]
0x14003aa02  lea     edx, [r15+57h]
0x14003aa06  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003aa0d  call    WPP_SF_
0x14003aa12  cmp     [rdi+50h], r15b
0x14003aa16  jz      short loc_14003AA94
0x14003aa18  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003aa1f  mov     rcx, [rax+0B68h]; Event
0x14003aa26  test    rcx, rcx
0x14003aa29  jz      short loc_14003AA4E
0x14003aa2b  call    cs:__imp_KeReadStateEvent
0x14003aa32  nop     dword ptr [rax+rax+00h]
0x14003aa37  test    eax, eax
0x14003aa39  jz      short loc_14003AA4E
0x14003aa3b  lea     rsi, [rdi+10h]
0x14003aa3f  mov     rax, [rsi]
0x14003aa42  mov     dword ptr [rax+58h], 0C013000Ch
0x14003aa49  jmp     loc_14003AD6F
0x14003aa4e  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003aa55  mov     rcx, [rax+0B70h]
0x14003aa5c  test    rcx, rcx
0x14003aa5f  jz      short loc_14003AA94
0x14003aa61  mov     rax, ds:0FFFFF78000000008h
0x14003aa6b  sub     rax, rcx
0x14003aa6e  cmp     rax, 11E1A300h
0x14003aa74  jl      short loc_14003AA84
0x14003aa76  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003aa7d  mov     [rax+0B70h], r15
0x14003aa84  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003aa8b  cmp     [rax+0B70h], r15
0x14003aa92  jnz     short loc_14003AA3B
0x14003aa94  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003aa9b  lea     rsi, [rdi+10h]
0x14003aa9f  add     rcx, 0B78h; Event
0x14003aaa6  call    cs:__imp_KeReadStateEvent
0x14003aaad  nop     dword ptr [rax+rax+00h]
0x14003aab2  test    eax, eax
0x14003aab4  jz      short loc_14003AAC5
0x14003aab6  mov     rax, [rsi]
0x14003aab9  mov     dword ptr [rax+58h], 0C00002EBh
0x14003aac0  jmp     loc_14003AD68
0x14003aac5  lea     r12, [rbx+80h]
0x14003aacc  mov     rcx, r12; SpinLock
0x14003aacf  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003aad3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003aada  nop     dword ptr [rax+rax+00h]
0x14003aadf  mov     ecx, [rbx+78h]
0x14003aae2  lea     eax, [rcx+1]
0x14003aae5  mov     [rbx+78h], eax
0x14003aae8  mov     rax, [rsi]
0x14003aaeb  mov     [rax+8], ecx
0x14003aaee  mov     rax, [rsi]
0x14003aaf1  mov     dword ptr [rax+58h], 103h
0x14003aaf8  mov     rax, [rsi]
0x14003aafb  mov     [rax+5Ch], r15d
0x14003aaff  lea     rax, [rbx+58h]
0x14003ab03  mov     rcx, [rax+8]
0x14003ab07  cmp     [rcx], rax
0x14003ab0a  jnz     loc_14003AE25
0x14003ab10  mov     [rdi+8], rcx
0x14003ab14  xor     edx, edx; PeekContext
0x14003ab16  mov     [rdi], rax
0x14003ab19  mov     [rcx], rdi
0x14003ab1c  mov     rcx, rbx; Csq
0x14003ab1f  mov     [rax+8], rdi
0x14003ab23  call    cs:__imp_IoCsqRemoveNextIrp
0x14003ab2a  nop     dword ptr [rax+rax+00h]
0x14003ab2f  mov     r14, rax
0x14003ab32  test    rax, rax
0x14003ab35  jz      short loc_14003AB57
0x14003ab37  mov     rdx, rax; struct _IRP *
0x14003ab3a  mov     rcx, rbx; this
0x14003ab3d  call    ?GetInternal@SP_CONTROL_WORK@@AEAAJPEAU_IRP@@@Z; SP_CONTROL_WORK::GetInternal(_IRP *)
0x14003ab42  xor     edx, edx; PriorityBoost
0x14003ab44  mov     [r14+30h], eax
0x14003ab48  mov     rcx, r14; Irp
0x14003ab4b  call    cs:__imp_IofCompleteRequest
0x14003ab52  nop     dword ptr [rax+rax+00h]
0x14003ab57  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003ab5b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ab62  nop     dword ptr [rax+rax+00h]
0x14003ab67  mov     dword ptr [rsp+80h+Timeout], r15d
0x14003ab6c  lea     rcx, WNF_SPAC_SPACEPORT_WORK_REQUESTED
0x14003ab73  mov     dword ptr [rsp+80h+Alertable], r15d
0x14003ab78  xor     r9d, r9d
0x14003ab7b  xor     r8d, r8d
0x14003ab7e  mov     qword ptr [rsp+80h+WaitMode], r15
0x14003ab83  xor     edx, edx
0x14003ab85  call    cs:__imp_ZwUpdateWnfStateData
0x14003ab8c  nop     dword ptr [rax+rax+00h]
0x14003ab91  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003ab98  lea     r13, [rdi+20h]
0x14003ab9c  xor     ecx, ecx
0x14003ab9e  mov     qword ptr [rbp+var_40], 0FFFFFFFFF70F2E80h
0x14003aba6  mov     [rsp+80h+WaitBlockArray], rcx; WaitBlockArray
0x14003abab  lea     rdx, [rbp+Object]; Object
0x14003abaf  add     rax, 0B78h
0x14003abb5  mov     [rbp+Object], r13
0x14003abb9  mov     [rbp+Object+8], rax
0x14003abbd  xor     r9d, r9d; WaitReason
0x14003abc0  lea     rax, [rbp+var_40]
0x14003abc4  mov     r14, 0FFFFF78000000008h
0x14003abce  mov     [rsp+80h+Timeout], rax; Timeout
0x14003abd3  lea     r8d, [rcx+1]; WaitType
0x14003abd7  mov     [rsp+80h+Alertable], cl; Alertable
0x14003abdb  mov     [rsp+80h+WaitMode], cl; WaitMode
0x14003abdf  lea     ecx, [r9+2]; Count
0x14003abe3  mov     r15, [r14]
0x14003abe6  call    cs:__imp_KeWaitForMultipleObjects
0x14003abed  nop     dword ptr [rax+rax+00h]
0x14003abf2  mov     rcx, [r14]
0x14003abf5  mov     r8d, 102h
0x14003abfb  mov     ebx, eax
0x14003abfd  cmp     eax, 1
0x14003ac00  jnz     short loc_14003AC0C
0x14003ac02  mov     ebx, 0C00002EBh
0x14003ac07  jmp     loc_14003ACCA
0x14003ac0c  cmp     eax, r8d
0x14003ac0f  jz      loc_14003ACCA
0x14003ac15  mov     r14d, 0C00002EBh
0x14003ac1b  cmp     eax, r14d
0x14003ac1e  jz      loc_14003ACBD
0x14003ac24  mov     rax, [rdi+18h]
0x14003ac28  xor     edx, edx
0x14003ac2a  sub     rax, r15
0x14003ac2d  add     rcx, rax
0x14003ac30  mov     qword ptr [rbp+var_40], rcx
0x14003ac34  js      short loc_14003AC3E
0x14003ac36  mov     ebx, r8d
0x14003ac39  jmp     loc_14003ACCA
0x14003ac3e  lea     rax, [rdi+38h]
0x14003ac42  mov     r10d, 2
0x14003ac48  mov     [rbp+Object], rax
0x14003ac4c  cmp     [rdi+50h], dl
0x14003ac4f  jz      short loc_14003AC6E
0x14003ac51  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003ac58  mov     rcx, [rax+0B68h]
0x14003ac5f  test    rcx, rcx
0x14003ac62  jz      short loc_14003AC6E
0x14003ac64  mov     [rbp+var_10], rcx
0x14003ac68  mov     r10d, 3
0x14003ac6e  mov     [rsp+80h+WaitBlockArray], rdx; WaitBlockArray
0x14003ac73  lea     rax, [rbp+var_40]
0x14003ac77  mov     [rsp+80h+Timeout], rax; Timeout
0x14003ac7c  xor     r9d, r9d; WaitReason
0x14003ac7f  mov     [rsp+80h+Alertable], dl; Alertable
0x14003ac83  mov     ecx, r10d; Count
0x14003ac86  mov     [rsp+80h+WaitMode], dl; WaitMode
0x14003ac8a  lea     rdx, [rbp+Object]; Object
0x14003ac8e  lea     r8d, [r9+1]; WaitType
0x14003ac92  call    cs:__imp_KeWaitForMultipleObjects
0x14003ac99  nop     dword ptr [rax+rax+00h]
0x14003ac9e  mov     ebx, eax
0x14003aca0  cmp     eax, 1
0x14003aca3  jnz     short loc_14003ACAA
0x14003aca5  mov     ebx, r14d
0x14003aca8  jmp     short loc_14003ACCA
0x14003acaa  cmp     eax, 2
0x14003acad  jnz     short loc_14003ACB6
0x14003acaf  mov     ebx, 0C013000Ch
0x14003acb4  jmp     short loc_14003ACCA
0x14003acb6  cmp     eax, 102h
0x14003acbb  jz      short loc_14003ACCA
0x14003acbd  cmp     ebx, 0C013000Ch
0x14003acc3  jz      short loc_14003ACCA
0x14003acc5  cmp     ebx, r14d
0x14003acc8  jnz     short loc_14003AD49
0x14003acca  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003acce  mov     rcx, r12; SpinLock
0x14003acd1  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003acd8  nop     dword ptr [rax+rax+00h]
0x14003acdd  mov     rcx, [rdi]
0x14003ace0  cmp     [rcx+8], rdi
0x14003ace4  jnz     loc_14003AE25
0x14003acea  mov     rax, [rdi+8]
0x14003acee  cmp     [rax], rdi
0x14003acf1  jnz     loc_14003AE25
0x14003acf7  mov     [rax], rcx
0x14003acfa  mov     [rcx+8], rax
0x14003acfe  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003ad02  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ad09  nop     dword ptr [rax+rax+00h]
0x14003ad0e  cmp     ebx, 102h
0x14003ad14  jnz     short loc_14003AD43
0x14003ad16  xor     r15d, r15d
0x14003ad19  cmp     [rdi+50h], r15b
0x14003ad1d  jz      short loc_14003AD37
0x14003ad1f  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003ad26  mov     rax, ds:0FFFFF78000000008h
0x14003ad30  mov     [rcx+0B70h], rax
0x14003ad37  mov     rax, [rsi]
0x14003ad3a  mov     dword ptr [rax+58h], 0C00000B5h
0x14003ad41  jmp     short loc_14003AD49
0x14003ad43  mov     rax, [rsi]
0x14003ad46  mov     [rax+58h], ebx
0x14003ad49  mov     rcx, r13; Event
0x14003ad4c  call    cs:__imp_KeResetEvent
0x14003ad53  nop     dword ptr [rax+rax+00h]
0x14003ad58  lea     rcx, [rdi+38h]; Event
0x14003ad5c  call    cs:__imp_KeResetEvent
0x14003ad63  nop     dword ptr [rax+rax+00h]
0x14003ad68  lea     r14, WPP_GLOBAL_Control
0x14003ad6f  mov     rax, [rsi]
0x14003ad72  mov     ebx, [rax+58h]
0x14003ad75  test    ebx, ebx
0x14003ad77  jns     short loc_14003ADA8
0x14003ad79  cmp     ebx, 80000005h
0x14003ad7f  jz      short loc_14003ADA8
0x14003ad81  cmp     ebx, 0C0000023h
0x14003ad87  jz      short loc_14003ADA8
0x14003ad89  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003ad8f  cmp     ecx, 1
0x14003ad92  jz      short loc_14003AD9F
0x14003ad94  mov     ecx, 1
0x14003ad99  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003ad9f  lea     r9, aError; "Error"
0x14003ada6  jmp     short loc_14003ADC5
0x14003ada8  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003adae  cmp     ecx, 3
0x14003adb1  jz      short loc_14003ADBE
0x14003adb3  mov     ecx, 3
0x14003adb8  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003adbe  lea     r9, aExit; "Exit "
0x14003adc5  mov     r10, cs:WPP_GLOBAL_Control
0x14003adcc  cmp     r10, r14
0x14003adcf  jz      short loc_14003ADFB
0x14003add1  mov     eax, [r10+2Ch]
0x14003add5  test    al, 1
0x14003add7  jz      short loc_14003ADFB
0x14003add9  movzx   edx, byte ptr [r10+29h]
0x14003adde  cmp     edx, ecx
0x14003ade0  jb      short loc_14003ADFB
0x14003ade2  mov     rcx, [r10+18h]
0x14003ade6  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003aded  mov     edx, 58h ; 'X'
0x14003adf2  mov     dword ptr [rsp+80h+WaitMode], ebx
0x14003adf6  call    WPP_SF_sd
0x14003adfb  mov     eax, ebx
0x14003adfd  mov     rcx, [rbp+var_8]
0x14003ae01  xor     rcx, rsp; StackCookie
0x14003ae04  call    __security_check_cookie
0x14003ae09  mov     rbx, [rsp+80h+arg_10]
0x14003ae11  add     rsp, 80h
0x14003ae18  pop     r15
0x14003ae1a  pop     r14
0x14003ae1c  pop     r13
0x14003ae1e  pop     r12
0x14003ae20  pop     rdi
0x14003ae21  pop     rsi
0x14003ae22  pop     rbp
0x14003ae23  retn
0x14003ae25  mov     ecx, 3
0x14003ae2a  int     29h; Win8: RtlFailFast(ecx)
```
