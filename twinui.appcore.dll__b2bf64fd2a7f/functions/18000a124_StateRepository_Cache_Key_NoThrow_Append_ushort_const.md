# StateRepository::Cache::Key_NoThrow::Append(ushort const *)

- ea: `0x18000a124`
- end: `0x18000a32c`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `520`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001c214`

## callees

- `0x18000a124`
- `0x18000a334`
- `0x18001cc38`
- `0x18002e495`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a236`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a236`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000a1c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000a1c6`

## string_xrefs

- `0x18000a183`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000a1d9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000a1fc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // r14
  unsigned __int64 v6; // rbp
  __int64 v7; // rbx
  const unsigned __int16 *i; // rcx
  __int64 v9; // rdx
  __int64 v10; // rax
  unsigned __int64 v12; // rsi
  void *v13; // rax
  void *v14; // r15
  HRESULT v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  _WORD *v21; // rax
  unsigned __int64 v22; // rax
  _WORD *v23; // rcx
  unsigned __int64 j; // rdx
  int cchToCopy; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v4 = a2;
  if ( a2 )
  {
    v6 = 0;
    v7 = 0;
    for ( i = a2; ; ++i )
    {
      v9 = *i;
      if ( !(_WORD)v9 )
        break;
      if ( ++v6 >= 0x7FFFFFFF )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          cchToCopy);
        return 2147942487LL;
      }
      v10 = v7 + 1;
      if ( (_WORD)v9 != 94 )
        v10 = v7;
      v7 = v10;
    }
    v12 = v6 + v7 + *((_QWORD *)this + 65) + 1LL;
    if ( v12 <= *((_QWORD *)this + 66) )
    {
      v12 = *((_QWORD *)this + 66);
    }
    else
    {
      v13 = (void *)SRCache_AllocStringBuffer((unsigned int)v12, v9, a3, a4);
      v14 = v13;
      if ( !v13 )
      {
        v15 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x193,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x8007000ELL,
          cchToCopy);
        v16 = 310;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v16,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v15,
          cchToCopy);
        return (unsigned int)v15;
      }
      memcpy_0(v13, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v18 = *(_QWORD *)this;
      *(_QWORD *)this = v14;
      if ( v18 )
        SRCache_Free(v18, v17);
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v12;
    }
    v19 = *((_QWORD *)this + 67);
    if ( v7 )
    {
      v23 = (_WORD *)(v19 + 2LL * *((_QWORD *)this + 65));
      for ( j = 0; j < v6; ++v23 )
      {
        if ( *v4 == 94 )
          *v23++ = 94;
        ++j;
        *v23 = *v4++;
      }
      *v23 = 0;
    }
    else
    {
      if ( v12 - 1 > 0x7FFFFFFE )
      {
        v15 = -2147024809;
LABEL_29:
        v16 = 313;
        goto LABEL_12;
      }
      v20 = v12;
      v21 = (_WORD *)*((_QWORD *)this + 67);
      do
      {
        if ( !*v21 )
          break;
        ++v21;
        --v20;
      }
      while ( v20 );
      v15 = v20 == 0 ? 0x80070057 : 0;
      if ( v20 )
        v22 = v12 - v20;
      else
        v22 = 0;
      if ( !v20 )
        goto LABEL_29;
      v15 = StringCopyWorkerW((STRSAFE_LPWSTR)(v19 + 2 * v22), v12 - v22, (size_t *)0x7FFFFFFE, v4, 0x7FFFFFFEu);
      if ( v15 < 0 )
        goto LABEL_29;
    }
    *((_QWORD *)this + 65) += v6;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a124  push    rbx
