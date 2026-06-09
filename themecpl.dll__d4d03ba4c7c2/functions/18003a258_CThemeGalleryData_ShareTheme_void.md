# CThemeGalleryData::_ShareTheme(void)

- ea: `0x18003a258`
- end: `0x18003a4d8`
- name: `?_ShareTheme@CThemeGalleryData@@AEAAJXZ`
- size: `640`
- prototype: `__int64 __fastcall(CThemeGalleryData *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180039f80`

## callees

- `0x180002280`
- `0x180002f34`
- `0x18003a258`
- `0x18004fddc`
- `0x1800551a0`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x18003a32d`
- `SHELL32!SHGetFolderPathEx` at `0x18003a32d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a296`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a40b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a43a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a296`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a40b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18003a43a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003a486`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003a486`
- `USER32!MessageBoxW` at `0x18003a4a6`
- `USER32!MessageBoxW` at `0x18003a4a6`

## pseudocode

```c
__int64 __fastcall CThemeGalleryData::_ShareTheme(CThemeGalleryData *this)
{
  __int64 v2; // r8
  int v3; // ebx
  __int64 v4; // rcx
  _WORD *v5; // rdx
  __int64 i; // r8
  va_list Arguments; // [rsp+40h] [rbp-C0h] BYREF
  tagOFNW v9; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[64]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v11[256]; // [rsp+170h] [rbp+70h] BYREF
  _WORD v12[264]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v13[528]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Source[520]; // [rsp+690h] [rbp+590h] BYREF
  WCHAR Text[520]; // [rsp+AA0h] [rbp+9A0h] BYREF

  if ( LoadStringW(g_hinst, 0xDu, Buffer, 64) )
  {
    v3 = ResourceStringCopyEx(g_hinst, 14, v2, v11, 127);
    if ( v3 >= 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( *(_WORD *)&v11[2 * v4] );
      v5 = v11;
      for ( i = v4; i; --i )
      {
        if ( !*v5 )
          break;
        if ( *v5 == 124 )
          *v5 = 0;
        ++v5;
      }
      *(_WORD *)&v11[2 * v4 + 2] = 0;
      v3 = SHGetFolderPathEx(&FOLDERID_Documents, 0, 0, v13, 260);
      if ( v3 >= 0 )
      {
        memset_0(&v9, 0, sizeof(v9));
        v9.hInstance = g_hinst;
        v9.lpstrTitle = Buffer;
        v9.lpstrFilter = (LPCWSTR)v11;
        v9.lpstrInitialDir = (LPCWSTR)v13;
        v9.lpstrFile = v12;
        v9.lpstrDefExt = L"deskthemepack";
        v12[0] = 0;
        v9.lStructSize = 152;
        v9.hwndOwner = 0;
        v9.nFilterIndex = 1;
        v9.nMaxFile = 260;
        v9.Flags = 526342;
        if ( GetSaveFileNameW(&v9) )
        {
          v3 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _WORD *, _QWORD))(**((_QWORD **)this + 2) + 120LL))(
                 *((_QWORD *)this + 2),
                 0,
                 v12,
                 0);
          if ( v3 < 0 )
          {
            if ( LoadStringW(g_hinst, 0xFu, Buffer, 64) )
            {
              if ( LoadStringW(g_hinst, 0x10u, Source, 520) )
              {
                Arguments = (va_list)v12;
                if ( FormatMessageW(0x2400u, Source, 0, 0, Text, 0x208u, &Arguments) )
                  MessageBoxW(0, Text, Buffer, 0x10u);
              }
            }
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a258  push    rbp
0x18003a25a  push    rbx
0x18003a25b  push    rdi
0x18003a25c  push    r14
0x18003a25e  lea     rbp, [rsp-0DC8h]
0x18003a266  sub     rsp, 0EC8h
0x18003a26d  mov     rax, cs:__security_cookie
0x18003a274  xor     rax, rsp
0x18003a277  mov     [rbp+0DE0h+var_30], rax
0x18003a27e  mov     r9d, 40h ; '@'; cchBufferMax
0x18003a284  lea     r8, [rbp+0DE0h+Buffer]; lpBuffer
0x18003a288  mov     rdi, rcx
0x18003a28b  mov     rcx, cs:g_hinst; hInstance
0x18003a292  lea     edx, [r9-33h]; uID
0x18003a296  call    cs:__imp_LoadStringW
0x18003a29d  nop     dword ptr [rax+rax+00h]
0x18003a2a2  xor     r14d, r14d
0x18003a2a5  test    eax, eax
0x18003a2a7  jz      loc_18003A4B4
0x18003a2ad  mov     rcx, cs:g_hinst
0x18003a2b4  lea     r9, [rbp+0DE0h+var_D70]
0x18003a2b8  lea     edx, [r14+0Eh]
0x18003a2bc  mov     [rsp+0EE0h+lpBuffer], 7Fh
0x18003a2c5  call    _ResourceStringCopyEx
0x18003a2ca  mov     ebx, eax
0x18003a2cc  test    eax, eax
0x18003a2ce  js      loc_18003A4B9
0x18003a2d4  lea     rax, [rbp+0DE0h+var_D70]
0x18003a2d8  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18003a2dc  inc     rcx
0x18003a2df  cmp     [rax+rcx*2], r14w
0x18003a2e4  jnz     short loc_18003A2DC
0x18003a2e6  lea     rdx, [rbp+0DE0h+var_D70]
0x18003a2ea  mov     r8, rcx
0x18003a2ed  test    rcx, rcx
0x18003a2f0  jz      short loc_18003A30C
0x18003a2f2  cmp     [rdx], r14w
0x18003a2f6  jz      short loc_18003A30C
0x18003a2f8  cmp     word ptr [rdx], 7Ch ; '|'
0x18003a2fc  jnz     short loc_18003A302
0x18003a2fe  mov     [rdx], r14w
0x18003a302  add     rdx, 2
0x18003a306  sub     r8, 1
0x18003a30a  jnz     short loc_18003A2F2
0x18003a30c  mov     [rbp+rcx*2+0DE0h+var_D6E], r14w
0x18003a312  lea     r9, [rbp+0DE0h+var_A60]
0x18003a319  lea     rcx, FOLDERID_Documents
0x18003a320  mov     dword ptr [rsp+0EE0h+lpBuffer], 104h
0x18003a328  xor     r8d, r8d
0x18003a32b  xor     edx, edx
0x18003a32d  call    cs:__imp_SHGetFolderPathEx
0x18003a334  nop     dword ptr [rax+rax+00h]
0x18003a339  mov     ebx, eax
0x18003a33b  test    eax, eax
0x18003a33d  js      loc_18003A4B9
0x18003a343  xor     edx, edx; Val
0x18003a345  lea     rcx, [rsp+0EE0h+var_E90]; void *
0x18003a34a  mov     r8d, 98h; Size
0x18003a350  call    memset_0
0x18003a355  mov     rax, cs:g_hinst
0x18003a35c  lea     rcx, [rsp+0EE0h+var_E90]; LPOPENFILENAMEW
0x18003a361  mov     [rsp+0EE0h+var_E90.hInstance], rax
0x18003a366  lea     rax, [rbp+0DE0h+Buffer]
0x18003a36a  mov     [rbp+0DE0h+var_E90.lpstrTitle], rax
0x18003a36e  lea     rax, [rbp+0DE0h+var_D70]
0x18003a372  mov     [rsp+0EE0h+var_E90.lpstrFilter], rax
0x18003a377  lea     rax, [rbp+0DE0h+var_A60]
0x18003a37e  mov     [rbp+0DE0h+var_E90.lpstrInitialDir], rax
0x18003a382  lea     rax, [rbp+0DE0h+var_C70]
0x18003a389  mov     [rbp+0DE0h+var_E90.lpstrFile], rax
0x18003a38d  lea     rax, aDeskthemepack; "deskthemepack"
0x18003a394  mov     [rbp+0DE0h+var_E90.lpstrDefExt], rax
0x18003a398  mov     [rbp+0DE0h+var_C70], r14w
0x18003a3a0  mov     [rsp+0EE0h+var_E90.lStructSize], 98h
0x18003a3a8  mov     [rsp+0EE0h+var_E90.hwndOwner], r14
0x18003a3ad  mov     [rsp+0EE0h+var_E90.nFilterIndex], 1
0x18003a3b5  mov     [rbp+0DE0h+var_E90.nMaxFile], 104h
0x18003a3bc  mov     [rbp+0DE0h+var_E90.Flags], 80806h
0x18003a3c3  call    GetSaveFileNameW
0x18003a3c8  test    eax, eax
0x18003a3ca  jz      loc_18003A4B9
0x18003a3d0  mov     rcx, [rdi+10h]
0x18003a3d4  lea     r8, [rbp+0DE0h+var_C70]
0x18003a3db  xor     r9d, r9d
0x18003a3de  xor     edx, edx
0x18003a3e0  mov     rax, [rcx]
0x18003a3e3  mov     rax, [rax+78h]
0x18003a3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3ec  mov     ebx, eax
0x18003a3ee  test    eax, eax
0x18003a3f0  jns     loc_18003A4B9
0x18003a3f6  mov     rcx, cs:g_hinst; hInstance
0x18003a3fd  lea     r8, [rbp+0DE0h+Buffer]; lpBuffer
0x18003a401  mov     r9d, 40h ; '@'; cchBufferMax
0x18003a407  lea     edx, [r9-31h]; uID
0x18003a40b  call    cs:__imp_LoadStringW
0x18003a412  nop     dword ptr [rax+rax+00h]
0x18003a417  test    eax, eax
0x18003a419  jz      loc_18003A4B9
0x18003a41f  mov     rcx, cs:g_hinst; hInstance
0x18003a426  lea     r8, [rbp+0DE0h+Source]; lpBuffer
0x18003a42d  mov     edi, 10h
0x18003a432  mov     r9d, 208h; cchBufferMax
0x18003a438  mov     edx, edi; uID
0x18003a43a  call    cs:__imp_LoadStringW
0x18003a441  nop     dword ptr [rax+rax+00h]
0x18003a446  test    eax, eax
0x18003a448  jz      short loc_18003A4B9
0x18003a44a  lea     rax, [rbp+0DE0h+var_C70]
0x18003a451  xor     r9d, r9d; dwLanguageId
0x18003a454  mov     [rsp+0EE0h+var_EA0], rax
0x18003a459  lea     rdx, [rbp+0DE0h+Source]; lpSource
0x18003a460  lea     rax, [rsp+0EE0h+var_EA0]
0x18003a465  xor     r8d, r8d; dwMessageId
0x18003a468  mov     [rsp+0EE0h+Arguments], rax; Arguments
0x18003a46d  mov     ecx, 2400h; dwFlags
0x18003a472  lea     rax, [rbp+0DE0h+Text]
0x18003a479  mov     [rsp+0EE0h+nSize], 208h; nSize
0x18003a481  mov     [rsp+0EE0h+lpBuffer], rax; lpBuffer
0x18003a486  call    cs:__imp_FormatMessageW
0x18003a48d  nop     dword ptr [rax+rax+00h]
0x18003a492  test    eax, eax
0x18003a494  jz      short loc_18003A4B9
0x18003a496  mov     r9d, edi; uType
0x18003a499  lea     r8, [rbp+0DE0h+Buffer]; lpCaption
0x18003a49d  lea     rdx, [rbp+0DE0h+Text]; lpText
0x18003a4a4  xor     ecx, ecx; hWnd
0x18003a4a6  call    cs:__imp_MessageBoxW
0x18003a4ad  nop     dword ptr [rax+rax+00h]
0x18003a4b2  jmp     short loc_18003A4B9
0x18003a4b4  mov     ebx, 80004005h
0x18003a4b9  mov     eax, ebx
0x18003a4bb  mov     rcx, [rbp+0DE0h+var_30]
0x18003a4c2  xor     rcx, rsp; StackCookie
0x18003a4c5  call    __security_check_cookie
0x18003a4ca  add     rsp, 0EC8h
0x18003a4d1  pop     r14
0x18003a4d3  pop     rdi
0x18003a4d4  pop     rbx
0x18003a4d5  pop     rbp
0x18003a4d6  retn
```
