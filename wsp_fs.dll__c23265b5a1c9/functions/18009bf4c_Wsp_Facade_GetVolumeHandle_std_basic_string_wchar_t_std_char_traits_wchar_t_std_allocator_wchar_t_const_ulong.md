# Wsp::Facade::GetVolumeHandle(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong)

- ea: `0x18009bf4c`
- end: `0x18009c030`
- name: `?GetVolumeHandle@Facade@Wsp@@YA?AU?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0?0@cxl@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@K@Z`
- size: `228`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18005efa0`
- `0x18005f704`

## callees

- `0x180002ad0`
- `0x18000aa10`
- `0x18000d5b8`
- `0x18000e14c`
- `0x18005e62c`
- `0x18009bf4c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bfea`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009bfea`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Wsp::Facade::GetVolumeHandle(_QWORD *a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rdx
  __int64 v5; // rax
  __int64 v6; // rdx
  const WCHAR *v7; // rax
  HANDLE FileW; // rbx
  _BYTE v10[16]; // [rsp+50h] [rbp-38h] BYREF
  __int64 v11; // [rsp+60h] [rbp-28h]

  *a1 = -1;
  std::wstring::wstring(v10, a2);
  if ( v11 )
  {
    v3 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
    if ( *(_WORD *)(v3 + 2 * v4 - 2) == 92 )
    {
      v11 = v4 - 1;
      v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
      *(_WORD *)(v5 + 2 * v6) = 0;
    }
  }
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v10);
  FileW = CreateFileW(v7, 0x80000000, 3u, 0, 3u, 0, 0);
  cxl::AutoHandle<void *,int,&int CloseHandle(void *),-1>::Close(a1);
  *a1 = FileW;
  std::wstring::_Tidy_deallocate(v10);
  return a1;
}

```

## disassembly

```asm
0x18009bf4c  mov     [rsp+arg_10], rbx
0x18009bf51  push    rdi
0x18009bf52  sub     rsp, 80h
0x18009bf59  mov     rax, cs:__security_cookie
0x18009bf60  xor     rax, rsp
0x18009bf63  mov     [rsp+88h+var_18], rax
0x18009bf68  mov     rdi, rcx
0x18009bf6b  mov     [rsp+88h+var_40], rcx
0x18009bf70  xor     ebx, ebx
0x18009bf72  mov     [rsp+88h+var_48], ebx
0x18009bf76  mov     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18009bf7d  mov     [rsp+88h+var_48], 1
0x18009bf85  lea     rcx, [rsp+88h+var_38]
0x18009bf8a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009bf8f  mov     rdx, [rsp+88h+var_28]
0x18009bf94  test    rdx, rdx
0x18009bf97  jz      short loc_18009BFC1
0x18009bf99  lea     rcx, [rsp+88h+var_38]
0x18009bf9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009bfa3  cmp     word ptr [rax+rdx*2-2], 5Ch ; '\'
0x18009bfa9  jnz     short loc_18009BFC1
0x18009bfab  dec     rdx
0x18009bfae  mov     [rsp+88h+var_28], rdx
0x18009bfb3  lea     rcx, [rsp+88h+var_38]
0x18009bfb8  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009bfbd  mov     [rax+rdx*2], bx
0x18009bfc1  lea     rcx, [rsp+88h+var_38]
0x18009bfc6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18009bfcb  mov     rcx, rax; lpFileName
0x18009bfce  mov     [rsp+88h+hTemplateFile], rbx; hTemplateFile
0x18009bfd3  mov     [rsp+88h+dwFlagsAndAttributes], ebx; dwFlagsAndAttributes
0x18009bfd7  mov     r8d, 3; dwShareMode
0x18009bfdd  mov     [rsp+88h+dwCreationDisposition], r8d; dwCreationDisposition
0x18009bfe2  xor     r9d, r9d; lpSecurityAttributes
0x18009bfe5  mov     edx, 80000000h; dwDesiredAccess
0x18009bfea  call    cs:__imp_CreateFileW
0x18009bff1  nop     dword ptr [rax+rax+00h]
0x18009bff6  mov     rbx, rax
0x18009bff9  mov     rcx, rdi
0x18009bffc  call    ?Close@?$AutoHandle@PEAXH$1?CloseHandle@@YAHPEAX@Z$0?0@cxl@@QEAAXXZ; cxl::AutoHandle<void *,int,&CloseHandle(void *),-1>::Close(void)
0x18009c001  mov     [rdi], rbx
0x18009c004  lea     rcx, [rsp+88h+var_38]
0x18009c009  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18009c00e  mov     rax, rdi
0x18009c011  mov     rcx, [rsp+88h+var_18]
0x18009c016  xor     rcx, rsp; StackCookie
0x18009c019  call    __security_check_cookie
0x18009c01e  mov     rbx, [rsp+88h+arg_10]
0x18009c026  add     rsp, 80h
0x18009c02d  pop     rdi
0x18009c02e  retn
```
