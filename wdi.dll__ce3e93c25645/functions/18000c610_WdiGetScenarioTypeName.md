# WdiGetScenarioTypeName

- ea: `0x18000c610`
- end: `0x18000c87b`
- name: `WdiGetScenarioTypeName`
- size: `619`
- prototype: `__int64 __fastcall(__int64, unsigned int, WCHAR *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180007020`
- `0x18000c610`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18000c788`
- `msvcrt!swscanf_s` at `0x18000c788`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c857`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c7e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c857`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c838`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c838`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c7b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c7b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c7dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c7dc`

## pseudocode

```c
__int64 __fastcall WdiGetScenarioTypeName(__int64 a1, unsigned int a2, WCHAR *a3, int a4)
{
  HMODULE Library; // rsi
  const wchar_t *v5; // r15
  const WCHAR *v6; // rbp
  signed int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rdi
  signed int Args; // eax
  int v13; // r8d
  bool v14; // sf
  signed int LastError; // eax
  UINT uID; // [rsp+60h] [rbp+8h] BYREF

  Library = 0;
  v5 = 0;
  v6 = 0;
  uID = 0;
  if ( !a1 )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      964,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      965,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  v10 = *(_QWORD *)(a1 + 168);
  if ( !v10 )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      966,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 16) != 1 )
  {
    v9 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      971,
      (int)L"Error = %d",
      221);
    goto LABEL_29;
  }
  if ( a2 >= *(_DWORD *)(a1 + 156) )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      979,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  v11 = 104LL * a2;
  if ( (*(_BYTE *)(v11 + v10 + 68) & 2) != 0 )
  {
    v9 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      992,
      (int)L"Error = %d",
      221);
    goto LABEL_29;
  }
  v5 = (const wchar_t *)WdipAlloc(2048);
  if ( !v5 )
  {
    v9 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      997,
      (int)L"Error = %d",
      14);
    goto LABEL_29;
  }
  v6 = (const WCHAR *)WdipAlloc(2048);
  if ( !v6 )
  {
    v9 = -2147024882;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      998,
      (int)L"Error = %d",
      14);
    goto LABEL_29;
  }
  Args = WdipExpandVariables(v5, 1024, *(_QWORD *)(v11 + v10 + 88));
  v9 = Args;
  if ( Args < 0 )
  {
    v13 = 1004;
LABEL_28:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      v13,
      (int)L"Error = %d",
      Args);
    goto LABEL_29;
  }
  if ( swscanf_s(v5, L"@%[^,],-%d", v6, 1024, &uID) != 2 )
  {
    v9 = -2147467259;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioTypeName",
      1014,
      (int)L"Error = %d",
      5);
    goto LABEL_29;
  }
  Library = LoadLibraryExW(v6, 0, 0x20u);
  if ( (unsigned __int64)Library - 1 > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( v9 < 0 )
    {
      LOBYTE(Args) = v9;
      v13 = 1018;
      goto LABEL_28;
    }
  }
  else
  {
    v9 = 0;
  }
  if ( !LoadStringW(Library, uID, a3, a4) )
  {
    Args = GetLastError();
    v14 = Args < 0;
    if ( Args > 0 )
    {
      Args = (unsigned __int16)Args | 0x80070000;
      v14 = Args < 0;
    }
    if ( v14 )
    {
      v13 = 1025;
      goto LABEL_28;
    }
  }
LABEL_29:
  WdipFree(v5);
  WdipFree(v6);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c610  mov     rax, rsp
0x18000c613  mov     [rax+10h], rbx
0x18000c617  mov     [rax+18h], rbp
0x18000c61b  push    rsi
0x18000c61c  push    rdi
0x18000c61d  push    r12
0x18000c61f  push    r14
0x18000c621  push    r15
0x18000c623  sub     rsp, 30h
0x18000c627  xor     esi, esi
0x18000c629  xor     r15d, r15d
0x18000c62c  xor     ebp, ebp
0x18000c62e  mov     [rax+8], esi
0x18000c631  mov     r12d, r9d
0x18000c634  mov     r14, r8
0x18000c637  test    rcx, rcx
0x18000c63a  jnz     short loc_18000C653
0x18000c63c  mov     ebx, 80070057h
0x18000c641  mov     dword ptr [rax-38h], 57h ; 'W'
0x18000c648  mov     r8d, 3C4h
0x18000c64e  jmp     loc_18000C806
0x18000c653  test    r14, r14
0x18000c656  jnz     short loc_18000C670
0x18000c658  mov     ebx, 80070057h
0x18000c65d  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c665  mov     r8d, 3C5h
0x18000c66b  jmp     loc_18000C806
0x18000c670  mov     rbx, [rcx+0A8h]
0x18000c677  test    rbx, rbx
0x18000c67a  jnz     short loc_18000C694
0x18000c67c  mov     ebx, 80070057h
0x18000c681  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c689  mov     r8d, 3C6h
0x18000c68f  jmp     loc_18000C806
0x18000c694  cmp     dword ptr [rcx+10h], 1
0x18000c698  jz      short loc_18000C6B2
0x18000c69a  mov     ebx, 800710DDh
0x18000c69f  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000c6a7  mov     r8d, 3CBh
0x18000c6ad  jmp     loc_18000C806
0x18000c6b2  cmp     edx, [rcx+9Ch]
0x18000c6b8  jb      short loc_18000C6D2
0x18000c6ba  mov     ebx, 80070057h
0x18000c6bf  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c6c7  mov     r8d, 3D3h
0x18000c6cd  jmp     loc_18000C806
0x18000c6d2  mov     eax, edx
0x18000c6d4  imul    rdi, rax, 68h ; 'h'
0x18000c6d8  test    byte ptr [rdi+rbx+44h], 2
0x18000c6dd  jz      short loc_18000C6F7
0x18000c6df  mov     ebx, 800710DDh
0x18000c6e4  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000c6ec  mov     r8d, 3E0h
0x18000c6f2  jmp     loc_18000C806
0x18000c6f7  mov     ecx, 800h
0x18000c6fc  call    WdipAlloc
0x18000c701  mov     r15, rax
0x18000c704  test    rax, rax
0x18000c707  jnz     short loc_18000C721
0x18000c709  mov     ebx, 8007000Eh
0x18000c70e  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000c716  mov     r8d, 3E5h
0x18000c71c  jmp     loc_18000C806
0x18000c721  mov     ecx, 800h
0x18000c726  call    WdipAlloc
0x18000c72b  mov     rbp, rax
0x18000c72e  test    rax, rax
0x18000c731  jnz     short loc_18000C74B
0x18000c733  mov     ebx, 8007000Eh
0x18000c738  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000c740  mov     r8d, 3E6h
0x18000c746  jmp     loc_18000C806
0x18000c74b  mov     r8, [rdi+rbx+58h]
0x18000c750  mov     rcx, r15
0x18000c753  mov     edi, 400h
0x18000c758  mov     edx, edi
0x18000c75a  call    WdipExpandVariables
0x18000c75f  mov     ebx, eax
0x18000c761  test    eax, eax
0x18000c763  jns     short loc_18000C76E
0x18000c765  lea     r8d, [rdi-14h]
0x18000c769  jmp     loc_18000C7FF
0x18000c76e  lea     rax, [rsp+58h+uID]
0x18000c773  mov     r9d, edi
0x18000c776  mov     r8, rbp
0x18000c779  mov     qword ptr [rsp+58h+Args], rax
0x18000c77e  lea     rdx, aD; "@%[^,],-%d"
0x18000c785  mov     rcx, r15; Buffer
0x18000c788  call    cs:__imp_swscanf_s
0x18000c78e  cmp     eax, 2
0x18000c791  jz      short loc_18000C7A8
0x18000c793  mov     ebx, 80004005h
0x18000c798  mov     dword ptr [rsp+58h+Args], 4005h
0x18000c7a0  mov     r8d, 3F6h
0x18000c7a6  jmp     short loc_18000C806
0x18000c7a8  xor     edx, edx; hFile
0x18000c7aa  mov     rcx, rbp; lpLibFileName
0x18000c7ad  lea     r8d, [rdx+20h]; dwFlags
0x18000c7b1  call    cs:__imp_LoadLibraryExW
0x18000c7b7  mov     rsi, rax
0x18000c7ba  mov     edi, 80070000h
0x18000c7bf  lea     rcx, [rax-1]
0x18000c7c3  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c7c7  ja      loc_18000C857
0x18000c7cd  xor     ebx, ebx
0x18000c7cf  mov     edx, [rsp+58h+uID]; uID
0x18000c7d3  mov     r9d, r12d; cchBufferMax
0x18000c7d6  mov     r8, r14; lpBuffer
0x18000c7d9  mov     rcx, rsi; hInstance
0x18000c7dc  call    cs:__imp_LoadStringW
0x18000c7e2  test    eax, eax
0x18000c7e4  jnz     short loc_18000C820
0x18000c7e6  call    cs:__imp_GetLastError
0x18000c7ec  test    eax, eax
0x18000c7ee  jle     short loc_18000C7F7
0x18000c7f0  movzx   eax, ax
0x18000c7f3  or      eax, edi
0x18000c7f5  test    eax, eax
0x18000c7f7  jns     short loc_18000C820
0x18000c7f9  mov     r8d, 401h; int
0x18000c7ff  movzx   eax, ax
0x18000c802  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000c806  lea     r9, aErrorD_0; "Error = %d"
0x18000c80d  lea     rdx, aWdigetscenario_10; "WdiGetScenarioTypeName"
0x18000c814  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000c81b  call    WdipTraceError
0x18000c820  mov     rcx, r15
0x18000c823  call    WdipFree
0x18000c828  mov     rcx, rbp
0x18000c82b  call    WdipFree
0x18000c830  test    rsi, rsi
0x18000c833  jz      short loc_18000C83E
0x18000c835  mov     rcx, rsi; hLibModule
0x18000c838  call    cs:__imp_FreeLibrary
0x18000c83e  mov     rbp, [rsp+58h+arg_10]
0x18000c843  mov     eax, ebx
0x18000c845  mov     rbx, [rsp+58h+arg_8]
0x18000c84a  add     rsp, 30h
0x18000c84e  pop     r15
0x18000c850  pop     r14
0x18000c852  pop     r12
0x18000c854  pop     rdi
0x18000c855  pop     rsi
0x18000c856  retn
0x18000c857  call    cs:__imp_GetLastError
0x18000c85d  mov     ebx, eax
0x18000c85f  test    eax, eax
0x18000c861  jle     short loc_18000C868
0x18000c863  movzx   ebx, ax
0x18000c866  or      ebx, edi
0x18000c868  test    ebx, ebx
0x18000c86a  jns     loc_18000C7CF
0x18000c870  movzx   eax, bx
0x18000c873  mov     r8d, 3FAh
0x18000c879  jmp     short loc_18000C802
```
