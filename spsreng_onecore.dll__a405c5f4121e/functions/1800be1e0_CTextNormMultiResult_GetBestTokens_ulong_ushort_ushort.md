# CTextNormMultiResult::GetBestTokens(ulong *,ushort * * *,ushort * *)

- ea: `0x1800be1e0`
- end: `0x1800be30d`
- name: `?GetBestTokens@CTextNormMultiResult@@UEAAJPEAKPEAPEAPEAGPEAPEAG@Z`
- size: `301`
- prototype: `__int64 __fastcall(CTextNormMultiResult *__hidden this, unsigned int *, unsigned __int16 ***, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800040b8`
- `0x1800be1e0`
- `0x180102010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be28e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800be28e`

## pseudocode

```c
__int64 __fastcall CTextNormMultiResult::GetBestTokens(
        CTextNormMultiResult *this,
        unsigned int *a2,
        unsigned __int16 ***a3,
        unsigned __int16 **a4)
{
  int v8; // ebx
  __int64 v9; // rdi
  int v10; // r15d
  unsigned int v11; // edx
  int v12; // ecx
  unsigned int v13; // r15d
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // r14
  __int64 v17; // rdx
  unsigned int v18; // r8d
  __int64 v19; // rax

  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = (*(__int64 (__fastcall **)(CTextNormMultiResult *, __int64))(*(_QWORD *)this + 184LL))(this, 1);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(CTextNormMultiResult *, unsigned __int16 **))(*(_QWORD *)this + 24LL))(this, a4);
    if ( v8 >= 0 )
    {
      if ( *a4 )
      {
        v9 = -1;
        do
          ++v9;
        while ( (*a4)[v9] );
        if ( (_DWORD)v9 )
        {
          v10 = 0;
          v11 = 0;
          do
          {
            v12 = v10 + 1;
            if ( (*a4)[v11] != 32 )
              v12 = v10;
            ++v11;
            v10 = v12;
          }
          while ( v11 < (unsigned int)v9 );
          v13 = v12 + 1;
          v14 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)(v12 + 1));
          v15 = v14;
          if ( !v14 )
            return 2147942414LL;
          memset_0(v14, 0, 8LL * v13);
          v17 = 0;
          *v15 = *a4;
          v18 = 1;
          do
          {
            if ( v18 >= v13 )
              break;
            if ( (*a4)[v17] == 32 )
            {
              (*a4)[v17] = 0;
              v19 = v18++;
              v15[v19] = &(*a4)[v17 + 1];
            }
            v17 = (unsigned int)(v17 + 1);
          }
          while ( (unsigned int)v17 < (unsigned int)v9 );
          *a2 = v13;
          *a3 = v15;
        }
      }
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800be1e0  push    rbx
0x1800be1e2  push    rbp
0x1800be1e3  push    rsi
0x1800be1e4  push    rdi
0x1800be1e5  push    r12
0x1800be1e7  push    r13
0x1800be1e9  push    r14
0x1800be1eb  push    r15
0x1800be1ed  sub     rsp, 28h
0x1800be1f1  xor     ebp, ebp
0x1800be1f3  mov     r13, rdx
0x1800be1f6  mov     [rdx], ebp
0x1800be1f8  mov     rsi, r9
0x1800be1fb  mov     [r8], rbp
0x1800be1fe  mov     r12, r8
0x1800be201  mov     [r9], rbp
0x1800be204  mov     rdi, rcx
0x1800be207  mov     rax, [rcx]
0x1800be20a  lea     edx, [rbp+1]
0x1800be20d  mov     rax, [rax+0B8h]
0x1800be214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be219  mov     ebx, eax
0x1800be21b  test    eax, eax
0x1800be21d  js      loc_1800BE2FA
0x1800be223  mov     rax, [rdi]
0x1800be226  mov     rdx, rsi
0x1800be229  mov     rcx, rdi
0x1800be22c  mov     rax, [rax+18h]
0x1800be230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be235  mov     ebx, eax
0x1800be237  test    eax, eax
0x1800be239  js      loc_1800BE2FA
0x1800be23f  mov     rax, [rsi]
0x1800be242  test    rax, rax
0x1800be245  jz      loc_1800BE2FA
0x1800be24b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800be24f  inc     rdi
0x1800be252  cmp     [rax+rdi*2], bp
0x1800be256  jnz     short loc_1800BE24F
0x1800be258  test    edi, edi
0x1800be25a  jz      loc_1800BE2FA
0x1800be260  mov     r15d, ebp
0x1800be263  mov     edx, ebp
0x1800be265  mov     r8, rax
0x1800be268  mov     eax, edx
0x1800be26a  lea     ecx, [r15+1]
0x1800be26e  cmp     word ptr [r8+rax*2], 20h ; ' '
0x1800be274  cmovnz  ecx, r15d
0x1800be278  inc     edx
0x1800be27a  mov     r15d, ecx
0x1800be27d  cmp     edx, edi
0x1800be27f  jb      short loc_1800BE268
0x1800be281  inc     r15d
0x1800be284  mov     ebp, r15d
0x1800be287  shl     rbp, 3
0x1800be28b  mov     rcx, rbp; cb
0x1800be28e  call    cs:__imp_CoTaskMemAlloc
0x1800be294  mov     r14, rax
0x1800be297  test    rax, rax
0x1800be29a  jnz     short loc_1800BE2A3
0x1800be29c  mov     eax, 8007000Eh
0x1800be2a1  jmp     short loc_1800BE2FC
0x1800be2a3  mov     r8, rbp; Size
0x1800be2a6  xor     edx, edx; Val
0x1800be2a8  mov     rcx, r14; void *
0x1800be2ab  call    memset_0
0x1800be2b0  mov     rax, [rsi]
0x1800be2b3  xor     edx, edx
0x1800be2b5  mov     [r14], rax
0x1800be2b8  lea     r8d, [rdx+1]
0x1800be2bc  test    edi, edi
0x1800be2be  jz      short loc_1800BE2F2
0x1800be2c0  cmp     r8d, r15d
0x1800be2c3  jnb     short loc_1800BE2F2
0x1800be2c5  mov     r9, [rsi]
0x1800be2c8  cmp     word ptr [r9+rdx*2], 20h ; ' '
0x1800be2ce  jnz     short loc_1800BE2EC
0x1800be2d0  xor     eax, eax
0x1800be2d2  mov     [r9+rdx*2], ax
0x1800be2d7  mov     rax, [rsi]
0x1800be2da  add     rax, 2
0x1800be2de  lea     rcx, [rax+rdx*2]
0x1800be2e2  mov     eax, r8d
0x1800be2e5  inc     r8d
0x1800be2e8  mov     [r14+rax*8], rcx
0x1800be2ec  inc     edx
0x1800be2ee  cmp     edx, edi
0x1800be2f0  jb      short loc_1800BE2C0
0x1800be2f2  mov     [r13+0], r15d
0x1800be2f6  mov     [r12], r14
0x1800be2fa  mov     eax, ebx
0x1800be2fc  add     rsp, 28h
0x1800be300  pop     r15
0x1800be302  pop     r14
0x1800be304  pop     r13
0x1800be306  pop     r12
0x1800be308  pop     rdi
0x1800be309  pop     rsi
0x1800be30a  pop     rbp
0x1800be30b  pop     rbx
0x1800be30c  retn
```
