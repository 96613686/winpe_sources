# wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)

- ea: `0x1800194b0`
- end: `0x18001951c`
- name: `??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z`
- size: `108`
- prototype: `HSTRING *__fastcall(HSTRING *string, PCNZWCH sourceString, __int64 length)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180019150`
- `0x180019270`
- `0x180019390`
- `0x180039e64`
- `0x18003a5d8`
- `0x18003a8a8`
- `0x18003ab5c`

## callees

- `0x1800194b0`
- `0x180019524`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800194f0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800194f0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
HSTRING *__fastcall wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
        HSTRING *string,
        PCNZWCH sourceString,
        __int64 length)
{
  __int64 v3; // rax
  void *v5; // rdx
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  LODWORD(v3) = length;
  *string = 0;
  if ( length == -1 )
  {
    v3 = -1;
    do
      ++v3;
    while ( sourceString[v3] );
  }
  *string = 0;
  WindowsCreateString(sourceString, v3, string);
  if ( !*string )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v5, v6, v7);
  return string;
}

```

## disassembly

```asm
0x1800194b0  mov     [rsp+arg_18], rbx
0x1800194b5  push    rdi
0x1800194b6  sub     rsp, 30h
0x1800194ba  mov     rax, r8
0x1800194bd  mov     r9, rdx
0x1800194c0  mov     rbx, rcx
0x1800194c3  mov     [rsp+38h+var_10], rcx
0x1800194c8  xor     edi, edi
0x1800194ca  mov     [rsp+38h+var_18], edi
0x1800194ce  xor     ecx, ecx
0x1800194d0  mov     [rbx], rcx
0x1800194d3  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800194d7  jnz     short loc_1800194E5
0x1800194d9  or      rax, r8
0x1800194dc  inc     rax
0x1800194df  cmp     [rdx+rax*2], di
0x1800194e3  jnz     short loc_1800194DC
0x1800194e5  mov     [rbx], rdi
0x1800194e8  mov     r8, rbx; string
0x1800194eb  mov     edx, eax; length
0x1800194ed  mov     rcx, r9; sourceString
0x1800194f0  call    cs:__imp_WindowsCreateString
0x1800194f6  mov     [rsp+38h+var_18], 1
0x1800194fe  cmp     [rbx], rdi
0x180019501  jz      short loc_180019511
0x180019503  mov     rax, rbx
0x180019506  mov     rbx, [rsp+38h+arg_18]
0x18001950b  add     rsp, 30h
0x18001950f  pop     rdi
0x180019510  retn
0x180019511  mov     rcx, [rsp+38h]; this
0x180019516  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
