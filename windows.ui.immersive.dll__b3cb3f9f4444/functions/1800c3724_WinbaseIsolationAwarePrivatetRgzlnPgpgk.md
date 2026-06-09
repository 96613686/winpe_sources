# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800c3724`
- end: `0x1800c3964`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `576`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c3614`

## callees

- `0x180054130`
- `0x180054ad4`
- `0x1800c3724`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800c3812`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800c3812`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800c37eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800c37eb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3830`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c3830`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c3893`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c3923`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800c3923`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800c387c`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800c387c`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800c3937`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800ec7b0`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800c3937`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800ec7b0`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x1800c390c`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x1800c390c`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800c3798`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800c3798`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800c38cb`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800c38cb`

## string_xrefs

- `0x1800c38fd`: `Comctl32.dll`
- `0x1800c391c`: `Comctl32.dll`

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
0x1800c3724  push    rbx
0x1800c3726  sub     rsp, 2F0h
0x1800c372d  mov     rax, cs:__security_cookie
0x1800c3734  xor     rax, rsp
0x1800c3737  mov     [rsp+2F8h+var_18], rax
0x1800c373f  xorps   xmm0, xmm0
0x1800c3742  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x1800c3747  mov     [rsp+2F8h+Cookie], 0
0x1800c3750  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800c3757  jnz     loc_1800C3943
0x1800c375d  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800c3765  jnz     loc_1800C3943
0x1800c376b  xor     ebx, ebx
0x1800c376d  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800c3772  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800c377b  lea     rax, [rsp+2F8h+hActCtx]
0x1800c3780  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800c3785  lea     r9d, [rbx+1]; ulInfoClass
0x1800c3789  xor     r8d, r8d; pvSubInstance
0x1800c378c  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800c3793  mov     ecx, 80000010h; dwFlags
0x1800c3798  call    cs:__imp_QueryActCtxW
0x1800c379f  nop     dword ptr [rax+rax+00h]
0x1800c37a4  test    eax, eax
0x1800c37a6  jz      loc_1800C3948
0x1800c37ac  mov     rax, [rsp+2F8h+hActCtx]
0x1800c37b1  test    rax, rax
0x1800c37b4  jnz     loc_1800C38BC
0x1800c37ba  xorps   xmm0, xmm0
0x1800c37bd  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800c37c2  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800c37c7  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800c37cf  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800c37d7  mov     [rsp+2F8h+phModule], rax
0x1800c37dc  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800c37e1  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800c37e8  lea     ecx, [rbx+6]; dwFlags
0x1800c37eb  call    cs:__imp_GetModuleHandleExW
0x1800c37f2  nop     dword ptr [rax+rax+00h]
0x1800c37f7  test    eax, eax
0x1800c37f9  jz      loc_1800C3948
0x1800c37ff  mov     r8d, 105h; nSize
0x1800c3805  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800c380d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800c3812  call    cs:__imp_GetModuleFileNameW
0x1800c3819  nop     dword ptr [rax+rax+00h]
0x1800c381e  test    eax, eax
0x1800c3820  jz      loc_1800C3948
0x1800c3826  cmp     eax, 105h
0x1800c382b  jb      short loc_1800C3841
0x1800c382d  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800c3830  call    cs:__imp_SetLastError
0x1800c3837  nop     dword ptr [rax+rax+00h]
0x1800c383c  jmp     loc_1800C3948
0x1800c3841  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x1800c3849  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800c3851  lea     rax, [rsp+2F8h+Filename]
0x1800c3859  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800c385e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800c386a  mov     rax, [rsp+2F8h+phModule]
0x1800c386f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800c3877  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800c387c  call    cs:__imp_CreateActCtxW
0x1800c3883  nop     dword ptr [rax+rax+00h]
0x1800c3888  mov     [rsp+2F8h+hActCtx], rax
0x1800c388d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800c3891  jnz     short loc_1800C38BC
0x1800c3893  call    cs:__imp_GetLastError
0x1800c389a  nop     dword ptr [rax+rax+00h]
0x1800c389f  lea     ecx, [rax-2]
0x1800c38a2  cmp     ecx, 1
0x1800c38a5  jbe     short loc_1800C38B5
0x1800c38a7  add     eax, 0FFFFF8ECh
0x1800c38ac  cmp     eax, 3
0x1800c38af  ja      loc_1800C3948
0x1800c38b5  xor     eax, eax
0x1800c38b7  mov     [rsp+2F8h+hActCtx], rax
0x1800c38bc  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800c38c3  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800c38c8  mov     rcx, rax; hActCtx
0x1800c38cb  call    cs:__imp_ActivateActCtx
0x1800c38d2  nop     dword ptr [rax+rax+00h]
0x1800c38d7  test    eax, eax
0x1800c38d9  jz      short loc_1800C3943
0x1800c38db  mov     ebx, 70h ; 'p'
0x1800c38e0  mov     r8d, ebx; Size
0x1800c38e3  xor     edx, edx; Val
0x1800c38e5  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x1800c38ea  call    memset_0
0x1800c38ef  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x1800c38f3  lea     rax, [rsp+2F8h+pActCtx]
0x1800c38f8  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800c38fd  lea     r9, StringToFind; "Comctl32.dll"
0x1800c3904  xor     edx, edx; lpExtensionGuid
0x1800c3906  lea     r8d, [rbx-6Eh]; ulSectionId
0x1800c390a  xor     ecx, ecx; dwFlags
0x1800c390c  call    cs:__imp_FindActCtxSectionStringW
0x1800c3913  nop     dword ptr [rax+rax+00h]
0x1800c3918  test    eax, eax
0x1800c391a  jz      short loc_1800C3930
0x1800c391c  lea     rcx, StringToFind; "Comctl32.dll"
0x1800c3923  call    cs:__imp_LoadLibraryW
0x1800c392a  nop     dword ptr [rax+rax+00h]
0x1800c392f  nop
0x1800c3930  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800c3935  xor     ecx, ecx; dwFlags
0x1800c3937  call    cs:__imp_DeactivateActCtx
0x1800c393e  nop     dword ptr [rax+rax+00h]
0x1800c3943  mov     ebx, 1
0x1800c3948  mov     eax, ebx
0x1800c394a  mov     rcx, [rsp+2F8h+var_18]
0x1800c3952  xor     rcx, rsp; StackCookie
0x1800c3955  call    __security_check_cookie
0x1800c395a  add     rsp, 2F0h
0x1800c3961  pop     rbx
0x1800c3962  retn
0x1800ec7a1  push    rbp
0x1800ec7a3  sub     rsp, 40h
0x1800ec7a7  mov     rbp, rdx
0x1800ec7aa  mov     rdx, [rbp+48h]; ulCookie
0x1800ec7ae  xor     ecx, ecx; dwFlags
0x1800ec7b0  call    cs:__imp_DeactivateActCtx
0x1800ec7b7  nop     dword ptr [rax+rax+00h]
0x1800ec7bc  nop
0x1800ec7bd  add     rsp, 40h
0x1800ec7c1  pop     rbp
0x1800ec7c2  retn
```
