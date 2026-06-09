# PatternMatch(ushort *,int,ushort *,ulong,_STRING_TOKEN *,ulong *)

- ea: `0x140019e10`
- end: `0x14001a072`
- name: `?PatternMatch@@YAKPEAGH0KPEAU_STRING_TOKEN@@PEAK@Z`
- size: `610`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, unsigned __int16 *, unsigned int, struct _STRING_TOKEN *, unsigned int *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140019960`
- `0x140019e10`

## callees

- `0x140019e10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x140019ef7`
- `msvcrt!_wcsicmp` at `0x140019ef7`

## pseudocode

```c
__int64 __fastcall PatternMatch(
        unsigned __int16 *a1,
        int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        struct _STRING_TOKEN *a5,
        unsigned int *a6)
{
  unsigned __int16 v6; // ax
  int v9; // r10d
  unsigned __int16 *v10; // rdi
  unsigned int *v11; // r15
  struct _STRING_TOKEN *v12; // r14
  int v13; // ebx
  wchar_t v14; // cx
  wchar_t v16; // dx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // r12
  unsigned int v20; // r13d
  __int64 v21; // rcx
  __int64 v22; // r9
  __int64 v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // ebx
  wchar_t String2; // [rsp+70h] [rbp+8h] BYREF
  __int16 v27; // [rsp+72h] [rbp+Ah]
  int v28; // [rsp+78h] [rbp+10h]
  wchar_t String1; // [rsp+80h] [rbp+18h] BYREF
  __int16 v30; // [rsp+82h] [rbp+1Ah]

  v28 = a2;
  v6 = *a1;
  v9 = a2;
  v10 = a1;
  if ( !*a1 )
    return *a3 != 0 ? 0x491 : 0;
  v11 = a6;
  v12 = a5;
  v13 = 0;
  while ( 1 )
  {
    if ( v6 == 42 )
    {
      while ( *++v10 )
      {
        v18 = *v11;
        v19 = v18;
        *((_DWORD *)v12 + 2 * v18) = a4;
        v20 = v18 + 1;
        *((_DWORD *)v12 + 2 * v18 + 1) = 0;
        *v11 = v18 + 1;
        if ( *v10 != 42 )
        {
          v24 = PatternMatch(v10, v9, a3, a4, v12, v11);
          v25 = 1169;
          while ( v24 == 1169 )
          {
            ++*((_DWORD *)v12 + 2 * v19 + 1);
            ++a3;
            *v11 = v20;
            if ( !*a3 )
              return v25;
            v24 = PatternMatch(v10, v28, a3, ++a4, v12, v11);
          }
          return v24;
        }
      }
      v21 = *v11;
      v22 = v21;
      *((_DWORD *)v12 + 2 * v21) = a4;
      *v11 = v21 + 1;
      if ( a3 )
      {
        v23 = 0x7FFFFFFF;
        do
        {
          if ( !*a3 )
            break;
          ++a3;
          --v23;
        }
        while ( v23 );
        if ( v23 )
        {
          *((_DWORD *)v12 + 2 * v22 + 1) = v23 != 0 ? 0x7FFFFFFF - v23 : 0;
          return 0;
        }
      }
      return 13;
    }
    if ( v6 == 47 )
      return 13;
    if ( v6 == 63 )
      break;
    if ( v6 == 92 )
    {
      v14 = *++v10;
      if ( !*v10 )
        return 13;
      switch ( v14 )
      {
        case '?':
          v14 = 63;
          break;
        case '*':
          v14 = 42;
          break;
        case '/':
          v14 = 47;
          break;
        case '\\':
          break;
        default:
          return 13;
      }
    }
    else
    {
      v14 = v6;
    }
    v16 = *a3;
    if ( v9 )
    {
      String1 = v14;
      String2 = v16;
      v30 = 0;
      v27 = 0;
      if ( _wcsicmp(&String1, &String2) )
        return 1169;
      v9 = v28;
    }
    else if ( v16 != v14 )
    {
      return 1169;
    }
    v17 = *v11;
    if ( !v13 )
    {
      v13 = 1;
LABEL_26:
      *((_DWORD *)v12 + 2 * v17) = a4;
      *v11 = v17 + 1;
      *((_DWORD *)v12 + 2 * v17 + 1) = 1;
      goto LABEL_27;
    }
    ++*((_DWORD *)v12 + 2 * (unsigned int)(v17 - 1) + 1);
LABEL_27:
    ++v10;
    ++a3;
    ++a4;
    v6 = *v10;
    if ( !*v10 )
      return *a3 != 0 ? 0x491 : 0;
  }
  if ( *a3 )
  {
    v17 = *v11;
    v13 = 0;
    goto LABEL_26;
  }
  return 1169;
}

