# EnumOverTable

- ea: `0x180002150`
- end: `0x180002376`
- name: `EnumOverTable`
- size: `550`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800018c8`
- `0x180003730`
- `0x1800064f0`
- `0x180006780`

## callees

- `0x180002150`
- `0x180002560`

## pseudocode

```c
__int64 __fastcall EnumOverTable(
        __int64 a1,
        _WORD *a2,
        _BYTE *a3,
        _OWORD *a4,
        unsigned __int16 a5,
        _BYTE *a6,
        unsigned int *a7,
        __int64 a8)
{
  _OWORD *v8; // rbx
  _BYTE *v9; // rdi
  __int64 v12; // rdx
  __int64 v13; // rax
  unsigned int *v14; // r9
  unsigned int v16; // r8d
  __int64 v17; // r14
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  unsigned __int16 v21; // bp
  int v22; // eax
  _BYTE *v23; // rcx
  int v24; // r11d
  _BYTE *v25; // r10
  int v26; // r11d
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int16 v30; // ax
  char *v31; // rdx
  int i; // ecx
  char v33; // al
  _OWORD v34[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v35; // [rsp+80h] [rbp+8h] BYREF

  v8 = v34;
  v34[0] = 0;
  if ( a4 )
    v8 = a4;
  v9 = a3;
  v34[1] = 0;
  if ( !*((_DWORD *)v8 + 4)
    && (unsigned int)SearchInTable(a1, (unsigned __int16)*a2, (_DWORD)a3, (_DWORD)v8, (__int64)&v35) )
  {
    *(_QWORD *)v8 = 0;
  }
  v12 = *(_QWORD *)v8;
  if ( *(_QWORD *)v8 )
    goto LABEL_14;
  v12 = *((_QWORD *)v8 + 1);
  if ( !v12 )
    goto LABEL_13;
  if ( *((_DWORD *)v8 + 4) == -1 )
    goto LABEL_14;
  if ( *(_QWORD *)(v12 + 8) )
  {
    do
    {
      v13 = *(_QWORD *)(v12 + 8);
      if ( *(_QWORD *)(v13 + 16) == v12 )
        break;
      v12 = *(_QWORD *)(v12 + 8);
    }
    while ( *(_QWORD *)(v13 + 8) );
  }
  v12 = *(_QWORD *)(v12 + 8);
  if ( v12 )
  {
LABEL_14:
    v14 = a7;
    if ( *a7 )
    {
      v16 = 0;
      v17 = a8;
      if ( !a6 )
      {
        while ( 1 )
        {
          v18 = v16++;
          *(_QWORD *)(v17 + 8 * v18) = *(_QWORD *)(v12 + 24);
          v19 = *(_QWORD *)(v12 + 32);
          if ( v19 )
          {
            v12 = *(_QWORD *)(v12 + 32);
            if ( *(_QWORD *)(v19 + 16) )
            {
              do
                v12 = *(_QWORD *)(v12 + 16);
              while ( *(_QWORD *)(v12 + 16) );
            }
          }
          else
          {
            if ( *(_QWORD *)(v12 + 8) )
            {
              do
              {
                v20 = *(_QWORD *)(v12 + 8);
                if ( *(_QWORD *)(v20 + 16) == v12 )
                  break;
                v12 = *(_QWORD *)(v12 + 8);
              }
              while ( *(_QWORD *)(v20 + 8) );
            }
            v12 = *(_QWORD *)(v12 + 8);
            if ( !v12 )
              goto LABEL_34;
          }
          if ( v16 >= *v14 )
            goto LABEL_46;
        }
      }
      v21 = a5;
      do
      {
        v22 = *(_DWORD *)(a1 + 8);
        if ( !v22 )
          goto LABEL_36;
        v23 = a6;
        v24 = v22 - 1;
        v25 = (_BYTE *)(v12 + 46);
        if ( v22 != 1 )
        {
          do
          {
            if ( *v25 != *v23 )
              break;
            ++v25;
            ++v23;
            --v24;
          }
          while ( v24 );
        }
        v26 = (unsigned __int8)*v25 - (unsigned __int8)*v23;
        if ( v26 )
        {
          if ( v26 > 0 )
            goto LABEL_34;
        }
        else
        {
LABEL_36:
          if ( *(_WORD *)(v12 + 44) > v21 )
            goto LABEL_34;
        }
        v27 = v16++;
        *(_QWORD *)(v17 + 8 * v27) = *(_QWORD *)(v12 + 24);
        v28 = *(_QWORD *)(v12 + 32);
        if ( v28 )
        {
          v12 = *(_QWORD *)(v12 + 32);
          if ( *(_QWORD *)(v28 + 16) )
          {
            do
              v12 = *(_QWORD *)(v12 + 16);
            while ( *(_QWORD *)(v12 + 16) );
          }
        }
        else
        {
          if ( *(_QWORD *)(v12 + 8) )
          {
            do
            {
              v29 = *(_QWORD *)(v12 + 8);
              if ( *(_QWORD *)(v29 + 16) == v12 )
                break;
              v12 = *(_QWORD *)(v12 + 8);
            }
            while ( *(_QWORD *)(v29 + 8) );
          }
          v12 = *(_QWORD *)(v12 + 8);
          if ( !v12 )
          {
LABEL_34:
            *v14 = v16;
            return 259;
          }
        }
      }
      while ( v16 < *v14 );
LABEL_46:
      *(_QWORD *)v8 = v12;
      if ( v9 )
      {
        v30 = *(_WORD *)(v12 + 44);
        v31 = (char *)(v12 + 46);
        *a2 = v30;
        for ( i = *(_DWORD *)(a1 + 8); i; --i )
        {
          v33 = *v31++;
          *v9++ = v33;
        }
      }
      *v14 = v16;
      return 0;
    }
    else
    {
      return 87;
    }
  }
  else
  {
LABEL_13:
    *a7 = 0;
    return 259;
  }
}

```

## disassembly

```asm
0x180002150  mov     rax, rsp
0x180002153  mov     [rax+10h], rbx
0x180002157  mov     [rax+18h], rbp
0x18000215b  push    rdi
0x18000215c  push    r12
0x18000215e  push    r13
0x180002160  push    r14
0x180002162  push    r15
0x180002164  sub     rsp, 50h
0x180002168  xor     r13d, r13d
0x18000216b  lea     rbx, [rax-48h]
0x18000216f  test    r9, r9
0x180002172  xorps   xmm0, xmm0
0x180002175  movups  xmmword ptr [rax-48h], xmm0
0x180002179  cmovnz  rbx, r9
0x18000217d  mov     rdi, r8
0x180002180  movups  xmmword ptr [rax-38h], xmm0
0x180002184  mov     r12, rdx
0x180002187  mov     r15, rcx
0x18000218a  cmp     [rbx+10h], r13d
0x18000218e  jnz     short loc_1800021AB
0x180002190  movzx   edx, word ptr [rdx]
0x180002193  lea     rax, [rax+8]
0x180002197  mov     r9, rbx
0x18000219a  mov     [rsp+78h+var_58], rax
0x18000219f  call    SearchInTable
0x1800021a4  test    eax, eax
0x1800021a6  jz      short loc_1800021AB
0x1800021a8  mov     [rbx], r13
0x1800021ab  mov     rdx, [rbx]
0x1800021ae  test    rdx, rdx
0x1800021b1  jnz     short loc_1800021F4
0x1800021b3  mov     rdx, [rbx+8]
0x1800021b7  test    rdx, rdx
0x1800021ba  jz      short loc_1800021E4
0x1800021bc  cmp     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800021c0  jz      short loc_1800021F4
0x1800021c2  cmp     [rdx+8], r13
0x1800021c6  jz      short loc_1800021DB
0x1800021c8  mov     rax, [rdx+8]
0x1800021cc  cmp     [rax+10h], rdx
0x1800021d0  jz      short loc_1800021DB
0x1800021d2  mov     rdx, rax
0x1800021d5  cmp     [rax+8], r13
0x1800021d9  jnz     short loc_1800021C8
0x1800021db  mov     rdx, [rdx+8]
0x1800021df  test    rdx, rdx
0x1800021e2  jnz     short loc_1800021F4
0x1800021e4  mov     rax, [rsp+78h+arg_30]
0x1800021ec  mov     [rax], r13d
0x1800021ef  jmp     loc_1800022C4
0x1800021f4  mov     r9, [rsp+78h+arg_30]
0x1800021fc  cmp     [r9], r13d
0x1800021ff  jnz     short loc_18000220B
0x180002201  mov     eax, 57h ; 'W'
0x180002206  jmp     loc_1800022C9
0x18000220b  mov     r8d, r13d
0x18000220e  mov     r14, [rsp+78h+arg_38]
0x180002216  cmp     [rsp+78h+arg_28], r13
0x18000221e  jnz     short loc_180002278
0x180002220  mov     rax, [rdx+18h]
0x180002224  mov     ecx, r8d
0x180002227  inc     r8d
0x18000222a  mov     [r14+rcx*8], rax
0x18000222e  mov     rax, [rdx+20h]
0x180002232  test    rax, rax
0x180002235  jz      short loc_18000224C
0x180002237  mov     rdx, rax
0x18000223a  cmp     [rax+10h], r13
0x18000223e  jz      short loc_18000226E
0x180002240  mov     rdx, [rdx+10h]
0x180002244  cmp     [rdx+10h], r13
0x180002248  jnz     short loc_180002240
0x18000224a  jmp     short loc_18000226E
0x18000224c  cmp     [rdx+8], r13
0x180002250  jz      short loc_180002265
0x180002252  mov     rax, [rdx+8]
0x180002256  cmp     [rax+10h], rdx
0x18000225a  jz      short loc_180002265
0x18000225c  mov     rdx, rax
0x18000225f  cmp     [rax+8], r13
0x180002263  jnz     short loc_180002252
0x180002265  mov     rdx, [rdx+8]
0x180002269  test    rdx, rdx
0x18000226c  jz      short loc_1800022C1
0x18000226e  cmp     r8d, [r9]
0x180002271  jb      short loc_180002220
0x180002273  jmp     loc_180002340
0x180002278  movzx   ebp, [rsp+78h+arg_20]
0x180002280  mov     eax, [r15+8]
0x180002284  test    eax, eax
0x180002286  jz      short loc_1800022E3
0x180002288  mov     rcx, [rsp+78h+arg_28]
0x180002290  lea     r11d, [rax-1]
0x180002294  lea     r10, [rdx+2Eh]
0x180002298  test    r11d, r11d
0x18000229b  jz      short loc_1800022B0
0x18000229d  mov     al, [rcx]
0x18000229f  cmp     [r10], al
0x1800022a2  jnz     short loc_1800022B0
0x1800022a4  inc     r10
0x1800022a7  inc     rcx
0x1800022aa  add     r11d, 0FFFFFFFFh
0x1800022ae  jnz     short loc_18000229D
0x1800022b0  movzx   r11d, byte ptr [r10]
0x1800022b4  movzx   eax, byte ptr [rcx]
0x1800022b7  sub     r11d, eax
0x1800022ba  jz      short loc_1800022E3
0x1800022bc  test    r11d, r11d
0x1800022bf  jle     short loc_1800022E9
0x1800022c1  mov     [r9], r8d
0x1800022c4  mov     eax, 103h
0x1800022c9  lea     r11, [rsp+78h+var_28]
0x1800022ce  mov     rbx, [r11+38h]
0x1800022d2  mov     rbp, [r11+40h]
0x1800022d6  mov     rsp, r11
0x1800022d9  pop     r15
0x1800022db  pop     r14
0x1800022dd  pop     r13
0x1800022df  pop     r12
0x1800022e1  pop     rdi
0x1800022e2  retn
0x1800022e3  cmp     [rdx+2Ch], bp
0x1800022e7  ja      short loc_1800022C1
0x1800022e9  mov     rax, [rdx+18h]
0x1800022ed  mov     ecx, r8d
0x1800022f0  inc     r8d
0x1800022f3  mov     [r14+rcx*8], rax
0x1800022f7  mov     rax, [rdx+20h]
0x1800022fb  test    rax, rax
0x1800022fe  jz      short loc_180002315
0x180002300  mov     rdx, rax
0x180002303  cmp     [rax+10h], r13
0x180002307  jz      short loc_180002337
0x180002309  mov     rdx, [rdx+10h]
0x18000230d  cmp     [rdx+10h], r13
0x180002311  jnz     short loc_180002309
0x180002313  jmp     short loc_180002337
0x180002315  cmp     [rdx+8], r13
0x180002319  jz      short loc_18000232E
0x18000231b  mov     rax, [rdx+8]
0x18000231f  cmp     [rax+10h], rdx
0x180002323  jz      short loc_18000232E
0x180002325  mov     rdx, rax
0x180002328  cmp     [rax+8], r13
0x18000232c  jnz     short loc_18000231B
0x18000232e  mov     rdx, [rdx+8]
0x180002332  test    rdx, rdx
0x180002335  jz      short loc_1800022C1
0x180002337  cmp     r8d, [r9]
0x18000233a  jb      loc_180002280
0x180002340  mov     [rbx], rdx
0x180002343  test    rdi, rdi
0x180002346  jz      short loc_18000236C
0x180002348  movzx   eax, word ptr [rdx+2Ch]
0x18000234c  add     rdx, 2Eh ; '.'
0x180002350  mov     [r12], ax
0x180002355  mov     ecx, [r15+8]
0x180002359  test    ecx, ecx
0x18000235b  jz      short loc_18000236C
0x18000235d  mov     al, [rdx]
0x18000235f  inc     rdx
0x180002362  mov     [rdi], al
0x180002364  inc     rdi
0x180002367  add     ecx, 0FFFFFFFFh
0x18000236a  jnz     short loc_18000235D
0x18000236c  mov     [r9], r8d
0x18000236f  xor     eax, eax
0x180002371  jmp     loc_1800022C9
```
