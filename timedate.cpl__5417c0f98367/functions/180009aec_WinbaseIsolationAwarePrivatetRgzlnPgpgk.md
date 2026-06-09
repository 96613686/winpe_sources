# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180009aec`
- end: `0x180009ceb`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180009a60`

## callees

- `0x180009aec`
- `0x180028f2e`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180009bad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180009bad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009bce`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180009bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009c3d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009be6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009be6`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009cb7`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180009cb7`
- `KERNEL32!ActivateActCtx` at `0x180009c6b`
- `KERNEL32!ActivateActCtx` at `0x180009c6b`
- `KERNEL32!FindActCtxSectionStringW` at `0x180009ca6`
- `KERNEL32!FindActCtxSectionStringW` at `0x180009ca6`
- `KERNEL32!CreateActCtxW` at `0x180009c2c`
- `KERNEL32!CreateActCtxW` at `0x180009c2c`
- `KERNEL32!DeactivateActCtx` at `0x180009cc5`
- `KERNEL32!DeactivateActCtx` at `0x1800293e4`
- `KERNEL32!DeactivateActCtx` at `0x180009cc5`
- `KERNEL32!DeactivateActCtx` at `0x1800293e4`
- `KERNEL32!QueryActCtxW` at `0x180009b60`
- `KERNEL32!QueryActCtxW` at `0x180009b60`

## string_xrefs

- `0x180009c97`: `Comctl32.dll`
- `0x180009cb0`: `Comctl32.dll`

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
0x180009aec  push    rbx
0x180009aee  sub     rsp, 2F0h
0x180009af5  mov     rax, cs:__security_cookie
0x180009afc  xor     rax, rsp
0x180009aff  mov     [rsp+2F8h+var_18], rax
0x180009b07  xorps   xmm0, xmm0
0x180009b0a  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180009b0f  mov     [rsp+2F8h+Cookie], 0
0x180009b18  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180009b1f  jnz     loc_180009CCB
0x180009b25  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180009b2d  jnz     loc_180009CCB
0x180009b33  xor     ebx, ebx
0x180009b35  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180009b3a  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180009b43  lea     rax, [rsp+2F8h+hActCtx]
0x180009b48  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180009b4d  lea     r9d, [rbx+1]; ulInfoClass
0x180009b51  xor     r8d, r8d; pvSubInstance
0x180009b54  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180009b5b  mov     ecx, 80000010h; dwFlags
0x180009b60  call    cs:__imp_QueryActCtxW
0x180009b66  test    eax, eax
0x180009b68  jz      loc_180009CD0
0x180009b6e  mov     rax, [rsp+2F8h+hActCtx]
0x180009b73  test    rax, rax
0x180009b76  jnz     loc_180009C5C
0x180009b7c  xorps   xmm0, xmm0
0x180009b7f  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180009b84  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180009b89  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180009b91  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180009b99  mov     [rsp+2F8h+phModule], rax
0x180009b9e  lea     r8, [rsp+2F8h+phModule]; phModule
0x180009ba3  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180009baa  lea     ecx, [rbx+6]; dwFlags
0x180009bad  call    cs:__imp_GetModuleHandleExW
0x180009bb3  test    eax, eax
0x180009bb5  jz      loc_180009CD0
0x180009bbb  mov     r8d, 105h; nSize
0x180009bc1  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180009bc9  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180009bce  call    cs:__imp_GetModuleFileNameW
0x180009bd4  test    eax, eax
0x180009bd6  jz      loc_180009CD0
0x180009bdc  cmp     eax, 105h
0x180009be1  jb      short loc_180009BF1
0x180009be3  lea     ecx, [rbx+6Fh]; dwErrCode
0x180009be6  call    cs:__imp_SetLastError
0x180009bec  jmp     loc_180009CD0
0x180009bf1  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180009bf9  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180009c01  lea     rax, [rsp+2F8h+Filename]
0x180009c09  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180009c0e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180009c1a  mov     rax, [rsp+2F8h+phModule]
0x180009c1f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180009c27  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180009c2c  call    cs:__imp_CreateActCtxW
0x180009c32  mov     [rsp+2F8h+hActCtx], rax
0x180009c37  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009c3b  jnz     short loc_180009C5C
0x180009c3d  call    cs:__imp_GetLastError
0x180009c43  lea     ecx, [rax-2]
0x180009c46  cmp     ecx, 1
0x180009c49  jbe     short loc_180009C55
0x180009c4b  add     eax, 0FFFFF8ECh
0x180009c50  cmp     eax, 3
0x180009c53  ja      short loc_180009CD0
0x180009c55  xor     eax, eax
0x180009c57  mov     [rsp+2F8h+hActCtx], rax
0x180009c5c  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180009c63  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180009c68  mov     rcx, rax; hActCtx
0x180009c6b  call    cs:__imp_ActivateActCtx
0x180009c71  test    eax, eax
0x180009c73  jz      short loc_180009CCB
0x180009c75  mov     ebx, 70h ; 'p'
0x180009c7a  mov     r8d, ebx; Size
0x180009c7d  xor     edx, edx; Val
0x180009c7f  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180009c84  call    memset_0
0x180009c89  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180009c8d  lea     rax, [rsp+2F8h+pActCtx]
0x180009c92  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180009c97  lea     r9, LibFileName; "Comctl32.dll"
0x180009c9e  xor     edx, edx; lpExtensionGuid
0x180009ca0  lea     r8d, [rbx-6Eh]; ulSectionId
0x180009ca4  xor     ecx, ecx; dwFlags
0x180009ca6  call    cs:__imp_FindActCtxSectionStringW
0x180009cac  test    eax, eax
0x180009cae  jz      short loc_180009CBE
0x180009cb0  lea     rcx, LibFileName; "Comctl32.dll"
0x180009cb7  call    cs:__imp_LoadLibraryW
0x180009cbd  nop
0x180009cbe  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180009cc3  xor     ecx, ecx; dwFlags
0x180009cc5  call    cs:__imp_DeactivateActCtx
0x180009ccb  mov     ebx, 1
0x180009cd0  mov     eax, ebx
0x180009cd2  mov     rcx, [rsp+2F8h+var_18]
0x180009cda  xor     rcx, rsp; StackCookie
0x180009cdd  call    __security_check_cookie
0x180009ce2  add     rsp, 2F0h
0x180009ce9  pop     rbx
0x180009cea  retn
0x1800293d5  push    rbp
0x1800293d7  sub     rsp, 40h
0x1800293db  mov     rbp, rdx
0x1800293de  mov     rdx, [rbp+48h]; ulCookie
0x1800293e2  xor     ecx, ecx; dwFlags
0x1800293e4  call    cs:__imp_DeactivateActCtx
0x1800293ea  nop
0x1800293eb  add     rsp, 40h
0x1800293ef  pop     rbp
0x1800293f0  retn
```
