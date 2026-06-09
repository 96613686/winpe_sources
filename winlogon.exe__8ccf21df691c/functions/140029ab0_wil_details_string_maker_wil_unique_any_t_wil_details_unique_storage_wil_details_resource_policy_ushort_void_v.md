# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x140029ab0`
- end: `0x140029c27`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `375`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140060784`
- `0x1400862d0`
- `0x140086574`

## callees

- `0x140029ab0`
- `0x140054406`
- `0x1400544e0`
- `0x1400587ec`
- `0x14009cc54`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140029bf6`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x140029bf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140029c09`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029c1c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140029c1c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140029b2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029c14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029bb3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140029c14`

## string_xrefs

- `0x140029bca`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // r15
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  void *v12; // rsi
  __int64 result; // rax
  size_t v14; // rbx
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
  }
  else
  {
    v9 = a3;
  }
  if ( a3 == -1 )
    v4 = v9;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v14 = 2 * v9;
      if ( v14 )
      {
        if ( 2 * v4 + 2 < v14 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v14);
        }
      }
      v11[v14 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v12 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v12);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  result = 0;
  if ( !*(_QWORD *)a1 )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x140029ab0  push    rbp
0x140029ab2  push    r14
0x140029ab4  push    r15
0x140029ab6  sub     rsp, 30h
0x140029aba  mov     r15, r8
0x140029abd  mov     rbp, rdx
0x140029ac0  mov     r14, rcx
0x140029ac3  test    rdx, rdx
0x140029ac6  jz      loc_140029BBB
0x140029acc  mov     [rsp+48h+arg_0], rbx
0x140029ad1  mov     [rsp+48h+arg_8], rsi
0x140029ad6  mov     [rsp+48h+arg_10], rdi
0x140029adb  test    rbp, rbp
0x140029ade  jz      loc_140029BDC
0x140029ae4  mov     ecx, 7FFFFFFFh
0x140029ae9  mov     rax, r8
0x140029aec  cmp     r8, rcx
0x140029aef  mov     rbx, rbp
0x140029af2  cmovnb  rax, rcx
0x140029af6  test    rax, rax
0x140029af9  jz      short loc_140029B10
0x140029afb  nop     dword ptr [rax+rax+00h]
0x140029b00  cmp     word ptr [rbx], 0
0x140029b04  jz      short loc_140029B10
0x140029b06  add     rbx, 2
0x140029b0a  sub     rax, 1
0x140029b0e  jnz     short loc_140029B00
0x140029b10  sub     rbx, rbp
0x140029b13  sar     rbx, 1
0x140029b16  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140029b1a  jz      loc_140029BE4
0x140029b20  lea     rsi, ds:2[r15*2]
0x140029b28  mov     rcx, rsi; cb
0x140029b2b  call    cs:__imp_CoTaskMemAlloc
0x140029b31  mov     rdi, rax
0x140029b34  test    rax, rax
0x140029b37  jnz     short loc_140029B78
0x140029b39  lea     rax, [rsp+48h+var_28]
0x140029b3e  cmp     r14, rax
0x140029b41  jz      short loc_140029BAB
0x140029b43  mov     rsi, [r14]
0x140029b46  test    rsi, rsi
0x140029b49  jnz     loc_140029C09
0x140029b4f  mov     [r14], rdi
0x140029b52  mov     rdi, [rsp+48h+arg_10]
0x140029b57  xor     eax, eax
0x140029b59  cmp     [r14], rax
0x140029b5c  mov     ecx, 8007000Eh
0x140029b61  mov     rsi, [rsp+48h+arg_8]
0x140029b66  mov     rbx, [rsp+48h+arg_0]
0x140029b6b  cmovz   eax, ecx
0x140029b6e  add     rsp, 30h
0x140029b72  pop     r15
0x140029b74  pop     r14
0x140029b76  pop     rbp
0x140029b77  retn
0x140029b78  test    rbp, rbp
0x140029b7b  jz      short loc_140029BA4
0x140029b7d  add     rbx, rbx
0x140029b80  jz      short loc_140029B95
0x140029b82  mov     rcx, rdi; void *
0x140029b85  cmp     rsi, rbx
0x140029b88  jb      short loc_140029BEC
0x140029b8a  mov     r8, rbx; Size
0x140029b8d  mov     rdx, rbp; Src
0x140029b90  call    memcpy_0
0x140029b95  xor     eax, eax
0x140029b97  mov     [rbx+rdi], ax
0x140029b9b  xor     eax, eax
0x140029b9d  mov     [rdi+r15*2], ax
0x140029ba2  jmp     short loc_140029B39
0x140029ba4  xor     eax, eax
0x140029ba6  mov     [rdi], ax
0x140029ba9  jmp     short loc_140029B9B
0x140029bab  test    rdi, rdi
0x140029bae  jz      short loc_140029B52
0x140029bb0  mov     rcx, rdi; pv
0x140029bb3  call    cs:__imp_CoTaskMemFree
0x140029bb9  jmp     short loc_140029B52
0x140029bbb  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140029bbf  jnz     loc_140029ACC
0x140029bc5  mov     rcx, [rsp+48h]; this
0x140029bca  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140029bd1  mov     edx, 0F89h; void *
0x140029bd6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x140029bdc  mov     rbx, r8
0x140029bdf  jmp     loc_140029B16
0x140029be4  mov     r15, rbx
0x140029be7  jmp     loc_140029B20
0x140029bec  mov     r8, rsi; Size
0x140029bef  xor     edx, edx; Val
0x140029bf1  call    memset_0
0x140029bf6  call    cs:__imp__o__errno
0x140029bfc  mov     dword ptr [rax], 22h ; '"'
0x140029c02  call    _invalid_parameter_noinfo
0x140029c07  jmp     short loc_140029B95
0x140029c09  call    cs:__imp_GetLastError
0x140029c0f  mov     rcx, rsi; pv
0x140029c12  mov     ebx, eax
0x140029c14  call    cs:__imp_CoTaskMemFree
0x140029c1a  mov     ecx, ebx; dwErrCode
0x140029c1c  call    cs:__imp_SetLastError
0x140029c22  jmp     loc_140029B4F
```
