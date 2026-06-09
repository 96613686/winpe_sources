# Wsp::Facade::GetVolumeHandle(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x180099ac8`
- end: `0x180099ba6`
- name: `?GetVolumeHandle@Facade@Wsp@@YA?AU?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0?0@cxl@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `222`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005de0c`
- `0x18005e554`

## callees

- `0x180002a70`
- `0x18000a6dc`
- `0x18000d250`
- `0x18000dd74`
- `0x18005d4d4`
- `0x180099ac8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099b66`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180099b66`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Wsp::Facade::GetVolumeHandle(_QWORD *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx
  const WCHAR *v6; // rax
  HANDLE FileW; // rbx
  _BYTE v9[16]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v10; // [rsp+60h] [rbp-28h]

  *a1 = -1;
  std::wstring::wstring(v9);
  if ( v10 )
  {
    v2 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
    if ( *(_WORD *)(v2 + 2 * v3 - 2) == 92 )
    {
      v10 = v3 - 1;
      v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
      *(_WORD *)(v4 + 2 * v5) = 0;
    }
  }
  v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v9);
  FileW = CreateFileW(v6, 0x80000000, 3u, 0, 3u, 0, 0);
  cxl::AutoHandle<void *,int,&int CloseHandle(void *),-1>::Close(a1);
  *a1 = FileW;
  std::wstring::_Tidy_deallocate(v9);
  return a1;
}

```

## disassembly

```asm
0x180099ac8  mov     [rsp+arg_10], rbx
0x180099acd  push    rdi
0x180099ace  sub     rsp, 80h
0x180099ad5  mov     rax, cs:__security_cookie
0x180099adc  xor     rax, rsp
0x180099adf  mov     [rsp+88h+var_18], rax
0x180099ae4  mov     rdi, rcx
0x180099ae7  mov     [rsp+88h+var_40], rcx
0x180099aec  xor     ebx, ebx
0x180099aee  mov     [rsp+88h+var_48], ebx
0x180099af2  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x180099af9  mov     [rsp+88h+var_48], 1
0x180099b01  lea     rcx, [rsp+88h+var_38]
0x180099b06  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180099b0b  mov     rdx, [rsp+88h+var_28]
0x180099b10  test    rdx, rdx
0x180099b13  jz      short loc_180099B3D
0x180099b15  lea     rcx, [rsp+88h+var_38]
0x180099b1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180099b1f  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x180099b25  jnz     short loc_180099B3D
0x180099b27  dec     rdx
0x180099b2a  mov     [rsp+88h+var_28], rdx
0x180099b2f  lea     rcx, [rsp+88h+var_38]
0x180099b34  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180099b39  mov     [rax+rdx*2], bx
0x180099b3d  lea     rcx, [rsp+88h+var_38]
0x180099b42  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x180099b47  mov     rcx, rax; lpFileName
0x180099b4a  mov     [rsp+88h+hTemplateFile], rbx; hTemplateFile
0x180099b4f  mov     [rsp+88h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x180099b53  mov     r8d, 3; dwShareMode
0x180099b59  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x180099b5e  xor     r9d, r9d; lpSecurityAttributes
0x180099b61  mov     edx, 80000000h; dwDesiredAccess
0x180099b66  call    cs:__imp_CreateFileW
0x180099b6c  mov     rbx, rax
0x180099b6f  mov     rcx, rdi
0x180099b72  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0?0@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),-1>::Close(void)
0x180099b77  mov     [rdi], rbx
0x180099b7a  lea     rcx, [rsp+88h+var_38]
0x180099b7f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180099b84  mov     rax, rdi
0x180099b87  mov     rcx, [rsp+88h+var_18]
0x180099b8c  xor     rcx, rsp; StackCookie
0x180099b8f  call    __security_check_cookie
0x180099b94  mov     rbx, [rsp+88h+arg_10]
0x180099b9c  add     rsp, 80h
0x180099ba3  pop     rdi
0x180099ba4  retn
```
