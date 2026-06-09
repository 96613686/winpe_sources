# CBCryptLoaderT<CEmptyType>::InitFunctionPointers(HINSTANCE__ *)

- ea: `0x1800386ec`
- end: `0x180038ae4`
- name: `?InitFunctionPointers@?$CBCryptLoaderT@VCEmptyType@@@@CAJPEAUHINSTANCE__@@@Z`
- size: `1016`
- prototype: `__int64 __fastcall(HMODULE hModule)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180037870`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800386ec`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800386ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038762`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800387bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038814`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003886d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800388c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003891f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800389d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800386ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038762`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800387bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038814`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003886d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800388c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003891f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038978`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800389d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a2a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180038a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003887e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003871a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800387cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038825`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003887e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800388d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038930`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038989`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800389e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038a90`

## string_xrefs

- `0x1800386f5`: `BCryptOpenAlgorithmProvider`
- `0x1800387b1`: `BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall CBCryptLoaderT<CEmptyType>::InitFunctionPointers(HMODULE hModule)
{
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  unsigned int v4; // ebx
  FARPROC v5; // rax
  signed int v6; // eax
  FARPROC v7; // rax
  signed int v8; // eax
  FARPROC v9; // rax
  signed int v10; // eax
  FARPROC v11; // rax
  signed int v12; // eax
  FARPROC v13; // rax
  signed int v14; // eax
  FARPROC v15; // rax
  signed int v16; // eax
  FARPROC v17; // rax
  signed int v18; // eax
  FARPROC v19; // rax
  signed int v20; // eax
  FARPROC v21; // rax
  signed int v22; // eax
  FARPROC v23; // rax
  signed int v24; // eax

  ProcAddress = GetProcAddress(hModule, "BCryptOpenAlgorithmProvider");
  if ( ProcAddress )
  {
    v4 = 0;
    qword_180047080 = (__int64)ProcAddress;
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v5 = GetProcAddress(hModule, "BCryptGetProperty");
  if ( v5 )
  {
    v4 = 0;
    qword_180047088 = (__int64)v5;
  }
  else
  {
    v6 = GetLastError();
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v7 = GetProcAddress(hModule, "BCryptCreateHash");
  if ( v7 )
  {
    v4 = 0;
    qword_180047090 = (__int64)v7;
  }
  else
  {
    v8 = GetLastError();
    v4 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v4 = (unsigned __int16)v8 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v9 = GetProcAddress(hModule, "BCryptGenRandom");
  if ( v9 )
  {
    v4 = 0;
    qword_180047098 = (__int64)v9;
  }
  else
  {
    v10 = GetLastError();
    v4 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v4 = (unsigned __int16)v10 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v11 = GetProcAddress(hModule, "BCryptHashData");
  if ( v11 )
  {
    v4 = 0;
    qword_1800470A0 = (__int64)v11;
  }
  else
  {
    v12 = GetLastError();
    v4 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v4 = (unsigned __int16)v12 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v13 = GetProcAddress(hModule, "BCryptFinishHash");
  if ( v13 )
  {
    v4 = 0;
    qword_1800470A8 = (__int64)v13;
  }
  else
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 )
    {
      if ( v14 > 0 )
        v4 = (unsigned __int16)v14 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v15 = GetProcAddress(hModule, "BCryptCloseAlgorithmProvider");
  if ( v15 )
  {
    v4 = 0;
    qword_1800470B0 = (__int64)v15;
  }
  else
  {
    v16 = GetLastError();
    v4 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v4 = (unsigned __int16)v16 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v17 = GetProcAddress(hModule, "BCryptDestroyKey");
  if ( v17 )
  {
    v4 = 0;
    qword_1800470B8 = (__int64)v17;
  }
  else
  {
    v18 = GetLastError();
    v4 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v4 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v19 = GetProcAddress(hModule, "BCryptDestroyHash");
  if ( v19 )
  {
    v4 = 0;
    qword_1800470C0 = (__int64)v19;
  }
  else
  {
    v20 = GetLastError();
    v4 = v20;
    if ( v20 )
    {
      if ( v20 > 0 )
        v4 = (unsigned __int16)v20 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v21 = GetProcAddress(hModule, "BCryptFreeBuffer");
  if ( v21 )
  {
    v4 = 0;
    qword_1800470C8 = (__int64)v21;
  }
  else
  {
    v22 = GetLastError();
    v4 = v22;
    if ( v22 )
    {
      if ( v22 > 0 )
        v4 = (unsigned __int16)v22 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
    goto LABEL_89;
  v23 = GetProcAddress(hModule, "BCryptVerifySignature");
  if ( v23 )
  {
    v4 = 0;
    qword_1800470D0 = (__int64)v23;
  }
  else
  {
    v24 = GetLastError();
    v4 = v24;
    if ( v24 )
    {
      if ( v24 > 0 )
        v4 = (unsigned __int16)v24 | 0x80070000;
    }
    else
    {
      v4 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  if ( (v4 & 0x80000000) != 0 )
LABEL_89:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v4);
  return v4;
}

```

