# _RNvNtCs9MWeMO1rkJG_4core3fmt5write

- ea: `0x140006620`
- end: `0x140006821`
- name: `_RNvNtCs9MWeMO1rkJG_4core3fmt5write`
- size: `513`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400072e0`
- `0x140007910`
- `0x140007c60`

## callees

- `0x140006620`
- `0x140017a10`
- `0x140017a50`

## pseudocode

```c
char __fastcall RNvNtCs9MWeMO1rkJG_4core3fmt5write(__int64 a1, __int64 a2, unsigned __int8 *a3, unsigned __int64 a4)
{
  unsigned __int8 *v5; // r13
  unsigned __int8 v8; // al
  unsigned __int8 (__fastcall *v9)(__int64, unsigned __int8 *, __int64); // r14
  __int64 v10; // r15
  unsigned __int8 *v11; // r12
  __int64 v12; // rbp
  __int64 v13; // rax
  __int64 v14; // r12
  int v15; // ecx
  unsigned __int16 v16; // dx
  unsigned __int16 v17; // r8
  char result; // al
  _BYTE v19[40]; // [rsp+0h] [rbp-88h] BYREF
  _QWORD v20[2]; // [rsp+28h] [rbp-60h] BYREF
  __int64 v21; // [rsp+38h] [rbp-50h]
  __int64 v22; // [rsp+40h] [rbp-48h]

  v5 = a3;
  if ( (a4 & 1) == 0 )
  {
    v8 = *a3;
    if ( !*a3 )
    {
LABEL_32:
      result = 0;
      goto LABEL_34;
    }
    v9 = *(unsigned __int8 (__fastcall **)(__int64, unsigned __int8 *, __int64))(a2 + 24);
    v10 = 0;
    while ( 1 )
    {
      v11 = v5 + 1;
      v12 = v8;
      if ( (v8 & 0x80u) == 0 )
      {
        if ( v9(a1, v5 + 1, v8) )
          goto LABEL_33;
        v11 += v12;
        goto LABEL_4;
      }
      if ( v8 == 0x80 )
      {
        v14 = *(unsigned __int16 *)(v5 + 1);
        if ( v9(a1, v5 + 3, v14) )
          goto LABEL_33;
        v11 = &v5[v14 + 3];
        goto LABEL_4;
      }
      if ( v8 != 192 )
        break;
      v13 = 16 * v10;
      v21 = 1610612768;
LABEL_26:
      v20[0] = a1;
      v20[1] = a2;
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD *))(a4 + v13 + 8))(*(_QWORD *)(a4 + v13), v20) )
      {
LABEL_33:
        result = 1;
LABEL_34:
        if ( _security_cookie != ((unsigned __int64)v19 ^ v22) )
LABEL_35:
          JUMPOUT(0x140006820LL);
        return result;
      }
      ++v10;
LABEL_4:
      v8 = *v11;
      v5 = v11;
      if ( !*v11 )
        goto LABEL_32;
    }
    v15 = 1610612768;
    if ( (v8 & 1) != 0 )
    {
      v15 = *(_DWORD *)(v5 + 1);
      v11 = v5 + 5;
    }
    if ( (v8 & 2) != 0 )
    {
      v16 = *(_WORD *)v11;
      v11 += 2;
      if ( (v8 & 4) != 0 )
      {
LABEL_17:
        v17 = *(_WORD *)v11;
        v11 += 2;
        if ( (v8 & 8) == 0 )
        {
LABEL_22:
          if ( (v8 & 0x10) != 0 )
          {
            v16 = *(_WORD *)(a4 + 16 * (unsigned int)v16 + 8);
            if ( (v8 & 0x20) == 0 )
              goto LABEL_25;
          }
          else if ( (v8 & 0x20) == 0 )
          {
LABEL_25:
            v13 = 16 * v10;
            LODWORD(v21) = v15;
            WORD2(v21) = v16;
            HIWORD(v21) = v17;
            goto LABEL_26;
          }
          v17 = *(_WORD *)(a4 + 16 * (unsigned int)v17 + 8);
          goto LABEL_25;
        }
LABEL_21:
        v10 = *(unsigned __int16 *)v11;
        v11 += 2;
        goto LABEL_22;
      }
    }
    else
    {
      v16 = 0;
      if ( (v8 & 4) != 0 )
        goto LABEL_17;
    }
    v17 = 0;
    if ( (v8 & 8) == 0 )
      goto LABEL_22;
    goto LABEL_21;
  }
  if ( _security_cookie != ((unsigned __int64)v19 ^ v22) )
    goto LABEL_35;
  return (*(__int64 (__fastcall **)(__int64, unsigned __int8 *, unsigned __int64))(a2 + 24))(a1, a3, a4 >> 1);
}

