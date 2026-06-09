# VhdmpiAllocateSurface(_VHD_SURFACE * *)

- ea: `0x1400b9b34`
- end: `0x1400b9ceb`
- name: `?VhdmpiAllocateSurface@@YAJPEAPEAU_VHD_SURFACE@@@Z`
- size: `439`
- prototype: `__int64 __fastcall(struct _EX_RUNDOWN_REF **)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400b9cf4`

## callees

- `0x140020cc0`
- `0x140023560`
- `0x140026a00`
- `0x140035e94`
- `0x1400b9b34`

## import_xrefs

- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9bbb`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9c5e`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9bbb`
- `ntoskrnl!ExInitializeRundownProtection` at `0x1400b9c5e`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b9c6d`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x1400b9c6d`
- `ntoskrnl!ExRundownCompleted` at `0x1400b9c7c`
- `ntoskrnl!ExRundownCompleted` at `0x1400b9c7c`
- `ntoskrnl!KeInitializeTimer` at `0x1400b9be6`
- `ntoskrnl!KeInitializeTimer` at `0x1400b9be6`
- `ntoskrnl!KeInitializeDpc` at `0x1400b9c03`
- `ntoskrnl!KeInitializeDpc` at `0x1400b9c03`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9b58`
- `ntoskrnl!ExAllocatePool2` at `0x1400b9b58`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9bd3`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c18`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c30`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9bd3`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c18`
- `ntoskrnl!KeInitializeEvent` at `0x1400b9c30`

## pseudocode

```c
__int64 __fastcall VhdmpiAllocateSurface(struct _EX_RUNDOWN_REF **a1)
{
  struct _EX_RUNDOWN_REF *Pool2; // rax
  struct _EX_RUNDOWN_REF *v3; // rdi
  int v4; // r8d
  __int64 result; // rax
  char v6; // [rsp+28h] [rbp-10h]

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
    if ( (unsigned int)dword_140087708 > 2 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_140087708, 64) )
        TraceEvents(
          (int)"VhdmpiAllocateSurface",
          2615,
          v4,
          64,
          "VhdmpiSurfaceVirtualDisk: failed to alloc surface structure",
          v6);
    }
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x1400b9b34  mov     [rsp+arg_0], rbx
0x1400b9b39  mov     [rsp+arg_8], rsi
0x1400b9b3e  push    rdi
0x1400b9b3f  sub     rsp, 30h
0x1400b9b43  mov     rsi, rcx
0x1400b9b46  mov     ebx, 40h ; '@'
0x1400b9b4b  mov     ecx, ebx
0x1400b9b4d  mov     edx, 640h
0x1400b9b52  mov     r8d, 75444856h
0x1400b9b58  call    cs:__imp_ExAllocatePool2
0x1400b9b5f  nop     dword ptr [rax+rax+00h]
0x1400b9b64  mov     rdi, rax
0x1400b9b67  test    rax, rax
0x1400b9b6a  jnz     short loc_1400B9BB7
0x1400b9b6c  mov     eax, cs:dword_140087708
0x1400b9b72  lea     r8d, [rbx-3Eh]
0x1400b9b76  cmp     eax, r8d
0x1400b9b79  jbe     short loc_1400B9BAD
0x1400b9b7b  mov     edx, ebx
0x1400b9b7d  lea     rcx, dword_140087708
0x1400b9b84  call    _tlgKeywordOn
0x1400b9b89  test    al, al
0x1400b9b8b  jz      short loc_1400B9BAD
0x1400b9b8d  lea     rax, aVhdmpisurfacev_4; "VhdmpiSurfaceVirtualDisk: failed to all"...
0x1400b9b94  mov     edx, 0A37h; int
0x1400b9b99  mov     r9d, ebx; int
0x1400b9b9c  mov     [rsp+38h+var_18], rax; char *
0x1400b9ba1  lea     rcx, aVhdmpiallocate_2; "VhdmpiAllocateSurface"
0x1400b9ba8  call    TraceEvents
0x1400b9bad  mov     eax, 0C000009Ah
0x1400b9bb2  jmp     loc_1400B9CDA
0x1400b9bb7  lea     rcx, [rax+50h]; RunRef
0x1400b9bbb  call    cs:__imp_ExInitializeRundownProtection
0x1400b9bc2  nop     dword ptr [rax+rax+00h]
0x1400b9bc7  lea     rcx, [rdi+148h]; Event
0x1400b9bce  xor     r8d, r8d; State
0x1400b9bd1  xor     edx, edx; Type
0x1400b9bd3  call    cs:__imp_KeInitializeEvent
0x1400b9bda  nop     dword ptr [rax+rax+00h]
0x1400b9bdf  lea     rcx, [rdi+160h]; Timer
0x1400b9be6  call    cs:__imp_KeInitializeTimer
0x1400b9bed  nop     dword ptr [rax+rax+00h]
0x1400b9bf2  lea     rcx, [rdi+1A0h]; Dpc
0x1400b9bf9  mov     r8, rdi; DeferredContext
0x1400b9bfc  lea     rdx, ?VhdmpiCompletionTimerExpired@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x1400b9c03  call    cs:__imp_KeInitializeDpc
0x1400b9c0a  nop     dword ptr [rax+rax+00h]
0x1400b9c0f  lea     rcx, [rdi+68h]; Event
0x1400b9c13  xor     r8d, r8d; State
0x1400b9c16  xor     edx, edx; Type
0x1400b9c18  call    cs:__imp_KeInitializeEvent
0x1400b9c1f  nop     dword ptr [rax+rax+00h]
0x1400b9c24  lea     rcx, [rdi+80h]; Event
0x1400b9c2b  xor     r8d, r8d; State
0x1400b9c2e  xor     edx, edx; Type
0x1400b9c30  call    cs:__imp_KeInitializeEvent
0x1400b9c37  nop     dword ptr [rax+rax+00h]
0x1400b9c3c  lea     rcx, [rdi+118h]
0x1400b9c43  call    VhdmpiInitializePassiveLock
0x1400b9c48  lea     rcx, [rdi+130h]
0x1400b9c4f  call    VhdmpiInitializePassiveLock
0x1400b9c54  lea     rbx, [rdi+610h]
0x1400b9c5b  mov     rcx, rbx; RunRef
0x1400b9c5e  call    cs:__imp_ExInitializeRundownProtection
0x1400b9c65  nop     dword ptr [rax+rax+00h]
0x1400b9c6a  mov     rcx, rbx; RunRef
0x1400b9c6d  call    cs:__imp_ExWaitForRundownProtectionRelease
0x1400b9c74  nop     dword ptr [rax+rax+00h]
0x1400b9c79  mov     rcx, rbx; RunRef
0x1400b9c7c  call    cs:__imp_ExRundownCompleted
0x1400b9c83  nop     dword ptr [rax+rax+00h]
0x1400b9c88  lea     rcx, [rdi+600h]
0x1400b9c8f  call    VhdmpiInitializePassiveLock
0x1400b9c94  lea     rcx, [rdi+240h]
0x1400b9c9b  lea     rax, [rcx+8]
0x1400b9c9f  lea     rdx, ?VhdmpiSrbExtensionWorkerRoutine@@YAXPEAU_VHD_THREAD_POOL_WORK_ITEM@@@Z; VhdmpiSrbExtensionWorkerRoutine(_VHD_THREAD_POOL_WORK_ITEM *)
0x1400b9ca6  mov     dword ptr [rax+20h], 1
0x1400b9cad  mov     [rax+10h], rdx
0x1400b9cb1  mov     [rax+18h], rax
0x1400b9cb5  mov     qword ptr [rax], 0
0x1400b9cbc  call    DvInitializeWorkQueue
0x1400b9cc1  xor     eax, eax
0x1400b9cc3  mov     dword ptr [rdi+1F8h], 103h
0x1400b9ccd  mov     dword ptr [rdi+1F4h], 3
0x1400b9cd7  mov     [rsi], rdi
0x1400b9cda  mov     rbx, [rsp+38h+arg_0]
0x1400b9cdf  mov     rsi, [rsp+38h+arg_8]
0x1400b9ce4  add     rsp, 30h
0x1400b9ce8  pop     rdi
0x1400b9ce9  retn
```
