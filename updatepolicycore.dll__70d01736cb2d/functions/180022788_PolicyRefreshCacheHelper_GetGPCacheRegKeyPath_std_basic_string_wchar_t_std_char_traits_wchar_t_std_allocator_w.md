# PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180022788`
- end: `0x180022a40`
- name: `?GetGPCacheRegKeyPath@PolicyRefreshCacheHelper@@CAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@KAEAV23@1@Z`
- size: `696`
- prototype: `__int64 __fastcall(wchar_t **Src, int, __int64, _QWORD *)`
- caller_count: `3`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180023468`
- `0x1800236b8`
- `0x1800242b8`

## callees

- `0x18000aac0`
- `0x18000f27c`
- `0x18000f860`
- `0x18000f9fc`
- `0x18000fb4c`
- `0x18000fcc4`
- `0x180010260`
- `0x18001eea4`
- `0x180022788`
- `0x180024738`
- `0x18002df30`
- `0x18002fda9`
- `0x18002ffd0`
- `0x180036a90`

## string_xrefs

- `0x1800227dd`: `SOFTWARE\Microsoft\WindowsUpdate\UpdatePolicy\GPCache\CacheSet001\`
- `0x1800227e4`: `SOFTWARE\Microsoft\WindowsUpdate\UpdatePolicy\GPCache\CacheSet002\`
- `0x1800229f4`: `C:\__w\1\s\src\Client\policy\src\helpers\PolicyRefreshCacheHelper.cpp`

## pseudocode

```c
__int64 __fastcall PolicyRefreshCacheHelper::GetGPCacheRegKeyPath(wchar_t **Src, int a2, __int64 a3, _QWORD *a4)
{
  unsigned int v7; // edi
  const wchar_t *v8; // r9
  unsigned __int64 v9; // rdx
  __int64 v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rdx
  const wchar_t *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // r8
  char v19; // al
  wchar_t *v20; // rbx
  unsigned __int64 v21; // rcx
  int v23; // [rsp+20h] [rbp-E0h]
  _OWORD v24[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v25[256]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v26; // [rsp+170h] [rbp+70h] BYREF
  __int64 v27; // [rsp+180h] [rbp+80h]
  __int64 v28; // [rsp+188h] [rbp+88h]
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  v7 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 7;
  LOWORD(v26) = 0;
  v8 = L"SOFTWARE\\Microsoft\\WindowsUpdate\\UpdatePolicy\\GPCache\\CacheSet002\\";
  if ( a2 == 1 )
    v8 = L"SOFTWARE\\Microsoft\\WindowsUpdate\\UpdatePolicy\\GPCache\\CacheSet001\\";
  v9 = -1;
  do
    ++v9;
  while ( v8[v9] );
  if ( v9 > 7 )
  {
    std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(&v26, v9, a3, v8);
  }
  else
  {
    v27 = v9;
    v10 = 2 * v9;
    memmove(&v26, v8, 2 * v9);
    *(_WORD *)((char *)&v26 + v10) = 0;
  }
  v11 = Src[2];
  v12 = (wchar_t *)Src;
  if ( (unsigned __int64)Src[3] > 7 )
    v12 = *Src;
  if ( !v11 )
    goto LABEL_35;
  v13 = (__int64)v11 - 1;
  v14 = -1;
  if ( v13 != -1 )
    v14 = v13;
  if ( (unsigned __int64)(v14 + 2) < 0x10 )
  {
    memset_0(v25, 0, sizeof(v25));
    v16 = L"\\";
    v15 = 256;
    while ( *v16 < 0x100u )
    {
      v25[*(unsigned __int8 *)v16++] = 1;
      if ( v16 == L"" )
      {
        v19 = 1;
        goto LABEL_20;
      }
    }
    v19 = 0;
LABEL_20:
    v20 = &v12[v14];
    if ( v19 )
    {
      while ( *v20 >= 0x100u || !v25[*v20] )
      {
        if ( v20 == v12 )
          goto LABEL_35;
        --v20;
      }
    }
    else
    {
      while ( !wmemchr(L"\\", *v20, 1u) )
      {
        if ( v20 == v12 )
          goto LABEL_35;
        --v20;
      }
    }
    v17 = v20 - v12;
  }
  else
  {
    v17 = anonymous_namespace_::__std_find_last_of::_Dispatch_pos_unsigned_short_(v12);
  }
  if ( v17 == -1 )
  {
LABEL_35:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\helpers\\PolicyRefreshCacheHelper.cpp",
      (const char *)0x80070057LL,
      v23);
  }
  else
  {
    memset(v24, 0, sizeof(v24));
    if ( (unsigned __int64)Src[2] < v17 + 1 )
      std::_String_val<std::_Simple_types<wchar_t>>::_Xran(v16, v15, v18);
    std::wstring::_Construct<1,wchar_t const *>(v24);
    std::wstring::operator=(a4, v24);
    std::wstring::~wstring(v24);
    v21 = a4[2];
    if ( 0x7FFFFFFFFFFFFFFELL - v27 < v21 )
      std::_Xlen_string();
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::wstring(v24, v27, a4, v21);
    std::wstring::operator=(a3, v24);
    std::wstring::~wstring(v24);
  }
  std::wstring::~wstring(&v26);
  return v7;
}

