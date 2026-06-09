# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::make(wchar_t const *,unsigned __int64)

- ea: `0x180024dac`
- end: `0x180024ef7`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEB_W_K@Z`
- size: `331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018f44`
- `0x18003deb0`

## callees

- `0x180024dac`
- `0x180026c18`
- `0x1800424e6`
- `0x18004255e`
- `0x180047ab0`
- `0x180047e70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024e92`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ea5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180024ea5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180024e29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024eb8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024e9d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024eb8`

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
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  void *v16; // rsi
  DWORD LastError; // ebx
  char v19; // [rsp+20h] [rbp-28h] BYREF
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
          *(_DWORD *)o__errno_0(v14, v13, v15) = 34;
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
  if ( a1 == &v19 )
  {
    if ( v11 )
      CoTaskMemFree(v11);
  }
  else
  {
    v16 = *(void **)a1;
    if ( *(_QWORD *)a1 )
    {
      LastError = GetLastError();
      CoTaskMemFree(v16);
      SetLastError(LastError);
    }
    *(_QWORD *)a1 = v11;
  }
  return *(_QWORD *)a1 == 0 ? 0x8007000E : 0;
}

```

## disassembly

```asm
0x180024dac  mov     rax, rsp
0x180024daf  mov     [rax+8], rbx
0x180024db3  mov     [rax+10h], rbp
0x180024db7  mov     [rax+18h], rsi
0x180024dbb  mov     [rax+20h], rdi
0x180024dbf  push    r12
0x180024dc1  push    r14
0x180024dc3  push    r15
0x180024dc5  sub     rsp, 30h
0x180024dc9  xor     r12d, r12d
0x180024dcc  mov     rsi, r8
0x180024dcf  mov     rbp, rdx
0x180024dd2  mov     r14, rcx
0x180024dd5  test    rdx, rdx
0x180024dd8  jnz     short loc_180024DE4
0x180024dda  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180024dde  jz      loc_180024EEC
0x180024de4  mov     rbx, rsi
0x180024de7  test    rbp, rbp
0x180024dea  jz      short loc_180024E16
0x180024dec  mov     eax, 7FFFFFFFh
0x180024df1  mov     rbx, rbp
0x180024df4  cmp     rsi, rax
0x180024df7  cmovb   rax, rsi
0x180024dfb  test    rax, rax
0x180024dfe  jz      short loc_180024E10
0x180024e00  cmp     [rbx], r12w
0x180024e04  jz      short loc_180024E10
0x180024e06  add     rbx, 2
0x180024e0a  sub     rax, 1
0x180024e0e  jnz     short loc_180024E00
0x180024e10  sub     rbx, rbp
0x180024e13  sar     rbx, 1
0x180024e16  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180024e1a  cmovz   rsi, rbx
0x180024e1e  lea     r15, ds:2[rsi*2]
0x180024e26  mov     rcx, r15; cb
0x180024e29  call    cs:__imp_CoTaskMemAlloc
0x180024e2f  mov     rdi, rax
0x180024e32  test    rax, rax
0x180024e35  jz      short loc_180024E80
0x180024e37  test    rbp, rbp
0x180024e3a  jz      short loc_180024E77
0x180024e3c  add     rbx, rbx
0x180024e3f  jz      short loc_180024E70
0x180024e41  mov     rcx, rax; void *
0x180024e44  cmp     r15, rbx
0x180024e47  jb      short loc_180024E56
0x180024e49  mov     r8, rbx; Size
0x180024e4c  mov     rdx, rbp; Src
0x180024e4f  call    memmove
0x180024e54  jmp     short loc_180024E70
0x180024e56  mov     r8, r15; Size
0x180024e59  xor     edx, edx; Val
0x180024e5b  call    memset
0x180024e60  call    _o__errno_0
0x180024e65  mov     dword ptr [rax], 22h ; '"'
0x180024e6b  call    _invalid_parameter_noinfo
0x180024e70  mov     [rbx+rdi], r12w
0x180024e75  jmp     short loc_180024E7B
0x180024e77  mov     [rax], r12w
0x180024e7b  mov     [rdi+rsi*2], r12w
0x180024e80  lea     rax, [rsp+48h+var_28]
0x180024e85  cmp     r14, rax
0x180024e88  jz      short loc_180024EB0
0x180024e8a  mov     rsi, [r14]
0x180024e8d  test    rsi, rsi
0x180024e90  jz      short loc_180024EAB
0x180024e92  call    cs:__imp_GetLastError
0x180024e98  mov     rcx, rsi; pv
0x180024e9b  mov     ebx, eax
0x180024e9d  call    cs:__imp_CoTaskMemFree
0x180024ea3  mov     ecx, ebx; dwErrCode
0x180024ea5  call    cs:__imp_SetLastError
0x180024eab  mov     [r14], rdi
0x180024eae  jmp     short loc_180024EBE
0x180024eb0  test    rdi, rdi
0x180024eb3  jz      short loc_180024EBE
0x180024eb5  mov     rcx, rdi; pv
0x180024eb8  call    cs:__imp_CoTaskMemFree
0x180024ebe  mov     rax, [r14]
0x180024ec1  mov     rbx, [rsp+48h+arg_0]
0x180024ec6  neg     rax
0x180024ec9  mov     rbp, [rsp+48h+arg_8]
0x180024ece  mov     rsi, [rsp+48h+arg_10]
0x180024ed3  sbb     eax, eax
0x180024ed5  mov     rdi, [rsp+48h+arg_18]
0x180024eda  not     eax
0x180024edc  and     eax, 8007000Eh
0x180024ee1  add     rsp, 30h
0x180024ee5  pop     r15
0x180024ee7  pop     r14
0x180024ee9  pop     r12
0x180024eeb  retn
0x180024eec  mov     rcx, [rsp+48h]; this
0x180024ef1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
