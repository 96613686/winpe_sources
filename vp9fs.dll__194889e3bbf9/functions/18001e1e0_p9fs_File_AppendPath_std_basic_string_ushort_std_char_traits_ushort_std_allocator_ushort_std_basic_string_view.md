# p9fs::File::AppendPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,std::basic_string_view<char,std::char_traits<char>>)

- ea: `0x18001e1e0`
- end: `0x18001e420`
- name: `?AppendPath@File@p9fs@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$basic_string_view@DU?$char_traits@D@std@@@4@@Z`
- size: `576`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x18001e494`
- `0x180022120`

## callees

- `0x180004120`
- `0x180004c74`
- `0x180004c98`
- `0x1800074e0`
- `0x18001d340`
- `0x18001d588`
- `0x18001d8b4`
- `0x18001d940`
- `0x18001dc10`
- `0x18001e1e0`
- `0x18001ff4c`

## import_xrefs

- `lxutil!LxUtilNtFileNameEscapeInPlace` at `0x18001e293`
- `lxutil!LxUtilNtFileNameEscapeInPlace` at `0x18001e293`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall p9fs::File::AppendPath(__int64 a1, _QWORD *a2, __int64 a3)
{
  unsigned __int64 v5; // r8
  __int64 v6; // rcx
  __int64 v7; // r9
  _QWORD *v8; // rax
  __int128 *v9; // rdx
  __int64 v10; // r9
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  _QWORD *v14; // rax
  _QWORD *v15; // rdx
  __int64 v16; // rdx
  void **v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rdi
  __int128 pExceptionObject; // [rsp+38h] [rbp-41h] BYREF
  __int64 v21; // [rsp+48h] [rbp-31h]
  __int128 v22; // [rsp+58h] [rbp-21h] BYREF
  __int64 v23; // [rsp+68h] [rbp-11h]
  unsigned __int64 v24; // [rsp+70h] [rbp-9h]
  char v25; // [rsp+78h] [rbp-1h]
  void *Src[2]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v27; // [rsp+90h] [rbp+17h]
  unsigned __int64 v28; // [rsp+98h] [rbp+1Fh]
  _WORD v29[2]; // [rsp+A0h] [rbp+27h] BYREF
  int v30; // [rsp+A4h] [rbp+2Bh]
  __int128 *v31; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v5 = *(_QWORD *)(a3 + 8);
  v22 = 0;
  v6 = 0;
  v23 = 0;
  v7 = 7;
  v24 = 7;
  LOWORD(v22) = 0;
  if ( !v5 )
  {
LABEL_7:
    v25 = 1;
    *(_OWORD *)Src = v22;
    v27 = v6;
    v28 = v7;
    v23 = 0;
    v24 = 7;
    LOWORD(v22) = 0;
    goto LABEL_8;
  }
  if ( v5 <= 0xFF )
  {
    v8 = Vml::MultiByteToWide(&pExceptionObject, *(LPCCH *)a3, v5);
    std::wstring::operator=(&v22, v8);
    std::wstring::~wstring(&pExceptionObject);
    v9 = &v22;
    if ( v24 > 7 )
      v9 = (__int128 *)v22;
    if ( (unsigned __int16)(2 * v23) != 2 * v23 )
    {
      pExceptionObject = 0;
      v21 = 0;
      gsl::narrowing_error::narrowing_error((gsl::narrowing_error *)&pExceptionObject);
      throw (gsl::narrowing_error *)&pExceptionObject;
    }
    v29[0] = 2 * v23;
    v29[1] = 2 * v23;
    v30 = 0;
    v31 = v9;
    LxUtilNtFileNameEscapeInPlace(v29);
    v7 = v24;
    v6 = v23;
    goto LABEL_7;
  }
  v25 = 0;
  LODWORD(Src[0]) = -36;
LABEL_8:
  std::wstring::~wstring(&v22);
  if ( !v25 )
    return LODWORD(Src[0]);
  v12 = a2[2];
  if ( v12 )
  {
    v13 = a2[3];
    v14 = v13 <= 7 ? a2 : (_QWORD *)*a2;
    v10 = 92;
    if ( *((_WORD *)v14 + v12 - 1) != 92 )
    {
      if ( v12 >= v13 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(a2);
      }
      else
      {
        a2[2] = v12 + 1;
        if ( v13 <= 7 )
          v15 = a2;
        else
          v15 = (_QWORD *)*a2;
        *(_DWORD *)((char *)v15 + 2 * v12) = 92;
      }
    }
  }
  if ( !v25 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\vm\\inc\\expected.h",
      (const char *)v10);
  v16 = v27;
  v17 = Src;
  if ( v28 > 7 )
    v17 = (void **)Src[0];
  v18 = a2[2];
  if ( v27 > (unsigned __int64)(a2[3] - v18) )
  {
    std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,unsigned short const *,unsigned __int64>(
      a2,
      v27);
  }
  else
  {
    v19 = v18 + v27;
    a2[2] = v18 + v27;
    if ( a2[3] > 7u )
      a2 = (_QWORD *)*a2;
    memmove_0((char *)a2 + 2 * v18, v17, 2 * v16);
    *((_WORD *)a2 + v19) = 0;
  }
  if ( v25 )
    std::wstring::~wstring(Src);
  return 0;
}

```

