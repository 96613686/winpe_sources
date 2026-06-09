# WdiGetScenarioIcon

- ea: `0x18000bcd0`
- end: `0x18000bf12`
- name: `WdiGetScenarioIcon`
- size: `578`
- prototype: `__int64 __fastcall(__int64, unsigned int, HICON *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180001340`
- `0x180002ba0`
- `0x180003160`
- `0x180007020`
- `0x18000bcd0`

## import_xrefs

- `msvcrt!swscanf_s` at `0x18000be2d`
- `msvcrt!swscanf_s` at `0x18000be2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bee7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000be6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bee7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bed2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000bed2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000be59`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000be59`
- `USER32!LoadIconW` at `0x18000bea2`
- `USER32!LoadIconW` at `0x18000bea2`

## pseudocode

```c
__int64 __fastcall WdiGetScenarioIcon(__int64 a1, unsigned int a2, HICON *a3)
{
  const WCHAR *v3; // rbp
  const wchar_t *v4; // r15
  HMODULE Library; // rsi
  int v7; // r8d
  signed int v8; // ebx
  __int64 v9; // rbx
  __int64 v10; // rdi
  int Args; // eax
  signed int LastError; // eax
  HICON IconW; // rdi
  signed int v15; // eax
  int v16; // [rsp+70h] [rbp+8h] BYREF

  v3 = 0;
  v4 = 0;
  Library = 0;
  v16 = 0;
  if ( a1 )
  {
    if ( a3 )
    {
      v9 = *(_QWORD *)(a1 + 168);
      if ( v9 )
      {
        if ( *(_DWORD *)(a1 + 16) != 1 )
        {
          v8 = -2147020579;
          WdipTraceError(
            (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
            (int)L"WdiGetScenarioIcon",
            745,
            (int)L"Error = %d",
            221);
          goto LABEL_31;
        }
        if ( a2 < *(_DWORD *)(a1 + 156) )
        {
          v10 = 104LL * a2;
          if ( (*(_BYTE *)(v10 + v9 + 68) & 2) != 0 )
          {
            v8 = -2147020579;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioIcon",
              766,
              (int)L"Error = %d",
              221);
            goto LABEL_31;
          }
          v4 = (const wchar_t *)WdipAlloc(2048);
          if ( !v4 )
          {
            v8 = -2147024882;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioIcon",
              771,
              (int)L"Error = %d",
              14);
            goto LABEL_31;
          }
          v3 = (const WCHAR *)WdipAlloc(2048);
          if ( !v3 )
          {
            v8 = -2147024882;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioIcon",
              772,
              (int)L"Error = %d",
              14);
            goto LABEL_31;
          }
          Args = WdipExpandVariables(v4, 1024, *(_QWORD *)(v10 + v9 + 72));
          v8 = Args;
          if ( Args < 0 )
          {
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioIcon",
              778,
              (int)L"Error = %d",
              Args);
            goto LABEL_31;
          }
          if ( swscanf_s(v4, L"@%[^,],-%d", v3, 1024, &v16) != 2 )
          {
            v8 = -2147467259;
            WdipTraceError(
              (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
              (int)L"WdiGetScenarioIcon",
              788,
              (int)L"Error = %d",
              5);
            goto LABEL_31;
          }
          Library = LoadLibraryExW(v3, 0, 0x20u);
          if ( (((unsigned __int64)Library + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
          {
            LastError = GetLastError();
            v8 = LastError;
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
            if ( v8 < 0 )
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                (int)L"WdiGetScenarioIcon",
                792,
                (int)L"Error = %d",
                v8);
              goto LABEL_31;
            }
          }
          IconW = LoadIconW(Library, (LPCWSTR)(unsigned __int16)v16);
          if ( (unsigned __int64)IconW - 1 > 0xFFFFFFFFFFFFFFFDuLL )
          {
            v15 = GetLastError();
            v8 = v15;
            if ( v15 > 0 )
              v8 = (unsigned __int16)v15 | 0x80070000;
            if ( v8 < 0 )
            {
              WdipTraceError(
                (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
                (int)L"WdiGetScenarioIcon",
                797,
                (int)L"Error = %d",
                v8);
              goto LABEL_31;
            }
          }
          else
          {
            v8 = 0;
          }
          *a3 = IconW;
          goto LABEL_31;
        }
        v7 = 753;
      }
      else
      {
        v7 = 740;
      }
    }
    else
    {
      v7 = 739;
    }
  }
  else
  {
    v7 = 738;
  }
  v8 = -2147024809;
  WdipTraceError(
    (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\library\\ondemandlibrary.cpp",
    (int)L"WdiGetScenarioIcon",
    v7,
    (int)L"Error = %d",
    87);
LABEL_31:
  WdipFree(v4);
  WdipFree(v3);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000bcd0  push    rbx
0x18000bcd2  push    rbp
0x18000bcd3  push    rsi
0x18000bcd4  push    rdi
0x18000bcd5  push    r14
0x18000bcd7  push    r15
0x18000bcd9  sub     rsp, 38h
0x18000bcdd  xor     ebp, ebp
0x18000bcdf  xor     r15d, r15d
0x18000bce2  xor     esi, esi
0x18000bce4  mov     [rsp+68h+arg_0], ebp
0x18000bce8  mov     r14, r8
0x18000bceb  test    rcx, rcx
0x18000bcee  jnz     short loc_18000BD22
0x18000bcf0  mov     r8d, 2E2h; int
0x18000bcf6  mov     dword ptr [rsp+68h+Args], 57h ; 'W'; Args
0x18000bcfe  mov     ebx, 80070057h
0x18000bd03  lea     r9, aErrorD_0; "Error = %d"
0x18000bd0a  lea     rdx, aWdigetscenario_12; "WdiGetScenarioIcon"
0x18000bd11  lea     rcx, aClientcoreBase_13; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000bd18  call    WdipTraceError
0x18000bd1d  jmp     loc_18000BEBA
0x18000bd22  test    r14, r14
0x18000bd25  jnz     short loc_18000BD2F
0x18000bd27  mov     r8d, 2E3h
0x18000bd2d  jmp     short loc_18000BCF6
0x18000bd2f  mov     rbx, [rcx+0A8h]
0x18000bd36  test    rbx, rbx
0x18000bd39  jnz     short loc_18000BD43
0x18000bd3b  mov     r8d, 2E4h
0x18000bd41  jmp     short loc_18000BCF6
0x18000bd43  cmp     dword ptr [rcx+10h], 1
0x18000bd47  jz      short loc_18000BD5E
0x18000bd49  mov     ebx, 800710DDh
0x18000bd4e  mov     dword ptr [rsp+68h+Args], 10DDh
0x18000bd56  mov     r8d, 2E9h
0x18000bd5c  jmp     short loc_18000BD03
0x18000bd5e  cmp     edx, [rcx+9Ch]
0x18000bd64  jb      short loc_18000BD6E
0x18000bd66  mov     r8d, 2F1h
0x18000bd6c  jmp     short loc_18000BCF6
0x18000bd6e  mov     eax, edx
0x18000bd70  imul    rdi, rax, 68h ; 'h'
0x18000bd74  test    byte ptr [rdi+rbx+44h], 2
0x18000bd79  jz      short loc_18000BD93
0x18000bd7b  mov     ebx, 800710DDh
0x18000bd80  mov     dword ptr [rsp+68h+Args], 10DDh
0x18000bd88  mov     r8d, 2FEh
0x18000bd8e  jmp     loc_18000BD03
0x18000bd93  mov     ecx, 800h
0x18000bd98  call    WdipAlloc
0x18000bd9d  mov     r15, rax
0x18000bda0  test    rax, rax
0x18000bda3  jnz     short loc_18000BDBD
0x18000bda5  mov     ebx, 8007000Eh
0x18000bdaa  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000bdb2  mov     r8d, 303h
0x18000bdb8  jmp     loc_18000BD03
0x18000bdbd  mov     ecx, 800h
0x18000bdc2  call    WdipAlloc
0x18000bdc7  mov     rbp, rax
0x18000bdca  test    rax, rax
0x18000bdcd  jnz     short loc_18000BDE7
0x18000bdcf  mov     ebx, 8007000Eh
0x18000bdd4  mov     dword ptr [rsp+68h+Args], 0Eh
0x18000bddc  mov     r8d, 304h
0x18000bde2  jmp     loc_18000BD03
0x18000bde7  mov     r8, [rdi+rbx+48h]
0x18000bdec  mov     rcx, r15
0x18000bdef  mov     edi, 400h
0x18000bdf4  mov     edx, edi
0x18000bdf6  call    WdipExpandVariables
0x18000bdfb  mov     ebx, eax
0x18000bdfd  test    eax, eax
0x18000bdff  jns     short loc_18000BE13
0x18000be01  movzx   ecx, ax
0x18000be04  mov     r8d, 30Ah
0x18000be0a  mov     dword ptr [rsp+68h+Args], ecx
0x18000be0e  jmp     loc_18000BD03
0x18000be13  lea     rax, [rsp+68h+arg_0]
0x18000be18  mov     r9d, edi
0x18000be1b  mov     r8, rbp
0x18000be1e  mov     qword ptr [rsp+68h+Args], rax
0x18000be23  lea     rdx, aD; "@%[^,],-%d"
0x18000be2a  mov     rcx, r15; Buffer
0x18000be2d  call    cs:__imp_swscanf_s
0x18000be33  cmp     eax, 2
0x18000be36  jz      short loc_18000BE50
0x18000be38  mov     ebx, 80004005h
0x18000be3d  mov     dword ptr [rsp+68h+Args], 4005h
0x18000be45  mov     r8d, 314h
0x18000be4b  jmp     loc_18000BD03
0x18000be50  xor     edx, edx; hFile
0x18000be52  mov     rcx, rbp; lpLibFileName
0x18000be55  lea     r8d, [rdx+20h]; dwFlags
0x18000be59  call    cs:__imp_LoadLibraryExW
0x18000be5f  mov     rsi, rax
0x18000be62  lea     rcx, [rax+1]
0x18000be66  test    rcx, 0FFFFFFFFFFFFFFFEh
0x18000be6d  jnz     short loc_18000BE9A
0x18000be6f  call    cs:__imp_GetLastError
0x18000be75  mov     ebx, eax
0x18000be77  test    eax, eax
0x18000be79  jle     short loc_18000BE84
0x18000be7b  movzx   ebx, ax
0x18000be7e  or      ebx, 80070000h
0x18000be84  test    ebx, ebx
0x18000be86  jns     short loc_18000BE9A
0x18000be88  movzx   eax, bx
0x18000be8b  mov     r8d, 318h
0x18000be91  mov     dword ptr [rsp+68h+Args], eax
0x18000be95  jmp     loc_18000BD03
0x18000be9a  movzx   edx, word ptr [rsp+68h+arg_0]; lpIconName
0x18000be9f  mov     rcx, rsi; hInstance
0x18000bea2  call    cs:__imp_LoadIconW
0x18000bea8  mov     rdi, rax
0x18000beab  lea     rcx, [rax-1]
0x18000beaf  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18000beb3  ja      short loc_18000BEE7
0x18000beb5  xor     ebx, ebx
0x18000beb7  mov     [r14], rdi
0x18000beba  mov     rcx, r15
0x18000bebd  call    WdipFree
0x18000bec2  mov     rcx, rbp
0x18000bec5  call    WdipFree
0x18000beca  test    rsi, rsi
0x18000becd  jz      short loc_18000BED8
0x18000becf  mov     rcx, rsi; hLibModule
0x18000bed2  call    cs:__imp_FreeLibrary
0x18000bed8  mov     eax, ebx
0x18000beda  add     rsp, 38h
0x18000bede  pop     r15
0x18000bee0  pop     r14
0x18000bee2  pop     rdi
0x18000bee3  pop     rsi
0x18000bee4  pop     rbp
0x18000bee5  pop     rbx
0x18000bee6  retn
0x18000bee7  call    cs:__imp_GetLastError
0x18000beed  mov     ebx, eax
0x18000beef  test    eax, eax
0x18000bef1  jle     short loc_18000BEFC
0x18000bef3  movzx   ebx, ax
0x18000bef6  or      ebx, 80070000h
0x18000befc  test    ebx, ebx
0x18000befe  jns     short loc_18000BEB7
0x18000bf00  movzx   eax, bx
0x18000bf03  mov     r8d, 31Dh
0x18000bf09  mov     dword ptr [rsp+68h+Args], eax
0x18000bf0d  jmp     loc_18000BD03
```