```

## disassembly

```asm
0x180022788  push    rbp
0x18002278a  push    rbx
0x18002278b  push    rsi
0x18002278c  push    rdi
0x18002278d  push    r12
0x18002278f  push    r13
0x180022791  push    r14
0x180022793  push    r15
0x180022795  lea     rbp, [rsp-0A8h]
0x18002279d  sub     rsp, 1A8h
0x1800227a4  mov     rax, cs:__security_cookie
0x1800227ab  xor     rax, rsp
0x1800227ae  mov     [rbp+0E0h+var_50], rax
0x1800227b5  mov     r15, r9
0x1800227b8  mov     r13, r8
0x1800227bb  mov     rsi, rcx
0x1800227be  xor     edi, edi
0x1800227c0  xorps   xmm0, xmm0
0x1800227c3  movups  [rbp+0E0h+var_70], xmm0
0x1800227c7  mov     [rbp+0E0h+var_60], rdi
0x1800227ce  mov     [rbp+0E0h+var_58], 7
0x1800227d9  mov     word ptr [rbp+0E0h+var_70], di
0x1800227dd  lea     rax, aSoftwareMicros_17; "SOFTWARE\\Microsoft\\WindowsUpdate\\Upd"...
0x1800227e4  lea     r9, aSoftwareMicros_12; "SOFTWARE\\Microsoft\\WindowsUpdate\\Upd"...
0x1800227eb  cmp     edx, 1
0x1800227ee  cmovz   r9, rax
0x1800227f2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800227f6  mov     rdx, r12
0x1800227f9  inc     rdx
0x1800227fc  cmp     [r9+rdx*2], di
0x180022801  jnz     short loc_1800227F9
0x180022803  lea     rcx, [rbp+0E0h+var_70]; void *
0x180022807  cmp     rdx, 7
0x18002280b  ja      short loc_18002282A
0x18002280d  mov     [rbp+0E0h+var_60], rdx
0x180022814  lea     rbx, [rdx+rdx]
0x180022818  mov     r8, rbx; Size
0x18002281b  mov     rdx, r9; Src
0x18002281e  call    memmove
0x180022823  mov     word ptr [rbp+rbx+0E0h+var_70], di
0x180022828  jmp     short loc_18002282F
0x18002282a  call    ??$_Reallocate_for@V_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *>(unsigned __int64,_lambda_3fa8b2c8193a0f3144fc4b1b8f243931_,wchar_t const *)
0x18002282f  mov     rax, [rsi+10h]
0x180022833  mov     r14, rsi
0x180022836  cmp     qword ptr [rsi+18h], 7
0x18002283b  jbe     short loc_180022840
0x18002283d  mov     r14, [rsi]
0x180022840  test    rax, rax
0x180022843  jz      loc_1800229E5
0x180022849  dec     rax
0x18002284c  mov     rbx, r12
0x18002284f  cmp     rax, r12
0x180022852  cmovb   rbx, rax
0x180022856  lea     rdx, [rbx+1]
0x18002285a  lea     rax, [rdx+1]
0x18002285e  cmp     rax, 10h
0x180022862  jb      short loc_18002287A
0x180022864  mov     r9d, 1
0x18002286a  mov     rcx, r14; Src
0x18002286d  call    _anonymous_namespace_____std_find_last_of___Dispatch_pos_unsigned_short_
0x180022872  mov     rbx, rax
0x180022875  jmp     loc_180022911
0x18002287a  xor     edx, edx; Val
0x18002287c  mov     r8d, 100h; Size
0x180022882  lea     rcx, [rsp+1E0h+var_170]; void *
0x180022887  call    memset_0
0x18002288c  lea     rcx, Src; "\\"
0x180022893  mov     edx, 100h
0x180022898  cmp     [rcx], dx
0x18002289b  jnb     short loc_1800228B9
0x18002289d  movzx   eax, byte ptr [rcx]
0x1800228a0  mov     [rsp+rax+1E0h+var_170], 1
0x1800228a5  add     rcx, 2
0x1800228a9  lea     rax, Src+2; ""
0x1800228b0  cmp     rcx, rax
0x1800228b3  jnz     short loc_180022898
0x1800228b5  mov     al, 1
0x1800228b7  jmp     short loc_1800228BC
0x1800228b9  mov     al, dil
0x1800228bc  lea     rbx, [r14+rbx*2]
0x1800228c0  test    al, al
0x1800228c2  jz      short loc_1800228E2
0x1800228c4  cmp     [rbx], dx
0x1800228c7  jnb     short loc_1800228D3
0x1800228c9  movzx   eax, word ptr [rbx]
0x1800228cc  cmp     [rsp+rax+1E0h+var_170], dil
0x1800228d1  jnz     short loc_18002290B
0x1800228d3  cmp     rbx, r14
0x1800228d6  jz      loc_1800229E5
0x1800228dc  sub     rbx, 2
0x1800228e0  jmp     short loc_1800228C4
0x1800228e2  mov     r8d, 1; N
0x1800228e8  movzx   edx, word ptr [rbx]; C
0x1800228eb  lea     rcx, Src; "\\"
0x1800228f2  call    wmemchr
0x1800228f7  test    rax, rax
0x1800228fa  jnz     short loc_18002290B
0x1800228fc  cmp     rbx, r14
0x1800228ff  jz      loc_1800229E5
0x180022905  sub     rbx, 2
0x180022909  jmp     short loc_1800228E2
0x18002290b  sub     rbx, r14
0x18002290e  sar     rbx, 1
0x180022911  cmp     rbx, r12
0x180022914  jz      loc_1800229E5
0x18002291a  inc     rbx
0x18002291d  xorps   xmm0, xmm0
0x180022920  movups  [rsp+1E0h+var_198], xmm0
0x180022925  xorps   xmm1, xmm1
0x180022928  movdqu  [rsp+1E0h+var_188], xmm1
0x18002292e  mov     rax, [rsi+10h]
0x180022932  cmp     rax, rbx
0x180022935  jb      loc_180022A3A
0x18002293b  sub     rax, rbx
0x18002293e  cmp     rax, r12
0x180022941  cmovb   r12, rax
0x180022945  cmp     qword ptr [rsi+18h], 7
0x18002294a  jbe     short loc_18002294F
0x18002294c  mov     rsi, [rsi]
0x18002294f  lea     rdx, [rsi+rbx*2]
0x180022953  mov     r8, r12
0x180022956  lea     rcx, [rsp+1E0h+var_198]
0x18002295b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180022960  lea     rdx, [rsp+1E0h+var_198]
0x180022965  mov     rcx, r15
0x180022968  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002296d  lea     rcx, [rsp+1E0h+var_198]; void *
0x180022972  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022977  mov     rcx, [r15+10h]
0x18002297b  mov     rax, 7FFFFFFFFFFFFFFEh
0x180022985  mov     rdx, [rbp+0E0h+var_60]
0x18002298c  sub     rax, rdx
0x18002298f  cmp     rax, rcx
0x180022992  jb      loc_180022A34
0x180022998  lea     r9, [rbp+0E0h+var_70]
0x18002299c  cmp     [rbp+0E0h+var_58], 7
0x1800229a4  cmova   r9, qword ptr [rbp+0E0h+var_70]
0x1800229a9  cmp     qword ptr [r15+18h], 7
0x1800229ae  jbe     short loc_1800229B3
0x1800229b0  mov     r15, [r15]
0x1800229b3  mov     [rsp+1E0h+var_1B0], rcx; __int64
0x1800229b8  mov     [rsp+1E0h+Src], r15; Src
0x1800229bd  mov     [rsp+1E0h+var_1C0], rdx; __int64
0x1800229c2  lea     rcx, [rsp+1E0h+var_198]; void *
0x1800229c7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEB_W_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,wchar_t const * const,unsigned __int64,wchar_t const * const,unsigned __int64)
0x1800229cc  lea     rdx, [rsp+1E0h+var_198]
0x1800229d1  mov     rcx, r13
0x1800229d4  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800229d9  lea     rcx, [rsp+1E0h+var_198]; void *
0x1800229de  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800229e3  jmp     short loc_180022A06
0x1800229e5  mov     rcx, [rbp+0E8h]; this
0x1800229ec  mov     edi, 80070057h
0x1800229f1  mov     r9d, edi; char *
0x1800229f4  lea     r8, aCW1SSrcClientP_1; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800229fb  mov     edx, 57h ; 'W'; void *
0x180022a00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022a05  nop
0x180022a06  lea     rcx, [rbp+0E0h+var_70]; void *
0x180022a0a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022a0f  mov     eax, edi
0x180022a11  mov     rcx, [rbp+0E0h+var_50]
0x180022a18  xor     rcx, rsp; StackCookie
0x180022a1b  call    __security_check_cookie
0x180022a20  add     rsp, 1A8h
0x180022a27  pop     r15
0x180022a29  pop     r14
0x180022a2b  pop     r13
0x180022a2d  pop     r12
0x180022a2f  pop     rdi
0x180022a30  pop     rsi
0x180022a31  pop     rbx
0x180022a32  pop     rbp
0x180022a33  retn
0x180022a34  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180022a3a  call    ?_Xran@?$_String_val@U?$_Simple_types@_W@std@@@std@@SAXXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Xran(void)
```
