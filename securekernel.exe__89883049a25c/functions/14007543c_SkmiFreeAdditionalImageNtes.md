# SkmiFreeAdditionalImageNtes

- ea: `0x14007543c`
- end: `0x14007554e`
- name: `SkmiFreeAdditionalImageNtes`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x14001b520`

## callees

- `0x140003780`
- `0x140010b90`
- `0x1400130a0`
- `0x140024724`
- `0x14002b534`
- `0x14007543c`
- `0x140081290`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiFreeAdditionalImageNtes(unsigned __int64 StackBase, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 *v4; // rdi
  __int64 *v5; // r14
  unsigned __int64 v6; // rbx
  __int64 PteTrace; // rax
  __int64 v8; // rbp
  PVOID *v9; // rsi
  __int64 v10; // rcx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+78h] [rbp+10h] BYREF

  v4 = (__int64 *)(((StackBase >> 9) & 0x7FFFFFFFF8LL) - 0xA0000000000LL);
  v5 = &v4[(unsigned int)a2 - 1];
  while ( v4 <= v5 )
  {
    v6 = *v4;
    PteTrace = SkmiGetPteTrace(0, (_DWORD)v4, 0, 2081, *v4);
    v8 = PteTrace;
    if ( PteTrace )
    {
      v9 = (PVOID *)(PteTrace + 32);
      memset_0((void *)(PteTrace + 32), 0, 0x40u);
      if ( (SkmiFlags & 0x400000) != 0 )
      {
        StackBase = (unsigned __int64)KeGetPcr()->NtTib.StackBase;
        if ( StackBase )
        {
          if ( !RtlCaptureStackBackTrace(StackBase, 8u, v9, &BackTraceHash) )
          {
            *(_QWORD *)(v8 + 40) = retaddr;
            *v9 = (PVOID)SkmiGetInstructionPointer(StackBase, a2);
          }
        }
      }
    }
    *v4 = 2081;
    if ( (v6 & 0x801) == 1 || (v6 & 0x100) != 0 )
      SkmiFreePhysicalPage(0, (v6 >> 12) & 0xFFFFFFFFFFLL, a3);
    ++v4;
  }
  LOBYTE(v10) = SkmiAcquireNteAssertionLock(StackBase, a2, a3, a4);
  return SkmiReleaseNteAssertionLock(v10);
}

```

## disassembly

```asm
0x14007543c  push    rbx
0x14007543e  push    rbp
0x14007543f  push    rsi
0x140075440  push    rdi
0x140075441  push    r14
0x140075443  push    r15
0x140075445  sub     rsp, 38h
0x140075449  mov     rdi, rcx
0x14007544c  mov     rax, 7FFFFFFFF8h
0x140075456  shr     rdi, 9
0x14007545a  and     rdi, rax
0x14007545d  mov     rax, 0FFFFF60000000000h
0x140075467  add     rdi, rax
0x14007546a  mov     r14d, edx
0x14007546d  dec     r14
0x140075470  lea     r14, [rdi+r14*8]
0x140075474  jmp     loc_14007552B
0x140075479  mov     rbx, [rdi]
0x14007547c  mov     r9d, 821h
0x140075482  mov     rax, [rdi]
0x140075485  xor     r8d, r8d
0x140075488  mov     rdx, rdi
0x14007548b  mov     [rsp+68h+var_48], rax
0x140075490  xor     ecx, ecx
0x140075492  call    SkmiGetPteTrace
0x140075497  mov     rbp, rax
0x14007549a  test    rax, rax
0x14007549d  jz      short loc_1400754F3
0x14007549f  xor     edx, edx; Val
0x1400754a1  lea     rsi, [rax+20h]
0x1400754a5  mov     rcx, rsi; void *
0x1400754a8  lea     r8d, [rdx+40h]; Size
0x1400754ac  call    memset_0
0x1400754b1  test    cs:SkmiFlags, 400000h
0x1400754bb  jz      short loc_1400754F3
0x1400754bd  mov     rcx, gs:8; FramesToSkip
0x1400754c6  test    rcx, rcx
0x1400754c9  jz      short loc_1400754F3
0x1400754cb  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x1400754d0  mov     r8, rsi; BackTrace
0x1400754d3  mov     edx, 8; FramesToCapture
0x1400754d8  call    RtlCaptureStackBackTrace
0x1400754dd  test    ax, ax
0x1400754e0  jnz     short loc_1400754F3
0x1400754e2  mov     rax, [rsp+68h]
0x1400754e7  mov     [rbp+28h], rax
0x1400754eb  call    SkmiGetInstructionPointer
0x1400754f0  mov     [rsi], rax
0x1400754f3  mov     rax, rbx
0x1400754f6  mov     qword ptr [rdi], 821h
0x1400754fd  and     eax, 801h
0x140075502  cmp     rax, 1
0x140075506  jz      short loc_14007550F
0x140075508  bt      rbx, 8
0x14007550d  jnb     short loc_140075527
0x14007550f  shr     rbx, 0Ch
0x140075513  mov     rdx, 0FFFFFFFFFFh
0x14007551d  and     rdx, rbx
0x140075520  xor     ecx, ecx
0x140075522  call    SkmiFreePhysicalPage
0x140075527  add     rdi, 8
0x14007552b  cmp     rdi, r14
0x14007552e  jbe     loc_140075479
0x140075534  call    SkmiAcquireNteAssertionLock
0x140075539  mov     cl, al
0x14007553b  call    SkmiReleaseNteAssertionLock
0x140075540  add     rsp, 38h
0x140075544  pop     r15
0x140075546  pop     r14
0x140075548  pop     rdi
0x140075549  pop     rsi
0x14007554a  pop     rbp
0x14007554b  pop     rbx
0x14007554c  retn
```
