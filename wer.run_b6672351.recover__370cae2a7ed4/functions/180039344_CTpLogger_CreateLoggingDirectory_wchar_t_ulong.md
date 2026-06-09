# CTpLogger::CreateLoggingDirectory(wchar_t *,ulong)

- ea: `0x180039344`
- end: `0x1800394ce`
- name: `?CreateLoggingDirectory@CTpLogger@@AEAAJPEA_WK@Z`
- size: `394`
- prototype: `int(CTpLogger *__hidden this, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180046730`
- `0x1800a4f48`

## callees

- `0x180039344`
- `0x180039760`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039451`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x180039451`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039363`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180039363`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800393bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800393bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800393df`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800393df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039417`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800394a6`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180039483`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180039483`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180039407`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180039407`

## string_xrefs

- `0x1800393b8`: `kernelbase.dll`
- `0x1800393d5`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall CTpLogger::CreateLoggingDirectory(CTpLogger *this, wchar_t *a2)
{
  __int64 v3; // rax
  int result; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  WCHAR *v7; // rdx
  DWORD TempPathW; // eax
  signed int LastError; // eax
  unsigned int v10; // ebx
  HMODULE v11; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 6) == *((_QWORD *)this + 7) )
  {
    Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
    v11 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "GetTempPath2W");
      v7 = a2;
      if ( ProcAddress )
      {
        TempPathW = ((__int64 (__fastcall *)(__int64, wchar_t *))ProcAddress)(260, a2);
        goto LABEL_14;
      }
    }
    else
    {
      v7 = a2;
    }
    TempPathW = GetTempPathW(0x104u, v7);
LABEL_14:
    if ( TempPathW )
    {
      if ( TempPathW < 0x104 )
      {
        if ( !(unsigned int)_o_wcscat_s(a2, 260, L"TpLogger\\") )
        {
          tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v11);
          goto LABEL_23;
        }
        v10 = -2147467259;
      }
      else
      {
        v10 = -2147024774;
      }
    }
    else
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
    }
    tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),0>>(&v11);
    return v10;
  }
  if ( (unsigned int)_o_wcscpy_s(a2, 260) )
    return -2147024774;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( a2[(int)v3 - 1] != 92 )
  {
    if ( (unsigned int)(v3 + 1) < 0x104 )
    {
      *(_DWORD *)&a2[(int)v3] = 92;
      goto LABEL_23;
    }
    return -2147024774;
  }
LABEL_23:
  if ( CreateDirectoryW(a2, 0) || GetLastError() == 183 )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180039344  mov     [rsp+arg_8], rbx
0x180039349  push    rdi
0x18003934a  sub     rsp, 20h
0x18003934e  mov     rbx, rdx
0x180039351  mov     r8, [rcx+30h]
0x180039355  cmp     r8, [rcx+38h]
0x180039359  jz      short loc_1800393B0
0x18003935b  mov     edx, 104h
0x180039360  mov     rcx, rbx
0x180039363  call    cs:__imp__o_wcscpy_s
0x18003936a  nop     dword ptr [rax+rax+00h]
0x18003936f  xor     edi, edi
0x180039371  test    eax, eax
0x180039373  jnz     short loc_1800393A6
0x180039375  or      rax, 0FFFFFFFFFFFFFFFFh
0x180039379  inc     rax
0x18003937c  cmp     [rbx+rax*2], di
0x180039380  jnz     short loc_180039379
0x180039382  movsxd  rcx, eax
0x180039385  mov     edx, 5Ch ; '\'
0x18003938a  cmp     [rbx+rcx*2-2], dx
0x18003938f  jz      loc_18003947E
0x180039395  inc     eax
0x180039397  cmp     eax, 104h
0x18003939c  jnb     short loc_1800393A6
0x18003939e  mov     [rbx+rcx*2], edx
0x1800393a1  jmp     loc_18003947E
0x1800393a6  mov     eax, 8007007Ah
0x1800393ab  jmp     loc_1800394C2
0x1800393b0  xor     edx, edx; hFile
0x1800393b2  mov     r8d, 800h; dwFlags
0x1800393b8  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800393bf  call    cs:__imp_LoadLibraryExW
0x1800393c6  nop     dword ptr [rax+rax+00h]
0x1800393cb  mov     [rsp+28h+arg_0], rax
0x1800393d0  test    rax, rax
0x1800393d3  jz      short loc_1800393FF
0x1800393d5  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1800393dc  mov     rcx, rax; hModule
0x1800393df  call    cs:__imp_GetProcAddress
0x1800393e6  nop     dword ptr [rax+rax+00h]
0x1800393eb  mov     rdx, rbx
0x1800393ee  mov     ecx, 104h
0x1800393f3  test    rax, rax
0x1800393f6  jz      short loc_180039407
0x1800393f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800393fd  jmp     short loc_180039413
0x1800393ff  mov     rdx, rbx; lpBuffer
0x180039402  mov     ecx, 104h; nBufferLength
0x180039407  call    cs:__imp_GetTempPathW
0x18003940e  nop     dword ptr [rax+rax+00h]
0x180039413  test    eax, eax
0x180039415  jnz     short loc_180039434
0x180039417  call    cs:__imp_GetLastError
0x18003941e  nop     dword ptr [rax+rax+00h]
0x180039423  mov     ebx, eax
0x180039425  test    eax, eax
0x180039427  jle     short loc_180039466
0x180039429  movzx   ebx, ax
0x18003942c  or      ebx, 80070000h
0x180039432  jmp     short loc_180039466
0x180039434  cmp     eax, 104h
0x180039439  jb      short loc_180039442
0x18003943b  mov     ebx, 8007007Ah
0x180039440  jmp     short loc_180039466
0x180039442  lea     r8, aTplogger; "TpLogger\\"
0x180039449  mov     edx, 104h
0x18003944e  mov     rcx, rbx
0x180039451  call    cs:__imp__o_wcscat_s
0x180039458  nop     dword ptr [rax+rax+00h]
0x18003945d  test    eax, eax
0x18003945f  jz      short loc_180039474
0x180039461  mov     ebx, 80004005h
0x180039466  lea     rcx, [rsp+28h+arg_0]
0x18003946b  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x180039470  mov     eax, ebx
0x180039472  jmp     short loc_1800394C2
0x180039474  lea     rcx, [rsp+28h+arg_0]
0x180039479  call    ??1?$unique_any@U?$handle_traits@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>::~unique_any<tlx::handle_traits<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),0>>(void)
0x18003947e  xor     edx, edx; lpSecurityAttributes
0x180039480  mov     rcx, rbx; lpPathName
0x180039483  call    cs:__imp_CreateDirectoryW
0x18003948a  nop     dword ptr [rax+rax+00h]
0x18003948f  test    eax, eax
0x180039491  jnz     short loc_1800394C0
0x180039493  call    cs:__imp_GetLastError
0x18003949a  nop     dword ptr [rax+rax+00h]
0x18003949f  cmp     eax, 0B7h
0x1800394a4  jz      short loc_1800394C0
0x1800394a6  call    cs:__imp_GetLastError
0x1800394ad  nop     dword ptr [rax+rax+00h]
0x1800394b2  test    eax, eax
0x1800394b4  jle     short loc_1800394C2
0x1800394b6  movzx   eax, ax
0x1800394b9  or      eax, 80070000h
0x1800394be  jmp     short loc_1800394C2
0x1800394c0  xor     eax, eax
0x1800394c2  mov     rbx, [rsp+28h+arg_8]
0x1800394c7  add     rsp, 20h
0x1800394cb  pop     rdi
0x1800394cc  retn
```
