# VidPartitionpTraceInfo

- ea: `0x14008fef8`
- end: `0x14008ffa8`
- name: `VidPartitionpTraceInfo`
- size: `176`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x14008fc2c`

## callees

- `0x140024830`
- `0x140034554`
- `0x140034584`
- `0x14008fef8`

## import_xrefs

- `ntoskrnl!PsGetThreadId` at `0x14008ff3f`
- `ntoskrnl!PsGetThreadId` at `0x14008ff3f`
- `ntoskrnl!PsGetProcessId` at `0x14008ff6f`
- `ntoskrnl!PsGetProcessId` at `0x14008ff6f`

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
0x14008fef8  push    rbx
0x14008fefa  push    rsi
0x14008fefb  push    rdi
0x14008fefc  push    r14
0x14008fefe  sub     rsp, 48h
0x14008ff02  cmp     qword ptr [rcx+2840h], 0
0x14008ff0a  mov     r14, rdx
0x14008ff0d  mov     rdi, rcx
0x14008ff10  jz      loc_14008FF9D
0x14008ff16  call    VidObjectLockAcquireShared
0x14008ff1b  mov     ebx, [rdi+0C80h]
0x14008ff21  xor     esi, esi
0x14008ff23  test    ebx, ebx
0x14008ff25  jz      short loc_14008FF5B
0x14008ff27  mov     rcx, [rdi+0C88h]
0x14008ff2e  mov     ebx, esi
0x14008ff30  imul    rax, rbx, 9D0h
0x14008ff37  mov     rcx, [rax+rcx+150h]; Thread
0x14008ff3f  call    cs:__imp_PsGetThreadId
0x14008ff46  nop     dword ptr [rax+rax+00h]
0x14008ff4b  mov     [r14+rsi*8], rax
0x14008ff4f  inc     esi
0x14008ff51  mov     ebx, [rdi+0C80h]
0x14008ff57  cmp     esi, ebx
0x14008ff59  jb      short loc_14008FF27
0x14008ff5b  movups  xmm0, xmmword ptr [rdi+290h]
0x14008ff62  mov     rcx, [rdi+2848h]; Process
0x14008ff69  movdqu  [rsp+68h+var_38], xmm0
0x14008ff6f  call    cs:__imp_PsGetProcessId
0x14008ff76  nop     dword ptr [rax+rax+00h]
0x14008ff7b  lea     r8, [rdi+78h]
0x14008ff7f  mov     [rsp+68h+var_40], r14
0x14008ff84  mov     r9, rax
0x14008ff87  mov     [rsp+68h+var_48], ebx
0x14008ff8b  lea     rdx, [rsp+68h+var_38]
0x14008ff90  call    VidTraceGuidStringUint64Uint32Uint64ArrayRoutine
0x14008ff95  mov     rcx, rdi
0x14008ff98  call    VidObjectLockRelease
0x14008ff9d  add     rsp, 48h
0x14008ffa1  pop     r14
0x14008ffa3  pop     rdi
0x14008ffa4  pop     rsi
0x14008ffa5  pop     rbx
0x14008ffa6  retn
```