```

## disassembly

```asm
0x140006620  push    r15
0x140006622  push    r14
0x140006624  push    r13
0x140006626  push    r12
0x140006628  push    rsi
0x140006629  push    rdi
0x14000662a  push    rbp
0x14000662b  push    rbx
0x14000662c  sub     rsp, 48h
0x140006630  mov     rsi, r9
0x140006633  mov     r13, r8
0x140006636  mov     rbx, rdx
0x140006639  mov     rdi, rcx
0x14000663c  mov     rax, cs:__security_cookie
0x140006643  xor     rax, rsp
0x140006646  mov     [rsp+88h+var_48], rax
0x14000664b  test    sil, 1
0x14000664f  jnz     loc_1400067AD
0x140006655  movzx   eax, byte ptr [r13+0]
0x14000665a  test    al, al
0x14000665c  jz      loc_1400067E8
0x140006662  mov     r14, [rbx+18h]
0x140006666  xor     r15d, r15d
0x140006669  jmp     short loc_140006680
0x140006670  movzx   eax, byte ptr [r12]
0x140006675  mov     r13, r12
0x140006678  test    al, al
0x14000667a  jz      loc_1400067E8
0x140006680  lea     r12, [r13+1]
0x140006684  movzx   ebp, al
0x140006687  test    al, al
0x140006689  js      short loc_1400066B0
0x14000668b  mov     rcx, rdi
0x14000668e  mov     rdx, r12
0x140006691  mov     r8, rbp
0x140006694  mov     rax, r14
0x140006697  call    cs:__guard_dispatch_icall_fptr
0x14000669d  test    al, al
0x14000669f  jnz     loc_1400067EC
0x1400066a5  add     r12, rbp
0x1400066a8  jmp     short loc_140006670
0x1400066b0  cmp     al, 80h
0x1400066b2  jz      short loc_1400066D1
0x1400066b4  cmp     ebp, 0C0h
0x1400066ba  jnz     short loc_1400066FD
0x1400066bc  mov     rax, r15
0x1400066bf  shl     rax, 4
0x1400066c3  mov     [rsp+88h+var_50], 60000020h
0x1400066cc  jmp     loc_140006772
0x1400066d1  movzx   r12d, word ptr [r13+1]
0x1400066d6  lea     rdx, [r13+3]
0x1400066da  mov     rcx, rdi
0x1400066dd  mov     r8, r12
0x1400066e0  mov     rax, r14
0x1400066e3  call    cs:__guard_dispatch_icall_fptr
0x1400066e9  test    al, al
0x1400066eb  jnz     loc_1400067EC
0x1400066f1  add     r12, r13
0x1400066f4  add     r12, 3
0x1400066f8  jmp     loc_140006670
0x1400066fd  mov     ecx, 60000020h
0x140006702  test    al, 1
0x140006704  jz      short loc_140006711
0x140006706  mov     ecx, [r13+1]
0x14000670a  add     r13, 5
0x14000670e  mov     r12, r13
0x140006711  test    al, 2
0x140006713  jnz     short loc_14000672A
0x140006715  xor     edx, edx
0x140006717  test    al, 4
0x140006719  jz      short loc_140006737
0x14000671b  movzx   r8d, word ptr [r12]
0x140006720  add     r12, 2
0x140006724  test    al, 8
0x140006726  jnz     short loc_14000673E
0x140006728  jmp     short loc_140006747
0x14000672a  movzx   edx, word ptr [r12]
0x14000672f  add     r12, 2
0x140006733  test    al, 4
0x140006735  jnz     short loc_14000671B
0x140006737  xor     r8d, r8d
0x14000673a  test    al, 8
0x14000673c  jz      short loc_140006747
0x14000673e  movzx   r15d, word ptr [r12]
0x140006743  add     r12, 2
0x140006747  test    al, 10h
0x140006749  jnz     short loc_14000679C
0x14000674b  test    al, 20h
0x14000674d  jz      short loc_14000675C
0x14000674f  movzx   eax, r8w
0x140006753  shl     eax, 4
0x140006756  movzx   r8d, word ptr [rsi+rax+8]
0x14000675c  mov     rax, r15
0x14000675f  shl     rax, 4
0x140006763  mov     dword ptr [rsp+88h+var_50], ecx
0x140006767  mov     word ptr [rsp+88h+var_50+4], dx
0x14000676c  mov     word ptr [rsp+88h+var_50+6], r8w
0x140006772  mov     [rsp+88h+var_60], rdi
0x140006777  mov     [rsp+88h+var_58], rbx
0x14000677c  mov     rcx, [rsi+rax]
0x140006780  mov     rax, [rsi+rax+8]
0x140006785  lea     rdx, [rsp+88h+var_60]
0x14000678a  call    cs:__guard_dispatch_icall_fptr
0x140006790  test    al, al
0x140006792  jnz     short loc_1400067EC
0x140006794  inc     r15
0x140006797  jmp     loc_140006670
0x14000679c  movzx   edx, dx
0x14000679f  shl     edx, 4
0x1400067a2  movzx   edx, word ptr [rsi+rdx+8]
0x1400067a7  test    al, 20h
0x1400067a9  jnz     short loc_14000674F
0x1400067ab  jmp     short loc_14000675C
0x1400067ad  mov     rax, [rsp+88h+var_48]
0x1400067b2  xor     rax, rsp
0x1400067b5  mov     rcx, cs:__security_cookie
0x1400067bc  cmp     rcx, rax
0x1400067bf  jnz     short loc_140006813
0x1400067c1  shr     rsi, 1
0x1400067c4  mov     rax, [rbx+18h]
0x1400067c8  mov     rcx, rdi
0x1400067cb  mov     rdx, r13
0x1400067ce  mov     r8, rsi
0x1400067d1  add     rsp, 48h
0x1400067d5  pop     rbx
0x1400067d6  pop     rbp
0x1400067d7  pop     rdi
0x1400067d8  pop     rsi
0x1400067d9  pop     r12
0x1400067db  pop     r13
0x1400067dd  pop     r14
0x1400067df  pop     r15
0x1400067e1  jmp     cs:__guard_dispatch_icall_fptr
0x1400067e8  xor     eax, eax
0x1400067ea  jmp     short loc_1400067EE
0x1400067ec  mov     al, 1
0x1400067ee  mov     rcx, [rsp+88h+var_48]
0x1400067f3  xor     rcx, rsp
0x1400067f6  mov     rdx, cs:__security_cookie
0x1400067fd  cmp     rdx, rcx
0x140006800  jnz     short loc_140006813
0x140006802  add     rsp, 48h
0x140006806  pop     rbx
0x140006807  pop     rbp
0x140006808  pop     rdi
0x140006809  pop     rsi
0x14000680a  pop     r12
0x14000680c  pop     r13
0x14000680e  pop     r14
0x140006810  pop     r15
0x140006812  retn
0x140006813  mov     rcx, [rsp+88h+var_48]
0x140006818  xor     rcx, rsp; StackCookie
0x14000681b  call    __security_check_cookie
```
