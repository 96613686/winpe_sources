# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000ca14`
- end: `0x18000cc13`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c6ec`

## callees

- `0x18000ca14`
- `0x18002d80e`
- `0x18002d840`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000cad5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000caf6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000caf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cb65`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cb0e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000cbdf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000cbdf`
- `KERNEL32!QueryActCtxW` at `0x18000ca88`
- `KERNEL32!QueryActCtxW` at `0x18000ca88`
- `KERNEL32!DeactivateActCtx` at `0x18000cbed`
- `KERNEL32!DeactivateActCtx` at `0x18002df1a`
- `KERNEL32!DeactivateActCtx` at `0x18000cbed`
- `KERNEL32!DeactivateActCtx` at `0x18002df1a`
- `KERNEL32!ActivateActCtx` at `0x18000cb93`
- `KERNEL32!ActivateActCtx` at `0x18000cb93`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000cbce`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000cbce`
- `KERNEL32!CreateActCtxW` at `0x18000cb54`
- `KERNEL32!CreateActCtxW` at `0x18000cb54`

## string_xrefs

- `0x18000cbbf`: `Comctl32.dll`
- `0x18000cbd8`: `Comctl32.dll`

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
0x18000ca14  push    rbx
0x18000ca16  sub     rsp, 2F0h
0x18000ca1d  mov     rax, cs:__security_cookie
0x18000ca24  xor     rax, rsp
0x18000ca27  mov     [rsp+2F8h+var_18], rax
0x18000ca2f  xorps   xmm0, xmm0
0x18000ca32  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000ca37  mov     [rsp+2F8h+Cookie], 0
0x18000ca40  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ca47  jnz     loc_18000CBF3
0x18000ca4d  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000ca55  jnz     loc_18000CBF3
0x18000ca5b  xor     ebx, ebx
0x18000ca5d  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000ca62  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000ca6b  lea     rax, [rsp+2F8h+hActCtx]
0x18000ca70  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000ca75  lea     r9d, [rbx+1]; ulInfoClass
0x18000ca79  xor     r8d, r8d; pvSubInstance
0x18000ca7c  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000ca83  mov     ecx, 80000010h; dwFlags
0x18000ca88  call    cs:__imp_QueryActCtxW
0x18000ca8e  test    eax, eax
0x18000ca90  jz      loc_18000CBF8
0x18000ca96  mov     rax, [rsp+2F8h+hActCtx]
0x18000ca9b  test    rax, rax
0x18000ca9e  jnz     loc_18000CB84
0x18000caa4  xorps   xmm0, xmm0
0x18000caa7  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000caac  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000cab1  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000cab9  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000cac1  mov     [rsp+2F8h+phModule], rax
0x18000cac6  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000cacb  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000cad2  lea     ecx, [rbx+6]; dwFlags
0x18000cad5  call    cs:__imp_GetModuleHandleExW
0x18000cadb  test    eax, eax
0x18000cadd  jz      loc_18000CBF8
0x18000cae3  mov     r8d, 105h; nSize
0x18000cae9  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000caf1  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000caf6  call    cs:__imp_GetModuleFileNameW
0x18000cafc  test    eax, eax
0x18000cafe  jz      loc_18000CBF8
0x18000cb04  cmp     eax, 105h
0x18000cb09  jb      short loc_18000CB19
0x18000cb0b  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000cb0e  call    cs:__imp_SetLastError
0x18000cb14  jmp     loc_18000CBF8
0x18000cb19  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000cb21  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000cb29  lea     rax, [rsp+2F8h+Filename]
0x18000cb31  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000cb36  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000cb42  mov     rax, [rsp+2F8h+phModule]
0x18000cb47  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000cb4f  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000cb54  call    cs:__imp_CreateActCtxW
0x18000cb5a  mov     [rsp+2F8h+hActCtx], rax
0x18000cb5f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000cb63  jnz     short loc_18000CB84
0x18000cb65  call    cs:__imp_GetLastError
0x18000cb6b  lea     ecx, [rax-2]
0x18000cb6e  cmp     ecx, 1
0x18000cb71  jbe     short loc_18000CB7D
0x18000cb73  add     eax, 0FFFFF8ECh
0x18000cb78  cmp     eax, 3
0x18000cb7b  ja      short loc_18000CBF8
0x18000cb7d  xor     eax, eax
0x18000cb7f  mov     [rsp+2F8h+hActCtx], rax
0x18000cb84  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000cb8b  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000cb90  mov     rcx, rax; hActCtx
0x18000cb93  call    cs:__imp_ActivateActCtx
0x18000cb99  test    eax, eax
0x18000cb9b  jz      short loc_18000CBF3
0x18000cb9d  mov     ebx, 70h ; 'p'
0x18000cba2  mov     r8d, ebx; Size
0x18000cba5  xor     edx, edx; Val
0x18000cba7  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000cbac  call    memset_0
0x18000cbb1  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000cbb5  lea     rax, [rsp+2F8h+pActCtx]
0x18000cbba  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000cbbf  lea     r9, LibFileName; "Comctl32.dll"
0x18000cbc6  xor     edx, edx; lpExtensionGuid
0x18000cbc8  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000cbcc  xor     ecx, ecx; dwFlags
0x18000cbce  call    cs:__imp_FindActCtxSectionStringW
0x18000cbd4  test    eax, eax
0x18000cbd6  jz      short loc_18000CBE6
0x18000cbd8  lea     rcx, LibFileName; "Comctl32.dll"
0x18000cbdf  call    cs:__imp_LoadLibraryW
0x18000cbe5  nop
0x18000cbe6  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000cbeb  xor     ecx, ecx; dwFlags
0x18000cbed  call    cs:__imp_DeactivateActCtx
0x18000cbf3  mov     ebx, 1
0x18000cbf8  mov     eax, ebx
0x18000cbfa  mov     rcx, [rsp+2F8h+var_18]
0x18000cc02  xor     rcx, rsp; StackCookie
0x18000cc05  call    __security_check_cookie
0x18000cc0a  add     rsp, 2F0h
0x18000cc11  pop     rbx
0x18000cc12  retn
0x18002df0b  push    rbp
0x18002df0d  sub     rsp, 40h
0x18002df11  mov     rbp, rdx
0x18002df14  mov     rdx, [rbp+48h]; ulCookie
0x18002df18  xor     ecx, ecx; dwFlags
0x18002df1a  call    cs:__imp_DeactivateActCtx
0x18002df20  nop
0x18002df21  add     rsp, 40h
0x18002df25  pop     rbp
0x18002df26  retn
```
