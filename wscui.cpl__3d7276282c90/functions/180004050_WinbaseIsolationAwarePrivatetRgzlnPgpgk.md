# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180004050`
- end: `0x18000424f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180003fa8`

## callees

- `0x180004050`
- `0x18000a616`
- `0x18000a640`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000421b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000421b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800041a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000414a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000414a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004132`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004132`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004111`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x180004111`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800040c4`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800040c4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180004229`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000abf6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x180004229`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18000abf6`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800041cf`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800041cf`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000420a`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18000420a`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180004190`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x180004190`

## string_xrefs

- `0x1800041fb`: `Comctl32.dll`
- `0x180004214`: `Comctl32.dll`

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
0x180004050  push    rbx
0x180004052  sub     rsp, 2F0h
0x180004059  mov     rax, cs:__security_cookie
0x180004060  xor     rax, rsp
0x180004063  mov     [rsp+2F8h+var_18], rax
0x18000406b  xorps   xmm0, xmm0
0x18000406e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180004073  mov     [rsp+2F8h+Cookie], 0
0x18000407c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180004083  jnz     loc_18000422F
0x180004089  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180004091  jnz     loc_18000422F
0x180004097  xor     ebx, ebx
0x180004099  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000409e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800040a7  lea     rax, [rsp+2F8h+hActCtx]
0x1800040ac  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800040b1  lea     r9d, [rbx+1]; ulInfoClass
0x1800040b5  xor     r8d, r8d; pvSubInstance
0x1800040b8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800040bf  mov     ecx, 80000010h; dwFlags
0x1800040c4  call    cs:__imp_QueryActCtxW
0x1800040ca  test    eax, eax
0x1800040cc  jz      loc_180004234
0x1800040d2  mov     rax, [rsp+2F8h+hActCtx]
0x1800040d7  test    rax, rax
0x1800040da  jnz     loc_1800041C0
0x1800040e0  xorps   xmm0, xmm0
0x1800040e3  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800040e8  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800040ed  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800040f5  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800040fd  mov     [rsp+2F8h+phModule], rax
0x180004102  lea     r8, [rsp+2F8h+phModule]; phModule
0x180004107  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000410e  lea     ecx, [rbx+6]; dwFlags
0x180004111  call    cs:__imp_GetModuleHandleExW
0x180004117  test    eax, eax
0x180004119  jz      loc_180004234
0x18000411f  mov     r8d, 105h; nSize
0x180004125  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000412d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180004132  call    cs:__imp_GetModuleFileNameW
0x180004138  test    eax, eax
0x18000413a  jz      loc_180004234
0x180004140  cmp     eax, 105h
0x180004145  jb      short loc_180004155
0x180004147  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000414a  call    cs:__imp_SetLastError
0x180004150  jmp     loc_180004234
0x180004155  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000415d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180004165  lea     rax, [rsp+2F8h+Filename]
0x18000416d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180004172  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000417e  mov     rax, [rsp+2F8h+phModule]
0x180004183  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000418b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180004190  call    cs:__imp_CreateActCtxW
0x180004196  mov     [rsp+2F8h+hActCtx], rax
0x18000419b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000419f  jnz     short loc_1800041C0
0x1800041a1  call    cs:__imp_GetLastError
0x1800041a7  lea     ecx, [rax-2]
0x1800041aa  cmp     ecx, 1
0x1800041ad  jbe     short loc_1800041B9
0x1800041af  add     eax, 0FFFFF8ECh
0x1800041b4  cmp     eax, 3
0x1800041b7  ja      short loc_180004234
0x1800041b9  xor     eax, eax
0x1800041bb  mov     [rsp+2F8h+hActCtx], rax
0x1800041c0  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800041c7  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800041cc  mov     rcx, rax; hActCtx
0x1800041cf  call    cs:__imp_ActivateActCtx
0x1800041d5  test    eax, eax
0x1800041d7  jz      short loc_18000422F
0x1800041d9  mov     ebx, 70h ; 'p'
0x1800041de  mov     r8d, ebx; Size
0x1800041e1  xor     edx, edx; Val
0x1800041e3  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x1800041e8  call    memset_0
0x1800041ed  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x1800041f1  lea     rax, [rsp+2F8h+pActCtx]
0x1800041f6  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800041fb  lea     r9, LibFileName; "Comctl32.dll"
0x180004202  xor     edx, edx; lpExtensionGuid
0x180004204  lea     r8d, [rbx-6Eh]; ulSectionId
0x180004208  xor     ecx, ecx; dwFlags
0x18000420a  call    cs:__imp_FindActCtxSectionStringW
0x180004210  test    eax, eax
0x180004212  jz      short loc_180004222
0x180004214  lea     rcx, LibFileName; "Comctl32.dll"
0x18000421b  call    cs:__imp_LoadLibraryW
0x180004221  nop
0x180004222  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180004227  xor     ecx, ecx; dwFlags
0x180004229  call    cs:__imp_DeactivateActCtx
0x18000422f  mov     ebx, 1
0x180004234  mov     eax, ebx
0x180004236  mov     rcx, [rsp+2F8h+var_18]
0x18000423e  xor     rcx, rsp; StackCookie
0x180004241  call    __security_check_cookie
0x180004246  add     rsp, 2F0h
0x18000424d  pop     rbx
0x18000424e  retn
0x18000abe7  push    rbp
0x18000abe9  sub     rsp, 40h
0x18000abed  mov     rbp, rdx
0x18000abf0  mov     rdx, [rbp+48h]; ulCookie
0x18000abf4  xor     ecx, ecx; dwFlags
0x18000abf6  call    cs:__imp_DeactivateActCtx
0x18000abfc  nop
0x18000abfd  add     rsp, 40h
0x18000ac01  pop     rbp
0x18000ac02  retn
```