0x18000a126  push    rbp
0x18000a127  push    rsi
0x18000a128  push    rdi
0x18000a129  push    r12
0x18000a12b  push    r13
0x18000a12d  push    r14
0x18000a12f  push    r15
0x18000a131  sub     rsp, 38h
0x18000a135  xor     r12d, r12d
0x18000a138  mov     r14, rdx
0x18000a13b  mov     rdi, rcx
0x18000a13e  test    rdx, rdx
0x18000a141  jz      loc_18000A319
0x18000a147  mov     ebp, r12d
0x18000a14a  lea     r13d, [r12+5Eh]
0x18000a14f  mov     ebx, r12d
0x18000a152  mov     rcx, rdx
0x18000a155  movzx   edx, word ptr [rcx]
0x18000a158  test    dx, dx
0x18000a15b  jz      short loc_18000A1A4
0x18000a15d  inc     rbp
0x18000a160  cmp     rbp, 7FFFFFFFh
0x18000a167  jnb     short loc_18000A17E
0x18000a169  lea     rax, [rbx+1]
0x18000a16d  add     rcx, 2
0x18000a171  cmp     dx, r13w
0x18000a175  cmovnz  rax, rbx
0x18000a179  mov     rbx, rax
0x18000a17c  jmp     short loc_18000A155
0x18000a17e  mov     rcx, [rsp+78h]; this
0x18000a183  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a18a  mov     r9d, 80070057h; char *
0x18000a190  mov     edx, 135h; void *
0x18000a195  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a19a  mov     eax, 80070057h
0x18000a19f  jmp     loc_18000A31B
0x18000a1a4  mov     rsi, [rdi+208h]
0x18000a1ab  mov     rax, [rdi+210h]
0x18000a1b2  inc     rsi
0x18000a1b5  add     rsi, rbx
0x18000a1b8  add     rsi, rbp
0x18000a1bb  cmp     rsi, rax
0x18000a1be  jbe     loc_18000A24F
0x18000a1c4  mov     ecx, esi
0x18000a1c6  call    cs:__imp_SRCache_AllocStringBuffer
0x18000a1cc  mov     r15, rax
0x18000a1cf  test    rax, rax
0x18000a1d2  jnz     short loc_18000A212
0x18000a1d4  mov     rcx, [rsp+78h]; this
0x18000a1d9  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a1e0  mov     ebx, 8007000Eh
0x18000a1e5  mov     edx, 193h; void *
0x18000a1ea  mov     r9d, ebx; char *
0x18000a1ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1f2  mov     edx, 136h; void *
0x18000a1f7  mov     rcx, [rsp+78h]; this
0x18000a1fc  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000a203  mov     r9d, ebx; char *
0x18000a206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a20b  mov     eax, ebx
0x18000a20d  jmp     loc_18000A31B
0x18000a212  mov     r8, [rdi+210h]
0x18000a219  mov     rcx, r15; void *
0x18000a21c  mov     rdx, [rdi+218h]; Src
0x18000a223  add     r8, r8; Size
0x18000a226  call    memcpy_0
0x18000a22b  mov     rcx, [rdi]
0x18000a22e  mov     [rdi], r15
0x18000a231  test    rcx, rcx
0x18000a234  jz      short loc_18000A23C
0x18000a236  call    cs:__imp_SRCache_Free
0x18000a23c  mov     rax, [rdi]
0x18000a23f  mov     [rdi+218h], rax
0x18000a246  mov     [rdi+210h], rsi
0x18000a24d  jmp     short loc_18000A252
0x18000a24f  mov     rsi, rax
0x18000a252  mov     rdx, [rdi+218h]
0x18000a259  test    rbx, rbx
0x18000a25c  jnz     short loc_18000A2D6
0x18000a25e  lea     rax, [rsi-1]
0x18000a262  mov     r8d, 7FFFFFFEh; pcchNewDestLength
0x18000a268  cmp     rax, r8
0x18000a26b  ja      short loc_18000A2C7
0x18000a26d  mov     rcx, rsi
0x18000a270  mov     rax, rdx
0x18000a273  cmp     [rax], r12w
0x18000a277  jz      short loc_18000A283
0x18000a279  add     rax, 2
0x18000a27d  sub     rcx, 1
0x18000a281  jnz     short loc_18000A273
0x18000a283  mov     rax, rcx
0x18000a286  neg     rax
0x18000a289  sbb     ebx, ebx
0x18000a28b  not     ebx
0x18000a28d  and     ebx, 80070057h
0x18000a293  test    rcx, rcx
0x18000a296  jz      short loc_18000A2A0
0x18000a298  mov     rax, rsi
0x18000a29b  sub     rax, rcx
0x18000a29e  jmp     short loc_18000A2A3
0x18000a2a0  mov     rax, r12
0x18000a2a3  test    rcx, rcx
0x18000a2a6  jz      short loc_18000A2CC
0x18000a2a8  sub     rsi, rax
0x18000a2ab  mov     qword ptr [rsp+78h+cchToCopy], r8; cchToCopy
0x18000a2b0  lea     rcx, [rdx+rax*2]; pszDest
0x18000a2b4  mov     r9, r14; pszSrc
0x18000a2b7  mov     rdx, rsi; cchDest
0x18000a2ba  call    StringCopyWorkerW
0x18000a2bf  mov     ebx, eax
0x18000a2c1  test    eax, eax
0x18000a2c3  jns     short loc_18000A312
0x18000a2c5  jmp     short loc_18000A2CC
0x18000a2c7  mov     ebx, 80070057h
0x18000a2cc  mov     edx, 139h
0x18000a2d1  jmp     loc_18000A1F7
0x18000a2d6  mov     rax, [rdi+208h]
0x18000a2dd  lea     rcx, [rdx+rax*2]
0x18000a2e1  mov     rdx, r12
0x18000a2e4  test    rbp, rbp
0x18000a2e7  jz      short loc_18000A30E
0x18000a2e9  cmp     [r14], r13w
0x18000a2ed  jnz     short loc_18000A2F7
0x18000a2ef  mov     [rcx], r13w
0x18000a2f3  add     rcx, 2
0x18000a2f7  movzx   eax, word ptr [r14]
0x18000a2fb  inc     rdx
0x18000a2fe  mov     [rcx], ax
0x18000a301  add     r14, 2
0x18000a305  add     rcx, 2
0x18000a309  cmp     rdx, rbp
0x18000a30c  jb      short loc_18000A2E9
0x18000a30e  mov     [rcx], r12w
0x18000a312  add     [rdi+208h], rbp
0x18000a319  xor     eax, eax
0x18000a31b  add     rsp, 38h
0x18000a31f  pop     r15
0x18000a321  pop     r14
0x18000a323  pop     r13
0x18000a325  pop     r12
0x18000a327  pop     rdi
0x18000a328  pop     rsi
0x18000a329  pop     rbp
0x18000a32a  pop     rbx
0x18000a32b  retn
```
