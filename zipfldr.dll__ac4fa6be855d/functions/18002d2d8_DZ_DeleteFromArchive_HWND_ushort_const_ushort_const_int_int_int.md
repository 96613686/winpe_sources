# DZ_DeleteFromArchive(HWND__ *,ushort const *,ushort const *,int,int,int)

- ea: `0x18002d2d8`
- end: `0x18002d576`
- name: `?DZ_DeleteFromArchive@@YAJPEAUHWND__@@PEBG1HHH@Z`
- size: `670`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180029d2c`

## callees

- `0x180010c30`
- `0x18001ceb4`
- `0x18002840c`
- `0x18002d2d8`
- `0x180036f50`
- `0x180037390`
- `0x180037958`

## import_xrefs

- `SHELL32!SHChangeNotifySuspendResume` at `0x18002d359`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18002d51b`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18002d359`
- `SHELL32!SHChangeNotifySuspendResume` at `0x18002d51b`
- `SHELL32!SHParseDisplayName` at `0x18002d3f6`
- `SHELL32!SHParseDisplayName` at `0x18002d4d5`
- `SHELL32!SHParseDisplayName` at `0x18002d3f6`
- `SHELL32!SHParseDisplayName` at `0x18002d4d5`
- `SHELL32!SHChangeNotify` at `0x18002d4b0`
- `SHELL32!SHChangeNotify` at `0x18002d4ee`
- `SHELL32!SHChangeNotify` at `0x18002d52e`
- `SHELL32!SHChangeNotify` at `0x18002d4b0`
- `SHELL32!SHChangeNotify` at `0x18002d4ee`
- `SHELL32!SHChangeNotify` at `0x18002d52e`
- `SHELL32!__imp_ILFree` at `0x18002d4f9`
- `SHELL32!__imp_ILFree` at `0x18002d504`
- `SHELL32!__imp_ILFree` at `0x18002d537`
- `SHELL32!__imp_ILFree` at `0x18002d4f9`
- `SHELL32!__imp_ILFree` at `0x18002d504`
- `SHELL32!__imp_ILFree` at `0x18002d537`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18002d33e`
- `SHELL32!__imp_ILCreateFromPathW` at `0x18002d33e`
- `SHLWAPI!PathAppendW` at `0x18002d3d2`
- `SHLWAPI!PathAppendW` at `0x18002d3d2`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002d32d`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18002d32d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d541`
- `KERNEL32!lstrlenW` at `0x18002d39c`
- `KERNEL32!lstrlenW` at `0x18002d39c`

## pseudocode

