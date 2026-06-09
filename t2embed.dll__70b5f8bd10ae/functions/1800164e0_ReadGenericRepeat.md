# ReadGenericRepeat

- ea: `0x1800164e0`
- end: `0x18001676a`
- name: `ReadGenericRepeat`
- size: `650`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000fe8c`
- `0x1800121e4`
- `0x18001400c`
- `0x180014cd4`
- `0x180016770`
- `0x18001a6c4`
- `0x180027c1c`
- `0x180027d28`
- `0x1800281d0`
- `0x180029228`

## callees

- `0x1800164e0`
- `0x18001cd3c`

## pseudocode

```c
__int64 __fastcall ReadGenericRepeat(
        __int64 *a1,
        __int64 a2,
        unsigned __int8 *a3,
        unsigned int a4,
        _DWORD *a5,
        unsigned __int16 a6,
        unsigned __int16 a7)
{
  unsigned __int8 *v9; // r9
  __int64 *v10; // r10
  unsigned __int16 v11; // r13
  __int64 v12; // r11
  unsigned __int16 v13; // ax
  __int64 v14; // r8
  unsigned __int16 v15; // di
  unsigned __int16 v16; // r14
  unsigned __int8 v17; // dl
  __int64 v18; // r9
  unsigned int v19; // ecx
  __int64 result; // rax
  unsigned int v21; // r9d
  __int64 v22; // rcx
  int v23; // eax
  int v24; // edx
  int v25; // edx
  unsigned int v26; // ecx
  __int64 v27; // rax
  __int16 v28; // dx
  __int16 v29; // ax
  int v30; // r8d
  __int16 v31; // dx
  __int16 v32; // ax
  unsigned __int16 v33; // [rsp+20h] [rbp-38h]

  v9 = a3;
  v10 = a1;
  v11 = 0;
  LOWORD(v12) = 1;
  while ( 2 )
  {
    if ( v11 >= a6 )
    {
      *a5 = a7 * a6;
      return 0;
    }
    else
    {
      v13 = *v9;
      v14 = a4;
      v33 = v13;
      v15 = 0;
      v16 = v12;
      while ( v16 <= v13 )
      {
        v17 = v9[v16];
        if ( (v17 & 7) == 1 )
        {
          if ( (unsigned __int64)v15 + 1 > a7 )
            return 1003;
          if ( (v17 & 0x10) != 0 )
          {
            *(_BYTE *)(v15 + a2) = 0;
          }
          else
          {
            result = ReadByte(v10, v15 + a2, v14);
            if ( (_WORD)result )
              return result;
            v9 = a3;
            v14 = (unsigned int)(v12 + v30);
          }
          v29 = v12;
        }
        else if ( (v9[v16] & 7) == 2 )
        {
          if ( (unsigned __int64)v15 + 2 > a7 )
            return 1003;
          if ( (v17 & 0x10) != 0 )
          {
            v28 = 0;
          }
          else
          {
            if ( (v17 & 0x20) != 0 )
            {
              if ( !*v10 )
                return 1001;
              v19 = v14 + 2;
              if ( (int)v14 + 2 < (unsigned int)v14 || v19 > *((_DWORD *)v10 + 2) )
                return 1001;
              v28 = *(_WORD *)((unsigned int)v14 + *v10);
            }
            else
            {
              v18 = *v10;
              if ( !*v10 )
                return 1001;
              v19 = v14 + 2;
              if ( (int)v14 + 2 < (unsigned int)v14 || v19 > *((_DWORD *)v10 + 2) )
                return 1001;
              v31 = *(unsigned __int8 *)((unsigned int)v14 + v18 + 1);
              v32 = *(unsigned __int8 *)((unsigned int)v14 + v18);
              v9 = a3;
              v28 = (v32 << 8) | v31;
            }
            v14 = v19;
          }
          v29 = 2;
          *(_WORD *)(v15 + a2) = v28;
          LOWORD(v12) = 1;
        }
        else
        {
          if ( (v9[v16] & 7) != 4 || (unsigned __int64)v15 + 4 > a7 )
            return 1003;
          if ( (v17 & 0x10) != 0 )
          {
            v25 = 0;
          }
          else if ( (v17 & 0x20) != 0 )
          {
            if ( !*v10 )
              return 1001;
            v26 = v14 + 4;
            if ( (int)v14 + 4 < (unsigned int)v14 || v26 > *((_DWORD *)v10 + 2) )
              return 1001;
            v27 = (unsigned int)v14;
            v14 = v26;
            v25 = *(_DWORD *)(v27 + *v10);
          }
          else
          {
            v12 = *v10;
            if ( !*v10 )
              return 1001;
            v21 = v14 + 4;
            if ( (int)v14 + 4 < (unsigned int)v14 || v21 > *((_DWORD *)v10 + 2) )
              return 1001;
            v22 = (unsigned int)v14;
            v14 = v21;
            v9 = a3;
            v23 = *(unsigned __int8 *)(v22 + v12 + 3);
            v24 = (*(unsigned __int8 *)(v22 + v12 + 2)
                 | (((*(unsigned __int8 *)(v22 + v12) << 8) | *(unsigned __int8 *)(v22 + v12 + 1)) << 8)) << 8;
            LOWORD(v12) = 1;
            v25 = v23 | v24;
          }
          *(_DWORD *)(v15 + a2) = v25;
          v29 = 4;
        }
        v16 += v12;
        v15 += v29;
        v13 = v33;
      }
      if ( v15 >= a7 )
      {
        a2 += a7;
        a4 += (unsigned __int16)(v14 - a4);
        v11 += v12;
        continue;
      }
      return 1003;
    }
  }
}

