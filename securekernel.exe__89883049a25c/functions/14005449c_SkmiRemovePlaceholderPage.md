# SkmiRemovePlaceholderPage

- ea: `0x14005449c`
- end: `0x140054659`
- name: `SkmiRemovePlaceholderPage`
- size: `445`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter3)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140002a04`

## callees

- `0x140009890`
- `0x14000d020`
- `0x14000e4b0`
- `0x14002b534`
- `0x14005449c`
- `0x140081290`
- `0x1400f2fc0`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkmiRemovePlaceholderPage(ULONG_PTR BugCheckParameter3)
{
  signed __int64 v2; // r15
  unsigned __int64 *v3; // r14
  unsigned __int8 CurrentIrql; // bp
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // rdi
  int v8; // ecx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 DataTraceEntry; // rax
  __int64 v12; // rcx
  __int64 v13; // rsi
  __int64 v14; // rdx
  unsigned int v15; // ebx
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h]
  ULONG BackTraceHash; // [rsp+70h] [rbp+8h] BYREF

  if ( BugCheckParameter3 > 0xFFFFFFFFFFLL )
    return 3221225485LL;
  v2 = 8 * BugCheckParameter3;
  v3 = (unsigned __int64 *)(8 * BugCheckParameter3 - 0x180000000000LL);
  CurrentIrql = KeGetCurrentIrql();
  __writecr8(2u);
  _m_prefetchw(v3);
  v5 = *v3;
  do
  {
    if ( v5 >> 61 != 2 )
    {
      v8 = 1025;
      goto LABEL_19;
    }
    if ( (v5 & 0xFFF) != 0x400 && (v5 & 0xFFF) - 1032 >= 5 )
    {
      v8 = 1026;
LABEL_19:
      SKMI_SECURITY(v8);
      v15 = -1073741819;
      goto LABEL_20;
    }
    v6 = v5;
    v7 = v5;
    v5 = _InterlockedCompareExchange64((volatile signed __int64 *)v3, 0x2000000000000000LL, v5);
  }
  while ( v5 != v6 );
  SkmiProtectPageRange(BugCheckParameter3);
  DataTraceEntry = SkmiAllocateDataTraceEntry(0, 0, v9, v10);
  v13 = DataTraceEntry;
  if ( DataTraceEntry )
  {
    *(_QWORD *)(DataTraceEntry + 16) = v7;
    *(_QWORD *)(DataTraceEntry + 24) = 0x2000000000000000LL;
    *(_QWORD *)DataTraceEntry = v2 >> 3;
    *(_BYTE *)(DataTraceEntry + 8) = 2;
    memset_0((void *)(DataTraceEntry + 32), 0, 0x40u);
    if ( (SkmiFlags & 0x400000) != 0
      && KeGetPcr()->NtTib.StackBase
      && !RtlCaptureStackBackTrace(v12, 8u, (PVOID *)(v13 + 32), &BackTraceHash) )
    {
      *(_QWORD *)(v13 + 40) = retaddr;
      *(_QWORD *)(v13 + 32) = SkmiGetInstructionPointer(v12, v14);
    }
  }
  *v3 = 0x2000000000000000LL;
  if ( v5 >> 61 != 5 && (v5 & 0xFFF) == 0x400 )
    _InterlockedDecrement(&SkmiUnprotectedPageCount);
  v15 = 0;
LABEL_20:
  LOBYTE(v12) = CurrentIrql;
  SkeLowerIrql(v12);
  return v15;
}

```

## disassembly

