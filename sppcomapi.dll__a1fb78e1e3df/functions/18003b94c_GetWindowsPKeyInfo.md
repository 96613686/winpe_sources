# GetWindowsPKeyInfo

- ea: `0x18003b94c`
- end: `0x18003bd77`
- name: `GetWindowsPKeyInfo`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x180019210`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800044d8`
- `0x18001ecb0`
- `0x18003b0e8`
- `0x18003b94c`
- `0x18003c52a`
- `0x18003c560`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bac7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bcb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bd0d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bac7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bcb3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bce0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003bd0d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003badc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bcf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bd23`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003badc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bcc8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bcf5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003bd23`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bd3e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003bd3e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ba28`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003ba28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ba74`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003ba74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ba3f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003bb2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003bb2f`

## string_xrefs

- `0x18003b9f8`: `pidgenx.dll`

## pseudocode

```c
__int64 __fastcall GetWindowsPKeyInfo(_WORD *a1, __int64 a2, __int64 a3, _OWORD *a4)
{
  HMODULE v5; // rbx
  __int64 v6; // r12
  LPCWSTR v7; // r15
  unsigned int v9; // edi
  int v10; // eax
  signed int v11; // esi
  HMODULE Library; // rax
  signed int LastError; // eax
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  HANDLE ProcessHeap; // rax
  int v18; // eax
  DWORD FileAttributesW; // eax
  BOOL v20; // edi
  __int64 v21; // rcx
  _OWORD *v22; // rax
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  __int128 v28; // xmm0
  __int128 v29; // xmm1
  __int128 v30; // xmm1
  __int128 v31; // xmm0
  __int128 v32; // xmm1
  __int128 v33; // xmm0
  __int128 v34; // xmm1
  __int128 v35; // xmm0
  __int64 v36; // rax
  HANDLE v37; // rax
  HANDLE v38; // rax
  unsigned int lpLibFileName; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v43; // [rsp+58h] [rbp-A8h]
  FARPROC ProcAddress; // [rsp+60h] [rbp-A0h]
  _OWORD v45[3]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD v46[44]; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v47[320]; // [rsp+150h] [rbp+50h] BYREF

  v43 = a1;
  v42 = 0;
  lpFileName = 0;
  v5 = 0;
  v6 = 0;
  v7 = 0;
  memset(v45, 0, sizeof(v45));
  memset_0(v46, 0, 0xA4u);
  memset_0(v47, 0, 0x4F8u);
  if ( !a1 || !*a1 || (v9 = 0, !a4) )
  {
    v14 = 2147942487LL;
    v11 = -2147024809;
    goto LABEL_38;
  }
  v10 = CMiscHelpersT<CEmptyType>::AppendToSystemPath(L"pidgenx.dll");
  v11 = v10;
  if ( v10 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v10);
    goto LABEL_39;
  }
  Library = LoadLibraryExW(0, 0, 0);
  v5 = Library;
  if ( !Library )
  {
    v5 = 0;
    goto LABEL_8;
  }
  ProcAddress = GetProcAddress(Library, "PidGenX");
  if ( !ProcAddress )
  {
LABEL_8:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v11 = -2147467259;
    }
LABEL_12:
    v14 = (unsigned int)v11;
