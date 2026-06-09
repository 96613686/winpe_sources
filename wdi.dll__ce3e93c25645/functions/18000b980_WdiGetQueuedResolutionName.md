# WdiGetQueuedResolutionName

- ea: `0x18000b980`
- end: `0x18000bbed`
- name: `WdiGetQueuedResolutionName`
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
- `0x18000b980`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18000bafa`
- `msvcrt!swscanf_s` at `0x18000bafa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bb58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bbc9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bbaa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bbaa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bb23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bb23`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bb4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000bb4e`

## pseudocode

```c
__int64 __fastcall WdiGetQueuedResolutionName(__int64 a1, unsigned int a2, WCHAR *a3, int a4)
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
      (int)L"WdiGetQueuedResolutionName",
      1146,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( !a3 )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetQueuedResolutionName",
      1147,
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
      (int)L"WdiGetQueuedResolutionName",
      1148,
      (int)L"Error = %d",
      87);
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 16) != 1 )
  {
    v9 = -2147020579;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetQueuedResolutionName",
      1153,
      (int)L"Error = %d",
      221);
    goto LABEL_29;
  }
  if ( a2 >= *(_DWORD *)(a1 + 156) )
  {
    v9 = -2147024809;
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetQueuedResolutionName",
      1161,
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
      (int)L"WdiGetQueuedResolutionName",
      1174,
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
      (int)L"WdiGetQueuedResolutionName",
      1179,
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
      (int)L"WdiGetQueuedResolutionName",
      1180,
      (int)L"Error = %d",
      14);
    goto LABEL_29;
  }
  Args = WdipExpandVariables(v5, 1024, *(_QWORD *)(v11 + v10 + 96));
  v9 = Args;
  if ( Args < 0 )
  {
    v13 = 1186;
LABEL_28:
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
      (int)L"WdiGetQueuedResolutionName",
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
      (int)L"WdiGetQueuedResolutionName",
      1196,
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
      v13 = 1200;
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
      v13 = 1207;
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
0x18000b980  mov     rax, rsp
0x18000b983  mov     [rax+10h], rbx
0x18000b987  mov     [rax+18h], rbp
0x18000b98b  push    rsi
0x18000b98c  push    rdi
0x18000b98d  push    r12
0x18000b98f  push    r14
0x18000b991  push    r15
0x18000b993  sub     rsp, 30h
0x18000b997  xor     esi, esi
0x18000b999  xor     r15d, r15d
0x18000b99c  xor     ebp, ebp
0x18000b99e  mov     [rax+8], esi
0x18000b9a1  mov     r12d, r9d
0x18000b9a4  mov     r14, r8
0x18000b9a7  test    rcx, rcx
0x18000b9aa  jnz     short loc_18000B9C3
0x18000b9ac  mov     ebx, 80070057h
0x18000b9b1  mov     dword ptr [rax-38h], 57h ; 'W'
0x18000b9b8  mov     r8d, 47Ah
0x18000b9be  jmp     loc_18000BB78
0x18000b9c3  test    r14, r14
0x18000b9c6  jnz     short loc_18000B9E0
0x18000b9c8  mov     ebx, 80070057h
0x18000b9cd  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000b9d5  mov     r8d, 47Bh
0x18000b9db  jmp     loc_18000BB78
0x18000b9e0  mov     rbx, [rcx+0A8h]
0x18000b9e7  test    rbx, rbx
0x18000b9ea  jnz     short loc_18000BA04
0x18000b9ec  mov     ebx, 80070057h
0x18000b9f1  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000b9f9  mov     r8d, 47Ch
0x18000b9ff  jmp     loc_18000BB78
0x18000ba04  cmp     dword ptr [rcx+10h], 1
0x18000ba08  jz      short loc_18000BA22
0x18000ba0a  mov     ebx, 800710DDh
0x18000ba0f  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000ba17  mov     r8d, 481h
0x18000ba1d  jmp     loc_18000BB78
0x18000ba22  cmp     edx, [rcx+9Ch]
0x18000ba28  jb      short loc_18000BA42
0x18000ba2a  mov     ebx, 80070057h
0x18000ba2f  mov     dword ptr [rsp+58h+Args], 57h ; 'W'
0x18000ba37  mov     r8d, 489h
0x18000ba3d  jmp     loc_18000BB78
0x18000ba42  mov     eax, edx
0x18000ba44  imul    rdi, rax, 68h ; 'h'
0x18000ba48  test    byte ptr [rdi+rbx+44h], 2
0x18000ba4d  jz      short loc_18000BA67
0x18000ba4f  mov     ebx, 800710DDh
0x18000ba54  mov     dword ptr [rsp+58h+Args], 10DDh
0x18000ba5c  mov     r8d, 496h
0x18000ba62  jmp     loc_18000BB78
0x18000ba67  mov     ecx, 800h
0x18000ba6c  call    WdipAlloc
0x18000ba71  mov     r15, rax
0x18000ba74  test    rax, rax
0x18000ba77  jnz     short loc_18000BA91
0x18000ba79  mov     ebx, 8007000Eh
0x18000ba7e  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000ba86  mov     r8d, 49Bh
0x18000ba8c  jmp     loc_18000BB78
0x18000ba91  mov     ecx, 800h
0x18000ba96  call    WdipAlloc
0x18000ba9b  mov     rbp, rax
0x18000ba9e  test    rax, rax
0x18000baa1  jnz     short loc_18000BABB
0x18000baa3  mov     ebx, 8007000Eh
0x18000baa8  mov     dword ptr [rsp+58h+Args], 0Eh
0x18000bab0  mov     r8d, 49Ch
0x18000bab6  jmp     loc_18000BB78
0x18000babb  mov     r8, [rdi+rbx+60h]
0x18000bac0  mov     rcx, r15
0x18000bac3  mov     edi, 400h
0x18000bac8  mov     edx, edi
0x18000baca  call    WdipExpandVariables
0x18000bacf  mov     ebx, eax
0x18000bad1  test    eax, eax
0x18000bad3  jns     short loc_18000BAE0
0x18000bad5  mov     r8d, 4A2h
0x18000badb  jmp     loc_18000BB71
0x18000bae0  lea     rax, [rsp+58h+uID]
0x18000bae5  mov     r9d, edi
0x18000bae8  mov     r8, rbp
0x18000baeb  mov     qword ptr [rsp+58h+Args], rax
0x18000baf0  lea     rdx, aD; "@%[^,],-%d"
0x18000baf7  mov     rcx, r15; Buffer
0x18000bafa  call    cs:__imp_swscanf_s
0x18000bb00  cmp     eax, 2
0x18000bb03  jz      short loc_18000BB1A
0x18000bb05  mov     ebx, 80004005h
0x18000bb0a  mov     dword ptr [rsp+58h+Args], 4005h
0x18000bb12  mov     r8d, 4ACh
0x18000bb18  jmp     short loc_18000BB78
0x18000bb1a  xor     edx, edx; hFile
0x18000bb1c  mov     rcx, rbp; lpLibFileName
0x18000bb1f  lea     r8d, [rdx+20h]; dwFlags
0x18000bb23  call    cs:__imp_LoadLibraryExW
0x18000bb29  mov     rsi, rax
0x18000bb2c  mov     edi, 80070000h
0x18000bb31  lea     rcx, [rax-1]
0x18000bb35  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000bb39  ja      loc_18000BBC9
0x18000bb3f  xor     ebx, ebx
0x18000bb41  mov     edx, [rsp+58h+uID]; uID
0x18000bb45  mov     r9d, r12d; cchBufferMax
0x18000bb48  mov     r8, r14; lpBuffer
0x18000bb4b  mov     rcx, rsi; hInstance
0x18000bb4e  call    cs:__imp_LoadStringW
0x18000bb54  test    eax, eax
0x18000bb56  jnz     short loc_18000BB92
0x18000bb58  call    cs:__imp_GetLastError
0x18000bb5e  test    eax, eax
0x18000bb60  jle     short loc_18000BB69
0x18000bb62  movzx   eax, ax
0x18000bb65  or      eax, edi
0x18000bb67  test    eax, eax
0x18000bb69  jns     short loc_18000BB92
0x18000bb6b  mov     r8d, 4B7h; int
0x18000bb71  movzx   eax, ax
0x18000bb74  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000bb78  lea     r9, aErrorD_0; "Error = %d"
0x18000bb7f  lea     rdx, aWdigetqueuedre_8; "WdiGetQueuedResolutionName"
0x18000bb86  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000bb8d  call    WdipTraceError
0x18000bb92  mov     rcx, r15
0x18000bb95  call    WdipFree
0x18000bb9a  mov     rcx, rbp
0x18000bb9d  call    WdipFree
0x18000bba2  test    rsi, rsi
0x18000bba5  jz      short loc_18000BBB0
0x18000bba7  mov     rcx, rsi; hLibModule
0x18000bbaa  call    cs:__imp_FreeLibrary
0x18000bbb0  mov     rbp, [rsp+58h+arg_10]
0x18000bbb5  mov     eax, ebx
0x18000bbb7  mov     rbx, [rsp+58h+arg_8]
0x18000bbbc  add     rsp, 30h
0x18000bbc0  pop     r15
0x18000bbc2  pop     r14
0x18000bbc4  pop     r12
0x18000bbc6  pop     rdi
0x18000bbc7  pop     rsi
0x18000bbc8  retn
0x18000bbc9  call    cs:__imp_GetLastError
0x18000bbcf  mov     ebx, eax
0x18000bbd1  test    eax, eax
0x18000bbd3  jle     short loc_18000BBDA
0x18000bbd5  movzx   ebx, ax
0x18000bbd8  or      ebx, edi
0x18000bbda  test    ebx, ebx
0x18000bbdc  jns     loc_18000BB41
0x18000bbe2  movzx   eax, bx
0x18000bbe5  mov     r8d, 4B0h
0x18000bbeb  jmp     short loc_18000BB74
```
