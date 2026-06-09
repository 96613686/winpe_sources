# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180022c90`
- end: `0x180022e8f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022c04`

## callees

- `0x180022c90`
- `0x180035590`
- `0x1800361ba`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180022de1`
- `KERNEL32!GetLastError` at `0x180022de1`
- `KERNEL32!DeactivateActCtx` at `0x180022e69`
- `KERNEL32!DeactivateActCtx` at `0x180075c82`
- `KERNEL32!DeactivateActCtx` at `0x180022e69`
- `KERNEL32!DeactivateActCtx` at `0x180075c82`
- `KERNEL32!LoadLibraryW` at `0x180022e5b`
- `KERNEL32!LoadLibraryW` at `0x180022e5b`
- `KERNEL32!ActivateActCtx` at `0x180022e0f`
- `KERNEL32!ActivateActCtx` at `0x180022e0f`
- `KERNEL32!FindActCtxSectionStringW` at `0x180022e4a`
- `KERNEL32!FindActCtxSectionStringW` at `0x180022e4a`
- `KERNEL32!CreateActCtxW` at `0x180022dd0`
- `KERNEL32!CreateActCtxW` at `0x180022dd0`
- `KERNEL32!GetModuleFileNameW` at `0x180022d72`
- `KERNEL32!GetModuleFileNameW` at `0x180022d72`
- `KERNEL32!QueryActCtxW` at `0x180022d04`
- `KERNEL32!QueryActCtxW` at `0x180022d04`
- `KERNEL32!GetModuleHandleExW` at `0x180022d51`
- `KERNEL32!GetModuleHandleExW` at `0x180022d51`
- `KERNEL32!SetLastError` at `0x180022d8a`
- `KERNEL32!SetLastError` at `0x180022d8a`

## string_xrefs

- `0x180022e3b`: `Comctl32.dll`
- `0x180022e54`: `Comctl32.dll`

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
        if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
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
0x180022c90  push    rbx
0x180022c92  sub     rsp, 2F0h
0x180022c99  mov     rax, cs:__security_cookie
0x180022ca0  xor     rax, rsp
0x180022ca3  mov     [rsp+2F8h+var_18], rax
0x180022cab  xorps   xmm0, xmm0
0x180022cae  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180022cb3  mov     [rsp+2F8h+Cookie], 0
0x180022cbc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180022cc3  jnz     loc_180022E6F
0x180022cc9  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180022cd1  jnz     loc_180022E6F
0x180022cd7  xor     ebx, ebx
0x180022cd9  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180022cde  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180022ce7  lea     rax, [rsp+2F8h+hActCtx]
0x180022cec  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180022cf1  lea     r9d, [rbx+1]; ulInfoClass
0x180022cf5  xor     r8d, r8d; pvSubInstance
0x180022cf8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180022cff  mov     ecx, 80000010h; dwFlags
0x180022d04  call    cs:__imp_QueryActCtxW
0x180022d0a  test    eax, eax
0x180022d0c  jz      loc_180022E74
0x180022d12  mov     rax, [rsp+2F8h+hActCtx]
0x180022d17  test    rax, rax
0x180022d1a  jnz     loc_180022E00
0x180022d20  xorps   xmm0, xmm0
0x180022d23  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180022d28  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180022d2d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180022d35  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180022d3d  mov     [rsp+2F8h+phModule], rax
0x180022d42  lea     r8, [rsp+2F8h+phModule]; phModule
0x180022d47  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180022d4e  lea     ecx, [rbx+6]; dwFlags
0x180022d51  call    cs:__imp_GetModuleHandleExW
0x180022d57  test    eax, eax
0x180022d59  jz      loc_180022E74
0x180022d5f  mov     r8d, 105h; nSize
0x180022d65  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180022d6d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180022d72  call    cs:__imp_GetModuleFileNameW
0x180022d78  test    eax, eax
0x180022d7a  jz      loc_180022E74
0x180022d80  cmp     eax, 105h
0x180022d85  jb      short loc_180022D95
0x180022d87  lea     ecx, [rbx+6Fh]; dwErrCode
0x180022d8a  call    cs:__imp_SetLastError
0x180022d90  jmp     loc_180022E74
0x180022d95  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180022d9d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180022da5  lea     rax, [rsp+2F8h+Filename]
0x180022dad  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180022db2  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180022dbe  mov     rax, [rsp+2F8h+phModule]
0x180022dc3  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180022dcb  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180022dd0  call    cs:__imp_CreateActCtxW
0x180022dd6  mov     [rsp+2F8h+hActCtx], rax
0x180022ddb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022ddf  jnz     short loc_180022E00
0x180022de1  call    cs:__imp_GetLastError
0x180022de7  lea     ecx, [rax-2]
0x180022dea  cmp     ecx, 1
0x180022ded  jbe     short loc_180022DF9
0x180022def  add     eax, 0FFFFF8ECh
0x180022df4  cmp     eax, 3
0x180022df7  ja      short loc_180022E74
0x180022df9  xor     eax, eax
0x180022dfb  mov     [rsp+2F8h+hActCtx], rax
0x180022e00  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180022e07  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180022e0c  mov     rcx, rax; hActCtx
0x180022e0f  call    cs:__imp_ActivateActCtx
0x180022e15  test    eax, eax
0x180022e17  jz      short loc_180022E6F
0x180022e19  mov     ebx, 70h ; 'p'
0x180022e1e  mov     r8d, ebx; Size
0x180022e21  xor     edx, edx; Val
0x180022e23  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180022e28  call    memset_0
0x180022e2d  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180022e31  lea     rax, [rsp+2F8h+pActCtx]
0x180022e36  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180022e3b  lea     r9, LibFileName; "Comctl32.dll"
0x180022e42  xor     edx, edx; lpExtensionGuid
0x180022e44  lea     r8d, [rbx-6Eh]; ulSectionId
0x180022e48  xor     ecx, ecx; dwFlags
0x180022e4a  call    cs:__imp_FindActCtxSectionStringW
0x180022e50  test    eax, eax
0x180022e52  jz      short loc_180022E62
0x180022e54  lea     rcx, LibFileName; "Comctl32.dll"
0x180022e5b  call    cs:__imp_LoadLibraryW
0x180022e61  nop
0x180022e62  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180022e67  xor     ecx, ecx; dwFlags
0x180022e69  call    cs:__imp_DeactivateActCtx
0x180022e6f  mov     ebx, 1
0x180022e74  mov     eax, ebx
0x180022e76  mov     rcx, [rsp+2F8h+var_18]
0x180022e7e  xor     rcx, rsp; StackCookie
0x180022e81  call    __security_check_cookie
0x180022e86  add     rsp, 2F0h
0x180022e8d  pop     rbx
0x180022e8e  retn
0x180075c73  push    rbp
0x180075c75  sub     rsp, 40h
0x180075c79  mov     rbp, rdx
0x180075c7c  mov     rdx, [rbp+48h]; ulCookie
0x180075c80  xor     ecx, ecx; dwFlags
0x180075c82  call    cs:__imp_DeactivateActCtx
0x180075c88  nop
0x180075c89  add     rsp, 40h
0x180075c8d  pop     rbp
0x180075c8e  retn
```
