# WinHvpDepositMemoryFromMdl

- ea: `0x14002670c`
- end: `0x140026864`
- name: `WinHvpDepositMemoryFromMdl`
- size: `344`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x140021d00`
- `0x140022484`
- `0x140022900`
- `0x140022f88`

## callees

- `0x140003b70`
- `0x140009c90`
- `0x140009d40`
- `0x14000a040`
- `0x140022484`
- `0x14002670c`

## pseudocode

```c
__int64 __fastcall WinHvpDepositMemoryFromMdl(__int64 a1, __int64 a2, char a3, char a4, _QWORD *a5)
{
  _QWORD *v9; // r13
  unsigned __int64 v10; // rdi
  int v11; // r15d
  __int64 v12; // rbx
  _QWORD v14[16]; // [rsp+80h] [rbp-31h] BYREF
  __int64 v15; // [rsp+110h] [rbp+5Fh] BYREF

  memset(v14, 0, 0x40u);
  v9 = a5;
  LOBYTE(v14[3]) = a3;
  v15 = 0;
  a5 = (_QWORD *)a1;
  *v9 = 0;
  v10 = ((unsigned __int64)*(unsigned int *)(a2 + 40) + 4095) >> 12;
  v11 = WinHvpSpecialListRepHypercall(
          a4 != 0 ? 255 : 72,
          v10,
          &a5,
          8u,
          0,
          0,
          (char *)(a2 + 48),
          8u,
          (void (__fastcall *)(char *, char *, _QWORD))WinHvpDepositMemoryBuilder,
          (__int64 (__fastcall *)(char *, _QWORD))WinHvpDepositMemoryAdvancer,
          0,
          0,
          0,
          v14,
          &v15);
  if ( a4 && !a3 )
  {
    a5 = 0;
    WinHvpPersistMirroringDeposit(a1, a2, &a5);
  }
  v12 = v15;
  *v9 = v15;
  if ( v11 < 0 && (!a4 || !a3) && v12 )
  {
    memmove((void *)(a2 + 48), (const void *)(a2 + 8 * (v12 + 6)), 8 * (v10 - v12));
    *(_DWORD *)(a2 + 40) += -4096 * v12;
  }
  if ( v14[0] )
    ((void (*)(void))v14[7])();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002670c  push    rbp
0x14002670e  push    rbx
0x14002670f  push    rsi
0x140026710  push    rdi
0x140026711  push    r12
0x140026713  push    r13
0x140026715  push    r14
0x140026717  push    r15
0x140026719  lea     rbp, [rsp-17h]
0x14002671e  sub     rsp, 0C8h
0x140026725  mov     rsi, rdx
0x140026728  mov     r14b, r8b
0x14002672b  xor     edx, edx; Val
0x14002672d  mov     rbx, rcx
0x140026730  lea     rcx, [rbp+4Fh+var_80]; void *
0x140026734  mov     r12b, r9b
0x140026737  lea     r8d, [rdx+40h]; Size
0x14002673b  call    memset
0x140026740  mov     r13, [rbp+4Fh+arg_20]
0x140026744  lea     rdx, [rsi+30h]
0x140026748  xor     r8d, r8d
0x14002674b  mov     [rbp+4Fh+var_68], r14b
0x14002674f  mov     al, r12b
0x140026752  mov     [rbp+4Fh+arg_0], r8
0x140026756  mov     [rbp+4Fh+arg_20], rbx
0x14002675a  mov     [r13+0], r8
0x14002675e  mov     edi, [rsi+28h]
0x140026761  lea     r9d, [r8+8]
0x140026765  add     rdi, 0FFFh
0x14002676c  shr     rdi, 0Ch
0x140026770  neg     al
0x140026772  lea     rax, [rbp+4Fh+arg_0]
0x140026776  mov     [rsp+100h+var_90], rax
0x14002677b  sbb     ecx, ecx
0x14002677d  lea     rax, [rbp+4Fh+var_80]
0x140026781  and     ecx, 0B7h
0x140026787  mov     [rsp+100h+var_98], rax
0x14002678c  add     ecx, 48h ; 'H'
0x14002678f  mov     [rsp+100h+var_A0], r8
0x140026794  lea     rax, WinHvpDepositMemoryAdvancer
0x14002679b  mov     [rsp+100h+var_A8], r8d
0x1400267a0  mov     [rsp+100h+var_B0], r8
0x1400267a5  mov     [rsp+100h+var_B8], rax
0x1400267aa  lea     rax, WinHvpDepositMemoryBuilder
0x1400267b1  mov     [rsp+100h+var_C0], rax
0x1400267b6  mov     [rsp+100h+var_C8], r9d
0x1400267bb  mov     [rsp+100h+var_D0], rdx
0x1400267c0  mov     rdx, rdi
0x1400267c3  mov     [rsp+100h+var_D8], r8
0x1400267c8  mov     [rsp+100h+var_E0], r8
0x1400267cd  lea     r8, [rbp+4Fh+arg_20]
0x1400267d1  call    WinHvpSpecialListRepHypercall
0x1400267d6  mov     r15d, eax
0x1400267d9  test    r12b, r12b
0x1400267dc  jz      short loc_1400267FA
0x1400267de  test    r14b, r14b
0x1400267e1  jnz     short loc_1400267FA
0x1400267e3  lea     r8, [rbp+4Fh+arg_20]
0x1400267e7  mov     [rbp+4Fh+arg_20], 0
0x1400267ef  mov     rdx, rsi
0x1400267f2  mov     rcx, rbx
0x1400267f5  call    WinHvpPersistMirroringDeposit
0x1400267fa  mov     rbx, [rbp+4Fh+arg_0]
0x1400267fe  mov     [r13+0], rbx
0x140026802  test    r15d, r15d
0x140026805  jns     short loc_14002683A
0x140026807  test    r12b, r12b
0x14002680a  jz      short loc_140026811
0x14002680c  test    r14b, r14b
0x14002680f  jnz     short loc_14002683A
0x140026811  test    rbx, rbx
0x140026814  jz      short loc_14002683A
0x140026816  sub     rdi, rbx
0x140026819  lea     rdx, [rbx+6]
0x14002681d  shl     rdi, 3
0x140026821  lea     rdx, [rsi+rdx*8]; Src
0x140026825  mov     r8, rdi; Size
0x140026828  lea     rcx, [rsi+30h]; void *
0x14002682c  call    memmove
0x140026831  imul    eax, ebx, 0FFFFF000h
0x140026837  add     [rsi+28h], eax
0x14002683a  mov     rcx, [rbp+4Fh+var_80]
0x14002683e  test    rcx, rcx
0x140026841  jz      short loc_14002684C
0x140026843  mov     rax, [rbp+4Fh+var_48]
0x140026847  call    _guard_dispatch_icall
0x14002684c  mov     eax, r15d
0x14002684f  add     rsp, 0C8h
0x140026856  pop     r15
0x140026858  pop     r14
0x14002685a  pop     r13
0x14002685c  pop     r12
0x14002685e  pop     rdi
0x14002685f  pop     rsi
0x140026860  pop     rbx
0x140026861  pop     rbp
0x140026862  retn
```
