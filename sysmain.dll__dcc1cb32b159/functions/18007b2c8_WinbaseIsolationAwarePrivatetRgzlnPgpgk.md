# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18007b2c8`
- end: `0x18007b4c7`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18007b190`

## callees

- `0x18007b2c8`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b3c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007b3c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b419`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007b419`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007b3aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18007b3aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007b389`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18007b389`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b493`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18007b493`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18007b408`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18007b408`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18007b447`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18007b447`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18007b33c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18007b33c`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18007b482`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18007b482`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18007b4a1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800b69a4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18007b4a1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800b69a4`

## string_xrefs

- `0x18007b473`: `Comctl32.dll`
- `0x18007b48c`: `Comctl32.dll`

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
0x18007b2c8  push    rbx
0x18007b2ca  sub     rsp, 2F0h
0x18007b2d1  mov     rax, cs:__security_cookie
0x18007b2d8  xor     rax, rsp
0x18007b2db  mov     [rsp+2F8h+var_18], rax
0x18007b2e3  xorps   xmm0, xmm0
0x18007b2e6  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18007b2eb  mov     [rsp+2F8h+Cookie], 0
0x18007b2f4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18007b2fb  jnz     loc_18007B4A7
0x18007b301  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18007b309  jnz     loc_18007B4A7
0x18007b30f  xor     ebx, ebx
0x18007b311  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18007b316  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18007b31f  lea     rax, [rsp+2F8h+hActCtx]
0x18007b324  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18007b329  lea     r9d, [rbx+1]; ulInfoClass
0x18007b32d  xor     r8d, r8d; pvSubInstance
0x18007b330  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18007b337  mov     ecx, 80000010h; dwFlags
0x18007b33c  call    cs:__imp_QueryActCtxW
0x18007b342  test    eax, eax
0x18007b344  jz      loc_18007B4AC
0x18007b34a  mov     rax, [rsp+2F8h+hActCtx]
0x18007b34f  test    rax, rax
0x18007b352  jnz     loc_18007B438
0x18007b358  xorps   xmm0, xmm0
0x18007b35b  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18007b360  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18007b365  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18007b36d  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18007b375  mov     [rsp+2F8h+phModule], rax
0x18007b37a  lea     r8, [rsp+2F8h+phModule]; phModule
0x18007b37f  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18007b386  lea     ecx, [rbx+6]; dwFlags
0x18007b389  call    cs:__imp_GetModuleHandleExW
0x18007b38f  test    eax, eax
0x18007b391  jz      loc_18007B4AC
0x18007b397  mov     r8d, 105h; nSize
0x18007b39d  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18007b3a5  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18007b3aa  call    cs:__imp_GetModuleFileNameW
0x18007b3b0  test    eax, eax
0x18007b3b2  jz      loc_18007B4AC
0x18007b3b8  cmp     eax, 105h
0x18007b3bd  jb      short loc_18007B3CD
0x18007b3bf  lea     ecx, [rbx+6Fh]; dwErrCode
0x18007b3c2  call    cs:__imp_SetLastError
0x18007b3c8  jmp     loc_18007B4AC
0x18007b3cd  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18007b3d5  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18007b3dd  lea     rax, [rsp+2F8h+Filename]
0x18007b3e5  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18007b3ea  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18007b3f6  mov     rax, [rsp+2F8h+phModule]
0x18007b3fb  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18007b403  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18007b408  call    cs:__imp_CreateActCtxW
0x18007b40e  mov     [rsp+2F8h+hActCtx], rax
0x18007b413  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b417  jnz     short loc_18007B438
0x18007b419  call    cs:__imp_GetLastError
0x18007b41f  lea     ecx, [rax-2]
0x18007b422  cmp     ecx, 1
0x18007b425  jbe     short loc_18007B431
0x18007b427  add     eax, 0FFFFF8ECh
0x18007b42c  cmp     eax, 3
0x18007b42f  ja      short loc_18007B4AC
0x18007b431  xor     eax, eax
0x18007b433  mov     [rsp+2F8h+hActCtx], rax
0x18007b438  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18007b43f  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18007b444  mov     rcx, rax; hActCtx
0x18007b447  call    cs:__imp_ActivateActCtx
0x18007b44d  test    eax, eax
0x18007b44f  jz      short loc_18007B4A7
0x18007b451  mov     ebx, 70h ; 'p'
0x18007b456  mov     r8d, ebx; Size
0x18007b459  xor     edx, edx; Val
0x18007b45b  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18007b460  call    memset_0
0x18007b465  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18007b469  lea     rax, [rsp+2F8h+pActCtx]
0x18007b46e  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18007b473  lea     r9, StringToFind; "Comctl32.dll"
0x18007b47a  xor     edx, edx; lpExtensionGuid
0x18007b47c  lea     r8d, [rbx-6Eh]; ulSectionId
0x18007b480  xor     ecx, ecx; dwFlags
0x18007b482  call    cs:__imp_FindActCtxSectionStringW
0x18007b488  test    eax, eax
0x18007b48a  jz      short loc_18007B49A
0x18007b48c  lea     rcx, StringToFind; "Comctl32.dll"
0x18007b493  call    cs:__imp_LoadLibraryW
0x18007b499  nop
0x18007b49a  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18007b49f  xor     ecx, ecx; dwFlags
0x18007b4a1  call    cs:__imp_DeactivateActCtx
0x18007b4a7  mov     ebx, 1
0x18007b4ac  mov     eax, ebx
0x18007b4ae  mov     rcx, [rsp+2F8h+var_18]
0x18007b4b6  xor     rcx, rsp; StackCookie
0x18007b4b9  call    __security_check_cookie
0x18007b4be  add     rsp, 2F0h
0x18007b4c5  pop     rbx
0x18007b4c6  retn
0x1800b6995  push    rbp
0x1800b6997  sub     rsp, 40h
0x1800b699b  mov     rbp, rdx
0x1800b699e  mov     rdx, [rbp+48h]; ulCookie
0x1800b69a2  xor     ecx, ecx; dwFlags
0x1800b69a4  call    cs:__imp_DeactivateActCtx
0x1800b69aa  nop
0x1800b69ab  add     rsp, 40h
0x1800b69af  pop     rbp
0x1800b69b0  retn
```
