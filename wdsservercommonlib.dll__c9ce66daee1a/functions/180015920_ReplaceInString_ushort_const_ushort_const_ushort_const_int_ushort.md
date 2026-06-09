# ReplaceInString(ushort const *,ushort const *,ushort const *,int,ushort * *)

- ea: `0x180015920`
- end: `0x180015c4b`
- name: `?ReplaceInString@@YAJPEBG00HPEAPEAG@Z`
- size: `811`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000179c`
- `0x18000ce1c`
- `0x180015920`
- `0x180015de0`
- `0x18002e468`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800159cd`
- `msvcrt!wcsstr` at `0x180015a9d`
- `msvcrt!wcsstr` at `0x1800159cd`
- `msvcrt!wcsstr` at `0x180015a9d`

## pseudocode

```c
__int64 __fastcall ReplaceInString(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char *a3,
        int a4,
        unsigned __int16 **a5)
{
  const unsigned __int16 *v6; // rsi
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // rbx
  unsigned __int64 v9; // r13
  unsigned __int64 v10; // r12
  const unsigned __int16 *v11; // rax
  wchar_t *v13; // rax
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rbx
  unsigned __int128 v16; // rax
  unsigned __int64 v17; // rax
  unsigned __int64 v18; // rcx
  _WORD *v19; // rax
  _BYTE *v20; // r15
  signed int v21; // ebx
  unsigned __int16 *v22; // r14
  unsigned __int16 *v23; // rax
  unsigned __int64 v24; // r8
  unsigned __int64 v25; // rdx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // r9
  unsigned __int16 *v28; // r8
  unsigned __int16 v29; // ax
  unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // rsi
  char *v32; // rdx
  unsigned __int64 v33; // rcx
  unsigned __int64 v34; // r9
  _WORD *v35; // r8
  __int16 v36; // ax
  _WORD *v37; // rax
  unsigned __int64 v40; // [rsp+60h] [rbp+8h]

  v6 = a1;
  v7 = 0;
  if ( a1 && a2 && *a2 && a3 && a5 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a1[v8] );
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = -1;
    do
      ++v10;
    while ( *(_WORD *)&a3[2 * v10] );
    v11 = a1;
    if ( *a1 )
    {
      do
      {
        if ( a4 )
          v13 = StringIStrW(v11, a2);
        else
          v13 = wcsstr(v11, a2);
        if ( !v13 )
          break;
        ++v7;
        v11 = &v13[v9];
      }
      while ( *v11 );
      v6 = a1;
    }
    v14 = v9 * v7;
    if ( is_mul_ok(v9, v7)
      && v8 >= v14
      && (v15 = v8 - v14, v16 = v10 * (unsigned __int128)v7, is_mul_ok(v10, v7))
      && (v17 = v15 + v16, v17 >= v15)
      && (v18 = v17 + 1, v40 = v17 + 1, v17 + 1 >= v17) )
    {
      *(_QWORD *)&v16 = v18 * (unsigned int)(DWORD2(v16) + 2);
      if ( !is_mul_ok(v18, (unsigned int)(DWORD2(v16) + 2)) )
        *(_QWORD *)&v16 = -1;
      v19 = operator new[](v16, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( v19 )
      {
        *v19 = 0;
        v22 = v19;
        v21 = 0;
        if ( *v6 )
        {
          while ( 1 )
          {
            v23 = a4 ? StringIStrW(v6, a2) : wcsstr(v6, a2);
            v24 = v40;
            v25 = v40 - (((char *)v22 - v20) >> 1);
            if ( !v23 )
              break;
            v26 = v23 - v6;
            if ( v25 - 1 > 0x7FFFFFFE )
            {
              v21 = -2147024809;
              if ( v25 )
                goto LABEL_58;
            }
            else
            {
              if ( v26 > 0x7FFFFFFE )
              {
                v21 = -2147024809;
LABEL_58:
                *v22 = 0;
                goto LABEL_63;
              }
              v27 = v26 - v25;
              v28 = v22;
              do
              {
                if ( !(v27 + v25) )
                  break;
                v29 = *(unsigned __int16 *)((char *)v28 + (char *)v6 - (char *)v22);
                if ( !v29 )
                  break;
                *v28++ = v29;
                --v25;
              }
              while ( v25 );
              v30 = v28 - 1;
              if ( v25 )
                v30 = v28;
              v24 = v40;
              *v30 = 0;
              v21 = v25 == 0 ? 0x8007007A : 0;
            }
            if ( v21 < 0 )
              goto LABEL_63;
            v31 = &v6[v26];
            v32 = (char *)&v22[v26];
            v33 = v24 - ((v32 - v20) >> 1);
            if ( v33 - 1 > 0x7FFFFFFE )
            {
              v21 = -2147024809;
              if ( v33 )
                goto LABEL_60;
            }
            else
            {
              if ( v10 > 0x7FFFFFFE )
              {
                v21 = -2147024809;
LABEL_60:
                *(_WORD *)v32 = 0;
                goto LABEL_63;
              }
              v34 = v10 - v33;
              v35 = v32;
              do
              {
                if ( !(v34 + v33) )
                  break;
                v36 = *(_WORD *)((char *)v35 + a3 - v32);
                if ( !v36 )
                  break;
                *v35++ = v36;
                --v33;
              }
              while ( v33 );
              v37 = v35 - 1;
              if ( v33 )
                v37 = v35;
              v21 = v33 == 0 ? 0x8007007A : 0;
              *v37 = 0;
            }
            if ( v21 < 0 )
              goto LABEL_63;
            v6 = &v31[v9];
            v22 = (unsigned __int16 *)&v32[2 * v10];
            if ( !*v6 )
              goto LABEL_62;
          }
          v21 = StringCchCopyW(v22, v25, v6);
          if ( v21 >= 0 )
            goto LABEL_62;
LABEL_63:
          operator delete(v20);
        }
        else
        {
LABEL_62:
          *a5 = (unsigned __int16 *)v20;
        }
      }
      else
      {
        return (unsigned int)-2147024882;
      }
    }
    else
    {
      return (unsigned int)-2147024362;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180015920  mov     rax, rsp
0x180015923  mov     [rax+10h], rbx
0x180015927  mov     [rax+20h], r9d
0x18001592b  mov     [rax+18h], r8
0x18001592f  mov     [rax+8], rcx
0x180015933  push    rbp
0x180015934  push    rsi
0x180015935  push    rdi
0x180015936  push    r12
0x180015938  push    r13
0x18001593a  push    r14
0x18001593c  push    r15
0x18001593e  sub     rsp, 20h
0x180015942  xor     r14d, r14d
0x180015945  mov     rax, r8
0x180015948  mov     rbp, rdx
0x18001594b  mov     rsi, rcx
0x18001594e  mov     edi, r14d
0x180015951  test    rcx, rcx
0x180015954  jz      loc_180015C2E
0x18001595a  test    rdx, rdx
0x18001595d  jz      loc_180015C2E
0x180015963  cmp     [rdx], r14w
0x180015967  jz      loc_180015C2E
0x18001596d  test    rax, rax
0x180015970  jz      loc_180015C2E
0x180015976  cmp     [rsp+58h+arg_20], r14
0x18001597e  jz      loc_180015C2E
0x180015984  or      r15, 0FFFFFFFFFFFFFFFFh
0x180015988  mov     rbx, r15
0x18001598b  inc     rbx
0x18001598e  cmp     [rcx+rbx*2], r14w
0x180015993  jnz     short loc_18001598B
0x180015995  mov     r13, r15
0x180015998  inc     r13
0x18001599b  cmp     [rdx+r13*2], r14w
0x1800159a0  jnz     short loc_180015998
0x1800159a2  mov     r12, r15
0x1800159a5  inc     r12
0x1800159a8  cmp     [r8+r12*2], r14w
0x1800159ad  jnz     short loc_1800159A5
0x1800159af  mov     rax, rcx
0x1800159b2  cmp     [rcx], r14w
0x1800159b6  jz      short loc_1800159F0
0x1800159b8  mov     esi, [rsp+58h+arg_18]
0x1800159bc  mov     rdx, rbp; unsigned __int16 *
0x1800159bf  mov     rcx, rax; unsigned __int16 *
0x1800159c2  test    esi, esi
0x1800159c4  jz      short loc_1800159CD
0x1800159c6  call    ?StringIStrW@@YAPEAGPEBG0@Z; StringIStrW(ushort const *,ushort const *)
0x1800159cb  jmp     short loc_1800159D9
0x1800159cd  call    cs:__imp_wcsstr
0x1800159d4  nop     dword ptr [rax+rax+00h]
0x1800159d9  test    rax, rax
0x1800159dc  jz      short loc_1800159EB
0x1800159de  inc     rdi
0x1800159e1  lea     rax, [rax+r13*2]
0x1800159e5  cmp     [rax], r14w
0x1800159e9  jnz     short loc_1800159BC
0x1800159eb  mov     rsi, [rsp+58h+arg_0]
0x1800159f0  mov     rax, rdi
0x1800159f3  mov     [rsp+58h+arg_0], r14
0x1800159f8  mul     r13
0x1800159fb  test    rdx, rdx
0x1800159fe  jnz     loc_180015C27
0x180015a04  cmp     rbx, rax
0x180015a07  jb      loc_180015C27
0x180015a0d  sub     rbx, rax
0x180015a10  mov     [rsp+58h+arg_0], r14
0x180015a15  mov     rax, rdi
0x180015a18  mul     r12
0x180015a1b  test    rdx, rdx
0x180015a1e  jnz     loc_180015C27
0x180015a24  add     rax, rbx
0x180015a27  cmp     rax, rbx
0x180015a2a  jb      loc_180015C27
0x180015a30  lea     rcx, [rax+1]
0x180015a34  mov     [rsp+58h+arg_0], rcx
0x180015a39  cmp     rcx, rax
0x180015a3c  jb      loc_180015C27
0x180015a42  lea     eax, [rdx+2]
0x180015a45  mul     rcx
0x180015a48  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015a4f  cmovo   rax, r15
0x180015a53  mov     rcx, rax; unsigned __int64
0x180015a56  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180015a5b  xor     r11d, r11d
0x180015a5e  mov     r15, rax
0x180015a61  test    rax, rax
0x180015a64  jnz     short loc_180015A70
0x180015a66  mov     ebx, 8007000Eh
0x180015a6b  jmp     loc_180015C33
0x180015a70  mov     [rax], r11w
0x180015a74  mov     r14, r15
0x180015a77  mov     ebx, r11d
0x180015a7a  cmp     [rsi], r11w
0x180015a7e  jz      loc_180015C0E
0x180015a84  mov     edi, 80070057h
0x180015a89  mov     rdx, rbp; unsigned __int16 *
0x180015a8c  mov     rcx, rsi; unsigned __int16 *
0x180015a8f  cmp     [rsp+58h+arg_18], r11d
0x180015a94  jz      short loc_180015A9D
0x180015a96  call    ?StringIStrW@@YAPEAGPEBG0@Z; StringIStrW(ushort const *,ushort const *)
0x180015a9b  jmp     short loc_180015AA9
0x180015a9d  call    cs:__imp_wcsstr
0x180015aa4  nop     dword ptr [rax+rax+00h]
0x180015aa9  mov     r8, [rsp+58h+arg_0]
0x180015aae  mov     rcx, rax
0x180015ab1  mov     rax, r14
0x180015ab4  mov     rdx, r8
0x180015ab7  sub     rax, r15
0x180015aba  xor     r11d, r11d
0x180015abd  sar     rax, 1
0x180015ac0  sub     rdx, rax; unsigned __int64
0x180015ac3  test    rcx, rcx
0x180015ac6  jz      loc_180015BFD
0x180015acc  sub     rcx, rsi
0x180015acf  lea     rax, [rdx-1]
0x180015ad3  sar     rcx, 1
0x180015ad6  mov     r9d, 7FFFFFFEh
0x180015adc  cmp     rax, r9
0x180015adf  ja      short loc_180015B43
0x180015ae1  cmp     rcx, r9
0x180015ae4  ja      loc_180015BED
0x180015aea  mov     r9, rcx
0x180015aed  mov     r10, rsi
0x180015af0  sub     r9, rdx
0x180015af3  mov     r8, r14
0x180015af6  sub     r10, r14
0x180015af9  lea     rax, [r9+rdx]
0x180015afd  test    rax, rax
0x180015b00  jz      short loc_180015B1A
0x180015b02  movzx   eax, word ptr [r10+r8]
0x180015b07  test    ax, ax
0x180015b0a  jz      short loc_180015B1A
0x180015b0c  mov     [r8], ax
0x180015b10  add     r8, 2
0x180015b14  sub     rdx, 1
0x180015b18  jnz     short loc_180015AF9
0x180015b1a  test    rdx, rdx
0x180015b1d  lea     rax, [r8-2]
0x180015b21  mov     r9d, 7FFFFFFEh
0x180015b27  cmovnz  rax, r8
0x180015b2b  mov     r8, [rsp+58h+arg_0]
0x180015b30  neg     rdx
0x180015b33  sbb     ebx, ebx
0x180015b35  not     ebx
0x180015b37  mov     [rax], r11w
0x180015b3b  and     ebx, 8007007Ah
0x180015b41  jmp     short loc_180015B4E
0x180015b43  mov     ebx, edi
0x180015b45  test    rdx, rdx
0x180015b48  jnz     loc_180015BEF
0x180015b4e  test    ebx, ebx
0x180015b50  js      loc_180015C1D
0x180015b56  lea     rax, [rcx+rcx]
0x180015b5a  mov     rcx, r8
0x180015b5d  add     rsi, rax
0x180015b60  lea     rdx, [rax+r14]
0x180015b64  mov     rax, rdx
0x180015b67  sub     rax, r15
0x180015b6a  sar     rax, 1
0x180015b6d  sub     rcx, rax
0x180015b70  lea     rax, [rcx-1]
0x180015b74  cmp     rax, r9
0x180015b77  ja      short loc_180015BCE
0x180015b79  cmp     r12, r9
0x180015b7c  ja      short loc_180015BF5
0x180015b7e  mov     r10, [rsp+58h+arg_10]
0x180015b83  mov     r9, r12
0x180015b86  sub     r9, rcx
0x180015b89  mov     r8, rdx
0x180015b8c  sub     r10, rdx
0x180015b8f  lea     rax, [r9+rcx]
0x180015b93  test    rax, rax
0x180015b96  jz      short loc_180015BB0
0x180015b98  movzx   eax, word ptr [r10+r8]
0x180015b9d  test    ax, ax
0x180015ba0  jz      short loc_180015BB0
0x180015ba2  mov     [r8], ax
0x180015ba6  add     r8, 2
0x180015baa  sub     rcx, 1
0x180015bae  jnz     short loc_180015B8F
0x180015bb0  test    rcx, rcx
0x180015bb3  lea     rax, [r8-2]
0x180015bb7  cmovnz  rax, r8
0x180015bbb  neg     rcx
0x180015bbe  sbb     ebx, ebx
0x180015bc0  not     ebx
0x180015bc2  and     ebx, 8007007Ah
0x180015bc8  mov     [rax], r11w
0x180015bcc  jmp     short loc_180015BD5
0x180015bce  mov     ebx, edi
0x180015bd0  test    rcx, rcx
0x180015bd3  jnz     short loc_180015BF7
0x180015bd5  test    ebx, ebx
0x180015bd7  js      short loc_180015C1D
0x180015bd9  lea     rsi, [rsi+r13*2]
0x180015bdd  lea     r14, [rdx+r12*2]
0x180015be1  cmp     [rsi], r11w
0x180015be5  jnz     loc_180015A89
0x180015beb  jmp     short loc_180015C0E
0x180015bed  mov     ebx, edi
0x180015bef  mov     [r14], r11w
0x180015bf3  jmp     short loc_180015C1D
0x180015bf5  mov     ebx, edi
0x180015bf7  mov     [rdx], r11w
0x180015bfb  jmp     short loc_180015C1D
0x180015bfd  mov     r8, rsi; unsigned __int16 *
0x180015c00  mov     rcx, r14; unsigned __int16 *
0x180015c03  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015c08  mov     ebx, eax
0x180015c0a  test    eax, eax
0x180015c0c  js      short loc_180015C1D
0x180015c0e  mov     rax, [rsp+58h+arg_20]
0x180015c16  mov     [rax], r15
0x180015c19  test    ebx, ebx
0x180015c1b  jns     short loc_180015C33
0x180015c1d  mov     rcx, r15; lpMem
0x180015c20  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180015c25  jmp     short loc_180015C33
0x180015c27  mov     ebx, 80070216h
0x180015c2c  jmp     short loc_180015C33
0x180015c2e  mov     ebx, 80070057h
0x180015c33  mov     eax, ebx
0x180015c35  mov     rbx, [rsp+58h+arg_8]
0x180015c3a  add     rsp, 20h
0x180015c3e  pop     r15
0x180015c40  pop     r14
0x180015c42  pop     r13
0x180015c44  pop     r12
0x180015c46  pop     rdi
0x180015c47  pop     rsi
0x180015c48  pop     rbp
0x180015c49  retn
```
