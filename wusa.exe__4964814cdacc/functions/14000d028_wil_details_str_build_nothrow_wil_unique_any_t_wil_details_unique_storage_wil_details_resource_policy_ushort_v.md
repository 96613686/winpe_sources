# wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wil::details::string_view_t const *,unsigned __int64)

- ea: `0x14000d028`
- end: `0x14000d255`
- name: `??$str_build_nothrow_@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBUstring_view_t@01@_K@Z`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000d620`

## callees

- `0x140004100`
- `0x14000c0dc`
- `0x14000d028`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000d1a4`
- `KERNEL32!GetLastError` at `0x14000d1a4`
- `KERNEL32!SetLastError` at `0x14000d1b7`
- `KERNEL32!SetLastError` at `0x14000d1b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d1fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000d205`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d06e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000d06e`

## string_xrefs

- `0x14000d1e3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000d214`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x14000d243`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::str_build_nothrow_<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        int *a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v4; // rbp
  __int64 v5; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  _WORD *v9; // rax
  void *v10; // rdi
  _WORD *v11; // r8
  _WORD *v12; // r15
  _WORD *v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rax
  signed int v16; // ebx
  _WORD *v17; // rdx
  _WORD *v18; // r9
  __int64 v19; // r11
  _WORD *v20; // rcx
  __int64 v21; // rax
  void *v22; // rsi
  DWORD LastError; // ebx
  int v25; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v4 = a2 + 48;
  v5 = a2;
  v7 = 0;
  v8 = a2;
  do
  {
    v7 += *(_QWORD *)(v8 + 8);
    v8 += 16;
  }
  while ( v8 != v4 );
  if ( v7 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v9 = CoTaskMemAlloc(2 * v7 + 2);
  v10 = v9;
  if ( !v9 )
  {
    v16 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x788,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      (const char *)0x8007000ELL,
      v25);
    return (unsigned int)v16;
  }
  *v9 = 0;
  v11 = v9;
  v9[v7] = 0;
  v12 = &v9[v7];
  if ( v5 == v4 )
  {
LABEL_32:
    if ( a1 == &v25 )
    {
      CoTaskMemFree(v10);
    }
    else
    {
      v22 = *(void **)a1;
      if ( *(_QWORD *)a1 )
      {
        LastError = GetLastError();
        CoTaskMemFree(v22);
        SetLastError(LastError);
      }
      *(_QWORD *)a1 = v10;
    }
    return 0;
  }
  while ( 1 )
  {
    v13 = *(_WORD **)v5;
    if ( !*(_QWORD *)v5 )
      goto LABEL_31;
    v14 = v12 + 1 - v11;
    if ( !v11 && v14 )
    {
      v16 = -2147024809;
      goto LABEL_39;
    }
    if ( v14 > 0x7FFFFFFF )
      break;
    v15 = *(_QWORD *)(v5 + 8);
    if ( v15 < 0x7FFFFFFF )
    {
      if ( v14 )
      {
        v18 = v11;
        v19 = 0;
        do
        {
          if ( !v15 )
            break;
          if ( !*v13 )
            break;
          *v18++ = *v13++;
          --v15;
          ++v19;
          --v14;
        }
        while ( v14 );
        v20 = v18 - 1;
        if ( v14 )
          v20 = v18;
        v21 = v19 - 1;
        v16 = v14 != 0 ? 0 : 0x8007007A;
        *v20 = 0;
        if ( v14 )
          v21 = v19;
        v17 = &v11[v21];
      }
      else
      {
        v17 = v11;
        v16 = 0;
        if ( v15 && *v13 )
        {
          if ( !v11 )
          {
            v16 = -2147024809;
            goto LABEL_40;
          }
          v16 = -2147024774;
        }
      }
      if ( v16 >= 0 || v16 == -2147024774 )
        v11 = v17;
    }
    else
    {
      v16 = -2147024809;
      if ( v14 )
        *v11 = 0;
    }
    if ( v16 < 0 )
      goto LABEL_40;
LABEL_31:
    v5 += 16;
    if ( v5 == v4 )
      goto LABEL_32;
  }
  v16 = -2147024809;
