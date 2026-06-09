# VhdmpiCompletionTimerExpired(_KDPC *,void *,void *,void *)

- ea: `0x140035330`
- end: `0x14003558a`
- name: `?VhdmpiCompletionTimerExpired@@YAXPEAU_KDPC@@PEAX11@Z`
- size: `602`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001e350`
- `0x140023980`
- `0x1400344ec`
- `0x140035330`
- `0x140035b8c`
- `0x140035e40`
- `0x140035fac`
- `0x140036284`

## import_xrefs

- `ntoskrnl!KeSetTimer` at `0x140035408`
- `ntoskrnl!KeSetTimer` at `0x140035408`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035481`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140035481`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400354a4`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400354a4`
- `storport!StorPortNotification` at `0x14003544e`
- `storport!StorPortNotification` at `0x14003544e`

## string_xrefs

- `0x14003536c`: `Completion Timer expired on surface %p`
- `0x140035389`: `VhdmpiCompletionTimerExpired`
- `0x1400354da`: `VhdmpiCompletionTimerExpired`
- `0x14003555e`: `VhdmpiCompletionTimerExpired`

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
  unsigned __int8 v10; // r8
  int v11; // [rsp+50h] [rbp-18h] BYREF
  char v12; // [rsp+54h] [rbp-14h]
  char v13; // [rsp+55h] [rbp-13h]
  char v14; // [rsp+56h] [rbp-12h]
  char v15; // [rsp+57h] [rbp-11h]
  unsigned int v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = 0;
  if ( (unsigned int)dword_1400876D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
    TraceEvents(
      "VhdmpiCompletionTimerExpired",
      0x1036u,
      4u,
      0x10u,
      "Completion Timer expired on surface %p",
      DeferredContext);
  v5 = *((_DWORD *)DeferredContext + 121);
  v6 = *((_DWORD *)DeferredContext + 120) == v5;
  *((_DWORD *)DeferredContext + 120) -= v5;
  if ( v6
    || (v13 = DeferredContext[32],
        v14 = DeferredContext[33],
        v15 = DeferredContext[34],
        v11 = 8,
        v12 = 0,
        !VhdmpiAddRundownRefSurfaceByAddress(&v11)) )
  {
    if ( (unsigned int)dword_1400876D0 > 3 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
      TraceEvents(
        "VhdmpiCompletionTimerExpired",
        0x108Cu,
        v10,
        0x10u,
        "Surface timeout on surface %p. Cancelling surface operation.",
        DeferredContext);
    VhdmpiCancelSurfaceDiskRequestAndRelease(DeferredContext, 3221225653LL);
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
      if ( (unsigned int)dword_1400876D0 > 4 )
      {
        if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 16) )
          TraceEvents(
            "VhdmpiCompletionTimerExpired",
            0x1082u,
            4u,
            0x10u,
            "Retry targeted scan request for (%u,%u,%u), surface %p",
            (unsigned __int8)DeferredContext[32],
            (unsigned __int8)DeferredContext[33],
            (unsigned __int8)DeferredContext[34],
            DeferredContext);
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
0x140035330  mov     [rsp+arg_0], rbx
0x140035335  mov     [rsp+arg_10], rbp
0x14003533a  push    rdi
0x14003533b  sub     rsp, 60h
0x14003533f  mov     eax, cs:dword_1400876D0
0x140035345  mov     rdi, rdx
0x140035348  mov     [rsp+68h+arg_8], 0
0x140035350  mov     ebp, 10h
0x140035355  cmp     eax, 4
0x140035358  jbe     short loc_140035395
0x14003535a  mov     edx, ebp
0x14003535c  lea     rcx, dword_1400876D0
0x140035363  call    _tlgKeywordOn
0x140035368  test    al, al
0x14003536a  jz      short loc_140035395
0x14003536c  lea     rax, aCompletionTime; "Completion Timer expired on surface %p"
0x140035373  mov     qword ptr [rsp+68h+var_40], rdi; char
0x140035378  mov     edx, 1036h; int
0x14003537d  mov     [rsp+68h+var_48], rax; char *
0x140035382  mov     r9d, ebp; int
0x140035385  lea     r8d, [rbp-0Ch]; int
0x140035389  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x140035390  call    TraceEvents
0x140035395  mov     eax, [rdi+1E4h]
0x14003539b  sub     [rdi+1E0h], eax
0x1400353a1  jz      loc_140035521
0x1400353a7  mov     al, [rdi+20h]
0x1400353aa  lea     rcx, [rsp+68h+var_18]
0x1400353af  mov     [rsp+68h+var_13], al
0x1400353b3  mov     al, [rdi+21h]
0x1400353b6  mov     [rsp+68h+var_12], al
0x1400353ba  mov     al, [rdi+22h]
0x1400353bd  mov     [rsp+68h+var_11], al
0x1400353c1  mov     [rsp+68h+var_18], 8
0x1400353c9  mov     [rsp+68h+var_14], 0
0x1400353ce  call    VhdmpiAddRundownRefSurfaceByAddress
0x1400353d3  test    rax, rax
0x1400353d6  jz      loc_140035521
0x1400353dc  mov     eax, cs:dword_14008E334
0x1400353e2  lea     r8, [rdi+1A0h]; Dpc
0x1400353e9  mov     ecx, [rdi+1E0h]
0x1400353ef  cmp     ecx, eax
0x1400353f1  cmovb   eax, ecx
0x1400353f4  lea     rcx, [rdi+160h]; Timer
0x1400353fb  imul    rdx, rax, 0FFFFFFFFFF676980h; DueTime
0x140035402  mov     [rdi+1E4h], eax
0x140035408  call    cs:__imp_KeSetTimer
0x14003540f  nop     dword ptr [rax+rax+00h]
0x140035414  mov     rdx, cs:VhdmpAdapterExtension
0x14003541b  lea     rax, [rsp+68h+arg_8]
0x140035420  mov     [rsp+68h+var_30], rax
0x140035425  lea     r9, [rdi+18h]
0x140035429  lea     rax, ?VhdmpHwStateChangeCallback@@YAXPEAX0F0K@Z; VhdmpHwStateChangeCallback(void *,void *,short,void *,ulong)
0x140035430  mov     [rsp+68h+var_38], rdi
0x140035435  mov     qword ptr [rsp+68h+var_40], rax
0x14003543a  mov     r8d, 1
0x140035440  mov     ecx, 1005h
0x140035445  mov     [rsp+68h+var_48], 0
0x14003544e  call    cs:__imp_StorPortNotification
0x140035455  nop     dword ptr [rax+rax+00h]
0x14003545a  mov     ecx, [rsp+68h+arg_8]; unsigned int
0x14003545e  call    ?VhdmpiStorportStatusToNtStatus@@YAJK@Z; VhdmpiStorportStatusToNtStatus(ulong)
0x140035463  test    eax, eax
0x140035465  jns     short loc_140035476
0x140035467  xor     edx, edx
0x140035469  mov     rcx, rdi
0x14003546c  call    VhdmpiReleaseRundownRefVirtualDiskSurface
0x140035471  jmp     loc_140035577
0x140035476  mov     rcx, cs:VhdmpAdapterExtension
0x14003547d  add     rcx, 30h ; '0'; SpinLock
0x140035481  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140035488  nop     dword ptr [rax+rax+00h]
0x14003548d  mov     rcx, rdi
0x140035490  mov     bl, al
0x140035492  call    VhdmpiMarkSurfaceAsReported
0x140035497  mov     rcx, cs:VhdmpAdapterExtension
0x14003549e  mov     dl, bl; NewIrql
0x1400354a0  add     rcx, 30h ; '0'; SpinLock
0x1400354a4  call    cs:__imp_KeReleaseSpinLock
0x1400354ab  nop     dword ptr [rax+rax+00h]
0x1400354b0  mov     eax, cs:dword_1400876D0
0x1400354b6  cmp     eax, 4
0x1400354b9  jbe     loc_140035577
0x1400354bf  mov     rdx, rbp
0x1400354c2  lea     rcx, dword_1400876D0
0x1400354c9  call    _tlgKeywordOn
0x1400354ce  test    al, al
0x1400354d0  jz      loc_140035577
0x1400354d6  movzx   eax, byte ptr [rdi+22h]
0x1400354da  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x1400354e1  movzx   edx, byte ptr [rdi+21h]
0x1400354e5  mov     r11d, 1082h
0x1400354eb  movzx   r10d, byte ptr [rdi+20h]
0x1400354f0  mov     r9d, ebp; int
0x1400354f3  mov     [rsp+68h+var_28], rdi
0x1400354f8  mov     r8d, 4; int
0x1400354fe  mov     dword ptr [rsp+68h+var_30], eax
0x140035502  lea     rax, aRetryTargetedS; "Retry targeted scan request for (%u,%u,"...
0x140035509  mov     dword ptr [rsp+68h+var_38], edx
0x14003550d  mov     edx, r11d; int
0x140035510  mov     dword ptr [rsp+68h+var_40], r10d; char
0x140035515  mov     [rsp+68h+var_48], rax; char *
0x14003551a  call    TraceEvents
0x14003551f  jmp     short loc_140035577
0x140035521  mov     eax, cs:dword_1400876D0
0x140035527  mov     r8d, 3
0x14003552d  cmp     eax, r8d
0x140035530  jbe     short loc_14003556A
0x140035532  mov     rdx, rbp
0x140035535  lea     rcx, dword_1400876D0
0x14003553c  call    _tlgKeywordOn
0x140035541  test    al, al
0x140035543  jz      short loc_14003556A
0x140035545  lea     rax, aSurfaceTimeout; "Surface timeout on surface %p. Cancelli"...
0x14003554c  mov     qword ptr [rsp+68h+var_40], rdi; char
0x140035551  mov     edx, 108Ch; int
0x140035556  mov     [rsp+68h+var_48], rax; char *
0x14003555b  mov     r9d, ebp; int
0x14003555e  lea     rcx, aVhdmpicompleti; "VhdmpiCompletionTimerExpired"
0x140035565  call    TraceEvents
0x14003556a  mov     edx, 0C00000B5h
0x14003556f  mov     rcx, rdi
0x140035572  call    VhdmpiCancelSurfaceDiskRequestAndRelease
0x140035577  lea     r11, [rsp+68h+var_8]
0x14003557c  mov     rbx, [r11+10h]
0x140035580  mov     rbp, [r11+20h]
0x140035584  mov     rsp, r11
0x140035587  pop     rdi
0x140035588  retn
```
