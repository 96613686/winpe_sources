# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::_Change_array(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> * const,unsigned __int64,unsigned __int64)

- ea: `0x18001711c`
- end: `0x1800171df`
- name: `?_Change_array@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAXQEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_K1@Z`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180016fe0`
- `0x1800171e8`

## callees

- `0x18001711c`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017156`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017156`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800171d8`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800171d8`

## pseudocode

```c
__int64 __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Change_array(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  HSTRING *v4; // rbx
  HSTRING *v9; // rbp
  HSTRING *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 result; // rax

  v4 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    v9 = *(HSTRING **)(a1 + 8);
    while ( v4 != v9 )
    {
      if ( *v4 )
        WindowsDeleteString(*v4);
      ++v4;
    }
    v10 = *(HSTRING **)a1;
    v11 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v11 >= 0x1000 )
    {
      v11 += 39LL;
      if ( (unsigned __int64)((char *)v10 - (char *)*(v10 - 1) - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v10 = (HSTRING *)*(v10 - 1);
    }
    operator delete(v10, v11);
  }
  *(_QWORD *)a1 = a2;
  *(_QWORD *)(a1 + 8) = a2 + 8 * a3;
  result = a2 + 8 * a4;
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x18001711c  mov     [rsp+arg_8], rbx
0x180017121  mov     [rsp+arg_10], rbp
0x180017126  mov     [rsp+arg_18], rsi
0x18001712b  push    rdi
0x18001712c  push    r14
0x18001712e  push    r15
0x180017130  sub     rsp, 30h
0x180017134  mov     rbx, [rcx]
0x180017137  mov     r14, r9
0x18001713a  mov     r15, r8
0x18001713d  mov     rsi, rdx
0x180017140  mov     rdi, rcx
0x180017143  test    rbx, rbx
0x180017146  jz      short loc_180017199
0x180017148  mov     rbp, [rcx+8]
0x18001714c  jmp     short loc_180017160
0x18001714e  mov     rcx, [rbx]; string
0x180017151  test    rcx, rcx
0x180017154  jz      short loc_18001715C
0x180017156  call    cs:__imp_WindowsDeleteString
0x18001715c  add     rbx, 8
0x180017160  cmp     rbx, rbp
0x180017163  jnz     short loc_18001714E
0x180017165  mov     rcx, [rdi]
0x180017168  mov     rdx, [rdi+10h]
0x18001716c  sub     rdx, rcx
0x18001716f  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180017173  cmp     rdx, 1000h
0x18001717a  jb      short loc_180017194
0x18001717c  mov     rax, [rcx-8]
0x180017180  add     rdx, 27h ; '''; unsigned __int64
0x180017184  sub     rcx, rax
0x180017187  sub     rcx, 8
0x18001718b  cmp     rcx, 1Fh
0x18001718f  ja      short loc_1800171C5
0x180017191  mov     rcx, rax; void *
0x180017194  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180017199  mov     rbx, [rsp+48h+arg_8]
0x18001719e  lea     rax, [rsi+r15*8]
0x1800171a2  mov     rbp, [rsp+48h+arg_10]
0x1800171a7  mov     [rdi], rsi
0x1800171aa  mov     [rdi+8], rax
0x1800171ae  lea     rax, [rsi+r14*8]
0x1800171b2  mov     rsi, [rsp+48h+arg_18]
0x1800171b7  mov     [rdi+10h], rax
0x1800171bb  add     rsp, 30h
0x1800171bf  pop     r15
0x1800171c1  pop     r14
0x1800171c3  pop     rdi
0x1800171c4  retn
0x1800171c5  xor     r9d, r9d; LineNo
0x1800171c8  mov     [rsp+48h+Reserved], 0; Reserved
0x1800171d1  xor     r8d, r8d; FileName
0x1800171d4  xor     edx, edx; FunctionName
0x1800171d6  xor     ecx, ecx; Expression
0x1800171d8  call    cs:__imp__invoke_watson
```
