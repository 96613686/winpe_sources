# tip2::details::shared_data<0,0,1>::log(char const *)

- ea: `0x180049ec4`
- end: `0x180049fa0`
- name: `?log@?$shared_data@$0A@$0A@$00@details@tip2@@QEAAXPEBD@Z`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180049fa8`

## callees

- `0x18000a1f0`
- `0x180012c68`
- `0x180019c88`
- `0x180049ec4`
- `0x18004a05c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049ef1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180049ef1`

## string_xrefs

- `0x180049f8e`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
void __fastcall tip2::details::shared_data<0,0,1>::log(__int64 a1, _BYTE *a2, __int64 a3, const char *a4)
{
  rsize_t v6; // rdi
  _BYTE *v7; // rax
  _BYTE *v8; // r14
  unsigned __int64 v9; // rcx
  __int64 v10; // rdx
  char v11; // di
  __int64 v12; // rcx
  __int64 v13; // rax
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  void *v15; // [rsp+60h] [rbp+8h] BYREF

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = CoTaskMemAlloc(v6 + 1);
  v8 = v7;
  if ( v7 )
  {
    memcpy_s(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  v9 = *(_QWORD *)(a1 + 104);
  v15 = v8;
  if ( *(_QWORD *)(a1 + 112) < v9 )
    goto LABEL_11;
  v10 = 2 * v9;
  if ( !v9 )
    v10 = 10;
  if ( (unsigned __int8)tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(
                          a1 + 96,
                          v10) )
  {
LABEL_11:
    v12 = *(_QWORD *)(a1 + 112);
    v11 = 0;
    v13 = *(_QWORD *)(a1 + 96);
    v15 = 0;
    *(_QWORD *)(v13 + 8 * v12) = v8;
    ++*(_QWORD *)(a1 + 112);
  }
  else
  {
    v11 = 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v15);
  if ( v11 )
    *(_DWORD *)(a1 + 64) |= 0x100000u;
}

```

## disassembly

```asm
0x180049ec4  push    rbx
0x180049ec6  push    rbp
0x180049ec7  push    rsi
0x180049ec8  push    rdi
0x180049ec9  push    r14
0x180049ecb  push    r15
0x180049ecd  sub     rsp, 28h
0x180049ed1  mov     rbp, rdx
0x180049ed4  mov     rsi, rcx
0x180049ed7  test    rdx, rdx
0x180049eda  jz      loc_180049F89
0x180049ee0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180049ee4  inc     rdi
0x180049ee7  cmp     byte ptr [rdi+rdx], 0
0x180049eeb  jnz     short loc_180049EE4
0x180049eed  lea     rcx, [rdi+1]; cb
0x180049ef1  call    cs:__imp_CoTaskMemAlloc
0x180049ef7  mov     r14, rax
0x180049efa  test    rax, rax
0x180049efd  jz      short loc_180049F16
0x180049eff  mov     r9, rdi; SourceSize
0x180049f02  lea     rdx, [rdi+1]; DestinationSize
0x180049f06  mov     r8, rbp; Source
0x180049f09  mov     rcx, rax; Destination
0x180049f0c  call    memcpy_s
0x180049f11  mov     byte ptr [rdi+r14], 0
0x180049f16  mov     rcx, [rsi+68h]
0x180049f1a  mov     [rsp+58h+arg_0], r14
0x180049f1f  cmp     [rsi+70h], rcx
0x180049f23  jb      short loc_180049F47
0x180049f25  lea     rdx, [rcx+rcx]
0x180049f29  test    rcx, rcx
0x180049f2c  jnz     short loc_180049F33
0x180049f2e  mov     edx, 0Ah
0x180049f33  lea     rcx, [rsi+60h]
0x180049f37  call    ?reserve@?$vector_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@tip2@@QEAA_N_K@Z; tip2::vector_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x180049f3c  test    al, al
0x180049f3e  jnz     short loc_180049F47
0x180049f40  mov     edi, 1
0x180049f45  jmp     short loc_180049F68
0x180049f47  mov     rcx, [rsi+70h]
0x180049f4b  mov     edi, 1
0x180049f50  mov     rax, [rsi+60h]
0x180049f54  mov     [rsp+58h+arg_0], 0
0x180049f5d  mov     [rax+rcx*8], r14
0x180049f61  add     [rsi+70h], rdi
0x180049f65  xor     dil, dil
0x180049f68  lea     rcx, [rsp+58h+arg_0]
0x180049f6d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180049f72  test    dil, dil
0x180049f75  jz      short loc_180049F7C
0x180049f77  bts     dword ptr [rsi+40h], 14h
0x180049f7c  add     rsp, 28h
0x180049f80  pop     r15
0x180049f82  pop     r14
0x180049f84  pop     rdi
0x180049f85  pop     rsi
0x180049f86  pop     rbp
0x180049f87  pop     rbx
0x180049f88  retn
0x180049f89  mov     rcx, [rsp+58h]; this
0x180049f8e  lea     r8, aOnecoreInterna_5; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180049f95  mov     edx, 0FBDh; void *
0x180049f9a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
