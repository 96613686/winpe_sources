# UdfPrepareDeviceForWrite

- ea: `0x140031b04`
- end: `0x140031d93`
- name: `UdfPrepareDeviceForWrite`
- size: `655`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003148`
- `0x14000aadc`
- `0x14003aa44`

## callees

- `0x14000ca10`
- `0x14000cad4`
- `0x14001bc30`
- `0x140031b04`
- `0x14004c1b4`

## pseudocode

```c
char __fastcall UdfPrepareDeviceForWrite(__int64 a1, struct _DEVICE_OBJECT *a2, int a3, char a4)
{
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  unsigned int v12; // r9d
  char v13; // al
  char v14; // al
  union _LARGE_INTEGER v15; // [rsp+30h] [rbp-D0h]
  union _LARGE_INTEGER v16; // [rsp+30h] [rbp-D0h]
  __int64 v17; // [rsp+38h] [rbp-C8h]
  __int64 v18; // [rsp+38h] [rbp-C8h]
  size_t v19; // [rsp+40h] [rbp-C0h]
  size_t v20; // [rsp+40h] [rbp-C0h]
  __int64 v21; // [rsp+48h] [rbp-B8h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  int v23; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v24; // [rsp+50h] [rbp-B0h]
  unsigned __int8 v25[24]; // [rsp+58h] [rbp-A8h] BYREF
  __int16 v26; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+72h] [rbp-8Eh]
  char v28; // [rsp+76h] [rbp-8Ah]
  char v29; // [rsp+77h] [rbp-89h]
  char v30; // [rsp+7Ah] [rbp-86h]
  char v31; // [rsp+7Bh] [rbp-85h]
  char v32; // [rsp+7Ch] [rbp-84h]
  char v33; // [rsp+80h] [rbp-80h]
  __int16 v34; // [rsp+82h] [rbp-7Eh]
  char v35; // [rsp+84h] [rbp-7Ch]
  char v36; // [rsp+85h] [rbp-7Bh]

  HIWORD(v23) = 0;
  if ( (a3 & 0x4000004) != 0 )
  {
    v7 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) == 0 )
    {
      return 1;
    }
    v8 = 28;
LABEL_5:
    WPP_SF_(*(_QWORD *)(v7 + 24), v8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids);
    return 1;
  }
  *(_OWORD *)v25 = 0;
  *(_WORD *)v25 = 2138;
  v25[2] = 5;
  *(_WORD *)&v25[7] = 1;
  if ( (int)UdfSendSptCdb(a2, v25, &v26, 0x100u, 1, 5u, v15, v17, v19, v21) < 0 )
  {
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) == 0 )
    {
      return 0;
    }
    v10 = *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL);
    v11 = 29;
    goto LABEL_23;
  }
  if ( v28 || v29 )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 30, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids);
    }
    return 0;
  }
  LOBYTE(v23) = HIBYTE(v26);
  BYTE1(v23) = v26;
  v12 = v23 + 2;
  v13 = v30 & 0xE0;
  v24 = HIBYTE(v26) + 2;
  v26 = 0;
  v27 = 0;
  v30 &= 0xE0u;
  if ( (a3 & 0x10) != 0 )
  {
    v30 = v13 | 0x40;
    v31 = a4 != 0 ? -59 : 5;
  }
  else
  {
    v34 = 0;
    v35 = 0;
    v31 = 37;
    v36 = (a3 & 8) != 0 ? 16 : 32;
  }
  if ( a3 == 144 )
  {
    v33 = 32;
    v14 = v32 & 0xF0 | 0xA;
  }
  else
  {
    v33 = 0;
    v14 = v32 & 0xF0 | 8;
  }
  v32 = v14;
  *(_OWORD *)v25 = 0;
  v25[7] = BYTE1(v12);
  v25[8] = v24;
  *(_WORD *)v25 = 4181;
  if ( (int)UdfSendSptCdb(a2, v25, &v26, v12, 0, 5u, v16, v18, v20, v22) >= 0 )
  {
    v7 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) == 0 )
    {
      return 1;
    }
    v8 = 32;
    goto LABEL_5;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40) != 0 )
  {
    v10 = *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL);
    v11 = 31;
