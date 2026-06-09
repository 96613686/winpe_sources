# EapMapToEapConfigArray

- ea: `0x180015a44`
- end: `0x180015d88`
- name: `EapMapToEapConfigArray`
- size: `836`
- prototype: `__int64 __fastcall(unsigned int, __int64, __int128 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180015020`

## callees

- `0x180001e26`
- `0x180015980`
- `0x180015a44`

## import_xrefs

- `MobileNetworking!AllocateMemory` at `0x180015a93`
- `MobileNetworking!AllocateMemory` at `0x180015c57`
- `MobileNetworking!AllocateMemory` at `0x180015cf4`
- `MobileNetworking!AllocateMemory` at `0x180015a93`
- `MobileNetworking!AllocateMemory` at `0x180015c57`
- `MobileNetworking!AllocateMemory` at `0x180015cf4`

## string_xrefs

- `0x180015a89`: `EapMapToEapConfigArray`
- `0x180015c4d`: `EapMapToEapConfigArray`
- `0x180015cea`: `EapMapToEapConfigArray`

## pseudocode

```c
__int64 __fastcall EapMapToEapConfigArray(unsigned int a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r12
  unsigned int v5; // edi
  unsigned __int64 v6; // rcx
  _QWORD *v7; // r14
  unsigned int Memory; // ebx
  unsigned int v9; // eax
  __int64 v10; // r8
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  __int64 v19; // rdi
  __int64 v20; // r13
  _WORD *v21; // rcx
  __int64 v23; // rax
  unsigned int v24; // r12d
  __int64 v25; // r13
  __int16 *v26; // rcx
  __int16 v27; // ax
  __int64 v28; // rax
  unsigned int v29; // r12d
  __int128 v31; // [rsp+30h] [rbp-58h] BYREF
  __int16 *v32; // [rsp+40h] [rbp-48h]
  unsigned int v35; // [rsp+A8h] [rbp+20h]

  v4 = a2;
  v5 = a1;
  v6 = 40LL * a1;
  if ( v6 > 0xFFFFFFFF )
  {
    Memory = 87;
  }
  else
  {
    v7 = (_QWORD *)a3 + 1;
    Memory = AllocateMemory(v6, (char *)a3 + 8, "EapMapToEapConfigArray", 93);
    if ( !Memory )
    {
      *((_DWORD *)a3 + 1) = v5;
      v9 = 0;
      while ( 1 )
      {
        v35 = v9;
        if ( v9 >= v5 )
          break;
        v10 = 2580LL * v9;
        *(_QWORD *)&v31 = v10;
        v11 = *(_DWORD *)(v10 + v4);
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                v15 = v14 - 1;
                if ( v15 )
                {
                  v16 = v15 - 1;
                  if ( v16 )
                  {
                    v17 = v16 - 2;
                    if ( v17 )
                    {
                      v18 = v17 - 1;
                      if ( v18 )
                      {
                        if ( v18 != 1 )
                        {
                          Memory = 13;
                          break;
                        }
                        v19 = 40LL * v9;
                        *(_DWORD *)(v19 + *v7 + 4) = 8;
                      }
                      else
                      {
                        v19 = 40LL * v9;
                        *(_DWORD *)(v19 + *v7 + 4) = 7;
                      }
                    }
                    else
                    {
                      v19 = 40LL * v9;
                      *(_DWORD *)(v19 + *v7 + 4) = 6;
                    }
                  }
                  else
                  {
                    v19 = 40LL * v9;
                    *(_DWORD *)(v19 + *v7 + 4) = 5;
                  }
                }
                else
                {
                  v19 = 40LL * v9;
                  *(_DWORD *)(v19 + *v7 + 4) = 4;
                }
              }
              else
              {
                v19 = 40LL * v9;
                *(_DWORD *)(v19 + *v7 + 4) = 3;
              }
            }
            else
            {
              v19 = 40LL * v9;
              *(_DWORD *)(v19 + *v7 + 4) = 2;
            }
          }
          else
          {
            v19 = 40LL * v9;
            *(_DWORD *)(v19 + *v7 + 4) = 1;
          }
        }
        else
        {
          v19 = 40LL * v9;
          *(_DWORD *)(v19 + *v7 + 4) = 0;
        }
        *(_DWORD *)(*v7 + v19 + 8) = *(_DWORD *)(v10 + v4 + 4);
        v20 = v10 + v4;
        v21 = (_WORD *)(v10 + v4 + 12);
        while ( *v21++ )
          ;
        v23 = -1;
        do
          ++v23;
        while ( *(_WORD *)(v20 + 2 * v23 + 12) );
        v24 = 2 * v23 + 2;
        Memory = AllocateMemory(v24, v19 + *v7 + 16LL, "EapMapToEapConfigArray", 151);
        if ( Memory )
          break;
        memcpy_0(*(void **)(*v7 + v19 + 16), (const void *)(v20 + 12), v24);
        v25 = v31 + a2;
        v26 = (__int16 *)(v31 + a2 + 524);
        v32 = v26;
        do
        {
          v27 = *v26++;
          v32 = v26;
        }
        while ( v27 );
        v28 = -1;
        do
          ++v28;
        while ( *(_WORD *)(v25 + 2 * v28 + 524) );
        if ( (unsigned int)v28 > *(_DWORD *)(v31 + a2 + 2576) || (unsigned int)v28 < *(_DWORD *)(v31 + a2 + 2572) )
        {
          Memory = 24;
          break;
        }
        v29 = 2 * v28 + 2;
        Memory = AllocateMemory(v29, v19 + *v7 + 24LL, "EapMapToEapConfigArray", 181);
        if ( Memory )
          break;
        memcpy_0(*(void **)(*v7 + v19 + 24), (const void *)(v25 + 524), v29);
        v9 = v35 + 1;
        v4 = a2;
        v5 = a1;
      }
    }
  }
  if ( Memory )
  {
    v31 = *a3;
    EapFreeEapConfigArray(&v31);
  }
  return Memory;
}

```

