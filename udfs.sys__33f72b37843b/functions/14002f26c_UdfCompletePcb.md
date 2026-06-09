# UdfCompletePcb

- ea: `0x14002f26c`
- end: `0x14002f810`
- name: `UdfCompletePcb`
- size: `1444`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140003148`
- `0x140049f80`

## callees

- `0x140004340`
- `0x14000ca10`
- `0x14000cad4`
- `0x14001093c`
- `0x140010990`
- `0x140010c5c`
- `0x14002f26c`
- `0x14003c2e4`

## pseudocode

```c
__int64 __fastcall UdfCompletePcb(__int64 a1, _DWORD *a2, __int64 a3)
{
  unsigned __int16 i; // r14
  __int64 v7; // rsi
  __int64 v8; // rdx
  unsigned __int16 v9; // ax
  __int64 v10; // rdx
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rdx
  _DWORD *v14; // rdx
  __int64 v15; // r9
  int v16; // r10d
  int SparingTables; // ebp
  __int64 v18; // rbp
  unsigned int v19; // eax
  int v20; // edx
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rdx
  unsigned int v25; // r8d

  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    WPP_SF_qq(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      32,
      WPP_3702783af02333f5d52357996bb663b1_Traceguids,
      a2,
      a3);
  }
  for ( i = 0; i < *(_WORD *)(a3 + 4); ++i )
  {
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
    {
      WPP_SF_dd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        33,
        WPP_3702783af02333f5d52357996bb663b1_Traceguids,
        i,
        *(_DWORD *)(56LL * i + a3 + 96));
    }
    v7 = 56LL * i;
    if ( *(_DWORD *)(v7 + a3 + 96) == 1 )
    {
      v14 = *(_DWORD **)(v7 + a3 + 128);
      if ( !v14 )
      {
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            34,
            WPP_3702783af02333f5d52357996bb663b1_Traceguids);
        }
        return 3221225522LL;
      }
      v15 = (unsigned int)v14[47];
      *(_DWORD *)(v7 + a3 + 104) = v15;
      v16 = v14[48];
      *(_DWORD *)(v7 + a3 + 108) = v16;
      *(_DWORD *)(56 * (i + 2LL) + a3) = v14[46];
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
      {
        WPP_SF_dd(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          35,
          WPP_3702783af02333f5d52357996bb663b1_Traceguids,
          v15,
          v16);
      }
      if ( *(_QWORD *)(v7 + a3 + 136) )
      {
        SparingTables = UdfLoadSparingTables(a1, (__int64)a2, a3, i);
        if ( SparingTables < 0 )
        {
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
          {
            WPP_SF_d(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              36,
              WPP_3702783af02333f5d52357996bb663b1_Traceguids);
          }
          return (unsigned int)SparingTables;
        }
        a2[12] |= 0x1000000u;
      }
      v18 = *(_QWORD *)(v7 + a3 + 128);
      v19 = *(_DWORD *)(v18 + 184);
      if ( v19 == 2 )
      {
        v20 = a2[12];
        if ( (v20 & 0x4000) == 0 )
        {
          if ( (a2[21] & 0x388) != 0 && (a2[21] & 0x10) != 0 )
          {
            *(_WORD *)(a3 + 92) = i;
            a2[164] = *(_DWORD *)(v7 + a3 + 104);
            goto LABEL_71;
          }
          a2[12] = v20 | 0x10;
          v21 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) == 0 )
          {
            goto LABEL_71;
          }
          v22 = 37;
LABEL_47:
          WPP_SF_d(*(_QWORD *)(v21 + 24), v22, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
          goto LABEL_71;
        }
        goto LABEL_67;
      }
      if ( !v19 )
      {
        a2[12] |= 0x20000000u;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
        {
          WPP_SF_(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            38,
            WPP_3702783af02333f5d52357996bb663b1_Traceguids);
        }
        if ( (a2[21] & 0x110) != 0x110 )
        {
          a2[12] |= 0x10u;
          v21 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) == 0 )
          {
            goto LABEL_71;
          }
          v22 = 39;
          goto LABEL_47;
        }
        *(_WORD *)(a3 + 92) = i;
        a2[164] = *(_DWORD *)(v7 + a3 + 104);
