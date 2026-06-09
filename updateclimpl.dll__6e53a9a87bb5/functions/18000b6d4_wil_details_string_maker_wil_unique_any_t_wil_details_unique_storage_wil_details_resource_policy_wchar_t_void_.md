# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x18000b6d4`
- end: `0x18000b81f`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b88c`

## callees

- `0x18000b6b4`
- `0x18000b6d4`
- `0x18001018c`
- `0x1800101d4`
- `0x180014960`
- `0x180014d20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7cd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000b7cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b7ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000b751`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b7e0`

## pseudocode

```c
__int64 __fastcall wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(
        char *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  void *v13; // rsi
  DWORD LastError; // ebx
  char v16; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
  v7 = a3;
  if ( a2 )
  {
    v8 = 0x7FFFFFFF;
    v9 = a2;
    if ( a3 < 0x7FFFFFFF )
      v8 = a3;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
  }
  if ( a3 == -1 )
    v4 = v7;
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
          memset(v10, 0, 2 * v4 + 2);
          *(_DWORD *)o__errno_0() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memmove(v10, a2, v12);
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
0x18000b6d4  mov     rax, rsp
0x18000b6d7  mov     [rax+8], rbx
0x18000b6db  mov     [rax+10h], rbp
0x18000b6df  mov     [rax+18h], rsi
0x18000b6e3  mov     [rax+20h], rdi
0x18000b6e7  push    r12
0x18000b6e9  push    r14
0x18000b6eb  push    r15
0x18000b6ed  sub     rsp, 30h
0x18000b6f1  xor     r12d, r12d
0x18000b6f4  mov     rsi, r8
0x18000b6f7  mov     rbp, rdx
0x18000b6fa  mov     r14, rcx
0x18000b6fd  test    rdx, rdx
0x18000b700  jnz     short loc_18000B70C
0x18000b702  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000b706  jz      loc_18000B814
0x18000b70c  mov     rbx, rsi
0x18000b70f  test    rbp, rbp
0x18000b712  jz      short loc_18000B73E
0x18000b714  mov     eax, 7FFFFFFFh
0x18000b719  mov     rbx, rbp
0x18000b71c  cmp     rsi, rax
0x18000b71f  cmovb   rax, rsi
0x18000b723  test    rax, rax
0x18000b726  jz      short loc_18000B738
0x18000b728  cmp     [rbx], r12w
0x18000b72c  jz      short loc_18000B738
0x18000b72e  add     rbx, 2
0x18000b732  sub     rax, 1
0x18000b736  jnz     short loc_18000B728
0x18000b738  sub     rbx, rbp
0x18000b73b  sar     rbx, 1
0x18000b73e  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000b742  cmovz   rsi, rbx
0x18000b746  lea     r15, ds:2[rsi*2]
0x18000b74e  mov     rcx, r15; cb
0x18000b751  call    cs:__imp_CoTaskMemAlloc
0x18000b757  mov     rdi, rax
0x18000b75a  test    rax, rax
0x18000b75d  jz      short loc_18000B7A8
0x18000b75f  test    rbp, rbp
0x18000b762  jz      short loc_18000B79F
0x18000b764  add     rbx, rbx
0x18000b767  jz      short loc_18000B798
0x18000b769  mov     rcx, rax; void *
0x18000b76c  cmp     r15, rbx
0x18000b76f  jb      short loc_18000B77E
0x18000b771  mov     r8, rbx; Size
0x18000b774  mov     rdx, rbp; Src
0x18000b777  call    memmove
0x18000b77c  jmp     short loc_18000B798
0x18000b77e  mov     r8, r15; Size
0x18000b781  xor     edx, edx; Val
0x18000b783  call    memset
0x18000b788  call    _o__errno_0
0x18000b78d  mov     dword ptr [rax], 22h ; '"'
0x18000b793  call    _invalid_parameter_noinfo
0x18000b798  mov     [rbx+rdi], r12w
0x18000b79d  jmp     short loc_18000B7A3
0x18000b79f  mov     [rax], r12w
0x18000b7a3  mov     [rdi+rsi*2], r12w
0x18000b7a8  lea     rax, [rsp+48h+var_28]
0x18000b7ad  cmp     r14, rax
0x18000b7b0  jz      short loc_18000B7D8
0x18000b7b2  mov     rsi, [r14]
0x18000b7b5  test    rsi, rsi
0x18000b7b8  jz      short loc_18000B7D3
0x18000b7ba  call    cs:__imp_GetLastError
0x18000b7c0  mov     rcx, rsi; pv
0x18000b7c3  mov     ebx, eax
0x18000b7c5  call    cs:__imp_CoTaskMemFree
0x18000b7cb  mov     ecx, ebx; dwErrCode
0x18000b7cd  call    cs:__imp_SetLastError
0x18000b7d3  mov     [r14], rdi
0x18000b7d6  jmp     short loc_18000B7E6
0x18000b7d8  test    rdi, rdi
0x18000b7db  jz      short loc_18000B7E6
0x18000b7dd  mov     rcx, rdi; pv
0x18000b7e0  call    cs:__imp_CoTaskMemFree
0x18000b7e6  mov     rax, [r14]
0x18000b7e9  mov     rbx, [rsp+48h+arg_0]
0x18000b7ee  neg     rax
0x18000b7f1  mov     rbp, [rsp+48h+arg_8]
0x18000b7f6  mov     rsi, [rsp+48h+arg_10]
0x18000b7fb  sbb     eax, eax
0x18000b7fd  mov     rdi, [rsp+48h+arg_18]
0x18000b802  not     eax
0x18000b804  and     eax, 8007000Eh
0x18000b809  add     rsp, 30h
0x18000b80d  pop     r15
0x18000b80f  pop     r14
0x18000b811  pop     r12
0x18000b813  retn
0x18000b814  mov     rcx, [rsp+48h]; this
0x18000b819  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
