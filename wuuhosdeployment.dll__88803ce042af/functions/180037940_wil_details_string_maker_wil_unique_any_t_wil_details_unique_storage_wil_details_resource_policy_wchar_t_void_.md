# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x180037940`
- end: `0x180037a8b`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180037350`
- `0x18003753c`

## callees

- `0x180009e08`
- `0x180037940`
- `0x180042547`
- `0x180042583`
- `0x1800492e0`
- `0x1800496a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037a39`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037a39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037a26`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037a4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800379bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800379bd`

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
0x180037940  mov     rax, rsp
0x180037943  mov     [rax+8], rbx
0x180037947  mov     [rax+10h], rbp
0x18003794b  mov     [rax+18h], rsi
0x18003794f  mov     [rax+20h], rdi
0x180037953  push    r12
0x180037955  push    r14
0x180037957  push    r15
0x180037959  sub     rsp, 30h
0x18003795d  xor     r12d, r12d
0x180037960  mov     rsi, r8
0x180037963  mov     rbp, rdx
0x180037966  mov     r14, rcx
0x180037969  test    rdx, rdx
0x18003796c  jnz     short loc_180037978
0x18003796e  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180037972  jz      loc_180037A80
0x180037978  mov     rbx, rsi
0x18003797b  test    rbp, rbp
0x18003797e  jz      short loc_1800379AA
0x180037980  mov     eax, 7FFFFFFFh
0x180037985  mov     rbx, rbp
0x180037988  cmp     rsi, rax
0x18003798b  cmovb   rax, rsi
0x18003798f  test    rax, rax
0x180037992  jz      short loc_1800379A4
0x180037994  cmp     [rbx], r12w
0x180037998  jz      short loc_1800379A4
0x18003799a  add     rbx, 2
0x18003799e  sub     rax, 1
0x1800379a2  jnz     short loc_180037994
0x1800379a4  sub     rbx, rbp
0x1800379a7  sar     rbx, 1
0x1800379aa  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800379ae  cmovz   rsi, rbx
0x1800379b2  lea     r15, ds:2[rsi*2]
0x1800379ba  mov     rcx, r15; cb
0x1800379bd  call    cs:__imp_CoTaskMemAlloc
0x1800379c3  mov     rdi, rax
0x1800379c6  test    rax, rax
0x1800379c9  jz      short loc_180037A14
0x1800379cb  test    rbp, rbp
0x1800379ce  jz      short loc_180037A0B
0x1800379d0  add     rbx, rbx
0x1800379d3  jz      short loc_180037A04
0x1800379d5  mov     rcx, rax; void *
0x1800379d8  cmp     r15, rbx
0x1800379db  jb      short loc_1800379EA
0x1800379dd  mov     r8, rbx; Size
0x1800379e0  mov     rdx, rbp; Src
0x1800379e3  call    memmove
0x1800379e8  jmp     short loc_180037A04
0x1800379ea  mov     r8, r15; Size
0x1800379ed  xor     edx, edx; Val
0x1800379ef  call    memset
0x1800379f4  call    _o__errno_0
0x1800379f9  mov     dword ptr [rax], 22h ; '"'
0x1800379ff  call    _invalid_parameter_noinfo
0x180037a04  mov     [rbx+rdi], r12w
0x180037a09  jmp     short loc_180037A0F
0x180037a0b  mov     [rax], r12w
0x180037a0f  mov     [rdi+rsi*2], r12w
0x180037a14  lea     rax, [rsp+48h+var_28]
0x180037a19  cmp     r14, rax
0x180037a1c  jz      short loc_180037A44
0x180037a1e  mov     rsi, [r14]
0x180037a21  test    rsi, rsi
0x180037a24  jz      short loc_180037A3F
0x180037a26  call    cs:__imp_GetLastError
0x180037a2c  mov     rcx, rsi; pv
0x180037a2f  mov     ebx, eax
0x180037a31  call    cs:__imp_CoTaskMemFree
0x180037a37  mov     ecx, ebx; dwErrCode
0x180037a39  call    cs:__imp_SetLastError
0x180037a3f  mov     [r14], rdi
0x180037a42  jmp     short loc_180037A52
0x180037a44  test    rdi, rdi
0x180037a47  jz      short loc_180037A52
0x180037a49  mov     rcx, rdi; pv
0x180037a4c  call    cs:__imp_CoTaskMemFree
0x180037a52  mov     rax, [r14]
0x180037a55  mov     rbx, [rsp+48h+arg_0]
0x180037a5a  neg     rax
0x180037a5d  mov     rbp, [rsp+48h+arg_8]
0x180037a62  mov     rsi, [rsp+48h+arg_10]
0x180037a67  sbb     eax, eax
0x180037a69  mov     rdi, [rsp+48h+arg_18]
0x180037a6e  not     eax
0x180037a70  and     eax, 8007000Eh
0x180037a75  add     rsp, 30h
0x180037a79  pop     r15
0x180037a7b  pop     r14
0x180037a7d  pop     r12
0x180037a7f  retn
0x180037a80  mov     rcx, [rsp+48h]; this
0x180037a85  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