```c
__int64 __fastcall DZ_DeleteFromArchive(HWND a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  ITEMIDLIST *v5; // rdi
  LPITEMIDLIST v6; // rax
  unsigned __int64 v7; // rcx
  int inited; // ebx
  int v9; // eax
  ITEMIDLIST *v10; // rcx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE Src[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+44h] [rbp-BCh]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h]
  WCHAR String[264]; // [rsp+8E0h] [rbp+7E0h] BYREF
  WCHAR pszPath[264]; // [rsp+AF0h] [rbp+9F0h] BYREF
  WCHAR pszName[264]; // [rsp+D00h] [rbp+C00h] BYREF

  StringCchCopyW(pszPath, 0x104u, a2);
  v5 = 0;
  if ( PathRemoveFileSpecW(pszPath) )
  {
    v6 = ILCreateFromPathW(pszPath);
    v5 = v6;
    if ( v6 )
      SHChangeNotifySuspendResume(1, v6, 1, 0);
  }
  ppidl = 0;
  if ( (int)StringCchCopyW(pszName, 0x104u, a2) >= 0 && (int)StringCchCopyW(String, 0x104u, a3 + 1) >= 0 )
  {
    v7 = 2LL * lstrlenW(String) - 2;
    if ( v7 >= 0x208 )
      _report_rangecheckfailure();
    *(WCHAR *)((char *)String + v7) = 0;
    if ( PathAppendW(pszName, String) )
      SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
  }
  memset_0(Src, 0, 0x89Cu);
  inited = InitZIPCMDSTRUCTOneRoot((struct ZIPCMDSTRUCT *)Src, a2, a3);
  if ( inited >= 0 )
  {
    v15 = 2;
    *((_DWORD *)hMem + 65) = 0;
    v9 = dzip(Src);
    inited = -2147467259;
    if ( v9 != 12 )
    {
      if ( !v9 )
      {
LABEL_21:
        inited = 0;
        goto LABEL_22;
      }
      if ( v9 == 4 )
      {
        inited = -2147024882;
      }
      else if ( v9 == 9 )
      {
        inited = -2147023673;
      }
      else
      {
        if ( v9 != 22 )
        {
          if ( v9 != 23 )
          {
            if ( v9 == 10219 )
              inited = -2147417803;
            goto LABEL_22;
          }
          goto LABEL_21;
        }
        inited = -2147024891;
      }
    }
LABEL_22:
    v10 = ppidl;
    if ( ppidl )
    {
      if ( inited >= 0 )
      {
        SHChangeNotify(4, 0, ppidl, 0);
        pidl = 0;
        if ( SHParseDisplayName(a2, 0, &pidl, 0, 0) >= 0 )
        {
          SHChangeNotify(0x2000, 0, pidl, 0);
          ILFree(pidl);
        }
        v10 = ppidl;
      }
      ILFree(v10);
    }
    if ( v5 )
    {
      SHChangeNotifySuspendResume(0, v5, 1, 0);
      SHChangeNotify(4096, 0, v5, 0);
      ILFree(v5);
    }
    LocalFree(hMem);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18002d2d8  mov     [rsp-8+arg_0], rbx
0x18002d2dd  mov     [rsp-8+arg_18], rsi
0x18002d2e2  push    rbp
0x18002d2e3  push    rdi
0x18002d2e4  push    r15
0x18002d2e6  lea     rbp, [rsp-0E20h]
0x18002d2ee  sub     rsp, 0F20h
0x18002d2f5  mov     rax, cs:__security_cookie
0x18002d2fc  xor     rax, rsp
0x18002d2ff  mov     [rbp+0E30h+var_20], rax
0x18002d306  mov     rbx, r8
0x18002d309  lea     rcx, [rbp+0E30h+pszPath]; unsigned __int16 *
0x18002d310  mov     r8, rdx; unsigned __int16 *
0x18002d313  mov     rsi, rdx
0x18002d316  mov     r15d, 104h
0x18002d31c  mov     edx, r15d; unsigned __int64
0x18002d31f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d324  lea     rcx, [rbp+0E30h+pszPath]; pszPath
0x18002d32b  xor     edi, edi
0x18002d32d  call    cs:__imp_PathRemoveFileSpecW
0x18002d333  test    eax, eax
0x18002d335  jz      short loc_18002D35F
0x18002d337  lea     rcx, [rbp+0E30h+pszPath]; pszPath
0x18002d33e  call    cs:__imp_ILCreateFromPathW
0x18002d344  mov     rdi, rax
0x18002d347  test    rax, rax
0x18002d34a  jz      short loc_18002D35F
0x18002d34c  xor     r9d, r9d
0x18002d34f  mov     rdx, rax
0x18002d352  lea     r8d, [r9+1]
0x18002d356  mov     ecx, r8d
0x18002d359  call    cs:__imp_SHChangeNotifySuspendResume
0x18002d35f  mov     r8, rsi; unsigned __int16 *
0x18002d362  mov     [rsp+0F30h+ppidl], 0
0x18002d36b  mov     rdx, r15; unsigned __int64
0x18002d36e  lea     rcx, [rbp+0E30h+pszName]; unsigned __int16 *
0x18002d375  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d37a  test    eax, eax
0x18002d37c  js      short loc_18002D3FC
0x18002d37e  lea     r8, [rbx+2]; unsigned __int16 *
0x18002d382  mov     rdx, r15; unsigned __int64
0x18002d385  lea     rcx, [rbp+0E30h+String]; unsigned __int16 *
0x18002d38c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002d391  test    eax, eax
0x18002d393  js      short loc_18002D3FC
0x18002d395  lea     rcx, [rbp+0E30h+String]; lpString
0x18002d39c  call    cs:__imp_lstrlenW
0x18002d3a2  movsxd  rcx, eax
0x18002d3a5  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18002d3ad  cmp     rcx, 208h
0x18002d3b4  jnb     loc_18002D570
0x18002d3ba  xor     eax, eax
0x18002d3bc  lea     rdx, [rbp+0E30h+String]; pszMore
0x18002d3c3  mov     [rbp+rcx+0E30h+String], ax
0x18002d3cb  lea     rcx, [rbp+0E30h+pszName]; pszPath
0x18002d3d2  call    cs:__imp_PathAppendW
0x18002d3d8  test    eax, eax
0x18002d3da  jz      short loc_18002D3FC
0x18002d3dc  xor     r9d, r9d; sfgaoIn
0x18002d3df  mov     [rsp+0F30h+psfgaoOut], 0; psfgaoOut
0x18002d3e8  lea     r8, [rsp+0F30h+ppidl]; ppidl
0x18002d3ed  xor     edx, edx; pbc
0x18002d3ef  lea     rcx, [rbp+0E30h+pszName]; pszName
0x18002d3f6  call    cs:__imp_SHParseDisplayName
0x18002d3fc  xor     edx, edx; Val
0x18002d3fe  lea     rcx, [rsp+0F30h+Src]; void *
0x18002d403  mov     r8d, 89Ch; Size
0x18002d409  call    memset_0
0x18002d40e  mov     r8, rbx; unsigned __int16 *
0x18002d411  lea     rcx, [rsp+0F30h+Src]; struct ZIPCMDSTRUCT *
0x18002d416  mov     rdx, rsi; unsigned __int16 *
0x18002d419  call    ?InitZIPCMDSTRUCTOneRoot@@YAJPEAUZIPCMDSTRUCT@@PEBG1@Z; InitZIPCMDSTRUCTOneRoot(ZIPCMDSTRUCT *,ushort const *,ushort const *)
0x18002d41e  mov     ebx, eax
0x18002d420  test    eax, eax
0x18002d422  js      loc_18002D547
0x18002d428  mov     rax, [rbp+0E30h+hMem]
0x18002d42c  lea     rcx, [rsp+0F30h+Src]; Src
0x18002d431  mov     [rsp+0F30h+var_EEC], 2
0x18002d439  mov     dword ptr [rax+104h], 0
0x18002d443  call    dzip
0x18002d448  mov     ecx, eax
0x18002d44a  mov     ebx, 80004005h
0x18002d44f  cmp     eax, 0Ch
0x18002d452  jz      short loc_18002D497
0x18002d454  test    eax, eax
0x18002d456  jz      short loc_18002D495
0x18002d458  sub     ecx, 4
0x18002d45b  jz      short loc_18002D48E
0x18002d45d  sub     ecx, 5
0x18002d460  jz      short loc_18002D487
0x18002d462  sub     ecx, 3
0x18002d465  jz      short loc_18002D495
0x18002d467  sub     ecx, 0Ah
0x18002d46a  jz      short loc_18002D480
0x18002d46c  sub     ecx, 1
0x18002d46f  jz      short loc_18002D495
0x18002d471  cmp     ecx, 27D4h
0x18002d477  jnz     short loc_18002D497
0x18002d479  mov     ebx, 80010135h
0x18002d47e  jmp     short loc_18002D497
0x18002d480  mov     ebx, 80070005h
0x18002d485  jmp     short loc_18002D497
0x18002d487  mov     ebx, 800704C7h
0x18002d48c  jmp     short loc_18002D497
0x18002d48e  mov     ebx, 8007000Eh
0x18002d493  jmp     short loc_18002D497
0x18002d495  xor     ebx, ebx
0x18002d497  mov     rcx, [rsp+0F30h+ppidl]
0x18002d49c  test    rcx, rcx
0x18002d49f  jz      short loc_18002D50A
0x18002d4a1  test    ebx, ebx
0x18002d4a3  js      short loc_18002D504
0x18002d4a5  xor     edx, edx; uFlags
0x18002d4a7  mov     r8, rcx; dwItem1
0x18002d4aa  xor     r9d, r9d; dwItem2
0x18002d4ad  lea     ecx, [rdx+4]; wEventId
0x18002d4b0  call    cs:__imp_SHChangeNotify
0x18002d4b6  xor     r9d, r9d; sfgaoIn
0x18002d4b9  mov     [rsp+0F30h+pidl], 0
0x18002d4c2  lea     r8, [rsp+0F30h+pidl]; ppidl
0x18002d4c7  mov     [rsp+0F30h+psfgaoOut], 0; psfgaoOut
0x18002d4d0  xor     edx, edx; pbc
0x18002d4d2  mov     rcx, rsi; pszName
0x18002d4d5  call    cs:__imp_SHParseDisplayName
0x18002d4db  test    eax, eax
0x18002d4dd  js      short loc_18002D4FF
0x18002d4df  mov     r8, [rsp+0F30h+pidl]; dwItem1
0x18002d4e4  xor     r9d, r9d; dwItem2
0x18002d4e7  xor     edx, edx; uFlags
0x18002d4e9  mov     ecx, 2000h; wEventId
0x18002d4ee  call    cs:__imp_SHChangeNotify
0x18002d4f4  mov     rcx, [rsp+0F30h+pidl]; pidl
0x18002d4f9  call    cs:__imp_ILFree
0x18002d4ff  mov     rcx, [rsp+0F30h+ppidl]; pidl
0x18002d504  call    cs:__imp_ILFree
0x18002d50a  test    rdi, rdi
0x18002d50d  jz      short loc_18002D53D
0x18002d50f  xor     r9d, r9d
0x18002d512  mov     rdx, rdi
0x18002d515  xor     ecx, ecx
0x18002d517  lea     r8d, [r9+1]
0x18002d51b  call    cs:__imp_SHChangeNotifySuspendResume
0x18002d521  xor     r9d, r9d; dwItem2
0x18002d524  mov     r8, rdi; dwItem1
0x18002d527  xor     edx, edx; uFlags
0x18002d529  mov     ecx, 1000h; wEventId
0x18002d52e  call    cs:__imp_SHChangeNotify
0x18002d534  mov     rcx, rdi; pidl
0x18002d537  call    cs:__imp_ILFree
0x18002d53d  mov     rcx, [rbp+0E30h+hMem]; hMem
0x18002d541  call    cs:__imp_LocalFree
0x18002d547  mov     eax, ebx
0x18002d549  mov     rcx, [rbp+0E30h+var_20]
0x18002d550  xor     rcx, rsp; StackCookie
0x18002d553  call    __security_check_cookie
0x18002d558  lea     r11, [rsp+0F30h+var_10]
0x18002d560  mov     rbx, [r11+20h]
0x18002d564  mov     rsi, [r11+38h]
0x18002d568  mov     rsp, r11
0x18002d56b  pop     r15
0x18002d56d  pop     rdi
0x18002d56e  pop     rbp
0x18002d56f  retn
0x18002d570  call    __report_rangecheckfailure
```
