# WdcFolderBrowser(HWND__ *,ushort *,unsigned __int64)

- ea: `0x18002b364`
- end: `0x18002b530`
- name: `?WdcFolderBrowser@@YAJPEAUHWND__@@PEAG_K@Z`
- size: `460`
- prototype: `int(HWND, unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800555c4`
- `0x18005a004`

## callees

- `0x1800044ac`
- `0x1800071e0`
- `0x180008ab0`
- `0x18000b854`
- `0x18002b364`
- `0x180033058`
- `0x18003b0ac`
- `0x180086010`

## import_xrefs

- `SHELL32!SHGetPathFromIDListW` at `0x18002b467`
- `SHELL32!SHGetPathFromIDListW` at `0x18002b467`
- `SHELL32!SHGetMalloc` at `0x18002b3e4`
- `SHELL32!SHGetMalloc` at `0x18002b3e4`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18002b3ff`
- `SHELL32!SHGetSpecialFolderLocation` at `0x18002b3ff`
- `SHELL32!SHBrowseForFolderW` at `0x18002b44e`
- `SHELL32!SHBrowseForFolderW` at `0x18002b44e`
- `KERNEL32!GetLastError` at `0x18002b475`
- `KERNEL32!GetLastError` at `0x18002b475`

## pseudocode

```c
__int64 __fastcall WdcFolderBrowser(HWND a1, unsigned __int16 *a2)
{
  const ITEMIDLIST *v2; // r14
  const char *v5; // rdx
  int v6; // r8d
  WCHAR *v7; // rsi
  signed int v8; // ebx
  HRESULT String; // eax
  unsigned __int64 v10; // rdx
  const ITEMIDLIST *v11; // rax
  const char *v12; // rdx
  int v13; // r8d
  signed int LastError; // eax
  IMalloc *v15; // rcx
  int v17; // [rsp+20h] [rbp-50h]
  _browseinfoW bi; // [rsp+30h] [rbp-40h] BYREF
  IMalloc *ppMalloc; // [rsp+B0h] [rbp+40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+B8h] [rbp+48h] BYREF

  v2 = 0;
  ppidl = 0;
  ppMalloc = 0;
  memset_0(&bi, 0, sizeof(bi));
  v7 = (WCHAR *)WdcAlloc(0x100u, v5, v6);
  if ( !v7 )
  {
    v8 = -2147024882;
    v17 = -2147024882;
LABEL_19:
    WdcDebugMessage("base\\diagnosis\\pdui\\perfmon\\mmc\\dialogs.cpp", "WdcFolderBrowser", 0, L"FAILURE: 0x%08x", v17);
    goto LABEL_20;
  }
  *v7 = 0;
  String = WdcLoadString(0x14u, v7, 0x80u);
  v8 = String;
  if ( String < 0
    || (String = SHGetMalloc(&ppMalloc), v8 = String, String < 0)
    || (String = SHGetSpecialFolderLocation(0, 17, &ppidl), v8 = String, String < 0)
    || (String = WdcExpandVariables(a2, v10, a2), v8 = String, String < 0) )
  {
LABEL_18:
    v17 = String;
    goto LABEL_19;
  }
  bi.pidlRoot = ppidl;
  bi.lpfn = (BFFCALLBACK)WdcFolderBrowserCallback;
  bi.hwndOwner = a1;
  bi.lpszTitle = v7;
  bi.ulFlags = 75;
  bi.pszDisplayName = a2;
  bi.lParam = (LPARAM)a2;
  v11 = SHBrowseForFolderW(&bi);
  v2 = v11;
  if ( !v11 )
  {
    v8 = 1;
    goto LABEL_20;
  }
  if ( SHGetPathFromIDListW(v11, a2) )
  {
    v8 = 0;
    goto LABEL_20;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( !LastError )
  {
    v8 = -2147467259;
LABEL_17:
    String = v8;
    goto LABEL_18;
  }
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 < 0 )
    goto LABEL_17;
LABEL_20:
  v15 = ppMalloc;
  if ( ppMalloc )
  {
    if ( v2 )
    {
      ((void (__fastcall *)(IMalloc *, const ITEMIDLIST *))ppMalloc->lpVtbl->Free)(ppMalloc, v2);
      v15 = ppMalloc;
    }
    v12 = (const char *)ppidl;
    if ( ppidl )
    {
      ((void (__fastcall *)(IMalloc *))v15->lpVtbl->Free)(v15);
      v15 = ppMalloc;
    }
    if ( v15 )
    {
      ((void (__fastcall *)(IMalloc *))v15->lpVtbl->Release)(v15);
      ppMalloc = 0;
    }
  }
  if ( v7 )
    WdcFree(v7, v12, v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b364  mov     [rsp-28h+arg_0], rbx
0x18002b369  mov     [rsp-28h+ppMalloc], r8
0x18002b36e  push    rbp
0x18002b36f  push    rsi
0x18002b370  push    rdi
0x18002b371  push    r14
0x18002b373  push    r15
0x18002b375  mov     rbp, rsp
0x18002b378  sub     rsp, 70h
0x18002b37c  xor     r14d, r14d
0x18002b37f  mov     [rbp+ppidl], 0
0x18002b387  mov     rdi, rdx
0x18002b38a  mov     [rbp+ppMalloc], r14
0x18002b38e  mov     r15, rcx
0x18002b391  xor     edx, edx; Val
0x18002b393  lea     rcx, [rbp+bi]; void *
0x18002b397  lea     r8d, [r14+40h]; Size
0x18002b39b  call    memset_0
0x18002b3a0  mov     ecx, 100h; dwBytes
0x18002b3a5  call    ?WdcAlloc@@YAPEAX_KPEBDH@Z; WdcAlloc(unsigned __int64,char const *,int)
0x18002b3aa  mov     rsi, rax
0x18002b3ad  test    rax, rax
0x18002b3b0  jnz     short loc_18002B3C0
0x18002b3b2  mov     ebx, 8007000Eh
0x18002b3b7  mov     [rsp+70h+var_50], ebx
0x18002b3bb  jmp     loc_18002B49D
0x18002b3c0  xor     eax, eax
0x18002b3c2  mov     r8d, 80h; cchBufferMax
0x18002b3c8  mov     rdx, rsi; lpBuffer
0x18002b3cb  mov     [rsi], ax
0x18002b3ce  lea     ecx, [rax+14h]; uID
0x18002b3d1  call    ?WdcLoadString@@YAJKPEAG_K@Z; WdcLoadString(ulong,ushort *,unsigned __int64)
0x18002b3d6  mov     ebx, eax
0x18002b3d8  test    eax, eax
0x18002b3da  js      loc_18002B499
0x18002b3e0  lea     rcx, [rbp+ppMalloc]; ppMalloc
0x18002b3e4  call    cs:__imp_SHGetMalloc
0x18002b3ea  mov     ebx, eax
0x18002b3ec  test    eax, eax
0x18002b3ee  js      loc_18002B499
0x18002b3f4  lea     r8, [rbp+ppidl]; ppidl
0x18002b3f8  mov     edx, 11h; csidl
0x18002b3fd  xor     ecx, ecx; hwnd
0x18002b3ff  call    cs:__imp_SHGetSpecialFolderLocation
0x18002b405  mov     ebx, eax
0x18002b407  test    eax, eax
0x18002b409  js      loc_18002B499
0x18002b40f  mov     r8, rdi; unsigned __int16 *
0x18002b412  mov     rcx, rdi; unsigned __int16 *
0x18002b415  call    ?WdcExpandVariables@@YAJPEAG_KPEBG@Z; WdcExpandVariables(ushort *,unsigned __int64,ushort const *)
0x18002b41a  mov     ebx, eax
0x18002b41c  test    eax, eax
0x18002b41e  js      short loc_18002B499
0x18002b420  mov     rax, [rbp+ppidl]
0x18002b424  lea     rcx, [rbp+bi]; lpbi
0x18002b428  mov     [rbp+bi.pidlRoot], rax
0x18002b42c  lea     rax, ?WdcFolderBrowserCallback@@YAHPEAUHWND__@@I_J1@Z; WdcFolderBrowserCallback(HWND__ *,uint,__int64,__int64)
0x18002b433  mov     [rbp+bi.lpfn], rax
0x18002b437  mov     [rbp+bi.hwndOwner], r15
0x18002b43b  mov     [rbp+bi.lpszTitle], rsi
0x18002b43f  mov     [rbp+bi.ulFlags], 4Bh ; 'K'
0x18002b446  mov     [rbp+bi.pszDisplayName], rdi
0x18002b44a  mov     [rbp+bi.lParam], rdi
0x18002b44e  call    cs:__imp_SHBrowseForFolderW
0x18002b454  mov     r14, rax
0x18002b457  test    rax, rax
0x18002b45a  jnz     short loc_18002B461
0x18002b45c  lea     ebx, [rax+1]
0x18002b45f  jmp     short loc_18002B4BA
0x18002b461  mov     rdx, rdi; pszPath
0x18002b464  mov     rcx, rax; pidl
0x18002b467  call    cs:__imp_SHGetPathFromIDListW
0x18002b46d  test    eax, eax
0x18002b46f  jz      short loc_18002B475
0x18002b471  xor     ebx, ebx
0x18002b473  jmp     short loc_18002B4BA
0x18002b475  call    cs:__imp_GetLastError
0x18002b47b  mov     ebx, eax
0x18002b47d  test    eax, eax
0x18002b47f  jz      short loc_18002B492
0x18002b481  jle     short loc_18002B48C
0x18002b483  movzx   ebx, ax
0x18002b486  or      ebx, 80070000h
0x18002b48c  test    ebx, ebx
0x18002b48e  jns     short loc_18002B4BA
0x18002b490  jmp     short loc_18002B497
0x18002b492  mov     ebx, 80004005h
0x18002b497  mov     eax, ebx
0x18002b499  mov     [rsp+70h+var_50], eax
0x18002b49d  lea     r9, aFailure0x08x; "FAILURE: 0x%08x"
0x18002b4a4  xor     r8d, r8d; int
0x18002b4a7  lea     rdx, aWdcfolderbrows; "WdcFolderBrowser"
0x18002b4ae  lea     rcx, aBaseDiagnosisP_28; "base\\diagnosis\\pdui\\perfmon\\mmc\\di"...
0x18002b4b5  call    ?WdcDebugMessage@@YAXPEBD0HPEBGZZ; WdcDebugMessage(char const *,char const *,int,ushort const *,...)
0x18002b4ba  mov     rcx, [rbp+ppMalloc]
0x18002b4be  test    rcx, rcx
0x18002b4c1  jz      short loc_18002B50D
0x18002b4c3  test    r14, r14
0x18002b4c6  jz      short loc_18002B4DB
0x18002b4c8  mov     rax, [rcx]
0x18002b4cb  mov     rdx, r14
0x18002b4ce  mov     rax, [rax+28h]
0x18002b4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4d7  mov     rcx, [rbp+ppMalloc]
0x18002b4db  mov     rdx, [rbp+ppidl]
0x18002b4df  test    rdx, rdx
0x18002b4e2  jz      short loc_18002B4F4
0x18002b4e4  mov     rax, [rcx]
0x18002b4e7  mov     rax, [rax+28h]
0x18002b4eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4f0  mov     rcx, [rbp+ppMalloc]
0x18002b4f4  test    rcx, rcx
0x18002b4f7  jz      short loc_18002B50D
0x18002b4f9  mov     rax, [rcx]
0x18002b4fc  mov     rax, [rax+10h]
0x18002b500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b505  mov     [rbp+ppMalloc], 0
0x18002b50d  test    rsi, rsi
0x18002b510  jz      short loc_18002B51A
0x18002b512  mov     rcx, rsi; void *
0x18002b515  call    ?WdcFree@@YAXPEAXPEBDH@Z; WdcFree(void *,char const *,int)
0x18002b51a  mov     eax, ebx
0x18002b51c  mov     rbx, [rsp+70h+arg_0]
0x18002b524  add     rsp, 70h
0x18002b528  pop     r15
0x18002b52a  pop     r14
0x18002b52c  pop     rdi
0x18002b52d  pop     rsi
0x18002b52e  pop     rbp
0x18002b52f  retn
```
