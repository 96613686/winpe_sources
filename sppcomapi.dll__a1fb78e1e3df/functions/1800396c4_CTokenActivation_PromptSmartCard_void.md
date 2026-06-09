# CTokenActivation::PromptSmartCard(void)

- ea: `0x1800396c4`
- end: `0x1800398ad`
- name: `?PromptSmartCard@CTokenActivation@@IEAAJXZ`
- size: `489`
- prototype: `__int64 __fastcall(CTokenActivation *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003a800`

## callees

- `0x180003520`
- `0x180004288`
- `0x1800396c4`
- `0x18003c52a`
- `0x18003c560`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003987a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003987a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800397af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800397af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800397fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800397fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003980d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800397c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003980d`
- `WinSCard!SCardEstablishContext` at `0x18003973d`
- `WinSCard!SCardEstablishContext` at `0x18003973d`
- `WinSCard!SCardReleaseContext` at `0x18003985d`
- `WinSCard!SCardReleaseContext` at `0x18003985d`

## string_xrefs

- `0x18003978e`: `SCARDDLG.DLL`

## pseudocode

```c
__int64 __fastcall CTokenActivation::PromptSmartCard(CTokenActivation *this)
{
  LONG v2; // eax
  unsigned int v3; // edi
  HMODULE v4; // rbx
  HMODULE Library; // rax
  signed int v6; // eax
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  __int64 v9; // rcx
  SCARDCONTEXT phContext[2]; // [rsp+20h] [rbp-E0h] BYREF
  int v12; // [rsp+30h] [rbp-D0h] BYREF
  SCARDCONTEXT v13; // [rsp+38h] [rbp-C8h]
  __int64 v14; // [rsp+40h] [rbp-C0h]
  int v15; // [rsp+48h] [rbp-B8h]
  __int128 v16; // [rsp+50h] [rbp-B0h]
  _BYTE *v17; // [rsp+88h] [rbp-78h]
  int v18; // [rsp+90h] [rbp-70h]
  _BYTE *v19; // [rsp+98h] [rbp-68h]
  int v20; // [rsp+A0h] [rbp-60h]
  _BYTE v21[512]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v22[512]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset_0(&v12, 0, 0x80u);
  phContext[0] = 0;
  memset_0(v21, 0, sizeof(v21));
  memset_0(v22, 0, sizeof(v22));
  v2 = SCardEstablishContext(0, 0, 0, phContext);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    goto LABEL_16;
  }
  v13 = phContext[0];
  v14 = *((_QWORD *)this + 20);
  v18 = 256;
  v17 = v21;
  v20 = 256;
  v19 = v22;
  v12 = 128;
  v15 = 4;
  v16 = 0;
  Library = LoadLibraryExW(L"SCARDDLG.DLL", 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "SCardUIDlgSelectCardW");
    if ( !ProcAddress )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v3 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v3 = -2147467259;
      }
      v9 = v3;
      goto LABEL_17;
    }
    v2 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v12);
    v3 = v2;
    if ( v2 >= 0 )
      goto LABEL_18;
LABEL_16:
    v9 = (unsigned int)v2;
LABEL_17:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_18;
  }
  v6 = GetLastError();
  v3 = v6;
  if ( v6 )
  {
    if ( v6 > 0 )
      v3 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v3 = -2147467259;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v3);
  v4 = 0;
LABEL_18:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v3);
  if ( phContext[0] )
  {
    SCardReleaseContext(phContext[0]);
    phContext[0] = 0;
  }
  if ( v4 )
    FreeLibrary(v4);
  return v3;
}

