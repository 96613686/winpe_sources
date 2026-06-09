# RtlpCSparseBitmapPageDecommit

- ea: `0x1400cb184`
- end: `0x1400cb505`
- name: `RtlpCSparseBitmapPageDecommit`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400ca84c`

## callees

- `0x1400364c4`
- `0x14006962c`
- `0x140095cd8`
- `0x1400cb184`
- `0x1400d37ec`
- `0x1400d3824`
- `0x1400d3894`

## pseudocode

```c
char __fastcall RtlpCSparseBitmapPageDecommit(_QWORD *a1, unsigned __int64 a2)
{
  _QWORD *v3; // r12
  unsigned __int64 v4; // rax
  __int64 v5; // r15
  unsigned __int64 v6; // rbx
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rax
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // r9
  int v11; // r11d
  __int64 v12; // r13
  unsigned __int64 v13; // rax
  int v14; // ecx
  bool v15; // zf
  _QWORD *v16; // rdx
  __int64 v17; // rdx
  volatile signed __int32 **v18; // rdx
  int v19; // ecx
  bool v20; // zf
  unsigned __int64 *v21; // rdx
  bool j; // zf
  _QWORD *StackBase; // rcx
  __int64 v24; // rdx
  signed __int32 v26[8]; // [rsp+0h] [rbp-B8h] BYREF
  const signed __int64 **v27; // [rsp+20h] [rbp-98h]
  int v28; // [rsp+28h] [rbp-90h]
  _QWORD *i; // [rsp+30h] [rbp-88h]
  unsigned __int64 v30; // [rsp+38h] [rbp-80h]
  __int64 v31; // [rsp+40h] [rbp-78h]
  unsigned __int64 v32; // [rsp+48h] [rbp-70h]
  unsigned __int64 v33; // [rsp+50h] [rbp-68h]
  _QWORD *v34; // [rsp+58h] [rbp-60h]
  __int128 v35; // [rsp+60h] [rbp-58h] BYREF
  _QWORD v36[9]; // [rsp+70h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp+10h] BYREF
  int v39; // [rsp+D0h] [rbp+18h]
  unsigned __int64 v40; // [rsp+D8h] [rbp+20h] BYREF

  v38 = a2;
  v3 = a1;
  v27 = (const signed __int64 **)a1;
  v35 = 0;
  v39 = 0;
  v4 = a1[2];
  v34 = a1 + 1;
  v30 = v4;
  v5 = a1[1];
  v31 = v5;
  v6 = a2 << 15;
  v32 = a2 << 15;
  v7 = 0x8000;
  v8 = v4 - (a2 << 15);
  if ( v8 <= 0x8000 )
    v7 = v8;
  v33 = v7;
  RtlCSparseBitmapEnterLockingRegion(v36, a1);
  v12 = (unsigned int)(v11 + 1);
  while ( 1 )
  {
    if ( (_DWORD)v9 )
      goto LABEL_22;
    LOBYTE(v13) = v30;
    if ( v6 < v30 && v7 )
    {
      if ( v7 == v12 )
      {
        LOBYTE(v13) = _bittest64((const signed __int64 *)(v5 + 8 * (v6 >> 6)), 0);
        v14 = 0;
        v15 = (_BYTE)v13 == 0;
LABEL_9:
        LOBYTE(v14) = v15;
        goto LABEL_21;
      }
      LOBYTE(v13) = v30 - v6;
      if ( v30 - v6 >= v7 )
      {
        v16 = (_QWORD *)(v5 + 8 * (v6 >> 6));
        i = v16;
        v10 = v5 + 8 * ((v7 + v6 - 1) >> 6);
        v9 = *v16;
        if ( v16 == (_QWORD *)v10 )
        {
          v13 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v7) << v6;
          v15 = (v13 & v9) == 0;
LABEL_13:
          v14 = 0;
          goto LABEL_9;
        }
        v13 = -1LL << v6;
        if ( ((-1LL << v6) & v9) == 0 )
        {
          v13 = (unsigned __int64)(v16 + 1);
          for ( i = v16 + 1; ; i = (_QWORD *)v13 )
          {
            v17 = *(_QWORD *)v13;
            if ( v13 == v10 )
              break;
            if ( v17 )
              goto LABEL_20;
            v13 += 8LL;
          }
          v13 = 0xFFFFFFFFFFFFFFFFuLL >> ~((unsigned __int8)v7 + (unsigned __int8)v6 - 1);
          v15 = (v13 & v17) == 0;
          goto LABEL_13;
        }
      }
    }
LABEL_20:
    v14 = 0;
LABEL_21:
    v28 = v14;
    if ( !v14 )
      goto LABEL_41;
LABEL_22:
    RtlpCSparseBitmapLock(v3, (unsigned int)v12, &v35);
    v36[0] = v3[4];
    if ( v36[0] == -1 )
      break;
    RtlpCSparseBitmapUnlock(&v35);
    RtlpCSparseBitmapWaitOnAddress(v3 + 4, v36);
    LOBYTE(v13) = (_BYTE)v27;
    if ( !_bittest64(*v27, a2) )
      goto LABEL_41;
    v9 = 0;
    v3 = a1;
  }
  v3[4] = a2;
  RtlpCSparseBitmapUnlock(&v35);
  v39 = v12;
  v18 = (volatile signed __int32 **)v27;
  v13 = (unsigned __int64)*v27;
  if ( _bittest64(*v27, a2) )
  {
    LOBYTE(v13) = v30;
    if ( v6 < v30 )
    {
      if ( v7 )
      {
        if ( v7 == v12 )
        {
          LOBYTE(v13) = _bittest64((const signed __int64 *)(v5 + 8 * (v6 >> 6)), 0);
          v19 = 0;
          v20 = (_BYTE)v13 == 0;
          goto LABEL_39;
        }
        LOBYTE(v13) = v30 - v6;
        if ( v30 - v6 >= v7 )
        {
          v21 = (unsigned __int64 *)(v5 + 8 * (v6 >> 6));
          v9 = v5 + 8 * ((v7 + v6 - 1) >> 6);
          v10 = *v21;
          if ( v21 == (unsigned __int64 *)v9 )
          {
            v13 = 0xFFFFFFFFFFFFFFFFuLL >> (64 - (unsigned __int8)v7) << v6;
            v20 = (v13 & v10) == 0;
LABEL_38:
            v18 = (volatile signed __int32 **)v27;
            v19 = 0;
LABEL_39:
            LOBYTE(v19) = v20;
            if ( v19 )
            {
              _interlockedbittestandreset64(*v18, a2);
              v40 = *v34 + (a2 << 12);
              v38 = 4096;
              LOBYTE(v13) = SkmmFreePoolMemory(&v40, &v38, 1073758208);
            }
          }
          else
          {
            v13 = -1LL << v6;
            for ( j = ((-1LL << v6) & v10) == 0; j; j = *v21 == 0 )
            {
              if ( ++v21 == (unsigned __int64 *)v9 )
              {
                v13 = 0xFFFFFFFFFFFFFFFFuLL >> ~((unsigned __int8)v7 + (unsigned __int8)v6 - 1);
                v20 = (v13 & *v21) == 0;
                goto LABEL_38;
              }
            }
          }
        }
      }
    }
  }