LABEL_39:
  *v11 = 0;
LABEL_40:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x791,
    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
    (const char *)(unsigned int)v16,
    v25);
  CoTaskMemFree(v10);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000d028  push    rbx
0x14000d02a  push    rbp
0x14000d02b  push    rsi
0x14000d02c  push    rdi
0x14000d02d  push    r12
0x14000d02f  push    r14
0x14000d031  push    r15
0x14000d033  sub     rsp, 30h
0x14000d037  xor     r12d, r12d
0x14000d03a  lea     rbp, [rdx+30h]
0x14000d03e  mov     rsi, rdx
0x14000d041  mov     r14, rcx
0x14000d044  mov     ebx, r12d
0x14000d047  mov     rax, rdx
0x14000d04a  cmp     rdx, rbp
0x14000d04d  jz      short loc_14000D066
0x14000d04f  add     rbx, [rax+8]
0x14000d053  add     rax, 10h
0x14000d057  cmp     rax, rbp
0x14000d05a  jnz     short loc_14000D04F
0x14000d05c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x14000d060  jz      loc_14000D23E
0x14000d066  lea     rcx, ds:2[rbx*2]; cb
0x14000d06e  call    cs:__imp_CoTaskMemAlloc
0x14000d074  mov     rdi, rax
0x14000d077  test    rax, rax
0x14000d07a  jz      loc_14000D20F
0x14000d080  mov     [rax], r12w
0x14000d084  mov     r8, rax
0x14000d087  mov     [rax+rbx*2], r12w
0x14000d08c  lea     r15, [rax+rbx*2]
0x14000d090  cmp     rsi, rbp
0x14000d093  jz      loc_14000D192
0x14000d099  mov     r9d, 8007007Ah
0x14000d09f  mov     rcx, [rsi]
0x14000d0a2  test    rcx, rcx
0x14000d0a5  jz      loc_14000D185
0x14000d0ab  lea     rdx, [r15+2]
0x14000d0af  sub     rdx, r8
0x14000d0b2  sar     rdx, 1
0x14000d0b5  test    r8, r8
0x14000d0b8  jnz     short loc_14000D0C3
0x14000d0ba  test    rdx, rdx
0x14000d0bd  jnz     loc_14000D1C2
0x14000d0c3  cmp     rdx, 7FFFFFFFh
0x14000d0ca  ja      loc_14000D1D5
0x14000d0d0  mov     rax, [rsi+8]
0x14000d0d4  cmp     rax, 7FFFFFFFh
0x14000d0da  jb      short loc_14000D0F3
0x14000d0dc  mov     ebx, 80070057h
0x14000d0e1  test    rdx, rdx
0x14000d0e4  jz      loc_14000D181
0x14000d0ea  mov     [r8], r12w
0x14000d0ee  jmp     loc_14000D181
0x14000d0f3  test    rdx, rdx
0x14000d0f6  jnz     short loc_14000D117
0x14000d0f8  mov     rdx, r8
0x14000d0fb  mov     ebx, r12d
0x14000d0fe  test    rax, rax
0x14000d101  jz      short loc_14000D175
0x14000d103  cmp     [rcx], r12w
0x14000d107  jz      short loc_14000D175
0x14000d109  test    r8, r8
0x14000d10c  jz      loc_14000D1CE
0x14000d112  mov     ebx, r9d
0x14000d115  jmp     short loc_14000D175
0x14000d117  mov     r9, r8
0x14000d11a  mov     r11, r12
0x14000d11d  test    rax, rax
0x14000d120  jz      short loc_14000D144
0x14000d122  movzx   r10d, word ptr [rcx]
0x14000d126  test    r10w, r10w
0x14000d12a  jz      short loc_14000D144
0x14000d12c  mov     [r9], r10w
0x14000d130  add     rcx, 2
0x14000d134  add     r9, 2
0x14000d138  dec     rax
0x14000d13b  inc     r11
0x14000d13e  sub     rdx, 1
0x14000d142  jnz     short loc_14000D11D
0x14000d144  test    rdx, rdx
0x14000d147  lea     rcx, [r9-2]
0x14000d14b  mov     rax, rdx
0x14000d14e  cmovnz  rcx, r9
0x14000d152  neg     rax
0x14000d155  mov     r9d, 8007007Ah
0x14000d15b  lea     rax, [r11-1]
0x14000d15f  sbb     ebx, ebx
0x14000d161  not     ebx
0x14000d163  and     ebx, r9d
0x14000d166  mov     [rcx], r12w
0x14000d16a  test    rdx, rdx
0x14000d16d  cmovnz  rax, r11
0x14000d171  lea     rdx, [r8+rax*2]
0x14000d175  test    ebx, ebx
0x14000d177  jns     short loc_14000D17E
0x14000d179  cmp     ebx, r9d
0x14000d17c  jnz     short loc_14000D181
0x14000d17e  mov     r8, rdx
0x14000d181  test    ebx, ebx
0x14000d183  js      short loc_14000D1DE
0x14000d185  add     rsi, 10h
0x14000d189  cmp     rsi, rbp
0x14000d18c  jnz     loc_14000D09F
0x14000d192  lea     rax, [rsp+68h+var_48]
0x14000d197  cmp     r14, rax
0x14000d19a  jz      short loc_14000D202
0x14000d19c  mov     rsi, [r14]
0x14000d19f  test    rsi, rsi
0x14000d1a2  jz      short loc_14000D1BD
0x14000d1a4  call    cs:__imp_GetLastError
0x14000d1aa  mov     rcx, rsi; pv
0x14000d1ad  mov     ebx, eax
0x14000d1af  call    cs:__imp_CoTaskMemFree
0x14000d1b5  mov     ecx, ebx; dwErrCode
0x14000d1b7  call    cs:__imp_SetLastError
0x14000d1bd  mov     [r14], rdi
0x14000d1c0  jmp     short loc_14000D20B
0x14000d1c2  mov     ebx, 80070057h
0x14000d1c7  test    rdx, rdx
0x14000d1ca  jz      short loc_14000D1DE
0x14000d1cc  jmp     short loc_14000D1DA
0x14000d1ce  mov     ebx, 80070057h
0x14000d1d3  jmp     short loc_14000D1DE
0x14000d1d5  mov     ebx, 80070057h
0x14000d1da  mov     [r8], r12w
0x14000d1de  mov     rcx, [rsp+68h]; this
0x14000d1e3  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000d1ea  mov     r9d, ebx; char *
0x14000d1ed  mov     edx, 791h; void *
0x14000d1f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d1f7  mov     rcx, rdi; pv
0x14000d1fa  call    cs:__imp_CoTaskMemFree
0x14000d200  jmp     short loc_14000D22D
0x14000d202  mov     rcx, rdi; pv
0x14000d205  call    cs:__imp_CoTaskMemFree
0x14000d20b  xor     eax, eax
0x14000d20d  jmp     short loc_14000D22F
0x14000d20f  mov     rcx, [rsp+68h]; this
0x14000d214  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000d21b  mov     ebx, 8007000Eh
0x14000d220  mov     edx, 788h; void *
0x14000d225  mov     r9d, ebx; char *
0x14000d228  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000d22d  mov     eax, ebx
0x14000d22f  add     rsp, 30h
0x14000d233  pop     r15
0x14000d235  pop     r14
0x14000d237  pop     r12
0x14000d239  pop     rdi
0x14000d23a  pop     rsi
0x14000d23b  pop     rbp
0x14000d23c  pop     rbx
0x14000d23d  retn
0x14000d23e  mov     rcx, [rsp+68h]; this
0x14000d243  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000d24a  mov     edx, 0F89h; void *
0x14000d24f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