```

## disassembly

```asm
0x1800396c4  mov     [rsp-8+arg_8], rbx
0x1800396c9  mov     [rsp-8+arg_10], rdi
0x1800396ce  push    rbp
0x1800396cf  lea     rbp, [rsp-3C0h]
0x1800396d7  sub     rsp, 4C0h
0x1800396de  mov     rax, cs:__security_cookie
0x1800396e5  xor     rax, rsp
0x1800396e8  mov     [rbp+3C0h+var_10], rax
0x1800396ef  mov     rbx, rcx
0x1800396f2  xor     edx, edx; Val
0x1800396f4  lea     rcx, [rsp+4C0h+var_490]; void *
0x1800396f9  mov     r8d, 80h; Size
0x1800396ff  call    memset_0
0x180039704  mov     edi, 200h
0x180039709  mov     [rsp+4C0h+phContext], 0
0x180039712  mov     r8d, edi; Size
0x180039715  lea     rcx, [rbp+3C0h+var_410]; void *
0x180039719  xor     edx, edx; Val
0x18003971b  call    memset_0
0x180039720  mov     r8d, edi; Size
0x180039723  lea     rcx, [rbp+3C0h+var_210]; void *
0x18003972a  xor     edx, edx; Val
0x18003972c  call    memset_0
0x180039731  lea     r9, [rsp+4C0h+phContext]; phContext
0x180039736  xor     r8d, r8d; pvReserved2
0x180039739  xor     edx, edx; pvReserved1
0x18003973b  xor     ecx, ecx; dwScope
0x18003973d  call    cs:__imp_SCardEstablishContext
0x180039744  nop     dword ptr [rax+rax+00h]
0x180039749  mov     edi, eax
0x18003974b  test    eax, eax
0x18003974d  jns     short loc_180039756
0x18003974f  xor     ebx, ebx
0x180039751  jmp     loc_180039845
0x180039756  mov     rax, [rsp+4C0h+phContext]
0x18003975b  mov     ecx, 100h
0x180039760  mov     [rsp+4C0h+var_488], rax
0x180039765  xorps   xmm0, xmm0
0x180039768  mov     rax, [rbx+0A0h]
0x18003976f  xor     r8d, r8d; dwFlags
0x180039772  mov     [rsp+4C0h+var_480], rax
0x180039777  xor     edx, edx; hFile
0x180039779  lea     rax, [rbp+3C0h+var_410]
0x18003977d  mov     [rbp+3C0h+var_430], ecx
0x180039780  mov     [rbp+3C0h+var_438], rax
0x180039784  lea     rax, [rbp+3C0h+var_210]
0x18003978b  mov     [rbp+3C0h+var_420], ecx
0x18003978e  lea     rcx, LibFileName; "SCARDDLG.DLL"
0x180039795  mov     [rbp+3C0h+var_428], rax
0x180039799  mov     [rsp+4C0h+var_490], 80h
0x1800397a1  mov     [rsp+4C0h+var_478], 4
0x1800397a9  movdqa  [rsp+4C0h+var_470], xmm0
0x1800397af  call    cs:__imp_LoadLibraryExW
0x1800397b6  nop     dword ptr [rax+rax+00h]
0x1800397bb  mov     rbx, rax
0x1800397be  test    rax, rax
0x1800397c1  jnz     short loc_1800397F2
0x1800397c3  call    cs:__imp_GetLastError
0x1800397ca  nop     dword ptr [rax+rax+00h]
0x1800397cf  mov     edi, eax
0x1800397d1  test    eax, eax
0x1800397d3  jnz     short loc_1800397DC
0x1800397d5  mov     edi, 80004005h
0x1800397da  jmp     short loc_1800397E7
0x1800397dc  jle     short loc_1800397E7
0x1800397de  movzx   edi, ax
0x1800397e1  or      edi, 80070000h
0x1800397e7  mov     ecx, edi
0x1800397e9  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800397ee  xor     ebx, ebx
0x1800397f0  jmp     short loc_18003984C
0x1800397f2  mov     rcx, rax; hModule
0x1800397f5  lea     rdx, aScarduidlgsele; "SCardUIDlgSelectCardW"
0x1800397fc  call    cs:__imp_GetProcAddress
0x180039803  nop     dword ptr [rax+rax+00h]
0x180039808  test    rax, rax
0x18003980b  jnz     short loc_180039835
0x18003980d  call    cs:__imp_GetLastError
0x180039814  nop     dword ptr [rax+rax+00h]
0x180039819  mov     edi, eax
0x18003981b  test    eax, eax
0x18003981d  jnz     short loc_180039826
0x18003981f  mov     edi, 80004005h
0x180039824  jmp     short loc_180039831
0x180039826  jle     short loc_180039831
0x180039828  movzx   edi, ax
0x18003982b  or      edi, 80070000h
0x180039831  mov     ecx, edi
0x180039833  jmp     short loc_180039847
0x180039835  lea     rcx, [rsp+4C0h+var_490]
0x18003983a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003983f  mov     edi, eax
0x180039841  test    eax, eax
0x180039843  jns     short loc_18003984C
0x180039845  mov     ecx, eax
0x180039847  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003984c  mov     ecx, edi
0x18003984e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039853  mov     rcx, [rsp+4C0h+phContext]; hContext
0x180039858  test    rcx, rcx
0x18003985b  jz      short loc_180039872
0x18003985d  call    cs:__imp_SCardReleaseContext
0x180039864  nop     dword ptr [rax+rax+00h]
0x180039869  mov     [rsp+4C0h+phContext], 0
0x180039872  test    rbx, rbx
0x180039875  jz      short loc_180039886
0x180039877  mov     rcx, rbx; hLibModule
0x18003987a  call    cs:__imp_FreeLibrary
0x180039881  nop     dword ptr [rax+rax+00h]
0x180039886  mov     eax, edi
0x180039888  mov     rcx, [rbp+3C0h+var_10]
0x18003988f  xor     rcx, rsp; StackCookie
0x180039892  call    __security_check_cookie
0x180039897  lea     r11, [rsp+4C0h+var_s0]
0x18003989f  mov     rbx, [r11+18h]
0x1800398a3  mov     rdi, [r11+20h]
0x1800398a7  mov     rsp, r11
0x1800398aa  pop     rbp
0x1800398ab  retn
```