LABEL_38:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v14);
    goto LABEL_39;
  }
  v46[0] = 164;
  v47[0] = 1272;
  v16 = CMiscHelpersT<CEmptyType>::ExpandFileName(v15, &v42);
  v11 = v16;
  if ( v16 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
    v6 = v42;
    goto LABEL_39;
  }
  v6 = v42;
  lpLibFileName = 0;
  do
  {
    if ( v7 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v7 - 2));
      v9 = lpLibFileName;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      lpFileName = 0;
    }
    v18 = STRAPI_Format((unsigned __int16 **)&lpFileName, L"%s\\%s", v6, off_18003EB60[v9]);
    v11 = v18;
    if ( v18 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v18);
      v7 = lpFileName;
      goto LABEL_39;
    }
    v7 = lpFileName;
    FileAttributesW = GetFileAttributesW(lpFileName);
    v20 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( v20 )
    {
      v11 = ((__int64 (__fastcall *)(_WORD *, LPCWSTR, const wchar_t *, _QWORD, _OWORD *, _DWORD *, _DWORD *))ProcAddress)(
              v43,
              v7,
              L"03612",
              0,
              v45,
              v46,
              v47);
      if ( v11 >= 0 )
        break;
    }
    else
    {
      v11 = -1073418160;
    }
    v9 = lpLibFileName + 1;
    lpLibFileName = v9;
  }
  while ( v9 < 2 );
  if ( v11 == -1979645951 )
  {
    v11 = -1073422314;
    goto LABEL_12;
  }
  if ( v11 == -1979645695 )
  {
    v11 = -1073418160;
    v14 = 3221549136LL;
    goto LABEL_38;
  }
  if ( v11 < 0 )
    goto LABEL_12;
  v21 = 9;
  v22 = v47;
  do
  {
    v23 = v22[1];
    *a4 = *v22;
    v24 = v22[2];
    a4[1] = v23;
    v25 = v22[3];
    a4[2] = v24;
    v26 = v22[4];
    a4[3] = v25;
    v27 = v22[5];
    a4[4] = v26;
    v28 = v22[6];
    a4[5] = v27;
    v29 = v22[7];
    v22 += 8;
    a4[6] = v28;
    a4[7] = v29;
    a4 += 8;
    --v21;
  }
  while ( v21 );
  v30 = v22[1];
  *a4 = *v22;
  v31 = v22[2];
  a4[1] = v30;
  v32 = v22[3];
  a4[2] = v31;
  v33 = v22[4];
  a4[3] = v32;
  v34 = v22[5];
  a4[4] = v33;
  v35 = v22[6];
  v36 = *((_QWORD *)v22 + 14);
  a4[5] = v34;
  a4[6] = v35;
  *((_QWORD *)a4 + 14) = v36;
