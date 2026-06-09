# HUBDESC_ValidateDeviceDescriptor

- ea: `0x14003d160`
- end: `0x14003d705`
- name: `HUBDESC_ValidateDeviceDescriptor`
- size: `1445`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x14002c90c`
- `0x14002d28c`

## callees

- `0x1400024b8`
- `0x1400067ac`
- `0x14003bf54`
- `0x14003d160`
- `0x140045570`

## pseudocode

```c
char __fastcall HUBDESC_ValidateDeviceDescriptor(__int64 a1, unsigned int a2, __int64 a3, _BYTE *a4, __int64 a5)
{
  int v7; // r14d
  __int64 v8; // rdx
  int v9; // edx
  char v10; // si
  int v12; // r13d
  void (__fastcall **v13)(_QWORD, __int64); // rax
  _QWORD *v14; // rdx
  char v15; // cl
  _QWORD *v16; // rcx
  _QWORD *v17; // rcx
  __int16 v18; // cx
  int v19; // eax
  char v20; // al
  __int64 v21; // rcx
  int v22; // r9d
  __int64 v23; // rcx
  char ShouldEnforceWin8ValidationMutable; // al
  __int64 v25; // rcx
  char v26; // [rsp+28h] [rbp-60h]
  char v27; // [rsp+28h] [rbp-60h]
  void (__fastcall **v28)(_QWORD, __int64); // [rsp+30h] [rbp-58h]
  void (__fastcall **v29)(_QWORD, __int64); // [rsp+38h] [rbp-50h]
  _QWORD *v30; // [rsp+40h] [rbp-48h]
  _QWORD *v31; // [rsp+90h] [rbp+8h]
  unsigned int v32; // [rsp+98h] [rbp+10h]

  v32 = a2;
  if ( !a1 )
  {
    v7 = a5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_(a5, a2, 5, 259, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
    }
    v8 = 79;
LABEL_5:
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), v8);
    goto LABEL_6;
  }
  if ( a2 < 2 )
  {
    v7 = a5;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = a2;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(a5, a2, 5, 260, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v26);
    }
    v8 = 71;
    goto LABEL_5;
  }
  v7 = a5;
  v12 = 0;
  if ( *(_BYTE *)a1 >= 0x12u )
  {
    v13 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    v14 = (_QWORD *)(a3 + 40);
    v29 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    v30 = (_QWORD *)(a3 + 40);
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(a5, a2, 5, 261, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *(_BYTE *)a1);
    }
    v29 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    v30 = (_QWORD *)(a3 + 40);
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 70);
    v13 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    v12 = 2;
    v14 = (_QWORD *)(a3 + 40);
  }
  v15 = *(_BYTE *)(a1 + 1);
  if ( v15 == 1 )
  {
    v16 = v14;
    v31 = v14;
    v28 = v13;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v31 = v14;
      v28 = v13;
    }
    else
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(a5, (_DWORD)v14, 5, 262, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v15);
      v28 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
      v31 = (_QWORD *)(a3 + 40);
      v13 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    }
    (*v13)(*(_QWORD *)(a3 + 40), 77);
    v16 = v31;
    v13 = (void (__fastcall **)(_QWORD, __int64))(a3 + 24);
    v14 = (_QWORD *)(a3 + 40);
    v12 = 2;
  }
  if ( v32 < 8 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v17 = v14;
    }
    else
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(a5, (_DWORD)v14, 5, 263, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v32);
      v17 = v31;
      v13 = v28;
    }
    (*v13)(*v17, 71);
    goto LABEL_6;
  }
  v9 = *(unsigned __int16 *)(a1 + 12);
  if ( (v9 & 0xF000u) > 0x9000 || (v9 & 0xF00u) > 0x900 || (*(_WORD *)(a1 + 12) & 0xF0u) > 0x90 || (v9 & 0xFu) > 9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(a5, v9, 5, 264, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *(_WORD *)(a1 + 12));
      v16 = (_QWORD *)(a3 + 40);
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 32))(*v16, 69);
  }
  if ( *(_BYTE *)(a1 + 4) == 17 && !*(_BYTE *)(a1 + 5) && !*(_BYTE *)(a1 + 6) )
  {
    v18 = *(_WORD *)(a1 + 2);
    v9 = 254;
    if ( (unsigned __int16)(v18 - 513) > 0xFEu )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(a5, v9, 5, 265, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v18);
      }
      (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 246);
      v12 = 2;
    }
    else if ( a4 )
    {
      *a4 = 1;
    }
  }
  v19 = *(_DWORD *)(a3 + 4);
  if ( v19 )
  {
    if ( v19 == 1 )
    {
      v9 = *(unsigned __int8 *)(a1 + 7);
      if ( (unsigned __int8)(v9 - 8) > 0x38u || (v23 = 0x100000001000101LL, !_bittest64(&v23, (unsigned int)(v9 - 8))) )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_d(
            a5,
            v9,
            5,
            268,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            *(_BYTE *)(a1 + 7));
        }
        (*v29)(*v30, 78);
        goto LABEL_73;
      }
    }
    else
    {
      if ( v19 != 2 )
      {
        if ( v19 == 3 && *(_BYTE *)(a1 + 7) != 9 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v9) = 2;
            WPP_RECORDER_SF_d(
              a5,
              v9,
              5,
              271,
              (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
              *(_BYTE *)(a1 + 7));
          }
          (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 78);
          if ( (unsigned __int8)HUBDESC_ShouldEnforceWin8ValidationMutable(a3) )
            goto LABEL_6;
        }
        goto LABEL_79;
      }
      if ( *(_BYTE *)(a1 + 7) != 64 )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v9) = 2;
          WPP_RECORDER_SF_d(
            a5,
            v9,
            5,
            269,
            (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids,
            *(_BYTE *)(a1 + 7));
        }
        (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 78);
        ShouldEnforceWin8ValidationMutable = HUBDESC_ShouldEnforceWin8ValidationMutable(a3);
        v9 = *(unsigned __int8 *)(a1 + 7);
        if ( ShouldEnforceWin8ValidationMutable )
          v12 = 2;
        if ( (unsigned __int8)(v9 - 8) > 0x38u || (v25 = 0x100000001000101LL, !_bittest64(&v25, (unsigned int)(v9 - 8))) )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v22 = 270;
            goto LABEL_71;
          }
