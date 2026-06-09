# IPxlatFindAndDeleteInstance

- ea: `0x140015dac`
- end: `0x140015eaf`
- name: `IPxlatFindAndDeleteInstance`
- size: `259`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140033a40`

## callees

- `0x140015dac`
- `0x14002d53c`
- `0x14002d57c`
- `0x14003363c`
- `0x140033868`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015e54`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140015e54`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015e2a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140015e2a`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015e6f`
- `ntoskrnl!ExReleaseResourceAndLeaveCriticalRegion` at `0x140015e6f`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140015dd4`
- `ntoskrnl!ExEnterCriticalRegionAndAcquireResourceExclusive` at `0x140015dd4`

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
  ExEnterCriticalRegionAndAcquireResourceExclusive(&stru_1400268F0);
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_i(v2, 18, v3, *a1);
  v4 = 0;
  if ( IPxlatGlobalState )
  {
    Instance = (_QWORD *)IPxlatFindInstance(*a1);
    if ( Instance )
    {
      KeAcquireInStackQueuedSpinLock(&qword_140026958, &LockHandle);
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
  ExReleaseResourceAndLeaveCriticalRegion(&stru_1400268F0);
  if ( (xmmword_1400262E0 & 2) != 0 )
    WPP_SF_id(v8, 19, v9, *a1, v4);
  return v4;
}

```

## disassembly

```asm
0x140015dac  mov     [rsp+arg_0], rbx
0x140015db1  mov     [rsp+arg_8], rsi
0x140015db6  push    rdi
0x140015db7  sub     rsp, 50h
0x140015dbb  mov     rsi, rcx
0x140015dbe  xorps   xmm0, xmm0
0x140015dc1  xor     eax, eax
0x140015dc3  lea     rcx, stru_1400268F0; Resource
0x140015dca  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140015dcf  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140015dd4  call    cs:__imp_ExEnterCriticalRegionAndAcquireResourceExclusive
0x140015ddb  nop     dword ptr [rax+rax+00h]
0x140015de0  test    byte ptr cs:xmmword_1400262E0, 2
0x140015de7  jz      short loc_140015DF6
0x140015de9  mov     r9, [rsi]
0x140015dec  mov     edx, 12h
0x140015df1  call    WPP_SF_i
0x140015df6  xor     ebx, ebx
0x140015df8  cmp     cs:IPxlatGlobalState, bl
0x140015dfe  jnz     short loc_140015E07
0x140015e00  mov     ebx, 0C0000184h
0x140015e05  jmp     short loc_140015E68
0x140015e07  mov     rcx, [rsi]
0x140015e0a  call    IPxlatFindInstance
0x140015e0f  mov     rdi, rax
0x140015e12  test    rax, rax
0x140015e15  jnz     short loc_140015E1E
0x140015e17  mov     ebx, 0C0000225h
0x140015e1c  jmp     short loc_140015E68
0x140015e1e  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140015e23  lea     rcx, qword_140026958; SpinLock
0x140015e2a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140015e31  nop     dword ptr [rax+rax+00h]
0x140015e36  mov     rdx, [rdi]
0x140015e39  cmp     [rdx+8], rdi
0x140015e3d  jnz     short loc_140015EA8
0x140015e3f  mov     rax, [rdi+8]
0x140015e43  cmp     [rax], rdi
0x140015e46  jnz     short loc_140015EA8
0x140015e48  mov     [rax], rdx
0x140015e4b  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140015e50  mov     [rdx+8], rax
0x140015e54  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140015e5b  nop     dword ptr [rax+rax+00h]
0x140015e60  mov     rcx, rdi; P
0x140015e63  call    IPxlatDeleteInstance
0x140015e68  lea     rcx, stru_1400268F0; Resource
0x140015e6f  call    cs:__imp_ExReleaseResourceAndLeaveCriticalRegion
0x140015e76  nop     dword ptr [rax+rax+00h]
0x140015e7b  test    byte ptr cs:xmmword_1400262E0, 2
0x140015e82  jz      short loc_140015E95
0x140015e84  mov     r9, [rsi]
0x140015e87  mov     edx, 13h
0x140015e8c  mov     [rsp+58h+var_38], ebx
0x140015e90  call    WPP_SF_id
0x140015e95  mov     rsi, [rsp+58h+arg_8]
0x140015e9a  mov     eax, ebx
0x140015e9c  mov     rbx, [rsp+58h+arg_0]
0x140015ea1  add     rsp, 50h
0x140015ea5  pop     rdi
0x140015ea6  retn
0x140015ea8  mov     ecx, 3
0x140015ead  int     29h; Win8: RtlFailFast(ecx)
```
