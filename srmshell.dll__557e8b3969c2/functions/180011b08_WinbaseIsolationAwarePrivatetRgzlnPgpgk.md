# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180011b08`
- end: `0x180011d08`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800117d4`

## callees

- `0x180011b08`
- `0x18001b3ee`
- `0x18001b420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011c59`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011c02`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011bea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180011bea`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011bc9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180011bc9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011cd4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180011cd4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011ce2`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e504`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180011ce2`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e504`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180011c48`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180011c48`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180011c88`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x180011c88`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180011b7c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x180011b7c`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180011cc3`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x180011cc3`

## string_xrefs

- `0x180011cb4`: `Comctl32.dll`
- `0x180011ccd`: `Comctl32.dll`

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
0x180011b08  push    rbx
0x180011b0a  sub     rsp, 2F0h
0x180011b11  mov     rax, cs:__security_cookie
0x180011b18  xor     rax, rsp
0x180011b1b  mov     [rsp+2F8h+var_18], rax
0x180011b23  xorps   xmm0, xmm0
0x180011b26  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180011b2b  mov     [rsp+2F8h+Cookie], 0
0x180011b34  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180011b3b  jnz     loc_180011CE8
0x180011b41  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180011b49  jnz     loc_180011CE8
0x180011b4f  xor     ebx, ebx
0x180011b51  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180011b56  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180011b5f  lea     rax, [rsp+2F8h+hActCtx]
0x180011b64  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180011b69  lea     r9d, [rbx+1]; ulInfoClass
0x180011b6d  xor     r8d, r8d; pvSubInstance
0x180011b70  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180011b77  mov     ecx, 80000010h; dwFlags
0x180011b7c  call    cs:__imp_QueryActCtxW
0x180011b82  test    eax, eax
0x180011b84  jz      loc_180011CED
0x180011b8a  mov     rax, [rsp+2F8h+hActCtx]
0x180011b8f  test    rax, rax
0x180011b92  jnz     loc_180011C79
0x180011b98  xorps   xmm0, xmm0
0x180011b9b  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180011ba0  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180011ba5  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180011bad  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180011bb5  mov     [rsp+2F8h+phModule], rax
0x180011bba  lea     r8, [rsp+2F8h+phModule]; phModule
0x180011bbf  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180011bc6  lea     ecx, [rbx+6]; dwFlags
0x180011bc9  call    cs:__imp_GetModuleHandleExW
0x180011bcf  test    eax, eax
0x180011bd1  jz      loc_180011CED
0x180011bd7  mov     r8d, 105h; nSize
0x180011bdd  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180011be5  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180011bea  call    cs:__imp_GetModuleFileNameW
0x180011bf0  test    eax, eax
0x180011bf2  jz      loc_180011CED
0x180011bf8  cmp     eax, 105h
0x180011bfd  jb      short loc_180011C0D
0x180011bff  lea     ecx, [rbx+6Fh]; dwErrCode
0x180011c02  call    cs:__imp_SetLastError
0x180011c08  jmp     loc_180011CED
0x180011c0d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180011c15  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180011c1d  lea     rax, [rsp+2F8h+Filename]
0x180011c25  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180011c2a  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180011c36  mov     rax, [rsp+2F8h+phModule]
0x180011c3b  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180011c43  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180011c48  call    cs:__imp_CreateActCtxW
0x180011c4e  mov     [rsp+2F8h+hActCtx], rax
0x180011c53  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011c57  jnz     short loc_180011C79
0x180011c59  call    cs:__imp_GetLastError
0x180011c5f  lea     ecx, [rax-714h]
0x180011c65  cmp     ecx, 3
0x180011c68  jbe     short loc_180011C72
0x180011c6a  add     eax, 0FFFFFFFEh
0x180011c6d  cmp     eax, 1
0x180011c70  ja      short loc_180011CED
0x180011c72  xor     eax, eax
0x180011c74  mov     [rsp+2F8h+hActCtx], rax
0x180011c79  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180011c80  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180011c85  mov     rcx, rax; hActCtx
0x180011c88  call    cs:__imp_ActivateActCtx
0x180011c8e  test    eax, eax
0x180011c90  jz      short loc_180011CE8
0x180011c92  mov     ebx, 70h ; 'p'
0x180011c97  mov     r8d, ebx; Size
0x180011c9a  xor     edx, edx; Val
0x180011c9c  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180011ca1  call    memset_0
0x180011ca6  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180011caa  lea     rax, [rsp+2F8h+pActCtx]
0x180011caf  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180011cb4  lea     r9, LibFileName; "Comctl32.dll"
0x180011cbb  xor     edx, edx; lpExtensionGuid
0x180011cbd  lea     r8d, [rbx-6Eh]; ulSectionId
0x180011cc1  xor     ecx, ecx; dwFlags
0x180011cc3  call    cs:__imp_FindActCtxSectionStringW
0x180011cc9  test    eax, eax
0x180011ccb  jz      short loc_180011CDB
0x180011ccd  lea     rcx, LibFileName; "Comctl32.dll"
0x180011cd4  call    cs:__imp_LoadLibraryW
0x180011cda  nop
0x180011cdb  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180011ce0  xor     ecx, ecx; dwFlags
0x180011ce2  call    cs:__imp_DeactivateActCtx
0x180011ce8  mov     ebx, 1
0x180011ced  mov     eax, ebx
0x180011cef  mov     rcx, [rsp+2F8h+var_18]
0x180011cf7  xor     rcx, rsp; StackCookie
0x180011cfa  call    __security_check_cookie
0x180011cff  add     rsp, 2F0h
0x180011d06  pop     rbx
0x180011d07  retn
0x18001e4f5  push    rbp
0x18001e4f7  sub     rsp, 40h
0x18001e4fb  mov     rbp, rdx
0x18001e4fe  mov     rdx, [rbp+48h]; ulCookie
0x18001e502  xor     ecx, ecx; dwFlags
0x18001e504  call    cs:__imp_DeactivateActCtx
0x18001e50a  nop
0x18001e50b  add     rsp, 40h
0x18001e50f  pop     rbp
0x18001e510  retn
```