LABEL_23:
    WPP_SF_d(v10, v11, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140031b04  mov     [rsp-8+arg_0], rbx
0x140031b09  mov     [rsp-8+arg_10], rsi
0x140031b0e  push    rbp
0x140031b0f  push    rdi
0x140031b10  push    r14
0x140031b12  lea     rbp, [rsp-80h]
0x140031b17  sub     rsp, 180h
0x140031b1e  mov     rax, cs:__security_cookie
0x140031b25  xor     rax, rsp
0x140031b28  mov     [rbp+90h+var_20], rax
0x140031b2c  xor     r14d, r14d
0x140031b2f  mov     dil, r9b
0x140031b32  mov     [rsp+190h+var_140], r14d
0x140031b37  mov     ebx, r8d
0x140031b3a  mov     rsi, rdx
0x140031b3d  test    r8d, 4000004h
0x140031b44  jz      short loc_140031B7B
0x140031b46  mov     rcx, cs:WPP_GLOBAL_Control
0x140031b4d  lea     rax, WPP_GLOBAL_Control
0x140031b54  cmp     rcx, rax
0x140031b57  jz      short loc_140031B74
0x140031b59  mov     eax, [rcx+2Ch]
0x140031b5c  test    al, 40h
0x140031b5e  jz      short loc_140031B74
0x140031b60  lea     edx, [r14+1Ch]
0x140031b64  mov     rcx, [rcx+18h]
0x140031b68  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140031b6f  call    WPP_SF_
0x140031b74  mov     al, 1
0x140031b76  jmp     loc_140031D6E
0x140031b7b  xorps   xmm0, xmm0
0x140031b7e  mov     [rsp+190h+var_168], 5
0x140031b86  movups  xmmword ptr [rsp+190h+var_138], xmm0
0x140031b8b  mov     r9d, 100h
0x140031b91  mov     word ptr [rsp+190h+var_138], 85Ah
0x140031b98  lea     r8, [rsp+190h+var_120]
0x140031b9d  mov     [rsp+190h+var_138+2], 5
0x140031ba2  lea     rdx, [rsp+190h+var_138]
0x140031ba7  mov     word ptr [rsp+190h+var_138+7], 1
0x140031bae  mov     rcx, rsi
0x140031bb1  mov     [rsp+190h+var_170], 1
0x140031bb6  call    UdfSendSptCdb
0x140031bbb  mov     r9d, eax
0x140031bbe  test    eax, eax
0x140031bc0  jns     short loc_140031BF4
0x140031bc2  mov     r10, cs:WPP_GLOBAL_Control
0x140031bc9  lea     rax, WPP_GLOBAL_Control
0x140031bd0  cmp     r10, rax
0x140031bd3  jz      loc_140031D6C
0x140031bd9  mov     ecx, [r10+2Ch]
0x140031bdd  test    cl, 40h
0x140031be0  jz      loc_140031D6C
0x140031be6  mov     rcx, [r10+18h]
0x140031bea  mov     edx, 1Dh
0x140031bef  jmp     loc_140031D03
0x140031bf4  cmp     [rsp+190h+var_11A], r14b
0x140031bf9  jnz     loc_140031D3D
0x140031bff  cmp     [rsp+190h+var_119], r14b
0x140031c04  jnz     loc_140031D3D
0x140031c0a  mov     al, byte ptr [rsp+190h+var_120+1]
0x140031c0e  mov     byte ptr [rsp+190h+var_140], al
0x140031c12  mov     al, byte ptr [rsp+190h+var_120]
0x140031c16  mov     byte ptr [rsp+190h+var_140+1], al
0x140031c1a  mov     r9d, [rsp+190h+var_140]
0x140031c1f  mov     al, [rsp+190h+var_116]
0x140031c23  add     r9d, 2
0x140031c27  and     al, 0E0h
0x140031c29  mov     [rsp+190h+var_140], r9d
0x140031c2e  mov     [rsp+190h+var_120], r14w
0x140031c34  mov     [rsp+190h+var_11E], r14b
0x140031c39  mov     [rsp+190h+var_116], al
0x140031c3d  test    bl, 10h
0x140031c40  jz      short loc_140031C57
0x140031c42  or      al, 40h
0x140031c44  mov     [rsp+190h+var_116], al
0x140031c48  neg     dil
0x140031c4b  sbb     al, al
0x140031c4d  and     al, 0C0h
0x140031c4f  add     al, 5
0x140031c51  mov     [rsp+190h+var_115], al
0x140031c55  jmp     short loc_140031C76
0x140031c57  mov     al, bl
0x140031c59  mov     [rbp+90h+var_10E], r14w
0x140031c5e  and     al, 8
0x140031c60  mov     [rbp+90h+var_10C], r14b
0x140031c64  neg     al
0x140031c66  mov     [rsp+190h+var_115], 25h ; '%'
0x140031c6b  sbb     ecx, ecx
0x140031c6d  and     ecx, 0FFFFFFF0h
0x140031c70  add     ecx, 20h ; ' '
0x140031c73  mov     [rbp+90h+var_10B], cl
0x140031c76  mov     al, [rsp+190h+var_114]
0x140031c7a  cmp     ebx, 90h
0x140031c80  jnz     short loc_140031C8C
0x140031c82  and     al, 0FAh
0x140031c84  mov     [rbp+90h+var_110], 20h ; ' '
0x140031c88  or      al, 0Ah
0x140031c8a  jmp     short loc_140031C94
0x140031c8c  and     al, 0F8h
0x140031c8e  mov     [rbp+90h+var_110], r14b
0x140031c92  or      al, 8
0x140031c94  mov     [rsp+190h+var_114], al
0x140031c98  lea     r8, [rsp+190h+var_120]
0x140031c9d  mov     eax, r9d
0x140031ca0  mov     [rsp+190h+var_168], 5
0x140031ca8  shr     eax, 8
0x140031cab  lea     rdx, [rsp+190h+var_138]
0x140031cb0  xorps   xmm0, xmm0
0x140031cb3  mov     [rsp+190h+var_170], r14b
0x140031cb8  movups  xmmword ptr [rsp+190h+var_138], xmm0
0x140031cbd  mov     [rsp+190h+var_138+7], al
0x140031cc1  mov     rcx, rsi
0x140031cc4  mov     al, byte ptr [rsp+190h+var_140]
0x140031cc8  mov     [rsp+190h+var_138+8], al
0x140031ccc  mov     word ptr [rsp+190h+var_138], 1055h
0x140031cd3  call    UdfSendSptCdb
0x140031cd8  mov     r9d, eax
0x140031cdb  test    eax, eax
0x140031cdd  jns     short loc_140031D11
0x140031cdf  mov     rcx, cs:WPP_GLOBAL_Control
0x140031ce6  lea     rax, WPP_GLOBAL_Control
0x140031ced  cmp     rcx, rax
0x140031cf0  jz      short loc_140031D6C
0x140031cf2  mov     edx, [rcx+2Ch]
0x140031cf5  test    dl, 40h
0x140031cf8  jz      short loc_140031D6C
0x140031cfa  mov     rcx, [rcx+18h]
0x140031cfe  mov     edx, 1Fh
0x140031d03  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140031d0a  call    WPP_SF_d
0x140031d0f  jmp     short loc_140031D6C
0x140031d11  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d18  lea     rax, WPP_GLOBAL_Control
0x140031d1f  cmp     rcx, rax
0x140031d22  jz      loc_140031B74
0x140031d28  mov     eax, [rcx+2Ch]
0x140031d2b  test    al, 40h
0x140031d2d  jz      loc_140031B74
0x140031d33  mov     edx, 20h ; ' '
0x140031d38  jmp     loc_140031B64
0x140031d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x140031d44  lea     rax, WPP_GLOBAL_Control
0x140031d4b  cmp     rcx, rax
0x140031d4e  jz      short loc_140031D6C
0x140031d50  mov     eax, [rcx+2Ch]
0x140031d53  test    al, 40h
0x140031d55  jz      short loc_140031D6C
0x140031d57  mov     rcx, [rcx+18h]
0x140031d5b  lea     r8, WPP_5bfc2f2093d839e585ee26edf42aa569_Traceguids
0x140031d62  mov     edx, 1Eh
0x140031d67  call    WPP_SF_
0x140031d6c  xor     al, al
0x140031d6e  mov     rcx, [rbp+90h+var_20]
0x140031d72  xor     rcx, rsp; StackCookie
0x140031d75  call    __security_check_cookie
0x140031d7a  lea     r11, [rsp+190h+var_10]
0x140031d82  mov     rbx, [r11+20h]
0x140031d86  mov     rsi, [r11+30h]
0x140031d8a  mov     rsp, r11
0x140031d8d  pop     r14
0x140031d8f  pop     rdi
0x140031d90  pop     rbp
0x140031d91  retn
```
