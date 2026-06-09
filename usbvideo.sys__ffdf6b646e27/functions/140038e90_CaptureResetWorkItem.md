# CaptureResetWorkItem

- ea: `0x140038e90`
- end: `0x14003911a`
- name: `CaptureResetWorkItem`
- size: `650`
- prototype: `__int64 __fastcall(PKSPIN Pin)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140002f64`
- `0x140008d90`
- `0x14000b34c`
- `0x14001ab4c`
- `0x14001b15c`
- `0x140038e90`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038f86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038fdc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038f86`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140038fdc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038f5b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140038f5b`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140038fa8`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x140038fa8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038fc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038ff6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003900e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038fc2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140038ff6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14003900e`
- `ntoskrnl!KeReleaseMutex` at `0x14003905a`
- `ntoskrnl!KeReleaseMutex` at `0x14003905a`
- `ks!KsPinAcquireProcessingMutex` at `0x140038ef7`
- `ks!KsPinAcquireProcessingMutex` at `0x140038ef7`
- `ks!KsDecrementCountedWorker` at `0x140039081`
- `ks!KsDecrementCountedWorker` at `0x140039081`
- `ks!KsPinReleaseProcessingMutex` at `0x140039069`
- `ks!KsPinReleaseProcessingMutex` at `0x1400390f5`
- `ks!KsPinReleaseProcessingMutex` at `0x140039069`
- `ks!KsPinReleaseProcessingMutex` at `0x1400390f5`

## pseudocode

```c
void __fastcall CaptureResetWorkItem(PKSPIN Pin)
{
  _QWORD *Context; // rbx
  PKSPIN v2; // rdi
  __int64 v3; // rsi
  int v4; // eax
  int v5; // r15d
  KIRQL v6; // al
  KIRQL v7; // r14
  PLIST_ENTRY v8; // r12
  int v10; // [rsp+78h] [rbp+10h] BYREF

  Context = Pin->Context;
  v2 = Pin;
  v3 = Context[12];
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, Context, Pin->Id);
  do
  {
    KsPinAcquireProcessingMutex(v2);
    if ( !*((_BYTE *)Context + 384) )
      goto LABEL_25;
    if ( (int)USBVideoCallUSBD(*(_QWORD *)(*Context + 24LL), 0, 0x220013u, (ULONG_PTR)&v10) < 0 || (v10 & 2) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, Context);
LABEL_25:
      KsPinReleaseProcessingMutex(v2);
      return;
    }
    *(_DWORD *)(v3 + 8) = 1;
    KeWaitForSingleObject((PVOID)(v3 + 248), Executive, 0, 0, 0);
    v4 = AbortUSBPipe(Context, 1);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, Context, v4);
    }
    else
    {
      v6 = KeAcquireSpinLockRaiseToDpc(Context + 15);
      v7 = v6;
      if ( *(_DWORD *)v3 )
      {
        do
        {
          v8 = ExInterlockedRemoveHeadList((PLIST_ENTRY)(v3 + 168), (PKSPIN_LOCK)(v3 + 184));
          if ( !v8 )
            break;
          KeReleaseSpinLock(Context + 15, v7);
          v5 = CaptureReQueueUrb(v8);
          v7 = KeAcquireSpinLockRaiseToDpc(Context + 15);
        }
        while ( v5 >= 0 );
        KeReleaseSpinLock(Context + 15, v7);
        v2 = Pin;
      }
      else
      {
        KeReleaseSpinLock(Context + 15, v6);
      }
    }
    KeReleaseMutex((PRKMUTEX)(v3 + 248), 0);
    KsPinReleaseProcessingMutex(v2);
  }
  while ( v5 >= 0 && KsDecrementCountedWorker(*(PKSWORKER *)(v3 + 208)) );
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids, Context, v2->Id);
}

```

## disassembly

