# wil::details::string_maker<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::make(ushort const *,unsigned __int64)

- ea: `0x14000a418`
- end: `0x14000a54b`
- name: `?make@?$string_maker@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAJPEBG_K@Z`
- size: `307`
- prototype: `__int64 __fastcall(char *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400065f4`

## callees

- `0x140002bb2`
- `0x140002c38`
- `0x140009cb4`
- `0x14000a418`
- `0x14000ac74`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a4c3`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x14000a4c3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a509`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000a509`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a51c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000a51c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a48c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x14000a48c`

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
    wil::details::in1diag3::_FailFast_Unexpected(retaddr, 0, 0xFFFFFFFF, a4);
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
0x14000a418  push    rbx
0x14000a41a  push    rbp
0x14000a41b  push    rsi
0x14000a41c  push    rdi
0x14000a41d  push    r12
0x14000a41f  push    r14
0x14000a421  push    r15
0x14000a423  sub     rsp, 30h
0x14000a427  xor     r12d, r12d
0x14000a42a  mov     rsi, r8
0x14000a42d  mov     rbp, rdx
0x14000a430  mov     r14, rcx
0x14000a433  test    rdx, rdx
0x14000a436  jnz     short loc_14000A442
0x14000a438  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x14000a43c  jz      loc_14000A540
0x14000a442  test    rbp, rbp
0x14000a445  jz      short loc_14000A476
0x14000a447  mov     ecx, 7FFFFFFFh
0x14000a44c  mov     rax, rsi
0x14000a44f  cmp     rsi, rcx
0x14000a452  mov     rbx, rbp
0x14000a455  cmovnb  rax, rcx
0x14000a459  test    rax, rax
0x14000a45c  jz      short loc_14000A46E
0x14000a45e  cmp     [rbx], r12w
0x14000a462  jz      short loc_14000A46E
0x14000a464  add     rbx, 2
0x14000a468  sub     rax, 1
0x14000a46c  jnz     short loc_14000A45E
0x14000a46e  sub     rbx, rbp
0x14000a471  sar     rbx, 1
0x14000a474  jmp     short loc_14000A479
0x14000a476  mov     rbx, rsi
0x14000a479  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x14000a47d  cmovz   rsi, rbx
0x14000a481  lea     r15, ds:2[rsi*2]
0x14000a489  mov     rcx, r15; cb
0x14000a48c  call    cs:__imp_CoTaskMemAlloc
0x14000a492  mov     rdi, rax
0x14000a495  test    rax, rax
0x14000a498  jz      short loc_14000A4E4
0x14000a49a  test    rbp, rbp
0x14000a49d  jz      short loc_14000A4DB
0x14000a49f  add     rbx, rbx
0x14000a4a2  jz      short loc_14000A4D4
0x14000a4a4  mov     rcx, rax; void *
0x14000a4a7  cmp     r15, rbx
0x14000a4aa  jb      short loc_14000A4B9
0x14000a4ac  mov     r8, rbx; Size
0x14000a4af  mov     rdx, rbp; Src
0x14000a4b2  call    memcpy_0
0x14000a4b7  jmp     short loc_14000A4D4
0x14000a4b9  mov     r8, r15; Size
0x14000a4bc  xor     edx, edx; Val
0x14000a4be  call    memset_0
0x14000a4c3  call    cs:__imp__o__errno
0x14000a4c9  mov     dword ptr [rax], 22h ; '"'
0x14000a4cf  call    _invalid_parameter_noinfo
0x14000a4d4  mov     [rbx+rdi], r12w
0x14000a4d9  jmp     short loc_14000A4DF
0x14000a4db  mov     [rax], r12w
0x14000a4df  mov     [rdi+rsi*2], r12w
0x14000a4e4  lea     rax, [rsp+68h+var_48]
0x14000a4e9  cmp     r14, rax
0x14000a4ec  jz      short loc_14000A514
0x14000a4ee  mov     rsi, [r14]
0x14000a4f1  test    rsi, rsi
0x14000a4f4  jz      short loc_14000A50F
0x14000a4f6  call    cs:__imp_GetLastError
0x14000a4fc  mov     rcx, rsi; pv
0x14000a4ff  mov     ebx, eax
0x14000a501  call    cs:__imp_CoTaskMemFree
0x14000a507  mov     ecx, ebx; dwErrCode
0x14000a509  call    cs:__imp_SetLastError
0x14000a50f  mov     [r14], rdi
0x14000a512  jmp     short loc_14000A522
0x14000a514  test    rdi, rdi
0x14000a517  jz      short loc_14000A522
0x14000a519  mov     rcx, rdi; pv
0x14000a51c  call    cs:__imp_CoTaskMemFree
0x14000a522  mov     rax, [r14]
0x14000a525  neg     rax
0x14000a528  sbb     eax, eax
0x14000a52a  not     eax
0x14000a52c  and     eax, 8007000Eh
0x14000a531  add     rsp, 30h
0x14000a535  pop     r15
0x14000a537  pop     r14
0x14000a539  pop     r12
0x14000a53b  pop     rdi
0x14000a53c  pop     rsi
0x14000a53d  pop     rbp
0x14000a53e  pop     rbx
0x14000a53f  retn
0x14000a540  mov     rcx, [rsp+68h]; this
0x14000a545  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
