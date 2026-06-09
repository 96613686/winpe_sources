# std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x180017080`
- end: `0x180017116`
- name: `??1_Reallocation_guard@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x1800171e8`

## callees

- `0x180017080`
- `0x18008ffd4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800170ab`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001710f`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18001710f`

## pseudocode

```c
void __fastcall std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>::_Reallocation_guard::~_Reallocation_guard(
        _QWORD *a1)
{
  HSTRING *v2; // rsi
  HSTRING *i; // rbx
  _QWORD *v4; // rcx
  unsigned __int64 v5; // rdx

  if ( a1[1] )
  {
    v2 = (HSTRING *)a1[4];
    for ( i = (HSTRING *)a1[3]; i != v2; ++i )
    {
      if ( *i )
        WindowsDeleteString(*i);
    }
    v4 = (_QWORD *)a1[1];
    v5 = 8LL * a1[2];
    if ( v5 >= 0x1000 )
    {
      v5 += 39LL;
      if ( (unsigned __int64)v4 - *(v4 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v4 = (_QWORD *)*(v4 - 1);
    }
    operator delete(v4, v5);
  }
}

```

## disassembly

```asm
0x180017080  mov     [rsp+arg_8], rbx
0x180017085  mov     [rsp+arg_10], rsi
0x18001708a  push    rdi
0x18001708b  sub     rsp, 30h
0x18001708f  cmp     qword ptr [rcx+8], 0
0x180017094  mov     rdi, rcx
0x180017097  jz      short loc_1800170EC
0x180017099  mov     rsi, [rcx+20h]
0x18001709d  mov     rbx, [rcx+18h]
0x1800170a1  jmp     short loc_1800170B5
0x1800170a3  mov     rcx, [rbx]; string
0x1800170a6  test    rcx, rcx
0x1800170a9  jz      short loc_1800170B1
0x1800170ab  call    cs:__imp_WindowsDeleteString
0x1800170b1  add     rbx, 8
0x1800170b5  cmp     rbx, rsi
0x1800170b8  jnz     short loc_1800170A3
0x1800170ba  mov     rdx, [rdi+10h]
0x1800170be  mov     rcx, [rdi+8]
0x1800170c2  shl     rdx, 3
0x1800170c6  cmp     rdx, 1000h
0x1800170cd  jb      short loc_1800170E7
0x1800170cf  mov     rax, [rcx-8]
0x1800170d3  add     rdx, 27h ; '''; unsigned __int64
0x1800170d7  sub     rcx, rax
0x1800170da  sub     rcx, 8
0x1800170de  cmp     rcx, 1Fh
0x1800170e2  ja      short loc_1800170FC
0x1800170e4  mov     rcx, rax; void *
0x1800170e7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800170ec  mov     rbx, [rsp+38h+arg_8]
0x1800170f1  mov     rsi, [rsp+38h+arg_10]
0x1800170f6  add     rsp, 30h
0x1800170fa  pop     rdi
0x1800170fb  retn
0x1800170fc  xor     r9d, r9d; LineNo
0x1800170ff  mov     [rsp+38h+Reserved], 0; Reserved
0x180017108  xor     r8d, r8d; FileName
0x18001710b  xor     edx, edx; FunctionName
0x18001710d  xor     ecx, ecx; Expression
0x18001710f  call    cs:__imp__invoke_watson
```
