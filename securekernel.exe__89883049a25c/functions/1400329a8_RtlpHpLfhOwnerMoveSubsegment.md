# RtlpHpLfhOwnerMoveSubsegment

- ea: `0x1400329a8`
- end: `0x140032ba1`
- name: `RtlpHpLfhOwnerMoveSubsegment`
- size: `505`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ffec`
- `0x14003286c`
- `0x140032cc4`
- `0x140032de4`
- `0x140035a44`
- `0x1400ceb74`

## callees

- `0x1400329a8`

## pseudocode

```c
__int64 __fastcall RtlpHpLfhOwnerMoveSubsegment(__int64 a1, char *a2, __int64 *a3, int a4, char a5)
{
  __int64 v7; // r15
  signed __int64 v8; // rax
  char v9; // si
  unsigned int v10; // edx
  __int64 v11; // r14
  char v12; // si
  _BYTE *v13; // r11
  _BYTE *v14; // r10
  __int16 v15; // r9
  bool v16; // zf
  __int64 v17; // rcx
  __int64 *v18; // rax
  __int64 **v19; // rcx
  __int64 **v20; // rcx
  __int64 **v21; // rax
  __int64 *v22; // rax
  char *v24; // [rsp+0h] [rbp-40h]
  _QWORD v25[5]; // [rsp+8h] [rbp-38h]
  __int128 v26; // [rsp+30h] [rbp-10h]
  signed __int64 v27; // [rsp+88h] [rbp+48h]
  signed __int64 v28; // [rsp+90h] [rbp+50h]

  v25[2] = 0;
  v24 = a2 + 24;
  v25[4] = 0;
  v25[0] = a2 + 1;
  v25[1] = a2 + 40;
  v7 = 2LL * a4;
  v25[3] = a2 + 40;
  v8 = a3[2];
  v9 = *a2;
  v10 = 1;
  v11 = 2LL * BYTE6(v8);
  v26 = 0;
  HIDWORD(v28) = HIDWORD(v8);
  v27 = v8;
  v12 = v9 & 1;
  if ( v12 )
  {
    v13 = 0;
    v14 = 0;
  }
  else
  {
    v14 = (_BYTE *)v25[2 * a4];
    v13 = (_BYTE *)v25[2 * BYTE6(v8)];
  }
  if ( a4 )
  {
    if ( a4 == 1 )
    {
      LODWORD(v28) = 0;
      v8 = v28;
    }
    else if ( a4 == 3 )
    {
      v15 = 0;
      WORD2(v27) = 0;
      goto LABEL_10;
    }
  }
  else if ( !v12 && *v14 >= 8u )
  {
    return 0;
  }
  v15 = WORD2(v27);
LABEL_10:
  if ( BYTE6(v28) == 3 )
  {
    v15 = (unsigned __int64)&a2[-a1] >> 6;
    WORD2(v27) = v15;
  }
  BYTE6(v27) = a4;
  if ( a4 == 1 )
  {
    v28 = _InterlockedCompareExchange64(a3 + 2, v27, v8);
    v16 = (_DWORD)v28 == 0;
  }
  else
  {
    if ( (a5 & 1) == 0 )
    {
      if ( *((_WORD *)a3 + 16) == *((_WORD *)a3 + 17) )
        a3[2] = v27;
      else
        WORD2(v28) = _InterlockedExchange((volatile __int32 *)a3 + 5, SHIDWORD(v27));
      goto LABEL_25;
    }
    if ( BYTE6(v8) == 2 )
      return 0;
    v16 = HIDWORD(v8) == _InterlockedCompareExchange((volatile signed __int32 *)a3 + 5, SHIDWORD(v27), SHIDWORD(v8));
  }
  if ( !v16 )
    return 0;
LABEL_25:
  v17 = v25[v11 - 1];
  if ( WORD2(v28) != v15 )
  {
    if ( v15 )
    {
      if ( (*a2 & 1) == 0 )
        *((_WORD *)a3 + 23) = *((_WORD *)a2 + 2);
    }
    else
    {
      *((_WORD *)a3 + 23) = 0;
    }
  }
  if ( v17 )
  {
    v18 = (__int64 *)*a3;
    if ( *(__int64 **)(*a3 + 8) != a3 )
      goto LABEL_40;
    v19 = (__int64 **)a3[1];
    if ( *v19 != a3 )
      goto LABEL_40;
    *v19 = v18;
    v18[1] = (__int64)v19;
    if ( v13 )
      --*v13;
  }
  v20 = (__int64 **)v25[v7 - 1];
  if ( !v20 )
    return v10;
  if ( *((_WORD *)a3 + 16) == *((_WORD *)a3 + 17) )
  {
    v21 = (__int64 **)v20[1];
    if ( *v21 == (__int64 *)v20 )
    {
      *a3 = (__int64)v20;
      a3[1] = (__int64)v21;
      *v21 = a3;
      v20[1] = a3;
      goto LABEL_42;
    }
LABEL_40:
    __fastfail(3u);
  }
  v22 = *v20;
  if ( (__int64 **)(*v20)[1] != v20 )
    goto LABEL_40;
  *a3 = (__int64)v22;
  a3[1] = (__int64)v20;
  v22[1] = (__int64)a3;
  *v20 = a3;
LABEL_42:
  if ( v14 )
    ++*v14;
  return v10;
}

