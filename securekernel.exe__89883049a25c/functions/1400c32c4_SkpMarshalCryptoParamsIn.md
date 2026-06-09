# SkpMarshalCryptoParamsIn

- ea: `0x1400c32c4`
- end: `0x1400c360e`
- name: `SkpMarshalCryptoParamsIn`
- size: `842`
- prototype: `__int64 __fastcall(void *Src, _WORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1400c2a28`

## callees

- `0x14000f0f0`
- `0x140040c7c`
- `0x1400c2d5c`
- `0x1400c32c4`
- `0x1400d4e8c`
- `0x1400f9a80`

## pseudocode

```c
__int64 __fastcall SkpMarshalCryptoParamsIn(void *Src, _WORD *a2)
{
  int v4; // ebx
  _QWORD *StackBase; // rax
  bool v6; // r15
  unsigned __int64 v7; // rdx
  unsigned __int64 v8; // rcx
  void *Pool; // rax
  size_t v10; // r8
  void *v11; // rax
  size_t v12; // r8
  __int64 v13; // rax
  __int64 v14; // rax
  void *v15; // rax
  _WORD v17[2]; // [rsp+20h] [rbp-98h] BYREF
  int v18; // [rsp+24h] [rbp-94h]
  int v19; // [rsp+28h] [rbp-90h]
  int v20; // [rsp+2Ch] [rbp-8Ch]
  __int64 v21; // [rsp+30h] [rbp-88h]
  size_t Size; // [rsp+38h] [rbp-80h]
  unsigned __int64 v23; // [rsp+40h] [rbp-78h]
  unsigned __int64 v24; // [rsp+48h] [rbp-70h]
  size_t v25; // [rsp+50h] [rbp-68h]
  void *Srca; // [rsp+58h] [rbp-60h]
  __int64 v27; // [rsp+60h] [rbp-58h]
  __int64 v28; // [rsp+68h] [rbp-50h]
  void *v29; // [rsp+70h] [rbp-48h]
  unsigned __int64 v30; // [rsp+78h] [rbp-40h]
  unsigned __int64 v31; // [rsp+80h] [rbp-38h]
  int v32; // [rsp+88h] [rbp-30h]
  __int64 v33; // [rsp+90h] [rbp-28h]
  void *v34; // [rsp+98h] [rbp-20h]

  v4 = 0;
  memset_0(v17, 0, 0x80u);
  memset_0(a2, 0, 0x80u);
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
    StackBase = (_QWORD *)StackBase[10];
  v6 = StackBase && (*(_DWORD *)StackBase & 0x200) != 0;
  if ( ((unsigned __int8)Src & 7) != 0 )
    ExRaiseDatatypeMisalignment();
  RtlCopyFromUser(v17, Src, 0x80u);
  *a2 = v17[0];
  *((_DWORD *)a2 + 1) = v18;
  *((_DWORD *)a2 + 2) = v19;
  *((_DWORD *)a2 + 3) = v20;
  *((_QWORD *)a2 + 2) = v21;
  v7 = v30;
  *((_QWORD *)a2 + 11) = v30;
  v8 = v31;
  *((_QWORD *)a2 + 12) = v31;
  *((_DWORD *)a2 + 26) = v32;
  *((_QWORD *)a2 + 14) = v33;
  if ( v7 )
  {
    if ( v23 )
    {
      if ( v23 != v7 )
        v4 = -1073741811;
      goto LABEL_52;
    }
    v23 = v7;
  }
  if ( v8 )
  {
    if ( v24 )
    {
      if ( v24 != v8 )
        goto LABEL_21;
    }
    else
    {
      v24 = v8;
    }
  }
  if ( Size )
  {
    if ( Size > 0xFFFFFFFF )
    {
LABEL_17:
      v4 = -1073741675;
LABEL_53:
      SkpCryptoFreeBuffers(a2);
      return (unsigned int)v4;
    }
    if ( !Srca || v6 && Size > 0xFFFF )
      goto LABEL_21;
    Pool = (void *)SkAllocatePool(1, Size);
    *((_QWORD *)a2 + 7) = Pool;
    if ( !Pool )
    {
LABEL_26:
      v4 = -1073741670;
      goto LABEL_53;
    }
    v10 = Size;
    *((_QWORD *)a2 + 3) = Size;
    RtlCopyFromUser(Pool, Srca, v10);
  }
  if ( v25 )
  {
    if ( v25 > 0xFFFFFFFF )
      goto LABEL_17;
    if ( !v29 || v6 && v25 > 0xFFFF )
      goto LABEL_21;
    v11 = (void *)SkAllocatePool(1, v25);
    *((_QWORD *)a2 + 10) = v11;
    if ( !v11 )
      goto LABEL_26;
    v12 = v25;
    *((_QWORD *)a2 + 6) = v25;
    RtlCopyFromUser(v11, v29, v12);
  }
  if ( v23 )
  {
    if ( v23 > 0xFFFFFFFF )
      goto LABEL_17;
    if ( !v27 || v6 && v23 > 0xFFFF )
      goto LABEL_21;
    v13 = SkAllocatePool(1, v23);
    *((_QWORD *)a2 + 8) = v13;
    if ( !v13 )
      goto LABEL_26;
    *((_QWORD *)a2 + 4) = v23;
  }
  if ( v24 )
  {
    if ( v24 > 0xFFFFFFFF )
      goto LABEL_17;
    if ( v28 && (!v6 || v24 <= 0xFFFF) )
    {
      v14 = SkAllocatePool(1, v24);
      *((_QWORD *)a2 + 9) = v14;
      if ( !v14 )
        goto LABEL_26;
      *((_QWORD *)a2 + 5) = v24;
      goto LABEL_49;
    }
LABEL_21:
    v4 = -1073741811;
    goto LABEL_53;
  }
LABEL_49:
  if ( v34 )
  {
    v15 = (void *)SkAllocatePool(1, 0x38u);
    *((_QWORD *)a2 + 15) = v15;
    if ( !v15 )
      goto LABEL_26;
    RtlCopyFromUser(v15, v34, 0x38u);
  }
LABEL_52:
  if ( v4 < 0 )
    goto LABEL_53;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400c32c4  mov     [rsp+arg_0], rbx
0x1400c32c9  mov     [rsp+arg_10], rsi
0x1400c32ce  mov     [rsp+arg_8], rdx
0x1400c32d3  push    rdi
0x1400c32d4  push    r14
0x1400c32d6  push    r15
0x1400c32d8  sub     rsp, 0A0h
0x1400c32df  mov     rdi, rdx
0x1400c32e2  mov     rsi, rcx
0x1400c32e5  xor     ebx, ebx
0x1400c32e7  mov     r14d, 80h
0x1400c32ed  mov     r8d, r14d; Size
0x1400c32f0  xor     edx, edx; Val
0x1400c32f2  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400c32f7  call    memset_0
0x1400c32fc  mov     r8d, r14d; Size
0x1400c32ff  xor     edx, edx; Val
0x1400c3301  mov     rcx, rdi; void *
0x1400c3304  call    memset_0
0x1400c3309  mov     rax, gs:8
0x1400c3312  test    rax, rax
0x1400c3315  jz      short loc_1400C331B
0x1400c3317  mov     rax, [rax+50h]
0x1400c331b  test    rax, rax
0x1400c331e  jz      short loc_1400C332D
0x1400c3320  test    dword ptr [rax], 200h
0x1400c3326  jz      short loc_1400C332D
0x1400c3328  mov     r15b, 1
0x1400c332b  jmp     short loc_1400C3330
0x1400c332d  xor     r15b, r15b
0x1400c3330  test    sil, 7
0x1400c3334  jz      short loc_1400C333C
0x1400c3336  call    ExRaiseDatatypeMisalignment
0x1400c333c  mov     r8, r14; Size
0x1400c333f  mov     rdx, rsi; Src
0x1400c3342  lea     rcx, [rsp+0B8h+var_98]; void *
0x1400c3347  call    RtlCopyFromUser
0x1400c334c  nop
0x1400c334d  mov     rax, [rsp+0B8h+var_98]
0x1400c3352  mov     [rdi], ax
0x1400c3355  mov     eax, dword ptr [rsp+0B8h+var_98+4]
0x1400c3359  mov     [rdi+4], eax
0x1400c335c  mov     eax, [rsp+0B8h+var_90]
0x1400c3360  mov     [rdi+8], eax
0x1400c3363  mov     eax, [rsp+0B8h+var_8C]
0x1400c3367  mov     [rdi+0Ch], eax
0x1400c336a  mov     rax, [rsp+0B8h+var_88]
0x1400c336f  mov     [rdi+10h], rax
0x1400c3373  mov     rdx, [rsp+0B8h+var_40]
0x1400c3378  mov     [rdi+58h], rdx
0x1400c337c  mov     rcx, [rsp+0B8h+var_38]
0x1400c3384  mov     [rdi+60h], rcx
0x1400c3388  mov     eax, [rsp+0B8h+var_30]
0x1400c338f  mov     [rdi+68h], eax
0x1400c3392  mov     rax, [rsp+0B8h+var_28]
0x1400c339a  mov     [rdi+70h], rax
0x1400c339e  test    rdx, rdx
0x1400c33a1  jz      short loc_1400C33B2
0x1400c33a3  mov     rax, [rsp+0B8h+var_78]
0x1400c33a8  test    rax, rax
0x1400c33ab  jnz     short loc_1400C33E7
0x1400c33ad  mov     [rsp+0B8h+var_78], rdx
0x1400c33b2  test    rcx, rcx
0x1400c33b5  jz      short loc_1400C33C4
0x1400c33b7  cmp     [rsp+0B8h+var_70], 0
0x1400c33bd  jnz     short loc_1400C33FA
0x1400c33bf  mov     [rsp+0B8h+var_70], rcx
0x1400c33c4  mov     rdx, [rsp+0B8h+Size]
0x1400c33c9  mov     r14d, 0FFFFFFFFh
0x1400c33cf  test    rdx, rdx
0x1400c33d2  jz      loc_1400C346C
0x1400c33d8  cmp     rdx, r14
0x1400c33db  jbe     short loc_1400C340B
0x1400c33dd  mov     ebx, 0C0000095h
0x1400c33e2  jmp     loc_1400C35EA
0x1400c33e7  cmp     rax, rdx
0x1400c33ea  jz      loc_1400C35E6
0x1400c33f0  mov     ebx, 0C000000Dh
0x1400c33f5  jmp     loc_1400C35E6
0x1400c33fa  cmp     [rsp+0B8h+var_70], rcx
0x1400c33ff  jz      short loc_1400C33C4
0x1400c3401  mov     ebx, 0C000000Dh
0x1400c3406  jmp     loc_1400C35EA
0x1400c340b  cmp     [rsp+0B8h+Src], 0
0x1400c3411  jz      short loc_1400C3401
0x1400c3413  mov     esi, 0FFFFh
0x1400c3418  test    r15b, r15b
0x1400c341b  jz      short loc_1400C3422
0x1400c341d  cmp     rdx, rsi
0x1400c3420  ja      short loc_1400C3401
0x1400c3422  mov     ecx, 1
0x1400c3427  mov     r8d, 42474E43h
0x1400c342d  call    SkAllocatePool
0x1400c3432  mov     [rdi+38h], rax
0x1400c3436  test    rax, rax
0x1400c3439  jnz     short loc_1400C3445
0x1400c343b  mov     ebx, 0C000009Ah
0x1400c3440  jmp     loc_1400C35EA
0x1400c3445  mov     r8, [rsp+0B8h+Size]; Size
0x1400c344a  mov     [rdi+18h], r8
0x1400c344e  mov     rdx, [rsp+0B8h+Src]; Src
0x1400c3453  mov     rcx, rax; void *
0x1400c3456  call    RtlCopyFromUser
0x1400c345b  jmp     short loc_1400C3471
0x1400c345d  mov     ebx, eax
0x1400c345f  mov     rdi, [rsp+0B8h+arg_8]
0x1400c3467  jmp     loc_1400C35E6
0x1400c346c  mov     esi, 0FFFFh
0x1400c3471  mov     rdx, [rsp+0B8h+var_68]
0x1400c3476  test    rdx, rdx
0x1400c3479  jz      short loc_1400C34DE
0x1400c347b  cmp     rdx, r14
0x1400c347e  ja      loc_1400C33DD
0x1400c3484  cmp     [rsp+0B8h+var_48], 0
0x1400c348a  jz      loc_1400C3401
0x1400c3490  test    r15b, r15b
0x1400c3493  jz      short loc_1400C349E
0x1400c3495  cmp     rdx, rsi
0x1400c3498  ja      loc_1400C3401
0x1400c349e  mov     ecx, 1
0x1400c34a3  mov     r8d, 42474E43h
0x1400c34a9  call    SkAllocatePool
0x1400c34ae  mov     [rdi+50h], rax
0x1400c34b2  test    rax, rax
0x1400c34b5  jz      short loc_1400C343B
0x1400c34b7  mov     r8, [rsp+0B8h+var_68]; Size
0x1400c34bc  mov     [rdi+30h], r8
0x1400c34c0  mov     rdx, [rsp+0B8h+var_48]; Src
0x1400c34c5  mov     rcx, rax; void *
0x1400c34c8  call    RtlCopyFromUser
0x1400c34cd  jmp     short loc_1400C34DE
0x1400c34cf  mov     ebx, eax
0x1400c34d1  mov     rdi, [rsp+0B8h+arg_8]
0x1400c34d9  jmp     loc_1400C35E6
0x1400c34de  mov     rax, [rsp+0B8h+var_78]
0x1400c34e3  test    rax, rax
0x1400c34e6  jz      short loc_1400C3536
0x1400c34e8  cmp     rax, r14
0x1400c34eb  ja      loc_1400C33DD
0x1400c34f1  cmp     [rsp+0B8h+var_58], 0
0x1400c34f7  jz      loc_1400C3401
0x1400c34fd  test    r15b, r15b
0x1400c3500  jz      short loc_1400C350B
0x1400c3502  cmp     rax, rsi
0x1400c3505  ja      loc_1400C3401
0x1400c350b  mov     r8d, 42474E43h
0x1400c3511  mov     rdx, [rsp+0B8h+var_78]
0x1400c3516  mov     ecx, 1
0x1400c351b  call    SkAllocatePool
0x1400c3520  mov     [rdi+40h], rax
0x1400c3524  test    rax, rax
0x1400c3527  jz      loc_1400C343B
0x1400c352d  mov     rax, [rsp+0B8h+var_78]
0x1400c3532  mov     [rdi+20h], rax
0x1400c3536  mov     rax, [rsp+0B8h+var_70]
0x1400c353b  test    rax, rax
0x1400c353e  jz      short loc_1400C358E
0x1400c3540  cmp     rax, r14
0x1400c3543  ja      loc_1400C33DD
0x1400c3549  cmp     [rsp+0B8h+var_50], 0
0x1400c354f  jz      loc_1400C3401
0x1400c3555  test    r15b, r15b
0x1400c3558  jz      short loc_1400C3563
0x1400c355a  cmp     rax, rsi
0x1400c355d  ja      loc_1400C3401
0x1400c3563  mov     r8d, 42474E43h
0x1400c3569  mov     rdx, [rsp+0B8h+var_70]
0x1400c356e  mov     ecx, 1
0x1400c3573  call    SkAllocatePool
0x1400c3578  mov     [rdi+48h], rax
0x1400c357c  test    rax, rax
0x1400c357f  jz      loc_1400C343B
0x1400c3585  mov     rax, [rsp+0B8h+var_70]
0x1400c358a  mov     [rdi+28h], rax
0x1400c358e  cmp     [rsp+0B8h+var_20], 0
0x1400c3597  jz      short loc_1400C35E6
0x1400c3599  mov     esi, 38h ; '8'
0x1400c359e  mov     r8d, 42474E43h
0x1400c35a4  mov     edx, esi
0x1400c35a6  lea     ecx, [rsi-37h]
0x1400c35a9  call    SkAllocatePool
0x1400c35ae  mov     [rdi+78h], rax
0x1400c35b2  test    rax, rax
0x1400c35b5  jz      loc_1400C343B
0x1400c35bb  mov     r8d, esi; Size
0x1400c35be  mov     rdx, [rsp+0B8h+var_20]; Src
0x1400c35c6  mov     rcx, rax; void *
0x1400c35c9  call    RtlCopyFromUser
0x1400c35ce  jmp     short loc_1400C35E6
0x1400c35d0  mov     ebx, eax
0x1400c35d2  mov     rdi, [rsp+0B8h+arg_8]
0x1400c35da  jmp     short loc_1400C35E6
0x1400c35dc  mov     ebx, eax
0x1400c35de  mov     rdi, [rsp+0B8h+arg_8]
0x1400c35e6  test    ebx, ebx
0x1400c35e8  jns     short loc_1400C35F2
0x1400c35ea  mov     rcx, rdi
0x1400c35ed  call    SkpCryptoFreeBuffers
0x1400c35f2  mov     eax, ebx
0x1400c35f4  lea     r11, [rsp+0B8h+var_18]
0x1400c35fc  mov     rbx, [r11+20h]
0x1400c3600  mov     rsi, [r11+30h]
0x1400c3604  mov     rsp, r11
0x1400c3607  pop     r15
0x1400c3609  pop     r14
0x1400c360b  pop     rdi
0x1400c360c  retn
```
