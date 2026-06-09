# ProcessDedupBuffer

- ea: `0x1400365c4`
- end: `0x14003683f`
- name: `ProcessDedupBuffer`
- size: `635`
- prototype: `__int64 __fastcall(__int64, void *, UCHAR *, ULONG, UCHAR *pbSecret, __int64, unsigned int, unsigned int, unsigned __int64, unsigned int *, _QWORD *, _QWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140036850`

## callees

- `0x1400365c4`
- `0x1400375fc`

## import_xrefs

- `ksecdd!BCryptHashData` at `0x14003675c`
- `ksecdd!BCryptHashData` at `0x14003675c`
- `ksecdd!BCryptDestroyHash` at `0x140036783`
- `ksecdd!BCryptDestroyHash` at `0x140036783`
- `ksecdd!BCryptCreateHash` at `0x140036737`
- `ksecdd!BCryptCreateHash` at `0x140036737`

## pseudocode

```c
__int64 __fastcall ProcessDedupBuffer(
        __int64 a1,
        void *a2,
        UCHAR *a3,
        ULONG a4,
        UCHAR *pbSecret,
        __int64 a6,
        unsigned int a7,
        unsigned int a8,
        unsigned __int64 a9,
        unsigned int *a10,
        _QWORD *a11,
        _QWORD *a12,
        _DWORD *a13)
{
  ULONG v13; // r11d
  UCHAR *v14; // rbx
  unsigned int v15; // ebp
  unsigned __int64 v16; // r10
  __int64 v17; // rax
  unsigned __int64 v18; // rdi
  unsigned int v19; // r12d
  __int64 v20; // rsi
  __int64 v21; // r8
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  unsigned int v24; // r15d
  __int64 v25; // r14
  unsigned int v26; // ebx
  unsigned int i; // r9d
  __int64 v28; // rax
  __int64 v29; // rcx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-58h] BYREF
  int v32; // [rsp+A0h] [rbp+8h]

  v13 = a4;
  v14 = a3;
  v15 = a7 - 1;
  if ( a7 - 1 > 0x3C3C3C2 )
    return (unsigned int)-1073741811;
  v16 = a9 + a8;
  if ( v16 < a9 )
    return (unsigned int)-1073741811;
  v17 = *a10;
  v18 = a9 + v17 + 68 * v15 + 24;
  if ( v18 + 68 < v18 )
    return (unsigned int)-2147483643;
  if ( v18 + 68 > v16 )
    return (unsigned int)-2147483643;
  v19 = 68 * v15 + 24 + v17 + 68;
  if ( v19 > a8 )
    return (unsigned int)-2147483643;
  v20 = v17 + a9;
  if ( a11 )
  {
    v21 = *(_QWORD *)(v20 + 8);
    *a11 = v21;
    if ( a12 )
      *a12 = *(_QWORD *)(56LL * v15 + v20 + 8) + *(_QWORD *)(56LL * v15 + v20 + 16) - v21;
  }
  if ( a13 )
  {
    v22 = *(_QWORD *)(v20 + 8);
    if ( *a11 >= v22 )
    {
      v23 = *a11 - v22;
      if ( v23 <= 0xFFFFFFF )
      {
        *a13 = v23;
        goto LABEL_13;
      }
    }
    return (unsigned int)-1073741675;
  }
LABEL_13:
  v24 = 0;
  while ( v24 < a7 )
  {
    v25 = 56LL * v15;
    if ( *(__int64 *)(v25 + v20 + 16) > 0xFFFFFFFFLL )
      return (unsigned int)-1073741675;
    v32 = *(_DWORD *)(v25 + v20 + 16);
    phHash = 0;
    v26 = BCryptCreateHash(a2, &phHash, v14, v13, pbSecret, 0x20u, 0);
    if ( !v26 )
    {
      v26 = BCryptHashData(phHash, (PUCHAR)(v25 + v20 + 24), 0x20u, 0);
      if ( !v26 )
        v26 = DeDupFinishHash(phHash, (_OWORD *)(v18 + 36));
    }
    BCryptDestroyHash(phHash);
    if ( v26 )
      return v26;
    for ( i = 0; i < 0x20; ++i )
    {
      v28 = 31 - i;
      v29 = 35 - i;
      *(_BYTE *)(v29 + v18) = *(_BYTE *)(v28 + v25 + v20 + 24);
    }
    v13 = a4;
    v14 = a3;
    ++v24;
    *(_BYTE *)(v18 + 2) = BYTE1(v32);
    *(_BYTE *)(v18 + 3) = v32;
    *(_BYTE *)(v18 + 1) = BYTE2(v32);
    *(_BYTE *)v18 = HIBYTE(v32);
    v18 -= 68LL;
    --v15;
  }
  *a10 = v19;
  return 0;
}

```