## disassembly

```asm
0x180015a44  mov     [rsp+arg_10], r8
0x180015a49  mov     [rsp+arg_8], rdx
0x180015a4e  mov     [rsp+arg_0], ecx
0x180015a52  push    rbx
0x180015a53  push    rsi
0x180015a54  push    rdi
0x180015a55  push    r12
0x180015a57  push    r13
0x180015a59  push    r14
0x180015a5b  push    r15
0x180015a5d  sub     rsp, 50h
0x180015a61  mov     r15, r8
0x180015a64  mov     r12, rdx
0x180015a67  mov     edi, ecx
0x180015a69  lea     rcx, [rdi+rdi*4]
0x180015a6d  shl     rcx, 3
0x180015a71  mov     eax, 0FFFFFFFFh
0x180015a76  cmp     rcx, rax
0x180015a79  ja      loc_180015D59
0x180015a7f  lea     r14, [r8+8]
0x180015a83  mov     r9d, 5Dh ; ']'
0x180015a89  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x180015a90  mov     rdx, r14
0x180015a93  call    cs:__imp_AllocateMemory
0x180015a99  mov     ebx, eax
0x180015a9b  xor     esi, esi
0x180015a9d  test    eax, eax
0x180015a9f  jnz     loc_180015D5E
0x180015aa5  mov     [r15+4], edi
0x180015aa9  mov     eax, esi
0x180015aab  mov     [rsp+88h+arg_18], eax
0x180015ab2  cmp     eax, edi
0x180015ab4  jnb     loc_180015D5E
0x180015aba  mov     edx, eax
0x180015abc  imul    r8, rdx, 0A14h
0x180015ac3  mov     qword ptr [rsp+88h+var_58], r8
0x180015ac8  mov     ecx, [r8+r12]
0x180015acc  test    ecx, ecx
0x180015ace  jz      loc_180015BE7
0x180015ad4  sub     ecx, 1
0x180015ad7  jz      loc_180015BCE
0x180015add  sub     ecx, 1
0x180015ae0  jz      loc_180015BB5
0x180015ae6  sub     ecx, 1
0x180015ae9  jz      loc_180015B9C
0x180015aef  sub     ecx, 1
0x180015af2  jz      loc_180015B83
0x180015af8  sub     ecx, 1
0x180015afb  jz      short loc_180015B6A
0x180015afd  sub     ecx, 2
0x180015b00  jz      short loc_180015B4E
0x180015b02  sub     ecx, 1
0x180015b05  jz      short loc_180015B32
0x180015b07  cmp     ecx, 1
0x180015b0a  jz      short loc_180015B16
0x180015b0c  mov     ebx, 0Dh
0x180015b11  jmp     loc_180015D5E
0x180015b16  lea     rax, [rdx+rdx*4]
0x180015b1a  lea     rdi, ds:0[rax*8]
0x180015b22  mov     rax, [r14]
0x180015b25  mov     dword ptr [rdi+rax+4], 8
0x180015b2d  jmp     loc_180015BFA
0x180015b32  lea     rax, [rdx+rdx*4]
0x180015b36  lea     rdi, ds:0[rax*8]
0x180015b3e  mov     rax, [r14]
0x180015b41  mov     dword ptr [rdi+rax+4], 7
0x180015b49  jmp     loc_180015BFA
0x180015b4e  lea     rax, [rdx+rdx*4]
0x180015b52  lea     rdi, ds:0[rax*8]
0x180015b5a  mov     rax, [r14]
0x180015b5d  mov     dword ptr [rdi+rax+4], 6
0x180015b65  jmp     loc_180015BFA
0x180015b6a  lea     rax, [rdx+rdx*4]
0x180015b6e  lea     rdi, ds:0[rax*8]
0x180015b76  mov     rax, [r14]
0x180015b79  mov     dword ptr [rdi+rax+4], 5
0x180015b81  jmp     short loc_180015BFA
0x180015b83  lea     rax, [rdx+rdx*4]
0x180015b87  lea     rdi, ds:0[rax*8]
0x180015b8f  mov     rax, [r14]
0x180015b92  mov     dword ptr [rdi+rax+4], 4
0x180015b9a  jmp     short loc_180015BFA
0x180015b9c  lea     rax, [rdx+rdx*4]
0x180015ba0  lea     rdi, ds:0[rax*8]
0x180015ba8  mov     rax, [r14]
0x180015bab  mov     dword ptr [rdi+rax+4], 3
0x180015bb3  jmp     short loc_180015BFA
0x180015bb5  lea     rax, [rdx+rdx*4]
0x180015bb9  lea     rdi, ds:0[rax*8]
0x180015bc1  mov     rax, [r14]
0x180015bc4  mov     dword ptr [rdi+rax+4], 2
0x180015bcc  jmp     short loc_180015BFA
0x180015bce  lea     rax, [rdx+rdx*4]
0x180015bd2  lea     rdi, ds:0[rax*8]
0x180015bda  mov     rax, [r14]
0x180015bdd  mov     dword ptr [rdi+rax+4], 1
0x180015be5  jmp     short loc_180015BFA
0x180015be7  lea     rax, [rdx+rdx*4]
0x180015beb  lea     rdi, ds:0[rax*8]
0x180015bf3  mov     rax, [r14]
0x180015bf6  mov     [rdi+rax+4], esi
0x180015bfa  mov     rcx, [r14]
0x180015bfd  mov     eax, [r8+r12+4]
0x180015c02  mov     [rcx+rdi+8], eax
0x180015c06  lea     r13, [r8+r12]
0x180015c0a  lea     rcx, [r13+0Ch]
0x180015c0e  mov     [rsp+88h+var_68], rcx
0x180015c13  movzx   eax, word ptr [rcx]
0x180015c16  add     rcx, 2
0x180015c1a  mov     [rsp+88h+var_68], rcx
0x180015c1f  test    ax, ax
0x180015c22  jz      short loc_180015C26
0x180015c24  jmp     short loc_180015C13
0x180015c26  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015c2a  inc     rax
0x180015c2d  cmp     [r13+rax*2+0Ch], si
0x180015c33  jnz     short loc_180015C2A
0x180015c35  lea     r12d, ds:2[rax*2]
0x180015c3d  mov     rdx, [r14]
0x180015c40  add     rdx, 10h
0x180015c44  add     rdx, rdi
0x180015c47  mov     r9d, 97h
0x180015c4d  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x180015c54  mov     ecx, r12d
0x180015c57  call    cs:__imp_AllocateMemory
0x180015c5d  mov     ebx, eax
0x180015c5f  test    eax, eax
0x180015c61  jnz     loc_180015D5E
0x180015c67  mov     r8d, r12d; Size
0x180015c6a  mov     rcx, [r14]
0x180015c6d  lea     rdx, [r13+0Ch]; Src
0x180015c71  mov     rcx, [rcx+rdi+10h]; void *
0x180015c76  call    memcpy_0
0x180015c7b  nop
0x180015c7c  mov     rdx, qword ptr [rsp+88h+var_58]
0x180015c81  mov     r8, [rsp+88h+arg_8]
0x180015c89  lea     r13, [rdx+r8]
0x180015c8d  lea     rcx, [r13+20Ch]
0x180015c94  mov     [rsp+88h+var_48], rcx
0x180015c99  movzx   eax, word ptr [rcx]
0x180015c9c  add     rcx, 2
0x180015ca0  mov     [rsp+88h+var_48], rcx
0x180015ca5  test    ax, ax
0x180015ca8  jz      short loc_180015CAC
0x180015caa  jmp     short loc_180015C99
0x180015cac  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015cb0  inc     rax
0x180015cb3  cmp     [r13+rax*2+20Ch], si
0x180015cbc  jnz     short loc_180015CB0
0x180015cbe  cmp     eax, [rdx+r8+0A10h]
0x180015cc6  ja      short loc_180015D34
0x180015cc8  cmp     eax, [rdx+r8+0A0Ch]
0x180015cd0  jb      short loc_180015D34
0x180015cd2  lea     r12d, ds:2[rax*2]
0x180015cda  mov     rdx, [r14]
0x180015cdd  add     rdx, 18h
0x180015ce1  add     rdx, rdi
0x180015ce4  mov     r9d, 0B5h
0x180015cea  lea     r8, aEapmaptoeapcon; "EapMapToEapConfigArray"
0x180015cf1  mov     ecx, r12d
0x180015cf4  call    cs:__imp_AllocateMemory
0x180015cfa  mov     ebx, eax
0x180015cfc  test    eax, eax
0x180015cfe  jnz     short loc_180015D5E
0x180015d00  mov     r8d, r12d; Size
0x180015d03  mov     rcx, [r14]
0x180015d06  lea     rdx, [r13+20Ch]; Src
0x180015d0d  mov     rcx, [rcx+rdi+18h]; void *
0x180015d12  call    memcpy_0
0x180015d17  mov     eax, [rsp+88h+arg_18]
0x180015d1e  inc     eax
0x180015d20  mov     r12, [rsp+88h+arg_8]
0x180015d28  mov     edi, [rsp+88h+arg_0]
0x180015d2f  jmp     loc_180015AAB
0x180015d34  mov     ebx, 18h
0x180015d39  jmp     short loc_180015D5E
0x180015d3b  mov     ebx, 57h ; 'W'
0x180015d40  mov     r15, [rsp+88h+arg_10]
0x180015d48  jmp     short loc_180015D5E
0x180015d4a  mov     ebx, 57h ; 'W'
0x180015d4f  mov     r15, [rsp+88h+arg_10]
0x180015d57  jmp     short loc_180015D5E
0x180015d59  mov     ebx, 57h ; 'W'
0x180015d5e  test    ebx, ebx
0x180015d60  jz      short loc_180015D76
0x180015d62  movups  xmm0, xmmword ptr [r15]
0x180015d66  movdqu  [rsp+88h+var_58], xmm0
0x180015d6c  lea     rcx, [rsp+88h+var_58]
0x180015d71  call    EapFreeEapConfigArray
0x180015d76  mov     eax, ebx
0x180015d78  add     rsp, 50h
0x180015d7c  pop     r15
0x180015d7e  pop     r14
0x180015d80  pop     r13
0x180015d82  pop     r12
0x180015d84  pop     rdi
0x180015d85  pop     rsi
0x180015d86  pop     rbx
0x180015d87  retn
```
