# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18001eb24`
- end: `0x18001ed65`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `577`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001ea84`

## callees

- `0x18001eb24`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ec12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001ec12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ebeb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001ebeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec30`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ec30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec93`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ec93`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001ed38`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af67f`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001ed38`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af67f`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001ec7c`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001ec7c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18001eb98`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18001eb98`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18001ed0d`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18001ed0d`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18001eccc`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18001eccc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ed24`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001ed24`

## string_xrefs

- `0x18001ecfe`: `Comctl32.dll`
- `0x18001ed1d`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  v0 = 0;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    memset(&pActCtx, 0, 56);
    phModule = 0;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            memset_0(&pActCtx, 0, sizeof(pActCtx));
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001eb24  push    rbx
0x18001eb26  sub     rsp, 2F0h
0x18001eb2d  mov     rax, cs:__security_cookie
0x18001eb34  xor     rax, rsp
0x18001eb37  mov     [rsp+2F8h+var_18], rax
0x18001eb3f  xorps   xmm0, xmm0
0x18001eb42  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18001eb47  mov     [rsp+2F8h+Cookie], 0
0x18001eb50  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001eb57  jnz     loc_18001ED44
0x18001eb5d  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18001eb65  jnz     loc_18001ED44
0x18001eb6b  xor     ebx, ebx
0x18001eb6d  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18001eb72  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18001eb7b  lea     rax, [rsp+2F8h+hActCtx]
0x18001eb80  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18001eb85  lea     r9d, [rbx+1]; ulInfoClass
0x18001eb89  xor     r8d, r8d; pvSubInstance
0x18001eb8c  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18001eb93  mov     ecx, 80000010h; dwFlags
0x18001eb98  call    cs:__imp_QueryActCtxW
0x18001eb9f  nop     dword ptr [rax+rax+00h]
0x18001eba4  test    eax, eax
0x18001eba6  jz      loc_18001ED49
0x18001ebac  mov     rax, [rsp+2F8h+hActCtx]
0x18001ebb1  test    rax, rax
0x18001ebb4  jnz     loc_18001ECBD
0x18001ebba  xorps   xmm0, xmm0
0x18001ebbd  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18001ebc2  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18001ebc7  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18001ebcf  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001ebd7  mov     [rsp+2F8h+phModule], rax
0x18001ebdc  lea     r8, [rsp+2F8h+phModule]; phModule
0x18001ebe1  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18001ebe8  lea     ecx, [rbx+6]; dwFlags
0x18001ebeb  call    cs:__imp_GetModuleHandleExW
0x18001ebf2  nop     dword ptr [rax+rax+00h]
0x18001ebf7  test    eax, eax
0x18001ebf9  jz      loc_18001ED49
0x18001ebff  mov     r8d, 105h; nSize
0x18001ec05  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18001ec0d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18001ec12  call    cs:__imp_GetModuleFileNameW
0x18001ec19  nop     dword ptr [rax+rax+00h]
0x18001ec1e  test    eax, eax
0x18001ec20  jz      loc_18001ED49
0x18001ec26  cmp     eax, 105h
0x18001ec2b  jb      short loc_18001EC41
0x18001ec2d  lea     ecx, [rbx+6Fh]; dwErrCode
0x18001ec30  call    cs:__imp_SetLastError
0x18001ec37  nop     dword ptr [rax+rax+00h]
0x18001ec3c  jmp     loc_18001ED49
0x18001ec41  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18001ec49  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18001ec51  lea     rax, [rsp+2F8h+Filename]
0x18001ec59  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18001ec5e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18001ec6a  mov     rax, [rsp+2F8h+phModule]
0x18001ec6f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001ec77  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18001ec7c  call    cs:__imp_CreateActCtxW
0x18001ec83  nop     dword ptr [rax+rax+00h]
0x18001ec88  mov     [rsp+2F8h+hActCtx], rax
0x18001ec8d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ec91  jnz     short loc_18001ECBD
0x18001ec93  call    cs:__imp_GetLastError
0x18001ec9a  nop     dword ptr [rax+rax+00h]
0x18001ec9f  lea     ecx, [rax-714h]
0x18001eca5  cmp     ecx, 3
0x18001eca8  jbe     short loc_18001ECB6
0x18001ecaa  add     eax, 0FFFFFFFEh
0x18001ecad  cmp     eax, 1
0x18001ecb0  ja      loc_18001ED49
0x18001ecb6  xor     eax, eax
0x18001ecb8  mov     [rsp+2F8h+hActCtx], rax
0x18001ecbd  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18001ecc4  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18001ecc9  mov     rcx, rax; hActCtx
0x18001eccc  call    cs:__imp_ActivateActCtx
0x18001ecd3  nop     dword ptr [rax+rax+00h]
0x18001ecd8  test    eax, eax
0x18001ecda  jz      short loc_18001ED44
0x18001ecdc  mov     ebx, 70h ; 'p'
0x18001ece1  mov     r8d, ebx; Size
0x18001ece4  xor     edx, edx; Val
0x18001ece6  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18001eceb  call    memset_0
0x18001ecf0  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18001ecf4  lea     rax, [rsp+2F8h+pActCtx]
0x18001ecf9  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18001ecfe  lea     r9, LibFileName; "Comctl32.dll"
0x18001ed05  xor     edx, edx; lpExtensionGuid
0x18001ed07  lea     r8d, [rbx-6Eh]; ulSectionId
0x18001ed0b  xor     ecx, ecx; dwFlags
0x18001ed0d  call    cs:__imp_FindActCtxSectionStringW
0x18001ed14  nop     dword ptr [rax+rax+00h]
0x18001ed19  test    eax, eax
0x18001ed1b  jz      short loc_18001ED31
0x18001ed1d  lea     rcx, LibFileName; "Comctl32.dll"
0x18001ed24  call    cs:__imp_LoadLibraryW
0x18001ed2b  nop     dword ptr [rax+rax+00h]
0x18001ed30  nop
0x18001ed31  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18001ed36  xor     ecx, ecx; dwFlags
0x18001ed38  call    cs:__imp_DeactivateActCtx
0x18001ed3f  nop     dword ptr [rax+rax+00h]
0x18001ed44  mov     ebx, 1
0x18001ed49  mov     eax, ebx
0x18001ed4b  mov     rcx, [rsp+2F8h+var_18]
0x18001ed53  xor     rcx, rsp; StackCookie
0x18001ed56  call    __security_check_cookie
0x18001ed5b  add     rsp, 2F0h
0x18001ed62  pop     rbx
0x18001ed63  retn
0x1800af670  push    rbp
0x1800af672  sub     rsp, 40h
0x1800af676  mov     rbp, rdx
0x1800af679  mov     rdx, [rbp+48h]; ulCookie
0x1800af67d  xor     ecx, ecx; dwFlags
0x1800af67f  call    cs:__imp_DeactivateActCtx
0x1800af686  nop     dword ptr [rax+rax+00h]
0x1800af68b  nop
0x1800af68c  add     rsp, 40h
0x1800af690  pop     rbp
0x1800af691  retn
```
