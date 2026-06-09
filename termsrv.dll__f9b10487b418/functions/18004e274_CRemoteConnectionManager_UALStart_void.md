# CRemoteConnectionManager::UALStart(void)

- ea: `0x18004e274`
- end: `0x18004e3bc`
- name: `?UALStart@CRemoteConnectionManager@@AEAAJXZ`
- size: `328`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180046100`

## callees

- `0x18000a210`
- `0x1800321f0`
- `0x1800330c4`
- `0x18004e274`
- `0x18004e3c4`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e2ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e307`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e322`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e2ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e307`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e322`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004e2d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18004e2d0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004e2bc`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18004e2bc`

## string_xrefs

- `0x18004e2b5`: `%SystemRoot%\system32\UALAPI.dll`

## pseudocode

```c
__int64 __fastcall CRemoteConnectionManager::UALStart(CRemoteConnectionManager *this)
{
  unsigned int v2; // edi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v5; // rcx
  FARPROC v6; // rax
  HMODULE v7; // rcx
  __int64 (__fastcall *v8)(WCHAR *); // rax
  int v9; // eax
  WCHAR Dst[2]; // [rsp+20h] [rbp-2C8h] BYREF
  __int128 v12; // [rsp+24h] [rbp-2C4h]
  _BYTE v13[668]; // [rsp+34h] [rbp-2B4h] BYREF

  v2 = 0;
  memset_0(Dst, 0, 0x208u);
  if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\system32\\UALAPI.dll", Dst, 0x104u) )
  {
    Library = LoadLibraryExW(Dst, 0, 0);
    *((_QWORD *)this + 322) = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "UalStart");
      v5 = (HMODULE)*((_QWORD *)this + 322);
      *((_QWORD *)this + 323) = ProcAddress;
      v6 = GetProcAddress(v5, "UalStop");
      v7 = (HMODULE)*((_QWORD *)this + 322);
      *((_QWORD *)this + 324) = v6;
      *((_QWORD *)this + 325) = GetProcAddress(v7, "UalInstrument");
    }
  }
  if ( *((_QWORD *)this + 323) )
  {
    memset_0(v13, 0, sizeof(v13));
    v8 = (__int64 (__fastcall *)(WCHAR *))*((_QWORD *)this + 323);
    wcscpy(Dst, L"ʰ");
    v12 = xmmword_1800DFFD0;
    v9 = v8(Dst);
    v2 = v9;
    if ( v9 < 0 )
    {
      _DbgPrintMessage(8, "UalStart failed: 0x%x in %s", v9, "CRemoteConnectionManager::UALStart");
      CRemoteConnectionManager::UALStop(this);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18004e274  mov     [rsp+arg_8], rbx
0x18004e279  push    rdi
0x18004e27a  sub     rsp, 2E0h
0x18004e281  mov     rax, cs:__security_cookie
0x18004e288  xor     rax, rsp
0x18004e28b  mov     [rsp+2E8h+var_18], rax
0x18004e293  mov     rbx, rcx
0x18004e296  xor     edx, edx; Val
0x18004e298  lea     rcx, [rsp+2E8h+Dst]; void *
0x18004e29d  mov     r8d, 208h; Size
0x18004e2a3  xor     edi, edi
0x18004e2a5  call    memset_0
0x18004e2aa  mov     r8d, 104h; nSize
0x18004e2b0  lea     rdx, [rsp+2E8h+Dst]; lpDst
0x18004e2b5  lea     rcx, aSystemrootSyst_3; "%SystemRoot%\\system32\\UALAPI.dll"
0x18004e2bc  call    cs:__imp_ExpandEnvironmentStringsW
0x18004e2c2  test    eax, eax
0x18004e2c4  jz      short loc_18004E32F
0x18004e2c6  xor     r8d, r8d; dwFlags
0x18004e2c9  lea     rcx, [rsp+2E8h+Dst]; lpLibFileName
0x18004e2ce  xor     edx, edx; hFile
0x18004e2d0  call    cs:__imp_LoadLibraryExW
0x18004e2d6  mov     [rbx+0A10h], rax
0x18004e2dd  test    rax, rax
0x18004e2e0  jz      short loc_18004E32F
0x18004e2e2  lea     rdx, aUalstart; "UalStart"
0x18004e2e9  mov     rcx, rax; hModule
0x18004e2ec  call    cs:__imp_GetProcAddress
0x18004e2f2  mov     rcx, [rbx+0A10h]; hModule
0x18004e2f9  lea     rdx, aUalstop; "UalStop"
0x18004e300  mov     [rbx+0A18h], rax
0x18004e307  call    cs:__imp_GetProcAddress
0x18004e30d  mov     rcx, [rbx+0A10h]; hModule
0x18004e314  lea     rdx, aUalinstrument; "UalInstrument"
0x18004e31b  mov     [rbx+0A20h], rax
0x18004e322  call    cs:__imp_GetProcAddress
0x18004e328  mov     [rbx+0A28h], rax
0x18004e32f  cmp     [rbx+0A18h], rdi
0x18004e336  jz      short loc_18004E399
0x18004e338  xor     edx, edx; Val
0x18004e33a  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x18004e33f  mov     r8d, 29Ch; Size
0x18004e345  call    memset_0
0x18004e34a  movups  xmm0, cs:xmmword_1800DFFD0
0x18004e351  mov     rax, [rbx+0A18h]
0x18004e358  lea     rcx, [rsp+2E8h+Dst]
0x18004e35d  mov     dword ptr [rsp+2E8h+Dst], 2B0h
0x18004e365  movdqu  [rsp+2E8h+var_2C4], xmm0
0x18004e36b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e370  mov     edi, eax
0x18004e372  test    eax, eax
0x18004e374  jns     short loc_18004E399
0x18004e376  lea     r9, aCremoteconnect_15; "CRemoteConnectionManager::UALStart"
0x18004e37d  mov     r8d, eax
0x18004e380  lea     rdx, aUalstartFailed_0; "UalStart failed: 0x%x in %s"
0x18004e387  mov     ecx, 8; int
0x18004e38c  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004e391  mov     rcx, rbx; this
0x18004e394  call    ?UALStop@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::UALStop(void)
0x18004e399  mov     eax, edi
0x18004e39b  mov     rcx, [rsp+2E8h+var_18]
0x18004e3a3  xor     rcx, rsp; StackCookie
0x18004e3a6  call    __security_check_cookie
0x18004e3ab  mov     rbx, [rsp+2E8h+arg_8]
0x18004e3b3  add     rsp, 2E0h
0x18004e3ba  pop     rdi
0x18004e3bb  retn
```
