# CInternetTimeReadOnly::_InitAdvancedPage(void)

- ea: `0x1800178b0`
- end: `0x1800179f3`
- name: `?_InitAdvancedPage@CInternetTimeReadOnly@@AEAAJXZ`
- size: `323`
- prototype: `__int64 __fastcall(CInternetTimeReadOnly *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180017730`

## callees

- `0x1800089c8`
- `0x1800168c8`
- `0x1800178b0`
- `0x1800179fc`
- `0x18001b618`
- `0x180028f60`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017949`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017992`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017949`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180017992`
- `USER32!SetWindowTextW` at `0x1800179ca`
- `USER32!SetWindowTextW` at `0x1800179ca`
- `USER32!GetDlgItem` at `0x1800179bc`
- `USER32!GetDlgItem` at `0x1800179bc`

## pseudocode

```c
__int64 __fastcall CInternetTimeReadOnly::_InitAdvancedPage(HWND *this)
{
  signed int v2; // ebx
  int v3; // ecx
  __int64 v4; // r8
  HWND DlgItem; // rax
  WCHAR String[256]; // [rsp+20h] [rbp-618h] BYREF
  WCHAR Buffer[256]; // [rsp+220h] [rbp-418h] BYREF
  unsigned __int16 v9[256]; // [rsp+420h] [rbp-218h] BYREF

  if ( **((_DWORD **)g_pom + 61) )
  {
    v2 = CDateTimeOm::CheckInternetTimeStatus(g_pom);
    if ( v2 < 0 )
      return (unsigned int)v2;
    v2 = -2147467259;
    v3 = -2147467259;
    v4 = *((_QWORD *)g_pom + 61);
    if ( *(_DWORD *)v4 && (v3 = StringCchCopyW(v9, 0x100u, (size_t *)(v4 + 4)), v3 >= 0) )
    {
      if ( !LoadStringW(g_hInst, 0x201u, Buffer, 255) )
        return (unsigned int)v2;
      v2 = FormatMessageWedge(Buffer, String, 0xFFu, v9);
    }
    else
    {
      v2 = v3;
    }
  }
  else
  {
    v2 = LoadStringW(g_hInst, 0x202u, String, 255) == 0 ? 0x80004005 : 0;
    CInternetTimeReadOnly::_OnUpdateStatusString((CInternetTimeReadOnly *)this, 0);
  }
  if ( v2 >= 0 )
  {
    DlgItem = GetDlgItem(this[2], 820);
    SetWindowTextW(DlgItem, String);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800178b0  mov     [rsp+arg_8], rbx
0x1800178b5  push    rdi
0x1800178b6  sub     rsp, 630h
0x1800178bd  mov     rax, cs:__security_cookie
0x1800178c4  xor     rax, rsp
0x1800178c7  mov     [rsp+638h+var_18], rax
0x1800178cf  mov     rdi, rcx
0x1800178d2  mov     rcx, cs:?g_pom@@3PEAVCDateTimeOm@@EA; this
0x1800178d9  mov     rax, [rcx+1E8h]
0x1800178e0  cmp     dword ptr [rax], 0
0x1800178e3  jz      loc_18001797B
0x1800178e9  call    ?CheckInternetTimeStatus@CDateTimeOm@@QEAAJXZ; CDateTimeOm::CheckInternetTimeStatus(void)
0x1800178ee  mov     ebx, eax
0x1800178f0  test    eax, eax
0x1800178f2  js      loc_1800179D0
0x1800178f8  mov     rax, cs:?g_pom@@3PEAVCDateTimeOm@@EA; CDateTimeOm * g_pom
0x1800178ff  mov     ebx, 80004005h
0x180017904  mov     ecx, ebx
0x180017906  mov     r8, [rax+1E8h]
0x18001790d  cmp     dword ptr [r8], 0
0x180017911  jz      short loc_180017977
0x180017913  add     r8, 4; unsigned __int16 *
0x180017917  lea     rcx, [rsp+638h+var_218]; unsigned __int16 *
0x18001791f  mov     edx, 100h; unsigned __int64
0x180017924  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017929  mov     ecx, eax
0x18001792b  test    eax, eax
0x18001792d  js      short loc_180017977
0x18001792f  mov     rcx, cs:g_hInst; hInstance
0x180017936  lea     r8, [rsp+638h+Buffer]; lpBuffer
0x18001793e  mov     r9d, 0FFh; cchBufferMax
0x180017944  mov     edx, 201h; uID
0x180017949  call    cs:__imp_LoadStringW
0x18001794f  test    eax, eax
0x180017951  jz      short loc_1800179D0
0x180017953  lea     r9, [rsp+638h+var_218]
0x18001795b  mov     r8d, 0FFh; unsigned int
0x180017961  lea     rdx, [rsp+638h+String]; unsigned __int16 *
0x180017966  lea     rcx, [rsp+638h+Buffer]; lpSource
0x18001796e  call    ?FormatMessageWedge@@YAJPEBGPEAGKZZ; FormatMessageWedge(ushort const *,ushort *,ulong,...)
0x180017973  mov     ebx, eax
0x180017975  jmp     short loc_1800179AF
0x180017977  mov     ebx, ecx
0x180017979  jmp     short loc_1800179AF
0x18001797b  mov     rcx, cs:g_hInst; hInstance
0x180017982  lea     r8, [rsp+638h+String]; lpBuffer
0x180017987  mov     r9d, 0FFh; cchBufferMax
0x18001798d  mov     edx, 202h; uID
0x180017992  call    cs:__imp_LoadStringW
0x180017998  mov     ebx, 80004005h
0x18001799d  mov     rcx, rdi; this
0x1800179a0  neg     eax
0x1800179a2  sbb     edx, edx
0x1800179a4  not     edx
0x1800179a6  and     ebx, edx
0x1800179a8  xor     edx, edx; unsigned __int16 *
0x1800179aa  call    ?_OnUpdateStatusString@CInternetTimeReadOnly@@AEAAJPEBG@Z; CInternetTimeReadOnly::_OnUpdateStatusString(ushort const *)
0x1800179af  test    ebx, ebx
0x1800179b1  js      short loc_1800179D0
0x1800179b3  mov     rcx, [rdi+10h]; hDlg
0x1800179b7  mov     edx, 334h; nIDDlgItem
0x1800179bc  call    cs:__imp_GetDlgItem
0x1800179c2  mov     rcx, rax; hWnd
0x1800179c5  lea     rdx, [rsp+638h+String]; lpString
0x1800179ca  call    cs:__imp_SetWindowTextW
0x1800179d0  mov     eax, ebx
0x1800179d2  mov     rcx, [rsp+638h+var_18]
0x1800179da  xor     rcx, rsp; StackCookie
0x1800179dd  call    __security_check_cookie
0x1800179e2  mov     rbx, [rsp+638h+arg_8]
0x1800179ea  add     rsp, 630h
0x1800179f1  pop     rdi
0x1800179f2  retn
```
