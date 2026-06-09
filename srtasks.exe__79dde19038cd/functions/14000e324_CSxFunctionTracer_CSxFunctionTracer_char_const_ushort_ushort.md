# CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)

- ea: `0x14000e324`
- end: `0x14000e414`
- name: `??0CSxFunctionTracer@@QEAA@PEBDGG@Z`
- size: `240`
- prototype: `CSxFunctionTracer *__fastcall(CSxFunctionTracer *this, const char *, __int16, __int16)`
- caller_count: `50`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b3c`
- `0x140001dec`
- `0x1400020c4`
- `0x1400022c0`
- `0x140002484`
- `0x140002670`
- `0x1400029b4`
- `0x140002ae8`
- `0x140002f30`
- `0x14000312c`
- `0x140003320`
- `0x140003584`
- `0x14000372c`
- `0x1400039e4`
- `0x140003dc4`
- `0x140003e70`
- `0x1400041ec`
- `0x140004410`
- `0x1400047e4`
- `0x140004a70`
- `0x1400050f0`
- `0x140005784`
- `0x14000595c`
- `0x140005ac0`
- `0x140005c10`
- `0x140005eb0`
- `0x140006018`
- `0x140006334`
- `0x1400066e0`
- `0x1400068d4`
- `0x140006ab0`
- `0x140006e40`
- `0x140007030`
- `0x1400074d8`
- `0x1400075cc`
- `0x14000771c`
- `0x140007954`
- `0x14000d688`
- `0x14000de58`
- `0x14000e0f0`
- `0x14000ec40`
- `0x14000ed4c`
- `0x14000ef3c`
- `0x14000f0b0`
- `0x14000f188`
- `0x14000f24c`
- `0x14000f510`
- `0x14000f7a0`
- `0x14000fa1c`
- `0x14000fd0c`

## callees

- `0x140002e44`
- `0x14000e324`
- `0x14000ea74`

## import_xrefs

- `SPP!SxTracerGetThreadContextRetail` at `0x14000e35e`
- `SPP!SxTracerGetThreadContextRetail` at `0x14000e35e`

## pseudocode

```c
CSxFunctionTracer *__fastcall CSxFunctionTracer::CSxFunctionTracer(
        CSxFunctionTracer *this,
        const char *a2,
        __int16 a3,
        __int16 a4)
{
  char *v4; // rdi
  int ThreadContextRetail; // eax
  __int64 v7; // r8
  __int64 v8; // rcx
  _DWORD *v9; // rcx
  __int64 v10; // rdx

  *((_WORD *)this + 2) = a3;
  *(_DWORD *)this = 0;
  v4 = (char *)this + 32;
  *((_WORD *)this + 6) = a4;
  *((_QWORD *)this + 2) = a2;
  *((_QWORD *)this + 3) = 0;
  *((_WORD *)this + 3) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_DWORD *)this + 12) = 0;
  *((_QWORD *)this + 4) = 0;
  ThreadContextRetail = SxTracerGetThreadContextRetail((char *)this + 32);
  if ( ThreadContextRetail >= 0 )
  {
    v8 = *(_QWORD *)v4;
    *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)v4 + 32LL);
    *(_QWORD *)(v8 + 32) = this;
LABEL_6:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_7;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids,
      (unsigned int)ThreadContextRetail);
    goto LABEL_6;
  }
LABEL_7:
  if ( *((_WORD *)this + 6) )
  {
    if ( *((_WORD *)this + 6) == 1 )
    {
      if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x20000000) != 0 )
      {
        v10 = 12;
        goto LABEL_18;
      }
    }
    else if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x20000) != 0 )
    {
      v10 = 13;
      goto LABEL_18;
    }
  }
  else if ( v9 != (_DWORD *)&WPP_GLOBAL_Control && (v9[7] & 0x8000000) != 0 )
  {
    v10 = 11;
LABEL_18:
    WPP_SF_s(*((_QWORD *)v9 + 2), v10, v7, *((_QWORD *)this + 2));
  }
  return this;
}

