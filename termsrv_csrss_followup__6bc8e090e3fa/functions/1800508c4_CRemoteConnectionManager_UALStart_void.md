# CRemoteConnectionManager::UALStart(void)

- ea: `0x1800508c4`
- end: `0x180050a2f`
- name: `?UALStart@CRemoteConnectionManager@@AEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(CRemoteConnectionManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180048510`

## callees

- `0x180009940`
- `0x180033f60`
- `0x180034e64`
- `0x1800508c4`
- `0x180050a38`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005094c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005096d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005098e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005094c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005096d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18005098e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005092a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005092a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005090c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005090c`

## string_xrefs

- `0x180050905`: `%SystemRoot%\system32\UALAPI.dll`

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
    v12 = xmmword_1800E6020;
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
0x1800508c4  mov     [rsp+arg_8], rbx
0x1800508c9  push    rdi
0x1800508ca  sub     rsp, 2E0h
0x1800508d1  mov     rax, cs:__security_cookie
0x1800508d8  xor     rax, rsp
0x1800508db  mov     [rsp+2E8h+var_18], rax
0x1800508e3  mov     rbx, rcx
0x1800508e6  xor     edx, edx; Val
0x1800508e8  lea     rcx, [rsp+2E8h+Dst]; void *
0x1800508ed  mov     r8d, 208h; Size
0x1800508f3  xor     edi, edi
0x1800508f5  call    memset_0
0x1800508fa  mov     r8d, 104h; nSize
0x180050900  lea     rdx, [rsp+2E8h+Dst]; lpDst
0x180050905  lea     rcx, aSystemrootSyst_3; "%SystemRoot%\\system32\\UALAPI.dll"
0x18005090c  call    cs:__imp_ExpandEnvironmentStringsW
0x180050913  nop     dword ptr [rax+rax+00h]
0x180050918  test    eax, eax
0x18005091a  jz      loc_1800509A1
0x180050920  xor     r8d, r8d; dwFlags
0x180050923  lea     rcx, [rsp+2E8h+Dst]; lpLibFileName
0x180050928  xor     edx, edx; hFile
0x18005092a  call    cs:__imp_LoadLibraryExW
0x180050931  nop     dword ptr [rax+rax+00h]
0x180050936  mov     [rbx+0A10h], rax
0x18005093d  test    rax, rax
0x180050940  jz      short loc_1800509A1
0x180050942  lea     rdx, aUalstart; "UalStart"
0x180050949  mov     rcx, rax; hModule
0x18005094c  call    cs:__imp_GetProcAddress
0x180050953  nop     dword ptr [rax+rax+00h]
0x180050958  mov     rcx, [rbx+0A10h]; hModule
0x18005095f  lea     rdx, aUalstop; "UalStop"
0x180050966  mov     [rbx+0A18h], rax
0x18005096d  call    cs:__imp_GetProcAddress
0x180050974  nop     dword ptr [rax+rax+00h]
0x180050979  mov     rcx, [rbx+0A10h]; hModule
0x180050980  lea     rdx, aUalinstrument; "UalInstrument"
0x180050987  mov     [rbx+0A20h], rax
0x18005098e  call    cs:__imp_GetProcAddress
0x180050995  nop     dword ptr [rax+rax+00h]
0x18005099a  mov     [rbx+0A28h], rax
0x1800509a1  cmp     [rbx+0A18h], rdi
0x1800509a8  jz      short loc_180050A0B
0x1800509aa  xor     edx, edx; Val
0x1800509ac  lea     rcx, [rsp+2E8h+var_2B4]; void *
0x1800509b1  mov     r8d, 29Ch; Size
0x1800509b7  call    memset_0
0x1800509bc  movups  xmm0, cs:xmmword_1800E6020
0x1800509c3  mov     rax, [rbx+0A18h]
0x1800509ca  lea     rcx, [rsp+2E8h+Dst]
0x1800509cf  mov     dword ptr [rsp+2E8h+Dst], 2B0h
0x1800509d7  movdqu  [rsp+2E8h+var_2C4], xmm0
0x1800509dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800509e2  mov     edi, eax
0x1800509e4  test    eax, eax
0x1800509e6  jns     short loc_180050A0B
0x1800509e8  lea     r9, aCremoteconnect_15; "CRemoteConnectionManager::UALStart"
0x1800509ef  mov     r8d, eax
0x1800509f2  lea     rdx, aUalstartFailed_0; "UalStart failed: 0x%x in %s"
0x1800509f9  mov     ecx, 8; int
0x1800509fe  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180050a03  mov     rcx, rbx; this
0x180050a06  call    ?UALStop@CRemoteConnectionManager@@AEAAJXZ; CRemoteConnectionManager::UALStop(void)
0x180050a0b  mov     eax, edi
0x180050a0d  mov     rcx, [rsp+2E8h+var_18]
0x180050a15  xor     rcx, rsp; StackCookie
0x180050a18  call    __security_check_cookie
0x180050a1d  mov     rbx, [rsp+2E8h+arg_8]
0x180050a25  add     rsp, 2E0h
0x180050a2c  pop     rdi
0x180050a2d  retn
```
