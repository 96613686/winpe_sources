# RtlpCSparseBitmapPageCommit

- ea: `0x1400362ec`
- end: `0x1400364bc`
- name: `RtlpCSparseBitmapPageCommit`
- size: `464`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140036064`
- `0x140036114`
- `0x1400361ec`

## callees

- `0x1400362ec`
- `0x1400364c4`
- `0x140095cd8`
- `0x1400c9434`
- `0x1400d37ec`
- `0x1400d3824`
- `0x1400d3894`

## pseudocode

```c
__int64 __fastcall RtlpCSparseBitmapPageCommit(__int64 a1, unsigned __int64 a2, __int64 a3, _OWORD *a4)
{
  unsigned __int64 v4; // r15
  unsigned __int8 v6; // cf
  int v10; // edi
  int v11; // ecx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *StackBase; // rcx
  __int64 v16; // rdx
  int v18; // [rsp+28h] [rbp-48h]
  unsigned __int64 v19; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v20[24]; // [rsp+58h] [rbp-18h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+30h] BYREF
  unsigned __int64 v22; // [rsp+A8h] [rbp+38h] BYREF

  v22 = a2;
  v19 = 0;
  v4 = a2 >> 15;
  v6 = _bittest64((const signed __int64 *)(a1 + 56), a2 >> 15);
  v21 = 0;
  if ( !v6 )
  {
    v19 = *(_QWORD *)a1 + (v4 << 12);
    v18 = *(unsigned __int8 *)(a1 + 49);
    v21 = 4096;
    v10 = RtlpHpEnvAllocVA((unsigned int)&v19, (unsigned int)&v21, 0, 1073745920, 4, v18);
    if ( v10 < 0 )
      return (unsigned int)v10;
    _interlockedbittestandset64((volatile signed __int32 *)(a1 + 56), v4);
  }
  *a4 = *(_OWORD *)RtlCSparseBitmapEnterLockingRegion(v20, a1);
  RtlpCSparseBitmapLock(a1, 0, a3);
  while ( *(_QWORD *)(a1 + 32) == a2 )
  {
    RtlpCSparseBitmapUnlock(a3);
    RtlpCSparseBitmapWaitOnAddress(a1 + 32, &v22);
    RtlpCSparseBitmapLock(a1, 0, a3);
  }
  if ( _bittest64(*(const signed __int64 **)a1, a2) )
    return 0;
  v11 = *(unsigned __int8 *)(a1 + 49);
  v19 = *(_QWORD *)(a1 + 8) + (a2 << 12);
  v21 = 4096;
  v10 = RtlpHpEnvAllocVA((unsigned int)&v19, (unsigned int)&v21, 0, 1073745920, 4, v11);
  if ( v10 >= 0 )
  {
    _interlockedbittestandset64(*(volatile signed __int32 **)a1, a2);
    return 0;
  }
  RtlpCSparseBitmapUnlock(a3);
  StackBase = KeGetPcr()->NtTib.StackBase;
  v16 = StackBase[18];
  if ( v16 )
  {
    if ( (*(_WORD *)(v16 + *((_QWORD *)&xmmword_140167150 + 1)))++ == 0xFFFF
      && *(_QWORD *)(v16 + xmmword_140167160) != (_QWORD)xmmword_140167160 + StackBase[17] )
    {
      SkiCheckForKernelApcDelivery(xmmword_140167160, v16, v13, v14);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400362ec  mov     r11, rsp
0x1400362ef  mov     [r11+18h], rbx
0x1400362f3  mov     [r11+20h], rsi
0x1400362f7  mov     [r11+10h], rdx
0x1400362fb  push    rbp
0x1400362fc  push    rdi
0x1400362fd  push    r12
0x1400362ff  push    r14
0x140036301  push    r15
0x140036303  mov     rbp, rsp
0x140036306  sub     rsp, 70h
0x14003630a  mov     r15, rdx
0x14003630d  mov     [rbp+var_20], 0
0x140036315  shr     r15, 0Fh
0x140036319  mov     r12, r9
0x14003631c  bt      [rcx+38h], r15
0x140036321  mov     r14, r8
0x140036324  mov     [rbp+arg_0], 0
0x14003632c  mov     rsi, rdx
0x14003632f  mov     rbx, rcx
0x140036332  jb      short loc_140036398
0x140036334  mov     [rsp+70h+var_30], 0
0x14003633c  lea     rdx, [rbp+arg_0]
0x140036340  mov     qword ptr [r11-60h], 0
0x140036348  mov     rax, r15
0x14003634b  shl     rax, 0Ch
0x14003634f  mov     r9d, 40001000h
0x140036355  add     rax, [rcx]
0x140036358  xor     r8d, r8d
0x14003635b  mov     [rbp+var_20], rax
0x14003635f  movzx   eax, byte ptr [rcx+32h]
0x140036363  movzx   ecx, byte ptr [rcx+31h]
0x140036367  mov     [rsp+70h+var_40], eax
0x14003636b  mov     [rsp+70h+var_48], ecx
0x14003636f  lea     rcx, [rbp+var_20]
0x140036373  mov     [rbp+arg_0], 1000h
0x14003637b  mov     [rsp+70h+var_50], 4
0x140036383  call    RtlpHpEnvAllocVA
0x140036388  mov     edi, eax
0x14003638a  test    eax, eax
0x14003638c  js      loc_140036455
0x140036392  lock bts [rbx+38h], r15
0x140036398  mov     rdx, rbx
0x14003639b  lea     rcx, [rbp+var_18]
0x14003639f  call    RtlCSparseBitmapEnterLockingRegion
0x1400363a4  mov     r8, r14
0x1400363a7  xor     edx, edx
0x1400363a9  mov     rcx, rbx
0x1400363ac  movups  xmm0, xmmword ptr [rax]
0x1400363af  movdqu  xmmword ptr [r12], xmm0
0x1400363b5  call    RtlpCSparseBitmapLock
0x1400363ba  lea     rdi, [rbx+20h]
0x1400363be  jmp     short loc_1400363E1
0x1400363c0  mov     rcx, r14
0x1400363c3  call    RtlpCSparseBitmapUnlock
0x1400363c8  lea     rdx, [rbp+arg_8]
0x1400363cc  mov     rcx, rdi
0x1400363cf  call    RtlpCSparseBitmapWaitOnAddress
0x1400363d4  mov     r8, r14
0x1400363d7  xor     edx, edx
0x1400363d9  mov     rcx, rbx
0x1400363dc  call    RtlpCSparseBitmapLock
0x1400363e1  cmp     [rdi], rsi
0x1400363e4  jz      short loc_1400363C0
0x1400363e6  mov     rax, [rbx]
0x1400363e9  bt      [rax], rsi
0x1400363ed  jb      short loc_140036453
0x1400363ef  movzx   ecx, byte ptr [rbx+31h]
0x1400363f3  lea     rdx, [rbp+arg_0]
0x1400363f7  mov     [rsp+70h+var_30], 0
0x1400363ff  mov     rax, rsi
0x140036402  shl     rax, 0Ch
0x140036406  mov     r9d, 40001000h
0x14003640c  add     rax, [rbx+8]
0x140036410  xor     r8d, r8d
0x140036413  mov     [rsp+70h+var_38], 0
0x14003641c  mov     [rbp+var_20], rax
0x140036420  movzx   eax, byte ptr [rbx+32h]
0x140036424  mov     [rsp+70h+var_40], eax
0x140036428  mov     [rsp+70h+var_48], ecx
0x14003642c  lea     rcx, [rbp+var_20]
0x140036430  mov     [rbp+arg_0], 1000h
0x140036438  mov     [rsp+70h+var_50], 4
0x140036440  call    RtlpHpEnvAllocVA
0x140036445  mov     edi, eax
0x140036447  test    eax, eax
0x140036449  js      short loc_140036471
0x14003644b  mov     rax, [rbx]
0x14003644e  lock bts [rax], rsi
0x140036453  xor     edi, edi
0x140036455  lea     r11, [rsp+70h+var_s0]
0x14003645a  mov     eax, edi
0x14003645c  mov     rbx, [r11+40h]
0x140036460  mov     rsi, [r11+48h]
0x140036464  mov     rsp, r11
0x140036467  pop     r15
0x140036469  pop     r14
0x14003646b  pop     r12
0x14003646d  pop     rdi
0x14003646e  pop     rbp
0x14003646f  retn
0x140036471  mov     rcx, r14
0x140036474  call    RtlpCSparseBitmapUnlock
0x140036479  mov     rcx, gs:8
0x140036482  mov     rdx, [rcx+90h]
0x140036489  test    rdx, rdx
0x14003648c  jz      short loc_140036455
0x14003648e  nop
0x14003648f  mov     rax, qword ptr cs:xmmword_140167150+8
0x140036496  add     word ptr [rdx+rax], 1
0x14003649b  jnz     short loc_140036455
0x14003649d  mov     rax, [rcx+88h]
0x1400364a4  nop
0x1400364a5  mov     rcx, qword ptr cs:xmmword_140167160
0x1400364ac  add     rax, rcx
0x1400364af  cmp     [rdx+rcx], rax
0x1400364b3  jz      short loc_140036455
0x1400364b5  call    SkiCheckForKernelApcDelivery
0x1400364ba  jmp     short loc_140036455
```
