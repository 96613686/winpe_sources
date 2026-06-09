# SkeExitThreadWithReturn

- ea: `0x1400eedd0`
- end: `0x1400eef10`
- name: `SkeExitThreadWithReturn`
- size: `320`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x140021428`
- `0x140099358`
- `0x140099404`
- `0x1400b00bc`
- `0x1400b0f54`

## callees

- `0x140094078`
- `0x1400ee8b0`
- `0x1400eedd0`
- `0x1400f4040`

## pseudocode

```c
// positive sp value has been detected, the output may be wrong!
void __fastcall SkeExitThreadWithReturn(void (__fastcall *a1)(__int128 *, __int64), __int64 a2)
{
  struct _EXCEPTION_REGISTRATION_RECORD *ExceptionList; // r14
  ULONG_PTR Handler; // r8
  PEXCEPTION_ROUTINE v6; // rsi
  __int64 v7; // [rsp-28h] [rbp-98h] BYREF
  __int128 varsA8; // [rsp+118h] [rbp+A8h] BYREF

  KeGetCurrentIrql();
  _disable();
  ExceptionList = KeGetPcr()->NtTib.ExceptionList;
  Handler = (ULONG_PTR)ExceptionList->Handler;
  if ( BYTE6(ExceptionList[11].Handler) )
  {
    _fxsave(*(void **)(Handler + 112));
    _fxrstor(SkeDefaultNpxState);
    BYTE6(ExceptionList[11].Handler) = 0;
  }
  SkiUpdateXStateForVtlTransition(Handler);
  if ( (KeGetPcr()->HalReserved[3] & 2) != 0 && (KeGetPcr()[7].PcrAlign1[16] & 0x40) != 0 )
    SkiFlushBhb();
  __writegsbyte(0xCCu, KeGetPcr()->HalReserved[3] & 0xF9);
  v6 = ExceptionList[2].Handler;
  *((_QWORD *)ExceptionList->Handler + 16) = &v7;
  __writecr8(2u);
  ExceptionList->Handler = v6;
  *((_QWORD *)v6 + 8) = ExceptionList;
  _enable();
  a1(&varsA8, a2);
  JUMPOUT(0x1400EE960LL);
}

```

## disassembly

```asm
0x1400eedd0  push    r15
0x1400eedd2  push    r14
0x1400eedd4  push    r13
0x1400eedd6  push    r12
0x1400eedd8  push    rbx
0x1400eedd9  push    rsi
0x1400eedda  push    rdi
0x1400eeddb  push    rbp
0x1400eeddc  pushfq
0x1400eeddd  sub     rsp, 0D0h
0x1400eede4  movaps  [rsp+8+var_s28], xmm6
0x1400eede9  movaps  [rsp+8+var_s38], xmm7
0x1400eedee  movaps  [rsp+8+var_s48], xmm8
0x1400eedf4  movaps  [rsp+8+var_s58], xmm9
0x1400eedfa  movaps  [rsp+8+var_s68], xmm10
0x1400eee00  movaps  [rsp+8+var_s78], xmm11
0x1400eee09  movaps  [rsp+8+var_s88], xmm12
0x1400eee12  movaps  [rsp+8+var_s98], xmm13
0x1400eee1b  movaps  [rsp+8+var_sA8], xmm14
0x1400eee24  movaps  [rsp+8+var_sB8], xmm15
0x1400eee2d  mov     rbp, rsp
0x1400eee30  mov     r8, cr8
0x1400eee34  and     [rbp+arg_10], 0
0x1400eee3c  mov     [rbp+arg_12], r8b
0x1400eee43  cli
0x1400eee44  mov     r14, gs:0
0x1400eee4d  mov     r8, [r14+8]
0x1400eee51  cmp     byte ptr [r14+0BEh], 0
0x1400eee59  jz      short loc_1400EEE76
0x1400eee5b  mov     r11, [r8+70h]
0x1400eee5f  lea     r10, SkeDefaultNpxState
0x1400eee66  fxsave  dword ptr [r11]
0x1400eee6a  fxrstor dword ptr [r10]
0x1400eee6e  and     byte ptr [r14+0BEh], 0
0x1400eee76  mov     r12, rcx
0x1400eee79  mov     r13, rdx
0x1400eee7c  mov     rcx, r8; BugCheckParameter3
0x1400eee7f  mov     edx, 1
0x1400eee84  call    SkiUpdateXStateForVtlTransition
0x1400eee89  mov     al, gs:0CCh
0x1400eee91  test    al, 2
0x1400eee93  jz      short loc_1400EEEA6
0x1400eee95  mov     al, gs:0BA0h
0x1400eee9d  test    al, 40h
0x1400eee9f  jz      short loc_1400EEEA6
0x1400eeea1  call    SkiFlushBhb
0x1400eeea6  and     byte ptr gs:0CCh, 0F9h
0x1400eeeaf  mov     r8, [r14+8]
0x1400eeeb3  mov     rsi, [r14+28h]
0x1400eeeb7  mov     [r8+80h], rsp
0x1400eeebe  mov     rsp, [rsi+80h]
0x1400eeec5  mov     rbp, rsp
0x1400eeec8  mov     eax, 2
0x1400eeecd  mov     cr8, rax
0x1400eeed1  mov     [r14+8], rsi
0x1400eeed5  mov     [rsi+40h], r14
0x1400eeed9  sti
0x1400eeeda  sub     rsp, 90h
0x1400eeee1  lea     r15, [rsp-110h+arg_20]
0x1400eeee6  mov     rax, r12
0x1400eeee9  mov     rcx, r15
0x1400eeeec  mov     rdx, r13
0x1400eeeef  call    rax
0x1400eeef1  xor     edi, edi
0x1400eeef3  xor     r12, r12
0x1400eeef6  xor     r13, r13
0x1400eeef9  xorps   xmm6, xmm6
0x1400eeefc  xorps   xmm7, xmm7
0x1400eeeff  xorps   xmm8, xmm8
0x1400eef03  xorps   xmm9, xmm9
0x1400eef07  mov     ebx, [r15+4]
0x1400eef0b  jmp     SkpPrepareForNormalCall
```
