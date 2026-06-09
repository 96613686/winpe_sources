# GetComponentGlyphList

- ea: `0x18000faf0`
- end: `0x18000fcfc`
- name: `GetComponentGlyphList`
- size: `524`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000f298`
- `0x18000faf0`
- `0x18001357c`

## callees

- `0x18000faf0`
- `0x180013230`
- `0x180013ea8`
- `0x18002a590`

## pseudocode

```c
__int64 __fastcall GetComponentGlyphList(
        __int64 *a1,
        int a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 a5,
        unsigned __int16 *a6,
        unsigned __int16 a7,
        unsigned __int16 a8,
        int a9,
        int a10)
{
  __int64 result; // rax
  unsigned __int16 GenericSize; // ax
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // di
  int v18; // r9d
  int v19; // edx
  __int16 v20; // [rsp+50h] [rbp-31h] BYREF
  __int16 v21; // [rsp+54h] [rbp-2Dh] BYREF
  int v22; // [rsp+58h] [rbp-29h] BYREF
  __int64 v23; // [rsp+60h] [rbp-21h]
  __int64 v24; // [rsp+68h] [rbp-19h] BYREF
  __int16 v25; // [rsp+70h] [rbp-11h]

  v24 = 0;
  v25 = 0;
  v23 = a4;
  *a3 = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  result = GetGlyphHeader((_DWORD)a1, a2, a8, a9, a10, (__int64)&v24, (__int64)&v22, (__int64)&v21);
  if ( !(_WORD)result )
  {
    if ( *a6 < a7 )
      *a6 = a7;
    if ( (v24 & 0x8000u) == 0LL )
    {
      return 0;
    }
    else
    {
      GenericSize = GetGenericSize(&GLYF_HEADER_CONTROL);
      v14 = v22 + (unsigned int)GenericSize;
      while ( *a3 < a5 )
      {
        v15 = *a1;
        if ( !*a1 )
          return 1001;
        v16 = (unsigned int)(v14 + 2);
        if ( (unsigned int)v16 < (unsigned int)v14
          || (unsigned int)v16 > *((_DWORD *)a1 + 2)
          || (int)v14 + 4 < (unsigned int)(v14 + 2)
          || (unsigned int)(v14 + 4) > *((_DWORD *)a1 + 2) )
        {
          return 1001;
        }
        v19 = *(unsigned __int8 *)(v16 + v15 + 1);
        v17 = *(_BYTE *)(v14 + v15 + 1);
        v18 = v23;
        LOWORD(v19) = _byteswap_ushort(*(_WORD *)(v16 + v15));
        *(_WORD *)(v23 + 2LL * (*a3)++) = v19;
        if ( (v17 & 1) != 0 )
          v14 = (unsigned int)(v14 + 8);
        else
          v14 = (unsigned int)(v14 + 6);
        if ( (v17 & 8) != 0 )
        {
          v14 = (unsigned int)(v14 + 2);
        }
        else if ( (v17 & 0x40) != 0 )
        {
          v14 = (unsigned int)(v14 + 4);
        }
        else if ( v17 < 0 )
        {
          v14 = (unsigned int)(v14 + 8);
        }
        result = GetComponentGlyphList(
                   (_DWORD)a1,
                   v19,
                   (unsigned int)&v20,
                   v18 + 2 * (unsigned int)*a3,
                   a5 - *a3,
                   (__int64)a6,
                   a7 + 1,
                   a8,
                   a9,
                   a10);
        if ( (_WORD)result )
          return result;
        if ( v20 )
          *a3 += v20;
        if ( (v17 & 0x20) == 0 )
          return 0;
      }
      return 1066;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000faf0  push    rbp
0x18000faf2  push    rbx
0x18000faf3  push    rsi
0x18000faf4  push    rdi
0x18000faf5  push    r12
0x18000faf7  push    r13
0x18000faf9  push    r14
0x18000fafb  push    r15
0x18000fafd  lea     rbp, [rsp-7]
0x18000fb02  sub     rsp, 88h
0x18000fb09  mov     rax, cs:__security_cookie
0x18000fb10  xor     rax, rsp
0x18000fb13  mov     [rbp+3Fh+var_48], rax
0x18000fb17  mov     r15, [rbp+3Fh+arg_28]
0x18000fb1b  xor     eax, eax
0x18000fb1d  mov     [rbp+3Fh+var_58], rax
0x18000fb21  xor     edi, edi
0x18000fb23  mov     [rbp+3Fh+var_50], ax
0x18000fb27  mov     rsi, r8
0x18000fb2a  lea     rax, [rbp+3Fh+var_6C]
0x18000fb2e  mov     [rbp+3Fh+var_60], r9
0x18000fb32  mov     r9d, [rbp+3Fh+arg_40]
0x18000fb39  mov     r12, rcx
0x18000fb3c  mov     [rsp+0C0h+var_88], rax
0x18000fb41  lea     rax, [rbp+3Fh+var_68]
0x18000fb45  mov     [rsp+0C0h+var_90], rax
0x18000fb4a  lea     rax, [rbp+3Fh+var_58]
0x18000fb4e  mov     [rsp+0C0h+var_98], rax
0x18000fb53  mov     eax, [rbp+3Fh+arg_48]
0x18000fb59  mov     [r8], di
0x18000fb5d  movzx   r8d, [rbp+3Fh+arg_38]
0x18000fb65  mov     [rsp+0C0h+var_A0], eax
0x18000fb69  mov     [rbp+3Fh+var_68], edi
0x18000fb6c  mov     [rbp+3Fh+var_6C], di
0x18000fb70  mov     [rbp+3Fh+var_70], di
0x18000fb74  call    GetGlyphHeader
0x18000fb79  test    ax, ax
0x18000fb7c  jnz     short loc_18000FBE2
0x18000fb7e  movzx   r14d, [rbp+3Fh+arg_30]
0x18000fb83  cmp     [r15], r14w
0x18000fb87  jb      loc_18000FCCC
0x18000fb8d  cmp     word ptr [rbp+3Fh+var_58], di
0x18000fb91  jge     loc_18000FCBD
0x18000fb97  lea     rcx, GLYF_HEADER_CONTROL
0x18000fb9e  call    GetGenericSize
0x18000fba3  movzx   r13d, [rbp+3Fh+arg_20]
0x18000fba8  movzx   ebx, ax
0x18000fbab  add     ebx, [rbp+3Fh+var_68]
0x18000fbae  cmp     [rsi], r13w
0x18000fbb2  jnb     loc_18000FCF2
0x18000fbb8  mov     rcx, [r12]
0x18000fbbc  test    rcx, rcx
0x18000fbbf  jz      short loc_18000FBDD
0x18000fbc1  lea     eax, [rbx+2]
0x18000fbc4  cmp     eax, ebx
0x18000fbc6  jb      short loc_18000FBDD
0x18000fbc8  cmp     eax, [r12+8]
0x18000fbcd  ja      short loc_18000FBDD
0x18000fbcf  lea     edx, [rax+2]
0x18000fbd2  cmp     edx, eax
0x18000fbd4  jb      short loc_18000FBDD
0x18000fbd6  cmp     edx, [r12+8]
0x18000fbdb  jbe     short loc_18000FC02
0x18000fbdd  mov     eax, 3E9h
0x18000fbe2  mov     rcx, [rbp+3Fh+var_48]
0x18000fbe6  xor     rcx, rsp; StackCookie
0x18000fbe9  call    __security_check_cookie
0x18000fbee  add     rsp, 88h
0x18000fbf5  pop     r15
0x18000fbf7  pop     r14
0x18000fbf9  pop     r13
0x18000fbfb  pop     r12
0x18000fbfd  pop     rdi
0x18000fbfe  pop     rsi
0x18000fbff  pop     rbx
0x18000fc00  pop     rbp
0x18000fc01  retn
0x18000fc02  movzx   edx, byte ptr [rax+rcx+1]
0x18000fc07  movzx   eax, byte ptr [rax+rcx]
0x18000fc0b  movzx   edi, byte ptr [rbx+rcx+1]
0x18000fc10  mov     r9, [rbp+3Fh+var_60]
0x18000fc14  shl     ax, 8
0x18000fc18  or      dx, ax
0x18000fc1b  movzx   eax, word ptr [rsi]
0x18000fc1e  mov     [r9+rax*2], dx
0x18000fc23  inc     word ptr [rsi]
0x18000fc26  test    dil, 1
0x18000fc2a  jz      loc_18000FCC4
0x18000fc30  add     ebx, 8
0x18000fc33  test    dil, 8
0x18000fc37  jnz     loc_18000FCD5
0x18000fc3d  test    dil, 40h
0x18000fc41  jnz     loc_18000FCDD
0x18000fc47  test    dil, dil
0x18000fc4a  js      loc_18000FCE5
0x18000fc50  movzx   eax, word ptr [rsi]
0x18000fc53  lea     ecx, [r14+1]
0x18000fc57  movzx   r8d, r13w
0x18000fc5b  sub     r8w, [rsi]
0x18000fc5f  lea     r9, [r9+rax*2]
0x18000fc63  mov     eax, [rbp+3Fh+arg_48]
0x18000fc69  mov     [rsp+0C0h+var_78], eax
0x18000fc6d  mov     eax, [rbp+3Fh+arg_40]
0x18000fc73  mov     [rsp+0C0h+var_80], eax
0x18000fc77  movzx   eax, [rbp+3Fh+arg_38]
0x18000fc7e  mov     word ptr [rsp+0C0h+var_88], ax
0x18000fc83  mov     word ptr [rsp+0C0h+var_90], cx
0x18000fc88  mov     rcx, r12
0x18000fc8b  mov     [rsp+0C0h+var_98], r15
0x18000fc90  mov     word ptr [rsp+0C0h+var_A0], r8w
0x18000fc96  lea     r8, [rbp+3Fh+var_70]
0x18000fc9a  call    GetComponentGlyphList
0x18000fc9f  test    ax, ax
0x18000fca2  jnz     loc_18000FBE2
0x18000fca8  movzx   eax, [rbp+3Fh+var_70]
0x18000fcac  test    ax, ax
0x18000fcaf  jnz     short loc_18000FCED
0x18000fcb1  test    dil, 20h
0x18000fcb5  jnz     loc_18000FBAE
0x18000fcbb  xor     edi, edi
0x18000fcbd  mov     eax, edi
0x18000fcbf  jmp     loc_18000FBE2
0x18000fcc4  add     ebx, 6
0x18000fcc7  jmp     loc_18000FC33
0x18000fccc  mov     [r15], r14w
0x18000fcd0  jmp     loc_18000FB8D
0x18000fcd5  add     ebx, 2
0x18000fcd8  jmp     loc_18000FC50
0x18000fcdd  add     ebx, 4
0x18000fce0  jmp     loc_18000FC50
0x18000fce5  add     ebx, 8
0x18000fce8  jmp     loc_18000FC50
0x18000fced  add     [rsi], ax
0x18000fcf0  jmp     short loc_18000FCB1
0x18000fcf2  mov     eax, 42Ah
0x18000fcf7  jmp     loc_18000FBE2
```
