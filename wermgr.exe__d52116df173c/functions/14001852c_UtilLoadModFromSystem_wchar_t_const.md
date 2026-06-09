# UtilLoadModFromSystem(wchar_t const *)

- ea: `0x14001852c`
- end: `0x1400185bb`
- name: `?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z`
- size: `143`
- prototype: `HMODULE *__fastcall(HMODULE *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x14001aec4`

## callees

- `0x140003224`
- `0x14001817c`
- `0x14001852c`
- `0x1400189c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018582`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018582`

## string_xrefs

- `0x140018565`: `ntdll.dll`

## pseudocode

```c
HMODULE *__fastcall UtilLoadModFromSystem(HMODULE *a1)
{
  LPCWSTR lpLibFileName[2]; // [rsp+28h] [rbp-28h] BYREF
  _WORD v4[12]; // [rsp+38h] [rbp-18h] BYREF

  lpLibFileName[0] = v4;
  lpLibFileName[1] = v4;
  v4[0] = 0;
  if ( UtilGetSystemDirectory2(lpLibFileName) >= 0
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          lpLibFileName,
                          L"ntdll.dll",
                          9) )
  {
    *a1 = LoadLibraryExW(lpLibFileName[0], 0, 0);
  }
  else
  {
    *a1 = 0;
  }
  if ( lpLibFileName[0] != v4 )
    operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return a1;
}

```

## disassembly

```asm
0x14001852c  mov     [rsp-8+arg_0], rbx
0x140018531  push    rbp
0x140018532  mov     rbp, rsp
0x140018535  sub     rsp, 50h
0x140018539  mov     rbx, rcx
0x14001853c  lea     rax, [rbp+var_18]
0x140018540  mov     [rbp+lpLibFileName], rax
0x140018544  lea     rax, [rbp+var_18]
0x140018548  mov     [rbp+var_20], rax
0x14001854c  xor     eax, eax
0x14001854e  mov     [rbp+var_18], ax
0x140018552  lea     rcx, [rbp+lpLibFileName]
0x140018556  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x14001855b  test    eax, eax
0x14001855d  js      short loc_14001858D
0x14001855f  mov     r8d, 9
0x140018565  lea     rdx, aNtdllDll_1; "ntdll.dll"
0x14001856c  lea     rcx, [rbp+lpLibFileName]
0x140018570  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140018575  test    al, al
0x140018577  jz      short loc_14001858D
0x140018579  xor     r8d, r8d; dwFlags
0x14001857c  xor     edx, edx; hFile
0x14001857e  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x140018582  call    cs:__imp_LoadLibraryExW
0x140018588  mov     [rbx], rax
0x14001858b  jmp     short loc_140018594
0x14001858d  mov     qword ptr [rbx], 0
0x140018594  lea     rax, [rbp+var_18]
0x140018598  mov     rcx, [rbp+lpLibFileName]; void *
0x14001859c  cmp     rcx, rax
0x14001859f  jz      short loc_1400185AD
0x1400185a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400185a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400185ad  mov     rax, rbx
0x1400185b0  mov     rbx, [rsp+50h+arg_0]
0x1400185b5  add     rsp, 50h
0x1400185b9  pop     rbp
0x1400185ba  retn
```