## disassembly

```asm
0x18001e1e0  mov     [rsp-8+arg_0], rbx
0x18001e1e5  push    rbp
0x18001e1e6  push    rdi
0x18001e1e7  push    r14
0x18001e1e9  lea     rbp, [rsp-47h]
0x18001e1ee  sub     rsp, 0C0h
0x18001e1f5  mov     rax, cs:__security_cookie
0x18001e1fc  xor     rax, rsp
0x18001e1ff  mov     [rbp+57h+var_20], rax
0x18001e203  mov     r10, r8
0x18001e206  mov     rbx, rdx
0x18001e209  mov     r8, [r8+8]; cbMultiByte
0x18001e20d  xorps   xmm0, xmm0
0x18001e210  movups  [rbp+57h+var_78], xmm0
0x18001e214  xor     ecx, ecx
0x18001e216  mov     [rbp+57h+var_68], rcx
0x18001e21a  lea     r14d, [rcx+7]
0x18001e21e  mov     r9d, r14d
0x18001e221  mov     [rbp+57h+var_60], r14
0x18001e225  xor     eax, eax
0x18001e227  mov     word ptr [rbp+57h+var_78], ax
0x18001e22b  test    r8, r8
0x18001e22e  jz      short loc_18001E2A1
0x18001e230  cmp     r8, 0FFh
0x18001e237  ja      loc_18001E2EE
0x18001e23d  mov     rdx, [r10]; lpMultiByteStr
0x18001e240  lea     rcx, [rbp+57h+pExceptionObject]; Src
0x18001e244  call    ?MultiByteToWide@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD_KI@Z; Vml::MultiByteToWide(char const *,unsigned __int64,uint)
0x18001e249  mov     rdx, rax
0x18001e24c  lea     rcx, [rbp+57h+var_78]
0x18001e250  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001e255  lea     rcx, [rbp+57h+pExceptionObject]
0x18001e259  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e25e  lea     rdx, [rbp+57h+var_78]
0x18001e262  cmp     [rbp+57h+var_60], r14
0x18001e266  cmova   rdx, qword ptr [rbp+57h+var_78]
0x18001e26b  mov     rax, [rbp+57h+var_68]
0x18001e26f  add     rax, rax
0x18001e272  movzx   ecx, ax
0x18001e275  cmp     rcx, rax
0x18001e278  jnz     loc_18001E3F9
0x18001e27e  xor     eax, eax
0x18001e280  mov     [rbp+57h+var_30], cx
0x18001e284  mov     [rbp+57h+var_2E], cx
0x18001e288  mov     [rbp+57h+var_2C], eax
0x18001e28b  mov     [rbp+57h+var_28], rdx
0x18001e28f  lea     rcx, [rbp+57h+var_30]
0x18001e293  call    cs:__imp_LxUtilNtFileNameEscapeInPlace
0x18001e299  mov     r9, [rbp+57h+var_60]
0x18001e29d  mov     rcx, [rbp+57h+var_68]
0x18001e2a1  mov     [rbp+57h+var_58], 1
0x18001e2a5  xorps   xmm0, xmm0
0x18001e2a8  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18001e2ac  mov     rax, qword ptr [rbp+57h+var_78]
0x18001e2b0  mov     [rbp+57h+Src], rax
0x18001e2b4  mov     rax, qword ptr [rbp+57h+var_78+8]
0x18001e2b8  mov     [rbp+57h+Src+8], rax
0x18001e2bc  mov     [rbp+57h+var_40], rcx
0x18001e2c0  mov     [rbp+57h+var_38], r9
0x18001e2c4  mov     [rbp+57h+var_68], 0
0x18001e2cc  mov     [rbp+57h+var_60], r14
0x18001e2d0  xor     eax, eax
0x18001e2d2  mov     word ptr [rbp+57h+var_78], ax
0x18001e2d6  lea     rcx, [rbp+57h+var_78]
0x18001e2da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e2df  nop
0x18001e2e0  cmp     [rbp+57h+var_58], 0
0x18001e2e4  jnz     short loc_18001E2FB
0x18001e2e6  mov     eax, dword ptr [rbp+57h+Src]
0x18001e2e9  jmp     loc_18001E3C7
0x18001e2ee  mov     [rbp+57h+var_58], 0
0x18001e2f2  mov     dword ptr [rbp+57h+Src], 0FFFFFFDCh
0x18001e2f9  jmp     short loc_18001E2D6
0x18001e2fb  mov     rcx, [rbx+10h]
0x18001e2ff  test    rcx, rcx
0x18001e302  jz      short loc_18001E34B
0x18001e304  mov     rdx, [rbx+18h]
0x18001e308  cmp     rdx, r14
0x18001e30b  jbe     short loc_18001E312
0x18001e30d  mov     rax, [rbx]
0x18001e310  jmp     short loc_18001E315
0x18001e312  mov     rax, rbx
0x18001e315  mov     r9d, 5Ch ; '\'
0x18001e31b  cmp     [rax+rcx*2-2], r9w
0x18001e321  jz      short loc_18001E34B
0x18001e323  cmp     rcx, rdx
0x18001e326  jnb     short loc_18001E343
0x18001e328  lea     rax, [rcx+1]
0x18001e32c  mov     [rbx+10h], rax
0x18001e330  cmp     rdx, r14
0x18001e333  jbe     short loc_18001E33A
0x18001e335  mov     rdx, [rbx]
0x18001e338  jmp     short loc_18001E33D
0x18001e33a  mov     rdx, rbx
0x18001e33d  mov     [rdx+rcx*2], r9d
0x18001e341  jmp     short loc_18001E34B
0x18001e343  mov     rcx, rbx; Src
0x18001e346  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18001e34b  cmp     [rbp+57h+var_58], 0
0x18001e34f  setz    al
0x18001e352  mov     rcx, [rbp+5Fh]; this
0x18001e356  test    al, al
0x18001e358  jnz     loc_18001E3E7
0x18001e35e  mov     rdx, [rbp+57h+var_40]
0x18001e362  lea     r9, [rbp+57h+Src]
0x18001e366  cmp     [rbp+57h+var_38], r14
0x18001e36a  cmova   r9, [rbp+57h+Src]
0x18001e36f  mov     rcx, [rbx+10h]
0x18001e373  mov     rax, [rbx+18h]
0x18001e377  sub     rax, rcx
0x18001e37a  cmp     rdx, rax
0x18001e37d  ja      short loc_18001E3A8
0x18001e37f  lea     rdi, [rcx+rdx]
0x18001e383  mov     [rbx+10h], rdi
0x18001e387  cmp     [rbx+18h], r14
0x18001e38b  jbe     short loc_18001E390
0x18001e38d  mov     rbx, [rbx]
0x18001e390  lea     r8, [rdx+rdx]; Size
0x18001e394  lea     rcx, [rbx+rcx*2]; void *
0x18001e398  mov     rdx, r9; Src
0x18001e39b  call    memmove_0
0x18001e3a0  xor     eax, eax
0x18001e3a2  mov     [rbx+rdi*2], ax
0x18001e3a6  jmp     short loc_18001E3B6
0x18001e3a8  mov     [rsp+0D0h+var_B0], rdx; __int64
0x18001e3ad  mov     rcx, rbx; Src
0x18001e3b0  call    ??$_Reallocate_grow_by@V_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_@@PEBG_K@Z; std::wstring::_Reallocate_grow_by<_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64>(unsigned __int64,_lambda_c79e6e710bf88f1f5f03e0c24b6ab143_,ushort const *,unsigned __int64)
0x18001e3b5  nop
0x18001e3b6  cmp     [rbp+57h+var_58], 0
0x18001e3ba  jz      short loc_18001E3C5
0x18001e3bc  lea     rcx, [rbp+57h+Src]
0x18001e3c0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001e3c5  xor     eax, eax
0x18001e3c7  mov     rcx, [rbp+57h+var_20]
0x18001e3cb  xor     rcx, rsp; StackCookie
0x18001e3ce  call    __security_check_cookie
0x18001e3d3  mov     rbx, [rsp+0D0h+arg_0]
0x18001e3db  add     rsp, 0C0h
0x18001e3e2  pop     r14
0x18001e3e4  pop     rdi
0x18001e3e5  pop     rbp
0x18001e3e6  retn
0x18001e3e7  lea     r8, aOnecoreVmIncEx; "onecore\\vm\\inc\\expected.h"
0x18001e3ee  mov     edx, 139h; void *
0x18001e3f3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001e3f9  xorps   xmm0, xmm0
0x18001e3fc  xor     eax, eax
0x18001e3fe  movups  [rbp+57h+pExceptionObject], xmm0
0x18001e402  mov     [rbp+57h+var_88], rax
0x18001e406  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18001e40a  call    ??0narrowing_error@gsl@@QEAA@XZ; gsl::narrowing_error::narrowing_error(void)
0x18001e40f  lea     rdx, _TI2?AUnarrowing_error@gsl@@; pThrowInfo
0x18001e416  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18001e41a  call    _CxxThrowException_0
```
