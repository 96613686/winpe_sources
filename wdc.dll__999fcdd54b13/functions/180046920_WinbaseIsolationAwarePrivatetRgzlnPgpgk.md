# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180046920`
- end: `0x180046b1f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180046818`

## callees

- `0x18003a3c0`
- `0x18003b0ac`
- `0x180046920`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x180046994`
- `KERNEL32!QueryActCtxW` at `0x180046994`
- `KERNEL32!GetModuleFileNameW` at `0x180046a02`
- `KERNEL32!GetModuleFileNameW` at `0x180046a02`
- `KERNEL32!CreateActCtxW` at `0x180046a60`
- `KERNEL32!CreateActCtxW` at `0x180046a60`
- `KERNEL32!FindActCtxSectionStringW` at `0x180046ada`
- `KERNEL32!FindActCtxSectionStringW` at `0x180046ada`
- `KERNEL32!LoadLibraryW` at `0x180046aeb`
- `KERNEL32!LoadLibraryW` at `0x180046aeb`
- `KERNEL32!ActivateActCtx` at `0x180046a9f`
- `KERNEL32!ActivateActCtx` at `0x180046a9f`
- `KERNEL32!DeactivateActCtx` at `0x180046af9`
- `KERNEL32!DeactivateActCtx` at `0x18008510f`
- `KERNEL32!DeactivateActCtx` at `0x180046af9`
- `KERNEL32!DeactivateActCtx` at `0x18008510f`
- `KERNEL32!GetLastError` at `0x180046a71`
- `KERNEL32!GetLastError` at `0x180046a71`
- `KERNEL32!GetModuleHandleExW` at `0x1800469e1`
- `KERNEL32!GetModuleHandleExW` at `0x1800469e1`
- `KERNEL32!SetLastError` at `0x180046a1a`
- `KERNEL32!SetLastError` at `0x180046a1a`

## string_xrefs

- `0x180046acb`: `Comctl32.dll`
- `0x180046ae4`: `Comctl32.dll`

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
0x180046920  push    rbx
0x180046922  sub     rsp, 2F0h
0x180046929  mov     rax, cs:__security_cookie
0x180046930  xor     rax, rsp
0x180046933  mov     [rsp+2F8h+var_18], rax
0x18004693b  xorps   xmm0, xmm0
0x18004693e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180046943  mov     [rsp+2F8h+Cookie], 0
0x18004694c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180046953  jnz     loc_180046AFF
0x180046959  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180046961  jnz     loc_180046AFF
0x180046967  xor     ebx, ebx
0x180046969  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18004696e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180046977  lea     rax, [rsp+2F8h+hActCtx]
0x18004697c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180046981  lea     r9d, [rbx+1]; ulInfoClass
0x180046985  xor     r8d, r8d; pvSubInstance
0x180046988  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18004698f  mov     ecx, 80000010h; dwFlags
0x180046994  call    cs:__imp_QueryActCtxW
0x18004699a  test    eax, eax
0x18004699c  jz      loc_180046B04
0x1800469a2  mov     rax, [rsp+2F8h+hActCtx]
0x1800469a7  test    rax, rax
0x1800469aa  jnz     loc_180046A90
0x1800469b0  xorps   xmm0, xmm0
0x1800469b3  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800469b8  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800469bd  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800469c5  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800469cd  mov     [rsp+2F8h+phModule], rax
0x1800469d2  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800469d7  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800469de  lea     ecx, [rbx+6]; dwFlags
0x1800469e1  call    cs:__imp_GetModuleHandleExW
0x1800469e7  test    eax, eax
0x1800469e9  jz      loc_180046B04
0x1800469ef  mov     r8d, 105h; nSize
0x1800469f5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800469fd  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180046a02  call    cs:__imp_GetModuleFileNameW
0x180046a08  test    eax, eax
0x180046a0a  jz      loc_180046B04
0x180046a10  cmp     eax, 105h
0x180046a15  jb      short loc_180046A25
0x180046a17  lea     ecx, [rbx+6Fh]; dwErrCode
0x180046a1a  call    cs:__imp_SetLastError
0x180046a20  jmp     loc_180046B04
0x180046a25  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180046a2d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180046a35  lea     rax, [rsp+2F8h+Filename]
0x180046a3d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180046a42  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180046a4e  mov     rax, [rsp+2F8h+phModule]
0x180046a53  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180046a5b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180046a60  call    cs:__imp_CreateActCtxW
0x180046a66  mov     [rsp+2F8h+hActCtx], rax
0x180046a6b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046a6f  jnz     short loc_180046A90
0x180046a71  call    cs:__imp_GetLastError
0x180046a77  lea     ecx, [rax-2]
0x180046a7a  cmp     ecx, 1
0x180046a7d  jbe     short loc_180046A89
0x180046a7f  add     eax, 0FFFFF8ECh
0x180046a84  cmp     eax, 3
0x180046a87  ja      short loc_180046B04
0x180046a89  xor     eax, eax
0x180046a8b  mov     [rsp+2F8h+hActCtx], rax
0x180046a90  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180046a97  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180046a9c  mov     rcx, rax; hActCtx
0x180046a9f  call    cs:__imp_ActivateActCtx
0x180046aa5  test    eax, eax
0x180046aa7  jz      short loc_180046AFF
0x180046aa9  mov     ebx, 70h ; 'p'
0x180046aae  mov     r8d, ebx; Size
0x180046ab1  xor     edx, edx; Val
0x180046ab3  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180046ab8  call    memset_0
0x180046abd  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180046ac1  lea     rax, [rsp+2F8h+pActCtx]
0x180046ac6  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180046acb  lea     r9, LibFileName; "Comctl32.dll"
0x180046ad2  xor     edx, edx; lpExtensionGuid
0x180046ad4  lea     r8d, [rbx-6Eh]; ulSectionId
0x180046ad8  xor     ecx, ecx; dwFlags
0x180046ada  call    cs:__imp_FindActCtxSectionStringW
0x180046ae0  test    eax, eax
0x180046ae2  jz      short loc_180046AF2
0x180046ae4  lea     rcx, LibFileName; "Comctl32.dll"
0x180046aeb  call    cs:__imp_LoadLibraryW
0x180046af1  nop
0x180046af2  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180046af7  xor     ecx, ecx; dwFlags
0x180046af9  call    cs:__imp_DeactivateActCtx
0x180046aff  mov     ebx, 1
0x180046b04  mov     eax, ebx
0x180046b06  mov     rcx, [rsp+2F8h+var_18]
0x180046b0e  xor     rcx, rsp; StackCookie
0x180046b11  call    __security_check_cookie
0x180046b16  add     rsp, 2F0h
0x180046b1d  pop     rbx
0x180046b1e  retn
0x180085100  push    rbp
0x180085102  sub     rsp, 40h
0x180085106  mov     rbp, rdx
0x180085109  mov     rdx, [rbp+48h]; ulCookie
0x18008510d  xor     ecx, ecx; dwFlags
0x18008510f  call    cs:__imp_DeactivateActCtx
0x180085115  nop
0x180085116  add     rsp, 40h
0x18008511a  pop     rbp
0x18008511b  retn
```
