# UdfIsRemount

- ea: `0x14004c5f0`
- end: `0x14004c895`
- name: `UdfIsRemount`
- size: `677`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140049f80`

## callees

- `0x14000ca54`
- `0x14000cad4`
- `0x140010b14`
- `0x140012cc8`
- `0x14001c5a0`
- `0x14002ce08`
- `0x14004c5f0`

## pseudocode

```c
char __fastcall UdfIsRemount(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  __int64 v4; // r13
  __int64 v8; // rcx
  __int64 v9; // rbp
  char v10; // r15
  __int64 i; // rbx
  __int64 v12; // rsi
  int v13; // r14d
  __int64 v14; // rdx
  __int64 v15; // r8
  _DWORD *v16; // rdx
  int v17; // eax

  v4 = a4;
  if ( UdfNoRemounts )
    return 0;
  v8 = *(_QWORD *)&WPP_GLOBAL_Control;
  v9 = *(_QWORD *)(a2 + 8);
  v10 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      55,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      a2);
  }
  for ( i = qword_140025B20; (__int64 *)i != &qword_140025B20; i = *(_QWORD *)i )
  {
    *a3 = i - 32;
    if ( a2 != i - 32 )
    {
      v12 = *(_QWORD *)(i - 24);
      if ( v12 != v9 && *(_QWORD *)(v12 + 16) == *(_QWORD *)(v9 + 16) && !*(_DWORD *)(i + 20) )
      {
        if ( (unsigned __int8)UdfEquivalentPcb(v8, *(_QWORD *)(i - 16), *(_QWORD *)(a2 + 16)) )
        {
          if ( *(_DWORD *)(i + 52) == *(_DWORD *)(a2 + 84) )
          {
            v8 = *(_QWORD *)(i + 256);
            if ( *(_DWORD *)(v8 + 184) == *(_DWORD *)(v4 + 404) )
            {
              v13 = *(_DWORD *)(a2 + 48);
              if ( ((*(_DWORD *)(i + 16) ^ v13) & 0x4000) == 0 )
              {
                v14 = *(_QWORD *)(a2 + 344);
                v15 = *(_QWORD *)(i + 312);
                v8 = v14 != 0;
                if ( (v15 != 0) == (_DWORD)v8
                  && *(_WORD *)(i + 2108) == *(_WORD *)(a2 + 2140)
                  && (!v14
                   || *(_QWORD *)(v14 + 184) == *(_QWORD *)(v15 + 184) && *(_QWORD *)(v14 + 32) == *(_QWORD *)(v15 + 32)) )
                {
                  a4 = *(_QWORD *)(a2 + 1424);
                  v16 = *(_DWORD **)(i + 1392);
                  v8 = a4 == 0;
                  if ( (v16 == 0) == (_DWORD)v8 )
                  {
                    if ( !a4
                      || (v17 = *(_DWORD *)(a4 + 72), v17 == v16[18])
                      && !memcmp(
                            *(const void **)(a2 + 1424),
                            v16,
                            *(unsigned int *)(a4 + 76) + 80LL + 4LL * (unsigned int)(2 * v17)) )
                    {
                      if ( *(_DWORD *)(v12 + 24) == *(_DWORD *)(v9 + 24)
                        && *(_WORD *)(v9 + 6) == *(_WORD *)(v12 + 6)
                        && !memcmp((const void *)(v12 + 32), (const void *)(v9 + 32), *(unsigned __int16 *)(v9 + 6)) )
                      {
                        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
                        {
                          WPP_SF_qD(
                            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                            56,
                            WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
                            *a3,
                            *(_DWORD *)(*a3 + 48LL) ^ v13);
                        }
                        if ( ((*(_BYTE *)(a2 + 48) ^ *(_BYTE *)(*a3 + 48LL)) & 0x80u) != 0
                          && *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
                        {
                          WPP_SF_(
                            *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                            57,
                            WPP_808b98bda8443bb0d475e79494837b3d_Traceguids);
                        }
                        v10 = 1;
                        break;
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x800) != 0 )
  {
    LOBYTE(a4) = v10 != 0 ? 84 : 70;
    WPP_SF_c(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      58,
      WPP_808b98bda8443bb0d475e79494837b3d_Traceguids,
      a4);
  }
  return v10;
}

```

## disassembly

```asm
0x14004c5f0  push    rbx
0x14004c5f2  push    rbp
0x14004c5f3  push    rsi
0x14004c5f4  push    rdi
0x14004c5f5  push    r12
0x14004c5f7  push    r13
0x14004c5f9  push    r14
0x14004c5fb  push    r15
0x14004c5fd  sub     rsp, 38h
0x14004c601  cmp     cs:UdfNoRemounts, 0
0x14004c608  mov     r13, r9
0x14004c60b  mov     r12, r8
0x14004c60e  mov     rdi, rdx
0x14004c611  jz      short loc_14004C61A
0x14004c613  xor     al, al
0x14004c615  jmp     loc_14004C883
0x14004c61a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c621  lea     rsi, WPP_GLOBAL_Control
0x14004c628  mov     rbp, [rdx+8]
0x14004c62c  xor     r15b, r15b
0x14004c62f  cmp     rcx, rsi
0x14004c632  jz      short loc_14004C655
0x14004c634  test    dword ptr [rcx+2Ch], 800h
0x14004c63b  jz      short loc_14004C655
0x14004c63d  mov     rcx, [rcx+18h]
0x14004c641  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004c648  mov     edx, 37h ; '7'
0x14004c64d  mov     r9, rdi
0x14004c650  call    WPP_SF_q
0x14004c655  mov     rbx, cs:qword_140025B20
0x14004c65c  lea     rax, qword_140025B20
0x14004c663  cmp     rbx, rax
0x14004c666  jz      loc_14004C83F
0x14004c66c  lea     rax, [rbx-20h]
0x14004c670  mov     [r12], rax
0x14004c674  cmp     rdi, rax
0x14004c677  jz      loc_14004C7BC
0x14004c67d  mov     rsi, [rbx-18h]
0x14004c681  cmp     rsi, rbp
0x14004c684  jz      loc_14004C7BC
0x14004c68a  mov     rax, [rbp+10h]
0x14004c68e  cmp     [rsi+10h], rax
0x14004c692  jnz     loc_14004C7BC
0x14004c698  cmp     dword ptr [rbx+14h], 0
0x14004c69c  jnz     loc_14004C7BC
0x14004c6a2  mov     r8, [rdi+10h]
0x14004c6a6  mov     rdx, [rbx-10h]
0x14004c6aa  call    UdfEquivalentPcb
0x14004c6af  test    al, al
0x14004c6b1  jz      loc_14004C7BC
0x14004c6b7  mov     eax, [rdi+54h]
0x14004c6ba  cmp     [rbx+34h], eax
0x14004c6bd  jnz     loc_14004C7BC
0x14004c6c3  mov     rcx, [rbx+100h]
0x14004c6ca  mov     eax, [r13+194h]
0x14004c6d1  cmp     [rcx+0B8h], eax
0x14004c6d7  jnz     loc_14004C7BC
0x14004c6dd  mov     r14d, [rdi+30h]
0x14004c6e1  mov     eax, r14d
0x14004c6e4  xor     eax, [rbx+10h]
0x14004c6e7  bt      eax, 0Eh
0x14004c6eb  jb      loc_14004C7BC
0x14004c6f1  mov     rdx, [rdi+158h]
0x14004c6f8  xor     ecx, ecx
0x14004c6fa  mov     r8, [rbx+138h]
0x14004c701  test    rdx, rdx
0x14004c704  setnz   cl
0x14004c707  xor     eax, eax
0x14004c709  test    r8, r8
0x14004c70c  setnz   al
0x14004c70f  cmp     eax, ecx
0x14004c711  jnz     loc_14004C7BC
0x14004c717  movzx   eax, word ptr [rdi+85Ch]
0x14004c71e  cmp     [rbx+83Ch], ax
0x14004c725  jnz     loc_14004C7BC
0x14004c72b  test    rdx, rdx
0x14004c72e  jz      short loc_14004C74A
0x14004c730  mov     rax, [r8+0B8h]
0x14004c737  cmp     [rdx+0B8h], rax
0x14004c73e  jnz     short loc_14004C7BC
0x14004c740  mov     rax, [r8+20h]
0x14004c744  cmp     [rdx+20h], rax
0x14004c748  jnz     short loc_14004C7BC
0x14004c74a  mov     r9, [rdi+590h]
0x14004c751  xor     ecx, ecx
0x14004c753  mov     rdx, [rbx+570h]; Buf2
0x14004c75a  test    r9, r9
0x14004c75d  setz    cl
0x14004c760  xor     eax, eax
0x14004c762  test    rdx, rdx
0x14004c765  setz    al
0x14004c768  cmp     eax, ecx
0x14004c76a  jnz     short loc_14004C7BC
0x14004c76c  test    r9, r9
0x14004c76f  jz      short loc_14004C796
0x14004c771  mov     eax, [r9+48h]
0x14004c775  cmp     eax, [rdx+48h]
0x14004c778  jnz     short loc_14004C7BC
0x14004c77a  lea     r8d, [rax+rax]
0x14004c77e  mov     rcx, r9; Buf1
0x14004c781  mov     eax, [r9+4Ch]
0x14004c785  add     rax, 50h ; 'P'
0x14004c789  lea     r8, [rax+r8*4]; Size
0x14004c78d  call    memcmp
0x14004c792  test    eax, eax
0x14004c794  jnz     short loc_14004C7BC
0x14004c796  mov     eax, [rbp+18h]
0x14004c799  cmp     [rsi+18h], eax
0x14004c79c  jnz     short loc_14004C7BC
0x14004c79e  movzx   eax, word ptr [rbp+6]
0x14004c7a2  cmp     ax, [rsi+6]
0x14004c7a6  jnz     short loc_14004C7BC
0x14004c7a8  mov     r8d, eax; Size
0x14004c7ab  lea     rdx, [rbp+20h]; Buf2
0x14004c7af  lea     rcx, [rsi+20h]; Buf1
0x14004c7b3  call    memcmp
0x14004c7b8  test    eax, eax
0x14004c7ba  jz      short loc_14004C7C4
0x14004c7bc  mov     rbx, [rbx]
0x14004c7bf  jmp     loc_14004C65C
0x14004c7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c7cb  lea     rsi, WPP_GLOBAL_Control
0x14004c7d2  cmp     rcx, rsi
0x14004c7d5  jz      short loc_14004C802
0x14004c7d7  test    dword ptr [rcx+2Ch], 800h
0x14004c7de  jz      short loc_14004C802
0x14004c7e0  mov     r9, [r12]
0x14004c7e4  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004c7eb  mov     rcx, [rcx+18h]
0x14004c7ef  mov     edx, 38h ; '8'
0x14004c7f4  xor     r14d, [r9+30h]
0x14004c7f8  mov     [rsp+78h+var_58], r14d
0x14004c7fd  call    WPP_SF_qD
0x14004c802  mov     rax, [r12]
0x14004c806  mov     edx, [rax+30h]
0x14004c809  xor     edx, [rdi+30h]
0x14004c80c  test    dl, dl
0x14004c80e  jns     short loc_14004C83A
0x14004c810  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c817  cmp     rcx, rsi
0x14004c81a  jz      short loc_14004C83A
0x14004c81c  test    dword ptr [rcx+2Ch], 800h
0x14004c823  jz      short loc_14004C83A
0x14004c825  mov     rcx, [rcx+18h]
0x14004c829  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004c830  mov     edx, 39h ; '9'
0x14004c835  call    WPP_SF_
0x14004c83a  mov     r15b, 1
0x14004c83d  jmp     short loc_14004C846
0x14004c83f  lea     rsi, WPP_GLOBAL_Control
0x14004c846  mov     rcx, cs:WPP_GLOBAL_Control
0x14004c84d  cmp     rcx, rsi
0x14004c850  jz      short loc_14004C880
0x14004c852  test    dword ptr [rcx+2Ch], 800h
0x14004c859  jz      short loc_14004C880
0x14004c85b  mov     rcx, [rcx+18h]
0x14004c85f  lea     r8, WPP_808b98bda8443bb0d475e79494837b3d_Traceguids
0x14004c866  mov     dl, r15b
0x14004c869  neg     dl
0x14004c86b  mov     edx, 3Ah ; ':'
0x14004c870  sbb     r9b, r9b
0x14004c873  and     r9b, 0Eh
0x14004c877  add     r9b, 46h ; 'F'
0x14004c87b  call    WPP_SF_c
0x14004c880  mov     al, r15b
0x14004c883  add     rsp, 38h
0x14004c887  pop     r15
0x14004c889  pop     r14
0x14004c88b  pop     r13
0x14004c88d  pop     r12
0x14004c88f  pop     rdi
0x14004c890  pop     rsi
0x14004c891  pop     rbp
0x14004c892  pop     rbx
0x14004c893  retn
```
