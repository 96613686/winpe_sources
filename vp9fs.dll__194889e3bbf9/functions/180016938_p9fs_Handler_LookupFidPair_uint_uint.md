# p9fs::Handler::LookupFidPair(uint,uint)

- ea: `0x180016938`
- end: `0x180016ad1`
- name: `?LookupFidPair@Handler@p9fs@@AEAA?AU?$pair@V?$shared_ptr@VFid@p9fs@@@std@@V12@@std@@II@Z`
- size: `409`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001226c`
- `0x180013da8`
- `0x180013ec4`

## callees

- `0x1800030c0`
- `0x1800030e0`
- `0x180016938`
- `0x18001c75c`

## string_xrefs

- `0x180016aa1`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`
- `0x180016abc`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall p9fs::Handler::LookupFidPair(__int64 a1, _QWORD *a2, unsigned int a3, unsigned int a4)
{
  _Smtx_t *v8; // r14
  __int64 *v9; // rdx
  __int64 *v10; // r9
  __int64 *v11; // rcx
  __int64 *v12; // r8
  __int64 *v13; // rax
  char v14; // al
  __int64 *v15; // r8
  __int64 *v16; // rax
  char v17; // al
  __int64 v18; // rax
  __int64 v19; // rax
  int v21; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v8 = (_Smtx_t *)(a1 + 32);
  Smtx_lock_shared((_Smtx_t *)(a1 + 32));
  v9 = *(__int64 **)(a1 + 40);
  v10 = (__int64 *)v9[1];
  v11 = v9;
  v12 = v10;
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v12 + 8) >= a3 )
        v11 = v12;
      v13 = v12 + 2;
      if ( *((_DWORD *)v12 + 8) >= a3 )
        v13 = v12;
      v12 = (__int64 *)*v13;
    }
    while ( !*(_BYTE *)(*v13 + 25) );
  }
  if ( *((_BYTE *)v11 + 25) || a3 < *((_DWORD *)v11 + 8) )
  {
    v11 = *(__int64 **)(a1 + 40);
  }
  else if ( v11 != v9 )
  {
    v14 = 0;
    goto LABEL_13;
  }
  v14 = 1;
LABEL_13:
  if ( v14 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x574,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0x8000FFFFLL,
      v21);
  v15 = *(__int64 **)(a1 + 40);
  if ( !*((_BYTE *)v10 + 25) )
  {
    do
    {
      if ( *((_DWORD *)v10 + 8) >= a4 )
        v15 = v10;
      v16 = v10 + 2;
      if ( *((_DWORD *)v10 + 8) >= a4 )
        v16 = v10;
      v10 = (__int64 *)*v16;
    }
    while ( !*(_BYTE *)(*v16 + 25) );
  }
  if ( *((_BYTE *)v15 + 25) || a4 < *((_DWORD *)v15 + 8) )
  {
    v15 = *(__int64 **)(a1 + 40);
  }
  else if ( v15 != v9 )
  {
    v17 = 0;
    goto LABEL_26;
  }
  v17 = 1;
LABEL_26:
  if ( v17 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x576,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
      (const char *)0x8000FFFFLL,
      v21);
  *a2 = 0;
  a2[1] = 0;
  v18 = v11[6];
  if ( v18 )
    _InterlockedIncrement((volatile signed __int32 *)(v18 + 8));
  *a2 = v11[5];
  a2[1] = v11[6];
  a2[2] = 0;
  a2[3] = 0;
  v19 = v15[6];
  if ( v19 )
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
  a2[2] = v15[5];
  a2[3] = v15[6];
  Smtx_unlock_shared(v8);
  return a2;
}