```

## disassembly

```asm
0x1800164e0  mov     [rsp+arg_0], rbx
0x1800164e5  mov     [rsp+arg_8], rbp
0x1800164ea  mov     [rsp+arg_10], r8
0x1800164ef  push    rsi
0x1800164f0  push    rdi
0x1800164f1  push    r13
0x1800164f3  push    r14
0x1800164f5  push    r15
0x1800164f7  sub     rsp, 30h
0x1800164fb  movzx   r15d, [rsp+58h+arg_30]
0x180016504  xor     ebx, ebx
0x180016506  mov     ebp, r9d
0x180016509  mov     rsi, rdx
0x18001650c  mov     r9, r8
0x18001650f  mov     r10, rcx
0x180016512  mov     r13d, ebx
0x180016515  lea     r11d, [rbx+1]
0x180016519  cmp     r13w, [rsp+58h+arg_28]
0x180016522  jnb     loc_180016724
0x180016528  movzx   eax, byte ptr [r9]
0x18001652c  mov     r8d, ebp
0x18001652f  mov     [rsp+58h+var_38], ax
0x180016534  mov     edi, ebx
0x180016536  movzx   r14d, r11w
0x18001653a  cmp     r14w, ax
0x18001653e  ja      loc_18001663B
0x180016544  movzx   eax, r14w
0x180016548  movzx   edx, byte ptr [rax+r9]
0x18001654d  mov     ecx, edx
0x18001654f  and     ecx, 7
0x180016552  sub     ecx, 1
0x180016555  jz      loc_1800166B2
0x18001655b  sub     ecx, 1
0x18001655e  jnz     short loc_1800165BD
0x180016560  movzx   ecx, di
0x180016563  lea     rax, [rcx+2]
0x180016567  cmp     rax, r15
0x18001656a  ja      loc_1800166A8
0x180016570  lea     r11, [rcx+rsi]
0x180016574  test    dl, 10h
0x180016577  jnz     loc_180016688
0x18001657d  test    dl, 20h
0x180016580  jnz     loc_1800166CC
0x180016586  mov     r9, [r10]
0x180016589  test    r9, r9
0x18001658c  jz      short loc_1800165A1
0x18001658e  lea     ecx, [r8+2]
0x180016592  cmp     ecx, r8d
0x180016595  jb      short loc_1800165A1
0x180016597  cmp     ecx, [r10+8]
0x18001659b  jbe     loc_180016748
0x1800165a1  mov     eax, 3E9h
0x1800165a6  mov     rbx, [rsp+58h+arg_0]
0x1800165ab  mov     rbp, [rsp+58h+arg_8]
0x1800165b0  add     rsp, 30h
0x1800165b4  pop     r15
0x1800165b6  pop     r14
0x1800165b8  pop     r13
0x1800165ba  pop     rdi
0x1800165bb  pop     rsi
0x1800165bc  retn
0x1800165bd  cmp     ecx, 2
0x1800165c0  jnz     loc_1800166A8
0x1800165c6  movzx   ecx, di
0x1800165c9  lea     rax, [rcx+4]
0x1800165cd  cmp     rax, r15
0x1800165d0  ja      loc_1800166A8
0x1800165d6  lea     rbx, [rcx+rsi]
0x1800165da  test    dl, 10h
0x1800165dd  jnz     loc_1800166F8
0x1800165e3  test    dl, 20h
0x1800165e6  jnz     short loc_18001665A
0x1800165e8  mov     r11, [r10]
0x1800165eb  test    r11, r11
0x1800165ee  jz      short loc_1800165A1
0x1800165f0  lea     r9d, [r8+4]
0x1800165f4  cmp     r9d, r8d
0x1800165f7  jb      short loc_1800165A1
0x1800165f9  cmp     r9d, [r10+8]
0x1800165fd  ja      short loc_1800165A1
0x1800165ff  mov     ecx, r8d
0x180016602  mov     r8d, r9d
0x180016605  mov     r9, [rsp+58h+arg_10]
0x18001660a  movzx   eax, byte ptr [rcx+r11]
0x18001660f  movzx   edx, byte ptr [rcx+r11+1]
0x180016615  shl     eax, 8
0x180016618  or      edx, eax
0x18001661a  movzx   eax, byte ptr [rcx+r11+2]
0x180016620  shl     edx, 8
0x180016623  or      edx, eax
0x180016625  movzx   eax, byte ptr [rcx+r11+3]
0x18001662b  shl     edx, 8
0x18001662e  mov     r11d, 1
0x180016634  or      edx, eax
0x180016636  jmp     loc_1800166FA
0x18001663b  cmp     di, [rsp+58h+arg_30]
0x180016643  jb      short loc_1800166A8
0x180016645  sub     r8d, ebp
0x180016648  add     rsi, r15
0x18001664b  movzx   eax, r8w
0x18001664f  add     ebp, eax
0x180016651  add     r13w, r11w
0x180016655  jmp     loc_180016519
0x18001665a  mov     rdx, [r10]
0x18001665d  test    rdx, rdx
0x180016660  jz      loc_1800165A1
0x180016666  lea     ecx, [r8+4]
0x18001666a  cmp     ecx, r8d
0x18001666d  jb      loc_1800165A1
0x180016673  cmp     ecx, [r10+8]
0x180016677  ja      loc_1800165A1
0x18001667d  mov     eax, r8d
0x180016680  mov     r8d, ecx
0x180016683  mov     edx, [rax+rdx]
0x180016686  jmp     short loc_1800166FA
0x180016688  mov     edx, ebx
0x18001668a  mov     eax, 2
0x18001668f  mov     [r11], dx
0x180016693  lea     r11d, [rax-1]
0x180016697  add     r14w, r11w
0x18001669b  add     di, ax
0x18001669e  movzx   eax, [rsp+58h+var_38]
0x1800166a3  jmp     loc_18001653A
0x1800166a8  mov     eax, 3EBh
0x1800166ad  jmp     loc_1800165A6
0x1800166b2  movzx   ecx, di
0x1800166b5  lea     rax, [rcx+1]
0x1800166b9  cmp     rax, r15
0x1800166bc  ja      short loc_1800166A8
0x1800166be  test    dl, 10h
0x1800166c1  jz      short loc_180016705
0x1800166c3  mov     [rcx+rsi], bl
0x1800166c6  movzx   eax, r11w
0x1800166ca  jmp     short loc_180016697
0x1800166cc  mov     rdx, [r10]
0x1800166cf  test    rdx, rdx
0x1800166d2  jz      loc_1800165A1
0x1800166d8  lea     ecx, [r8+2]
0x1800166dc  cmp     ecx, r8d
0x1800166df  jb      loc_1800165A1
0x1800166e5  cmp     ecx, [r10+8]
0x1800166e9  ja      loc_1800165A1
0x1800166ef  mov     eax, r8d
0x1800166f2  movzx   edx, word ptr [rax+rdx]
0x1800166f6  jmp     short loc_180016762
0x1800166f8  xor     edx, edx
0x1800166fa  mov     [rbx], edx
0x1800166fc  mov     eax, 4
0x180016701  xor     ebx, ebx
0x180016703  jmp     short loc_180016697
0x180016705  lea     rdx, [rcx+rsi]
0x180016709  mov     rcx, r10
0x18001670c  call    ReadByte
0x180016711  test    ax, ax
0x180016714  jnz     loc_1800165A6
0x18001671a  mov     r9, [rsp+58h+arg_10]
0x18001671f  add     r8d, r11d
0x180016722  jmp     short loc_1800166C6
0x180016724  movzx   eax, [rsp+58h+arg_30]
0x18001672c  movzx   ecx, [rsp+58h+arg_28]
0x180016734  imul    ecx, eax
0x180016737  mov     rax, [rsp+58h+arg_20]
0x18001673f  mov     [rax], ecx
0x180016741  mov     eax, ebx
0x180016743  jmp     loc_1800165A6
0x180016748  mov     eax, r8d
0x18001674b  movzx   edx, byte ptr [rax+r9+1]
0x180016751  movzx   eax, byte ptr [rax+r9]
0x180016756  mov     r9, [rsp+58h+arg_10]
0x18001675b  shl     ax, 8
0x18001675f  or      dx, ax
0x180016762  mov     r8d, ecx
0x180016765  jmp     loc_18001668A
```
