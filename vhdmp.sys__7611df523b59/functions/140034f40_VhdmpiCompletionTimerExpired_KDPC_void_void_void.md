# VhdmpiCompletionTimerExpired(_KDPC *,void *,void *,void *)

- ea: `0x140034f40`
- end: `0x14003519a`
- name: `?VhdmpiCompletionTimerExpired@@YAXPEAU_KDPC@@PEAX11@Z`
- size: `602`
- prototype: `void __fastcall(struct _KDPC *Dpc, char *DeferredContext, PVOID SystemArgument1, PVOID SystemArgument2)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001df30`
- `0x140023560`
- `0x14003402c`
- `0x140034f40`
- `0x14003579c`
- `0x140035a50`
- `0x140035bbc`
- `0x140035e94`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140035018`
- `ntoskrnl!KeSetTimer` at `0x140035018`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035091`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035091`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400350b4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400350b4`
- `storport!StorPortNotification` at `0x14003505e`
- `storport!StorPortNotification` at `0x14003505e`

## string_xrefs

- `0x140034f7c`: `Completion Timer expired on surface %p`
- `0x140034f99`: `VhdmpiCompletionTimerExpired`
- `0x1400350ea`: `VhdmpiCompletionTimerExpired`
- `0x14003516e`: `VhdmpiCompletionTimerExpired`

## pseudocode

```c
void __fastcall VhdmpiCompletionTimerExpired(
        struct _KDPC *Dpc,
        char *DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  int v5; // eax
  bool v6; // zf
  __int64 v7; // rax
  unsigned int v8; // ecx
  KIRQL v9; // bl
  __int64 v10; // r8
  int v11; // [rsp+50h] [rbp-18h] BYREF
  char v12; // [rsp+54h] [rbp-14h]
  char v13; // [rsp+55h] [rbp-13h]
  char v14; // [rsp+56h] [rbp-12h]
  char v15; // [rsp+57h] [rbp-11h]
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = 0;
  if ( (unsigned int)dword_140087708 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
    TraceEvents(
      (int)"VhdmpiCompletionTimerExpired",
      4150,
      4,
      16,
      "Completion Timer expired on surface %p",
      (char)DeferredContext);
  v5 = *((_DWORD *)DeferredContext + 121);
  v6 = *((_DWORD *)DeferredContext + 120) == v5;
  *((_DWORD *)DeferredContext + 120) -= v5;
  if ( v6
    || (v13 = DeferredContext[32],
        v14 = DeferredContext[33],
        v15 = DeferredContext[34],
        v11 = 8,
        v12 = 0,
        !VhdmpiAddRundownRefSurfaceByAddress(&v11, DeferredContext, SystemArgument1, SystemArgument2)) )
  {
    v10 = 3;
    if ( (unsigned int)dword_140087708 > 3 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
      TraceEvents(
        (int)"VhdmpiCompletionTimerExpired",
        4236,
        v10,
        16,
        "Surface timeout on surface %p. Cancelling surface operation.",
        (char)DeferredContext);
    VhdmpiCancelSurfaceDiskRequestAndRelease(DeferredContext, 3221225653LL, v10, SystemArgument2);
  }
  else
  {
    v7 = (unsigned int)dword_14008E334;
    v8 = *((_DWORD *)DeferredContext + 120);
    if ( v8 < dword_14008E334 )
      v7 = v8;
    *((_DWORD *)DeferredContext + 121) = v7;
    KeSetTimer((PKTIMER)(DeferredContext + 352), (LARGE_INTEGER)(-10000000 * v7), (PKDPC)(DeferredContext + 416));
    StorPortNotification(
      4101,
      VhdmpAdapterExtension,
      1,
      DeferredContext + 24,
      0,
      VhdmpHwStateChangeCallback,
      DeferredContext,
      &v16);
    if ( (int)VhdmpiStorportStatusToNtStatus(v16) >= 0 )
    {
      v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)VhdmpAdapterExtension + 6);
      VhdmpiMarkSurfaceAsReported(DeferredContext);
      KeReleaseSpinLock((PKSPIN_LOCK)VhdmpAdapterExtension + 6, v9);
      if ( (unsigned int)dword_140087708 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 16) )
          TraceEvents(
            (int)"VhdmpiCompletionTimerExpired",
            4226,
            4,
            16,
            "Retry targeted scan request for (%u,%u,%u), surface %p",
            DeferredContext[32]);
      }
    }
    else
    {
      VhdmpiReleaseRundownRefVirtualDiskSurface(DeferredContext, 0);
    }
  }
}

```

