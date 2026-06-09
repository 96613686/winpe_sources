# fp_format_a

- ea: `0x100431a44`
- end: `0x100431ddb`
- name: `fp_format_a`
- size: `919`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, char *Str@<rdx>, __int64, size_t Size, char, int, int, __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x10043257c`

## callees

- `0x1004277a0`
- `0x10042d4f0`
- `0x10042e504`
- `0x100431a44`
- `0x100431de4`
- `0x100432460`
- `0x1004393b0`

## pseudocode

```c
__int64 __fastcall fp_format_a(
        __int64 *a1,
        char *Str,
        unsigned __int64 a3,
        int a4,
        __int64 a5,
        size_t Size,
        char a7,
        int a8,
        unsigned int a9,
        __crt_cached_ptd_host *a10)
{
  int v10; // edi
  char *v11; // rbx
  __int64 result; // rax
  char *v14; // rax
  char *v15; // r12
  __int64 v16; // r15
  _BYTE *v17; // rsi
  char v18; // al
  unsigned __int64 v19; // r10
  unsigned __int16 v20; // ax
  char *i; // rcx
  char v22; // dl
  _BYTE *v23; // r9
  __int64 v24; // rcx
  __int64 v25; // rdx
  char v26; // al
  _BYTE *v27; // r8

  *Str = 0;
  v10 = 0;
  if ( (Size & 0x80000000) == 0LL )
    v10 = Size;
  v11 = Str;
  if ( a3 <= v10 + 11 )
  {
    *((_BYTE *)a10 + 48) = 1;
    *((_DWORD *)a10 + 11) = 34;
    invalid_parameter_internal(0, 0, 0, 0, 0, a10);
    return 34;
  }
  if ( (((unsigned __int64)*a1 >> 52) & 0x7FF) != 0x7FF )
  {
    if ( *a1 < 0 )
    {
      *Str = 45;
      v11 = Str + 1;
    }
    v15 = v11 + 1;
    v16 = 1023;
    if ( (*a1 & 0x7FF0000000000000LL) != 0 )
    {
      *v11 = 49;
    }
    else
    {
      *v11 = 48;
      v16 = (*a1 & 0xFFFFFFFFFFFFFLL) != 0 ? 0x3FE : 0;
    }
    v17 = v11 + 2;
    if ( v10 )
    {
      if ( !*((_BYTE *)a10 + 40) )
        __crt_cached_ptd_host::update_locale_slow(a10);
      v18 = ***(_BYTE ***)(*((_QWORD *)a10 + 3) + 248LL);
    }
    else
    {
      v18 = 0;
    }
    *v15 = v18;
    if ( (*a1 & 0xFFFFFFFFFFFFFLL) != 0 )
    {
      LODWORD(Str) = 48;
      v19 = 0xF000000000000LL;
      while ( v10 > 0 )
      {
        v20 = ((v19 & *a1 & 0xFFFFFFFFFFFFFLL) >> (char)Str) + 48;
        if ( v20 > 0x39u )
          LOBYTE(v20) = 32 * (a7 ^ 1) + 7 + v20;
        *v17 = v20;
        --v10;
        ++v17;
        v19 >>= 4;
        LOWORD(Str) = (_WORD)Str - 4;
        if ( (__int16)Str < 0 )
          goto LABEL_36;
      }
      if ( !(unsigned __int8)should_round_up(a1, v19, (unsigned __int16)Str, a9) )
      {
LABEL_38:
        if ( !*v15 )
          v17 = v11 + 1;
        *v17 = 32 * (a7 ^ 1) + 80;
        v23 = v17 + 2;
        v24 = (((unsigned __int64)*a1 >> 52) & 0x7FF) - v16;
        v25 = v24;
        if ( v24 < 0 )
          v24 = v16 - (((unsigned __int64)*a1 >> 52) & 0x7FF);
        v26 = 43;
        v27 = v17 + 2;
        if ( v25 < 0 )
          v26 = 45;
        v17[1] = v26;
        *v23 = 48;
        if ( v24 < 1000 )
        {
          if ( v24 < 100 )
          {
LABEL_48:
            if ( v24 < 10 )
            {
LABEL_50:
              *v27 = v24 + 48;
              v27[1] = 0;
              return 0;
            }
LABEL_49:
            *v27++ = v24 / 10 + 48;
            v24 %= 10;
            goto LABEL_50;
          }
        }
        else
        {
          v27 = v17 + 3;
          *v23 = v24 / 1000 + 48;
          v24 %= 1000;
        }
        *v27++ = v24 / 100 + 48;
        v24 %= 100;
        if ( v27 != v23 )
          goto LABEL_49;
        goto LABEL_48;
      }
      for ( i = v17 - 1; ; --i )
      {
        v22 = *i;
        if ( ((*i - 70) & 0xDF) != 0 )
          break;
        *i = 48;
      }
      if ( i == v15 )
      {
        ++*(i - 1);
      }
      else
      {
        if ( v22 == 57 )
          v22 = 32 * (a7 ^ 1) + 64;
        *i = v22 + 1;
      }
    }
LABEL_36:
    if ( v10 > 0 )
    {
      LOBYTE(Str) = 48;
      memset(v17, (int)Str, (unsigned int)v10);
      v17 += (unsigned int)v10;
    }
    goto LABEL_38;
  }
  result = fp_format_e((int)a1, (int)Str, a3, a4, a5, v10, 0, a8, a9, a10);
  if ( (_DWORD)result )
  {
    *v11 = 0;
    return result;
  }
  v14 = strrchr(v11, 101);
  if ( v14 )
  {
    *v14 = 32 * (a7 ^ 1) + 80;
    v14[3] = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x100431a44  mov     [rsp+arg_0], rbx
0x100431a49  mov     [rsp+arg_10], rbp
0x100431a4e  mov     [rsp+arg_18], rsi
0x100431a53  push    rdi
0x100431a54  push    r12
0x100431a56  push    r13
0x100431a58  push    r14
0x100431a5a  push    r15
0x100431a5c  sub     rsp, 50h
0x100431a60  mov     eax, dword ptr [rsp+78h+Size]
0x100431a67  xor     r11d, r11d
0x100431a6a  test    eax, eax
0x100431a6c  mov     [rdx], r11b
0x100431a6f  mov     edi, r11d
0x100431a72  mov     r10, r9
0x100431a75  cmovns  edi, eax
0x100431a78  mov     rbx, rdx
0x100431a7b  mov     r14, rcx
0x100431a7e  lea     eax, [rdi+0Bh]
0x100431a81  movsxd  r9, eax
0x100431a84  cmp     r8, r9
0x100431a87  ja      short loc_100431ABC
0x100431a89  mov     rcx, [rsp+78h+arg_48]
0x100431a91  lea     ebx, [r11+22h]
0x100431a95  mov     [rsp+78h+var_50], rcx; __crt_cached_ptd_host *
0x100431a9a  xor     r9d, r9d; LineNo
0x100431a9d  xor     r8d, r8d; FileName
0x100431aa0  mov     [rsp+78h+var_58], r11; uintptr_t
0x100431aa5  xor     edx, edx; FunctionName
0x100431aa7  mov     byte ptr [rcx+30h], 1
0x100431aab  mov     [rcx+2Ch], ebx
0x100431aae  xor     ecx, ecx; Expression
0x100431ab0  call    _invalid_parameter_internal
0x100431ab5  mov     eax, ebx
0x100431ab7  jmp     loc_100431DBD
0x100431abc  mov     rax, [rcx]
0x100431abf  mov     ecx, 7FFh
0x100431ac4  shr     rax, 34h
0x100431ac8  and     rax, rcx
0x100431acb  cmp     rax, rcx
0x100431ace  jnz     loc_100431B55
0x100431ad4  mov     rax, [rsp+78h+arg_48]
0x100431adc  mov     r9, r10; int
0x100431adf  mov     [rsp+78h+var_30], rax; __crt_cached_ptd_host *
0x100431ae4  mov     rcx, r14; int
0x100431ae7  mov     eax, [rsp+78h+arg_40]
0x100431aee  mov     [rsp+78h+var_38], eax; int
0x100431af2  mov     eax, [rsp+78h+arg_38]
0x100431af9  mov     [rsp+78h+var_40], eax; int
0x100431afd  mov     rax, [rsp+78h+arg_20]
0x100431b05  mov     [rsp+78h+var_48], r11b; char
0x100431b0a  mov     dword ptr [rsp+78h+var_50], edi; int
0x100431b0e  mov     [rsp+78h+var_58], rax; __int64
0x100431b13  call    fp_format_e
0x100431b18  test    eax, eax
0x100431b1a  jz      short loc_100431B24
0x100431b1c  mov     byte ptr [rbx], 0
0x100431b1f  jmp     loc_100431DBD
0x100431b24  mov     edx, 65h ; 'e'; Ch
0x100431b29  mov     rcx, rbx; Str
0x100431b2c  call    strrchr
0x100431b31  test    rax, rax
0x100431b34  jz      loc_100431DBB
0x100431b3a  mov     cl, [rsp+78h+arg_30]
0x100431b41  xor     cl, 1
0x100431b44  shl     cl, 5
0x100431b47  add     cl, 50h ; 'P'
0x100431b4a  mov     [rax], cl
0x100431b4c  mov     byte ptr [rax+3], 0
0x100431b50  jmp     loc_100431DBB
0x100431b55  mov     eax, 2Dh ; '-'
0x100431b5a  cmp     [r14], r11
0x100431b5d  jge     short loc_100431B64
0x100431b5f  mov     [rdx], al
0x100431b61  inc     rbx
0x100431b64  mov     al, [rsp+78h+arg_30]
0x100431b6b  lea     r12, [rbx+1]
0x100431b6f  xor     al, 1
0x100431b71  mov     r15d, 3FFh
0x100431b77  movzx   r13d, al
0x100431b7b  mov     r8d, 30h ; '0'
0x100431b81  mov     ebp, r13d
0x100431b84  mov     rax, 7FF0000000000000h
0x100431b8e  shl     ebp, 5
0x100431b91  mov     r9, 0FFFFFFFFFFFFFh
0x100431b9b  add     ebp, 7
0x100431b9e  test    [r14], rax
0x100431ba1  jnz     short loc_100431BBB
0x100431ba3  mov     [rbx], r8b
0x100431ba6  mov     rax, [r14]
0x100431ba9  and     rax, r9
0x100431bac  neg     rax
0x100431baf  sbb     r15, r15
0x100431bb2  and     r15d, 3FEh
0x100431bb9  jmp     short loc_100431BBE
0x100431bbb  mov     byte ptr [rbx], 31h ; '1'
0x100431bbe  lea     rsi, [r12+1]
0x100431bc3  test    edi, edi
0x100431bc5  jnz     short loc_100431BCC
0x100431bc7  mov     al, r11b
0x100431bca  jmp     short loc_100431C03
0x100431bcc  mov     rbx, [rsp+78h+arg_48]
0x100431bd4  cmp     [rbx+28h], r11b
0x100431bd8  jnz     short loc_100431BF3
0x100431bda  mov     rcx, rbx; this
0x100431bdd  call    ?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ; __crt_cached_ptd_host::update_locale_slow(void)
0x100431be2  xor     r11d, r11d
0x100431be5  mov     r9, 0FFFFFFFFFFFFFh
0x100431bef  lea     r8d, [r11+30h]
0x100431bf3  mov     rax, [rbx+18h]
0x100431bf7  mov     rcx, [rax+0F8h]
0x100431bfe  mov     rax, [rcx]
0x100431c01  mov     al, [rax]
0x100431c03  mov     [r12], al
0x100431c07  test    [r14], r9
0x100431c0a  jbe     loc_100431C9A
0x100431c10  movzx   edx, r8w
0x100431c14  mov     r10, 0F000000000000h
0x100431c1e  movzx   ecx, dx
0x100431c21  test    edi, edi
0x100431c23  jle     short loc_100431C51
0x100431c25  mov     rax, [r14]
0x100431c28  and     rax, r10
0x100431c2b  and     rax, r9
0x100431c2e  shr     rax, cl
0x100431c31  add     ax, r8w
0x100431c35  cmp     ax, 39h ; '9'
0x100431c39  jbe     short loc_100431C3E
0x100431c3b  add     ax, bp
0x100431c3e  mov     [rsi], al
0x100431c40  dec     edi
0x100431c42  inc     rsi
0x100431c45  shr     r10, 4
0x100431c49  add     dx, 0FFFCh
0x100431c4d  jns     short loc_100431C1E
0x100431c4f  jmp     short loc_100431C9A
0x100431c51  mov     r9d, [rsp+78h+arg_40]
0x100431c59  movzx   r8d, cx
0x100431c5d  mov     rcx, r14
0x100431c60  mov     rdx, r10
0x100431c63  call    should_round_up
0x100431c68  xor     r11d, r11d
0x100431c6b  test    al, al
0x100431c6d  jz      short loc_100431CBB
0x100431c6f  lea     rcx, [rsi-1]
0x100431c73  mov     dl, [rcx]
0x100431c75  lea     eax, [rdx-46h]
0x100431c78  test    al, 0DFh
0x100431c7a  jnz     short loc_100431C84
0x100431c7c  mov     byte ptr [rcx], 30h ; '0'
0x100431c7f  dec     rcx
0x100431c82  jmp     short loc_100431C73
0x100431c84  cmp     rcx, r12
0x100431c87  jz      short loc_100431C97
0x100431c89  cmp     dl, 39h ; '9'
0x100431c8c  jnz     short loc_100431C91
0x100431c8e  add     dl, bpl
0x100431c91  inc     dl
0x100431c93  mov     [rcx], dl
0x100431c95  jmp     short loc_100431C9A
0x100431c97  inc     byte ptr [rcx-1]
0x100431c9a  test    edi, edi
0x100431c9c  jle     short loc_100431CBB
0x100431c9e  mov     r8d, edi; Size
0x100431ca1  mov     rcx, rsi; void *
0x100431ca4  mov     ebx, edi
0x100431ca6  mov     edi, 30h ; '0'
0x100431cab  mov     dl, dil; Val
0x100431cae  call    memset
0x100431cb3  add     rsi, rbx
0x100431cb6  xor     r11d, r11d
0x100431cb9  jmp     short loc_100431CC0
0x100431cbb  mov     edi, 30h ; '0'
0x100431cc0  cmp     [r12], r11b
0x100431cc4  cmovz   rsi, r12
0x100431cc8  shl     r13b, 5
0x100431ccc  add     r13b, 50h ; 'P'
0x100431cd0  mov     [rsi], r13b
0x100431cd3  lea     r9, [rsi+2]
0x100431cd7  mov     rax, [r14]
0x100431cda  shr     rax, 34h
0x100431cde  and     eax, 7FFh
0x100431ce3  mov     ecx, eax
0x100431ce5  sub     rcx, r15
0x100431ce8  mov     rdx, rcx
0x100431ceb  jns     short loc_100431CF3
0x100431ced  mov     rcx, r15
0x100431cf0  sub     rcx, rax
0x100431cf3  test    rdx, rdx
0x100431cf6  mov     eax, 2Bh ; '+'
0x100431cfb  mov     r8, r9
0x100431cfe  lea     edx, [rax+2]
0x100431d01  cmovs   eax, edx
0x100431d04  mov     [rsi+1], al
0x100431d07  mov     [r9], dil
0x100431d0a  cmp     rcx, 3E8h
0x100431d11  jl      short loc_100431D47
0x100431d13  mov     rax, 20C49BA5E353F7CFh
0x100431d1d  lea     r8, [r9+1]
0x100431d21  imul    rcx
0x100431d24  sar     rdx, 7
0x100431d28  mov     rax, rdx
0x100431d2b  shr     rax, 3Fh
0x100431d2f  add     rdx, rax
0x100431d32  lea     eax, [rdi+rdx]
0x100431d35  mov     [r9], al
0x100431d38  imul    rax, rdx, 0FFFFFFFFFFFFFC18h
0x100431d3f  add     rcx, rax
0x100431d42  cmp     r8, r9
0x100431d45  jnz     short loc_100431D4D
0x100431d47  cmp     rcx, 64h ; 'd'
0x100431d4b  jl      short loc_100431D80
0x100431d4d  mov     rax, 0A3D70A3D70A3D70Bh
0x100431d57  imul    rcx
0x100431d5a  add     rdx, rcx
0x100431d5d  sar     rdx, 6
0x100431d61  mov     rax, rdx
0x100431d64  shr     rax, 3Fh
0x100431d68  add     rdx, rax
0x100431d6b  lea     eax, [rdi+rdx]
0x100431d6e  mov     [r8], al
0x100431d71  inc     r8
0x100431d74  imul    rax, rdx, -64h
0x100431d78  add     rcx, rax
0x100431d7b  cmp     r8, r9
0x100431d7e  jnz     short loc_100431D86
0x100431d80  cmp     rcx, 0Ah
0x100431d84  jl      short loc_100431DB1
0x100431d86  mov     rax, 6666666666666667h
0x100431d90  imul    rcx
0x100431d93  sar     rdx, 2
0x100431d97  mov     rax, rdx
0x100431d9a  shr     rax, 3Fh
0x100431d9e  add     rdx, rax
0x100431da1  lea     eax, [rdi+rdx]
0x100431da4  mov     [r8], al
0x100431da7  inc     r8
0x100431daa  imul    rax, rdx, -0Ah
0x100431dae  add     rcx, rax
0x100431db1  add     cl, dil
0x100431db4  mov     [r8], cl
0x100431db7  mov     [r8+1], r11b
0x100431dbb  xor     eax, eax
0x100431dbd  lea     r11, [rsp+78h+var_28]
0x100431dc2  mov     rbx, [r11+30h]
0x100431dc6  mov     rbp, [r11+40h]
0x100431dca  mov     rsi, [r11+48h]
0x100431dce  mov     rsp, r11
0x100431dd1  pop     r15
0x100431dd3  pop     r14
0x100431dd5  pop     r13
0x100431dd7  pop     r12
0x100431dd9  pop     rdi
0x100431dda  retn
```