LABEL_39:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v11);
  if ( v7 )
  {
    v37 = GetProcessHeap();
    HeapFree(v37, 0, (LPVOID)(v7 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v38 = GetProcessHeap();
    HeapFree(v38, 0, (LPVOID)(v6 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
    FreeLibrary(v5);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18003b94c  mov     [rsp-8+arg_8], rbx
0x18003b951  push    rbp
0x18003b952  push    rsi
0x18003b953  push    rdi
0x18003b954  push    r12
0x18003b956  push    r13
0x18003b958  push    r14
0x18003b95a  push    r15
0x18003b95c  lea     rbp, [rsp-560h]
0x18003b964  sub     rsp, 660h
0x18003b96b  mov     rax, cs:__security_cookie
0x18003b972  xor     rax, rsp
0x18003b975  mov     [rbp+590h+var_40], rax
0x18003b97c  xor     esi, esi
0x18003b97e  mov     [rsp+690h+var_638], rcx
0x18003b983  xorps   xmm0, xmm0
0x18003b986  mov     [rsp+690h+var_640], rsi
0x18003b98b  mov     rdi, rcx
0x18003b98e  mov     [rsp+690h+lpFileName], rsi
0x18003b993  lea     rcx, [rbp+590h+var_5F0]; void *
0x18003b997  mov     [rsp+690h+lpLibFileName], rsi
0x18003b99c  xor     edx, edx; Val
0x18003b99e  mov     r8d, 0A4h; Size
0x18003b9a4  mov     ebx, esi
0x18003b9a6  mov     r12d, esi
0x18003b9a9  mov     r15d, esi
0x18003b9ac  mov     r13d, esi
0x18003b9af  movups  [rsp+690h+var_628], xmm0
0x18003b9b4  mov     r14, r9
0x18003b9b7  movups  [rsp+690h+var_618], xmm0
0x18003b9bc  movups  [rbp+590h+var_608], xmm0
0x18003b9c0  call    memset_0
0x18003b9c5  xor     edx, edx; Val
0x18003b9c7  lea     rcx, [rbp+590h+var_540]; void *
0x18003b9cb  mov     r8d, 4F8h; Size
0x18003b9d1  call    memset_0
0x18003b9d6  test    rdi, rdi
0x18003b9d9  jz      loc_18003BC9B
0x18003b9df  cmp     [rdi], si
0x18003b9e2  jz      loc_18003BC9B
0x18003b9e8  xor     edi, edi
0x18003b9ea  test    r14, r14
0x18003b9ed  jz      loc_18003BC9B
0x18003b9f3  lea     rdx, [rsp+690h+lpLibFileName]
0x18003b9f8  lea     rcx, aPidgenxDll; "pidgenx.dll"
0x18003b9ff  call    ?AppendToSystemPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::AppendToSystemPath(ushort const *,ushort * *)
0x18003ba04  mov     esi, eax
0x18003ba06  test    eax, eax
0x18003ba08  jns     short loc_18003BA1B
0x18003ba0a  mov     ecx, eax
0x18003ba0c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003ba11  mov     r13, [rsp+690h+lpLibFileName]
0x18003ba16  jmp     loc_18003BCA7
0x18003ba1b  mov     r13, [rsp+690h+lpLibFileName]
0x18003ba20  xor     r8d, r8d; dwFlags
0x18003ba23  mov     rcx, r13; lpLibFileName
0x18003ba26  xor     edx, edx; hFile
0x18003ba28  call    cs:__imp_LoadLibraryExW
0x18003ba2f  nop     dword ptr [rax+rax+00h]
0x18003ba34  mov     rbx, rax
0x18003ba37  test    rax, rax
0x18003ba3a  jnz     short loc_18003BA6A
0x18003ba3c  mov     rbx, rdi
0x18003ba3f  call    cs:__imp_GetLastError
0x18003ba46  nop     dword ptr [rax+rax+00h]
0x18003ba4b  mov     esi, eax
0x18003ba4d  test    eax, eax
0x18003ba4f  jnz     short loc_18003BA58
0x18003ba51  mov     esi, 80004005h
0x18003ba56  jmp     short loc_18003BA63
0x18003ba58  jle     short loc_18003BA63
0x18003ba5a  movzx   esi, ax
0x18003ba5d  or      esi, 80070000h
0x18003ba63  mov     ecx, esi
0x18003ba65  jmp     loc_18003BCA2
0x18003ba6a  lea     rdx, aPidgenx; "PidGenX"
0x18003ba71  mov     rcx, rax; hModule
0x18003ba74  call    cs:__imp_GetProcAddress
0x18003ba7b  nop     dword ptr [rax+rax+00h]
0x18003ba80  mov     [rsp+690h+var_630], rax
0x18003ba85  test    rax, rax
0x18003ba88  jz      short loc_18003BA3F
0x18003ba8a  lea     rdx, [rsp+690h+var_640]
0x18003ba8f  mov     [rbp+590h+var_5F0], 0A4h
0x18003ba96  mov     [rbp+590h+var_540], 4F8h
0x18003ba9d  call    ?ExpandFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAPEAG@Z; CMiscHelpersT<CEmptyType>::ExpandFileName(ushort const *,ushort * *)
0x18003baa2  mov     esi, eax
0x18003baa4  test    eax, eax
0x18003baa6  jns     short loc_18003BAB9
0x18003baa8  mov     ecx, eax
0x18003baaa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003baaf  mov     r12, [rsp+690h+var_640]
0x18003bab4  jmp     loc_18003BCA7
0x18003bab9  mov     r12, [rsp+690h+var_640]
0x18003babe  mov     dword ptr [rsp+690h+lpLibFileName], edi
0x18003bac2  test    r15, r15
0x18003bac5  jz      short loc_18003BAFC
0x18003bac7  call    cs:__imp_GetProcessHeap
0x18003bace  nop     dword ptr [rax+rax+00h]
0x18003bad3  lea     r8, [r15-4]; lpMem
0x18003bad7  xor     edx, edx; dwFlags
0x18003bad9  mov     rcx, rax; hHeap
0x18003badc  call    cs:__imp_HeapFree
0x18003bae3  nop     dword ptr [rax+rax+00h]
0x18003bae8  mov     edi, dword ptr [rsp+690h+lpLibFileName]
0x18003baec  xor     ecx, ecx
0x18003baee  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003baf3  mov     [rsp+690h+lpFileName], 0
0x18003bafc  mov     eax, edi
0x18003bafe  lea     r9, off_18003EB60; "pkeyconfig.xrm-ms"
0x18003bb05  mov     r8, r12
0x18003bb08  lea     rdx, aSS; "%s\\%s"
0x18003bb0f  lea     rcx, [rsp+690h+lpFileName]; unsigned __int16 **
0x18003bb14  mov     r9, [r9+rax*8]
0x18003bb18  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x18003bb1d  mov     esi, eax
0x18003bb1f  test    eax, eax
0x18003bb21  js      loc_18003BC8D
0x18003bb27  mov     r15, [rsp+690h+lpFileName]
0x18003bb2c  mov     rcx, r15; lpFileName
0x18003bb2f  call    cs:__imp_GetFileAttributesW
0x18003bb36  nop     dword ptr [rax+rax+00h]
0x18003bb3b  mov     edi, eax
0x18003bb3d  cmp     eax, 0FFFFFFFFh
0x18003bb40  jz      short loc_18003BB4C
0x18003bb42  shr     edi, 4
0x18003bb45  not     edi
0x18003bb47  and     edi, 1
0x18003bb4a  jmp     short loc_18003BB4E
0x18003bb4c  xor     edi, edi
0x18003bb4e  xor     ecx, ecx
0x18003bb50  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bb55  xor     ecx, ecx
0x18003bb57  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bb5c  test    edi, edi
0x18003bb5e  jz      short loc_18003BBA0
0x18003bb60  mov     rcx, [rsp+690h+var_638]
0x18003bb65  lea     rax, [rbp+590h+var_540]
0x18003bb69  mov     [rsp+690h+var_660], rax
0x18003bb6e  lea     r8, a03612; "03612"
0x18003bb75  lea     rax, [rbp+590h+var_5F0]
0x18003bb79  xor     r9d, r9d
0x18003bb7c  mov     [rsp+690h+var_668], rax
0x18003bb81  mov     rdx, r15
0x18003bb84  lea     rax, [rsp+690h+var_628]
0x18003bb89  mov     [rsp+690h+var_670], rax
0x18003bb8e  mov     rax, [rsp+690h+var_630]
0x18003bb93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb98  mov     esi, eax
0x18003bb9a  test    eax, eax
0x18003bb9c  jns     short loc_18003BBB8
0x18003bb9e  jmp     short loc_18003BBA5
0x18003bba0  mov     esi, 0C004F050h
0x18003bba5  mov     edi, dword ptr [rsp+690h+lpLibFileName]
0x18003bba9  inc     edi
0x18003bbab  mov     dword ptr [rsp+690h+lpLibFileName], edi
0x18003bbaf  cmp     edi, 2
0x18003bbb2  jb      loc_18003BAC2
0x18003bbb8  cmp     esi, 8A010001h
0x18003bbbe  jnz     short loc_18003BBCA
0x18003bbc0  mov     esi, 0C004E016h
0x18003bbc5  jmp     loc_18003BA63
0x18003bbca  cmp     esi, 8A010101h
0x18003bbd0  jnz     short loc_18003BBE0
0x18003bbd2  mov     eax, 0C004F050h
0x18003bbd7  mov     esi, eax
0x18003bbd9  mov     ecx, eax
0x18003bbdb  jmp     loc_18003BCA2
0x18003bbe0  test    esi, esi
0x18003bbe2  js      loc_18003BA63
0x18003bbe8  mov     ecx, 9
0x18003bbed  lea     rax, [rbp+590h+var_540]
0x18003bbf1  lea     edx, [rcx+77h]
0x18003bbf4  movups  xmm0, xmmword ptr [rax]
0x18003bbf7  movups  xmm1, xmmword ptr [rax+10h]
0x18003bbfb  movups  xmmword ptr [r14], xmm0
0x18003bbff  movups  xmm0, xmmword ptr [rax+20h]
0x18003bc03  movups  xmmword ptr [r14+10h], xmm1
0x18003bc08  movups  xmm1, xmmword ptr [rax+30h]
0x18003bc0c  movups  xmmword ptr [r14+20h], xmm0
0x18003bc11  movups  xmm0, xmmword ptr [rax+40h]
0x18003bc15  movups  xmmword ptr [r14+30h], xmm1
0x18003bc1a  movups  xmm1, xmmword ptr [rax+50h]
0x18003bc1e  movups  xmmword ptr [r14+40h], xmm0
0x18003bc23  movups  xmm0, xmmword ptr [rax+60h]
0x18003bc27  movups  xmmword ptr [r14+50h], xmm1
0x18003bc2c  movups  xmm1, xmmword ptr [rax+70h]
0x18003bc30  add     rax, rdx
0x18003bc33  movups  xmmword ptr [r14+60h], xmm0
0x18003bc38  movups  xmmword ptr [r14+70h], xmm1
0x18003bc3d  add     r14, rdx
0x18003bc40  sub     rcx, 1
0x18003bc44  jnz     short loc_18003BBF4
0x18003bc46  movups  xmm0, xmmword ptr [rax]
0x18003bc49  movups  xmm1, xmmword ptr [rax+10h]
0x18003bc4d  movups  xmmword ptr [r14], xmm0
0x18003bc51  movups  xmm0, xmmword ptr [rax+20h]
0x18003bc55  movups  xmmword ptr [r14+10h], xmm1
0x18003bc5a  movups  xmm1, xmmword ptr [rax+30h]
0x18003bc5e  movups  xmmword ptr [r14+20h], xmm0
0x18003bc63  movups  xmm0, xmmword ptr [rax+40h]
0x18003bc67  movups  xmmword ptr [r14+30h], xmm1
0x18003bc6c  movups  xmm1, xmmword ptr [rax+50h]
0x18003bc70  movups  xmmword ptr [r14+40h], xmm0
0x18003bc75  movups  xmm0, xmmword ptr [rax+60h]
0x18003bc79  mov     rax, [rax+70h]
0x18003bc7d  movups  xmmword ptr [r14+50h], xmm1
0x18003bc82  movups  xmmword ptr [r14+60h], xmm0
0x18003bc87  mov     [r14+70h], rax
0x18003bc8b  jmp     short loc_18003BCA7
0x18003bc8d  mov     ecx, eax
0x18003bc8f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003bc94  mov     r15, [rsp+690h+lpFileName]
0x18003bc99  jmp     short loc_18003BCA7
0x18003bc9b  mov     ecx, 80070057h
0x18003bca0  mov     esi, ecx
0x18003bca2  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003bca7  mov     ecx, esi
0x18003bca9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bcae  test    r13, r13
0x18003bcb1  jz      short loc_18003BCDB
0x18003bcb3  call    cs:__imp_GetProcessHeap
0x18003bcba  nop     dword ptr [rax+rax+00h]
0x18003bcbf  lea     r8, [r13-4]; lpMem
0x18003bcc3  xor     edx, edx; dwFlags
0x18003bcc5  mov     rcx, rax; hHeap
0x18003bcc8  call    cs:__imp_HeapFree
0x18003bccf  nop     dword ptr [rax+rax+00h]
0x18003bcd4  xor     ecx, ecx
0x18003bcd6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bcdb  test    r15, r15
0x18003bcde  jz      short loc_18003BD08
0x18003bce0  call    cs:__imp_GetProcessHeap
0x18003bce7  nop     dword ptr [rax+rax+00h]
0x18003bcec  lea     r8, [r15-4]; lpMem
0x18003bcf0  xor     edx, edx; dwFlags
0x18003bcf2  mov     rcx, rax; hHeap
0x18003bcf5  call    cs:__imp_HeapFree
0x18003bcfc  nop     dword ptr [rax+rax+00h]
0x18003bd01  xor     ecx, ecx
0x18003bd03  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bd08  test    r12, r12
0x18003bd0b  jz      short loc_18003BD36
0x18003bd0d  call    cs:__imp_GetProcessHeap
0x18003bd14  nop     dword ptr [rax+rax+00h]
0x18003bd19  lea     r8, [r12-4]; lpMem
0x18003bd1e  xor     edx, edx; dwFlags
0x18003bd20  mov     rcx, rax; hHeap
0x18003bd23  call    cs:__imp_HeapFree
0x18003bd2a  nop     dword ptr [rax+rax+00h]
0x18003bd2f  xor     ecx, ecx
0x18003bd31  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003bd36  test    rbx, rbx
0x18003bd39  jz      short loc_18003BD4A
0x18003bd3b  mov     rcx, rbx; hLibModule
0x18003bd3e  call    cs:__imp_FreeLibrary
0x18003bd45  nop     dword ptr [rax+rax+00h]
0x18003bd4a  mov     eax, esi
0x18003bd4c  mov     rcx, [rbp+590h+var_40]
0x18003bd53  xor     rcx, rsp; StackCookie
0x18003bd56  call    __security_check_cookie
0x18003bd5b  mov     rbx, [rsp+690h+arg_8]
0x18003bd63  add     rsp, 660h
0x18003bd6a  pop     r15
0x18003bd6c  pop     r14
0x18003bd6e  pop     r13
0x18003bd70  pop     r12
0x18003bd72  pop     rdi
0x18003bd73  pop     rsi
0x18003bd74  pop     rbp
0x18003bd75  retn
```
