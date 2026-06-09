# VidPartitionpTraceInfo

- ea: `0x140091308`
- end: `0x1400913b8`
- name: `VidPartitionpTraceInfo`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14009103c`

## callees

- `0x1400249d0`
- `0x1400347a4`
- `0x1400347d4`
- `0x140091308`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14009134f`
- `ntoskrnl!PsGetThreadId` at `0x14009134f`
- `ntoskrnl!PsGetProcessId` at `0x14009137f`
- `ntoskrnl!PsGetProcessId` at `0x14009137f`

## pseudocode

```c
void __fastcall VidPartitionpTraceInfo(__int64 a1, __int64 a2)
{
  unsigned int v4; // ebx
  __int64 i; // rsi
  struct _KPROCESS *v6; // rcx
  unsigned int ProcessId; // eax
  int v8; // ecx
  __int128 v9; // [rsp+30h] [rbp-38h] BYREF

  if ( *(_QWORD *)(a1 + 10304) )
  {
    VidObjectLockAcquireShared(a1);
    v4 = *(_DWORD *)(a1 + 3200);
    for ( i = 0; (unsigned int)i < v4; v4 = *(_DWORD *)(a1 + 3200) )
    {
      *(_QWORD *)(a2 + 8 * i) = PsGetThreadId(*(PETHREAD *)(2512LL * (unsigned int)i + *(_QWORD *)(a1 + 3208) + 336));
      i = (unsigned int)(i + 1);
    }
    v6 = *(struct _KPROCESS **)(a1 + 10312);
    v9 = *(_OWORD *)(a1 + 656);
    ProcessId = (unsigned int)PsGetProcessId(v6);
    VidTraceGuidStringUint64Uint32Uint64ArrayRoutine(v8, (unsigned int)&v9, a1 + 120, ProcessId, v4, a2);
    VidObjectLockRelease(a1);
  }
}

```

## disassembly

```asm
0x140091308  push    rbx
0x14009130a  push    rsi
0x14009130b  push    rdi
0x14009130c  push    r14
0x14009130e  sub     rsp, 48h
0x140091312  cmp     qword ptr [rcx+2840h], 0
0x14009131a  mov     r14, rdx
0x14009131d  mov     rdi, rcx
0x140091320  jz      loc_1400913AD
0x140091326  call    VidObjectLockAcquireShared
0x14009132b  mov     ebx, [rdi+0C80h]
0x140091331  xor     esi, esi
0x140091333  test    ebx, ebx
0x140091335  jz      short loc_14009136B
0x140091337  mov     rcx, [rdi+0C88h]
0x14009133e  mov     ebx, esi
0x140091340  imul    rax, rbx, 9D0h
0x140091347  mov     rcx, [rax+rcx+150h]; Thread
0x14009134f  call    cs:__imp_PsGetThreadId
0x140091356  nop     dword ptr [rax+rax+00h]
0x14009135b  mov     [r14+rsi*8], rax
0x14009135f  inc     esi
0x140091361  mov     ebx, [rdi+0C80h]
0x140091367  cmp     esi, ebx
0x140091369  jb      short loc_140091337
0x14009136b  movups  xmm0, xmmword ptr [rdi+290h]
0x140091372  mov     rcx, [rdi+2848h]; Process
0x140091379  movdqu  [rsp+68h+var_38], xmm0
0x14009137f  call    cs:__imp_PsGetProcessId
0x140091386  nop     dword ptr [rax+rax+00h]
0x14009138b  lea     r8, [rdi+78h]
0x14009138f  mov     [rsp+68h+var_40], r14
0x140091394  mov     r9, rax
0x140091397  mov     [rsp+68h+var_48], ebx
0x14009139b  lea     rdx, [rsp+68h+var_38]
0x1400913a0  call    VidTraceGuidStringUint64Uint32Uint64ArrayRoutine
0x1400913a5  mov     rcx, rdi
0x1400913a8  call    VidObjectLockRelease
0x1400913ad  add     rsp, 48h
0x1400913b1  pop     r14
0x1400913b3  pop     rdi
0x1400913b4  pop     rsi
0x1400913b5  pop     rbx
0x1400913b6  retn
```
