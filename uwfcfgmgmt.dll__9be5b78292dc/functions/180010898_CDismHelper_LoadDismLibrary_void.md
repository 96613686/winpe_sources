# CDismHelper::LoadDismLibrary(void)

- ea: `0x180010898`
- end: `0x180010a54`
- name: `?LoadDismLibrary@CDismHelper@@QEAAJXZ`
- size: `444`
- prototype: `__int64 __fastcall(HMODULE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f364`

## callees

- `0x180010898`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001091e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001094e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001097e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010a32`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800108ee`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001091e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001094e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001097e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800109da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010a06`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010a32`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800108bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800108bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001092d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001095d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001098d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800108fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001092d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001095d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001098d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800109e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010a41`

## string_xrefs

- `0x1800108b2`: `dismapi.dll`
- `0x180010917`: `DismOpenSession`
- `0x1800109ff`: `DismDelete`

## pseudocode

```c
__int64 __fastcall CDismHelper::LoadDismLibrary(HMODULE *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  bool v4; // sf
  FARPROC ProcAddress; // rax
  signed int v6; // eax
  bool v7; // sf
  FARPROC v8; // rax
  signed int v9; // eax
  bool v10; // sf
  FARPROC v11; // rax
  signed int v12; // eax
  bool v13; // sf
  FARPROC v14; // rax
  signed int v15; // eax
  bool v16; // sf
  FARPROC v17; // rax
  signed int v18; // eax
  bool v19; // sf
  FARPROC v20; // rax
  signed int v21; // eax
  bool v22; // sf
  FARPROC v23; // rax
  signed int v24; // eax
  bool v25; // sf
  FARPROC v26; // rax

  if ( *this )
    goto LABEL_6;
  Library = LoadLibraryExW(L"dismapi.dll", 0, 0x800u);
  *this = Library;
  if ( Library )
    goto LABEL_6;
  LastError = GetLastError();
  v4 = LastError < 0;
  if ( LastError > 0 )
    v4 = 1;
  if ( !v4 )
  {
LABEL_6:
    ProcAddress = GetProcAddress(*this, "DismInitialize");
    this[1] = (HMODULE)ProcAddress;
    if ( ProcAddress )
      goto LABEL_10;
    v6 = GetLastError();
    v7 = v6 < 0;
    if ( v6 > 0 )
      v7 = 1;
    if ( !v7 )
    {
LABEL_10:
      v8 = GetProcAddress(*this, "DismOpenSession");
      this[2] = (HMODULE)v8;
      if ( v8 )
        goto LABEL_14;
      v9 = GetLastError();
      v10 = v9 < 0;
      if ( v9 > 0 )
        v10 = 1;
      if ( !v10 )
      {
LABEL_14:
        v11 = GetProcAddress(*this, "DismEnableFeature");
        this[3] = (HMODULE)v11;
        if ( v11 )
          goto LABEL_18;
        v12 = GetLastError();
        v13 = v12 < 0;
        if ( v12 > 0 )
          v13 = 1;
        if ( !v13 )
        {
LABEL_18:
          v14 = GetProcAddress(*this, "DismDisableFeature");
          this[4] = (HMODULE)v14;
          if ( v14 )
            goto LABEL_22;
          v15 = GetLastError();
          v16 = v15 < 0;
          if ( v15 > 0 )
            v16 = 1;
          if ( !v16 )
          {
LABEL_22:
            v17 = GetProcAddress(*this, "DismGetFeatureInfo");
            this[5] = (HMODULE)v17;
            if ( v17 )
              goto LABEL_26;
            v18 = GetLastError();
            v19 = v18 < 0;
            if ( v18 > 0 )
              v19 = 1;
            if ( !v19 )
            {
LABEL_26:
              v20 = GetProcAddress(*this, "DismCloseSession");
              this[7] = (HMODULE)v20;
              if ( v20 )
                goto LABEL_30;
              v21 = GetLastError();
              v22 = v21 < 0;
              if ( v21 > 0 )
                v22 = 1;
              if ( !v22 )
              {
LABEL_30:
                v23 = GetProcAddress(*this, "DismDelete");
                this[6] = (HMODULE)v23;
                if ( v23 )
                  goto LABEL_34;
                v24 = GetLastError();
                v25 = v24 < 0;
                if ( v24 > 0 )
                  v25 = 1;
                if ( !v25 )
                {
LABEL_34:
                  v26 = GetProcAddress(*this, "DismShutdown");
                  this[8] = (HMODULE)v26;
                  if ( !v26 )
                    GetLastError();
                }
              }
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180010898  mov     [rsp+arg_0], rbx
0x18001089d  push    rdi
0x18001089e  sub     rsp, 20h
0x1800108a2  cmp     qword ptr [rcx], 0
0x1800108a6  mov     rbx, rcx
0x1800108a9  mov     edi, 80070000h
0x1800108ae  jnz     short loc_1800108E4
0x1800108b0  xor     edx, edx; hFile
0x1800108b2  lea     rcx, aDismapiDll; "dismapi.dll"
0x1800108b9  mov     r8d, 800h; dwFlags
0x1800108bf  call    cs:__imp_LoadLibraryExW
0x1800108c5  mov     [rbx], rax
0x1800108c8  test    rax, rax
0x1800108cb  jnz     short loc_1800108E4
0x1800108cd  call    cs:__imp_GetLastError
0x1800108d3  test    eax, eax
0x1800108d5  jle     short loc_1800108DE
0x1800108d7  movzx   eax, ax
0x1800108da  or      eax, edi
0x1800108dc  test    eax, eax
0x1800108de  js      loc_180010A47
0x1800108e4  mov     rcx, [rbx]; hModule
0x1800108e7  lea     rdx, aDisminitialize; "DismInitialize"
0x1800108ee  call    cs:__imp_GetProcAddress
0x1800108f4  mov     [rbx+8], rax
0x1800108f8  test    rax, rax
0x1800108fb  jnz     short loc_180010914
0x1800108fd  call    cs:__imp_GetLastError
0x180010903  test    eax, eax
0x180010905  jle     short loc_18001090E
0x180010907  movzx   eax, ax
0x18001090a  or      eax, edi
0x18001090c  test    eax, eax
0x18001090e  js      loc_180010A47
0x180010914  mov     rcx, [rbx]; hModule
0x180010917  lea     rdx, aDismopensessio; "DismOpenSession"
0x18001091e  call    cs:__imp_GetProcAddress
0x180010924  mov     [rbx+10h], rax
0x180010928  test    rax, rax
0x18001092b  jnz     short loc_180010944
0x18001092d  call    cs:__imp_GetLastError
0x180010933  test    eax, eax
0x180010935  jle     short loc_18001093E
0x180010937  movzx   eax, ax
0x18001093a  or      eax, edi
0x18001093c  test    eax, eax
0x18001093e  js      loc_180010A47
0x180010944  mov     rcx, [rbx]; hModule
0x180010947  lea     rdx, aDismenablefeat; "DismEnableFeature"
0x18001094e  call    cs:__imp_GetProcAddress
0x180010954  mov     [rbx+18h], rax
0x180010958  test    rax, rax
0x18001095b  jnz     short loc_180010974
0x18001095d  call    cs:__imp_GetLastError
0x180010963  test    eax, eax
0x180010965  jle     short loc_18001096E
0x180010967  movzx   eax, ax
0x18001096a  or      eax, edi
0x18001096c  test    eax, eax
0x18001096e  js      loc_180010A47
0x180010974  mov     rcx, [rbx]; hModule
0x180010977  lea     rdx, aDismdisablefea; "DismDisableFeature"
0x18001097e  call    cs:__imp_GetProcAddress
0x180010984  mov     [rbx+20h], rax
0x180010988  test    rax, rax
0x18001098b  jnz     short loc_1800109A4
0x18001098d  call    cs:__imp_GetLastError
0x180010993  test    eax, eax
0x180010995  jle     short loc_18001099E
0x180010997  movzx   eax, ax
0x18001099a  or      eax, edi
0x18001099c  test    eax, eax
0x18001099e  js      loc_180010A47
0x1800109a4  mov     rcx, [rbx]; hModule
0x1800109a7  lea     rdx, aDismgetfeature; "DismGetFeatureInfo"
0x1800109ae  call    cs:__imp_GetProcAddress
0x1800109b4  mov     [rbx+28h], rax
0x1800109b8  test    rax, rax
0x1800109bb  jnz     short loc_1800109D0
0x1800109bd  call    cs:__imp_GetLastError
0x1800109c3  test    eax, eax
0x1800109c5  jle     short loc_1800109CE
0x1800109c7  movzx   eax, ax
0x1800109ca  or      eax, edi
0x1800109cc  test    eax, eax
0x1800109ce  js      short loc_180010A47
0x1800109d0  mov     rcx, [rbx]; hModule
0x1800109d3  lea     rdx, aDismclosesessi; "DismCloseSession"
0x1800109da  call    cs:__imp_GetProcAddress
0x1800109e0  mov     [rbx+38h], rax
0x1800109e4  test    rax, rax
0x1800109e7  jnz     short loc_1800109FC
0x1800109e9  call    cs:__imp_GetLastError
0x1800109ef  test    eax, eax
0x1800109f1  jle     short loc_1800109FA
0x1800109f3  movzx   eax, ax
0x1800109f6  or      eax, edi
0x1800109f8  test    eax, eax
0x1800109fa  js      short loc_180010A47
0x1800109fc  mov     rcx, [rbx]; hModule
0x1800109ff  lea     rdx, aDismdelete; "DismDelete"
0x180010a06  call    cs:__imp_GetProcAddress
0x180010a0c  mov     [rbx+30h], rax
0x180010a10  test    rax, rax
0x180010a13  jnz     short loc_180010A28
0x180010a15  call    cs:__imp_GetLastError
0x180010a1b  test    eax, eax
0x180010a1d  jle     short loc_180010A26
0x180010a1f  movzx   eax, ax
0x180010a22  or      eax, edi
0x180010a24  test    eax, eax
0x180010a26  js      short loc_180010A47
0x180010a28  mov     rcx, [rbx]; hModule
0x180010a2b  lea     rdx, aDismshutdown; "DismShutdown"
0x180010a32  call    cs:__imp_GetProcAddress
0x180010a38  mov     [rbx+40h], rax
0x180010a3c  test    rax, rax
0x180010a3f  jnz     short loc_180010A47
0x180010a41  call    cs:__imp_GetLastError
0x180010a47  mov     rbx, [rsp+28h+arg_0]
0x180010a4c  xor     eax, eax
0x180010a4e  add     rsp, 20h
0x180010a52  pop     rdi
0x180010a53  retn
```
