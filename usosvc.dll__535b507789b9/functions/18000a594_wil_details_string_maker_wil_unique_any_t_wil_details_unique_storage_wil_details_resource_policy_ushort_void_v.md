# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x18000a594`
- end: `0x18000a6d3`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `319`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006b80`

## callees

- `0x18000313a`
- `0x180003198`
- `0x180009d24`
- `0x18000a594`
- `0x18000e454`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a63f`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18000a63f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a685`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a672`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a672`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a67d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a698`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a608`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a608`

## string_xrefs

- `0x18000a6c1`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

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
      v12 = 2 * v9;
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
  if ( a1 == &v16 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v13 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v13);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  return *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x18000a594  push    rbx
0x18000a596  push    rbp
0x18000a597  push    rsi
0x18000a598  push    rdi
0x18000a599  push    r12
0x18000a59b  push    r14
0x18000a59d  push    r15
0x18000a59f  sub     rsp, 30h
0x18000a5a3  xor     r12d, r12d
0x18000a5a6  mov     rsi, r8
0x18000a5a9  mov     rbp, rdx
0x18000a5ac  mov     r14, rcx
0x18000a5af  test    rdx, rdx
0x18000a5b2  jnz     short loc_18000A5BE
0x18000a5b4  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000a5b8  jz      loc_18000A6BC
0x18000a5be  test    rbp, rbp
0x18000a5c1  jz      short loc_18000A5F2
0x18000a5c3  mov     ecx, 7FFFFFFFh
0x18000a5c8  mov     rax, rsi
0x18000a5cb  cmp     rsi, rcx
0x18000a5ce  mov     rbx, rbp
0x18000a5d1  cmovnb  rax, rcx
0x18000a5d5  test    rax, rax
0x18000a5d8  jz      short loc_18000A5EA
0x18000a5da  cmp     [rbx], r12w
0x18000a5de  jz      short loc_18000A5EA
0x18000a5e0  add     rbx, 2
0x18000a5e4  sub     rax, 1
0x18000a5e8  jnz     short loc_18000A5DA
0x18000a5ea  sub     rbx, rbp
0x18000a5ed  sar     rbx, 1
0x18000a5f0  jmp     short loc_18000A5F5
0x18000a5f2  mov     rbx, rsi
0x18000a5f5  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a5f9  cmovz   rsi, rbx
0x18000a5fd  lea     r15, ds:2[rsi*2]
0x18000a605  mov     rcx, r15; cb
0x18000a608  call    cs:__imp_CoTaskMemAlloc
0x18000a60e  mov     rdi, rax
0x18000a611  test    rax, rax
0x18000a614  jz      short loc_18000A660
0x18000a616  test    rbp, rbp
0x18000a619  jz      short loc_18000A657
0x18000a61b  add     rbx, rbx
0x18000a61e  jz      short loc_18000A650
0x18000a620  mov     rcx, rax; void *
0x18000a623  cmp     r15, rbx
0x18000a626  jb      short loc_18000A635
0x18000a628  mov     r8, rbx; Size
0x18000a62b  mov     rdx, rbp; Src
0x18000a62e  call    memcpy_0
0x18000a633  jmp     short loc_18000A650
0x18000a635  mov     r8, r15; Size
0x18000a638  xor     edx, edx; Val
0x18000a63a  call    memset_0
0x18000a63f  call    cs:__imp__o__errno
0x18000a645  mov     dword ptr [rax], 22h ; '"'
0x18000a64b  call    _invalid_parameter_noinfo
0x18000a650  mov     [rbx+rdi], r12w
0x18000a655  jmp     short loc_18000A65B
0x18000a657  mov     [rax], r12w
0x18000a65b  mov     [rdi+rsi*2], r12w
0x18000a660  lea     rax, [rsp+68h+var_48]
0x18000a665  cmp     r14, rax
0x18000a668  jz      short loc_18000A690
0x18000a66a  mov     rsi, [r14]
0x18000a66d  test    rsi, rsi
0x18000a670  jz      short loc_18000A68B
0x18000a672  call    cs:__imp_GetLastError
0x18000a678  mov     rcx, rsi; pv
0x18000a67b  mov     ebx, eax
0x18000a67d  call    cs:__imp_CoTaskMemFree
0x18000a683  mov     ecx, ebx; dwErrCode
0x18000a685  call    cs:__imp_SetLastError
0x18000a68b  mov     [r14], rdi
0x18000a68e  jmp     short loc_18000A69E
0x18000a690  test    rdi, rdi
0x18000a693  jz      short loc_18000A69E
0x18000a695  mov     rcx, rdi; pv
0x18000a698  call    cs:__imp_CoTaskMemFree
0x18000a69e  mov     rax, [r14]
0x18000a6a1  neg     rax
0x18000a6a4  sbb     eax, eax
0x18000a6a6  not     eax
0x18000a6a8  and     eax, 8007000Eh
0x18000a6ad  add     rsp, 30h
0x18000a6b1  pop     r15
0x18000a6b3  pop     r14
0x18000a6b5  pop     r12
0x18000a6b7  pop     rdi
0x18000a6b8  pop     rsi
0x18000a6b9  pop     rbp
0x18000a6ba  pop     rbx
0x18000a6bb  retn
0x18000a6bc  mov     rcx, [rsp+68h]; this
0x18000a6c1  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a6c8  mov     edx, 0F89h; void *
0x18000a6cd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
