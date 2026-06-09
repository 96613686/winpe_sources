# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x18000facc`
- end: `0x18000fbf3`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `295`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000fe10`
- `0x18001fb94`

## callees

- `0x1800029d0`
- `0x1800064a4`
- `0x18000facc`
- `0x180011648`
- `0x1800117f4`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fb05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fb15`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000fb45`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000fb45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fbb4`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000fb33`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18000fb33`

## string_xrefs

- `0x18000fb0e`: `GetSystemWow64Directory2W`
- `0x18000fafe`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c
signed int __fastcall UtilGetSystemDirectory2(__int64 a1, unsigned __int16 a2, char a3)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  UINT SystemWow64DirectoryW; // eax
  unsigned __int64 v9; // rbx
  signed int result; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-A8h] BYREF

  if ( a2 )
  {
    ModuleHandleW = GetModuleHandleW(L"api-ms-win-core-wow64-l1-1-1.dll");
    ProcAddress = GetProcAddress(ModuleHandleW, "GetSystemWow64Directory2W");
    if ( ProcAddress )
      SystemWow64DirectoryW = ((__int64 (__fastcall *)(WCHAR *, __int64, _QWORD))ProcAddress)(Buffer, 64, a2);
    else
      SystemWow64DirectoryW = GetSystemWow64DirectoryW(Buffer, 0x40u);
  }
  else
  {
    SystemWow64DirectoryW = GetSystemDirectoryW(Buffer, 0x40u);
  }
  if ( SystemWow64DirectoryW - 1 > 0x3F )
  {
    result = GetLastError();
    if ( result > 0 )
      result = (unsigned __int16)result | 0x80070000;
    if ( result >= 0 )
      return -2147467259;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( Buffer[v9] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1);
    if ( utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a1, Buffer, v9) )
    {
      if ( a3 )
        return 0;
      else
        return (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                  a1,
                                  92) == 0
             ? 0x8007000E
             : 0;
    }
    else
    {
      return -2147024882;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000facc  mov     [rsp+arg_10], rbx
0x18000fad1  push    rbp
0x18000fad2  push    rsi
0x18000fad3  push    rdi
0x18000fad4  sub     rsp, 0B0h
0x18000fadb  mov     rax, cs:__security_cookie
0x18000fae2  xor     rax, rsp
0x18000fae5  mov     [rsp+0C8h+var_28], rax
0x18000faed  xor     ebp, ebp
0x18000faef  movzx   esi, r8b
0x18000faf3  movzx   ebx, dx
0x18000faf6  mov     rdi, rcx
0x18000faf9  test    dx, dx
0x18000fafc  jz      short loc_18000FB3B
0x18000fafe  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x18000fb05  call    cs:__imp_GetModuleHandleW
0x18000fb0b  mov     rcx, rax; hModule
0x18000fb0e  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x18000fb15  call    cs:__imp_GetProcAddress
0x18000fb1b  lea     edx, [rbp+40h]; uSize
0x18000fb1e  lea     rcx, [rsp+0C8h+Buffer]; lpBuffer
0x18000fb23  test    rax, rax
0x18000fb26  jz      short loc_18000FB33
0x18000fb28  movzx   r8d, bx
0x18000fb2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb31  jmp     short loc_18000FB4B
0x18000fb33  call    cs:__imp_GetSystemWow64DirectoryW
0x18000fb39  jmp     short loc_18000FB4B
0x18000fb3b  mov     edx, 40h ; '@'; uSize
0x18000fb40  lea     rcx, [rsp+0C8h+Buffer]; lpBuffer
0x18000fb45  call    cs:__imp_GetSystemDirectoryW
0x18000fb4b  dec     eax
0x18000fb4d  cmp     eax, 3Fh ; '?'
0x18000fb50  ja      short loc_18000FBB4
0x18000fb52  lea     rax, [rsp+0C8h+Buffer]
0x18000fb57  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000fb5b  inc     rbx
0x18000fb5e  cmp     [rax+rbx*2], bp
0x18000fb62  jnz     short loc_18000FB5B
0x18000fb64  mov     rdx, rsi
0x18000fb67  mov     rcx, rdi
0x18000fb6a  xor     rdx, 1
0x18000fb6e  add     rdx, rbx
0x18000fb71  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18000fb76  mov     r8, rbx
0x18000fb79  lea     rdx, [rsp+0C8h+Buffer]
0x18000fb7e  mov     rcx, rdi
0x18000fb81  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18000fb86  test    al, al
0x18000fb88  jz      short loc_18000FBAD
0x18000fb8a  test    sil, sil
0x18000fb8d  jnz     short loc_18000FBA9
0x18000fb8f  mov     edx, 5Ch ; '\'
0x18000fb94  mov     rcx, rdi
0x18000fb97  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18000fb9c  neg     al
0x18000fb9e  sbb     eax, eax
0x18000fba0  not     eax
0x18000fba2  and     eax, 8007000Eh
0x18000fba7  jmp     short loc_18000FBD0
0x18000fba9  xor     eax, eax
0x18000fbab  jmp     short loc_18000FBD0
0x18000fbad  mov     eax, 8007000Eh
0x18000fbb2  jmp     short loc_18000FBD0
0x18000fbb4  call    cs:__imp_GetLastError
0x18000fbba  test    eax, eax
0x18000fbbc  jle     short loc_18000FBC6
0x18000fbbe  movzx   eax, ax
0x18000fbc1  or      eax, 80070000h
0x18000fbc6  test    eax, eax
0x18000fbc8  mov     ecx, 80004005h
0x18000fbcd  cmovns  eax, ecx
0x18000fbd0  mov     rcx, [rsp+0C8h+var_28]
0x18000fbd8  xor     rcx, rsp; StackCookie
0x18000fbdb  call    __security_check_cookie
0x18000fbe0  mov     rbx, [rsp+0C8h+arg_10]
0x18000fbe8  add     rsp, 0B0h
0x18000fbef  pop     rdi
0x18000fbf0  pop     rsi
0x18000fbf1  pop     rbp
0x18000fbf2  retn
```
