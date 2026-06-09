# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x140051114`
- end: `0x140051246`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `306`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140006ab0`
- `0x1400512b8`
- `0x1400513f0`

## callees

- `0x14000c16c`
- `0x140051114`
- `0x140052fe0`
- `0x1400538f0`
- `0x14005b124`
- `0x14005e4f4`

## string_xrefs

- `0x14005116b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14005122e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        void **a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 v6; // rax
  __int64 v7; // rbp
  int v8; // eax
  unsigned int v9; // ebx
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v11; // rcx
  unsigned __int16 *v12; // r15
  int v13; // eax
  int v14; // esi
  int v16; // [rsp+20h] [rbp-48h]
  int v17; // [rsp+20h] [rbp-48h]
  unsigned __int64 *v18; // [rsp+28h] [rbp-40h]
  unsigned int v19; // [rsp+30h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  unsigned __int16 *v21; // [rsp+78h] [rbp+10h] BYREF
  unsigned __int16 *v22; // [rsp+80h] [rbp+18h] BYREF

  v3 = 0;
  v4 = a2;
  v6 = a2;
  v7 = a2 + 16 * a3;
  if ( a2 != v7 )
  {
    do
    {
      v3 += *(_QWORD *)(v6 + 8);
      v6 += 16;
    }
    while ( v6 != v7 );
  }
  v21 = 0;
  v8 = wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
         &v21,
         0,
         v3);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = v21;
    v11 = v21;
    v22 = v21;
    v12 = &v21[v3 + 1];
    while ( 1 )
    {
      if ( v4 == v7 )
      {
        v22 = v10;
        v21 = 0;
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          a1,
          (void **)&v22);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v22);
        v9 = 0;
        goto LABEL_12;
      }
      if ( *(_QWORD *)v4 )
      {
        v13 = StringCchCopyNExW(v11, v12 - v11, *(const unsigned __int16 **)v4, *(_QWORD *)(v4 + 8), &v22, v18, v19);
        v14 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x791,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v13,
            v17);
          v9 = v14;
          goto LABEL_12;
        }
        v11 = v22;
      }
      v4 += 16;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x788,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v8,
    v16);
LABEL_12:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>((void **)&v21);
  return v9;
}

```

## disassembly

```asm
0x140051114  mov     [rsp+arg_0], rbx
0x140051119  push    rbp
0x14005111a  push    rsi
0x14005111b  push    rdi
0x14005111c  push    r14
0x14005111e  push    r15
0x140051120  sub     rsp, 40h
0x140051124  add     r8, r8
0x140051127  xor     esi, esi
0x140051129  mov     rdi, rdx
0x14005112c  mov     r14, rcx
0x14005112f  mov     rax, rdx
0x140051132  lea     rbp, [rdx+r8*8]
0x140051136  cmp     rdx, rbp
0x140051139  jz      short loc_140051148
0x14005113b  add     rsi, [rax+8]
0x14005113f  add     rax, 10h
0x140051143  cmp     rax, rbp
0x140051146  jnz     short loc_14005113B
0x140051148  mov     r8, rsi
0x14005114b  mov     [rsp+68h+arg_8], 0
0x140051154  xor     edx, edx
0x140051156  lea     rcx, [rsp+68h+arg_8]
0x14005115b  call    ?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z; wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)
0x140051160  mov     ebx, eax
0x140051162  test    eax, eax
0x140051164  jns     short loc_140051184
0x140051166  mov     rcx, [rsp+68h]; this
0x14005116b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140051172  mov     r9d, eax; char *
0x140051175  mov     edx, 788h; void *
0x14005117a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005117f  jmp     loc_14005120C
0x140051184  mov     rbx, [rsp+68h+arg_8]
0x140051189  mov     rcx, rbx
0x14005118c  mov     [rsp+68h+arg_10], rbx
0x140051194  lea     r15, [rbx+2]
0x140051198  lea     r15, [r15+rsi*2]
0x14005119c  jmp     short loc_1400511D7
0x14005119e  mov     r8, [rdi]; unsigned __int16 *
0x1400511a1  test    r8, r8
0x1400511a4  jz      short loc_1400511D3
0x1400511a6  mov     r9, [rdi+8]; unsigned __int64
0x1400511aa  lea     rax, [rsp+68h+arg_10]
0x1400511b2  mov     rdx, r15
0x1400511b5  mov     [rsp+68h+var_48], rax; int
0x1400511ba  sub     rdx, rcx
0x1400511bd  sar     rdx, 1; unsigned __int64
0x1400511c0  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1400511c5  mov     esi, eax
0x1400511c7  test    eax, eax
0x1400511c9  js      short loc_140051229
0x1400511cb  mov     rcx, [rsp+68h+arg_10]; unsigned __int16 *
0x1400511d3  add     rdi, 10h
0x1400511d7  cmp     rdi, rbp
0x1400511da  jnz     short loc_14005119E
0x1400511dc  lea     rdx, [rsp+68h+arg_10]
0x1400511e4  mov     [rsp+68h+arg_10], rbx
0x1400511ec  mov     rcx, r14
0x1400511ef  mov     [rsp+68h+arg_8], 0
0x1400511f8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1400511fd  lea     rcx, [rsp+68h+arg_10]
0x140051205  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14005120a  xor     ebx, ebx
0x14005120c  lea     rcx, [rsp+68h+arg_8]
0x140051211  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140051216  mov     eax, ebx
0x140051218  mov     rbx, [rsp+68h+arg_0]
0x14005121d  add     rsp, 40h
0x140051221  pop     r15
0x140051223  pop     r14
0x140051225  pop     rdi
0x140051226  pop     rsi
0x140051227  pop     rbp
0x140051228  retn
0x140051229  mov     rcx, [rsp+68h]; this
0x14005122e  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140051235  mov     r9d, esi; char *
0x140051238  mov     edx, 791h; void *
0x14005123d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140051242  mov     ebx, esi
0x140051244  jmp     short loc_14005120C
```
