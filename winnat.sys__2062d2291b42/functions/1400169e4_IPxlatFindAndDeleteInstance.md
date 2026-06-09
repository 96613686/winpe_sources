# IPxlatFindAndDeleteInstance

- ea: `0x1400169e4`
- end: `0x140016ae7`
- name: `IPxlatFindAndDeleteInstance`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140034d80`

## callees

- `0x1400169e4`
- `0x14002e53c`
- `0x14002e57c`
- `0x14003476c`
- `0x140034b28`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016a8c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140016a8c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016a62`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140016a62`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016aa7`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140016aa7`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016a0c`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140016a0c`

## pseudocode

```c
__int64 __fastcall IPxlatFindAndDeleteInstance(_QWORD *a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  unsigned int v4; // ebx
  _QWORD *Instance; // rdi
  __int64 v6; // rdx
  _QWORD *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400278F0);
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_i(v2, 20, v3, *a1);
  v4 = 0;
  if ( IPxlatGlobalState )
  {
    Instance = (_QWORD *)IPxlatFindInstance(*a1);
    if ( Instance )
    {
      KeAcquireInStackQueuedSpinLock(&qword_140027958, &LockHandle);
      v6 = *Instance;
      if ( *(_QWORD **)(*Instance + 8LL) != Instance || (v7 = (_QWORD *)Instance[1], (_QWORD *)*v7 != Instance) )
        __fastfail(3u);
      *v7 = v6;
      *(_QWORD *)(v6 + 8) = v7;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      IPxlatDeleteInstance(Instance);
    }
    else
    {
      v4 = -1073741275;
    }
  }
  else
  {
    v4 = -1073741436;
  }
  ExReleaseResourceAndLeaveCriticalRegion(&stru_1400278F0);
  if ( (xmmword_1400272E0 & 2) != 0 )
    WPP_SF_id(v8, 21, v9, *a1, v4);
  return v4;
}

```

## disassembly

```asm
0x1400169e4  mov     [rsp+arg_0], rbx
0x1400169e9  mov     [rsp+arg_8], rsi
0x1400169ee  push    rdi
0x1400169ef  sub     rsp, 50h
0x1400169f3  mov     rsi, rcx
0x1400169f6  xorps   xmm0, xmm0
0x1400169f9  xor     eax, eax
0x1400169fb  lea     rcx, stru_1400278F0; Resource
0x140016a02  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140016a07  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140016a0c  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140016a13  nop     dword ptr [rax+rax+00h]
0x140016a18  test    byte ptr cs:xmmword_1400272E0, 2
0x140016a1f  jz      short loc_140016A2E
0x140016a21  mov     r9, [rsi]
0x140016a24  mov     edx, 14h
0x140016a29  call    WPP_SF_i
0x140016a2e  xor     ebx, ebx
0x140016a30  cmp     cs:IPxlatGlobalState, bl
0x140016a36  jnz     short loc_140016A3F
0x140016a38  mov     ebx, 0C0000184h
0x140016a3d  jmp     short loc_140016AA0
0x140016a3f  mov     rcx, [rsi]
0x140016a42  call    IPxlatFindInstance
0x140016a47  mov     rdi, rax
0x140016a4a  test    rax, rax
0x140016a4d  jnz     short loc_140016A56
0x140016a4f  mov     ebx, 0C0000225h
0x140016a54  jmp     short loc_140016AA0
0x140016a56  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140016a5b  lea     rcx, qword_140027958; SpinLock
0x140016a62  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140016a69  nop     dword ptr [rax+rax+00h]
0x140016a6e  mov     rdx, [rdi]
0x140016a71  cmp     [rdx+8], rdi
0x140016a75  jnz     short loc_140016AE0
0x140016a77  mov     rax, [rdi+8]
0x140016a7b  cmp     [rax], rdi
0x140016a7e  jnz     short loc_140016AE0
0x140016a80  mov     [rax], rdx
0x140016a83  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140016a88  mov     [rdx+8], rax
0x140016a8c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140016a93  nop     dword ptr [rax+rax+00h]
0x140016a98  mov     rcx, rdi; P
0x140016a9b  call    IPxlatDeleteInstance
0x140016aa0  lea     rcx, stru_1400278F0; Resource
0x140016aa7  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140016aae  nop     dword ptr [rax+rax+00h]
0x140016ab3  test    byte ptr cs:xmmword_1400272E0, 2
0x140016aba  jz      short loc_140016ACD
0x140016abc  mov     r9, [rsi]
0x140016abf  mov     edx, 15h
0x140016ac4  mov     [rsp+58h+var_38], ebx
0x140016ac8  call    WPP_SF_id
0x140016acd  mov     rsi, [rsp+58h+arg_8]
0x140016ad2  mov     eax, ebx
0x140016ad4  mov     rbx, [rsp+58h+arg_0]
0x140016ad9  add     rsp, 50h
0x140016add  pop     rdi
0x140016ade  retn
0x140016ae0  mov     ecx, 3
0x140016ae5  int     29h; Win8: RtlFailFast(ecx)
```