```

## disassembly

```asm
0x180016938  mov     rax, rsp
0x18001693b  mov     [rax+18h], rbx
0x18001693f  mov     [rax+20h], rbp
0x180016943  mov     [rax+10h], rdx
0x180016947  push    rsi
0x180016948  push    rdi
0x180016949  push    r14
0x18001694b  sub     rsp, 50h
0x18001694f  mov     ebp, r9d
0x180016952  mov     esi, r8d
0x180016955  mov     rdi, rdx
0x180016958  mov     rbx, rcx
0x18001695b  mov     [rsp+68h+var_40], rdx
0x180016960  xorps   xmm0, xmm0
0x180016963  movups  xmmword ptr [rax-40h], xmm0
0x180016967  lea     r14, [rcx+20h]
0x18001696b  mov     [rax-40h], r14
0x18001696f  mov     byte ptr [rax-38h], 1
0x180016973  mov     rcx, r14; _Smtx_t *
0x180016976  call    _Smtx_lock_shared
0x18001697b  nop
0x18001697c  mov     rdx, [rbx+28h]
0x180016980  mov     r9, [rdx+8]
0x180016984  xor     eax, eax
0x180016986  mov     [rsp+68h+var_24], eax
0x18001698a  mov     rcx, rdx
0x18001698d  mov     r8, r9
0x180016990  cmp     [r9+19h], al
0x180016994  jnz     short loc_1800169B0
0x180016996  cmp     [r8+20h], esi
0x18001699a  cmovnb  rcx, r8
0x18001699e  lea     rax, [r8+10h]
0x1800169a2  cmovnb  rax, r8
0x1800169a6  mov     r8, [rax]
0x1800169a9  cmp     byte ptr [r8+19h], 0
0x1800169ae  jz      short loc_180016996
0x1800169b0  cmp     byte ptr [rcx+19h], 0
0x1800169b4  jnz     short loc_1800169C4
0x1800169b6  cmp     esi, [rcx+20h]
0x1800169b9  jb      short loc_1800169C4
0x1800169bb  cmp     rcx, rdx
0x1800169be  jz      short loc_1800169C7
0x1800169c0  xor     al, al
0x1800169c2  jmp     short loc_1800169C9
0x1800169c4  mov     rcx, rdx
0x1800169c7  mov     al, 1
0x1800169c9  mov     r10, [rsp+68h]
0x1800169ce  test    al, al
0x1800169d0  jnz     loc_180016AB6
0x1800169d6  xor     eax, eax
0x1800169d8  mov     [rsp+68h+var_24], eax
0x1800169dc  mov     r8, rdx
0x1800169df  cmp     [r9+19h], al
0x1800169e3  jnz     short loc_1800169FF
0x1800169e5  cmp     [r9+20h], ebp
0x1800169e9  cmovnb  r8, r9
0x1800169ed  lea     rax, [r9+10h]
0x1800169f1  cmovnb  rax, r9
0x1800169f5  mov     r9, [rax]
0x1800169f8  cmp     byte ptr [r9+19h], 0
0x1800169fd  jz      short loc_1800169E5
0x1800169ff  cmp     byte ptr [r8+19h], 0
0x180016a04  jnz     short loc_180016A15
0x180016a06  cmp     ebp, [r8+20h]
0x180016a0a  jb      short loc_180016A15
0x180016a0c  cmp     r8, rdx
0x180016a0f  jz      short loc_180016A18
0x180016a11  xor     al, al
0x180016a13  jmp     short loc_180016A1A
0x180016a15  mov     r8, rdx
0x180016a18  mov     al, 1
0x180016a1a  mov     r10, [rsp+68h]
0x180016a1f  test    al, al
0x180016a21  jnz     short loc_180016A9B
0x180016a23  mov     qword ptr [rdi], 0
0x180016a2a  mov     qword ptr [rdi+8], 0
0x180016a32  mov     rax, [rcx+30h]
0x180016a36  test    rax, rax
0x180016a39  jz      short loc_180016A3F
0x180016a3b  lock inc dword ptr [rax+8]
0x180016a3f  mov     rax, [rcx+28h]
0x180016a43  mov     [rdi], rax
0x180016a46  mov     rax, [rcx+30h]
0x180016a4a  mov     [rdi+8], rax
0x180016a4e  mov     qword ptr [rdi+10h], 0
0x180016a56  mov     qword ptr [rdi+18h], 0
0x180016a5e  mov     rax, [r8+30h]
0x180016a62  test    rax, rax
0x180016a65  jz      short loc_180016A6B
0x180016a67  lock inc dword ptr [rax+8]
0x180016a6b  mov     rdx, [r8+28h]
0x180016a6f  mov     [rdi+10h], rdx
0x180016a73  mov     rdx, [r8+30h]
0x180016a77  mov     [rdi+18h], rdx
0x180016a7b  mov     rcx, r14; _Smtx_t *
0x180016a7e  call    _Smtx_unlock_shared
0x180016a83  mov     rax, rdi
0x180016a86  lea     r11, [rsp+68h+var_18]
0x180016a8b  mov     rbx, [r11+30h]
0x180016a8f  mov     rbp, [r11+38h]
0x180016a93  mov     rsp, r11
0x180016a96  pop     r14
0x180016a98  pop     rdi
0x180016a99  pop     rsi
0x180016a9a  retn
0x180016a9b  mov     r9d, 8000FFFFh; char *
0x180016aa1  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016aa8  mov     edx, 576h; void *
0x180016aad  mov     rcx, r10; this
0x180016ab0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180016ab6  mov     r9d, 8000FFFFh; char *
0x180016abc  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180016ac3  mov     edx, 574h; void *
0x180016ac8  mov     rcx, r10; this
0x180016acb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