```

## disassembly

```asm
0x140019e10  mov     [rsp+arg_18], rbx
0x140019e15  mov     [rsp+arg_8], edx
0x140019e19  push    rbp
0x140019e1a  push    rsi
0x140019e1b  push    rdi
0x140019e1c  push    r12
0x140019e1e  push    r13
0x140019e20  push    r14
0x140019e22  push    r15
0x140019e24  sub     rsp, 30h
0x140019e28  movzx   eax, word ptr [rcx]
0x140019e2b  xor     r11d, r11d
0x140019e2e  mov     ebp, r9d
0x140019e31  mov     rsi, r8
0x140019e34  mov     r10d, edx
0x140019e37  mov     rdi, rcx
0x140019e3a  test    ax, ax
0x140019e3d  jz      loc_140019F68
0x140019e43  mov     r15, [rsp+68h+arg_28]
0x140019e4b  lea     edx, [r11+2Ah]
0x140019e4f  mov     r14, [rsp+68h+arg_20]
0x140019e57  lea     r12d, [r11+2Fh]
0x140019e5b  mov     ebx, r11d
0x140019e5e  lea     r13d, [r11+3Fh]
0x140019e62  lea     r8d, [r11+5Ch]
0x140019e66  cmp     ax, dx
0x140019e69  jz      loc_140019FB4
0x140019e6f  cmp     ax, r12w
0x140019e73  jz      short loc_140019EA9
0x140019e75  cmp     ax, r13w
0x140019e79  jz      loc_140019F33
0x140019e7f  cmp     ax, r8w
0x140019e83  jnz     short loc_140019EC3
0x140019e85  add     rdi, 2
0x140019e89  movzx   ecx, word ptr [rdi]
0x140019e8c  cmp     r11w, cx
0x140019e90  jz      short loc_140019EA9
0x140019e92  cmp     r13w, cx
0x140019e96  jz      short loc_140019EBD
0x140019e98  cmp     dx, cx
0x140019e9b  jz      short loc_140019EB8
0x140019e9d  cmp     r12w, cx
0x140019ea1  jz      short loc_140019EB3
0x140019ea3  cmp     r8w, cx
0x140019ea7  jz      short loc_140019EC6
0x140019ea9  mov     eax, 0Dh
0x140019eae  jmp     loc_140019F7A
0x140019eb3  mov     ecx, r12d
0x140019eb6  jmp     short loc_140019EC6
0x140019eb8  movzx   ecx, dx
0x140019ebb  jmp     short loc_140019EC6
0x140019ebd  movzx   ecx, r13w
0x140019ec1  jmp     short loc_140019EC6
0x140019ec3  movzx   ecx, ax
0x140019ec6  movzx   edx, word ptr [rsi]
0x140019ec9  test    r10d, r10d
0x140019ecc  jz      short loc_140019F13
0x140019ece  mov     [rsp+68h+String1], cx
0x140019ed6  lea     rcx, [rsp+68h+String1]; String1
0x140019ede  mov     [rsp+68h+String2], dx
0x140019ee3  lea     rdx, [rsp+68h+String2]; String2
0x140019ee8  mov     [rsp+68h+arg_12], r11w
0x140019ef1  mov     [rsp+68h+arg_2], r11w
0x140019ef7  call    cs:__imp__wcsicmp
0x140019efd  xor     r11d, r11d
0x140019f00  test    eax, eax
0x140019f02  jnz     loc_140019F92
0x140019f08  mov     r10d, [rsp+68h+arg_8]
0x140019f0d  lea     r8d, [r11+5Ch]
0x140019f11  jmp     short loc_140019F18
0x140019f13  cmp     dx, cx
0x140019f16  jnz     short loc_140019F92
0x140019f18  mov     ecx, [r15]
0x140019f1b  mov     edx, 2Ah ; '*'
0x140019f20  test    ebx, ebx
0x140019f22  jnz     short loc_140019F29
0x140019f24  lea     ebx, [rdx-29h]
0x140019f27  jmp     short loc_140019F3F
0x140019f29  lea     eax, [rcx-1]
0x140019f2c  inc     dword ptr [r14+rax*8+4]
0x140019f31  jmp     short loc_140019F52
0x140019f33  cmp     r11w, [rsi]
0x140019f37  jz      short loc_140019F92
0x140019f39  mov     ecx, [r15]
0x140019f3c  mov     ebx, r11d
0x140019f3f  lea     eax, [rcx+1]
0x140019f42  mov     [r14+rcx*8], ebp
0x140019f46  mov     [r15], eax
0x140019f49  mov     dword ptr [r14+rcx*8+4], 1
0x140019f52  add     rdi, 2
0x140019f56  add     rsi, 2
0x140019f5a  inc     ebp
0x140019f5c  movzx   eax, word ptr [rdi]
0x140019f5f  test    ax, ax
0x140019f62  jnz     loc_140019E66
0x140019f68  mov     eax, r11d
0x140019f6b  mov     ebx, 491h
0x140019f70  sub     ax, [rsi]
0x140019f73  neg     ax
0x140019f76  sbb     eax, eax
0x140019f78  and     eax, ebx
0x140019f7a  mov     rbx, [rsp+68h+arg_18]
0x140019f82  add     rsp, 30h
0x140019f86  pop     r15
0x140019f88  pop     r14
0x140019f8a  pop     r13
0x140019f8c  pop     r12
0x140019f8e  pop     rdi
0x140019f8f  pop     rsi
0x140019f90  pop     rbp
0x140019f91  retn
0x140019f92  mov     eax, 491h
0x140019f97  jmp     short loc_140019F7A
0x140019f99  mov     eax, [r15]
0x140019f9c  mov     r12d, eax
0x140019f9f  mov     [r14+rax*8], ebp
0x140019fa3  lea     r13d, [rax+1]
0x140019fa7  mov     [r14+rax*8+4], r11d
0x140019fac  mov     [r15], r13d
0x140019faf  cmp     dx, [rdi]
0x140019fb2  jnz     short loc_14001A012
0x140019fb4  add     rdi, 2
0x140019fb8  cmp     [rdi], r11w
0x140019fbc  jnz     short loc_140019F99
0x140019fbe  mov     ecx, [r15]
0x140019fc1  mov     r9d, ecx
0x140019fc4  mov     [r14+rcx*8], ebp
0x140019fc8  lea     eax, [rcx+1]
0x140019fcb  mov     [r15], eax
0x140019fce  test    rsi, rsi
0x140019fd1  jz      loc_140019EA9
0x140019fd7  mov     edx, 7FFFFFFFh
0x140019fdc  mov     ecx, edx
0x140019fde  cmp     [rsi], r11w
0x140019fe2  jz      short loc_140019FEE
0x140019fe4  add     rsi, 2
0x140019fe8  sub     rcx, 1
0x140019fec  jnz     short loc_140019FDE
0x140019fee  sub     rdx, rcx
0x140019ff1  mov     rax, rcx
0x140019ff4  neg     rax
0x140019ff7  sbb     r8, r8
0x140019ffa  and     r8, rdx
0x140019ffd  test    rcx, rcx
0x14001a000  jz      loc_140019EA9
0x14001a006  mov     [r14+r9*8+4], r8d
0x14001a00b  xor     eax, eax
0x14001a00d  jmp     loc_140019F7A
0x14001a012  mov     [rsp+68h+var_40], r15; unsigned int *
0x14001a017  mov     r9d, ebp; unsigned int
0x14001a01a  mov     r8, rsi; unsigned __int16 *
0x14001a01d  mov     [rsp+68h+var_48], r14; struct _STRING_TOKEN *
0x14001a022  mov     edx, r10d; int
0x14001a025  mov     rcx, rdi; unsigned __int16 *
0x14001a028  call    ?PatternMatch@@YAKPEAGH0KPEAU_STRING_TOKEN@@PEAK@Z; PatternMatch(ushort *,int,ushort *,ulong,_STRING_TOKEN *,ulong *)
0x14001a02d  mov     ebx, 491h
0x14001a032  jmp     short loc_14001A065
0x14001a034  inc     dword ptr [r14+r12*8+4]
0x14001a039  add     rsi, 2
0x14001a03d  xor     eax, eax
0x14001a03f  mov     [r15], r13d
0x14001a042  cmp     ax, [rsi]
0x14001a045  jz      short loc_14001A06B
0x14001a047  mov     edx, [rsp+68h+arg_8]; int
0x14001a04b  inc     ebp
0x14001a04d  mov     r9d, ebp; unsigned int
0x14001a050  mov     [rsp+68h+var_40], r15; unsigned int *
0x14001a055  mov     r8, rsi; unsigned __int16 *
0x14001a058  mov     [rsp+68h+var_48], r14; struct _STRING_TOKEN *
0x14001a05d  mov     rcx, rdi; unsigned __int16 *
0x14001a060  call    ?PatternMatch@@YAKPEAGH0KPEAU_STRING_TOKEN@@PEAK@Z; PatternMatch(ushort *,int,ushort *,ulong,_STRING_TOKEN *,ulong *)
0x14001a065  cmp     eax, ebx
0x14001a067  jz      short loc_14001A034
0x14001a069  mov     ebx, eax
0x14001a06b  mov     eax, ebx
0x14001a06d  jmp     loc_140019F7A
```
