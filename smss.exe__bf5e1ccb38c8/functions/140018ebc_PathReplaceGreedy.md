# PathReplaceGreedy

- ea: `0x140018ebc`
- end: `0x140019122`
- name: `PathReplaceGreedy`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x14000b21c`

## callees

- `0x140018ebc`
- `0x14001cc40`

## import_xrefs

- `ntdll!RtlUpcaseUnicodeChar` at `0x140018f4b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140018f5f`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140018f4b`
- `ntdll!RtlUpcaseUnicodeChar` at `0x140018f5f`

## pseudocode

```c
__int64 __fastcall PathReplaceGreedy(unsigned __int16 *a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int16 v4; // cx
  int v6; // r9d
  unsigned __int16 *v7; // r13
  unsigned __int16 v8; // r14
  unsigned __int16 v9; // si
  unsigned int v10; // ecx
  WCHAR v11; // bx
  __int64 v12; // rdx
  unsigned __int16 *v13; // r11
  unsigned int v14; // r8d
  int v15; // ecx
  int v17; // r9d
  int i; // r8d
  unsigned __int16 v19; // dx
  unsigned __int16 v20; // r10
  unsigned __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // r9d
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // rcx
  _WORD v29[4]; // [rsp+10h] [rbp-10h] BYREF
  unsigned __int16 *v30; // [rsp+18h] [rbp-8h]
  int v31; // [rsp+20h] [rbp+0h]
  unsigned __int16 *v32; // [rsp+28h] [rbp+8h]

  v32 = a2;
  v4 = *a3;
  if ( *a3 >= *a1 )
  {
    v6 = 0;
    v31 = 0;
    v7 = 0;
    v8 = 0;
    if ( (v4 & 0xFFFE) != 0 )
    {
      do
      {
        v9 = 0;
        if ( (*a1 & 0xFFFE) != 0 )
        {
          do
          {
            v10 = v8 + v9;
            if ( v10 >= *a3 >> 1 )
              break;
            v11 = RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * v10));
            if ( v11 != RtlUpcaseUnicodeChar(*(_WORD *)(*((_QWORD *)a1 + 1) + 2LL * v9)) )
              break;
            ++v9;
          }
          while ( v9 < (unsigned __int16)(*a1 >> 1) );
          v6 = v31;
        }
        if ( v9 == *a1 >> 1 )
        {
          v12 = v8 + (unsigned int)v9;
          if ( (_DWORD)v12 == *a3 >> 1 || *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v12) == 92 )
          {
            v30 = v7;
            LOWORD(v6) = v6 + 1;
            v29[0] = v8;
            v31 = v6;
            v7 = v29;
            v29[1] = v8 + v9;
          }
        }
        ++v8;
      }
      while ( v8 < (unsigned __int16)(*a3 >> 1) );
      if ( v7 )
      {
        v13 = v32;
        v14 = *a3;
        v15 = *v32;
        if ( (unsigned __int16)v15 > *a1 && v14 + (unsigned __int16)v6 * (v15 - *a1) > a3[1] )
          return 2147483653LL;
        v17 = (a3[1] >> 1) - 1;
        for ( i = (v14 >> 1) - 1; i >= 0; --i )
        {
          if ( v7 && i < v7[1] )
          {
            v19 = *v13;
            if ( (*v13 & 0xFFFE) != 0 )
            {
              v20 = 0;
              do
              {
                v21 = v19;
                v22 = v20++;
                v23 = v17--;
                *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v23) = *(_WORD *)(*((_QWORD *)v13 + 1) + 2 * ((v21 >> 1) - v22) - 2);
                v19 = *v13;
              }
              while ( v20 < (unsigned __int16)(*v13 >> 1) );
            }
            i = *v7;
            v7 = (unsigned __int16 *)*((_QWORD *)v7 + 1);
          }
          else
          {
            v24 = v17--;
            *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v24) = *(_WORD *)(*((_QWORD *)a3 + 1) + 2LL * i);
          }
        }
        v25 = v17 + 1;
        v26 = 0;
        while ( v25 < a3[1] >> 1 )
        {
          v27 = v25++;
          v28 = v26++;
          *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v28) = *(_WORD *)(*((_QWORD *)a3 + 1) + 2 * v27);
        }
        *a3 = 2 * v26;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140018ebc  push    rbp
0x140018ebe  push    rbx
0x140018ebf  push    rsi
0x140018ec0  push    rdi
0x140018ec1  push    r12
0x140018ec3  push    r13
0x140018ec5  push    r14
0x140018ec7  push    r15
0x140018ec9  sub     rsp, 48h
0x140018ecd  lea     rbp, [rsp+20h]
0x140018ed2  mov     rax, cs:__security_cookie
0x140018ed9  xor     rax, rbp
0x140018edc  mov     [rbp+60h+var_50], rax
0x140018ee0  mov     r15, rcx
0x140018ee3  mov     [rbp+60h+var_58], rdx
0x140018ee7  movzx   ecx, word ptr [r8]
0x140018eeb  mov     rdi, r8
0x140018eee  cmp     cx, [r15]
0x140018ef2  jb      loc_140019103
0x140018ef8  xor     r9d, r9d
0x140018efb  mov     r10d, 0FFFEh
0x140018f01  and     cx, r10w
0x140018f05  mov     [rbp+60h+var_60], r9d
0x140018f09  xor     r13d, r13d
0x140018f0c  xor     r14d, r14d
0x140018f0f  xor     eax, eax
0x140018f11  cmp     ax, cx
0x140018f14  jnb     loc_140019103
0x140018f1a  lea     ebx, [rax+1]
0x140018f1d  movzx   ecx, word ptr [r15]
0x140018f21  xor     esi, esi
0x140018f23  and     cx, r10w
0x140018f27  xor     eax, eax
0x140018f29  cmp     ax, cx
0x140018f2c  jnb     short loc_140018F88
0x140018f2e  movzx   r12d, r14w
0x140018f32  movzx   eax, word ptr [rdi]
0x140018f35  movzx   ecx, si
0x140018f38  add     ecx, r12d
0x140018f3b  shr     eax, 1
0x140018f3d  cmp     ecx, eax
0x140018f3f  jnb     short loc_140018F7E
0x140018f41  mov     eax, ecx
0x140018f43  mov     rcx, [rdi+8]
0x140018f47  movzx   ecx, word ptr [rcx+rax*2]; SourceCharacter
0x140018f4b  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018f51  mov     rcx, [r15+8]
0x140018f55  movzx   ebx, ax
0x140018f58  movzx   edx, si
0x140018f5b  movzx   ecx, word ptr [rcx+rdx*2]; SourceCharacter
0x140018f5f  call    cs:__imp_RtlUpcaseUnicodeChar
0x140018f65  cmp     bx, ax
0x140018f68  mov     ebx, 1
0x140018f6d  jnz     short loc_140018F7E
0x140018f6f  movzx   eax, word ptr [r15]
0x140018f73  add     si, bx
0x140018f76  shr     ax, 1
0x140018f79  cmp     si, ax
0x140018f7c  jb      short loc_140018F32
0x140018f7e  mov     r9d, [rbp+60h+var_60]
0x140018f82  mov     r10d, 0FFFEh
0x140018f88  movzx   eax, word ptr [r15]
0x140018f8c  shr     ax, 1
0x140018f8f  cmp     si, ax
0x140018f92  jnz     short loc_140018FDA
0x140018f94  movzx   eax, r14w
0x140018f98  movzx   edx, si
0x140018f9b  add     edx, eax
0x140018f9d  movzx   eax, word ptr [rdi]
0x140018fa0  shr     eax, 1
0x140018fa2  cmp     edx, eax
0x140018fa4  jz      short loc_140018FB1
0x140018fa6  mov     rax, [rdi+8]
0x140018faa  cmp     word ptr [rax+rdx*2], 5Ch ; '\'
0x140018faf  jnz     short loc_140018FDA
0x140018fb1  mov     eax, [rsp+80h+var_80]
0x140018fb4  sub     rsp, 10h
0x140018fb8  lea     rcx, [rsp+90h+var_70]
0x140018fbd  mov     eax, [rcx]
0x140018fbf  add     si, r14w
0x140018fc3  mov     [rcx+8], r13
0x140018fc7  add     r9w, bx
0x140018fcb  mov     [rcx], r14w
0x140018fcf  mov     [rbp+60h+var_60], r9d
0x140018fd3  mov     r13, rcx
0x140018fd6  mov     [rcx+2], si
0x140018fda  movzx   eax, word ptr [rdi]
0x140018fdd  add     r14w, bx
0x140018fe1  shr     ax, 1
0x140018fe4  cmp     r14w, ax
0x140018fe8  jb      loc_140018F1D
0x140018fee  test    r13, r13
0x140018ff1  jz      loc_140019103
0x140018ff7  mov     r11, [rbp+60h+var_58]
0x140018ffb  movzx   r8d, word ptr [rdi]
0x140018fff  movzx   ecx, word ptr [r11]
0x140019003  cmp     cx, [r15]
0x140019007  jbe     short loc_14001902B
0x140019009  movzx   eax, word ptr [r15]
0x14001900d  sub     ecx, eax
0x14001900f  movzx   eax, r9w
0x140019013  imul    ecx, eax
0x140019016  movzx   eax, word ptr [rdi+2]
0x14001901a  add     ecx, r8d
0x14001901d  cmp     ecx, eax
0x14001901f  jbe     short loc_14001902B
0x140019021  mov     eax, 80000005h
0x140019026  jmp     loc_140019105
0x14001902b  movzx   r9d, word ptr [rdi+2]
0x140019030  shr     r9d, 1
0x140019033  sub     r9d, ebx
0x140019036  shr     r8d, 1
0x140019039  sub     r8d, ebx
0x14001903c  js      loc_1400190D0
0x140019042  test    r13, r13
0x140019045  jz      short loc_1400190B1
0x140019047  movzx   eax, word ptr [r13+2]
0x14001904c  cmp     r8d, eax
0x14001904f  jge     short loc_1400190B1
0x140019051  movzx   edx, word ptr [r11]
0x140019055  xor     eax, eax
0x140019057  movzx   ecx, dx
0x14001905a  and     cx, r10w
0x14001905e  cmp     ax, cx
0x140019061  jnb     short loc_1400190A6
0x140019063  xor     r10d, r10d
0x140019066  mov     rcx, [rdi+8]
0x14001906a  movzx   r8d, dx
0x14001906e  movzx   eax, r10w
0x140019072  add     r10w, bx
0x140019076  movsxd  rdx, r9d
0x140019079  sub     r9d, ebx
0x14001907c  shr     r8, 1
0x14001907f  sub     r8, rax
0x140019082  mov     rax, [r11+8]
0x140019086  movzx   eax, word ptr [rax+r8*2-2]
0x14001908c  mov     [rcx+rdx*2], ax
0x140019090  movzx   edx, word ptr [r11]
0x140019094  movzx   eax, dx
0x140019097  shr     ax, 1
0x14001909a  cmp     r10w, ax
0x14001909e  jb      short loc_140019066
0x1400190a0  mov     r10d, 0FFFEh
0x1400190a6  movzx   r8d, word ptr [r13+0]
0x1400190ab  mov     r13, [r13+8]
0x1400190af  jmp     short loc_1400190C6
0x1400190b1  mov     rdx, [rdi+8]
0x1400190b5  movsxd  rcx, r9d
0x1400190b8  sub     r9d, ebx
0x1400190bb  movsxd  rax, r8d
0x1400190be  movzx   eax, word ptr [rdx+rax*2]
0x1400190c2  mov     [rdx+rcx*2], ax
0x1400190c6  sub     r8d, 1
0x1400190ca  jns     loc_140019042
0x1400190d0  inc     r9d
0x1400190d3  xor     r8d, r8d
0x1400190d6  jmp     short loc_1400190F0
0x1400190d8  mov     rdx, [rdi+8]
0x1400190dc  movsxd  rax, r9d
0x1400190df  add     r9d, ebx
0x1400190e2  movsxd  rcx, r8d
0x1400190e5  add     r8d, ebx
0x1400190e8  movzx   eax, word ptr [rdx+rax*2]
0x1400190ec  mov     [rdx+rcx*2], ax
0x1400190f0  movzx   eax, word ptr [rdi+2]
0x1400190f4  shr     eax, 1
0x1400190f6  cmp     r9d, eax
0x1400190f9  jl      short loc_1400190D8
0x1400190fb  add     r8w, r8w
0x1400190ff  mov     [rdi], r8w
0x140019103  xor     eax, eax
0x140019105  mov     rcx, [rbp+60h+var_50]
0x140019109  xor     rcx, rbp; StackCookie
0x14001910c  call    __security_check_cookie
0x140019111  lea     rsp, [rbp+28h]
0x140019115  pop     r15
0x140019117  pop     r14
0x140019119  pop     r13
0x14001911b  pop     r12
0x14001911d  pop     rdi
0x14001911e  pop     rsi
0x14001911f  pop     rbx
0x140019120  pop     rbp
0x140019121  retn
```
