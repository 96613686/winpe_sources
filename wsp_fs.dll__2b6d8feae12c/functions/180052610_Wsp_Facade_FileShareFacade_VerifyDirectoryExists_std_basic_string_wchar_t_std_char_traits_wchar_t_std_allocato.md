# Wsp::Facade::FileShareFacade::VerifyDirectoryExists(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180052610`
- end: `0x180052671`
- name: `?VerifyDirectoryExists@FileShareFacade@Facade@Wsp@@CAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180050ec0`

## callees

- `0x18000dd74`
- `0x180052610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005264d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005264d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052643`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180052643`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052627`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180052627`

## pseudocode

```c
DWORD __fastcall Wsp::Facade::FileShareFacade::VerifyDirectoryExists(__int64 a1, char a2)
{
  const WCHAR *v4; // rax
  DWORD FileAttributesW; // eax
  const WCHAR *v6; // rax

  v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
  FileAttributesW = GetFileAttributesW(v4);
  if ( FileAttributesW != -1 )
    return (FileAttributesW & 0x10) == 0 ? 0x10B : 0;
  if ( a2 )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(a1);
    if ( CreateDirectoryW(v6, 0) )
      return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180052610  mov     [rsp+arg_0], rbx
0x180052615  push    rdi
0x180052616  sub     rsp, 20h
0x18005261a  mov     bl, dl
0x18005261c  mov     rdi, rcx
0x18005261f  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180052624  mov     rcx, rax; lpFileName
0x180052627  call    cs:__imp_GetFileAttributesW
0x18005262d  cmp     eax, 0FFFFFFFFh
0x180052630  jnz     short loc_180052659
0x180052632  test    bl, bl
0x180052634  jz      short loc_18005264D
0x180052636  mov     rcx, rdi
0x180052639  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18005263e  mov     rcx, rax; lpPathName
0x180052641  xor     edx, edx; lpSecurityAttributes
0x180052643  call    cs:__imp_CreateDirectoryW
0x180052649  test    eax, eax
0x18005264b  jnz     short loc_180052655
0x18005264d  call    cs:__imp_GetLastError
0x180052653  jmp     short loc_180052666
0x180052655  xor     eax, eax
0x180052657  jmp     short loc_180052666
0x180052659  and     al, 10h
0x18005265b  neg     al
0x18005265d  sbb     eax, eax
0x18005265f  not     eax
0x180052661  and     eax, 10Bh
0x180052666  mov     rbx, [rsp+28h+arg_0]
0x18005266b  add     rsp, 20h
0x18005266f  pop     rdi
0x180052670  retn
```