```

## disassembly

```asm
0x1400329a8  mov     [rsp-38h+arg_0], rbx
0x1400329ad  push    rbp
0x1400329ae  push    rsi
0x1400329af  push    rdi
0x1400329b0  push    r12
0x1400329b2  push    r13
0x1400329b4  push    r14
0x1400329b6  push    r15
0x1400329b8  mov     rbp, rsp
0x1400329bb  sub     rsp, 40h
0x1400329bf  xor     r13d, r13d
0x1400329c2  movsxd  rbx, r9d
0x1400329c5  lea     rax, [rdx+18h]
0x1400329c9  mov     [rbp+var_28], r13
0x1400329cd  mov     [rbp+var_40], rax
0x1400329d1  mov     r12, rcx
0x1400329d4  lea     rax, [rdx+1]
0x1400329d8  mov     [rbp+var_18], r13
0x1400329dc  mov     [rbp+var_38], rax
0x1400329e0  mov     r15, rbx
0x1400329e3  lea     rax, [rdx+28h]
0x1400329e7  mov     rdi, rdx
0x1400329ea  mov     [rbp+var_30], rax
0x1400329ee  add     r15, r15
0x1400329f1  mov     [rbp+var_20], rax
0x1400329f5  xorps   xmm0, xmm0
0x1400329f8  mov     rax, [r8+10h]
0x1400329fc  mov     sil, [rdx]
0x1400329ff  mov     rcx, rax
0x140032a02  shr     rcx, 30h
0x140032a06  lea     edx, [r13+1]
0x140032a0a  movzx   r14d, cl
0x140032a0e  add     r14, r14
0x140032a11  movdqa  [rbp+var_10], xmm0
0x140032a16  mov     [rbp+arg_10], rax
0x140032a1a  mov     [rbp+arg_8], rax
0x140032a1e  and     sil, dl
0x140032a21  jz      short loc_140032A2B
0x140032a23  mov     r11d, r13d
0x140032a26  mov     r10d, r13d
0x140032a29  jmp     short loc_140032A35
0x140032a2b  mov     r10, [rbp+r15*8+var_38]
0x140032a30  mov     r11, [rbp+r14*8+var_38]
0x140032a35  mov     r9d, ebx
0x140032a38  test    ebx, ebx
0x140032a3a  jz      short loc_140032A92
0x140032a3c  sub     r9d, edx
0x140032a3f  jz      short loc_140032A51
0x140032a41  cmp     r9d, 2
0x140032a45  jnz     short loc_140032A59
0x140032a47  mov     r9d, r13d
0x140032a4a  mov     word ptr [rbp+arg_8+4], r13w
0x140032a4f  jmp     short loc_140032A5E
0x140032a51  mov     dword ptr [rbp+arg_10], r13d
0x140032a55  mov     rax, [rbp+arg_10]
0x140032a59  movzx   r9d, word ptr [rbp+arg_8+4]
0x140032a5e  cmp     byte ptr [rbp+arg_10+6], 3
0x140032a62  jnz     short loc_140032A76
0x140032a64  mov     rcx, rdi
0x140032a67  sub     rcx, r12
0x140032a6a  shr     rcx, 6
0x140032a6e  movzx   r9d, cx
0x140032a72  mov     word ptr [rbp+arg_8+4], cx
0x140032a76  mov     byte ptr [rbp+arg_8+6], bl
0x140032a79  cmp     ebx, edx
0x140032a7b  jnz     short loc_140032AA5
0x140032a7d  mov     rcx, [rbp+arg_8]
0x140032a81  lock cmpxchg [r8+10h], rcx
0x140032a87  mov     [rbp+arg_10], rax
0x140032a8b  cmp     eax, r13d
0x140032a8e  jz      short loc_140032AE5
0x140032a90  jmp     short loc_140032A9D
0x140032a92  test    sil, sil
0x140032a95  jnz     short loc_140032A59
0x140032a97  cmp     byte ptr [r10], 8
0x140032a9b  jb      short loc_140032A59
0x140032a9d  mov     edx, r13d
0x140032aa0  jmp     loc_140032B86
0x140032aa5  test    [rbp+arg_20], dl
0x140032aa8  jz      short loc_140032AC5
0x140032aaa  mov     rcx, rax
0x140032aad  shr     rcx, 30h
0x140032ab1  cmp     cl, 2
0x140032ab4  jz      short loc_140032A9D
0x140032ab6  mov     ecx, dword ptr [rbp+arg_8+4]
0x140032ab9  shr     rax, 20h
0x140032abd  lock cmpxchg [r8+14h], ecx
0x140032ac3  jmp     short loc_140032A8E
0x140032ac5  movzx   eax, word ptr [r8+22h]
0x140032aca  cmp     [r8+20h], ax
0x140032acf  jnz     short loc_140032ADB
0x140032ad1  mov     rax, [rbp+arg_8]
0x140032ad5  mov     [r8+10h], rax
0x140032ad9  jmp     short loc_140032AE5
0x140032adb  mov     eax, dword ptr [rbp+arg_8+4]
0x140032ade  xchg    eax, [r8+14h]
0x140032ae2  mov     dword ptr [rbp+arg_10+4], eax
0x140032ae5  mov     rcx, [rbp+r14*8+var_40]
0x140032aea  cmp     word ptr [rbp+arg_10+4], r9w
0x140032aef  jz      short loc_140032B0B
0x140032af1  test    r9w, r9w
0x140032af5  jnz     short loc_140032AFE
0x140032af7  mov     [r8+2Eh], r13w
0x140032afc  jmp     short loc_140032B0B
0x140032afe  test    [rdi], dl
0x140032b00  jnz     short loc_140032B0B
0x140032b02  movzx   eax, word ptr [rdi+4]
0x140032b06  mov     [r8+2Eh], ax
0x140032b0b  test    rcx, rcx
0x140032b0e  jz      short loc_140032B31
0x140032b10  mov     rax, [r8]
0x140032b13  cmp     [rax+8], r8
0x140032b17  jnz     short loc_140032B69
0x140032b19  mov     rcx, [r8+8]
0x140032b1d  cmp     [rcx], r8
0x140032b20  jnz     short loc_140032B69
0x140032b22  mov     [rcx], rax
0x140032b25  mov     [rax+8], rcx
0x140032b29  test    r11, r11
0x140032b2c  jz      short loc_140032B31
0x140032b2e  dec     byte ptr [r11]
0x140032b31  mov     rcx, [rbp+r15*8+var_40]
0x140032b36  test    rcx, rcx
0x140032b39  jz      short loc_140032B86
0x140032b3b  movzx   eax, word ptr [r8+22h]
0x140032b40  cmp     [r8+20h], ax
0x140032b45  jnz     short loc_140032B60
0x140032b47  mov     rax, [rcx+8]
0x140032b4b  cmp     [rax], rcx
0x140032b4e  jnz     short loc_140032B69
0x140032b50  mov     [r8], rcx
0x140032b53  mov     [r8+8], rax
0x140032b57  mov     [rax], r8
0x140032b5a  mov     [rcx+8], r8
0x140032b5e  jmp     short loc_140032B7E
0x140032b60  mov     rax, [rcx]
0x140032b63  cmp     [rax+8], rcx
0x140032b67  jz      short loc_140032B70
0x140032b69  mov     ecx, 3
0x140032b6e  int     29h; Win8: RtlFailFast(ecx)
0x140032b70  mov     [r8], rax
0x140032b73  mov     [r8+8], rcx
0x140032b77  mov     [rax+8], r8
0x140032b7b  mov     [rcx], r8
0x140032b7e  test    r10, r10
0x140032b81  jz      short loc_140032B86
0x140032b83  add     [r10], dl
0x140032b86  mov     rbx, [rsp+40h+arg_0]
0x140032b8e  mov     eax, edx
0x140032b90  add     rsp, 40h
0x140032b94  pop     r15
0x140032b96  pop     r14
0x140032b98  pop     r13
0x140032b9a  pop     r12
0x140032b9c  pop     rdi
0x140032b9d  pop     rsi
0x140032b9e  pop     rbp
0x140032b9f  retn
```
