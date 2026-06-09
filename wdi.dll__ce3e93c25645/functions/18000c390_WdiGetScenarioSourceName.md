# WdiGetScenarioSourceName

- ea: `0x18000c390`
- end: `0x18000c5fd`
- name: `WdiGetScenarioSourceName`
- size: `621`
- prototype: `__int64 __fastcall(__int64, unsigned int, WCHAR *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180007020`
- `0x18000c390`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18000c50a`
- `msvcrt!swscanf_s` at `0x18000c50a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c568`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c5d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c5ba`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c5ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c533`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c533`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c55e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000c55e`

## pseudocode

```c
__int64 __fastcall WdiGetScenarioSourceName(__int64 a1, unsigned int a2, WCHAR *a3, int a4)
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
      (int)L"WdiGetScenarioSourceName",
      850,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioSourceName",
      851,
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
      (int)L"WdiGetScenarioSourceName",
      852,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 16) != 1 )
  {
    v9 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioSourceName",
      857,
      (int)L"Error = %d",
      221);
    goto LABEL_29;
  }
  if ( a2 >= *(_DWORD *)(a1 + 156) )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioSourceName",
      865,
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
      (int)L"WdiGetScenarioSourceName",
      878,
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
      (int)L"WdiGetScenarioSourceName",
      883,
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
      (int)L"WdiGetScenarioSourceName",
      884,
      (int)L"Error = %d",
      14);
    goto LABEL_29;
  }
  Args = WdipExpandVariables(v5, 1024, *(_QWORD *)(v11 + v10 + 80));
  v9 = Args;
  if ( Args < 0 )
  {
    v13 = 890;
LABEL_28:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetScenarioSourceName",
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
      (int)L"WdiGetScenarioSourceName",
      900,
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
      v13 = 904;
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
      v13 = 911;
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
0x18000c390  mov     rax, rsp
0x18000c393  mov     [rax+10h], rbx
0x18000c397  mov     [rax+18h], rbp
0x18000c39b  push    rsi
0x18000c39c  push    rdi
0x18000c39d  push    r12
0x18000c39f  push    r14
0x18000c3a1  push    r15
0x18000c3a3  sub     rsp, 30h
0x18000c3a7  xor     esi, esi
0x18000c3a9  xor     r15d, r15d
0x18000c3ac  xor     ebp, ebp
0x18000c3ae  mov     [rax+8], esi
0x18000c3b1  mov     r12d, r9d
0x18000c3b4  mov     r14, r8
0x18000c3b7  test    rcx, rcx
0x18000c3ba  jnz     short loc_18000C3D3
0x18000c3bc  mov     ebx, 80070057h
0x18000c3c1  mov     dword ptr [rax-38h], 57h ; 'W'
0x18000c3c8  mov     r8d, 352h
0x18000c3ce  jmp     loc_18000C588
0x18000c3d3  test    r14, r14
0x18000c3d6  jnz     short loc_18000C3F0
0x18000c3d8  mov     ebx, 80070057h
0x18000c3dd  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c3e5  mov     r8d, 353h
0x18000c3eb  jmp     loc_18000C588
0x18000c3f0  mov     rbx, [rcx+0A8h]
0x18000c3f7  test    rbx, rbx
0x18000c3fa  jnz     short loc_18000C414
0x18000c3fc  mov     ebx, 80070057h
0x18000c401  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c409  mov     r8d, 354h
0x18000c40f  jmp     loc_18000C588
0x18000c414  cmp     dword ptr [rcx+10h], 1
0x18000c418  jz      short loc_18000C432
0x18000c41a  mov     ebx, 800710DDh
0x18000c41f  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000c427  mov     r8d, 359h
0x18000c42d  jmp     loc_18000C588
0x18000c432  cmp     edx, [rcx+9Ch]
0x18000c438  jb      short loc_18000C452
0x18000c43a  mov     ebx, 80070057h
0x18000c43f  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000c447  mov     r8d, 361h
0x18000c44d  jmp     loc_18000C588
0x18000c452  mov     eax, edx
0x18000c454  imul    rdi, rax, 68h ; 'h'
0x18000c458  test    byte ptr [rdi+rbx+44h], 2
0x18000c45d  jz      short loc_18000C477
0x18000c45f  mov     ebx, 800710DDh
0x18000c464  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000c46c  mov     r8d, 36Eh
0x18000c472  jmp     loc_18000C588
0x18000c477  mov     ecx, 800h
0x18000c47c  call    WdipAlloc
0x18000c481  mov     r15, rax
0x18000c484  test    rax, rax
0x18000c487  jnz     short loc_18000C4A1
0x18000c489  mov     ebx, 8007000Eh
0x18000c48e  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000c496  mov     r8d, 373h
0x18000c49c  jmp     loc_18000C588
0x18000c4a1  mov     ecx, 800h
0x18000c4a6  call    WdipAlloc
0x18000c4ab  mov     rbp, rax
0x18000c4ae  test    rax, rax
0x18000c4b1  jnz     short loc_18000C4CB
0x18000c4b3  mov     ebx, 8007000Eh
0x18000c4b8  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000c4c0  mov     r8d, 374h
0x18000c4c6  jmp     loc_18000C588
0x18000c4cb  mov     r8, [rdi+rbx+50h]
0x18000c4d0  mov     rcx, r15
0x18000c4d3  mov     edi, 400h
0x18000c4d8  mov     edx, edi
0x18000c4da  call    WdipExpandVariables
0x18000c4df  mov     ebx, eax
0x18000c4e1  test    eax, eax
0x18000c4e3  jns     short loc_18000C4F0
0x18000c4e5  mov     r8d, 37Ah
0x18000c4eb  jmp     loc_18000C581
0x18000c4f0  lea     rax, [rsp+58h+uID]
0x18000c4f5  mov     r9d, edi
0x18000c4f8  mov     r8, rbp
0x18000c4fb  mov     qword ptr [rsp+58h+Args], rax
0x18000c500  lea     rdx, aD; "@%[^,],-%d"
0x18000c507  mov     rcx, r15; Buffer
0x18000c50a  call    cs:__imp_swscanf_s
0x18000c510  cmp     eax, 2
0x18000c513  jz      short loc_18000C52A
0x18000c515  mov     ebx, 80004005h
0x18000c51a  mov     dword ptr [rsp+58h+Args], 4005h
0x18000c522  mov     r8d, 384h
0x18000c528  jmp     short loc_18000C588
0x18000c52a  xor     edx, edx; hFile
0x18000c52c  mov     rcx, rbp; lpLibFileName
0x18000c52f  lea     r8d, [rdx+20h]; dwFlags
0x18000c533  call    cs:__imp_LoadLibraryExW
0x18000c539  mov     rsi, rax
0x18000c53c  mov     edi, 80070000h
0x18000c541  lea     rcx, [rax-1]
0x18000c545  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000c549  ja      loc_18000C5D9
0x18000c54f  xor     ebx, ebx
0x18000c551  mov     edx, [rsp+58h+uID]; uID
0x18000c555  mov     r9d, r12d; cchBufferMax
0x18000c558  mov     r8, r14; lpBuffer
0x18000c55b  mov     rcx, rsi; hInstance
0x18000c55e  call    cs:__imp_LoadStringW
0x18000c564  test    eax, eax
0x18000c566  jnz     short loc_18000C5A2
0x18000c568  call    cs:__imp_GetLastError
0x18000c56e  test    eax, eax
0x18000c570  jle     short loc_18000C579
0x18000c572  movzx   eax, ax
0x18000c575  or      eax, edi
0x18000c577  test    eax, eax
0x18000c579  jns     short loc_18000C5A2
0x18000c57b  mov     r8d, 38Fh; int
0x18000c581  movzx   eax, ax
0x18000c584  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000c588  lea     r9, aErrorD_0; "Error = %d"
0x18000c58f  lea     rdx, aWdigetscenario_14; "WdiGetScenarioSourceName"
0x18000c596  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000c59d  call    WdipTraceError
0x18000c5a2  mov     rcx, r15
0x18000c5a5  call    WdipFree
0x18000c5aa  mov     rcx, rbp
0x18000c5ad  call    WdipFree
0x18000c5b2  test    rsi, rsi
0x18000c5b5  jz      short loc_18000C5C0
0x18000c5b7  mov     rcx, rsi; hLibModule
0x18000c5ba  call    cs:__imp_FreeLibrary
0x18000c5c0  mov     rbp, [rsp+58h+arg_10]
0x18000c5c5  mov     eax, ebx
0x18000c5c7  mov     rbx, [rsp+58h+arg_8]
0x18000c5cc  add     rsp, 30h
0x18000c5d0  pop     r15
0x18000c5d2  pop     r14
0x18000c5d4  pop     r12
0x18000c5d6  pop     rdi
0x18000c5d7  pop     rsi
0x18000c5d8  retn
0x18000c5d9  call    cs:__imp_GetLastError
0x18000c5df  mov     ebx, eax
0x18000c5e1  test    eax, eax
0x18000c5e3  jle     short loc_18000C5EA
0x18000c5e5  movzx   ebx, ax
0x18000c5e8  or      ebx, edi
0x18000c5ea  test    ebx, ebx
0x18000c5ec  jns     loc_18000C551
0x18000c5f2  movzx   eax, bx
0x18000c5f5  mov     r8d, 388h
0x18000c5fb  jmp     short loc_18000C584
```