```asm
0x14005449c  push    rbx
0x14005449e  push    rbp
0x14005449f  push    rsi
0x1400544a0  push    rdi
0x1400544a1  push    r12
0x1400544a3  push    r13
0x1400544a5  push    r14
0x1400544a7  push    r15
0x1400544a9  sub     rsp, 28h
0x1400544ad  mov     r9, rcx
0x1400544b0  mov     rdx, 0FFFFEFFFFFFFFFFFh
0x1400544ba  mov     rcx, 0FFFFE80000000000h
0x1400544c4  mov     rax, rcx
0x1400544c7  sub     rdx, rax
0x1400544ca  sar     rdx, 3
0x1400544ce  cmp     r9, rdx
0x1400544d1  ja      loc_140054642
0x1400544d7  lea     r15, ds:0[r9*8]
0x1400544df  mov     rax, rcx
0x1400544e2  lea     r14, [r15+rax]
0x1400544e6  mov     rbp, cr8
0x1400544ea  mov     ecx, 2
0x1400544ef  mov     cr8, rcx
0x1400544f3  prefetchw byte ptr [r14]
0x1400544f7  mov     rbx, [r14]
0x1400544fa  mov     rdx, 2000000000000000h
0x140054504  mov     r13d, 0FFFh
0x14005450a  mov     rax, rbx
0x14005450d  shr     rax, 3Dh
0x140054511  cmp     al, cl
0x140054513  jnz     loc_140054627
0x140054519  mov     rax, rbx
0x14005451c  and     rax, r13
0x14005451f  cmp     rax, 400h
0x140054525  jz      short loc_140054536
0x140054527  mov     eax, ebx
0x140054529  and     eax, r13d
0x14005452c  sub     eax, 408h
0x140054531  cmp     eax, 5
0x140054534  jnb     short loc_140054553
0x140054536  mov     rcx, rbx
0x140054539  mov     rdi, rbx
0x14005453c  mov     rax, rbx
0x14005453f  lock cmpxchg [r14], rdx
0x140054544  mov     rbx, rax
0x140054547  cmp     rax, rcx
0x14005454a  jz      short loc_14005455D
0x14005454c  mov     ecx, 2
0x140054551  jmp     short loc_14005450A
0x140054553  mov     ecx, 402h
0x140054558  jmp     loc_14005462C
0x14005455d  mov     r8d, cs:SkmmDefaultVtlProtection
0x140054564  mov     edx, 1
0x140054569  mov     rcx, r9; BugCheckParameter3
0x14005456c  call    SkmiProtectPageRange
0x140054571  xor     edx, edx
0x140054573  xor     ecx, ecx
0x140054575  call    SkmiAllocateDataTraceEntry
0x14005457a  xor     r12d, r12d
0x14005457d  mov     rsi, rax
0x140054580  test    rax, rax
0x140054583  jz      short loc_1400545F7
0x140054585  mov     [rax+10h], rdi
0x140054589  lea     r8d, [r12+40h]; Size
0x14005458e  mov     rax, 2000000000000000h
0x140054598  sar     r15, 3
0x14005459c  lea     rdi, [rsi+20h]
0x1400545a0  mov     [rsi+18h], rax
0x1400545a4  mov     rcx, rdi; void *
0x1400545a7  mov     [rsi], r15
0x1400545aa  xor     edx, edx; Val
0x1400545ac  mov     byte ptr [rsi+8], 2
0x1400545b0  call    memset_0
0x1400545b5  test    cs:SkmiFlags, 400000h
0x1400545bf  jz      short loc_1400545F7
0x1400545c1  mov     rax, gs:8
0x1400545ca  test    rax, rax
0x1400545cd  jz      short loc_1400545F7
0x1400545cf  lea     r9, [rsp+68h+BackTraceHash]; BackTraceHash
0x1400545d4  mov     r8, rdi; BackTrace
0x1400545d7  lea     edx, [r12+8]; FramesToCapture
0x1400545dc  call    RtlCaptureStackBackTrace
0x1400545e1  test    ax, ax
0x1400545e4  jnz     short loc_1400545F7
0x1400545e6  mov     rax, [rsp+68h]
0x1400545eb  mov     [rsi+28h], rax
0x1400545ef  call    SkmiGetInstructionPointer
0x1400545f4  mov     [rdi], rax
0x1400545f7  mov     rax, 2000000000000000h
0x140054601  mov     [r14], rax
0x140054604  mov     rax, rbx
0x140054607  shr     rax, 3Dh
0x14005460b  cmp     al, 5
0x14005460d  jz      short loc_140054622
0x14005460f  and     rbx, r13
0x140054612  cmp     rbx, 400h
0x140054619  jnz     short loc_140054622
0x14005461b  lock dec cs:SkmiUnprotectedPageCount
0x140054622  mov     ebx, r12d
0x140054625  jmp     short loc_140054636
0x140054627  mov     ecx, 401h
0x14005462c  call    SKMI_SECURITY
0x140054631  mov     ebx, 0C0000005h
0x140054636  mov     cl, bpl
0x140054639  call    SkeLowerIrql
0x14005463e  mov     eax, ebx
0x140054640  jmp     short loc_140054647
0x140054642  mov     eax, 0C000000Dh
0x140054647  add     rsp, 28h
0x14005464b  pop     r15
0x14005464d  pop     r14
0x14005464f  pop     r13
0x140054651  pop     r12
0x140054653  pop     rdi
0x140054654  pop     rsi
0x140054655  pop     rbp
0x140054656  pop     rbx
0x140054657  retn
```
