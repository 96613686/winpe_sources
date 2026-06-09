# SkpsCreateBasicEnclaveThread

- ea: `0x1400b04d8`
- end: `0x1400b0686`
- name: `SkpsCreateBasicEnclaveThread`
- size: `430`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140021428`

## callees

- `0x140002900`
- `0x14000b084`
- `0x14006bbc8`
- `0x140095cd8`
- `0x140098654`
- `0x1400b04d8`
- `0x1400b068c`
- `0x1400b0b38`
- `0x1400ee8b0`
- `0x1400f3620`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpsCreateBasicEnclaveThread(__int64 a1)
{
  _QWORD *StackBase; // rsi
  __int64 v3; // rsi
  _QWORD *v4; // rcx
  __int64 v5; // rbx
  __int64 v6; // rcx
  int EnclaveThread; // eax
  unsigned int v8; // edi
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  int v14; // [rsp+30h] [rbp-59h] BYREF
  __int64 v15; // [rsp+38h] [rbp-51h] BYREF
  _BYTE v16[2]; // [rsp+40h] [rbp-49h] BYREF
  __int16 v17; // [rsp+42h] [rbp-47h]
  __int64 v18; // [rsp+48h] [rbp-41h]
  __int64 v19; // [rsp+50h] [rbp-39h]
  __int64 v20; // [rsp+58h] [rbp-31h]

  v14 = 0;
  memset_0(v16, 0, 0x68u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    v3 = StackBase[10];
  else
    v3 = 0;
  v4 = KeGetPcr()->NtTib.StackBase;
  v5 = 0;
  v15 = 0;
  if ( v4 )
  {
    v6 = v4[18];
    if ( v6 )
      --*(_WORD *)(v6 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(v3 + 256);
  if ( (int)SkmmQueryEnclavePage(a1, &v14) >= 0 && v14 == 4 )
  {
    EnclaveThread = SkpsCreateEnclaveThread(v3, a1, a1, 0, (__int64)&v15);
    v5 = v15;
    v8 = EnclaveThread;
    if ( EnclaveThread >= 0 )
    {
      v16[1] = 0;
      v17 = 43;
      v18 = *(_QWORD *)(v3 + 240);
      v19 = a1;
      v20 = *(unsigned int *)(v15 + 168);
      SkCallNormalMode(v16);
      v8 = v18;
      if ( (int)v18 >= 0 )
      {
        LOBYTE(v9) = 1;
        SkeReadyEnclaveThread(v5, v9);
        goto LABEL_15;
      }
    }
  }
  else
  {
    v8 = -1073741800;
  }
  if ( v5 )
    SkpspDeleteEnclaveThread(v5);
LABEL_15:
  RtlReleaseSRWLockExclusive(v3 + 256);
  v10 = KeGetPcr()->NtTib.StackBase;
  if ( v10 )
  {
    v11 = v10[18];
    if ( v11 )
    {
      if ( (*(_WORD *)(v11 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v11 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v10[17]
        && !*(_WORD *)(v11 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery();
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1400b04d8  mov     [rsp-8+arg_8], rbx
0x1400b04dd  mov     [rsp-8+arg_10], rsi
0x1400b04e2  push    rbp
0x1400b04e3  push    rdi
0x1400b04e4  push    r12
0x1400b04e6  push    r14
0x1400b04e8  push    r15
0x1400b04ea  lea     rbp, [rsp-37h]
0x1400b04ef  sub     rsp, 0C0h
0x1400b04f6  mov     rax, cs:__security_cookie
0x1400b04fd  xor     rax, rsp
0x1400b0500  mov     [rbp+57h+var_30], rax
0x1400b0504  xor     r12d, r12d
0x1400b0507  mov     r14, rcx
0x1400b050a  xor     edx, edx; Val
0x1400b050c  mov     [rbp+57h+var_B0], r12d
0x1400b0510  lea     rcx, [rbp+57h+var_A0]; void *
0x1400b0514  lea     r8d, [r12+68h]; Size
0x1400b0519  call    memset_0
0x1400b051e  mov     rsi, gs:8
0x1400b0527  test    rsi, rsi
0x1400b052a  jz      short loc_1400B0532
0x1400b052c  mov     rsi, [rsi+50h]
0x1400b0530  jmp     short loc_1400B0535
0x1400b0532  mov     rsi, r12
0x1400b0535  mov     rcx, gs:8
0x1400b053e  mov     rbx, r12
0x1400b0541  mov     [rbp+57h+var_A8], rbx
0x1400b0545  test    rcx, rcx
0x1400b0548  jz      short loc_1400B0562
0x1400b054a  mov     rcx, [rcx+90h]
0x1400b0551  test    rcx, rcx
0x1400b0554  jz      short loc_1400B0562
0x1400b0556  mov     rax, qword ptr cs:xmmword_140167150
0x1400b055d  dec     word ptr [rcx+rax]
0x1400b0561  nop
0x1400b0562  lea     r15, [rsi+100h]
0x1400b0569  mov     rcx, r15
0x1400b056c  call    SkAcquirePushLockExclusive
0x1400b0571  lea     rdx, [rbp+57h+var_B0]
0x1400b0575  mov     rcx, r14
0x1400b0578  call    SkmmQueryEnclavePage
0x1400b057d  test    eax, eax
0x1400b057f  js      short loc_1400B05ED
0x1400b0581  cmp     [rbp+57h+var_B0], 4
0x1400b0585  jnz     short loc_1400B05ED
0x1400b0587  lea     rax, [rbp+57h+var_A8]
0x1400b058b  xor     r9d, r9d
0x1400b058e  mov     r8, r14
0x1400b0591  mov     [rsp+0E0h+var_C0], rax
0x1400b0596  mov     rdx, r14
0x1400b0599  mov     rcx, rsi
0x1400b059c  call    SkpsCreateEnclaveThread
0x1400b05a1  mov     rbx, [rbp+57h+var_A8]
0x1400b05a5  mov     edi, eax
0x1400b05a7  test    eax, eax
0x1400b05a9  js      short loc_1400B05F2
0x1400b05ab  mov     [rbp+57h+var_9F], r12b
0x1400b05af  lea     rcx, [rbp+57h+var_A0]
0x1400b05b3  mov     eax, 2Bh ; '+'
0x1400b05b8  mov     [rbp+57h+var_9E], ax
0x1400b05bc  mov     rax, [rsi+0F0h]
0x1400b05c3  mov     [rbp+57h+var_98], rax
0x1400b05c7  mov     [rbp+57h+var_90], r14
0x1400b05cb  mov     eax, [rbx+0A8h]
0x1400b05d1  mov     [rbp+57h+var_88], rax
0x1400b05d5  call    SkCallNormalMode
0x1400b05da  mov     edi, dword ptr [rbp+57h+var_98]
0x1400b05dd  test    edi, edi
0x1400b05df  js      short loc_1400B05F2
0x1400b05e1  mov     dl, 1
0x1400b05e3  mov     rcx, rbx
0x1400b05e6  call    SkeReadyEnclaveThread
0x1400b05eb  jmp     short loc_1400B05FF
0x1400b05ed  mov     edi, 0C0000018h
0x1400b05f2  test    rbx, rbx
0x1400b05f5  jz      short loc_1400B05FF
0x1400b05f7  mov     rcx, rbx
0x1400b05fa  call    SkpspDeleteEnclaveThread
0x1400b05ff  mov     rcx, r15
0x1400b0602  call    RtlReleaseSRWLockExclusive
0x1400b0607  mov     rcx, gs:8
0x1400b0610  test    rcx, rcx
0x1400b0613  jz      short loc_1400B065B
0x1400b0615  mov     rdx, [rcx+90h]
0x1400b061c  test    rdx, rdx
0x1400b061f  jz      short loc_1400B065B
0x1400b0621  nop
0x1400b0622  mov     rax, qword ptr cs:xmmword_140167150
0x1400b0629  add     word ptr [rdx+rax], 1
0x1400b062e  jnz     short loc_1400B065B
0x1400b0630  mov     rax, [rcx+88h]
0x1400b0637  nop
0x1400b0638  mov     rcx, qword ptr cs:xmmword_140167160
0x1400b063f  add     rax, rcx
0x1400b0642  cmp     [rdx+rcx], rax
0x1400b0646  jz      short loc_1400B065B
0x1400b0648  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400b064f  cmp     [rdx+rax], r12w
0x1400b0654  jnz     short loc_1400B065B
0x1400b0656  call    SkiCheckForKernelApcDelivery
0x1400b065b  mov     eax, edi
0x1400b065d  mov     rcx, [rbp+57h+var_30]
0x1400b0661  xor     rcx, rsp; StackCookie
0x1400b0664  call    __security_check_cookie
0x1400b0669  lea     r11, [rsp+0E0h+var_20]
0x1400b0671  mov     rbx, [r11+38h]
0x1400b0675  mov     rsi, [r11+40h]
0x1400b0679  mov     rsp, r11
0x1400b067c  pop     r15
0x1400b067e  pop     r14
0x1400b0680  pop     r12
0x1400b0682  pop     rdi
0x1400b0683  pop     rbp
0x1400b0684  retn
```
