# BfspIsWindowsBinary

- ea: `0x180037ea8`
- end: `0x180038145`
- name: `BfspIsWindowsBinary`
- size: `669`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180032518`
- `0x18003545c`

## callees

- `0x180037ea8`
- `0x180081010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800380e8`
- `msvcrt!_wcsicmp` at `0x1800380e8`
- `msvcrt!swprintf_s` at `0x1800380b0`
- `msvcrt!swprintf_s` at `0x1800380b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800380f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038112`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180037ff5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038071`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800380f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180038112`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038003`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038083`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038003`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180038083`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038120`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038107`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180038120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037f24`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037f12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180037f12`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037fa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037f77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180037fa4`

## string_xrefs

- `0x180037f09`: `version.dll`

## pseudocode

```c
__int64 __fastcall BfspIsWindowsBinary(__int64 a1, const wchar_t *a2, int a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rcx
  __int64 (__fastcall *v7)(__int64, int *); // r8
  FARPROC v8; // rax
  unsigned int v9; // r14d
  HANDLE ProcessHeap; // rax
  LPVOID v11; // rax
  void *v12; // rsi
  wchar_t *v13; // rdi
  unsigned int v14; // ebx
  HANDLE v15; // rax
  HANDLE v16; // rax
  HANDLE v17; // rax
  int v19; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v20; // [rsp+38h] [rbp-18h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-10h] BYREF
  int v22; // [rsp+90h] [rbp+40h] BYREF
  int v23; // [rsp+98h] [rbp+48h] BYREF

  v23 = 0;
  v22 = 0;
  v19 = 0;
  String1 = 0;
  v20 = 0;
  if ( a3 != 2 )
    return 0;
  Library = g_hInstVersionDLL;
  if ( !g_hInstVersionDLL )
  {
    Library = LoadLibraryExW(L"version.dll", 0, 8u);
    g_hInstVersionDLL = Library;
    if ( !Library )
    {
      if ( !GetLastError() )
      {
        Library = g_hInstVersionDLL;
        goto LABEL_6;
      }
      return 0;
    }
  }
LABEL_6:
  if ( !qword_1800AE778 )
  {
    qword_1800AE778 = (__int64)GetProcAddress(Library, "VerQueryValueW");
    Library = g_hInstVersionDLL;
  }
  ProcAddress = (FARPROC)qword_1800AE760;
  if ( !qword_1800AE760 )
  {
    ProcAddress = GetProcAddress(Library, "GetFileVersionInfoW");
    qword_1800AE760 = (__int64)ProcAddress;
    Library = g_hInstVersionDLL;
  }
  v7 = (__int64 (__fastcall *)(__int64, int *))qword_1800AE768;
  if ( !qword_1800AE768 )
  {
    v8 = GetProcAddress(Library, "GetFileVersionInfoSizeW");
    ProcAddress = (FARPROC)qword_1800AE760;
    v7 = (__int64 (__fastcall *)(__int64, int *))v8;
    qword_1800AE768 = (__int64)v8;
  }
  if ( !qword_1800AE778 )
    return 0;
  if ( !ProcAddress )
    return 0;
  if ( !v7 )
    return 0;
  v9 = v7(a1, &v19);
  if ( !v9 )
    return 0;
  ProcessHeap = GetProcessHeap();
  v11 = HeapAlloc(ProcessHeap, 8u, v9);
  v12 = v11;
  if ( !v11 )
    return 0;
  v13 = 0;
  v14 = ((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, LPVOID))qword_1800AE760)(a1, 0, v9, v11);
  if ( v14 )
    v14 = (unsigned int)((__int64 (__fastcall *)(void *, const wchar_t *, unsigned __int16 **, int *))qword_1800AE778)(
                          v12,
                          L"\\VarFileInfo\\Translation",
                          &v20,
                          &v22)
       && v20
       && v22
       && (v15 = GetProcessHeap(), (v13 = (wchar_t *)HeapAlloc(v15, 8u, 0x208u)) != 0)
       && (swprintf_s(v13, 0x104u, L"\\StringFileInfo\\%04x%04x\\InternalName", *v20, v20[1]),
           (unsigned int)((__int64 (__fastcall *)(void *, wchar_t *, wchar_t **, int *))qword_1800AE778)(
                           v12,
                           v13,
                           &String1,
                           &v23))
       && String1
       && v23
       && _wcsicmp(String1, a2) == 0;
  v16 = GetProcessHeap();
  HeapFree(v16, 0, v12);
  if ( v13 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v13);
  }
  return v14;
}

```