LABEL_41:
  if ( v39 )
  {
    LOBYTE(v13) = (_BYTE)a1;
    a1[4] = -1;
    _InterlockedOr(v26, 0);
  }
  StackBase = KeGetPcr()->NtTib.StackBase;
  v24 = StackBase[18];
  if ( v24 )
  {
    LOBYTE(v13) = BYTE8(xmmword_140167150);
    v15 = (_WORD)v12 + *(_WORD *)(v24 + *((_QWORD *)&xmmword_140167150 + 1)) == 0;
    *(_WORD *)(v24 + *((_QWORD *)&xmmword_140167150 + 1)) += v12;
    if ( v15 )
    {
      v13 = xmmword_140167160 + StackBase[17];
      if ( *(_QWORD *)(v24 + xmmword_140167160) != v13 )
        LOBYTE(v13) = SkiCheckForKernelApcDelivery(xmmword_140167160, v24, v9, v10);
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1400cb184  mov     [rsp+arg_8], rdx
0x1400cb189  mov     [rsp+arg_0], rcx
0x1400cb18e  push    rbx
0x1400cb18f  push    rsi
0x1400cb190  push    rdi
0x1400cb191  push    r12
0x1400cb193  push    r13
0x1400cb195  push    r14
0x1400cb197  push    r15
0x1400cb199  sub     rsp, 80h
0x1400cb1a0  mov     rsi, rdx
0x1400cb1a3  mov     r12, rcx
0x1400cb1a6  mov     [rsp+0B8h+var_98], rcx
0x1400cb1ab  xorps   xmm0, xmm0
0x1400cb1ae  movups  [rsp+0B8h+var_58], xmm0
0x1400cb1b3  xor     r11d, r11d
0x1400cb1b6  mov     [rsp+0B8h+arg_10], r11d
0x1400cb1be  mov     rax, [rcx+10h]
0x1400cb1c2  add     rcx, 8
0x1400cb1c6  mov     [rsp+0B8h+var_60], rcx
0x1400cb1cb  mov     [rsp+0B8h+var_80], rax
0x1400cb1d0  mov     r15, [rcx]
0x1400cb1d3  mov     [rsp+0B8h+var_78], r15
0x1400cb1d8  mov     rbx, rdx
0x1400cb1db  shl     rbx, 0Fh
0x1400cb1df  mov     [rsp+0B8h+var_70], rbx
0x1400cb1e4  mov     edi, 8000h
0x1400cb1e9  sub     rax, rbx
0x1400cb1ec  cmp     rax, rdi
0x1400cb1ef  cmovbe  rdi, rax
0x1400cb1f3  mov     [rsp+0B8h+var_68], rdi
0x1400cb1f8  mov     rdx, r12
0x1400cb1fb  lea     rcx, [rsp+0B8h+var_48]
0x1400cb200  call    RtlCSparseBitmapEnterLockingRegion
0x1400cb205  lea     r13d, [r11+1]
0x1400cb209  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400cb20d  test    r8d, r8d
0x1400cb210  jnz     loc_1400CB322
0x1400cb216  mov     rax, [rsp+0B8h+var_80]
0x1400cb21b  cmp     rbx, rax
0x1400cb21e  jnb     loc_1400CB2DE
0x1400cb224  test    rdi, rdi
0x1400cb227  jz      loc_1400CB2DE
0x1400cb22d  cmp     rdi, r13
0x1400cb230  jnz     short loc_1400CB24E
0x1400cb232  mov     rax, rbx
0x1400cb235  shr     rax, 6
0x1400cb239  bt      qword ptr [r15+rax*8], 0
0x1400cb23f  setb    al
0x1400cb242  xor     ecx, ecx
0x1400cb244  test    al, al
0x1400cb246  setz    cl
0x1400cb249  jmp     loc_1400CB2E0
0x1400cb24e  sub     rax, rbx
0x1400cb251  cmp     rax, rdi
0x1400cb254  jb      loc_1400CB2DE
0x1400cb25a  lea     r10, [rbx-1]
0x1400cb25e  add     r10, rdi
0x1400cb261  mov     rax, rbx
0x1400cb264  shr     rax, 6
0x1400cb268  lea     rdx, [r15+rax*8]
0x1400cb26c  mov     [rsp+0B8h+var_88], rdx
0x1400cb271  mov     rax, r10
0x1400cb274  shr     rax, 6
0x1400cb278  lea     r9, [r15+rax*8]
0x1400cb27c  mov     r8, [rdx]
0x1400cb27f  mov     rax, r14
0x1400cb282  cmp     rdx, r9
0x1400cb285  jnz     short loc_1400CB2A2
0x1400cb287  mov     ecx, 40h ; '@'
0x1400cb28c  sub     cl, dil
0x1400cb28f  shr     rax, cl
0x1400cb292  mov     rcx, rbx
0x1400cb295  shl     rax, cl
0x1400cb298  test    r8, rax
0x1400cb29b  mov     ecx, 0
0x1400cb2a0  jmp     short loc_1400CB246
0x1400cb2a2  mov     rcx, rbx
0x1400cb2a5  shl     rax, cl
0x1400cb2a8  test    r8, rax
0x1400cb2ab  jnz     short loc_1400CB2DE
0x1400cb2ad  lea     rax, [rdx+8]
0x1400cb2b1  mov     [rsp+0B8h+var_88], rax
0x1400cb2b6  mov     rdx, [rax]
0x1400cb2b9  cmp     rax, r9
0x1400cb2bc  jz      short loc_1400CB2CE
0x1400cb2be  test    rdx, rdx
0x1400cb2c1  jnz     short loc_1400CB2DE
0x1400cb2c3  add     rax, 8
0x1400cb2c7  mov     [rsp+0B8h+var_88], rax
0x1400cb2cc  jmp     short loc_1400CB2B6
0x1400cb2ce  mov     cl, r10b
0x1400cb2d1  not     cl
0x1400cb2d3  mov     rax, r14
0x1400cb2d6  shr     rax, cl
0x1400cb2d9  test    rdx, rax
0x1400cb2dc  jmp     short loc_1400CB29B
0x1400cb2de  xor     ecx, ecx
0x1400cb2e0  mov     [rsp+0B8h+var_90], ecx
0x1400cb2e4  jmp     short loc_1400CB31A
0x1400cb2e6  xor     ecx, ecx
0x1400cb2e8  mov     [rsp+0B8h+var_90], ecx
0x1400cb2ec  lea     r13d, [rcx+1]
0x1400cb2f0  or      r14, 0FFFFFFFFFFFFFFFFh
0x1400cb2f4  mov     rsi, [rsp+0B8h+arg_8]
0x1400cb2fc  mov     r15, [rsp+0B8h+var_78]
0x1400cb301  mov     [rsp+0B8h+arg_10], ecx
0x1400cb308  mov     rbx, [rsp+0B8h+var_70]
0x1400cb30d  mov     rdi, [rsp+0B8h+var_68]
0x1400cb312  mov     r12, [rsp+0B8h+arg_0]
0x1400cb31a  test    ecx, ecx
0x1400cb31c  jz      loc_1400CB495
0x1400cb322  lea     r8, [rsp+0B8h+var_58]
0x1400cb327  mov     edx, r13d
0x1400cb32a  mov     rcx, r12
0x1400cb32d  call    RtlpCSparseBitmapLock
0x1400cb332  mov     rax, [r12+20h]
0x1400cb337  mov     [rsp+0B8h+var_48], rax
0x1400cb33c  lea     rcx, [rsp+0B8h+var_58]
0x1400cb341  cmp     rax, r14
0x1400cb344  jz      short loc_1400CB37C
0x1400cb346  call    RtlpCSparseBitmapUnlock
0x1400cb34b  lea     rdx, [rsp+0B8h+var_48]
0x1400cb350  lea     rcx, [r12+20h]
0x1400cb355  call    RtlpCSparseBitmapWaitOnAddress
0x1400cb35a  mov     rax, [rsp+0B8h+var_98]
0x1400cb35f  mov     rcx, [rax]
0x1400cb362  bt      [rcx], rsi
0x1400cb366  jnb     loc_1400CB495
0x1400cb36c  xor     r8d, r8d
0x1400cb36f  mov     r12, [rsp+0B8h+arg_0]
0x1400cb377  jmp     loc_1400CB20D
0x1400cb37c  mov     [r12+20h], rsi
0x1400cb381  call    RtlpCSparseBitmapUnlock
0x1400cb386  mov     [rsp+0B8h+arg_10], r13d
0x1400cb38e  mov     rdx, [rsp+0B8h+var_98]
0x1400cb393  mov     rax, [rdx]
0x1400cb396  bt      [rax], rsi
0x1400cb39a  jnb     loc_1400CB495
0x1400cb3a0  mov     rax, [rsp+0B8h+var_80]
0x1400cb3a5  cmp     rbx, rax
0x1400cb3a8  jnb     loc_1400CB495
0x1400cb3ae  test    rdi, rdi
0x1400cb3b1  jz      loc_1400CB495
0x1400cb3b7  cmp     rdi, r13
0x1400cb3ba  jnz     short loc_1400CB3CF
0x1400cb3bc  shr     rbx, 6
0x1400cb3c0  bt      qword ptr [r15+rbx*8], 0
0x1400cb3c6  setb    al
0x1400cb3c9  xor     ecx, ecx
0x1400cb3cb  test    al, al
0x1400cb3cd  jmp     short loc_1400CB44B
0x1400cb3cf  sub     rax, rbx
0x1400cb3d2  cmp     rax, rdi
0x1400cb3d5  jb      loc_1400CB495
0x1400cb3db  lea     r10, [rbx-1]
0x1400cb3df  add     r10, rdi
0x1400cb3e2  mov     rax, rbx
0x1400cb3e5  shr     rax, 6
0x1400cb3e9  lea     rdx, [r15+rax*8]
0x1400cb3ed  mov     rax, r10
0x1400cb3f0  shr     rax, 6
0x1400cb3f4  lea     r8, [r15+rax*8]
0x1400cb3f8  mov     r9, [rdx]
0x1400cb3fb  mov     rax, r14
0x1400cb3fe  cmp     rdx, r8
0x1400cb401  jnz     short loc_1400CB419
0x1400cb403  mov     ecx, 40h ; '@'
0x1400cb408  sub     cl, dil
0x1400cb40b  shr     rax, cl
0x1400cb40e  mov     rcx, rbx
0x1400cb411  shl     rax, cl
0x1400cb414  test    r9, rax
0x1400cb417  jmp     short loc_1400CB441
0x1400cb419  mov     rcx, rbx
0x1400cb41c  shl     rax, cl
0x1400cb41f  test    r9, rax
0x1400cb422  jmp     short loc_1400CB428
0x1400cb424  cmp     qword ptr [rdx], 0
0x1400cb428  jnz     short loc_1400CB495
0x1400cb42a  add     rdx, 8
0x1400cb42e  cmp     rdx, r8
0x1400cb431  jnz     short loc_1400CB424
0x1400cb433  mov     cl, r10b
0x1400cb436  not     cl
0x1400cb438  mov     rax, r14
0x1400cb43b  shr     rax, cl
0x1400cb43e  test    [rdx], rax
0x1400cb441  mov     rdx, [rsp+0B8h+var_98]
0x1400cb446  mov     ecx, 0
0x1400cb44b  setz    cl
0x1400cb44e  test    ecx, ecx
0x1400cb450  jz      short loc_1400CB495
0x1400cb452  mov     rax, [rdx]
0x1400cb455  lock btr [rax], rsi
0x1400cb45a  shl     rsi, 0Ch
0x1400cb45e  mov     rax, [rsp+0B8h+var_60]
0x1400cb463  add     rsi, [rax]
0x1400cb466  mov     [rsp+0B8h+arg_18], rsi
0x1400cb46e  mov     [rsp+0B8h+arg_8], 1000h
0x1400cb47a  mov     r8d, 40004000h
0x1400cb480  lea     rdx, [rsp+0B8h+arg_8]
0x1400cb488  lea     rcx, [rsp+0B8h+arg_18]
0x1400cb490  call    SkmmFreePoolMemory
0x1400cb495  cmp     [rsp+0B8h+arg_10], 0
0x1400cb49d  jz      short loc_1400CB4B0
0x1400cb49f  mov     rax, [rsp+0B8h+arg_0]
0x1400cb4a7  mov     [rax+20h], r14
0x1400cb4ab  lock or [rsp+0B8h+var_B8], 0
0x1400cb4b0  mov     rcx, gs:8
0x1400cb4b9  mov     rdx, [rcx+90h]
0x1400cb4c0  test    rdx, rdx
0x1400cb4c3  jz      short loc_1400CB4F1
0x1400cb4c5  nop
0x1400cb4c6  mov     rax, qword ptr cs:xmmword_140167150+8
0x1400cb4cd  add     [rdx+rax], r13w
0x1400cb4d2  jnz     short loc_1400CB4F1
0x1400cb4d4  mov     rax, [rcx+88h]
0x1400cb4db  nop
0x1400cb4dc  mov     rcx, qword ptr cs:xmmword_140167160
0x1400cb4e3  add     rax, rcx
0x1400cb4e6  cmp     [rdx+rcx], rax
0x1400cb4ea  jz      short loc_1400CB4F1
0x1400cb4ec  call    SkiCheckForKernelApcDelivery
0x1400cb4f1  add     rsp, 80h
0x1400cb4f8  pop     r15
0x1400cb4fa  pop     r14
0x1400cb4fc  pop     r13
0x1400cb4fe  pop     r12
0x1400cb500  pop     rdi
0x1400cb501  pop     rsi
0x1400cb502  pop     rbx
0x1400cb503  retn
```
