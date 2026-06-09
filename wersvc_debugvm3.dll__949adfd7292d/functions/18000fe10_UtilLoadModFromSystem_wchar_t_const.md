# UtilLoadModFromSystem(wchar_t const *)

- ea: `0x18000fe10`
- end: `0x18000fe9d`
- name: `?UtilLoadModFromSystem@@YA?AV?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@PEB_W@Z`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000d640`

## callees

- `0x1800029f4`
- `0x18000facc`
- `0x18000fe10`
- `0x180011534`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fe64`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000fe64`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HMODULE *__fastcall UtilLoadModFromSystem(HMODULE *a1)
{
  __int64 v2; // rdx
  LPCWSTR lpLibFileName[2]; // [rsp+28h] [rbp-28h] BYREF
  _WORD v5[12]; // [rsp+38h] [rbp-18h] BYREF

  lpLibFileName[0] = v5;
  lpLibFileName[1] = v5;
  v5[0] = 0;
  if ( UtilGetSystemDirectory2((__int64)lpLibFileName, 0, 0) >= 0
    && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                          lpLibFileName,
                          v2,
                          9) )
  {
    *a1 = LoadLibraryExW(lpLibFileName[0], 0, 0);
  }
  else
  {
    *a1 = 0;
  }
  if ( lpLibFileName[0] != v5 )
    operator delete((void *)lpLibFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return a1;
}

```

## disassembly

```asm
0x18000fe10  mov     [rsp-8+arg_0], rbx
0x18000fe15  push    rbp
0x18000fe16  mov     rbp, rsp
0x18000fe19  sub     rsp, 50h
0x18000fe1d  mov     rbx, rcx
0x18000fe20  lea     rax, [rbp+var_18]
0x18000fe24  mov     [rbp+lpLibFileName], rax
0x18000fe28  lea     rax, [rbp+var_18]
0x18000fe2c  mov     [rbp+var_20], rax
0x18000fe30  xor     eax, eax
0x18000fe32  mov     [rbp+var_18], ax
0x18000fe36  xor     edx, edx
0x18000fe38  xor     r8d, r8d
0x18000fe3b  lea     rcx, [rbp+lpLibFileName]
0x18000fe3f  call    ?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z; UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)
0x18000fe44  test    eax, eax
0x18000fe46  js      short loc_18000FE6F
0x18000fe48  mov     r8d, 9
0x18000fe4e  lea     rcx, [rbp+lpLibFileName]
0x18000fe52  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18000fe57  test    al, al
0x18000fe59  jz      short loc_18000FE6F
0x18000fe5b  xor     r8d, r8d; dwFlags
0x18000fe5e  xor     edx, edx; hFile
0x18000fe60  mov     rcx, [rbp+lpLibFileName]; lpLibFileName
0x18000fe64  call    cs:__imp_LoadLibraryExW
0x18000fe6a  mov     [rbx], rax
0x18000fe6d  jmp     short loc_18000FE76
0x18000fe6f  mov     qword ptr [rbx], 0
0x18000fe76  lea     rax, [rbp+var_18]
0x18000fe7a  mov     rcx, [rbp+lpLibFileName]; void *
0x18000fe7e  cmp     rcx, rax
0x18000fe81  jz      short loc_18000FE8F
0x18000fe83  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000fe8a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fe8f  mov     rax, rbx
0x18000fe92  mov     rbx, [rsp+50h+arg_0]
0x18000fe97  add     rsp, 50h
0x18000fe9b  pop     rbp
0x18000fe9c  retn
```
