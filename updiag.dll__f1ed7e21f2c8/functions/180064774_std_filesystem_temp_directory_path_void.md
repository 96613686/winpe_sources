# std::filesystem::temp_directory_path(void)

- ea: `0x180064774`
- end: `0x1800648dc`
- name: `?temp_directory_path@filesystem@std@@YA?AVpath@12@XZ`
- size: `360`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x180039bd4`

## callees

- `0x180028b18`
- `0x180064774`
- `0x18006704c`
- `0x180079ebc`
- `0x18008fc40`
- `0x180096170`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800647d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800647d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800647e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800647e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064801`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064850`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180064850`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180064810`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180064810`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800647e9`

## string_xrefs

- `0x1800648c9`: `temp_directory_path`
- `0x1800647c9`: `kernel32.dll`
- `0x1800647d6`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::filesystem::temp_directory_path(_QWORD *a1)
{
  const WCHAR *v2; // rdi
  HMODULE ModuleHandleW; // rax
  unsigned int (__fastcall *ProcAddress)(__int64, const WCHAR *); // rax
  DWORD LastError; // edi
  DWORD FileAttributesW; // eax
  int v7; // edi
  const struct std::filesystem::path *v8; // r9
  void ***v9; // rax
  HANDLE hObject[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v12; // [rsp+40h] [rbp-18h]

  v12 = a1;
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  std::wstring::resize(a1);
  v2 = (const WCHAR *)a1;
  if ( a1[3] > 7u )
    v2 = (const WCHAR *)*a1;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  ProcAddress = (unsigned int (__fastcall *)(__int64, const WCHAR *))GetProcAddress(ModuleHandleW, "GetTempPath2W");
  if ( !ProcAddress )
    ProcAddress = (unsigned int (__fastcall *)(__int64, const WCHAR *))GetTempPathW;
  if ( ProcAddress(261, v2) )
  {
    FileAttributesW = GetFileAttributesW(v2);
    if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      goto LABEL_14;
    if ( (FileAttributesW & 0x400) == 0 )
      goto LABEL_13;
    hObject[0] = 0;
    v7 = _std_fs_open_handle(hObject, v2, 128, 0x2000000);
    if ( hObject[0] != (HANDLE)-1LL && !CloseHandle(hObject[0]) )
      abort();
    if ( v7 )
LABEL_14:
      LastError = -1;
    else
LABEL_13:
      LastError = 0;
  }
  else
  {
    LastError = GetLastError();
  }
  std::wstring::resize(a1);
  if ( LastError == -1 )
  {
    LastError = 20;
    v9 = &`std::_Immortalize_memcpy_image<std::_Generic_error_category>'::`2'::_Static;
  }
  else
  {
    v9 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  }
  LODWORD(hObject[0]) = LastError;
  hObject[1] = v9;
  if ( LastError )
    std::filesystem::_Throw_fs_error(
      (std::filesystem *)"temp_directory_path",
      (const char *)hObject,
      (const struct std::error_code *)a1,
      v8);
  return a1;
}