LABEL_72:
          (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 78);
LABEL_73:
          v12 = 2;
        }
      }
    }
  }
  else if ( *(_BYTE *)(a1 + 7) != 8 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(a5, v9, 5, 266, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, *(_BYTE *)(a1 + 7));
    }
    (*(void (__fastcall **)(_QWORD, __int64))(a3 + 24))(*(_QWORD *)(a3 + 40), 78);
    v20 = HUBDESC_ShouldEnforceWin8ValidationMutable(a3);
    v9 = *(unsigned __int8 *)(a1 + 7);
    if ( v20 )
      v12 = 2;
    if ( (unsigned __int8)(v9 - 8) > 0x38u || (v21 = 0x100000001000101LL, !_bittest64(&v21, (unsigned int)(v9 - 8))) )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v22 = 267;
LABEL_71:
        v27 = v9;
        LOBYTE(v9) = 2;
        WPP_RECORDER_SF_d(a5, v9, 5, v22, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids, v27);
        goto LABEL_72;
      }
      goto LABEL_72;
    }
  }
LABEL_79:
  if ( !v12 )
    return 1;
LABEL_6:
  v10 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 2;
    WPP_RECORDER_SF_(v7, v9, 5, 272, (__int64)WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids);
  }
  return v10;
}

```

## disassembly

```asm
0x14003d160  mov     [rsp+arg_10], rbx
0x14003d165  mov     [rsp+arg_18], r9
0x14003d16a  mov     [rsp+arg_8], edx
0x14003d16e  push    rbp
0x14003d16f  push    rsi
0x14003d170  push    rdi
0x14003d171  push    r12
0x14003d173  push    r13
0x14003d175  push    r14
0x14003d177  push    r15
0x14003d179  sub     rsp, 50h
0x14003d17d  mov     rsi, r8
0x14003d180  mov     eax, edx
0x14003d182  mov     r12, rcx
0x14003d185  test    rcx, rcx
0x14003d188  jnz     loc_14003D21D
0x14003d18e  mov     r14, [rsp+88h+arg_20]; __annotation("TMF:",
0x14003d196  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003d19d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003d1a4  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003d1ab  lea     ebp, [rcx+5]
0x14003d1ae  lea     ebx, [rcx+2]
0x14003d1b1  jz      short loc_14003D1CB
0x14003d1b3  mov     r9d, 103h
0x14003d1b9  mov     [rsp+88h+var_68], r15
0x14003d1be  mov     r8d, ebp
0x14003d1c1  mov     dl, bl
0x14003d1c3  mov     rcx, r14
0x14003d1c6  call    WPP_RECORDER_SF_
0x14003d1cb  mov     edx, 4Fh ; 'O'
0x14003d1d0  mov     rax, [rsi+18h]
0x14003d1d4  mov     rcx, [rsi+28h]
0x14003d1d8  call    _guard_dispatch_icall
0x14003d1dd  xor     sil, sil
0x14003d1e0  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d1e7  jz      short loc_14003D201
0x14003d1e9  mov     r9d, 110h
0x14003d1ef  mov     [rsp+88h+var_68], r15
0x14003d1f4  mov     r8d, ebp
0x14003d1f7  mov     dl, bl
0x14003d1f9  mov     rcx, r14
0x14003d1fc  call    WPP_RECORDER_SF_
0x14003d201  mov     rbx, [rsp+88h+arg_10]
0x14003d209  mov     al, sil
0x14003d20c  add     rsp, 50h
0x14003d210  pop     r15
0x14003d212  pop     r14
0x14003d214  pop     r13
0x14003d216  pop     r12
0x14003d218  pop     rdi
0x14003d219  pop     rsi
0x14003d21a  pop     rbp
0x14003d21b  retn
0x14003d21d  mov     ebx, 2
0x14003d222  cmp     eax, ebx
0x14003d224  jnb     short loc_14003D26E
0x14003d226  mov     r14, [rsp+88h+arg_20]; __annotation("TMF:",
0x14003d22e  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003d235  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14003d23c  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003d243  lea     ebp, [rbx+3]
0x14003d246  jz      short loc_14003D264
0x14003d248  mov     dword ptr [rsp+88h+var_60], eax
0x14003d24c  mov     r9d, 104h
0x14003d252  mov     r8d, ebp
0x14003d255  mov     [rsp+88h+var_68], r15
0x14003d25a  mov     dl, bl
0x14003d25c  mov     rcx, r14
0x14003d25f  call    WPP_RECORDER_SF_d
0x14003d264  mov     edx, 47h ; 'G'
0x14003d269  jmp     loc_14003D1D0
0x14003d26e  movzx   eax, byte ptr [rcx]
0x14003d271  lea     rdi, WPP_RECORDER_INITIALIZED
0x14003d278  mov     r14, [rsp+88h+arg_20]
0x14003d280  lea     r15, WPP_217391fd10f630c6cddebdfb4f852f5f_Traceguids
0x14003d287  xor     r13d, r13d
0x14003d28a  lea     ebp, [r13+5]
0x14003d28e  cmp     al, 12h
0x14003d290  jnb     short loc_14003D2E6
0x14003d292  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d299  jz      short loc_14003D2B7
0x14003d29b  mov     dword ptr [rsp+88h+var_60], eax
0x14003d29f  mov     r9d, 105h
0x14003d2a5  mov     r8d, ebp
0x14003d2a8  mov     [rsp+88h+var_68], r15
0x14003d2ad  mov     dl, bl
0x14003d2af  mov     rcx, r14
0x14003d2b2  call    WPP_RECORDER_SF_d
0x14003d2b7  lea     rax, [rsi+18h]
0x14003d2bb  mov     edx, 46h ; 'F'
0x14003d2c0  lea     rcx, [rsi+28h]
0x14003d2c4  mov     [rsp+88h+var_50], rax
0x14003d2c9  mov     rax, [rax]
0x14003d2cc  mov     [rsp+88h+var_48], rcx
0x14003d2d1  mov     rcx, [rcx]
0x14003d2d4  call    _guard_dispatch_icall
0x14003d2d9  lea     rax, [rsi+18h]
0x14003d2dd  mov     r13d, ebx
0x14003d2e0  lea     rdx, [rsi+28h]
0x14003d2e4  jmp     short loc_14003D2F8
0x14003d2e6  lea     rax, [r8+18h]
0x14003d2ea  lea     rdx, [r8+28h]
0x14003d2ee  mov     [rsp+88h+var_50], rax
0x14003d2f3  mov     [rsp+88h+var_48], rdx
0x14003d2f8  movzx   ecx, byte ptr [r12+1]
0x14003d2fe  cmp     cl, 1
0x14003d301  jz      short loc_14003D376
0x14003d303  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d30a  jz      short loc_14003D343
0x14003d30c  mov     dword ptr [rsp+88h+var_60], ecx
0x14003d310  mov     r9d, 106h
0x14003d316  mov     rcx, r14
0x14003d319  mov     [rsp+88h+var_68], r15
0x14003d31e  mov     r8d, ebp
0x14003d321  mov     dl, bl
0x14003d323  call    WPP_RECORDER_SF_d
0x14003d328  lea     r8, [rsi+18h]
0x14003d32c  lea     rcx, [rsi+28h]
0x14003d330  mov     [rsp+88h+var_58], r8
0x14003d335  mov     [rsp+88h+arg_0], rcx
0x14003d33d  lea     rax, [rsi+18h]
0x14003d341  jmp     short loc_14003D350
0x14003d343  mov     [rsp+88h+arg_0], rdx
0x14003d34b  mov     [rsp+88h+var_58], rax
0x14003d350  mov     rax, [rax]
0x14003d353  mov     edx, 4Dh ; 'M'
0x14003d358  mov     rcx, [rsi+28h]
0x14003d35c  call    _guard_dispatch_icall
0x14003d361  mov     rcx, [rsp+88h+arg_0]
0x14003d369  lea     rax, [rsi+18h]
0x14003d36d  lea     rdx, [rsi+28h]
0x14003d371  mov     r13d, ebx
0x14003d374  jmp     short loc_14003D386
0x14003d376  mov     rcx, rdx
0x14003d379  mov     [rsp+88h+arg_0], rdx
0x14003d381  mov     [rsp+88h+var_58], rax
0x14003d386  mov     r8d, [rsp+88h+arg_8]
0x14003d38e  cmp     r8d, 8
0x14003d392  jnb     short loc_14003D3DC
0x14003d394  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d39b  jz      short loc_14003D3C9
0x14003d39d  mov     dword ptr [rsp+88h+var_60], r8d
0x14003d3a2  mov     r9d, 107h
0x14003d3a8  mov     r8d, ebp
0x14003d3ab  mov     [rsp+88h+var_68], r15
0x14003d3b0  mov     dl, bl
0x14003d3b2  mov     rcx, r14
0x14003d3b5  call    WPP_RECORDER_SF_d
0x14003d3ba  mov     rcx, [rsp+88h+arg_0]
0x14003d3c2  mov     rax, [rsp+88h+var_58]
0x14003d3c7  jmp     short loc_14003D3CC
0x14003d3c9  mov     rcx, rdx
0x14003d3cc  mov     rax, [rax]
0x14003d3cf  mov     edx, 47h ; 'G'
0x14003d3d4  mov     rcx, [rcx]
0x14003d3d7  jmp     loc_14003D1D8
0x14003d3dc  movzx   edx, word ptr [r12+0Ch]
0x14003d3e2  mov     r8d, 0F000h
0x14003d3e8  movzx   eax, dx
0x14003d3eb  and     ax, r8w
0x14003d3ef  mov     r8d, 9000h
0x14003d3f5  cmp     ax, r8w
0x14003d3f9  ja      short loc_14003D435
0x14003d3fb  mov     r8d, 0F00h
0x14003d401  movzx   eax, dx
0x14003d404  and     ax, r8w
0x14003d408  mov     r8d, 900h
0x14003d40e  cmp     ax, r8w
0x14003d412  ja      short loc_14003D435
0x14003d414  mov     r8d, 0F0h
0x14003d41a  movzx   eax, dx
0x14003d41d  and     ax, r8w
0x14003d421  mov     r8d, 90h
0x14003d427  cmp     ax, r8w
0x14003d42b  ja      short loc_14003D435
0x14003d42d  mov     al, dl
0x14003d42f  and     al, 0Fh
0x14003d431  cmp     al, 9
0x14003d433  jbe     short loc_14003D46F
0x14003d435  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d43c  jz      short loc_14003D45E
0x14003d43e  mov     dword ptr [rsp+88h+var_60], edx
0x14003d442  mov     r9d, 108h
0x14003d448  mov     dl, bl
0x14003d44a  mov     [rsp+88h+var_68], r15
0x14003d44f  mov     r8d, ebp
0x14003d452  mov     rcx, r14
0x14003d455  call    WPP_RECORDER_SF_d
0x14003d45a  lea     rcx, [rsi+28h]
0x14003d45e  mov     rax, [rsi+20h]
0x14003d462  mov     edx, 45h ; 'E'
0x14003d467  mov     rcx, [rcx]
0x14003d46a  call    _guard_dispatch_icall
0x14003d46f  cmp     byte ptr [r12+4], 11h
0x14003d475  jnz     short loc_14003D4EE
0x14003d477  cmp     byte ptr [r12+5], 0
0x14003d47d  jnz     short loc_14003D4EE
0x14003d47f  cmp     byte ptr [r12+6], 0
0x14003d485  jnz     short loc_14003D4EE
0x14003d487  movzx   ecx, word ptr [r12+2]
0x14003d48d  mov     edx, 201h
0x14003d492  movzx   eax, cx
0x14003d495  sub     ax, dx
0x14003d498  mov     edx, 0FEh
0x14003d49d  cmp     ax, dx
0x14003d4a0  ja      short loc_14003D4B4
0x14003d4a2  mov     rax, [rsp+88h+arg_18]
0x14003d4aa  test    rax, rax
0x14003d4ad  jz      short loc_14003D4EE
0x14003d4af  mov     byte ptr [rax], 1
0x14003d4b2  jmp     short loc_14003D4EE
0x14003d4b4  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d4bb  jz      short loc_14003D4D9
0x14003d4bd  mov     dword ptr [rsp+88h+var_60], ecx
0x14003d4c1  mov     r9d, 109h
0x14003d4c7  mov     rcx, r14
0x14003d4ca  mov     [rsp+88h+var_68], r15
0x14003d4cf  mov     r8d, ebp
0x14003d4d2  mov     dl, bl
0x14003d4d4  call    WPP_RECORDER_SF_d
0x14003d4d9  mov     rax, [rsi+18h]
0x14003d4dd  mov     edx, 0F6h
0x14003d4e2  mov     rcx, [rsi+28h]
0x14003d4e6  call    _guard_dispatch_icall
0x14003d4eb  mov     r13d, ebx
0x14003d4ee  mov     eax, [rsi+4]
0x14003d4f1  test    eax, eax
0x14003d4f3  jnz     loc_14003D585
0x14003d4f9  movzx   eax, byte ptr [r12+7]
0x14003d4ff  cmp     al, 8
0x14003d501  jz      loc_14003D6F3
0x14003d507  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d50e  jz      short loc_14003D52C
0x14003d510  mov     dword ptr [rsp+88h+var_60], eax
0x14003d514  mov     r9d, 10Ah
0x14003d51a  mov     r8d, ebp
0x14003d51d  mov     [rsp+88h+var_68], r15
0x14003d522  mov     dl, bl
0x14003d524  mov     rcx, r14
0x14003d527  call    WPP_RECORDER_SF_d
0x14003d52c  mov     rax, [rsi+18h]
0x14003d530  mov     edx, 4Eh ; 'N'
0x14003d535  mov     rcx, [rsi+28h]
0x14003d539  call    _guard_dispatch_icall
0x14003d53e  mov     rcx, rsi
0x14003d541  call    HUBDESC_ShouldEnforceWin8ValidationMutable
0x14003d546  movzx   edx, byte ptr [r12+7]
0x14003d54c  test    al, al
0x14003d54e  cmovnz  r13d, ebx
0x14003d552  lea     eax, [rdx-8]
0x14003d555  cmp     al, 38h ; '8'
0x14003d557  ja      short loc_14003D56D
0x14003d559  mov     rcx, 100000001000101h
0x14003d563  bt      rcx, rax
0x14003d567  jb      loc_14003D6F3
0x14003d56d  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d574  jz      loc_14003D686
0x14003d57a  mov     r9d, 10Bh
0x14003d580  jmp     loc_14003D670
0x14003d585  cmp     eax, 1
0x14003d588  jnz     short loc_14003D5E5
0x14003d58a  movzx   edx, byte ptr [r12+7]
0x14003d590  lea     eax, [rdx-8]
0x14003d593  cmp     al, 38h ; '8'
0x14003d595  ja      short loc_14003D5AB
0x14003d597  mov     rcx, 100000001000101h
0x14003d5a1  bt      rcx, rax
0x14003d5a5  jb      loc_14003D6F3
0x14003d5ab  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d5b2  jz      short loc_14003D5D0
0x14003d5b4  mov     dword ptr [rsp+88h+var_60], edx
0x14003d5b8  mov     r9d, 10Ch
0x14003d5be  mov     dl, bl
0x14003d5c0  mov     [rsp+88h+var_68], r15
0x14003d5c5  mov     r8d, ebp
0x14003d5c8  mov     rcx, r14
0x14003d5cb  call    WPP_RECORDER_SF_d
0x14003d5d0  mov     rax, [rsp+88h+var_50]
0x14003d5d5  mov     rcx, [rsp+88h+var_48]
0x14003d5da  mov     rax, [rax]
0x14003d5dd  mov     rcx, [rcx]
0x14003d5e0  jmp     loc_14003D68E
0x14003d5e5  cmp     eax, ebx
0x14003d5e7  jnz     loc_14003D69D
0x14003d5ed  movzx   eax, byte ptr [r12+7]
0x14003d5f3  cmp     al, 40h ; '@'
0x14003d5f5  jz      loc_14003D6F3
0x14003d5fb  cmp     cs:WPP_RECORDER_INITIALIZED, rdi; __annotation("TMF:",
0x14003d602  jz      short loc_14003D620
0x14003d604  mov     dword ptr [rsp+88h+var_60], eax
0x14003d608  mov     r9d, 10Dh
0x14003d60e  mov     r8d, ebp
0x14003d611  mov     [rsp+88h+var_68], r15
0x14003d616  mov     dl, bl
0x14003d618  mov     rcx, r14
0x14003d61b  call    WPP_RECORDER_SF_d
0x14003d620  mov     rax, [rsi+18h]
0x14003d624  mov     edx, 4Eh ; 'N'
0x14003d629  mov     rcx, [rsi+28h]
0x14003d62d  call    _guard_dispatch_icall
  ... truncated ...
```
