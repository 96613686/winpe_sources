# Wsp::Facade::FileShareFacade::VerifyDirectoryExists(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x18005360c`
- end: `0x180053680`
- name: `?VerifyDirectoryExists@FileShareFacade@Facade@Wsp@@CAKAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_N@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180051e94`

## callees

- `0x18000e14c`
- `0x18005360c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053655`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053655`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180053645`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180053645`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180053623`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180053623`

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
0x18005360c  mov     [rsp+arg_0], rbx
0x180053611  push    rdi
0x180053612  sub     rsp, 20h
0x180053616  mov     bl, dl
0x180053618  mov     rdi, rcx
0x18005361b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180053620  mov     rcx, rax; lpFileName
0x180053623  call    cs:__imp_GetFileAttributesW
0x18005362a  nop     dword ptr [rax+rax+00h]
0x18005362f  cmp     eax, 0FFFFFFFFh
0x180053632  jnz     short loc_180053667
0x180053634  test    bl, bl
0x180053636  jz      short loc_180053655
0x180053638  mov     rcx, rdi
0x18005363b  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180053640  mov     rcx, rax; lpPathName
0x180053643  xor     edx, edx; lpSecurityAttributes
0x180053645  call    cs:__imp_CreateDirectoryW
0x18005364c  nop     dword ptr [rax+rax+00h]
0x180053651  test    eax, eax
0x180053653  jnz     short loc_180053663
0x180053655  call    cs:__imp_GetLastError
0x18005365c  nop     dword ptr [rax+rax+00h]
0x180053661  jmp     short loc_180053674
0x180053663  xor     eax, eax
0x180053665  jmp     short loc_180053674
0x180053667  and     al, 10h
0x180053669  neg     al
0x18005366b  sbb     eax, eax
0x18005366d  not     eax
0x18005366f  and     eax, 10Bh
0x180053674  mov     rbx, [rsp+28h+arg_0]
0x180053679  add     rsp, 20h
0x18005367d  pop     rdi
0x18005367e  retn
```