```asm
0x140038e90  mov     [rsp+arg_10], rbx
0x140038e95  mov     [rsp+Pin], rcx
0x140038e9a  push    rbp
0x140038e9b  push    rsi
0x140038e9c  push    rdi
0x140038e9d  push    r12
0x140038e9f  push    r13
0x140038ea1  push    r14
0x140038ea3  push    r15
0x140038ea5  sub     rsp, 30h
0x140038ea9  mov     rbx, [rcx+10h]
0x140038ead  mov     rdi, rcx
0x140038eb0  mov     rsi, [rbx+60h]
0x140038eb4  mov     [rsp+68h+arg_8], 0
0x140038ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x140038ec3  lea     rbp, WPP_GLOBAL_Control
0x140038eca  cmp     rcx, rbp
0x140038ecd  jz      short loc_140038EF4
0x140038ecf  cmp     byte ptr [rcx+29h], 4
0x140038ed3  jb      short loc_140038EF4
0x140038ed5  mov     eax, [rdi+18h]
0x140038ed8  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140038edf  mov     rcx, [rcx+18h]
0x140038ee3  mov     edx, 0Ah
0x140038ee8  mov     r9, rbx
0x140038eeb  mov     dword ptr [rsp+68h+Timeout], eax
0x140038eef  call    WPP_SF_qD
0x140038ef4  mov     rcx, rdi; Pin
0x140038ef7  call    cs:__imp_KsPinAcquireProcessingMutex
0x140038efe  nop     dword ptr [rax+rax+00h]
0x140038f03  cmp     byte ptr [rbx+180h], 0
0x140038f0a  jz      loc_1400390F2
0x140038f10  mov     rcx, [rbx]
0x140038f13  lea     r9, [rsp+68h+arg_8]
0x140038f18  xor     edx, edx
0x140038f1a  mov     r8d, 220013h
0x140038f20  mov     rcx, [rcx+18h]
0x140038f24  call    USBVideoCallUSBD
0x140038f29  test    eax, eax
0x140038f2b  js      loc_1400390C8
0x140038f31  test    byte ptr [rsp+68h+arg_8], 2
0x140038f36  jz      loc_1400390C8
0x140038f3c  lea     rcx, [rsi+0F8h]; Object
0x140038f43  mov     dword ptr [rsi+8], 1
0x140038f4a  xor     r9d, r9d; Alertable
0x140038f4d  mov     [rsp+68h+Timeout], 0; Timeout
0x140038f56  xor     r8d, r8d; WaitMode
0x140038f59  xor     edx, edx; WaitReason
0x140038f5b  call    cs:__imp_KeWaitForSingleObject
0x140038f62  nop     dword ptr [rax+rax+00h]
0x140038f67  mov     edx, 1
0x140038f6c  mov     rcx, rbx
0x140038f6f  call    AbortUSBPipe
0x140038f74  mov     r15d, eax
0x140038f77  test    eax, eax
0x140038f79  js      loc_140039023
0x140038f7f  lea     rbp, [rbx+78h]
0x140038f83  mov     rcx, rbp; SpinLock
0x140038f86  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140038f8d  nop     dword ptr [rax+rax+00h]
0x140038f92  cmp     dword ptr [rsi], 0
0x140038f95  mov     r14b, al
0x140038f98  jz      short loc_140039009
0x140038f9a  lea     rdx, [rsi+0B8h]; Lock
0x140038fa1  lea     rcx, [rsi+0A8h]; ListHead
0x140038fa8  call    cs:__imp_ExInterlockedRemoveHeadList
0x140038faf  nop     dword ptr [rax+rax+00h]
0x140038fb4  mov     r12, rax
0x140038fb7  test    rax, rax
0x140038fba  jz      short loc_140038FF0
0x140038fbc  mov     dl, r14b; NewIrql
0x140038fbf  mov     rcx, rbp; SpinLock
0x140038fc2  call    cs:__imp_KeReleaseSpinLock
0x140038fc9  nop     dword ptr [rax+rax+00h]
0x140038fce  mov     rcx, r12
0x140038fd1  call    CaptureReQueueUrb
0x140038fd6  mov     rcx, rbp; SpinLock
0x140038fd9  mov     r15d, eax
0x140038fdc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140038fe3  nop     dword ptr [rax+rax+00h]
0x140038fe8  mov     r14b, al
0x140038feb  test    r15d, r15d
0x140038fee  jns     short loc_140038F9A
0x140038ff0  mov     dl, r14b; NewIrql
0x140038ff3  mov     rcx, rbp; SpinLock
0x140038ff6  call    cs:__imp_KeReleaseSpinLock
0x140038ffd  nop     dword ptr [rax+rax+00h]
0x140039002  mov     rdi, [rsp+68h+Pin]
0x140039007  jmp     short loc_14003901A
0x140039009  mov     dl, al; NewIrql
0x14003900b  mov     rcx, rbp; SpinLock
0x14003900e  call    cs:__imp_KeReleaseSpinLock
0x140039015  nop     dword ptr [rax+rax+00h]
0x14003901a  lea     rbp, WPP_GLOBAL_Control
0x140039021  jmp     short loc_140039051
0x140039023  mov     rcx, cs:WPP_GLOBAL_Control
0x14003902a  cmp     rcx, rbp
0x14003902d  jz      short loc_140039051
0x14003902f  cmp     byte ptr [rcx+29h], 2
0x140039033  jb      short loc_140039051
0x140039035  mov     rcx, [rcx+18h]
0x140039039  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x140039040  mov     edx, 0Ch
0x140039045  mov     dword ptr [rsp+68h+Timeout], eax
0x140039049  mov     r9, rbx
0x14003904c  call    WPP_SF_qD
0x140039051  xor     edx, edx; Wait
0x140039053  lea     rcx, [rsi+0F8h]; Mutex
0x14003905a  call    cs:__imp_KeReleaseMutex
0x140039061  nop     dword ptr [rax+rax+00h]
0x140039066  mov     rcx, rdi; Pin
0x140039069  call    cs:__imp_KsPinReleaseProcessingMutex
0x140039070  nop     dword ptr [rax+rax+00h]
0x140039075  test    r15d, r15d
0x140039078  js      short loc_140039095
0x14003907a  mov     rcx, [rsi+0D0h]; Worker
0x140039081  call    cs:__imp_KsDecrementCountedWorker
0x140039088  nop     dword ptr [rax+rax+00h]
0x14003908d  test    eax, eax
0x14003908f  jnz     loc_140038EF4
0x140039095  mov     rcx, cs:WPP_GLOBAL_Control
0x14003909c  cmp     rcx, rbp
0x14003909f  jz      short loc_140039101
0x1400390a1  cmp     byte ptr [rcx+29h], 4
0x1400390a5  jb      short loc_140039101
0x1400390a7  mov     eax, [rdi+18h]
0x1400390aa  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400390b1  mov     rcx, [rcx+18h]
0x1400390b5  mov     edx, 0Dh
0x1400390ba  mov     r9, rbx
0x1400390bd  mov     dword ptr [rsp+68h+Timeout], eax
0x1400390c1  call    WPP_SF_qD
0x1400390c6  jmp     short loc_140039101
0x1400390c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400390cf  cmp     rcx, rbp
0x1400390d2  jz      short loc_1400390F2
0x1400390d4  cmp     byte ptr [rcx+29h], 3
0x1400390d8  jb      short loc_1400390F2
0x1400390da  mov     rcx, [rcx+18h]
0x1400390de  lea     r8, WPP_68563f4d4e9e3aac33108af67ea17a41_Traceguids
0x1400390e5  mov     edx, 0Bh
0x1400390ea  mov     r9, rbx
0x1400390ed  call    WPP_SF_q
0x1400390f2  mov     rcx, rdi; Pin
0x1400390f5  call    cs:__imp_KsPinReleaseProcessingMutex
0x1400390fc  nop     dword ptr [rax+rax+00h]
0x140039101  mov     rbx, [rsp+68h+arg_10]
0x140039109  add     rsp, 30h
0x14003910d  pop     r15
0x14003910f  pop     r14
0x140039111  pop     r13
0x140039113  pop     r12
0x140039115  pop     rdi
0x140039116  pop     rsi
0x140039117  pop     rbp
0x140039118  retn
```
