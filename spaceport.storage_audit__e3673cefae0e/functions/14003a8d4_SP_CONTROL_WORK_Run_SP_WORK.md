# SP_CONTROL_WORK::Run(SP_WORK *)

- ea: `0x14003a8d4`
- end: `0x14003ad6c`
- name: `?Run@SP_CONTROL_WORK@@QEAAJPEAVSP_WORK@@@Z`
- size: `1176`
- prototype: `__int64 __fastcall(SP_CONTROL_WORK *__hidden this, struct SP_WORK *)`
- caller_count: `8`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400aa7c4`
- `0x1400aaf54`
- `0x1400abe40`
- `0x1400ac194`
- `0x1400ac3b8`
- `0x1400ac544`
- `0x1400ac780`
- `0x1400b065c`

## callees

- `0x14002ae44`
- `0x14002ce90`
- `0x14002e43c`
- `0x14003a8d4`
- `0x140067fc0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003aa13`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ac11`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003aa13`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ac11`
- `ntoskrnl!KeResetEvent` at `0x14003ac8c`
- `ntoskrnl!KeResetEvent` at `0x14003ac9c`
- `ntoskrnl!KeResetEvent` at `0x14003ac8c`
- `ntoskrnl!KeResetEvent` at `0x14003ac9c`
- `ntoskrnl!KeReadStateEvent` at `0x14003a96b`
- `ntoskrnl!KeReadStateEvent` at `0x14003a9e6`
- `ntoskrnl!KeReadStateEvent` at `0x14003a96b`
- `ntoskrnl!KeReadStateEvent` at `0x14003a9e6`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003aac5`
- `ntoskrnl!ZwUpdateWnfStateData` at `0x14003aac5`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ab26`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003abd2`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003ab26`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x14003abd2`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003aa63`
- `ntoskrnl!IoCsqRemoveNextIrp` at `0x14003aa63`
- `ntoskrnl!IofCompleteRequest` at `0x14003aa8b`
- `ntoskrnl!IofCompleteRequest` at `0x14003aa8b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003aa9b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ac42`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003aa9b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003ac42`

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
0x14003a8d4  mov     [rsp-38h+arg_10], rbx
0x14003a8d9  push    rbp
0x14003a8da  push    rsi
0x14003a8db  push    rdi
0x14003a8dc  push    r12
0x14003a8de  push    r13
0x14003a8e0  push    r14
0x14003a8e2  push    r15
0x14003a8e4  mov     rbp, rsp
0x14003a8e7  sub     rsp, 80h
0x14003a8ee  mov     rax, cs:__security_cookie
0x14003a8f5  xor     rax, rsp
0x14003a8f8  mov     [rbp+var_8], rax
0x14003a8fc  xor     r15d, r15d
0x14003a8ff  xorps   xmm0, xmm0
0x14003a902  xor     eax, eax
0x14003a904  mov     [rbp+LockHandle.LockQueue.Next], r15
0x14003a908  mov     [rbp+var_10], rax
0x14003a90c  mov     rdi, rdx
0x14003a90f  mov     rbx, rcx
0x14003a912  mov     qword ptr [rbp+var_40], r15
0x14003a916  movups  xmmword ptr [rbp+LockHandle.LockQueue.Lock], xmm0
0x14003a91a  movups  xmmword ptr [rbp+Object], xmm0
0x14003a91e  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a925  lea     r14, WPP_GLOBAL_Control
0x14003a92c  cmp     rcx, r14
0x14003a92f  jz      short loc_14003A952
0x14003a931  mov     eax, [rcx+2Ch]
0x14003a934  test    al, 1
0x14003a936  jz      short loc_14003A952
0x14003a938  cmp     byte ptr [rcx+29h], 3
0x14003a93c  jb      short loc_14003A952
0x14003a93e  mov     rcx, [rcx+18h]
0x14003a942  lea     edx, [r15+57h]
0x14003a946  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003a94d  call    WPP_SF_
0x14003a952  cmp     [rdi+50h], r15b
0x14003a956  jz      short loc_14003A9D4
0x14003a958  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003a95f  mov     rcx, [rax+0B68h]; Event
0x14003a966  test    rcx, rcx
0x14003a969  jz      short loc_14003A98E
0x14003a96b  call    cs:__imp_KeReadStateEvent
0x14003a972  nop     dword ptr [rax+rax+00h]
0x14003a977  test    eax, eax
0x14003a979  jz      short loc_14003A98E
0x14003a97b  lea     rsi, [rdi+10h]
0x14003a97f  mov     rax, [rsi]
0x14003a982  mov     dword ptr [rax+58h], 0C013000Ch
0x14003a989  jmp     loc_14003ACAF
0x14003a98e  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003a995  mov     rcx, [rax+0B70h]
0x14003a99c  test    rcx, rcx
0x14003a99f  jz      short loc_14003A9D4
0x14003a9a1  mov     rax, ds:0FFFFF78000000008h
0x14003a9ab  sub     rax, rcx
0x14003a9ae  cmp     rax, 11E1A300h
0x14003a9b4  jl      short loc_14003A9C4
0x14003a9b6  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003a9bd  mov     [rax+0B70h], r15
0x14003a9c4  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003a9cb  cmp     [rax+0B70h], r15
0x14003a9d2  jnz     short loc_14003A97B
0x14003a9d4  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003a9db  lea     rsi, [rdi+10h]
0x14003a9df  add     rcx, 0B78h; Event
0x14003a9e6  call    cs:__imp_KeReadStateEvent
0x14003a9ed  nop     dword ptr [rax+rax+00h]
0x14003a9f2  test    eax, eax
0x14003a9f4  jz      short loc_14003AA05
0x14003a9f6  mov     rax, [rsi]
0x14003a9f9  mov     dword ptr [rax+58h], 0C00002EBh
0x14003aa00  jmp     loc_14003ACA8
0x14003aa05  lea     r12, [rbx+80h]
0x14003aa0c  mov     rcx, r12; SpinLock
0x14003aa0f  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003aa13  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003aa1a  nop     dword ptr [rax+rax+00h]
0x14003aa1f  mov     ecx, [rbx+78h]
0x14003aa22  lea     eax, [rcx+1]
0x14003aa25  mov     [rbx+78h], eax
0x14003aa28  mov     rax, [rsi]
0x14003aa2b  mov     [rax+8], ecx
0x14003aa2e  mov     rax, [rsi]
0x14003aa31  mov     dword ptr [rax+58h], 103h
0x14003aa38  mov     rax, [rsi]
0x14003aa3b  mov     [rax+5Ch], r15d
0x14003aa3f  lea     rax, [rbx+58h]
0x14003aa43  mov     rcx, [rax+8]
0x14003aa47  cmp     [rcx], rax
0x14003aa4a  jnz     loc_14003AD65
0x14003aa50  mov     [rdi+8], rcx
0x14003aa54  xor     edx, edx; PeekContext
0x14003aa56  mov     [rdi], rax
0x14003aa59  mov     [rcx], rdi
0x14003aa5c  mov     rcx, rbx; Csq
0x14003aa5f  mov     [rax+8], rdi
0x14003aa63  call    cs:__imp_IoCsqRemoveNextIrp
0x14003aa6a  nop     dword ptr [rax+rax+00h]
0x14003aa6f  mov     r14, rax
0x14003aa72  test    rax, rax
0x14003aa75  jz      short loc_14003AA97
0x14003aa77  mov     rdx, rax; struct _IRP *
0x14003aa7a  mov     rcx, rbx; this
0x14003aa7d  call    ?GetInternal@SP_CONTROL_WORK@@AEAAJPEAU_IRP@@@Z; SP_CONTROL_WORK::GetInternal(_IRP *)
0x14003aa82  xor     edx, edx; PriorityBoost
0x14003aa84  mov     [r14+30h], eax
0x14003aa88  mov     rcx, r14; Irp
0x14003aa8b  call    cs:__imp_IofCompleteRequest
0x14003aa92  nop     dword ptr [rax+rax+00h]
0x14003aa97  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003aa9b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003aaa2  nop     dword ptr [rax+rax+00h]
0x14003aaa7  mov     dword ptr [rsp+80h+Timeout], r15d
0x14003aaac  lea     rcx, WNF_SPAC_SPACEPORT_WORK_REQUESTED
0x14003aab3  mov     dword ptr [rsp+80h+Alertable], r15d
0x14003aab8  xor     r9d, r9d
0x14003aabb  xor     r8d, r8d
0x14003aabe  mov     qword ptr [rsp+80h+WaitMode], r15
0x14003aac3  xor     edx, edx
0x14003aac5  call    cs:__imp_ZwUpdateWnfStateData
0x14003aacc  nop     dword ptr [rax+rax+00h]
0x14003aad1  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003aad8  lea     r13, [rdi+20h]
0x14003aadc  xor     ecx, ecx
0x14003aade  mov     qword ptr [rbp+var_40], 0FFFFFFFFF70F2E80h
0x14003aae6  mov     [rsp+80h+WaitBlockArray], rcx; WaitBlockArray
0x14003aaeb  lea     rdx, [rbp+Object]; Object
0x14003aaef  add     rax, 0B78h
0x14003aaf5  mov     [rbp+Object], r13
0x14003aaf9  mov     [rbp+Object+8], rax
0x14003aafd  xor     r9d, r9d; WaitReason
0x14003ab00  lea     rax, [rbp+var_40]
0x14003ab04  mov     r14, 0FFFFF78000000008h
0x14003ab0e  mov     [rsp+80h+Timeout], rax; Timeout
0x14003ab13  lea     r8d, [rcx+1]; WaitType
0x14003ab17  mov     [rsp+80h+Alertable], cl; Alertable
0x14003ab1b  mov     [rsp+80h+WaitMode], cl; WaitMode
0x14003ab1f  lea     ecx, [r9+2]; Count
0x14003ab23  mov     r15, [r14]
0x14003ab26  call    cs:__imp_KeWaitForMultipleObjects
0x14003ab2d  nop     dword ptr [rax+rax+00h]
0x14003ab32  mov     rcx, [r14]
0x14003ab35  mov     r8d, 102h
0x14003ab3b  mov     ebx, eax
0x14003ab3d  cmp     eax, 1
0x14003ab40  jnz     short loc_14003AB4C
0x14003ab42  mov     ebx, 0C00002EBh
0x14003ab47  jmp     loc_14003AC0A
0x14003ab4c  cmp     eax, r8d
0x14003ab4f  jz      loc_14003AC0A
0x14003ab55  mov     r14d, 0C00002EBh
0x14003ab5b  cmp     eax, r14d
0x14003ab5e  jz      loc_14003ABFD
0x14003ab64  mov     rax, [rdi+18h]
0x14003ab68  xor     edx, edx
0x14003ab6a  sub     rax, r15
0x14003ab6d  add     rcx, rax
0x14003ab70  mov     qword ptr [rbp+var_40], rcx
0x14003ab74  js      short loc_14003AB7E
0x14003ab76  mov     ebx, r8d
0x14003ab79  jmp     loc_14003AC0A
0x14003ab7e  lea     rax, [rdi+38h]
0x14003ab82  mov     r10d, 2
0x14003ab88  mov     [rbp+Object], rax
0x14003ab8c  cmp     [rdi+50h], dl
0x14003ab8f  jz      short loc_14003ABAE
0x14003ab91  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x14003ab98  mov     rcx, [rax+0B68h]
0x14003ab9f  test    rcx, rcx
0x14003aba2  jz      short loc_14003ABAE
0x14003aba4  mov     [rbp+var_10], rcx
0x14003aba8  mov     r10d, 3
0x14003abae  mov     [rsp+80h+WaitBlockArray], rdx; WaitBlockArray
0x14003abb3  lea     rax, [rbp+var_40]
0x14003abb7  mov     [rsp+80h+Timeout], rax; Timeout
0x14003abbc  xor     r9d, r9d; WaitReason
0x14003abbf  mov     [rsp+80h+Alertable], dl; Alertable
0x14003abc3  mov     ecx, r10d; Count
0x14003abc6  mov     [rsp+80h+WaitMode], dl; WaitMode
0x14003abca  lea     rdx, [rbp+Object]; Object
0x14003abce  lea     r8d, [r9+1]; WaitType
0x14003abd2  call    cs:__imp_KeWaitForMultipleObjects
0x14003abd9  nop     dword ptr [rax+rax+00h]
0x14003abde  mov     ebx, eax
0x14003abe0  cmp     eax, 1
0x14003abe3  jnz     short loc_14003ABEA
0x14003abe5  mov     ebx, r14d
0x14003abe8  jmp     short loc_14003AC0A
0x14003abea  cmp     eax, 2
0x14003abed  jnz     short loc_14003ABF6
0x14003abef  mov     ebx, 0C013000Ch
0x14003abf4  jmp     short loc_14003AC0A
0x14003abf6  cmp     eax, 102h
0x14003abfb  jz      short loc_14003AC0A
0x14003abfd  cmp     ebx, 0C013000Ch
0x14003ac03  jz      short loc_14003AC0A
0x14003ac05  cmp     ebx, r14d
0x14003ac08  jnz     short loc_14003AC89
0x14003ac0a  lea     rdx, [rbp+LockHandle]; LockHandle
0x14003ac0e  mov     rcx, r12; SpinLock
0x14003ac11  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003ac18  nop     dword ptr [rax+rax+00h]
0x14003ac1d  mov     rcx, [rdi]
0x14003ac20  cmp     [rcx+8], rdi
0x14003ac24  jnz     loc_14003AD65
0x14003ac2a  mov     rax, [rdi+8]
0x14003ac2e  cmp     [rax], rdi
0x14003ac31  jnz     loc_14003AD65
0x14003ac37  mov     [rax], rcx
0x14003ac3a  mov     [rcx+8], rax
0x14003ac3e  lea     rcx, [rbp+LockHandle]; LockHandle
0x14003ac42  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003ac49  nop     dword ptr [rax+rax+00h]
0x14003ac4e  cmp     ebx, 102h
0x14003ac54  jnz     short loc_14003AC83
0x14003ac56  xor     r15d, r15d
0x14003ac59  cmp     [rdi+50h], r15b
0x14003ac5d  jz      short loc_14003AC77
0x14003ac5f  mov     rcx, cs:WPP_MAIN_CB.DeviceExtension
0x14003ac66  mov     rax, ds:0FFFFF78000000008h
0x14003ac70  mov     [rcx+0B70h], rax
0x14003ac77  mov     rax, [rsi]
0x14003ac7a  mov     dword ptr [rax+58h], 0C00000B5h
0x14003ac81  jmp     short loc_14003AC89
0x14003ac83  mov     rax, [rsi]
0x14003ac86  mov     [rax+58h], ebx
0x14003ac89  mov     rcx, r13; Event
0x14003ac8c  call    cs:__imp_KeResetEvent
0x14003ac93  nop     dword ptr [rax+rax+00h]
0x14003ac98  lea     rcx, [rdi+38h]; Event
0x14003ac9c  call    cs:__imp_KeResetEvent
0x14003aca3  nop     dword ptr [rax+rax+00h]
0x14003aca8  lea     r14, WPP_GLOBAL_Control
0x14003acaf  mov     rax, [rsi]
0x14003acb2  mov     ebx, [rax+58h]
0x14003acb5  test    ebx, ebx
0x14003acb7  jns     short loc_14003ACE8
0x14003acb9  cmp     ebx, 80000005h
0x14003acbf  jz      short loc_14003ACE8
0x14003acc1  cmp     ebx, 0C0000023h
0x14003acc7  jz      short loc_14003ACE8
0x14003acc9  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003accf  cmp     ecx, 1
0x14003acd2  jz      short loc_14003ACDF
0x14003acd4  mov     ecx, 1
0x14003acd9  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003acdf  lea     r9, aError; "Error"
0x14003ace6  jmp     short loc_14003AD05
0x14003ace8  mov     ecx, cs:WPP_MAIN_CB.DeviceType
0x14003acee  cmp     ecx, 3
0x14003acf1  jz      short loc_14003ACFE
0x14003acf3  mov     ecx, 3
0x14003acf8  mov     cs:WPP_MAIN_CB.DeviceType, ecx
0x14003acfe  lea     r9, aExit; "Exit "
0x14003ad05  mov     r10, cs:WPP_GLOBAL_Control
0x14003ad0c  cmp     r10, r14
0x14003ad0f  jz      short loc_14003AD3B
0x14003ad11  mov     eax, [r10+2Ch]
0x14003ad15  test    al, 1
0x14003ad17  jz      short loc_14003AD3B
0x14003ad19  movzx   edx, byte ptr [r10+29h]
0x14003ad1e  cmp     edx, ecx
0x14003ad20  jb      short loc_14003AD3B
0x14003ad22  mov     rcx, [r10+18h]
0x14003ad26  lea     r8, WPP_c4a5d22d2cc233e7d4f9a274e892dd73_Traceguids
0x14003ad2d  mov     edx, 58h ; 'X'
0x14003ad32  mov     dword ptr [rsp+80h+WaitMode], ebx
0x14003ad36  call    WPP_SF_sd
0x14003ad3b  mov     eax, ebx
0x14003ad3d  mov     rcx, [rbp+var_8]
0x14003ad41  xor     rcx, rsp; StackCookie
0x14003ad44  call    __security_check_cookie
0x14003ad49  mov     rbx, [rsp+80h+arg_10]
0x14003ad51  add     rsp, 80h
0x14003ad58  pop     r15
0x14003ad5a  pop     r14
0x14003ad5c  pop     r13
0x14003ad5e  pop     r12
0x14003ad60  pop     rdi
0x14003ad61  pop     rsi
0x14003ad62  pop     rbp
0x14003ad63  retn
0x14003ad65  mov     ecx, 3
0x14003ad6a  int     29h; Win8: RtlFailFast(ecx)
```
