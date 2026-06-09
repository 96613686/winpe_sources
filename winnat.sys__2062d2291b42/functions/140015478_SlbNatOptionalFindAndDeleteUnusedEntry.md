# SlbNatOptionalFindAndDeleteUnusedEntry

- ea: `0x140015478`
- end: `0x14001560b`
- name: `SlbNatOptionalFindAndDeleteUnusedEntry`
- size: `403`
- prototype: `char __fastcall(__int64, _QWORD *, void ***, char)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14000b658`

## callees

- `0x140015478`
- `0x1400196a4`
- `0x140019c78`
- `0x14001f560`
- `0x14001f680`
- `0x140032228`

## pseudocode

```c
char __fastcall SlbNatOptionalFindAndDeleteUnusedEntry(__int64 a1, _QWORD *a2, void ***a3, char a4)
{
  _QWORD *v6; // r13
  __int64 v7; // rbx
  __int16 v8; // r15
  size_t v9; // rbp
  char v10; // bl
  int v11; // r8d
  void ***v12; // rbx
  int v13; // r8d
  void **v14; // rax
  void **v15; // rcx
  int v17; // [rsp+28h] [rbp-70h]
  char v18; // [rsp+40h] [rbp-58h] BYREF
  char v19; // [rsp+41h] [rbp-57h]
  _OWORD v20[5]; // [rsp+48h] [rbp-50h] BYREF

  v19 = a4;
  v20[0] = 0;
  v18 = 0;
  v6 = (_QWORD *)(a1 + 24);
  while ( 1 )
  {
    if ( a2 == v6 )
      return 0;
    v7 = a2[10];
    if ( v7 )
    {
      v8 = *((_WORD *)a2 + 26);
      v9 = 4;
      if ( v8 != 2 )
        v9 = 16;
      if ( !memcmp(a3 + 7, a2 + 7, v9) )
      {
        v10 = *(_BYTE *)(v7 + 32);
        if ( *((_BYTE *)a3[10] + 32) == v10 )
        {
          memmove(v20, a2 + 7, v9);
          v11 = 4;
          LOBYTE(v17) = v10;
          if ( v8 != 2 )
            v11 = 16;
          if ( (int)WinNatLibDeterminePortUsage(
                      (_DWORD)qword_1400273D8,
                      (unsigned int)v20,
                      v11,
                      *((unsigned __int16 *)a2 + 36),
                      *((_WORD *)a2 + 37),
                      v17,
                      (__int64)&v18) >= 0 )
          {
            if ( v19 )
            {
              if ( v18 )
                goto LABEL_22;
              v12 = (void ***)a2;
            }
            else
            {
              v12 = a3;
            }
            if ( v12 )
            {
              v13 = 4;
              if ( *((_WORD *)v12 + 26) != 2 )
                v13 = 16;
              if ( (int)WinNatLibTryDisableAddress(
                          (_DWORD)qword_1400273D8,
                          (unsigned int)v20,
                          v13,
                          *((unsigned __int16 *)v12 + 36),
                          *((_WORD *)v12 + 37)) >= 0 )
                break;
            }
          }
        }
      }
    }
LABEL_22:
    a2 = (_QWORD *)*a2;
  }
  v14 = *v12;
  if ( (*v12)[1] != v12 || (v15 = v12[1], *v15 != v12) )
    __fastfail(3u);
  *v15 = v14;
  v14[1] = v15;
  SlbNatDeleteExternalAddress(v12);
  return 1;
}

```

## disassembly