## disassembly

```asm
0x180037ea8  mov     [rsp-28h+arg_0], rbx
0x180037ead  mov     [rsp-28h+arg_8], rsi
0x180037eb2  push    rbp
0x180037eb3  push    rdi
0x180037eb4  push    r12
0x180037eb6  push    r14
0x180037eb8  push    r15
0x180037eba  mov     rbp, rsp
0x180037ebd  sub     rsp, 50h
0x180037ec1  mov     [rbp+arg_18], 0
0x180037ec8  mov     r12, rdx
0x180037ecb  mov     [rbp+arg_10], 0
0x180037ed2  mov     r15, rcx
0x180037ed5  mov     [rbp+var_20], 0
0x180037edc  mov     [rbp+String1], 0
0x180037ee4  mov     [rbp+var_18], 0
0x180037eec  cmp     r8d, 2
0x180037ef0  jnz     loc_180038128
0x180037ef6  mov     rax, cs:g_hInstVersionDLL
0x180037efd  lea     edi, [r8+6]
0x180037f01  test    rax, rax
0x180037f04  jnz     short loc_180037F39
0x180037f06  mov     r8d, edi; dwFlags
0x180037f09  lea     rcx, aVersionDll; "version.dll"
0x180037f10  xor     edx, edx; hFile
0x180037f12  call    cs:__imp_LoadLibraryExW
0x180037f18  mov     cs:g_hInstVersionDLL, rax
0x180037f1f  test    rax, rax
0x180037f22  jnz     short loc_180037F39
0x180037f24  call    cs:__imp_GetLastError
0x180037f2a  test    eax, eax
0x180037f2c  jnz     loc_180038128
0x180037f32  mov     rax, cs:g_hInstVersionDLL
0x180037f39  cmp     cs:qword_1800AE778, 0
0x180037f41  jnz     short loc_180037F61
0x180037f43  lea     rdx, aVerqueryvaluew; "VerQueryValueW"
0x180037f4a  mov     rcx, rax; hModule
0x180037f4d  call    cs:__imp_GetProcAddress
0x180037f53  mov     cs:qword_1800AE778, rax
0x180037f5a  mov     rax, cs:g_hInstVersionDLL
0x180037f61  mov     rcx, cs:qword_1800AE760
0x180037f68  test    rcx, rcx
0x180037f6b  jnz     short loc_180037F8E
0x180037f6d  lea     rdx, aGetfileversion_0; "GetFileVersionInfoW"
0x180037f74  mov     rcx, rax; hModule
0x180037f77  call    cs:__imp_GetProcAddress
0x180037f7d  mov     rcx, rax
0x180037f80  mov     cs:qword_1800AE760, rax
0x180037f87  mov     rax, cs:g_hInstVersionDLL
0x180037f8e  mov     r8, cs:qword_1800AE768
0x180037f95  test    r8, r8
0x180037f98  jnz     short loc_180037FBB
0x180037f9a  lea     rdx, aGetfileversion; "GetFileVersionInfoSizeW"
0x180037fa1  mov     rcx, rax; hModule
0x180037fa4  call    cs:__imp_GetProcAddress
0x180037faa  mov     rcx, cs:qword_1800AE760
0x180037fb1  mov     r8, rax
0x180037fb4  mov     cs:qword_1800AE768, rax
0x180037fbb  cmp     cs:qword_1800AE778, 0
0x180037fc3  jz      loc_180038128
0x180037fc9  test    rcx, rcx
0x180037fcc  jz      loc_180038128
0x180037fd2  test    r8, r8
0x180037fd5  jz      loc_180038128
0x180037fdb  lea     rdx, [rbp+var_20]
0x180037fdf  mov     rcx, r15
0x180037fe2  mov     rax, r8
0x180037fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037fea  mov     r14d, eax
0x180037fed  test    eax, eax
0x180037fef  jz      loc_180038128
0x180037ff5  call    cs:__imp_GetProcessHeap
0x180037ffb  mov     r8d, r14d; dwBytes
0x180037ffe  mov     edx, edi; dwFlags
0x180038000  mov     rcx, rax; hHeap
0x180038003  call    cs:__imp_HeapAlloc
0x180038009  mov     rsi, rax
0x18003800c  test    rax, rax
0x18003800f  jz      loc_180038128
0x180038015  mov     r9, rax
0x180038018  mov     r8d, r14d
0x18003801b  mov     rax, cs:qword_1800AE760
0x180038022  xor     edx, edx
0x180038024  mov     rcx, r15
0x180038027  xor     edi, edi
0x180038029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003802e  mov     ebx, eax
0x180038030  test    eax, eax
0x180038032  jz      loc_1800380F9
0x180038038  mov     rax, cs:qword_1800AE778
0x18003803f  lea     r9, [rbp+arg_10]
0x180038043  lea     r8, [rbp+var_18]
0x180038047  mov     rcx, rsi
0x18003804a  lea     rdx, aVarfileinfoTra; "\\VarFileInfo\\Translation"
0x180038051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038056  test    eax, eax
0x180038058  jz      loc_1800380F7
0x18003805e  cmp     [rbp+var_18], rdi
0x180038062  jz      loc_1800380F7
0x180038068  cmp     [rbp+arg_10], edi
0x18003806b  jz      loc_1800380F7
0x180038071  call    cs:__imp_GetProcessHeap
0x180038077  lea     edx, [rdi+8]; dwFlags
0x18003807a  mov     r8d, 208h; dwBytes
0x180038080  mov     rcx, rax; hHeap
0x180038083  call    cs:__imp_HeapAlloc
0x180038089  mov     rdi, rax
0x18003808c  test    rax, rax
0x18003808f  jz      short loc_1800380F7
0x180038091  mov     rax, [rbp+var_18]
0x180038095  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04x%04x\\InternalNam"...
0x18003809c  mov     edx, 104h; BufferCount
0x1800380a1  movzx   ecx, word ptr [rax+2]
0x1800380a5  movzx   r9d, word ptr [rax]
0x1800380a9  mov     [rsp+50h+var_30], ecx
0x1800380ad  mov     rcx, rdi; Buffer
0x1800380b0  call    cs:__imp_swprintf_s
0x1800380b6  mov     rax, cs:qword_1800AE778
0x1800380bd  lea     r9, [rbp+arg_18]
0x1800380c1  lea     r8, [rbp+String1]
0x1800380c5  mov     rdx, rdi
0x1800380c8  mov     rcx, rsi
0x1800380cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800380d0  test    eax, eax
0x1800380d2  jz      short loc_1800380F7
0x1800380d4  mov     rcx, [rbp+String1]; String1
0x1800380d8  test    rcx, rcx
0x1800380db  jz      short loc_1800380F7
0x1800380dd  cmp     [rbp+arg_18], 0
0x1800380e1  jz      short loc_1800380F7
0x1800380e3  mov     rdx, r12; String2
0x1800380e6  xor     ebx, ebx
0x1800380e8  call    cs:__imp__wcsicmp
0x1800380ee  test    eax, eax
0x1800380f0  jnz     short loc_1800380F9
0x1800380f2  lea     ebx, [rax+1]
0x1800380f5  jmp     short loc_1800380F9
0x1800380f7  xor     ebx, ebx
0x1800380f9  call    cs:__imp_GetProcessHeap
0x1800380ff  mov     r8, rsi; lpMem
0x180038102  xor     edx, edx; dwFlags
0x180038104  mov     rcx, rax; hHeap
0x180038107  call    cs:__imp_HeapFree
0x18003810d  test    rdi, rdi
0x180038110  jz      short loc_18003812A
0x180038112  call    cs:__imp_GetProcessHeap
0x180038118  mov     r8, rdi; lpMem
0x18003811b  xor     edx, edx; dwFlags
0x18003811d  mov     rcx, rax; hHeap
0x180038120  call    cs:__imp_HeapFree
0x180038126  jmp     short loc_18003812A
0x180038128  xor     ebx, ebx
0x18003812a  lea     r11, [rsp+50h+var_s0]
0x18003812f  mov     eax, ebx
0x180038131  mov     rbx, [r11+30h]
0x180038135  mov     rsi, [r11+38h]
0x180038139  mov     rsp, r11
0x18003813c  pop     r15
0x18003813e  pop     r14
0x180038140  pop     r12
0x180038142  pop     rdi
0x180038143  pop     rbp
0x180038144  retn
```
