# CQueryKnownGameList::ValidateKGL(ulong)

- ea: `0x180022800`
- end: `0x180022c0c`
- name: `?ValidateKGL@CQueryKnownGameList@@AEAAJK@Z`
- size: `1036`
- prototype: `__int64 __fastcall(CQueryKnownGameList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180021c70`

## callees

- `0x180022800`
- `0x1800237c8`
- `0x180356360`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180022b22`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180022b33`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180022b22`
- `api-ms-win-crt-private-l1-1-0!_o__towlower_l` at `0x180022b33`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180022b45`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180022bea`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180022b45`
- `api-ms-win-crt-private-l1-1-0!_o__free_locale` at `0x180022bea`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180022b00`
- `api-ms-win-crt-private-l1-1-0!_o__create_locale` at `0x180022b00`

## string_xrefs

- `0x180022828`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x18002284b`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800228ae`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800228d9`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022915`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022943`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022982`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800229b8`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x1800229f1`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022a80`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022aa8`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022ac4`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022b69`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022b89`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022bc0`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`
- `0x180022bf5`: `onecoreuap\shell\twinui\broadcastdvrcomponent\kgl\lib\knowngamelist.cpp`

## pseudocode

```c
__int64 __fastcall CQueryKnownGameList::ValidateKGL(CQueryKnownGameList *this, unsigned int a2)
{
  wil::details::in1diag3 *v5; // rcx
  __int64 v6; // rdx
  unsigned int v7; // edx
  unsigned int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // r13d
  unsigned int i; // ebx
  __int64 v13; // rax
  int v14; // eax
  unsigned int v15; // edi
  __int64 v16; // rax
  int v17; // edi
  __int64 v18; // rbp
  struct localeinfo_struct *locale; // r15
  int v20; // edi
  wint_t v21; // ax
  __int64 v22; // [rsp+20h] [rbp-48h]
  __int128 v23; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*((_DWORD *)this + 10) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x328,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  v7 = *((_DWORD *)this + 11);
  if ( v7 >= a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x329,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  v8 = *((_DWORD *)this + 12);
  if ( v8 >= a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x32A,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  v9 = *((_DWORD *)this + 9);
  v10 = *((_DWORD *)this + 13);
  if ( v9 == 5 )
  {
    if ( v10 != 16 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32E,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
LABEL_13:
    if ( *((_DWORD *)this + 15) > 2u )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x339,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
    goto LABEL_16;
  }
  if ( v10 < 0x10 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x333,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  if ( v9 >= 2 )
    goto LABEL_13;
LABEL_16:
  if ( v9 >= 3 && (unsigned __int16)(*((_WORD *)this + 33) - 1) > 8u )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x33F,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070057LL,
      v22);
    return 2147942487LL;
  }
  if ( v8 + v7 < v8 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x342,
      (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
      (const char *)0x80070216LL,
      v22);
    return 2147942934LL;
  }
  else
  {
    if ( v8 + v7 >= a2 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
    v11 = v8 / v10;
    if ( v8 % v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x344,
        (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
    for ( i = 0; i < v11; ++i )
    {
      v13 = *(_QWORD *)this;
      v23 = 0;
      v14 = (*(__int64 (__fastcall **)(CQueryKnownGameList *, _QWORD, __int128 *))(v13 + 88))(this, i, &v23);
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x34F,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)(unsigned int)v14,
          v22);
        return v15;
      }
      if ( DWORD2(v23) >= a2 )
      {
        v5 = retaddr;
        v6 = 849;
LABEL_4:
        wil::details::in1diag3::Return_Hr(
          v5,
          (void *)v6,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)0x80070057LL,
          v22);
        return 2147942487LL;
      }
      if ( HIDWORD(v23) >= a2 )
      {
        v5 = retaddr;
        v6 = 850;
        goto LABEL_4;
      }
      if ( (unsigned int)(HIDWORD(v23) + DWORD2(v23)) < DWORD2(v23) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x353,
          (unsigned int)"onecoreuap\\shell\\twinui\\broadcastdvrcomponent\\kgl\\lib\\knowngamelist.cpp",
          (const char *)0x80070216LL,
          v22);
        return 2147942934LL;
      }
      if ( HIDWORD(v23) + DWORD2(v23) > a2 )
      {
        v5 = retaddr;
        v6 = 852;
        goto LABEL_4;
      }
      if ( i )
      {
        v16 = v23;
        if ( (_WORD)v23 )
        {
          v17 = 0;
          v18 = 0;
          locale = _create_locale(0, "C");
          while ( (unsigned int)v18 < 4 )
          {
            v20 = _towlower_l(*((_WORD *)&v22 + v18), locale);
            v21 = _towlower_l(*((_WORD *)&v23 + v18), locale);
            v18 = (unsigned int)(v18 + 1);
            v17 = v20 - v21;
            if ( v17 )
              goto LABEL_39;
          }
          if ( (_DWORD)v18 != 4 )
          {
            _free_locale(locale);
            goto LABEL_49;
          }
LABEL_39:
          _free_locale(locale);
          if ( v17 < 0 )
            goto LABEL_40;
LABEL_49:
          v5 = retaddr;
          v6 = 859;
          goto LABEL_4;
        }
      }
      else
      {
LABEL_40:
        v16 = v23;
      }
      v22 = v16;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180022800  push    r12
0x180022802  push    r14
0x180022804  sub     rsp, 58h
0x180022808  mov     rax, cs:__security_cookie
0x18002280f  xor     rax, rsp
0x180022812  mov     [rsp+68h+var_30], rax
0x180022817  cmp     dword ptr [rcx+28h], 0
0x18002281b  mov     r14d, edx
0x18002281e  mov     r12, rcx
0x180022821  jnz     short loc_1800228A1
0x180022823  mov     rcx, [rsp+68h]; this
0x180022828  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002282f  mov     r9d, 80070057h; char *
0x180022835  mov     edx, 328h; void *
0x18002283a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002283f  mov     eax, 80070057h
0x180022844  jmp     short loc_18002288B
0x180022846  mov     rcx, [rsp+68h]; this
0x18002284b  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022852  mov     r9d, 80070057h; char *
0x180022858  mov     edx, 351h; void *
0x18002285d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022862  mov     eax, 80070057h
0x180022867  mov     rbx, [rsp+68h+arg_8]
0x18002286c  mov     rdi, [rsp+68h+var_18]
0x180022871  mov     rsi, [rsp+68h+arg_18]
0x180022879  mov     rbp, [rsp+68h+arg_10]
0x180022881  mov     r15, [rsp+68h+var_28]
0x180022886  mov     r13, [rsp+68h+var_20]
0x18002288b  mov     rcx, [rsp+68h+var_30]
0x180022890  xor     rcx, rsp; StackCookie
0x180022893  call    __security_check_cookie
0x180022898  add     rsp, 58h
0x18002289c  pop     r14
0x18002289e  pop     r12
0x1800228a0  retn
0x1800228a1  mov     edx, [rcx+2Ch]
0x1800228a4  cmp     edx, r14d
0x1800228a7  jb      short loc_1800228CC
0x1800228a9  mov     rcx, [rsp+68h]; this
0x1800228ae  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800228b5  mov     r9d, 80070057h; char *
0x1800228bb  mov     edx, 329h; void *
0x1800228c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228c5  mov     eax, 80070057h
0x1800228ca  jmp     short loc_18002288B
0x1800228cc  mov     ecx, [rcx+30h]
0x1800228cf  cmp     ecx, r14d
0x1800228d2  jb      short loc_1800228F7
0x1800228d4  mov     rcx, [rsp+68h]; this
0x1800228d9  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800228e0  mov     r9d, 80070057h; char *
0x1800228e6  mov     edx, 32Ah; void *
0x1800228eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228f0  mov     eax, 80070057h
0x1800228f5  jmp     short loc_18002288B
0x1800228f7  mov     eax, [r12+24h]
0x1800228fc  mov     r8d, [r12+34h]
0x180022901  cmp     eax, 5
0x180022904  jnz     loc_180022BB1
0x18002290a  cmp     r8d, 10h
0x18002290e  jz      short loc_180022936
0x180022910  mov     rcx, [rsp+68h]; this
0x180022915  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002291c  mov     r9d, 80070057h; char *
0x180022922  mov     edx, 32Eh; void *
0x180022927  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002292c  mov     eax, 80070057h
0x180022931  jmp     loc_18002288B
0x180022936  cmp     dword ptr [r12+3Ch], 2
0x18002293c  jbe     short loc_180022969
0x18002293e  mov     rcx, [rsp+68h]; this
0x180022943  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x18002294a  mov     r9d, 80070057h; char *
0x180022950  mov     edx, 339h; void *
0x180022955  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002295a  mov     eax, 80070057h
0x18002295f  jmp     loc_18002288B
0x180022964  cmp     eax, 2
0x180022967  jnb     short loc_180022936
0x180022969  cmp     eax, 3
0x18002296c  jb      short loc_1800229A3
0x18002296e  movzx   eax, word ptr [r12+42h]
0x180022974  dec     ax
0x180022977  cmp     ax, 8
0x18002297b  jbe     short loc_1800229A3
0x18002297d  mov     rcx, [rsp+68h]; this
0x180022982  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022989  mov     r9d, 80070057h; char *
0x18002298f  mov     edx, 33Fh; void *
0x180022994  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022999  mov     eax, 80070057h
0x18002299e  jmp     loc_18002288B
0x1800229a3  lea     eax, [rcx+rdx]
0x1800229a6  cmp     eax, ecx
0x1800229a8  jb      loc_180022B84
0x1800229ae  cmp     eax, r14d
0x1800229b1  jb      short loc_1800229D9
0x1800229b3  mov     rcx, [rsp+68h]; this
0x1800229b8  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800229bf  mov     r9d, 80070057h; char *
0x1800229c5  mov     edx, 343h; void *
0x1800229ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800229cf  mov     eax, 80070057h
0x1800229d4  jmp     loc_18002288B
0x1800229d9  xor     edx, edx
0x1800229db  mov     [rsp+68h+var_20], r13
0x1800229e0  mov     eax, ecx
0x1800229e2  div     r8d
0x1800229e5  mov     r13d, eax
0x1800229e8  test    edx, edx
0x1800229ea  jz      short loc_180022A12
0x1800229ec  mov     rcx, [rsp+68h]; this
0x1800229f1  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x1800229f8  mov     r9d, 80070057h; char *
0x1800229fe  mov     edx, 344h; void *
0x180022a03  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a08  mov     eax, 80070057h
0x180022a0d  jmp     loc_180022886
0x180022a12  mov     [rsp+68h+arg_8], rbx
0x180022a17  xor     ebx, ebx
0x180022a19  mov     [rsp+68h+arg_10], rbp
0x180022a21  mov     [rsp+68h+arg_18], rsi
0x180022a29  mov     [rsp+68h+var_18], rdi
0x180022a2e  mov     [rsp+68h+var_28], r15
0x180022a33  cmp     ebx, r13d
0x180022a36  jnb     loc_180022BAA
0x180022a3c  mov     rax, [r12]
0x180022a40  lea     r8, [rsp+68h+var_40]
0x180022a45  xorps   xmm0, xmm0
0x180022a48  mov     edx, ebx
0x180022a4a  mov     rcx, r12
0x180022a4d  movups  [rsp+68h+var_40], xmm0
0x180022a52  mov     rax, [rax+58h]
0x180022a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a5b  mov     edi, eax
0x180022a5d  test    eax, eax
0x180022a5f  js      loc_180022B64
0x180022a65  mov     eax, dword ptr [rsp+68h+var_40+8]
0x180022a69  cmp     eax, r14d
0x180022a6c  jnb     loc_180022846
0x180022a72  mov     ecx, dword ptr [rsp+68h+var_40+0Ch]
0x180022a76  cmp     ecx, r14d
0x180022a79  jb      short loc_180022A97
0x180022a7b  mov     rcx, [rsp+68h]
0x180022a80  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022a87  mov     r9d, 80070057h
0x180022a8d  mov     edx, 352h
0x180022a92  jmp     loc_18002285D
0x180022a97  lea     edx, [rcx+rax]
0x180022a9a  cmp     edx, eax
0x180022a9c  jb      short loc_180022ABF
0x180022a9e  cmp     edx, r14d
0x180022aa1  jbe     short loc_180022AE5
0x180022aa3  mov     rcx, [rsp+68h]
0x180022aa8  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022aaf  mov     r9d, 80070057h
0x180022ab5  mov     edx, 354h
0x180022aba  jmp     loc_18002285D
0x180022abf  mov     rcx, [rsp+68h]; this
0x180022ac4  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022acb  mov     r9d, 80070216h; char *
0x180022ad1  mov     edx, 353h; void *
0x180022ad6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022adb  mov     eax, 80070216h
0x180022ae0  jmp     loc_180022867
0x180022ae5  test    ebx, ebx
0x180022ae7  jz      short loc_180022B53
0x180022ae9  mov     rax, qword ptr [rsp+68h+var_40]
0x180022aee  test    ax, ax
0x180022af1  jz      short loc_180022B58
0x180022af3  xor     edi, edi
0x180022af5  lea     rdx, Locale; "C"
0x180022afc  xor     ebp, ebp
0x180022afe  xor     ecx, ecx; Category
0x180022b00  call    cs:__imp__create_locale
0x180022b06  mov     r15, rax
0x180022b09  cmp     ebp, 4
0x180022b0c  jnb     loc_180022BE1
0x180022b12  lea     rsi, ds:0[rbp*2]
0x180022b1a  mov     rdx, r15; Locale
0x180022b1d  movzx   ecx, word ptr [rsp+rsi+68h+var_48]; C
0x180022b22  call    cs:__imp__towlower_l
0x180022b28  movzx   ecx, word ptr [rsp+rsi+68h+var_40]; C
0x180022b2d  mov     rdx, r15; Locale
0x180022b30  movzx   edi, ax
0x180022b33  call    cs:__imp__towlower_l
0x180022b39  movzx   ecx, ax
0x180022b3c  inc     ebp
0x180022b3e  sub     edi, ecx
0x180022b40  jz      short loc_180022B09
0x180022b42  mov     rcx, r15; Locale
0x180022b45  call    cs:__imp__free_locale
0x180022b4b  test    edi, edi
0x180022b4d  jns     loc_180022BF0
0x180022b53  mov     rax, qword ptr [rsp+68h+var_40]
0x180022b58  mov     [rsp+68h+var_48], rax
0x180022b5d  inc     ebx
0x180022b5f  jmp     loc_180022A33
0x180022b64  mov     rcx, [rsp+68h]; this
0x180022b69  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022b70  mov     r9d, edi; char *
0x180022b73  mov     edx, 34Fh; void *
0x180022b78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022b7d  mov     eax, edi
0x180022b7f  jmp     loc_180022867
0x180022b84  mov     rcx, [rsp+68h]; this
0x180022b89  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022b90  mov     r9d, 80070216h; char *
0x180022b96  mov     edx, 342h; void *
0x180022b9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022ba0  mov     eax, 80070216h
0x180022ba5  jmp     loc_18002288B
0x180022baa  xor     eax, eax
0x180022bac  jmp     loc_180022867
0x180022bb1  cmp     r8d, 10h
0x180022bb5  jnb     loc_180022964
0x180022bbb  mov     rcx, [rsp+68h]; this
0x180022bc0  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022bc7  mov     r9d, 80070057h; char *
0x180022bcd  mov     edx, 333h; void *
0x180022bd2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022bd7  mov     eax, 80070057h
0x180022bdc  jmp     loc_18002288B
0x180022be1  jz      loc_180022B42
0x180022be7  mov     rcx, r15; Locale
0x180022bea  call    cs:__imp__free_locale
0x180022bf0  mov     rcx, [rsp+68h]
0x180022bf5  lea     r8, aOnecoreuapShel_3; "onecoreuap\\shell\\twinui\\broadcastdvr"...
0x180022bfc  mov     r9d, 80070057h
0x180022c02  mov     edx, 35Bh
0x180022c07  jmp     loc_18002285D
```
