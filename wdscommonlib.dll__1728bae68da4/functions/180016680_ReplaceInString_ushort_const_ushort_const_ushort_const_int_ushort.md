# ReplaceInString(ushort const *,ushort const *,ushort const *,int,ushort * *)

- ea: `0x180016680`
- end: `0x1800169b2`
- name: `?ReplaceInString@@YAJPEBG00HPEAPEAG@Z`
- size: `818`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x18000214c`
- `0x18000d95c`
- `0x180016680`
- `0x180016b40`

## import_xrefs

- `msvcrt!wcsstr` at `0x18001672d`
- `msvcrt!wcsstr` at `0x1800167fd`
- `msvcrt!wcsstr` at `0x18001672d`
- `msvcrt!wcsstr` at `0x1800167fd`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016980`
- `msvcrt!??3@YAXPEAX@Z` at `0x180016980`

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
0x180016680  mov     rax, rsp
0x180016683  mov     [rax+10h], rbx
0x180016687  mov     [rax+20h], r9d
0x18001668b  mov     [rax+18h], r8
0x18001668f  mov     [rax+8], rcx
0x180016693  push    rbp
0x180016694  push    rsi
0x180016695  push    rdi
0x180016696  push    r12
0x180016698  push    r13
0x18001669a  push    r14
0x18001669c  push    r15
0x18001669e  sub     rsp, 20h
0x1800166a2  xor     r14d, r14d
0x1800166a5  mov     rax, r8
0x1800166a8  mov     rbp, rdx
0x1800166ab  mov     rsi, rcx
0x1800166ae  mov     edi, r14d
0x1800166b1  test    rcx, rcx
0x1800166b4  jz      loc_180016995
0x1800166ba  test    rdx, rdx
0x1800166bd  jz      loc_180016995
0x1800166c3  cmp     [rdx], r14w
0x1800166c7  jz      loc_180016995
0x1800166cd  test    rax, rax
0x1800166d0  jz      loc_180016995
0x1800166d6  cmp     [rsp+58h+arg_20], r14
0x1800166de  jz      loc_180016995
0x1800166e4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800166e8  mov     rbx, r15
0x1800166eb  inc     rbx
0x1800166ee  cmp     [rcx+rbx*2], r14w
0x1800166f3  jnz     short loc_1800166EB
0x1800166f5  mov     r13, r15
0x1800166f8  inc     r13
0x1800166fb  cmp     [rdx+r13*2], r14w
0x180016700  jnz     short loc_1800166F8
0x180016702  mov     r12, r15
0x180016705  inc     r12
0x180016708  cmp     [r8+r12*2], r14w
0x18001670d  jnz     short loc_180016705
0x18001670f  mov     rax, rcx
0x180016712  cmp     [rcx], r14w
0x180016716  jz      short loc_180016750
0x180016718  mov     esi, [rsp+58h+arg_18]
0x18001671c  mov     rdx, rbp; unsigned __int16 *
0x18001671f  mov     rcx, rax; unsigned __int16 *
0x180016722  test    esi, esi
0x180016724  jz      short loc_18001672D
0x180016726  call    ?StringIStrW@@YAPEAGPEBG0@Z; StringIStrW(ushort const *,ushort const *)
0x18001672b  jmp     short loc_180016739
0x18001672d  call    cs:__imp_wcsstr
0x180016734  nop     dword ptr [rax+rax+00h]
0x180016739  test    rax, rax
0x18001673c  jz      short loc_18001674B
0x18001673e  inc     rdi
0x180016741  lea     rax, [rax+r13*2]
0x180016745  cmp     [rax], r14w
0x180016749  jnz     short loc_18001671C
0x18001674b  mov     rsi, [rsp+58h+arg_0]
0x180016750  mov     rax, rdi
0x180016753  mov     [rsp+58h+arg_0], r14
0x180016758  mul     r13
0x18001675b  test    rdx, rdx
0x18001675e  jnz     loc_18001698E
0x180016764  cmp     rbx, rax
0x180016767  jb      loc_18001698E
0x18001676d  sub     rbx, rax
0x180016770  mov     [rsp+58h+arg_0], r14
0x180016775  mov     rax, rdi
0x180016778  mul     r12
0x18001677b  test    rdx, rdx
0x18001677e  jnz     loc_18001698E
0x180016784  add     rax, rbx
0x180016787  cmp     rax, rbx
0x18001678a  jb      loc_18001698E
0x180016790  lea     rcx, [rax+1]
0x180016794  mov     [rsp+58h+arg_0], rcx
0x180016799  cmp     rcx, rax
0x18001679c  jb      loc_18001698E
0x1800167a2  lea     eax, [rdx+2]
0x1800167a5  mul     rcx
0x1800167a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800167af  cmovo   rax, r15
0x1800167b3  mov     rcx, rax; unsigned __int64
0x1800167b6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800167bb  xor     r11d, r11d
0x1800167be  mov     r15, rax
0x1800167c1  test    rax, rax
0x1800167c4  jnz     short loc_1800167D0
0x1800167c6  mov     ebx, 8007000Eh
0x1800167cb  jmp     loc_18001699A
0x1800167d0  mov     [rax], r11w
0x1800167d4  mov     r14, r15
0x1800167d7  mov     ebx, r11d
0x1800167da  cmp     [rsi], r11w
0x1800167de  jz      loc_18001696E
0x1800167e4  mov     edi, 80070057h
0x1800167e9  mov     rdx, rbp; unsigned __int16 *
0x1800167ec  mov     rcx, rsi; unsigned __int16 *
0x1800167ef  cmp     [rsp+58h+arg_18], r11d
0x1800167f4  jz      short loc_1800167FD
0x1800167f6  call    ?StringIStrW@@YAPEAGPEBG0@Z; StringIStrW(ushort const *,ushort const *)
0x1800167fb  jmp     short loc_180016809
0x1800167fd  call    cs:__imp_wcsstr
0x180016804  nop     dword ptr [rax+rax+00h]
0x180016809  mov     r8, [rsp+58h+arg_0]
0x18001680e  mov     rcx, rax
0x180016811  mov     rax, r14
0x180016814  mov     rdx, r8
0x180016817  sub     rax, r15
0x18001681a  xor     r11d, r11d
0x18001681d  sar     rax, 1
0x180016820  sub     rdx, rax; unsigned __int64
0x180016823  test    rcx, rcx
0x180016826  jz      loc_18001695D
0x18001682c  sub     rcx, rsi
0x18001682f  lea     rax, [rdx-1]
0x180016833  sar     rcx, 1
0x180016836  mov     r9d, 7FFFFFFEh
0x18001683c  cmp     rax, r9
0x18001683f  ja      short loc_1800168A3
0x180016841  cmp     rcx, r9
0x180016844  ja      loc_18001694D
0x18001684a  mov     r9, rcx
0x18001684d  mov     r10, rsi
0x180016850  sub     r9, rdx
0x180016853  mov     r8, r14
0x180016856  sub     r10, r14
0x180016859  lea     rax, [r9+rdx]
0x18001685d  test    rax, rax
0x180016860  jz      short loc_18001687A
0x180016862  movzx   eax, word ptr [r10+r8]
0x180016867  test    ax, ax
0x18001686a  jz      short loc_18001687A
0x18001686c  mov     [r8], ax
0x180016870  add     r8, 2
0x180016874  sub     rdx, 1
0x180016878  jnz     short loc_180016859
0x18001687a  test    rdx, rdx
0x18001687d  lea     rax, [r8-2]
0x180016881  mov     r9d, 7FFFFFFEh
0x180016887  cmovnz  rax, r8
0x18001688b  mov     r8, [rsp+58h+arg_0]
0x180016890  neg     rdx
0x180016893  sbb     ebx, ebx
0x180016895  not     ebx
0x180016897  mov     [rax], r11w
0x18001689b  and     ebx, 8007007Ah
0x1800168a1  jmp     short loc_1800168AE
0x1800168a3  mov     ebx, edi
0x1800168a5  test    rdx, rdx
0x1800168a8  jnz     loc_18001694F
0x1800168ae  test    ebx, ebx
0x1800168b0  js      loc_18001697D
0x1800168b6  lea     rax, [rcx+rcx]
0x1800168ba  mov     rcx, r8
0x1800168bd  add     rsi, rax
0x1800168c0  lea     rdx, [rax+r14]
0x1800168c4  mov     rax, rdx
0x1800168c7  sub     rax, r15
0x1800168ca  sar     rax, 1
0x1800168cd  sub     rcx, rax
0x1800168d0  lea     rax, [rcx-1]
0x1800168d4  cmp     rax, r9
0x1800168d7  ja      short loc_18001692E
0x1800168d9  cmp     r12, r9
0x1800168dc  ja      short loc_180016955
0x1800168de  mov     r10, [rsp+58h+arg_10]
0x1800168e3  mov     r9, r12
0x1800168e6  sub     r9, rcx
0x1800168e9  mov     r8, rdx
0x1800168ec  sub     r10, rdx
0x1800168ef  lea     rax, [r9+rcx]
0x1800168f3  test    rax, rax
0x1800168f6  jz      short loc_180016910
0x1800168f8  movzx   eax, word ptr [r10+r8]
0x1800168fd  test    ax, ax
0x180016900  jz      short loc_180016910
0x180016902  mov     [r8], ax
0x180016906  add     r8, 2
0x18001690a  sub     rcx, 1
0x18001690e  jnz     short loc_1800168EF
0x180016910  test    rcx, rcx
0x180016913  lea     rax, [r8-2]
0x180016917  cmovnz  rax, r8
0x18001691b  neg     rcx
0x18001691e  sbb     ebx, ebx
0x180016920  not     ebx
0x180016922  and     ebx, 8007007Ah
0x180016928  mov     [rax], r11w
0x18001692c  jmp     short loc_180016935
0x18001692e  mov     ebx, edi
0x180016930  test    rcx, rcx
0x180016933  jnz     short loc_180016957
0x180016935  test    ebx, ebx
0x180016937  js      short loc_18001697D
0x180016939  lea     rsi, [rsi+r13*2]
0x18001693d  lea     r14, [rdx+r12*2]
0x180016941  cmp     [rsi], r11w
0x180016945  jnz     loc_1800167E9
0x18001694b  jmp     short loc_18001696E
0x18001694d  mov     ebx, edi
0x18001694f  mov     [r14], r11w
0x180016953  jmp     short loc_18001697D
0x180016955  mov     ebx, edi
0x180016957  mov     [rdx], r11w
0x18001695b  jmp     short loc_18001697D
0x18001695d  mov     r8, rsi; unsigned __int16 *
0x180016960  mov     rcx, r14; unsigned __int16 *
0x180016963  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016968  mov     ebx, eax
0x18001696a  test    eax, eax
0x18001696c  js      short loc_18001697D
0x18001696e  mov     rax, [rsp+58h+arg_20]
0x180016976  mov     [rax], r15
0x180016979  test    ebx, ebx
0x18001697b  jns     short loc_18001699A
0x18001697d  mov     rcx, r15
0x180016980  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180016987  nop     dword ptr [rax+rax+00h]
0x18001698c  jmp     short loc_18001699A
0x18001698e  mov     ebx, 80070216h
0x180016993  jmp     short loc_18001699A
0x180016995  mov     ebx, 80070057h
0x18001699a  mov     eax, ebx
0x18001699c  mov     rbx, [rsp+58h+arg_8]
0x1800169a1  add     rsp, 20h
0x1800169a5  pop     r15
0x1800169a7  pop     r14
0x1800169a9  pop     r13
0x1800169ab  pop     r12
0x1800169ad  pop     rdi
0x1800169ae  pop     rsi
0x1800169af  pop     rbp
0x1800169b0  retn
```
