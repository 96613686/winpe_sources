# UtilGetSystemDirectory2(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,ushort,bool)

- ea: `0x18003ada8`
- end: `0x18003aed1`
- name: `?UtilGetSystemDirectory2@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@G_N@Z`
- size: `297`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18003a7f0`
- `0x18003ad04`
- `0x1800697d0`
- `0x18007b178`
- `0x180091f00`

## callees

- `0x18000d40c`
- `0x18000ed68`
- `0x1800172c0`
- `0x18001c368`
- `0x18003ada8`
- `0x180053300`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ade0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003ade0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003adf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003adf6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003ae32`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003ae32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ae98`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18003ae1a`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18003ae1a`

## string_xrefs

- `0x18003adef`: `GetSystemWow64Directory2W`
- `0x18003add9`: `api-ms-win-core-wow64-l1-1-1.dll`

## pseudocode

```c
__int64 __fastcall UtilGetSystemDirectory2(void *a1, unsigned __int16 a2)
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  UINT SystemWow64DirectoryW; // eax
  __int64 v7; // rbx
  DWORD LastError; // eax
  WCHAR Buffer[64]; // [rsp+20h] [rbp-98h] BYREF

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
    LastError = GetLastError();
    return ERROR_HR_FROM_WIN32(LastError);
  }
  else
  {
    v7 = -1;
    do
      ++v7;
    while ( Buffer[v7] );
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(a1);
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            a1,
                            Buffer) )
      return (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                a1,
                                92) == 0
           ? 0x8007000E
           : 0;
    else
      return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18003ada8  mov     [rsp+arg_10], rbx
0x18003adad  mov     [rsp+arg_18], rsi
0x18003adb2  push    rdi
0x18003adb3  sub     rsp, 0B0h
0x18003adba  mov     rax, cs:__security_cookie
0x18003adc1  xor     rax, rsp
0x18003adc4  mov     [rsp+0B8h+var_18], rax
0x18003adcc  xor     esi, esi
0x18003adce  movzx   ebx, dx
0x18003add1  mov     rdi, rcx
0x18003add4  test    dx, dx
0x18003add7  jz      short loc_18003AE28
0x18003add9  lea     rcx, aApiMsWinCoreWo_1; "api-ms-win-core-wow64-l1-1-1.dll"
0x18003ade0  call    cs:__imp_GetModuleHandleW
0x18003ade7  nop     dword ptr [rax+rax+00h]
0x18003adec  mov     rcx, rax; hModule
0x18003adef  lea     rdx, aGetsystemwow64; "GetSystemWow64Directory2W"
0x18003adf6  call    cs:__imp_GetProcAddress
0x18003adfd  nop     dword ptr [rax+rax+00h]
0x18003ae02  lea     edx, [rsi+40h]; uSize
0x18003ae05  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x18003ae0a  test    rax, rax
0x18003ae0d  jz      short loc_18003AE1A
0x18003ae0f  movzx   r8d, bx
0x18003ae13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ae18  jmp     short loc_18003AE3E
0x18003ae1a  call    cs:__imp_GetSystemWow64DirectoryW
0x18003ae21  nop     dword ptr [rax+rax+00h]
0x18003ae26  jmp     short loc_18003AE3E
0x18003ae28  mov     edx, 40h ; '@'; uSize
0x18003ae2d  lea     rcx, [rsp+0B8h+Buffer]; lpBuffer
0x18003ae32  call    cs:__imp_GetSystemDirectoryW
0x18003ae39  nop     dword ptr [rax+rax+00h]
0x18003ae3e  dec     eax
0x18003ae40  cmp     eax, 3Fh ; '?'
0x18003ae43  ja      short loc_18003AE98
0x18003ae45  lea     rax, [rsp+0B8h+Buffer]
0x18003ae4a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003ae4e  inc     rbx
0x18003ae51  cmp     [rax+rbx*2], si
0x18003ae55  jnz     short loc_18003AE4E
0x18003ae57  lea     rdx, [rbx+1]
0x18003ae5b  mov     rcx, rdi
0x18003ae5e  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18003ae63  mov     r8, rbx
0x18003ae66  lea     rdx, [rsp+0B8h+Buffer]
0x18003ae6b  mov     rcx, rdi
0x18003ae6e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18003ae73  test    al, al
0x18003ae75  jz      short loc_18003AE91
0x18003ae77  mov     edx, 5Ch ; '\'
0x18003ae7c  mov     rcx, rdi
0x18003ae7f  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18003ae84  neg     al
0x18003ae86  sbb     eax, eax
0x18003ae88  not     eax
0x18003ae8a  and     eax, 8007000Eh
0x18003ae8f  jmp     short loc_18003AEAB
0x18003ae91  mov     eax, 8007000Eh
0x18003ae96  jmp     short loc_18003AEAB
0x18003ae98  call    cs:__imp_GetLastError
0x18003ae9f  nop     dword ptr [rax+rax+00h]
0x18003aea4  mov     ecx, eax; unsigned int
0x18003aea6  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18003aeab  mov     rcx, [rsp+0B8h+var_18]
0x18003aeb3  xor     rcx, rsp; StackCookie
0x18003aeb6  call    __security_check_cookie
0x18003aebb  lea     r11, [rsp+0B8h+var_8]
0x18003aec3  mov     rbx, [r11+20h]
0x18003aec7  mov     rsi, [r11+28h]
0x18003aecb  mov     rsp, r11
0x18003aece  pop     rdi
0x18003aecf  retn
```
