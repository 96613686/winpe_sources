# WMNewResize

- ea: `0x180013230`
- end: `0x18001340b`
- name: `WMNewResize`
- size: `475`
- prototype: `__int64 __fastcall(WMSDKRESIZER *this, unsigned __int8 *, __int64, _DWORD *, unsigned __int8 *, unsigned int, _DWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007e90`
- `0x180013420`

## callees

- `0x1800125b0`
- `0x1800129d0`
- `0x180013230`
- `0x180013b90`
- `0x180013e90`

## pseudocode

```c
__int64 __fastcall WMNewResize(
        WMSDKRESIZER *this,
        unsigned __int8 *a2,
        __int64 a3,
        _DWORD *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        _DWORD *a7)
{
  unsigned int v8; // ebp
  _DWORD *v11; // r14
  unsigned __int8 *v12; // rsi
  __int64 result; // rax
  int v14; // r9d
  unsigned int v15; // r12d
  unsigned int v16; // ebp
  int v17; // r9d
  int v18; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+44h] [rbp-34h] BYREF
  int v20; // [rsp+48h] [rbp-30h] BYREF
  int v21; // [rsp+98h] [rbp+20h] BYREF

  v8 = a3;
  if ( !a4 )
    return 1;
  v11 = a7;
  if ( !a7 )
    return 1;
  if ( !this )
    return 1;
  if ( !a2 )
    return 1;
  v12 = a5;
  if ( !a5 )
    return 1;
  if ( !*((_DWORD *)this + 271) )
    return WMResizeWithFullCropping(this, a2, a3);
  v14 = *((_DWORD *)this + 16);
  v21 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  *((_DWORD *)this + 199) = 0;
  *((_DWORD *)this + 250) = 0;
  if ( !(unsigned int)WMSDKRESIZER::getField(this, a2, 0, v14) )
    return 1;
  v15 = a6 >> 1;
  v16 = v8 >> 1;
  result = WMResize_old(this, *((_QWORD *)this + 137), v16, &v21, *((_QWORD *)this + 138), a6 >> 1, &v19);
  if ( (_DWORD)result )
    return result;
  if ( !(unsigned int)WMSDKRESIZER::putField(this, v12, 0, *((_DWORD *)this + 17)) )
    return 1;
  v17 = *((_DWORD *)this + 16);
  *((_DWORD *)this + 199) = 1;
  *((_DWORD *)this + 250) = 1;
  if ( !(unsigned int)WMSDKRESIZER::getField(this, a2, 1, v17) )
    return 1;
  result = WMResize_old(this, *((_QWORD *)this + 137), v16, &v18, *((_QWORD *)this + 138), v15, &v20);
  if ( (_DWORD)result )
    return result;
  if ( !(unsigned int)WMSDKRESIZER::putField(this, v12, 1, *((_DWORD *)this + 17)) )
    return 1;
  result = 0;
  *a4 = v18 + v21;
  *v11 = v20 + v19;
  return result;
}

```

## disassembly

