# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>(void)

- ea: `0x180017450`
- end: `0x1800174fc`
- name: `??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `172`
- prototype: `void __fastcall(__int64)`
- caller_count: `7`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180016e7c`
- `0x18001759c`
- `0x18003a5d8`
- `0x180098151`
- `0x180098199`
- `0x1800981c5`
- `0x18009a35c`

## callees

- `0x180017450`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017478`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017478`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800174f5`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800174f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  HSTRING *v1; // rbx
  HSTRING *v3; // rsi
  HSTRING *v4; // rcx
  unsigned __int64 v5; // rdx

  v1 = *(HSTRING **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(HSTRING **)(a1 + 8);
    while ( v1 != v3 )
    {
      if ( *v1 )
        WindowsDeleteString(*v1);
      ++v1;
    }
    v4 = *(HSTRING **)a1;
    v5 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v5 >= 0x1000 )
    {
      v5 += 39LL;
      if ( (unsigned __int64)((char *)v4 - (char *)*(v4 - 1) - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (HSTRING *)*(v4 - 1);
    }
    operator delete(v4, v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180017450  mov     [rsp+arg_8], rbx
0x180017455  mov     [rsp+arg_10], rsi
0x18001745a  push    rdi
0x18001745b  sub     rsp, 30h
0x18001745f  mov     rbx, [rcx]
0x180017462  mov     rdi, rcx
0x180017465  test    rbx, rbx
0x180017468  jz      short loc_1800174D2
0x18001746a  mov     rsi, [rcx+8]
0x18001746e  jmp     short loc_180017482
0x180017470  mov     rcx, [rbx]; string
0x180017473  test    rcx, rcx
0x180017476  jz      short loc_18001747E
0x180017478  call    cs:__imp_WindowsDeleteString
0x18001747e  add     rbx, 8
0x180017482  cmp     rbx, rsi
0x180017485  jnz     short loc_180017470
0x180017487  mov     rcx, [rdi]
0x18001748a  mov     rdx, [rdi+10h]
0x18001748e  sub     rdx, rcx
0x180017491  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180017495  cmp     rdx, 1000h
0x18001749c  jb      short loc_1800174B6
0x18001749e  mov     rax, [rcx-8]
0x1800174a2  add     rdx, 27h ; '''; unsigned __int64
0x1800174a6  sub     rcx, rax
0x1800174a9  sub     rcx, 8
0x1800174ad  cmp     rcx, 1Fh
0x1800174b1  ja      short loc_1800174E2
0x1800174b3  mov     rcx, rax; void *
0x1800174b6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800174bb  mov     qword ptr [rdi], 0
0x1800174c2  mov     qword ptr [rdi+8], 0
0x1800174ca  mov     qword ptr [rdi+10h], 0
0x1800174d2  mov     rbx, [rsp+38h+arg_8]
0x1800174d7  mov     rsi, [rsp+38h+arg_10]
0x1800174dc  add     rsp, 30h
0x1800174e0  pop     rdi
0x1800174e1  retn
0x1800174e2  xor     r9d, r9d; LineNo
0x1800174e5  mov     [rsp+38h+Reserved], 0; Reserved
0x1800174ee  xor     r8d, r8d; FileName
0x1800174f1  xor     edx, edx; FunctionName
0x1800174f3  xor     ecx, ecx; Expression
0x1800174f5  call    cs:__imp__invoke_watson
```
