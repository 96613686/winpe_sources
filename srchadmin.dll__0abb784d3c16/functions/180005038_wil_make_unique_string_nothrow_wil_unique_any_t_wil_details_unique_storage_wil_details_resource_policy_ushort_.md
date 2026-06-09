# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180005038`
- end: `0x180005127`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004e10`

## callees

- `0x180005038`
- `0x1800067fa`
- `0x180006864`
- `0x18000687c`
- `0x180007ce8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800050f1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800050f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800050ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800050ba`

## string_xrefs

- `0x180005063`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180005038  push    rbx
0x18000503a  push    rbp
0x18000503b  push    rsi
0x18000503c  push    rdi
0x18000503d  push    r12
0x18000503f  push    r14
0x180005041  push    r15
0x180005043  sub     rsp, 20h
0x180005047  xor     r12d, r12d
0x18000504a  mov     rbx, r8
0x18000504d  mov     rbp, rdx
0x180005050  mov     r15, rcx
0x180005053  test    rdx, rdx
0x180005056  jnz     short loc_18000507A
0x180005058  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000505c  jnz     short loc_180005075
0x18000505e  mov     rcx, [rsp+58h]; this
0x180005063  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000506a  mov     edx, 0F89h; void *
0x18000506f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005075  mov     rdi, rbx
0x180005078  jmp     short loc_1800050AF
0x18000507a  mov     ecx, 7FFFFFFFh
0x18000507f  mov     rax, rbx
0x180005082  cmp     rbx, rcx
0x180005085  mov     rdi, rbp
0x180005088  cmovnb  rax, rcx
0x18000508c  test    rax, rax
0x18000508f  jz      short loc_1800050A1
0x180005091  cmp     [rdi], r12w
0x180005095  jz      short loc_1800050A1
0x180005097  add     rdi, 2
0x18000509b  sub     rax, 1
0x18000509f  jnz     short loc_180005091
0x1800050a1  sub     rdi, rbp
0x1800050a4  sar     rdi, 1
0x1800050a7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800050ab  cmovz   rbx, rdi
0x1800050af  lea     r14, ds:2[rbx*2]
0x1800050b7  mov     rcx, r14; cb
0x1800050ba  call    cs:__imp_CoTaskMemAlloc
0x1800050c0  mov     rsi, rax
0x1800050c3  test    rax, rax
0x1800050c6  jz      short loc_180005112
0x1800050c8  test    rbp, rbp
0x1800050cb  jz      short loc_180005109
0x1800050cd  add     rdi, rdi
0x1800050d0  jz      short loc_180005102
0x1800050d2  mov     rcx, rax; void *
0x1800050d5  cmp     r14, rdi
0x1800050d8  jb      short loc_1800050E7
0x1800050da  mov     r8, rdi; Size
0x1800050dd  mov     rdx, rbp; Src
0x1800050e0  call    memcpy_0
0x1800050e5  jmp     short loc_180005102
0x1800050e7  mov     r8, r14; Size
0x1800050ea  xor     edx, edx; Val
0x1800050ec  call    memset_0
0x1800050f1  call    cs:__imp__o__errno
0x1800050f7  mov     dword ptr [rax], 22h ; '"'
0x1800050fd  call    _invalid_parameter_noinfo
0x180005102  mov     [rdi+rsi], r12w
0x180005107  jmp     short loc_18000510D
0x180005109  mov     [rax], r12w
0x18000510d  mov     [rsi+rbx*2], r12w
0x180005112  mov     [r15], rsi
0x180005115  mov     rax, r15
0x180005118  add     rsp, 20h
0x18000511c  pop     r15
0x18000511e  pop     r14
0x180005120  pop     r12
0x180005122  pop     rdi
0x180005123  pop     rsi
0x180005124  pop     rbp
0x180005125  pop     rbx
0x180005126  retn
```