## disassembly

```asm
0x1400365c4  mov     rax, rsp
0x1400365c7  mov     [rax+20h], r9d
0x1400365cb  mov     [rax+18h], r8
0x1400365cf  mov     [rax+10h], rdx
0x1400365d3  mov     [rax+8], ecx
0x1400365d6  push    rbx
0x1400365d7  push    rbp
0x1400365d8  push    rsi
0x1400365d9  push    rdi
0x1400365da  push    r12
0x1400365dc  push    r13
0x1400365de  push    r14
0x1400365e0  push    r15
0x1400365e2  sub     rsp, 58h
0x1400365e6  mov     r13d, [rsp+98h+arg_30]
0x1400365ee  mov     r11d, r9d
0x1400365f1  mov     rbx, r8
0x1400365f4  lea     ebp, [r13-1]
0x1400365f8  cmp     ebp, 3C3C3C2h
0x1400365fe  ja      loc_140036826
0x140036604  mov     rcx, [rsp+98h+arg_40]
0x14003660c  mov     r10d, [rsp+98h+arg_38]
0x140036614  add     r10, rcx
0x140036617  cmp     r10, rcx
0x14003661a  jb      loc_140036826
0x140036620  mov     r9, [rsp+98h+arg_48]
0x140036628  imul    r8d, ebp, 44h ; 'D'
0x14003662c  mov     eax, [r9]
0x14003662f  add     r8d, 18h
0x140036633  mov     edi, r8d
0x140036636  add     rdi, rax
0x140036639  add     rdi, rcx
0x14003663c  lea     rdx, [rdi+44h]
0x140036640  cmp     rdx, rdi
0x140036643  jb      loc_14003681F
0x140036649  cmp     rdx, r10
0x14003664c  ja      loc_14003681F
0x140036652  lea     r12d, [rax+44h]
0x140036656  add     r12d, r8d
0x140036659  cmp     r12d, [rsp+98h+arg_38]
0x140036661  ja      loc_14003681F
0x140036667  mov     rdx, [rsp+98h+arg_50]
0x14003666f  lea     rsi, [rax+rcx]
0x140036673  test    rdx, rdx
0x140036676  jz      short loc_1400366A2
0x140036678  mov     r9, [rsp+98h+arg_58]
0x140036680  mov     r8, [rsi+8]
0x140036684  mov     [rdx], r8
0x140036687  test    r9, r9
0x14003668a  jz      short loc_1400366A2
0x14003668c  mov     eax, ebp
0x14003668e  imul    rcx, rax, 38h ; '8'
0x140036692  mov     rax, [rcx+rsi+10h]
0x140036697  add     rax, [rcx+rsi+8]
0x14003669c  sub     rax, r8
0x14003669f  mov     [r9], rax
0x1400366a2  mov     rcx, [rsp+98h+arg_60]
0x1400366aa  test    rcx, rcx
0x1400366ad  jz      short loc_1400366D0
0x1400366af  mov     rax, [rdx]
0x1400366b2  mov     rdx, [rsi+8]
0x1400366b6  cmp     rax, rdx
0x1400366b9  jl      loc_140036809
0x1400366bf  sub     rax, rdx
0x1400366c2  cmp     rax, 0FFFFFFFh
0x1400366c8  ja      loc_140036809
0x1400366ce  mov     [rcx], eax
0x1400366d0  xor     r15d, r15d
0x1400366d3  mov     ecx, 0FFFFFFFFh
0x1400366d8  cmp     r15d, r13d
0x1400366db  jnb     loc_140036810
0x1400366e1  mov     eax, ebp
0x1400366e3  imul    r14, rax, 38h ; '8'
0x1400366e7  cmp     [r14+rsi+10h], rcx
0x1400366ec  jg      loc_140036809
0x1400366f2  mov     eax, [r14+rsi+10h]
0x1400366f7  lea     rdx, [rsp+98h+phHash]; phHash
0x1400366fc  mov     rcx, [rsp+98h+hAlgorithm]; hAlgorithm
0x140036704  mov     r9d, r11d; cbHashObject
0x140036707  mov     [rsp+98h+arg_0], eax
0x14003670e  mov     r8, rbx; pbHashObject
0x140036711  mov     rax, [rsp+98h+arg_20]
0x140036719  mov     [rsp+98h+dwFlags], 0; dwFlags
0x140036721  mov     [rsp+98h+cbSecret], 20h ; ' '; cbSecret
0x140036729  mov     [rsp+98h+pbSecret], rax; pbSecret
0x14003672e  mov     [rsp+98h+phHash], 0
0x140036737  call    cs:__imp_BCryptCreateHash
0x14003673e  nop     dword ptr [rax+rax+00h]
0x140036743  mov     ebx, eax
0x140036745  test    eax, eax
0x140036747  jnz     short loc_14003677E
0x140036749  mov     rcx, [rsp+98h+phHash]; hHash
0x14003674e  lea     rdx, [rsi+18h]
0x140036752  add     rdx, r14; pbInput
0x140036755  lea     r8d, [rax+20h]; cbInput
0x140036759  xor     r9d, r9d; dwFlags
0x14003675c  call    cs:__imp_BCryptHashData
0x140036763  nop     dword ptr [rax+rax+00h]
0x140036768  mov     ebx, eax
0x14003676a  test    eax, eax
0x14003676c  jnz     short loc_14003677E
0x14003676e  mov     rcx, [rsp+98h+phHash]
0x140036773  lea     rdx, [rdi+24h]
0x140036777  call    DeDupFinishHash
0x14003677c  mov     ebx, eax
0x14003677e  mov     rcx, [rsp+98h+phHash]; hHash
0x140036783  call    cs:__imp_BCryptDestroyHash
0x14003678a  nop     dword ptr [rax+rax+00h]
0x14003678f  test    ebx, ebx
0x140036791  jnz     loc_14003682B
0x140036797  mov     r8d, [rsp+98h+arg_0]
0x14003679f  lea     r10, [r14+rsi]
0x1400367a3  xor     r9d, r9d
0x1400367a6  mov     eax, 1Fh
0x1400367ab  mov     ecx, 23h ; '#'
0x1400367b0  sub     eax, r9d
0x1400367b3  sub     ecx, r9d
0x1400367b6  inc     r9d
0x1400367b9  mov     al, [rax+r10+18h]
0x1400367be  mov     [rcx+rdi], al
0x1400367c1  cmp     r9d, 20h ; ' '
0x1400367c5  jb      short loc_1400367A6
0x1400367c7  mov     r11d, [rsp+98h+arg_18]
0x1400367cf  mov     rax, r8
0x1400367d2  mov     rbx, [rsp+98h+arg_10]
0x1400367da  inc     r15d
0x1400367dd  shr     rax, 8
0x1400367e1  mov     ecx, 0FFFFFFFFh
0x1400367e6  mov     [rdi+2], al
0x1400367e9  mov     rax, r8
0x1400367ec  mov     [rdi+3], r8b
0x1400367f0  shr     rax, 10h
0x1400367f4  shr     r8, 18h
0x1400367f8  mov     [rdi+1], al
0x1400367fb  mov     [rdi], r8b
0x1400367fe  sub     rdi, 44h ; 'D'
0x140036802  add     ebp, ecx
0x140036804  jmp     loc_1400366D8
0x140036809  mov     ebx, 0C0000095h
0x14003680e  jmp     short loc_14003682B
0x140036810  mov     rax, [rsp+98h+arg_48]
0x140036818  mov     [rax], r12d
0x14003681b  xor     eax, eax
0x14003681d  jmp     short loc_14003682D
0x14003681f  mov     ebx, 80000005h
0x140036824  jmp     short loc_14003682B
0x140036826  mov     ebx, 0C000000Dh
0x14003682b  mov     eax, ebx
0x14003682d  add     rsp, 58h
0x140036831  pop     r15
0x140036833  pop     r14
0x140036835  pop     r13
0x140036837  pop     r12
0x140036839  pop     rdi
0x14003683a  pop     rsi
0x14003683b  pop     rbp
0x14003683c  pop     rbx
0x14003683d  retn
```