## disassembly

```asm
0x140034f40  mov     [rsp+arg_0], rbx
0x140034f45  mov     [rsp+arg_10], rbp
0x140034f4a  push    rdi
0x140034f4b  sub     rsp, 60h
0x140034f4f  mov     eax, cs:dword_140087708
0x140034f55  mov     rdi, rdx
0x140034f58  mov     [rsp+68h+arg_8], 0
0x140034f60  mov     ebp, 10h
0x140034f65  cmp     eax, 4
0x140034f68  jbe     short loc_140034FA5
0x140034f6a  mov     edx, ebp
0x140034f6c  lea     rcx, dword_140087708
0x140034f73  call    _tlgKeywordOn
0x140034f78  test    al, al
0x140034f7a  jz      short loc_140034FA5
0x140034f7c  lea     rax, aCompletionTime; "Completion Timer expired on surface %p"
0x140034f83  mov     qword ptr [rsp+68h+var_40], rdi; char
0x140034f88  mov     edx, 1036h; int
0x140034f8d  mov     [rsp+68h+var_48], rax; char *
0x140034f92  mov     r9d, ebp; int
0x140034f95  lea     r8d, [rbp-0Ch]; int
0x140034f99  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x140034fa0  call    TraceEvents
0x140034fa5  mov     eax, [rdi+1E4h]
0x140034fab  sub     [rdi+1E0h], eax
0x140034fb1  jz      loc_140035131
0x140034fb7  mov     al, [rdi+20h]
0x140034fba  lea     rcx, [rsp+68h+var_18]
0x140034fbf  mov     [rsp+68h+var_13], al
0x140034fc3  mov     al, [rdi+21h]
0x140034fc6  mov     [rsp+68h+var_12], al
0x140034fca  mov     al, [rdi+22h]
0x140034fcd  mov     [rsp+68h+var_11], al
0x140034fd1  mov     [rsp+68h+var_18], 8
0x140034fd9  mov     [rsp+68h+var_14], 0
0x140034fde  call    VhdmpiAddRundownRefSurfaceByAddress
0x140034fe3  test    rax, rax
0x140034fe6  jz      loc_140035131
0x140034fec  mov     eax, cs:dword_14008E334
0x140034ff2  lea     r8, [rdi+1A0h]; Dpc
0x140034ff9  mov     ecx, [rdi+1E0h]
0x140034fff  cmp     ecx, eax
0x140035001  cmovb   eax, ecx
0x140035004  lea     rcx, [rdi+160h]; Timer
0x14003500b  imul    rdx, rax, 0FFFFFFFFFF676980h; DueTime
0x140035012  mov     [rdi+1E4h], eax
0x140035018  call    cs:__imp_KeSetTimer
0x14003501f  nop     dword ptr [rax+rax+00h]
0x140035024  mov     rdx, cs:VhdmpAdapterExtension
0x14003502b  lea     rax, [rsp+68h+arg_8]
0x140035030  mov     [rsp+68h+var_30], rax
0x140035035  lea     r9, [rdi+18h]
0x140035039  lea     rax, ?VhdmpHwStateChangeCallback@@YAXPEAX0F0K@Z; VhdmpHwStateChangeCallback(void *,void *,short,void *,ulong)
0x140035040  mov     [rsp+68h+var_38], rdi
0x140035045  mov     qword ptr [rsp+68h+var_40], rax
0x14003504a  mov     r8d, 1
0x140035050  mov     ecx, 1005h
0x140035055  mov     [rsp+68h+var_48], 0
0x14003505e  call    cs:__imp_StorPortNotification
0x140035065  nop     dword ptr [rax+rax+00h]
0x14003506a  mov     ecx, [rsp+68h+arg_8]; unsigned int
0x14003506e  call    ?VhdmpiStorportStatusToNtStatus@@YAJK@Z; VhdmpiStorportStatusToNtStatus(ulong)
0x140035073  test    eax, eax
0x140035075  jns     short loc_140035086
0x140035077  xor     edx, edx
0x140035079  mov     rcx, rdi
0x14003507c  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x140035081  jmp     loc_140035187
0x140035086  mov     rcx, cs:VhdmpAdapterExtension
0x14003508d  add     rcx, 30h ; '0'; SpinLock
0x140035091  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035098  nop     dword ptr [rax+rax+00h]
0x14003509d  mov     rcx, rdi
0x1400350a0  mov     bl, al
0x1400350a2  call    VhdmpiMarkSurfaceAsReported
0x1400350a7  mov     rcx, cs:VhdmpAdapterExtension
0x1400350ae  mov     dl, bl; NewIrql
0x1400350b0  add     rcx, 30h ; '0'; SpinLock
0x1400350b4  call    cs:__imp_KeReleaseSpinLock
0x1400350bb  nop     dword ptr [rax+rax+00h]
0x1400350c0  mov     eax, cs:dword_140087708
0x1400350c6  cmp     eax, 4
0x1400350c9  jbe     loc_140035187
0x1400350cf  mov     rdx, rbp
0x1400350d2  lea     rcx, dword_140087708
0x1400350d9  call    _tlgKeywordOn
0x1400350de  test    al, al
0x1400350e0  jz      loc_140035187
0x1400350e6  movzx   eax, byte ptr [rdi+22h]
0x1400350ea  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x1400350f1  movzx   edx, byte ptr [rdi+21h]
0x1400350f5  mov     r11d, 1082h
0x1400350fb  movzx   r10d, byte ptr [rdi+20h]
0x140035100  mov     r9d, ebp; int
0x140035103  mov     [rsp+68h+var_28], rdi
0x140035108  mov     r8d, 4; int
0x14003510e  mov     dword ptr [rsp+68h+var_30], eax
0x140035112  lea     rax, aRetryTargetedS; "Retry targeted scan request for (%u,%u,"...
0x140035119  mov     dword ptr [rsp+68h+var_38], edx
0x14003511d  mov     edx, r11d; int
0x140035120  mov     dword ptr [rsp+68h+var_40], r10d; char
0x140035125  mov     [rsp+68h+var_48], rax; char *
0x14003512a  call    TraceEvents
0x14003512f  jmp     short loc_140035187
0x140035131  mov     eax, cs:dword_140087708
0x140035137  mov     r8d, 3
0x14003513d  cmp     eax, r8d
0x140035140  jbe     short loc_14003517A
0x140035142  mov     rdx, rbp
0x140035145  lea     rcx, dword_140087708
0x14003514c  call    _tlgKeywordOn
0x140035151  test    al, al
0x140035153  jz      short loc_14003517A
0x140035155  lea     rax, aSurfaceTimeout; "Surface timeout on surface %p. Cancelli"...
0x14003515c  mov     qword ptr [rsp+68h+var_40], rdi; char
0x140035161  mov     edx, 108Ch; int
0x140035166  mov     [rsp+68h+var_48], rax; char *
0x14003516b  mov     r9d, ebp; int
0x14003516e  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x140035175  call    TraceEvents
0x14003517a  mov     edx, 0C00000B5h
0x14003517f  mov     rcx, rdi
0x140035182  call    VhdmpiCancelSurfaceDiskRequestAndRelease
0x140035187  lea     r11, [rsp+68h+var_8]
0x14003518c  mov     rbx, [r11+10h]
0x140035190  mov     rbp, [r11+20h]
0x140035194  mov     rsp, r11
0x140035197  pop     rdi
0x140035198  retn
```
