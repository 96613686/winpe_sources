# VhdmpiAllocateSurface(_VHD_SURFACE * *)

- ea: `0x1400b9b24`
- end: `0x1400b9cdb`
- name: `?VhdmpiAllocateSurface@@YAJPEAPEAU_VHD_SURFACE@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _VHD_SURFACE **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b9ce4`

## callees

- `0x1400210e0`
- `0x140023980`
- `0x140026e20`
- `0x140036284`
- `0x1400b9b24`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9bab`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9c4e`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9bab`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9c4e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b9c5d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b9c5d`
- `ntoskrnl!ExRundownCompleted` at `0x1400b9c6c`
- `ntoskrnl!ExRundownCompleted` at `0x1400b9c6c`
- `ntoskrnl!KeInitializeTimer` at `0x1400b9bd6`
- `ntoskrnl!KeInitializeTimer` at `0x1400b9bd6`
- `ntoskrnl!KeInitializeDpc` at `0x1400b9bf3`
- `ntoskrnl!KeInitializeDpc` at `0x1400b9bf3`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9b48`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9b48`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9bc3`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c08`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c20`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9bc3`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c08`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c20`

## pseudocode

```c
__int64 __fastcall VhdmpiAllocateSurface(struct _EX_RUNDOWN_REF **a1)
{
  struct _EX_RUNDOWN_REF *Pool2; // rax
  struct _EX_RUNDOWN_REF *v3; // rdi
  unsigned __int8 v4; // r8
  __int64 result; // rax

  Pool2 = (struct _EX_RUNDOWN_REF *)ExAllocatePool2(64, 1600, 1967409238);
  v3 = Pool2;
  if ( Pool2 )
  {
    ExInitializeRundownProtection(Pool2 + 10);
    KeInitializeEvent((PRKEVENT)&v3[41], NotificationEvent, 0);
    KeInitializeTimer((PKTIMER)&v3[44]);
    KeInitializeDpc((PRKDPC)&v3[52], VhdmpiCompletionTimerExpired, v3);
    KeInitializeEvent((PRKEVENT)&v3[13], NotificationEvent, 0);
    KeInitializeEvent((PRKEVENT)&v3[16], NotificationEvent, 0);
    VhdmpiInitializePassiveLock(&v3[35]);
    VhdmpiInitializePassiveLock(&v3[38]);
    ExInitializeRundownProtection(v3 + 194);
    ExWaitForRundownProtectionRelease(v3 + 194);
    ExRundownCompleted(v3 + 194);
    VhdmpiInitializePassiveLock(&v3[192]);
    LODWORD(v3[77].Count) = 1;
    v3[75].Count = (ULONG_PTR)VhdmpiSrbExtensionWorkerRoutine;
    v3[76].Count = (ULONG_PTR)&v3[73];
    v3[73].Count = 0;
    DvInitializeWorkQueue(&v3[72]);
    result = 0;
    LODWORD(v3[63].Count) = 259;
    HIDWORD(v3[62].Ptr) = 3;
    *a1 = v3;
  }
  else
  {
    if ( (unsigned int)dword_1400876D0 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 64) )
        TraceEvents(
          "VhdmpiAllocateSurface",
          0xA37u,
          v4,
          0x40u,
          "VhdmpiSurfaceVirtualDisk: failed to alloc surface structure");
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400b9b24  mov     [rsp+arg_0], rbx
0x1400b9b29  mov     [rsp+arg_8], rsi
0x1400b9b2e  push    rdi
0x1400b9b2f  sub     rsp, 30h
0x1400b9b33  mov     rsi, rcx
0x1400b9b36  mov     ebx, 40h ; '@'
0x1400b9b3b  mov     ecx, ebx
0x1400b9b3d  mov     edx, 640h
0x1400b9b42  mov     r8d, 75444856h
0x1400b9b48  call    cs:__imp_ExAllocatePool2
0x1400b9b4f  nop     dword ptr [rax+rax+00h]
0x1400b9b54  mov     rdi, rax
0x1400b9b57  test    rax, rax
0x1400b9b5a  jnz     short loc_1400B9BA7
0x1400b9b5c  mov     eax, cs:dword_1400876D0
0x1400b9b62  lea     r8d, [rbx-3Eh]
0x1400b9b66  cmp     eax, r8d
0x1400b9b69  jbe     short loc_1400B9B9D
0x1400b9b6b  mov     edx, ebx
0x1400b9b6d  lea     rcx, dword_1400876D0
0x1400b9b74  call    _tlgKeywordOn
0x1400b9b79  test    al, al
0x1400b9b7b  jz      short loc_1400B9B9D
0x1400b9b7d  lea     rax, aVhdmpisurfacev_4; "VhdmpiSurfaceVirtualDisk: failed to all"...
0x1400b9b84  mov     edx, 0A37h; int
0x1400b9b89  mov     r9d, ebx; int
0x1400b9b8c  mov     [rsp+38h+var_18], rax; char *
0x1400b9b91  lea     rcx, aVhdmpiallocate_2; "VhdmpiAllocateSurface"
0x1400b9b98  call    TraceEvents
0x1400b9b9d  mov     eax, 0C000009Ah
0x1400b9ba2  jmp     loc_1400B9CCA
0x1400b9ba7  lea     rcx, [rax+50h]; RunRef
0x1400b9bab  call    cs:__imp_ExInitializeRundownProtection
0x1400b9bb2  nop     dword ptr [rax+rax+00h]
0x1400b9bb7  lea     rcx, [rdi+148h]; Event
0x1400b9bbe  xor     r8d, r8d; State
0x1400b9bc1  xor     edx, edx; Type
0x1400b9bc3  call    cs:__imp_KeInitializeEvent
0x1400b9bca  nop     dword ptr [rax+rax+00h]
0x1400b9bcf  lea     rcx, [rdi+160h]; Timer
0x1400b9bd6  call    cs:__imp_KeInitializeTimer
0x1400b9bdd  nop     dword ptr [rax+rax+00h]
0x1400b9be2  lea     rcx, [rdi+1A0h]; Dpc
0x1400b9be9  mov     r8, rdi; DeferredContext
0x1400b9bec  lea     rdx, ?VhdmpiCompletionTimerExpired@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x1400b9bf3  call    cs:__imp_KeInitializeDpc
0x1400b9bfa  nop     dword ptr [rax+rax+00h]
0x1400b9bff  lea     rcx, [rdi+68h]; Event
0x1400b9c03  xor     r8d, r8d; State
0x1400b9c06  xor     edx, edx; Type
0x1400b9c08  call    cs:__imp_KeInitializeEvent
0x1400b9c0f  nop     dword ptr [rax+rax+00h]
0x1400b9c14  lea     rcx, [rdi+80h]; Event
0x1400b9c1b  xor     r8d, r8d; State
0x1400b9c1e  xor     edx, edx; Type
0x1400b9c20  call    cs:__imp_KeInitializeEvent
0x1400b9c27  nop     dword ptr [rax+rax+00h]
0x1400b9c2c  lea     rcx, [rdi+118h]
0x1400b9c33  call    VhdmpiInitializePassiveLock
0x1400b9c38  lea     rcx, [rdi+130h]
0x1400b9c3f  call    VhdmpiInitializePassiveLock
0x1400b9c44  lea     rbx, [rdi+610h]
0x1400b9c4b  mov     rcx, rbx; RunRef
0x1400b9c4e  call    cs:__imp_ExInitializeRundownProtection
0x1400b9c55  nop     dword ptr [rax+rax+00h]
0x1400b9c5a  mov     rcx, rbx; RunRef
0x1400b9c5d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400b9c64  nop     dword ptr [rax+rax+00h]
0x1400b9c69  mov     rcx, rbx; RunRef
0x1400b9c6c  call    cs:__imp_ExRundownCompleted
0x1400b9c73  nop     dword ptr [rax+rax+00h]
0x1400b9c78  lea     rcx, [rdi+600h]
0x1400b9c7f  call    VhdmpiInitializePassiveLock
0x1400b9c84  lea     rcx, [rdi+240h]
0x1400b9c8b  lea     rax, [rcx+8]
0x1400b9c8f  lea     rdx, ?VhdmpiSrbExtensionWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiSrbExtensionWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x1400b9c96  mov     dword ptr [rax+20h], 1
0x1400b9c9d  mov     [rax+10h], rdx
0x1400b9ca1  mov     [rax+18h], rax
0x1400b9ca5  mov     qword ptr [rax], 0
0x1400b9cac  call    DvInitializeWorkQueue
0x1400b9cb1  xor     eax, eax
0x1400b9cb3  mov     dword ptr [rdi+1F8h], 103h
0x1400b9cbd  mov     dword ptr [rdi+1F4h], 3
0x1400b9cc7  mov     [rsi], rdi
0x1400b9cca  mov     rbx, [rsp+38h+arg_0]
0x1400b9ccf  mov     rsi, [rsp+38h+arg_8]
0x1400b9cd4  add     rsp, 30h
0x1400b9cd8  pop     rdi
0x1400b9cd9  retn
```