## disassembly

```asm
0x1800386ec  push    rbx
0x1800386ee  push    rbp
0x1800386ef  push    rsi
0x1800386f0  push    rdi
0x1800386f1  sub     rsp, 28h
0x1800386f5  lea     rdx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider"
0x1800386fc  mov     rdi, rcx
0x1800386ff  call    cs:__imp_GetProcAddress
0x180038706  nop     dword ptr [rax+rax+00h]
0x18003870b  mov     esi, 80004005h
0x180038710  mov     ebp, 80070000h
0x180038715  test    rax, rax
0x180038718  jnz     short loc_180038740
0x18003871a  call    cs:__imp_GetLastError
0x180038721  nop     dword ptr [rax+rax+00h]
0x180038726  mov     ebx, eax
0x180038728  test    eax, eax
0x18003872a  jnz     short loc_180038730
0x18003872c  mov     ebx, esi
0x18003872e  jmp     short loc_180038737
0x180038730  jle     short loc_180038737
0x180038732  movzx   ebx, ax
0x180038735  or      ebx, ebp
0x180038737  mov     ecx, ebx
0x180038739  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003873e  jmp     short loc_180038749
0x180038740  xor     ebx, ebx
0x180038742  mov     cs:qword_180047080, rax
0x180038749  mov     ecx, ebx
0x18003874b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038750  test    ebx, ebx
0x180038752  js      loc_180038ACA
0x180038758  lea     rdx, aBcryptgetprope; "BCryptGetProperty"
0x18003875f  mov     rcx, rdi; hModule
0x180038762  call    cs:__imp_GetProcAddress
0x180038769  nop     dword ptr [rax+rax+00h]
0x18003876e  test    rax, rax
0x180038771  jnz     short loc_180038799
0x180038773  call    cs:__imp_GetLastError
0x18003877a  nop     dword ptr [rax+rax+00h]
0x18003877f  mov     ebx, eax
0x180038781  test    eax, eax
0x180038783  jnz     short loc_180038789
0x180038785  mov     ebx, esi
0x180038787  jmp     short loc_180038790
0x180038789  jle     short loc_180038790
0x18003878b  movzx   ebx, ax
0x18003878e  or      ebx, ebp
0x180038790  mov     ecx, ebx
0x180038792  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038797  jmp     short loc_1800387A2
0x180038799  xor     ebx, ebx
0x18003879b  mov     cs:qword_180047088, rax
0x1800387a2  mov     ecx, ebx
0x1800387a4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800387a9  test    ebx, ebx
0x1800387ab  js      loc_180038ACA
0x1800387b1  lea     rdx, aBcryptcreateha; "BCryptCreateHash"
0x1800387b8  mov     rcx, rdi; hModule
0x1800387bb  call    cs:__imp_GetProcAddress
0x1800387c2  nop     dword ptr [rax+rax+00h]
0x1800387c7  test    rax, rax
0x1800387ca  jnz     short loc_1800387F2
0x1800387cc  call    cs:__imp_GetLastError
0x1800387d3  nop     dword ptr [rax+rax+00h]
0x1800387d8  mov     ebx, eax
0x1800387da  test    eax, eax
0x1800387dc  jnz     short loc_1800387E2
0x1800387de  mov     ebx, esi
0x1800387e0  jmp     short loc_1800387E9
0x1800387e2  jle     short loc_1800387E9
0x1800387e4  movzx   ebx, ax
0x1800387e7  or      ebx, ebp
0x1800387e9  mov     ecx, ebx
0x1800387eb  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800387f0  jmp     short loc_1800387FB
0x1800387f2  xor     ebx, ebx
0x1800387f4  mov     cs:qword_180047090, rax
0x1800387fb  mov     ecx, ebx
0x1800387fd  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038802  test    ebx, ebx
0x180038804  js      loc_180038ACA
0x18003880a  lea     rdx, aBcryptgenrando; "BCryptGenRandom"
0x180038811  mov     rcx, rdi; hModule
0x180038814  call    cs:__imp_GetProcAddress
0x18003881b  nop     dword ptr [rax+rax+00h]
0x180038820  test    rax, rax
0x180038823  jnz     short loc_18003884B
0x180038825  call    cs:__imp_GetLastError
0x18003882c  nop     dword ptr [rax+rax+00h]
0x180038831  mov     ebx, eax
0x180038833  test    eax, eax
0x180038835  jnz     short loc_18003883B
0x180038837  mov     ebx, esi
0x180038839  jmp     short loc_180038842
0x18003883b  jle     short loc_180038842
0x18003883d  movzx   ebx, ax
0x180038840  or      ebx, ebp
0x180038842  mov     ecx, ebx
0x180038844  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038849  jmp     short loc_180038854
0x18003884b  xor     ebx, ebx
0x18003884d  mov     cs:qword_180047098, rax
0x180038854  mov     ecx, ebx
0x180038856  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003885b  test    ebx, ebx
0x18003885d  js      loc_180038ACA
0x180038863  lea     rdx, aBcrypthashdata; "BCryptHashData"
0x18003886a  mov     rcx, rdi; hModule
0x18003886d  call    cs:__imp_GetProcAddress
0x180038874  nop     dword ptr [rax+rax+00h]
0x180038879  test    rax, rax
0x18003887c  jnz     short loc_1800388A4
0x18003887e  call    cs:__imp_GetLastError
0x180038885  nop     dword ptr [rax+rax+00h]
0x18003888a  mov     ebx, eax
0x18003888c  test    eax, eax
0x18003888e  jnz     short loc_180038894
0x180038890  mov     ebx, esi
0x180038892  jmp     short loc_18003889B
0x180038894  jle     short loc_18003889B
0x180038896  movzx   ebx, ax
0x180038899  or      ebx, ebp
0x18003889b  mov     ecx, ebx
0x18003889d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800388a2  jmp     short loc_1800388AD
0x1800388a4  xor     ebx, ebx
0x1800388a6  mov     cs:qword_1800470A0, rax
0x1800388ad  mov     ecx, ebx
0x1800388af  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800388b4  test    ebx, ebx
0x1800388b6  js      loc_180038ACA
0x1800388bc  lea     rdx, aBcryptfinishha; "BCryptFinishHash"
0x1800388c3  mov     rcx, rdi; hModule
0x1800388c6  call    cs:__imp_GetProcAddress
0x1800388cd  nop     dword ptr [rax+rax+00h]
0x1800388d2  test    rax, rax
0x1800388d5  jnz     short loc_1800388FD
0x1800388d7  call    cs:__imp_GetLastError
0x1800388de  nop     dword ptr [rax+rax+00h]
0x1800388e3  mov     ebx, eax
0x1800388e5  test    eax, eax
0x1800388e7  jnz     short loc_1800388ED
0x1800388e9  mov     ebx, esi
0x1800388eb  jmp     short loc_1800388F4
0x1800388ed  jle     short loc_1800388F4
0x1800388ef  movzx   ebx, ax
0x1800388f2  or      ebx, ebp
0x1800388f4  mov     ecx, ebx
0x1800388f6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800388fb  jmp     short loc_180038906
0x1800388fd  xor     ebx, ebx
0x1800388ff  mov     cs:qword_1800470A8, rax
0x180038906  mov     ecx, ebx
0x180038908  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18003890d  test    ebx, ebx
0x18003890f  js      loc_180038ACA
0x180038915  lea     rdx, aBcryptclosealg; "BCryptCloseAlgorithmProvider"
0x18003891c  mov     rcx, rdi; hModule
0x18003891f  call    cs:__imp_GetProcAddress
0x180038926  nop     dword ptr [rax+rax+00h]
0x18003892b  test    rax, rax
0x18003892e  jnz     short loc_180038956
0x180038930  call    cs:__imp_GetLastError
0x180038937  nop     dword ptr [rax+rax+00h]
0x18003893c  mov     ebx, eax
0x18003893e  test    eax, eax
0x180038940  jnz     short loc_180038946
0x180038942  mov     ebx, esi
0x180038944  jmp     short loc_18003894D
0x180038946  jle     short loc_18003894D
0x180038948  movzx   ebx, ax
0x18003894b  or      ebx, ebp
0x18003894d  mov     ecx, ebx
0x18003894f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038954  jmp     short loc_18003895F
0x180038956  xor     ebx, ebx
0x180038958  mov     cs:qword_1800470B0, rax
0x18003895f  mov     ecx, ebx
0x180038961  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038966  test    ebx, ebx
0x180038968  js      loc_180038ACA
0x18003896e  lea     rdx, aBcryptdestroyk; "BCryptDestroyKey"
0x180038975  mov     rcx, rdi; hModule
0x180038978  call    cs:__imp_GetProcAddress
0x18003897f  nop     dword ptr [rax+rax+00h]
0x180038984  test    rax, rax
0x180038987  jnz     short loc_1800389AF
0x180038989  call    cs:__imp_GetLastError
0x180038990  nop     dword ptr [rax+rax+00h]
0x180038995  mov     ebx, eax
0x180038997  test    eax, eax
0x180038999  jnz     short loc_18003899F
0x18003899b  mov     ebx, esi
0x18003899d  jmp     short loc_1800389A6
0x18003899f  jle     short loc_1800389A6
0x1800389a1  movzx   ebx, ax
0x1800389a4  or      ebx, ebp
0x1800389a6  mov     ecx, ebx
0x1800389a8  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800389ad  jmp     short loc_1800389B8
0x1800389af  xor     ebx, ebx
0x1800389b1  mov     cs:qword_1800470B8, rax
0x1800389b8  mov     ecx, ebx
0x1800389ba  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800389bf  test    ebx, ebx
0x1800389c1  js      loc_180038ACA
0x1800389c7  lea     rdx, aBcryptdestroyh; "BCryptDestroyHash"
0x1800389ce  mov     rcx, rdi; hModule
0x1800389d1  call    cs:__imp_GetProcAddress
0x1800389d8  nop     dword ptr [rax+rax+00h]
0x1800389dd  test    rax, rax
0x1800389e0  jnz     short loc_180038A08
0x1800389e2  call    cs:__imp_GetLastError
0x1800389e9  nop     dword ptr [rax+rax+00h]
0x1800389ee  mov     ebx, eax
0x1800389f0  test    eax, eax
0x1800389f2  jnz     short loc_1800389F8
0x1800389f4  mov     ebx, esi
0x1800389f6  jmp     short loc_1800389FF
0x1800389f8  jle     short loc_1800389FF
0x1800389fa  movzx   ebx, ax
0x1800389fd  or      ebx, ebp
0x1800389ff  mov     ecx, ebx
0x180038a01  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038a06  jmp     short loc_180038A11
0x180038a08  xor     ebx, ebx
0x180038a0a  mov     cs:qword_1800470C0, rax
0x180038a11  mov     ecx, ebx
0x180038a13  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038a18  test    ebx, ebx
0x180038a1a  js      loc_180038ACA
0x180038a20  lea     rdx, aBcryptfreebuff; "BCryptFreeBuffer"
0x180038a27  mov     rcx, rdi; hModule
0x180038a2a  call    cs:__imp_GetProcAddress
0x180038a31  nop     dword ptr [rax+rax+00h]
0x180038a36  test    rax, rax
0x180038a39  jnz     short loc_180038A61
0x180038a3b  call    cs:__imp_GetLastError
0x180038a42  nop     dword ptr [rax+rax+00h]
0x180038a47  mov     ebx, eax
0x180038a49  test    eax, eax
0x180038a4b  jnz     short loc_180038A51
0x180038a4d  mov     ebx, esi
0x180038a4f  jmp     short loc_180038A58
0x180038a51  jle     short loc_180038A58
0x180038a53  movzx   ebx, ax
0x180038a56  or      ebx, ebp
0x180038a58  mov     ecx, ebx
0x180038a5a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038a5f  jmp     short loc_180038A6A
0x180038a61  xor     ebx, ebx
0x180038a63  mov     cs:qword_1800470C8, rax
0x180038a6a  mov     ecx, ebx
0x180038a6c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038a71  test    ebx, ebx
0x180038a73  js      short loc_180038ACA
0x180038a75  lea     rdx, aBcryptverifysi; "BCryptVerifySignature"
0x180038a7c  mov     rcx, rdi; hModule
0x180038a7f  call    cs:__imp_GetProcAddress
0x180038a86  nop     dword ptr [rax+rax+00h]
0x180038a8b  test    rax, rax
0x180038a8e  jnz     short loc_180038AB6
0x180038a90  call    cs:__imp_GetLastError
0x180038a97  nop     dword ptr [rax+rax+00h]
0x180038a9c  mov     ebx, eax
0x180038a9e  test    eax, eax
0x180038aa0  jnz     short loc_180038AA6
0x180038aa2  mov     ebx, esi
0x180038aa4  jmp     short loc_180038AAD
0x180038aa6  jle     short loc_180038AAD
0x180038aa8  movzx   ebx, ax
0x180038aab  or      ebx, ebp
0x180038aad  mov     ecx, ebx
0x180038aaf  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038ab4  jmp     short loc_180038ABF
0x180038ab6  xor     ebx, ebx
0x180038ab8  mov     cs:qword_1800470D0, rax
0x180038abf  mov     ecx, ebx
0x180038ac1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038ac6  test    ebx, ebx
0x180038ac8  jns     short loc_180038AD1
0x180038aca  mov     ecx, ebx
0x180038acc  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180038ad1  mov     ecx, ebx
0x180038ad3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180038ad8  mov     eax, ebx
0x180038ada  add     rsp, 28h
0x180038ade  pop     rdi
0x180038adf  pop     rsi
0x180038ae0  pop     rbp
0x180038ae1  pop     rbx
0x180038ae2  retn
```
