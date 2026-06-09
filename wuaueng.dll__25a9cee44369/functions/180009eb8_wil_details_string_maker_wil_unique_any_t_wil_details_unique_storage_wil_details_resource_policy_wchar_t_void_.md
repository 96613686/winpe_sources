# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x180009eb8`
- end: `0x18000a003`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000a070`

## callees

- `0x180009e88`
- `0x180009eb8`
- `0x18000fbc2`
- `0x18000fbfe`
- `0x180015a30`
- `0x180015df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fb1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009fb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fa9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009fc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009f35`

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
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, -1, a4);
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
0x180009eb8  mov     rax, rsp
0x180009ebb  mov     [rax+8], rbx
0x180009ebf  mov     [rax+10h], rbp
0x180009ec3  mov     [rax+18h], rsi
0x180009ec7  mov     [rax+20h], rdi
0x180009ecb  push    r12
0x180009ecd  push    r14
0x180009ecf  push    r15
0x180009ed1  sub     rsp, 30h
0x180009ed5  xor     r12d, r12d
0x180009ed8  mov     rsi, r8
0x180009edb  mov     rbp, rdx
0x180009ede  mov     r14, rcx
0x180009ee1  test    rdx, rdx
0x180009ee4  jnz     short loc_180009EF0
0x180009ee6  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180009eea  jz      loc_180009FF8
0x180009ef0  mov     rbx, rsi
0x180009ef3  test    rbp, rbp
0x180009ef6  jz      short loc_180009F22
0x180009ef8  mov     eax, 7FFFFFFFh
0x180009efd  mov     rbx, rbp
0x180009f00  cmp     rsi, rax
0x180009f03  cmovb   rax, rsi
0x180009f07  test    rax, rax
0x180009f0a  jz      short loc_180009F1C
0x180009f0c  cmp     [rbx], r12w
0x180009f10  jz      short loc_180009F1C
0x180009f12  add     rbx, 2
0x180009f16  sub     rax, 1
0x180009f1a  jnz     short loc_180009F0C
0x180009f1c  sub     rbx, rbp
0x180009f1f  sar     rbx, 1
0x180009f22  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180009f26  cmovz   rsi, rbx
0x180009f2a  lea     r15, ds:2[rsi*2]
0x180009f32  mov     rcx, r15; cb
0x180009f35  call    cs:__imp_CoTaskMemAlloc
0x180009f3b  mov     rdi, rax
0x180009f3e  test    rax, rax
0x180009f41  jz      short loc_180009F8C
0x180009f43  test    rbp, rbp
0x180009f46  jz      short loc_180009F83
0x180009f48  add     rbx, rbx
0x180009f4b  jz      short loc_180009F7C
0x180009f4d  mov     rcx, rax; void *
0x180009f50  cmp     r15, rbx
0x180009f53  jb      short loc_180009F62
0x180009f55  mov     r8, rbx; Size
0x180009f58  mov     rdx, rbp; Src
0x180009f5b  call    memmove
0x180009f60  jmp     short loc_180009F7C
0x180009f62  mov     r8, r15; Size
0x180009f65  xor     edx, edx; Val
0x180009f67  call    memset
0x180009f6c  call    _o__errno_0
0x180009f71  mov     dword ptr [rax], 22h ; '"'
0x180009f77  call    _invalid_parameter_noinfo
0x180009f7c  mov     [rbx+rdi], r12w
0x180009f81  jmp     short loc_180009F87
0x180009f83  mov     [rax], r12w
0x180009f87  mov     [rdi+rsi*2], r12w
0x180009f8c  lea     rax, [rsp+48h+var_28]
0x180009f91  cmp     r14, rax
0x180009f94  jz      short loc_180009FBC
0x180009f96  mov     rsi, [r14]
0x180009f99  test    rsi, rsi
0x180009f9c  jz      short loc_180009FB7
0x180009f9e  call    cs:__imp_GetLastError
0x180009fa4  mov     rcx, rsi; pv
0x180009fa7  mov     ebx, eax
0x180009fa9  call    cs:__imp_CoTaskMemFree
0x180009faf  mov     ecx, ebx; dwErrCode
0x180009fb1  call    cs:__imp_SetLastError
0x180009fb7  mov     [r14], rdi
0x180009fba  jmp     short loc_180009FCA
0x180009fbc  test    rdi, rdi
0x180009fbf  jz      short loc_180009FCA
0x180009fc1  mov     rcx, rdi; pv
0x180009fc4  call    cs:__imp_CoTaskMemFree
0x180009fca  mov     rax, [r14]
0x180009fcd  mov     rbx, [rsp+48h+arg_0]
0x180009fd2  neg     rax
0x180009fd5  mov     rbp, [rsp+48h+arg_8]
0x180009fda  mov     rsi, [rsp+48h+arg_10]
0x180009fdf  sbb     eax, eax
0x180009fe1  mov     rdi, [rsp+48h+arg_18]
0x180009fe6  not     eax
0x180009fe8  and     eax, 8007000Eh
0x180009fed  add     rsp, 30h
0x180009ff1  pop     r15
0x180009ff3  pop     r14
0x180009ff5  pop     r12
0x180009ff7  retn
0x180009ff8  mov     rcx, [rsp+48h]; this
0x180009ffd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
