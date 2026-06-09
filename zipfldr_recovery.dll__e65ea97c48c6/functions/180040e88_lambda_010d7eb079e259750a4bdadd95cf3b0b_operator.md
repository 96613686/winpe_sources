# _lambda_010d7eb079e259750a4bdadd95cf3b0b_::operator()

- ea: `0x180040e88`
- end: `0x180040f9b`
- name: `_lambda_010d7eb079e259750a4bdadd95cf3b0b_::operator()`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x1800407d0`

## callees

- `0x180031e94`
- `0x180040d0c`
- `0x180040e20`
- `0x180040e88`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x180040ea9`
- `SHLWAPI!PathFindFileNameW` at `0x180040f02`
- `SHLWAPI!PathFindFileNameW` at `0x180040f3e`
- `SHLWAPI!PathFindFileNameW` at `0x180040ea9`
- `SHLWAPI!PathFindFileNameW` at `0x180040f02`
- `SHLWAPI!PathFindFileNameW` at `0x180040f3e`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180040f7a`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180040f7a`
- `SHLWAPI!PathStripPathW` at `0x180040f83`
- `SHLWAPI!PathStripPathW` at `0x180040f83`

## pseudocode

```c
__int64 __fastcall lambda_010d7eb079e259750a4bdadd95cf3b0b_::operator()(__int64 a1, LPCWSTR *a2, __int64 a3)
{
  LPWSTR FileNameW; // rax
  __int64 v6; // rdx
  LPWSTR v8; // rax
  LPWSTR v9; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  __int64 v11; // [rsp+30h] [rbp+10h] BYREF

  v11 = a1;
  FileNameW = PathFindFileNameW(a2[1]);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v11,
    FileNameW);
  *(_QWORD *)(a3 + 8) = v11;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  if ( !*(_QWORD *)(a3 + 8) )
  {
    v6 = 795;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"shell\\ext\\zip\\dropin.cpp",
      (const char *)0x8007000ELL);
    return 2147942414LL;
  }
  v8 = PathFindFileNameW(*a2);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v11,
    v8);
  *(_QWORD *)(a3 + 8) = v11;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  if ( !*(_QWORD *)(a3 + 16) )
  {
    v6 = 798;
    goto LABEL_3;
  }
  v9 = PathFindFileNameW(*a2);
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v11,
    v9);
  *(_QWORD *)a3 = v11;
  v11 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v11);
  if ( !*(_QWORD *)a3 )
  {
    v6 = 801;
    goto LABEL_3;
  }
  PathRemoveFileSpecW(*(LPWSTR *)a3);
  PathStripPathW(*(LPWSTR *)a3);
  return 0;
}

```

## disassembly

```asm
0x180040e88  mov     [rsp-8+arg_8], rbx
0x180040e8d  mov     [rsp-8+arg_10], rdi
0x180040e92  mov     [rsp-8+arg_0], rcx
0x180040e97  push    rbp
0x180040e98  mov     rbp, rsp
0x180040e9b  sub     rsp, 20h
0x180040e9f  mov     rcx, [rdx+8]; pszPath
0x180040ea3  mov     rbx, r8
0x180040ea6  mov     rdi, rdx
0x180040ea9  call    cs:__imp_PathFindFileNameW
0x180040eaf  mov     rdx, rax
0x180040eb2  lea     rcx, [rbp+arg_0]
0x180040eb6  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180040ebb  mov     rax, [rbp+arg_0]
0x180040ebf  lea     rcx, [rbp+arg_0]
0x180040ec3  mov     [rbx+8], rax
0x180040ec7  mov     [rbp+arg_0], 0
0x180040ecf  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040ed4  cmp     qword ptr [rbx+8], 0
0x180040ed9  jnz     short loc_180040EFF
0x180040edb  mov     edx, 31Bh
0x180040ee0  mov     rcx, [rbp+8]
0x180040ee4  lea     r8, aShellExtZipDro; "shell\\ext\\zip\\dropin.cpp"
0x180040eeb  mov     ebx, 8007000Eh
0x180040ef0  mov     r9d, ebx
0x180040ef3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040ef8  mov     eax, ebx
0x180040efa  jmp     loc_180040F8B
0x180040eff  mov     rcx, [rdi]; pszPath
0x180040f02  call    cs:__imp_PathFindFileNameW
0x180040f08  mov     rdx, rax
0x180040f0b  lea     rcx, [rbp+arg_0]
0x180040f0f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180040f14  mov     rax, [rbp+arg_0]
0x180040f18  lea     rcx, [rbp+arg_0]
0x180040f1c  mov     [rbx+8], rax
0x180040f20  mov     [rbp+arg_0], 0
0x180040f28  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040f2d  cmp     qword ptr [rbx+10h], 0
0x180040f32  jnz     short loc_180040F3B
0x180040f34  mov     edx, 31Eh
0x180040f39  jmp     short loc_180040EE0
0x180040f3b  mov     rcx, [rdi]; pszPath
0x180040f3e  call    cs:__imp_PathFindFileNameW
0x180040f44  mov     rdx, rax
0x180040f47  lea     rcx, [rbp+arg_0]
0x180040f4b  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180040f50  mov     rax, [rbp+arg_0]
0x180040f54  lea     rcx, [rbp+arg_0]
0x180040f58  mov     [rbx], rax
0x180040f5b  mov     [rbp+arg_0], 0
0x180040f63  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040f68  mov     rcx, [rbx]; pszPath
0x180040f6b  test    rcx, rcx
0x180040f6e  jnz     short loc_180040F7A
0x180040f70  mov     edx, 321h
0x180040f75  jmp     loc_180040EE0
0x180040f7a  call    cs:__imp_PathRemoveFileSpecW
0x180040f80  mov     rcx, [rbx]; pszPath
0x180040f83  call    cs:__imp_PathStripPathW
0x180040f89  xor     eax, eax
0x180040f8b  mov     rbx, [rsp+20h+arg_8]
0x180040f90  mov     rdi, [rsp+20h+arg_10]
0x180040f95  add     rsp, 20h
0x180040f99  pop     rbp
0x180040f9a  retn
```
