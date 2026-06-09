# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800222d0`
- end: `0x18002238c`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `188`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800229b8`

## callees

- `0x180002ffa`
- `0x180003088`
- `0x18000a238`
- `0x1800222d0`
- `0x1800315f8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002234c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002234c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002231a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002231a`

## string_xrefs

- `0x18002237a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = v8 + 2;
  v10 = (char *)LocalAlloc(0, v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x1800222d0  push    rbx
0x1800222d2  push    rbp
0x1800222d3  push    rsi
0x1800222d4  push    rdi
0x1800222d5  push    r14
0x1800222d7  push    r15
0x1800222d9  sub     rsp, 28h
0x1800222dd  xor     r15d, r15d
0x1800222e0  mov     rsi, rdx
0x1800222e3  mov     r14, rcx
0x1800222e6  test    rdx, rdx
0x1800222e9  jz      loc_180022375
0x1800222ef  mov     ecx, 7FFFFFFFh
0x1800222f4  mov     rax, rdx
0x1800222f7  cmp     [rax], r15w
0x1800222fb  jz      short loc_180022307
0x1800222fd  add     rax, 2
0x180022301  sub     rcx, 1
0x180022305  jnz     short loc_1800222F7
0x180022307  sub     rax, rsi
0x18002230a  xor     ecx, ecx; uFlags
0x18002230c  sar     rax, 1
0x18002230f  lea     rbx, [rax+rax]
0x180022313  lea     rbp, [rbx+2]
0x180022317  mov     rdx, rbp; uBytes
0x18002231a  call    cs:__imp_LocalAlloc
0x180022320  mov     rdi, rax
0x180022323  test    rax, rax
0x180022326  jz      short loc_180022362
0x180022328  test    rbx, rbx
0x18002232b  jz      short loc_18002235D
0x18002232d  mov     rcx, rax; void *
0x180022330  cmp     rbp, rbx
0x180022333  jb      short loc_180022342
0x180022335  mov     r8, rbx; Size
0x180022338  mov     rdx, rsi; Src
0x18002233b  call    memcpy_0
0x180022340  jmp     short loc_18002235D
0x180022342  mov     r8, rbp; Size
0x180022345  xor     edx, edx; Val
0x180022347  call    memset_0
0x18002234c  call    cs:__imp__o__errno
0x180022352  mov     dword ptr [rax], 22h ; '"'
0x180022358  call    _invalid_parameter_noinfo
0x18002235d  mov     [rbx+rdi], r15w
0x180022362  mov     [r14], rdi
0x180022365  mov     rax, r14
0x180022368  add     rsp, 28h
0x18002236c  pop     r15
0x18002236e  pop     r14
0x180022370  pop     rdi
0x180022371  pop     rsi
0x180022372  pop     rbp
0x180022373  pop     rbx
0x180022374  retn
0x180022375  mov     rcx, [rsp+58h]; this
0x18002237a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180022381  mov     edx, 0F89h; void *
0x180022386  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
