# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000d68c`
- end: `0x18000d88b`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d428`

## callees

- `0x180001820`
- `0x180002294`
- `0x18000d68c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d76e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000d76e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d74d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000d74d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d7dd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d786`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d857`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000d857`
- `KERNEL32!CreateActCtxW` at `0x18000d7cc`
- `KERNEL32!CreateActCtxW` at `0x18000d7cc`
- `KERNEL32!ActivateActCtx` at `0x18000d80b`
- `KERNEL32!ActivateActCtx` at `0x18000d80b`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000d846`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000d846`
- `KERNEL32!DeactivateActCtx` at `0x18000d865`
- `KERNEL32!DeactivateActCtx` at `0x18002fa6b`
- `KERNEL32!DeactivateActCtx` at `0x18000d865`
- `KERNEL32!DeactivateActCtx` at `0x18002fa6b`
- `KERNEL32!QueryActCtxW` at `0x18000d700`
- `KERNEL32!QueryActCtxW` at `0x18000d700`

## string_xrefs

- `0x18000d837`: `Comctl32.dll`
- `0x18000d850`: `Comctl32.dll`

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
0x18000d68c  push    rbx
0x18000d68e  sub     rsp, 2F0h
0x18000d695  mov     rax, cs:__security_cookie
0x18000d69c  xor     rax, rsp
0x18000d69f  mov     [rsp+2F8h+var_18], rax
0x18000d6a7  xorps   xmm0, xmm0
0x18000d6aa  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000d6af  mov     [rsp+2F8h+Cookie], 0
0x18000d6b8  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000d6bf  jnz     loc_18000D86B
0x18000d6c5  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000d6cd  jnz     loc_18000D86B
0x18000d6d3  xor     ebx, ebx
0x18000d6d5  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000d6da  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000d6e3  lea     rax, [rsp+2F8h+hActCtx]
0x18000d6e8  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000d6ed  lea     r9d, [rbx+1]; ulInfoClass
0x18000d6f1  xor     r8d, r8d; pvSubInstance
0x18000d6f4  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000d6fb  mov     ecx, 80000010h; dwFlags
0x18000d700  call    cs:__imp_QueryActCtxW
0x18000d706  test    eax, eax
0x18000d708  jz      loc_18000D870
0x18000d70e  mov     rax, [rsp+2F8h+hActCtx]
0x18000d713  test    rax, rax
0x18000d716  jnz     loc_18000D7FC
0x18000d71c  xorps   xmm0, xmm0
0x18000d71f  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000d724  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000d729  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000d731  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000d739  mov     [rsp+2F8h+phModule], rax
0x18000d73e  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000d743  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000d74a  lea     ecx, [rbx+6]; dwFlags
0x18000d74d  call    cs:__imp_GetModuleHandleExW
0x18000d753  test    eax, eax
0x18000d755  jz      loc_18000D870
0x18000d75b  mov     r8d, 105h; nSize
0x18000d761  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000d769  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000d76e  call    cs:__imp_GetModuleFileNameW
0x18000d774  test    eax, eax
0x18000d776  jz      loc_18000D870
0x18000d77c  cmp     eax, 105h
0x18000d781  jb      short loc_18000D791
0x18000d783  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000d786  call    cs:__imp_SetLastError
0x18000d78c  jmp     loc_18000D870
0x18000d791  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000d799  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000d7a1  lea     rax, [rsp+2F8h+Filename]
0x18000d7a9  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000d7ae  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000d7ba  mov     rax, [rsp+2F8h+phModule]
0x18000d7bf  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000d7c7  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000d7cc  call    cs:__imp_CreateActCtxW
0x18000d7d2  mov     [rsp+2F8h+hActCtx], rax
0x18000d7d7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000d7db  jnz     short loc_18000D7FC
0x18000d7dd  call    cs:__imp_GetLastError
0x18000d7e3  lea     ecx, [rax-2]
0x18000d7e6  cmp     ecx, 1
0x18000d7e9  jbe     short loc_18000D7F5
0x18000d7eb  add     eax, 0FFFFF8ECh
0x18000d7f0  cmp     eax, 3
0x18000d7f3  ja      short loc_18000D870
0x18000d7f5  xor     eax, eax
0x18000d7f7  mov     [rsp+2F8h+hActCtx], rax
0x18000d7fc  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000d803  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000d808  mov     rcx, rax; hActCtx
0x18000d80b  call    cs:__imp_ActivateActCtx
0x18000d811  test    eax, eax
0x18000d813  jz      short loc_18000D86B
0x18000d815  mov     ebx, 70h ; 'p'
0x18000d81a  mov     r8d, ebx; Size
0x18000d81d  xor     edx, edx; Val
0x18000d81f  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000d824  call    memset_0
0x18000d829  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000d82d  lea     rax, [rsp+2F8h+pActCtx]
0x18000d832  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000d837  lea     r9, LibFileName; "Comctl32.dll"
0x18000d83e  xor     edx, edx; lpExtensionGuid
0x18000d840  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000d844  xor     ecx, ecx; dwFlags
0x18000d846  call    cs:__imp_FindActCtxSectionStringW
0x18000d84c  test    eax, eax
0x18000d84e  jz      short loc_18000D85E
0x18000d850  lea     rcx, LibFileName; "Comctl32.dll"
0x18000d857  call    cs:__imp_LoadLibraryW
0x18000d85d  nop
0x18000d85e  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000d863  xor     ecx, ecx; dwFlags
0x18000d865  call    cs:__imp_DeactivateActCtx
0x18000d86b  mov     ebx, 1
0x18000d870  mov     eax, ebx
0x18000d872  mov     rcx, [rsp+2F8h+var_18]
0x18000d87a  xor     rcx, rsp; StackCookie
0x18000d87d  call    __security_check_cookie
0x18000d882  add     rsp, 2F0h
0x18000d889  pop     rbx
0x18000d88a  retn
0x18002fa5c  push    rbp
0x18002fa5e  sub     rsp, 40h
0x18002fa62  mov     rbp, rdx
0x18002fa65  mov     rdx, [rbp+48h]; ulCookie
0x18002fa69  xor     ecx, ecx; dwFlags
0x18002fa6b  call    cs:__imp_DeactivateActCtx
0x18002fa71  nop
0x18002fa72  add     rsp, 40h
0x18002fa76  pop     rbp
0x18002fa77  retn
```