```asm
0x140015478  mov     [rsp+arg_18], rbx
0x14001547d  push    rbp
0x14001547e  push    rsi
0x14001547f  push    rdi
0x140015480  push    r12
0x140015482  push    r13
0x140015484  push    r14
0x140015486  push    r15
0x140015488  sub     rsp, 60h
0x14001548c  xorps   xmm0, xmm0
0x14001548f  mov     [rsp+98h+var_57], r9b
0x140015494  movups  [rsp+98h+var_50], xmm0
0x140015499  mov     rsi, r8
0x14001549c  mov     [rsp+98h+var_58], 0
0x1400154a1  mov     rdi, rdx
0x1400154a4  lea     r13, [rcx+18h]
0x1400154a8  mov     r14, rcx
0x1400154ab  mov     r12d, 10h
0x1400154b1  cmp     rdi, r13
0x1400154b4  jz      loc_1400155F0
0x1400154ba  mov     rbx, [rdi+50h]
0x1400154be  test    rbx, rbx
0x1400154c1  jz      loc_1400155E1
0x1400154c7  movzx   r15d, word ptr [rdi+34h]
0x1400154cc  lea     rcx, [rsi+38h]; Buf1
0x1400154d0  cmp     r15w, 2
0x1400154d5  lea     rdx, [rdi+38h]; Buf2
0x1400154d9  mov     ebp, 4
0x1400154de  cmovnz  rbp, r12
0x1400154e2  mov     r8, rbp; Size
0x1400154e5  call    memcmp
0x1400154ea  test    eax, eax
0x1400154ec  jnz     loc_1400155DB
0x1400154f2  mov     rax, [rsi+50h]
0x1400154f6  mov     bl, [rbx+20h]
0x1400154f9  cmp     [rax+20h], bl
0x1400154fc  jnz     loc_1400155DB
0x140015502  mov     r8, rbp; Size
0x140015505  lea     rdx, [rdi+38h]; Src
0x140015509  lea     rcx, [rsp+98h+var_50]; void *
0x14001550e  call    memmove
0x140015513  movzx   r9d, word ptr [rdi+48h]
0x140015518  lea     rax, [rsp+98h+var_58]
0x14001551d  mov     rcx, cs:qword_1400273D8
0x140015524  lea     rdx, [rsp+98h+var_50]
0x140015529  mov     [rsp+98h+var_68], rax
0x14001552e  mov     r8d, 4
0x140015534  movzx   eax, word ptr [rdi+4Ah]
0x140015538  cmp     r15w, 2
0x14001553d  mov     [rsp+98h+var_70], bl
0x140015541  mov     [rsp+98h+var_78], ax
0x140015546  lea     r12d, [r8+0Ch]
0x14001554a  cmovnz  r8d, r12d
0x14001554e  call    WinNatLibDeterminePortUsage
0x140015553  test    eax, eax
0x140015555  js      loc_1400155E1
0x14001555b  cmp     [rsp+98h+var_57], 0
0x140015560  jnz     short loc_140015567
0x140015562  mov     rbx, rsi
0x140015565  jmp     short loc_140015571
0x140015567  cmp     [rsp+98h+var_58], 0
0x14001556c  jnz     short loc_1400155E1
0x14001556e  mov     rbx, rdi
0x140015571  test    rbx, rbx
0x140015574  jz      short loc_1400155E1
0x140015576  mov     rax, [rdi+50h]
0x14001557a  lea     rdx, [rsp+98h+var_50]
0x14001557f  cmp     word ptr [rbx+34h], 2
0x140015584  mov     r8d, 4
0x14001558a  movzx   r9d, word ptr [rbx+48h]
0x14001558f  mov     rcx, cs:qword_1400273D8
0x140015596  cmovnz  r8d, r12d
0x14001559a  mov     al, [rax+20h]
0x14001559d  mov     [rsp+98h+var_70], al
0x1400155a1  movzx   eax, word ptr [rbx+4Ah]
0x1400155a5  mov     [rsp+98h+var_78], ax
0x1400155aa  call    WinNatLibTryDisableAddress
0x1400155af  test    eax, eax
0x1400155b1  js      short loc_1400155E1
0x1400155b3  mov     rax, [rbx]
0x1400155b6  cmp     [rax+8], rbx
0x1400155ba  jnz     short loc_1400155E9
0x1400155bc  mov     rcx, [rbx+8]
0x1400155c0  cmp     [rcx], rbx
0x1400155c3  jnz     short loc_1400155E9
0x1400155c5  mov     [rcx], rax
0x1400155c8  mov     rdx, r14
0x1400155cb  mov     [rax+8], rcx
0x1400155cf  mov     rcx, rbx; P
0x1400155d2  call    SlbNatDeleteExternalAddress
0x1400155d7  mov     al, 1
0x1400155d9  jmp     short loc_1400155F2
0x1400155db  mov     r12d, 10h
0x1400155e1  mov     rdi, [rdi]
0x1400155e4  jmp     loc_1400154B1
0x1400155e9  mov     ecx, 3
0x1400155ee  int     29h; Win8: RtlFailFast(ecx)
0x1400155f0  xor     al, al
0x1400155f2  mov     rbx, [rsp+98h+arg_18]
0x1400155fa  add     rsp, 60h
0x1400155fe  pop     r15
0x140015600  pop     r14
0x140015602  pop     r13
0x140015604  pop     r12
0x140015606  pop     rdi
0x140015607  pop     rsi
0x140015608  pop     rbp
0x140015609  retn
```