```asm
0x180013230  mov     [rsp+arg_0], rbx
0x180013235  mov     [rsp+arg_8], rbp
0x18001323a  push    rsi
0x18001323b  push    rdi
0x18001323c  push    r12
0x18001323e  push    r14
0x180013240  push    r15
0x180013242  sub     rsp, 50h
0x180013246  mov     r15, r9
0x180013249  mov     ebp, r8d
0x18001324c  mov     rdi, rdx
0x18001324f  mov     rbx, rcx
0x180013252  test    r9, r9
0x180013255  jz      loc_1800133ED
0x18001325b  mov     r14, [rsp+78h+arg_30]
0x180013263  test    r14, r14
0x180013266  jz      loc_1800133ED
0x18001326c  test    rcx, rcx
0x18001326f  jz      loc_1800133ED
0x180013275  test    rdx, rdx
0x180013278  jz      loc_1800133ED
0x18001327e  mov     rsi, [rsp+78h+arg_20]
0x180013286  test    rsi, rsi
0x180013289  jz      loc_1800133ED
0x18001328f  cmp     dword ptr [rcx+43Ch], 0
0x180013296  jnz     short loc_1800132B9
0x180013298  mov     eax, [rsp+78h+arg_28]
0x18001329f  mov     [rsp+78h+var_48], r14
0x1800132a4  mov     [rsp+78h+var_50], eax
0x1800132a8  mov     [rsp+78h+var_58], rsi
0x1800132ad  call    WMResizeWithFullCropping
0x1800132b2  mov     edi, eax
0x1800132b4  jmp     loc_1800133F2
0x1800132b9  mov     r9d, [rcx+40h]; int
0x1800132bd  xor     eax, eax
0x1800132bf  xor     r8d, r8d; int
0x1800132c2  mov     [rsp+78h+arg_18], eax
0x1800132c9  mov     [rsp+78h+var_38], eax
0x1800132cd  mov     [rsp+78h+var_34], eax
0x1800132d1  mov     [rsp+78h+var_30], eax
0x1800132d5  mov     [rcx+31Ch], eax
0x1800132db  mov     [rcx+3E8h], eax
0x1800132e1  call    ?getField@WMSDKRESIZER@@QEAAHPEBEJH@Z; WMSDKRESIZER::getField(uchar const *,long,int)
0x1800132e6  test    eax, eax
0x1800132e8  jz      loc_1800133ED
0x1800132ee  mov     r12d, [rsp+78h+arg_28]
0x1800132f6  lea     rax, [rsp+78h+var_34]
0x1800132fb  mov     rdx, [rbx+448h]
0x180013302  lea     r9, [rsp+78h+arg_18]
0x18001330a  mov     [rsp+78h+var_48], rax
0x18001330f  mov     rcx, rbx
0x180013312  mov     rax, [rbx+450h]
0x180013319  shr     r12d, 1
0x18001331c  shr     ebp, 1
0x18001331e  mov     [rsp+78h+var_50], r12d
0x180013323  mov     r8d, ebp
0x180013326  mov     [rsp+78h+var_58], rax
0x18001332b  call    WMResize_old
0x180013330  test    eax, eax
0x180013332  jnz     loc_1800133F2
0x180013338  mov     r9d, [rbx+44h]; int
0x18001333c  xor     r8d, r8d; int
0x18001333f  mov     rdx, rsi; unsigned __int8 *
0x180013342  mov     rcx, rbx; this
0x180013345  call    ?putField@WMSDKRESIZER@@QEAAHPEAEJH@Z; WMSDKRESIZER::putField(uchar *,long,int)
0x18001334a  test    eax, eax
0x18001334c  jz      loc_1800133ED
0x180013352  mov     r9d, [rbx+40h]; int
0x180013356  mov     r8d, 1; int
0x18001335c  mov     rdx, rdi; unsigned __int8 *
0x18001335f  mov     dword ptr [rbx+31Ch], 1
0x180013369  mov     rcx, rbx; this
0x18001336c  mov     dword ptr [rbx+3E8h], 1
0x180013376  call    ?getField@WMSDKRESIZER@@QEAAHPEBEJH@Z; WMSDKRESIZER::getField(uchar const *,long,int)
0x18001337b  test    eax, eax
0x18001337d  jz      short loc_1800133ED
0x18001337f  mov     rdx, [rbx+448h]
0x180013386  lea     rax, [rsp+78h+var_30]
0x18001338b  mov     [rsp+78h+var_48], rax
0x180013390  lea     r9, [rsp+78h+var_38]
0x180013395  mov     rax, [rbx+450h]
0x18001339c  mov     r8d, ebp
0x18001339f  mov     [rsp+78h+var_50], r12d
0x1800133a4  mov     rcx, rbx
0x1800133a7  mov     [rsp+78h+var_58], rax
0x1800133ac  call    WMResize_old
0x1800133b1  mov     edi, eax
0x1800133b3  test    eax, eax
0x1800133b5  jnz     short loc_1800133F2
0x1800133b7  mov     r9d, [rbx+44h]; int
0x1800133bb  mov     r8d, 1; int
0x1800133c1  mov     rdx, rsi; unsigned __int8 *
0x1800133c4  mov     rcx, rbx; this
0x1800133c7  call    ?putField@WMSDKRESIZER@@QEAAHPEAEJH@Z; WMSDKRESIZER::putField(uchar *,long,int)
0x1800133cc  test    eax, eax
0x1800133ce  jz      short loc_1800133ED
0x1800133d0  mov     ecx, [rsp+78h+arg_18]
0x1800133d7  mov     eax, edi
0x1800133d9  add     ecx, [rsp+78h+var_38]
0x1800133dd  mov     [r15], ecx
0x1800133e0  mov     ecx, [rsp+78h+var_34]
0x1800133e4  add     ecx, [rsp+78h+var_30]
0x1800133e8  mov     [r14], ecx
0x1800133eb  jmp     short loc_1800133F2
0x1800133ed  mov     eax, 1
0x1800133f2  lea     r11, [rsp+78h+var_28]
0x1800133f7  mov     rbx, [r11+30h]
0x1800133fb  mov     rbp, [r11+38h]
0x1800133ff  mov     rsp, r11
0x180013402  pop     r15
0x180013404  pop     r14
0x180013406  pop     r12
0x180013408  pop     rdi
0x180013409  pop     rsi
0x18001340a  retn
```