```

## disassembly

```asm
0x180064774  mov     rax, rsp
0x180064777  mov     [rax+10h], rbx
0x18006477b  mov     [rax+18h], rbp
0x18006477f  mov     [rax+20h], rsi
0x180064783  push    rdi
0x180064784  sub     rsp, 50h
0x180064788  mov     rbx, rcx
0x18006478b  mov     [rax-18h], rcx
0x18006478f  xor     ebp, ebp
0x180064791  mov     [rax-38h], ebp
0x180064794  xorps   xmm0, xmm0
0x180064797  movups  xmmword ptr [rcx], xmm0
0x18006479a  mov     [rcx+10h], rbp
0x18006479e  mov     qword ptr [rcx+18h], 7
0x1800647a6  mov     [rcx], bp
0x1800647a9  mov     dword ptr [rax-38h], 2
0x1800647b0  mov     esi, 105h
0x1800647b5  mov     edx, esi
0x1800647b7  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800647bc  mov     rdi, rbx
0x1800647bf  cmp     qword ptr [rbx+18h], 7
0x1800647c4  jbe     short loc_1800647C9
0x1800647c6  mov     rdi, [rbx]
0x1800647c9  lea     rcx, aKernel32Dll; "kernel32.dll"
0x1800647d0  call    cs:__imp_GetModuleHandleW
0x1800647d6  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800647dd  mov     rcx, rax; hModule
0x1800647e0  call    cs:__imp_GetProcAddress
0x1800647e6  test    rax, rax
0x1800647e9  cmovz   rax, cs:__imp_GetTempPathW
0x1800647f1  mov     rdx, rdi
0x1800647f4  mov     ecx, esi
0x1800647f6  call    _guard_dispatch_icall
0x1800647fb  mov     esi, eax
0x1800647fd  test    eax, eax
0x1800647ff  jnz     short loc_18006480D
0x180064801  call    cs:__imp_GetLastError
0x180064807  mov     edi, eax
0x180064809  mov     esi, ebp
0x18006480b  jmp     short loc_180064865
0x18006480d  mov     rcx, rdi; lpFileName
0x180064810  call    cs:__imp_GetFileAttributesW
0x180064816  cmp     eax, 0FFFFFFFFh
0x180064819  jz      short loc_180064862
0x18006481b  test    al, 10h
0x18006481d  jz      short loc_180064862
0x18006481f  bt      eax, 0Ah
0x180064823  jnb     short loc_18006485E
0x180064825  mov     [rsp+58h+hObject], rbp
0x18006482a  mov     r9d, 2000000h
0x180064830  mov     r8d, 80h
0x180064836  mov     rdx, rdi
0x180064839  lea     rcx, [rsp+58h+hObject]
0x18006483e  call    __std_fs_open_handle
0x180064843  mov     edi, eax
0x180064845  mov     rcx, [rsp+58h+hObject]; hObject
0x18006484a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18006484e  jz      short loc_18006485A
0x180064850  call    cs:__imp_CloseHandle
0x180064856  test    eax, eax
0x180064858  jz      short loc_1800648D6
0x18006485a  test    edi, edi
0x18006485c  jnz     short loc_180064862
0x18006485e  mov     edi, ebp
0x180064860  jmp     short loc_180064865
0x180064862  or      edi, 0FFFFFFFFh
0x180064865  mov     edx, esi
0x180064867  mov     rcx, rbx; Src
0x18006486a  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x18006486f  cmp     edi, 0FFFFFFFFh
0x180064872  jnz     short loc_180064882
0x180064874  mov     edi, 14h
0x180064879  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_Generic_error_category@std@@@std@@YAAEBV_Generic_error_category@1@XZ@4V21@B; std::_Generic_error_category const `std::_Immortalize_memcpy_image<std::_Generic_error_category>(void)'::`2'::_Static
0x180064880  jmp     short loc_180064889
0x180064882  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4V21@B; std::_System_error_category const `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x180064889  mov     dword ptr [rsp+58h+hObject], edi
0x18006488d  mov     [rsp+58h+hObject+8], rax
0x180064892  movaps  xmm0, xmmword ptr [rsp+58h+hObject]
0x180064897  movdqa  xmmword ptr [rsp+58h+hObject], xmm0
0x18006489d  mov     [rsp+58h+var_38], 1
0x1800648a5  test    edi, edi
0x1800648a7  jnz     short loc_1800648C1
0x1800648a9  mov     rax, rbx
0x1800648ac  mov     rbx, [rsp+58h+arg_8]
0x1800648b1  mov     rbp, [rsp+58h+arg_10]
0x1800648b6  mov     rsi, [rsp+58h+arg_18]
0x1800648bb  add     rsp, 50h
0x1800648bf  pop     rdi
0x1800648c0  retn
0x1800648c1  mov     r8, rbx; struct std::error_code *
0x1800648c4  lea     rdx, [rsp+58h+hObject]; char *
0x1800648c9  lea     rcx, aTempDirectoryP; "temp_directory_path"
0x1800648d0  call    ?_Throw_fs_error@filesystem@std@@YAXPEBDAEBVerror_code@2@AEBVpath@12@@Z; std::filesystem::_Throw_fs_error(char const *,std::error_code const &,std::filesystem::path const &)
0x1800648d6  call    abort
```
