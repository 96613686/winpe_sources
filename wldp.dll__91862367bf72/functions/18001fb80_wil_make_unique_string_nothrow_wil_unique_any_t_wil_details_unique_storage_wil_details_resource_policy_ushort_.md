# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001fb80`
- end: `0x18001fc24`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001bb64`

## callees

- `0x1800133c0`
- `0x18001fb80`
- `0x1800267f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fbe3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fbe3`

## string_xrefs

- `0x18001fba9`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

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
  v9 = (char *)LocalAlloc(0, v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s_0(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x18001fb80  mov     [rsp+arg_0], rcx
0x18001fb85  push    rbx
0x18001fb86  push    rbp
0x18001fb87  push    rsi
0x18001fb88  push    rdi
0x18001fb89  push    r14
0x18001fb8b  push    r15
0x18001fb8d  sub     rsp, 38h
0x18001fb91  mov     rdi, rdx
0x18001fb94  mov     rbx, rcx
0x18001fb97  xor     r15d, r15d
0x18001fb9a  mov     [rsp+68h+var_48], r15d
0x18001fb9f  mov     rcx, [rsp+68h]; this
0x18001fba4  test    rdx, rdx
0x18001fba7  jnz     short loc_18001FBBB
0x18001fba9  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001fbb0  mov     edx, 0F89h; void *
0x18001fbb5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001fbbb  mov     ecx, 7FFFFFFFh
0x18001fbc0  mov     rax, rdi
0x18001fbc3  cmp     [rax], r15w
0x18001fbc7  jz      short loc_18001FBD3
0x18001fbc9  add     rax, 2
0x18001fbcd  sub     rcx, 1
0x18001fbd1  jnz     short loc_18001FBC3
0x18001fbd3  sub     rax, rdi
0x18001fbd6  sar     rax, 1
0x18001fbd9  lea     r14, [rax+rax]
0x18001fbdd  lea     rdx, [r14+2]; uBytes
0x18001fbe1  xor     ecx, ecx; uFlags
0x18001fbe3  call    cs:__imp_LocalAlloc
0x18001fbe9  mov     rsi, rax
0x18001fbec  test    rax, rax
0x18001fbef  jz      short loc_18001FC08
0x18001fbf1  mov     r9, r14; SourceSize
0x18001fbf4  mov     r8, rdi; Source
0x18001fbf7  lea     rdx, [r14+2]; DestinationSize
0x18001fbfb  mov     rcx, rax; Destination
0x18001fbfe  call    memcpy_s_0
0x18001fc03  mov     [r14+rsi], r15w
0x18001fc08  mov     [rbx], rsi
0x18001fc0b  mov     [rsp+68h+var_48], 1
0x18001fc13  mov     rax, rbx
0x18001fc16  add     rsp, 38h
0x18001fc1a  pop     r15
0x18001fc1c  pop     r14
0x18001fc1e  pop     rdi
0x18001fc1f  pop     rsi
0x18001fc20  pop     rbp
0x18001fc21  pop     rbx
0x18001fc22  retn
```