LABEL_71:
        a2[165] += *(_DWORD *)(v7 + a3 + 108);
        v25 = *(_DWORD *)(v7 + a3 + 108);
        if ( a2[165] < v25 )
          return 3221225621LL;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
        {
          WPP_SF_dd(
            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
            45,
            WPP_3702783af02333f5d52357996bb663b1_Traceguids,
            *(unsigned int *)(v7 + a3 + 104),
            v25);
        }
        UdfFreePool(v7 + a3 + 136);
        continue;
      }
      if ( v19 < 3 )
      {
LABEL_67:
        a2[12] |= 0x10u;
        v23 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) == 0 )
        {
          goto LABEL_71;
        }
        v24 = 44;
      }
      else
      {
        if ( *(_DWORD *)(v18 + 60) || *(_DWORD *)(v18 + 84) || *(_DWORD *)(v18 + 92) )
        {
          a2[12] |= 0x10u;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
          {
            WPP_SF_(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              40,
              WPP_3702783af02333f5d52357996bb663b1_Traceguids);
          }
        }
        *(_QWORD *)(v7 + a3 + 116) = *(_QWORD *)(v18 + 64);
        if ( (*(_DWORD *)(v18 + 64) & 0x3FFFFFFF) != 0 )
        {
LABEL_59:
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
          {
            WPP_SF_DDD(
              *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
              42,
              WPP_3702783af02333f5d52357996bb663b1_Traceguids,
              *(unsigned int *)(v18 + 68),
              *(_DWORD *)(v18 + 64) & 0x3FFFFFFF,
              *(_DWORD *)(v18 + 64) >> 30);
          }
        }
        else
        {
          a2[12] |= 0x10u;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
              WPP_SF_(
                *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                41,
                WPP_3702783af02333f5d52357996bb663b1_Traceguids);
            goto LABEL_59;
          }
        }
        if ( *(_WORD *)(a3 + 92) == 0xFFFF )
        {
          *(_WORD *)(a3 + 92) = i;
          a2[164] = *(_DWORD *)(v7 + a3 + 104);
          a2[166] = *(_DWORD *)(v7 + a3 + 108);
          goto LABEL_71;
        }
        a2[12] |= 0x10u;
        v23 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) == 0 )
        {
          goto LABEL_71;
        }
        v24 = 43;
      }
      WPP_SF_(*(_QWORD *)(v23 + 24), v24, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
      goto LABEL_71;
    }
    if ( *(_DWORD *)(v7 + a3 + 96) == 3 )
    {
      if ( (*(_BYTE *)(a3 + 6) & 4) != 0 )
      {
        v8 = *(unsigned __int16 *)(a3 + 84);
        v9 = *(_WORD *)(a3 + 86);
        if ( *(_WORD *)(56 * v8 + a3 + 108) != v9 )
          goto LABEL_20;
        v10 = 56 * v8;
        v11 = *(_DWORD *)(56LL * v9 + a3 + 144) - 1;
        if ( (v11 & *(_DWORD *)(v10 + a3 + 132)) != 0 || (v11 & *(_DWORD *)(v10 + a3 + 128)) != 0 )
        {
          v12 = *(_QWORD *)&WPP_GLOBAL_Control;
          if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
          {
            v13 = 47;
            goto LABEL_18;
          }
          return 3221225522LL;
        }
      }
      else if ( *(_WORD *)(56LL * *(unsigned __int16 *)(a3 + 84) + a3 + 108) != *(_WORD *)(a3 + 88) )
      {
LABEL_20:
        v12 = *(_QWORD *)&WPP_GLOBAL_Control;
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
        {
          v13 = 46;
LABEL_18:
          WPP_SF_(*(_QWORD *)(v12 + 24), v13, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
        }
        return 3221225522LL;
      }
    }
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 48, WPP_3702783af02333f5d52357996bb663b1_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x14002f26c  push    rbx
0x14002f26e  push    rbp
0x14002f26f  push    rsi
0x14002f270  push    rdi
0x14002f271  push    r12
0x14002f273  push    r13
0x14002f275  push    r14
0x14002f277  push    r15
0x14002f279  sub     rsp, 38h
0x14002f27d  mov     rbx, r8
0x14002f280  mov     rdi, rdx
0x14002f283  mov     r12, rcx
0x14002f286  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f28d  lea     rbp, WPP_GLOBAL_Control
0x14002f294  lea     r15, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f29b  mov     r13w, 1
0x14002f2a0  cmp     rcx, rbp
0x14002f2a3  jz      short loc_14002F2C6
0x14002f2a5  mov     eax, [rcx+2Ch]
0x14002f2a8  test    r13b, al
0x14002f2ab  jz      short loc_14002F2C6
0x14002f2ad  mov     rcx, [rcx+18h]
0x14002f2b1  mov     edx, 20h ; ' '
0x14002f2b6  mov     r9, rdi
0x14002f2b9  mov     [rsp+78h+var_58], rbx
0x14002f2be  mov     r8, r15
0x14002f2c1  call    WPP_SF_qq
0x14002f2c6  xor     r14d, r14d
0x14002f2c9  cmp     r14w, [rbx+4]
0x14002f2ce  jnb     loc_14002F7D7
0x14002f2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f2db  cmp     rcx, rbp
0x14002f2de  jz      short loc_14002F30D
0x14002f2e0  mov     eax, [rcx+2Ch]
0x14002f2e3  test    r13b, al
0x14002f2e6  jz      short loc_14002F30D
0x14002f2e8  mov     rcx, [rcx+18h]
0x14002f2ec  mov     edx, 21h ; '!'
0x14002f2f1  movzx   eax, r14w
0x14002f2f5  mov     r8, r15
0x14002f2f8  imul    rax, 38h ; '8'
0x14002f2fc  movzx   r9d, r14w
0x14002f300  mov     eax, [rax+rbx+60h]
0x14002f304  mov     dword ptr [rsp+78h+var_58], eax
0x14002f308  call    WPP_SF_dd
0x14002f30d  movzx   r8d, r14w
0x14002f311  imul    rsi, r8, 38h ; '8'
0x14002f315  mov     ecx, [rsi+rbx+60h]
0x14002f319  sub     ecx, 1
0x14002f31c  jz      loc_14002F3DA
0x14002f322  cmp     ecx, 2
0x14002f325  jnz     loc_14002F75F
0x14002f32b  test    byte ptr [rbx+6], 4
0x14002f32f  jz      short loc_14002F3A0
0x14002f331  movzx   edx, word ptr [rbx+54h]
0x14002f335  movzx   eax, word ptr [rbx+56h]
0x14002f339  imul    rcx, rdx, 38h ; '8'
0x14002f33d  cmp     [rcx+rbx+6Ch], ax
0x14002f342  jnz     short loc_14002F3B7
0x14002f344  movzx   eax, ax
0x14002f347  imul    rcx, rax, 38h ; '8'
0x14002f34b  imul    rdx, 38h ; '8'
0x14002f34f  mov     ecx, [rcx+rbx+90h]
0x14002f356  dec     ecx
0x14002f358  test    [rdx+rbx+84h], ecx
0x14002f35f  jnz     short loc_14002F36E
0x14002f361  test    [rdx+rbx+80h], ecx
0x14002f368  jz      loc_14002F75F
0x14002f36e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f375  cmp     rcx, rbp
0x14002f378  jz      loc_14002F7D0
0x14002f37e  mov     eax, [rcx+2Ch]
0x14002f381  test    r13b, al
0x14002f384  jz      loc_14002F7D0
0x14002f38a  mov     edx, 2Fh ; '/'
0x14002f38f  mov     rcx, [rcx+18h]
0x14002f393  mov     r8, r15
0x14002f396  call    WPP_SF_
0x14002f39b  jmp     loc_14002F7D0
0x14002f3a0  movzx   eax, word ptr [rbx+54h]
0x14002f3a4  imul    rcx, rax, 38h ; '8'
0x14002f3a8  movzx   eax, word ptr [rbx+58h]
0x14002f3ac  cmp     [rcx+rbx+6Ch], ax
0x14002f3b1  jz      loc_14002F75F
0x14002f3b7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f3be  cmp     rcx, rbp
0x14002f3c1  jz      loc_14002F7D0
0x14002f3c7  mov     eax, [rcx+2Ch]
0x14002f3ca  test    r13b, al
0x14002f3cd  jz      loc_14002F7D0
0x14002f3d3  mov     edx, 2Eh ; '.'
0x14002f3d8  jmp     short loc_14002F38F
0x14002f3da  mov     rdx, [rsi+rbx+80h]
0x14002f3e2  test    rdx, rdx
0x14002f3e5  jz      loc_14002F7A6
0x14002f3eb  mov     r9d, [rdx+0BCh]
0x14002f3f2  lea     rax, [r8+2]
0x14002f3f6  imul    rcx, rax, 38h ; '8'
0x14002f3fa  mov     [rsi+rbx+68h], r9d
0x14002f3ff  mov     r10d, [rdx+0C0h]
0x14002f406  mov     [rsi+rbx+6Ch], r10d
0x14002f40b  mov     eax, [rdx+0B8h]
0x14002f411  mov     [rcx+rbx], eax
0x14002f414  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f41b  cmp     rcx, rbp
0x14002f41e  jz      short loc_14002F43E
0x14002f420  mov     eax, [rcx+2Ch]
0x14002f423  test    r13b, al
0x14002f426  jz      short loc_14002F43E
0x14002f428  mov     rcx, [rcx+18h]
0x14002f42c  mov     edx, 23h ; '#'
0x14002f431  mov     r8, r15
0x14002f434  mov     dword ptr [rsp+78h+var_58], r10d
0x14002f439  call    WPP_SF_dd
0x14002f43e  lea     r15, [rsi+rbx]
0x14002f442  cmp     qword ptr [r15+88h], 0
0x14002f44a  jz      short loc_14002F46D
0x14002f44c  movzx   r9d, r14w
0x14002f450  mov     r8, rbx
0x14002f453  mov     rdx, rdi
0x14002f456  mov     rcx, r12
0x14002f459  call    UdfLoadSparingTables
0x14002f45e  mov     ebp, eax
0x14002f460  test    eax, eax
0x14002f462  js      loc_14002F768
0x14002f468  bts     dword ptr [rdi+30h], 18h
0x14002f46d  mov     rbp, [rsi+rbx+80h]
0x14002f475  mov     eax, [rbp+0B8h]
0x14002f47b  cmp     eax, 2
0x14002f47e  jnz     short loc_14002F4EF
0x14002f480  mov     edx, [rdi+30h]
0x14002f483  bt      edx, 0Eh
0x14002f487  jb      loc_14002F6C9
0x14002f48d  mov     eax, [rdi+54h]
0x14002f490  test    eax, 388h
0x14002f495  setnz   cl
0x14002f498  test    al, 10h
0x14002f49a  setnz   al
0x14002f49d  test    al, cl
0x14002f49f  jz      short loc_14002F4BC
0x14002f4a1  mov     [rbx+5Ch], r14w
0x14002f4a6  mov     eax, [rsi+rbx+68h]
0x14002f4aa  mov     [rdi+290h], eax
0x14002f4b0  lea     rbp, WPP_GLOBAL_Control
0x14002f4b7  jmp     loc_14002F6FD
0x14002f4bc  or      edx, 10h
0x14002f4bf  mov     [rdi+30h], edx
0x14002f4c2  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f4c9  lea     rbp, WPP_GLOBAL_Control
0x14002f4d0  cmp     rcx, rbp
0x14002f4d3  jz      loc_14002F6FD
0x14002f4d9  mov     eax, [rcx+2Ch]
0x14002f4dc  test    r13b, al
0x14002f4df  jz      loc_14002F6FD
0x14002f4e5  mov     edx, 25h ; '%'
0x14002f4ea  jmp     loc_14002F573
0x14002f4ef  test    eax, eax
0x14002f4f1  jnz     loc_14002F597
0x14002f4f7  bts     dword ptr [rdi+30h], 1Dh
0x14002f4fc  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f503  lea     rbp, WPP_GLOBAL_Control
0x14002f50a  cmp     rcx, rbp
0x14002f50d  jz      short loc_14002F52C
0x14002f50f  mov     eax, [rcx+2Ch]
0x14002f512  test    r13b, al
0x14002f515  jz      short loc_14002F52C
0x14002f517  mov     rcx, [rcx+18h]
0x14002f51b  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f522  mov     edx, 26h ; '&'
0x14002f527  call    WPP_SF_
0x14002f52c  mov     eax, [rdi+54h]
0x14002f52f  mov     ecx, 110h
0x14002f534  and     eax, ecx
0x14002f536  cmp     eax, ecx
0x14002f538  jnz     short loc_14002F54E
0x14002f53a  mov     [rbx+5Ch], r14w
0x14002f53f  mov     eax, [rsi+rbx+68h]
0x14002f543  mov     [rdi+290h], eax
0x14002f549  jmp     loc_14002F6FD
0x14002f54e  or      dword ptr [rdi+30h], 10h
0x14002f552  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f559  cmp     rcx, rbp
0x14002f55c  jz      loc_14002F6FD
0x14002f562  mov     eax, [rcx+2Ch]
0x14002f565  test    r13b, al
0x14002f568  jz      loc_14002F6FD
0x14002f56e  mov     edx, 27h ; '''
0x14002f573  mov     r9, [rsi+rbx+80h]
0x14002f57b  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f582  mov     rcx, [rcx+18h]
0x14002f586  mov     r9d, [r9+0B8h]
0x14002f58d  call    WPP_SF_d
0x14002f592  jmp     loc_14002F6FD
0x14002f597  cmp     eax, 3
0x14002f59a  jb      loc_14002F6C9
0x14002f5a0  cmp     dword ptr [rbp+3Ch], 0
0x14002f5a4  jnz     short loc_14002F5B2
0x14002f5a6  cmp     dword ptr [rbp+54h], 0
0x14002f5aa  jnz     short loc_14002F5B2
0x14002f5ac  cmp     dword ptr [rbp+5Ch], 0
0x14002f5b0  jz      short loc_14002F5E6
0x14002f5b2  or      dword ptr [rdi+30h], 10h
0x14002f5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f5bd  lea     rdx, WPP_GLOBAL_Control
0x14002f5c4  cmp     rcx, rdx
0x14002f5c7  jz      short loc_14002F5ED
0x14002f5c9  mov     eax, [rcx+2Ch]
0x14002f5cc  test    r13b, al
0x14002f5cf  jz      short loc_14002F5ED
0x14002f5d1  mov     rcx, [rcx+18h]
0x14002f5d5  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f5dc  mov     edx, 28h ; '('
0x14002f5e1  call    WPP_SF_
0x14002f5e6  lea     rdx, WPP_GLOBAL_Control
0x14002f5ed  mov     rax, [rbp+40h]
0x14002f5f1  mov     [rsi+rbx+74h], rax
0x14002f5f6  test    dword ptr [rbp+40h], 3FFFFFFFh
0x14002f5fd  jnz     short loc_14002F62C
0x14002f5ff  or      dword ptr [rdi+30h], 10h
0x14002f603  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f60a  cmp     rcx, rdx
0x14002f60d  jz      short loc_14002F67A
0x14002f60f  mov     eax, [rcx+2Ch]
0x14002f612  test    r13b, al
0x14002f615  jz      short loc_14002F62C
0x14002f617  mov     rcx, [rcx+18h]
0x14002f61b  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f622  mov     edx, 29h ; ')'
0x14002f627  call    WPP_SF_
0x14002f62c  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f633  lea     rax, WPP_GLOBAL_Control
0x14002f63a  cmp     rcx, rax
0x14002f63d  jz      short loc_14002F67A
0x14002f63f  mov     eax, [rcx+2Ch]
0x14002f642  test    r13b, al
0x14002f645  jz      short loc_14002F67A
0x14002f647  mov     r8d, [rbp+40h]
0x14002f64b  mov     edx, 2Ah ; '*'
0x14002f650  mov     r9d, [rbp+44h]
0x14002f654  mov     eax, r8d
0x14002f657  mov     rcx, [rcx+18h]
0x14002f65b  and     r8d, 3FFFFFFFh
0x14002f662  shr     eax, 1Eh
0x14002f665  mov     [rsp+78h+var_50], eax
0x14002f669  mov     dword ptr [rsp+78h+var_58], r8d
0x14002f66e  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f675  call    WPP_SF_DDD
0x14002f67a  mov     eax, 0FFFFh
0x14002f67f  cmp     [rbx+5Ch], ax
0x14002f683  jnz     short loc_14002F6A3
0x14002f685  mov     [rbx+5Ch], r14w
0x14002f68a  mov     eax, [rsi+rbx+68h]
0x14002f68e  mov     [rdi+290h], eax
0x14002f694  mov     eax, [rsi+rbx+6Ch]
0x14002f698  mov     [rdi+298h], eax
0x14002f69e  jmp     loc_14002F4B0
0x14002f6a3  or      dword ptr [rdi+30h], 10h
0x14002f6a7  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6ae  lea     rbp, WPP_GLOBAL_Control
0x14002f6b5  cmp     rcx, rbp
0x14002f6b8  jz      short loc_14002F6FD
0x14002f6ba  mov     eax, [rcx+2Ch]
0x14002f6bd  test    r13b, al
0x14002f6c0  jz      short loc_14002F6FD
0x14002f6c2  mov     edx, 2Bh ; '+'
0x14002f6c7  jmp     short loc_14002F6ED
0x14002f6c9  or      dword ptr [rdi+30h], 10h
0x14002f6cd  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f6d4  lea     rbp, WPP_GLOBAL_Control
0x14002f6db  cmp     rcx, rbp
0x14002f6de  jz      short loc_14002F6FD
0x14002f6e0  mov     eax, [rcx+2Ch]
0x14002f6e3  test    r13b, al
0x14002f6e6  jz      short loc_14002F6FD
0x14002f6e8  mov     edx, 2Ch ; ','
0x14002f6ed  mov     rcx, [rcx+18h]
0x14002f6f1  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f6f8  call    WPP_SF_
0x14002f6fd  mov     eax, [rsi+rbx+6Ch]
0x14002f701  add     [rdi+294h], eax
0x14002f707  mov     r8d, [rsi+rbx+6Ch]
0x14002f70c  cmp     [rdi+294h], r8d
0x14002f713  jb      loc_14002F79F
0x14002f719  mov     rcx, cs:WPP_GLOBAL_Control
0x14002f720  cmp     rcx, rbp
0x14002f723  jz      short loc_14002F74C
0x14002f725  mov     eax, [rcx+2Ch]
0x14002f728  test    r13b, al
0x14002f72b  jz      short loc_14002F74C
0x14002f72d  mov     r9d, [rsi+rbx+68h]
0x14002f732  mov     edx, 2Dh ; '-'
0x14002f737  mov     rcx, [rcx+18h]
0x14002f73b  mov     dword ptr [rsp+78h+var_58], r8d
0x14002f740  lea     r8, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f747  call    WPP_SF_dd
0x14002f74c  lea     rcx, [r15+88h]
0x14002f753  call    UdfFreePool
0x14002f758  lea     r15, WPP_3702783af02333f5d52357996bb663b1_Traceguids
0x14002f75f  add     r14w, r13w
0x14002f763  jmp     loc_14002F2C9
  ... truncated ...
```