```

## disassembly

```asm
0x14000e324  push    rbx
0x14000e326  push    rbp
0x14000e327  push    rsi
0x14000e328  push    rdi
0x14000e329  sub     rsp, 28h
0x14000e32d  xor     ebp, ebp
0x14000e32f  mov     [rcx+4], r8w
0x14000e334  mov     [rcx], ebp
0x14000e336  lea     rdi, [rcx+20h]
0x14000e33a  mov     [rcx+0Ch], r9w
0x14000e33f  mov     rbx, rcx
0x14000e342  mov     [rcx+10h], rdx
0x14000e346  mov     [rcx+18h], rbp
0x14000e34a  mov     [rcx+6], bp
0x14000e34e  mov     [rcx+8], ebp
0x14000e351  mov     [rcx+28h], rbp
0x14000e355  mov     [rcx+30h], ebp
0x14000e358  mov     rcx, rdi
0x14000e35b  mov     [rdi], rbp
0x14000e35e  call    cs:__imp_SxTracerGetThreadContextRetail
0x14000e364  lea     rsi, WPP_GLOBAL_Control
0x14000e36b  test    eax, eax
0x14000e36d  js      short loc_14000E380
0x14000e36f  mov     rcx, [rdi]
0x14000e372  mov     rax, [rcx+20h]
0x14000e376  mov     [rbx+18h], rax
0x14000e37a  mov     [rcx+20h], rbx
0x14000e37e  jmp     short loc_14000E3AA
0x14000e380  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e387  cmp     rcx, rsi
0x14000e38a  jz      short loc_14000E3B1
0x14000e38c  test    byte ptr [rcx+1Ch], 1
0x14000e390  jz      short loc_14000E3B1
0x14000e392  mov     rcx, [rcx+10h]
0x14000e396  lea     r8, WPP_15615b0606aa3464fc953e2bc9390e30_Traceguids
0x14000e39d  mov     edx, 0Ah
0x14000e3a2  mov     r9d, eax
0x14000e3a5  call    WPP_SF_d
0x14000e3aa  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e3b1  cmp     [rbx+0Ch], bp
0x14000e3b5  jnz     short loc_14000E3CC
0x14000e3b7  cmp     rcx, rsi
0x14000e3ba  jz      short loc_14000E408
0x14000e3bc  test    dword ptr [rcx+1Ch], 8000000h
0x14000e3c3  jz      short loc_14000E408
0x14000e3c5  mov     edx, 0Bh
0x14000e3ca  jmp     short loc_14000E3FB
0x14000e3cc  cmp     word ptr [rbx+0Ch], 1
0x14000e3d1  jnz     short loc_14000E3E8
0x14000e3d3  cmp     rcx, rsi
0x14000e3d6  jz      short loc_14000E408
0x14000e3d8  test    dword ptr [rcx+1Ch], 20000000h
0x14000e3df  jz      short loc_14000E408
0x14000e3e1  mov     edx, 0Ch
0x14000e3e6  jmp     short loc_14000E3FB
0x14000e3e8  cmp     rcx, rsi
0x14000e3eb  jz      short loc_14000E408
0x14000e3ed  test    dword ptr [rcx+1Ch], 20000h
0x14000e3f4  jz      short loc_14000E408
0x14000e3f6  mov     edx, 0Dh
0x14000e3fb  mov     r9, [rbx+10h]
0x14000e3ff  mov     rcx, [rcx+10h]
0x14000e403  call    WPP_SF_s
0x14000e408  mov     rax, rbx
0x14000e40b  add     rsp, 28h
0x14000e40f  pop     rdi
0x14000e410  pop     rsi
0x14000e411  pop     rbp
0x14000e412  pop     rbx
0x14000e413  retn
```
