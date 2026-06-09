# GetFolder

- ea: `0x180004cc0`
- end: `0x180004e3c`
- name: `GetFolder`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18000ca00`

## callees

- `0x180004cc0`
- `0x180009b40`
- `0x180010250`
- `0x180011010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180004dc2`
- `OLEAUT32!__imp_SysAllocString` at `0x180004dc2`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d53`
- `OLEAUT32!__imp_SysFreeString` at `0x180004d53`
- `KERNEL32!GetProcAddress` at `0x180004da3`
- `KERNEL32!GetProcAddress` at `0x180004da3`
- `KERNEL32!LoadLibraryExW` at `0x180004d8e`
- `KERNEL32!LoadLibraryExW` at `0x180004d8e`
- `SHELL32!SHGetPathFromIDListA` at `0x180004de4`
- `SHELL32!SHGetPathFromIDListA` at `0x180004de4`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180004cff`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180004cff`

## string_xrefs

- `0x180004d81`: `shell32.dll`
- `0x180004d99`: `SHGetPathFromIDListW`

## pseudocode

```c
__int64 __fastcall GetFolder(__int64 a1, int a2, __int64 a3)
{
  OLECHAR *v5; // rdi
  HRESULT v6; // ebx
  FARPROC ProcAddress; // rax
  LPITEMIDLIST v8; // rbx
  HMODULE Library; // rax
  int v11; // eax
  LPITEMIDLIST ppidl; // [rsp+20h] [rbp-358h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-350h] BYREF
  CHAR pszPath[272]; // [rsp+30h] [rbp-348h] BYREF
  OLECHAR psz[264]; // [rsp+140h] [rbp-238h] BYREF

  ppidl = 0;
  v5 = 0;
  v13 = 0;
  v6 = SHGetSpecialFolderLocation(0, a2, &ppidl);
  if ( v6 >= 0 )
  {
    if ( Global::g_fWindowsNT )
    {
      ProcAddress = (FARPROC)qword_180018BA8;
      v8 = ppidl;
      if ( !qword_180018BA8
        && ((Library = LoadLibraryExW(L"shell32.dll", 0, 0x800u)) == 0
         || (ProcAddress = GetProcAddress(Library, "SHGetPathFromIDListW"), (qword_180018BA8 = (__int64)ProcAddress) == 0))
        || !((unsigned int (__fastcall *)(LPITEMIDLIST, OLECHAR *))ProcAddress)(v8, psz) )
      {
        v6 = -2147024893;
        goto LABEL_6;
      }
      v5 = SysAllocString(psz);
      if ( !v5 )
      {
        v6 = -2147024882;
        goto LABEL_6;
      }
LABEL_17:
      *(_QWORD *)(a3 + 8) = v5;
      v5 = 0;
      v6 = 0;
      *(_WORD *)a3 = 8;
      goto LABEL_6;
    }
    if ( !SHGetPathFromIDListA(ppidl, pszPath) )
    {
      v6 = -2147024893;
      goto LABEL_6;
    }
    v11 = PSZToBSTR(pszPath, &v13);
    v5 = v13;
    v6 = v11;
    if ( v11 >= 0 )
      goto LABEL_17;
  }
LABEL_6:
  if ( ppidl )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
  SysFreeString(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180004cc0  mov     [rsp+arg_18], rbx
0x180004cc5  push    rsi
0x180004cc6  push    rdi
0x180004cc7  push    r14
0x180004cc9  sub     rsp, 360h
0x180004cd0  mov     rax, cs:__security_cookie
0x180004cd7  xor     rax, rsp
0x180004cda  mov     [rsp+378h+var_28], rax
0x180004ce2  mov     rsi, r8
0x180004ce5  mov     [rsp+378h+ppidl], 0
0x180004cee  mov     r14, rcx
0x180004cf1  lea     r8, [rsp+378h+ppidl]; ppidl
0x180004cf6  xor     edi, edi
0x180004cf8  xor     ecx, ecx; hwnd
0x180004cfa  mov     [rsp+378h+var_350], rdi
0x180004cff  call    cs:__imp_SHGetSpecialFolderLocation
0x180004d05  mov     ebx, eax
0x180004d07  test    eax, eax
0x180004d09  js      short loc_180004D42
0x180004d0b  cmp     cs:?g_fWindowsNT@Global@@2_NA, dil; bool Global::g_fWindowsNT
0x180004d12  jz      loc_180004DDA
0x180004d18  mov     rax, cs:qword_180018BA8
0x180004d1f  mov     rbx, [rsp+378h+ppidl]
0x180004d24  test    rax, rax
0x180004d27  jz      short loc_180004D7F
0x180004d29  lea     rdx, [rsp+378h+psz]
0x180004d31  mov     rcx, rbx
0x180004d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d39  test    eax, eax
0x180004d3b  jnz     short loc_180004DBA
0x180004d3d  mov     ebx, 80070003h
0x180004d42  mov     rdx, [rsp+378h+ppidl]
0x180004d47  test    rdx, rdx
0x180004d4a  jnz     loc_180004E28
0x180004d50  mov     rcx, rdi; bstrString
0x180004d53  call    cs:__imp_SysFreeString
0x180004d59  mov     eax, ebx
0x180004d5b  mov     rcx, [rsp+378h+var_28]
0x180004d63  xor     rcx, rsp; StackCookie
0x180004d66  call    __security_check_cookie
0x180004d6b  mov     rbx, [rsp+378h+arg_18]
0x180004d73  add     rsp, 360h
0x180004d7a  pop     r14
0x180004d7c  pop     rdi
0x180004d7d  pop     rsi
0x180004d7e  retn
0x180004d7f  xor     edx, edx; hFile
0x180004d81  lea     rcx, LibFileName; "shell32.dll"
0x180004d88  mov     r8d, 800h; dwFlags
0x180004d8e  call    cs:__imp_LoadLibraryExW
0x180004d94  test    rax, rax
0x180004d97  jz      short loc_180004D3D
0x180004d99  lea     rdx, ProcName; "SHGetPathFromIDListW"
0x180004da0  mov     rcx, rax; hModule
0x180004da3  call    cs:__imp_GetProcAddress
0x180004da9  mov     cs:qword_180018BA8, rax
0x180004db0  test    rax, rax
0x180004db3  jz      short loc_180004D3D
0x180004db5  jmp     loc_180004D29
0x180004dba  lea     rcx, [rsp+378h+psz]; psz
0x180004dc2  call    cs:__imp_SysAllocString
0x180004dc8  mov     rdi, rax
0x180004dcb  test    rax, rax
0x180004dce  jnz     short loc_180004E16
0x180004dd0  mov     ebx, 8007000Eh
0x180004dd5  jmp     loc_180004D42
0x180004dda  mov     rcx, [rsp+378h+ppidl]; pidl
0x180004ddf  lea     rdx, [rsp+378h+pszPath]; pszPath
0x180004de4  call    cs:__imp_SHGetPathFromIDListA
0x180004dea  test    eax, eax
0x180004dec  jnz     short loc_180004DF8
0x180004dee  mov     ebx, 80070003h
0x180004df3  jmp     loc_180004D42
0x180004df8  lea     rdx, [rsp+378h+var_350]; unsigned __int16 **
0x180004dfd  lea     rcx, [rsp+378h+pszPath]; lpMultiByteStr
0x180004e02  call    ?PSZToBSTR@@YAJPEBDPEAPEAG@Z; PSZToBSTR(char const *,ushort * *)
0x180004e07  mov     rdi, [rsp+378h+var_350]
0x180004e0c  mov     ebx, eax
0x180004e0e  test    eax, eax
0x180004e10  js      loc_180004D42
0x180004e16  mov     [rsi+8], rdi
0x180004e1a  xor     edi, edi
0x180004e1c  xor     ebx, ebx
0x180004e1e  mov     word ptr [rsi], 8
0x180004e23  jmp     loc_180004D42
0x180004e28  mov     rax, [r14]
0x180004e2b  mov     rcx, r14
0x180004e2e  mov     rax, [rax+28h]
0x180004e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e37  jmp     loc_180004D50
```
