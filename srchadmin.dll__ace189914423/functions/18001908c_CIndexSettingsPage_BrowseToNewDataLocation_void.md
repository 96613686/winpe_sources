# CIndexSettingsPage::_BrowseToNewDataLocation(void)

- ea: `0x18001908c`
- end: `0x180019246`
- name: `?_BrowseToNewDataLocation@CIndexSettingsPage@@AEAAJXZ`
- size: `442`
- prototype: `__int64 __fastcall(CIndexSettingsPage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800198d4`

## callees

- `0x180005cc0`
- `0x18000cfa0`
- `0x180010680`
- `0x18001908c`
- `0x1800193c8`

## import_xrefs

- `SHELL32!SHBrowseForFolderW` at `0x180019167`
- `SHELL32!SHBrowseForFolderW` at `0x180019167`
- `SHELL32!SHGetPathFromIDListW` at `0x180019183`
- `SHELL32!SHGetPathFromIDListW` at `0x180019183`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800190d3`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1800190d3`
- `SHLWAPI!PathCombineW` at `0x1800191a5`
- `SHLWAPI!PathCombineW` at `0x1800191a5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800190fa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800190fa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001920c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019217`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001920c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180019217`
- `USER32!IsDlgButtonChecked` at `0x1800191b3`
- `USER32!IsDlgButtonChecked` at `0x1800191b3`

## pseudocode

```c
__int64 __fastcall CIndexSettingsPage::_BrowseToNewDataLocation(HWND *this)
{
  HRESULT Error; // ebx
  const ITEMIDLIST *v3; // rax
  ITEMIDLIST *v4; // rsi
  unsigned __int16 *v5; // r14
  unsigned __int16 v6; // cx
  bool v8; // [rsp+20h] [rbp-E0h] BYREF
  bool v9; // [rsp+21h] [rbp-DFh] BYREF
  LPITEMIDLIST ppidl; // [rsp+28h] [rbp-D8h] BYREF
  _browseinfoW bi; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszPath[264]; // [rsp+280h] [rbp+180h] BYREF
  char v14; // [rsp+490h] [rbp+390h] BYREF

  ppidl = 0;
  Error = SHGetSpecialFolderLocation(*this, 17, &ppidl);
  if ( Error >= 0 )
  {
    if ( !LoadStringW(Globals, 0x25Fu, Buffer, 260) )
      Error = ResultFromLastError();
    if ( Error >= 0 )
    {
      bi.hwndOwner = *this;
      bi.pidlRoot = ppidl;
      bi.pszDisplayName = (LPWSTR)&v14;
      bi.lpszTitle = Buffer;
      bi.lpfn = (BFFCALLBACK)CIndexSettingsPage::s_BrowseCallbackProc;
      bi.lParam = (LPARAM)(this + 10);
      *(_QWORD *)&bi.ulFlags = 105;
      *(_QWORD *)&bi.iImage = 0;
      v3 = SHBrowseForFolderW(&bi);
      v4 = (ITEMIDLIST *)v3;
      if ( v3 && SHGetPathFromIDListW(v3, pszPath) )
      {
        v5 = (unsigned __int16 *)(this + 75);
        PathCombineW((LPWSTR)this + 300, pszPath, L"Search\\Data");
        if ( IsDlgButtonChecked(*this, 902) == 1 )
        {
          v6 = *v5;
          v8 = 0;
          v9 = 0;
          Error = IsPathBitlocked(v6, &v8, &v9);
          if ( Error < 0 || !v8 )
          {
            Error = CIndexSettingsPage::_DisplayBitlockerWarning((CIndexSettingsPage *)this, 0, 0);
            if ( Error == 1 )
              *v5 = 0;
          }
        }
      }
      else
      {
        Error = 1;
      }
      CoTaskMemFree(v4);
    }
    CoTaskMemFree(ppidl);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001908c  mov     [rsp-8+arg_8], rbx
0x180019091  mov     [rsp-8+arg_10], rsi
0x180019096  push    rbp
0x180019097  push    rdi
0x180019098  push    r14
0x18001909a  lea     rbp, [rsp-5B0h]
0x1800190a2  sub     rsp, 6B0h
0x1800190a9  mov     rax, cs:__security_cookie
0x1800190b0  xor     rax, rsp
0x1800190b3  mov     [rbp+5C0h+var_20], rax
0x1800190ba  mov     rdi, rcx
0x1800190bd  mov     [rsp+6C0h+ppidl], 0
0x1800190c6  mov     rcx, [rcx]; hwnd
0x1800190c9  lea     r8, [rsp+6C0h+ppidl]; ppidl
0x1800190ce  mov     edx, 11h; csidl
0x1800190d3  call    cs:__imp_SHGetSpecialFolderLocation
0x1800190d9  mov     ebx, eax
0x1800190db  test    eax, eax
0x1800190dd  js      loc_18001921D
0x1800190e3  mov     rcx, cs:Globals; hInstance
0x1800190ea  lea     r8, [rsp+6C0h+Buffer]; lpBuffer
0x1800190ef  mov     r9d, 104h; cchBufferMax
0x1800190f5  mov     edx, 25Fh; uID
0x1800190fa  call    cs:__imp_LoadStringW
0x180019100  test    eax, eax
0x180019102  jnz     short loc_18001910B
0x180019104  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180019109  mov     ebx, eax
0x18001910b  test    ebx, ebx
0x18001910d  js      loc_180019212
0x180019113  mov     rax, [rdi]
0x180019116  lea     rcx, [rsp+6C0h+bi]; lpbi
0x18001911b  mov     [rsp+6C0h+bi.hwndOwner], rax
0x180019120  mov     rax, [rsp+6C0h+ppidl]
0x180019125  mov     [rsp+6C0h+bi.pidlRoot], rax
0x18001912a  lea     rax, [rbp+5C0h+var_230]
0x180019131  mov     [rsp+6C0h+bi.pszDisplayName], rax
0x180019136  lea     rax, [rsp+6C0h+Buffer]
0x18001913b  mov     [rsp+6C0h+bi.lpszTitle], rax
0x180019140  lea     rax, ?s_BrowseCallbackProc@CIndexSettingsPage@@CAHPEAUHWND__@@I_J1@Z; CIndexSettingsPage::s_BrowseCallbackProc(HWND__ *,uint,__int64,__int64)
0x180019147  mov     [rsp+6C0h+bi.lpfn], rax
0x18001914c  lea     rax, [rdi+50h]
0x180019150  mov     [rsp+6C0h+bi.lParam], rax
0x180019155  mov     qword ptr [rsp+6C0h+bi.ulFlags], 69h ; 'i'
0x18001915e  mov     qword ptr [rsp+6C0h+bi.iImage], 0
0x180019167  call    cs:__imp_SHBrowseForFolderW
0x18001916d  mov     rsi, rax
0x180019170  test    rax, rax
0x180019173  jz      loc_180019204
0x180019179  lea     rdx, [rbp+5C0h+pszPath]; pszPath
0x180019180  mov     rcx, rax; pidl
0x180019183  call    cs:__imp_SHGetPathFromIDListW
0x180019189  test    eax, eax
0x18001918b  jz      short loc_180019204
0x18001918d  lea     r14, [rdi+258h]
0x180019194  mov     rcx, r14; pszDest
0x180019197  lea     r8, pszFile; "Search\\Data"
0x18001919e  lea     rdx, [rbp+5C0h+pszPath]; pszDir
0x1800191a5  call    cs:__imp_PathCombineW
0x1800191ab  mov     rcx, [rdi]; hDlg
0x1800191ae  mov     edx, 386h; nIDButton
0x1800191b3  call    cs:__imp_IsDlgButtonChecked
0x1800191b9  cmp     eax, 1
0x1800191bc  jnz     short loc_180019209
0x1800191be  movzx   ecx, word ptr [r14]; unsigned __int16
0x1800191c2  lea     r8, [rsp+6C0h+var_69F]; bool *
0x1800191c7  lea     rdx, [rsp+6C0h+var_6A0]; bool *
0x1800191cc  mov     [rsp+6C0h+var_6A0], 0
0x1800191d1  mov     [rsp+6C0h+var_69F], 0
0x1800191d6  call    ?IsPathBitlocked@@YAJGPEA_N0@Z; IsPathBitlocked(ushort,bool *,bool *)
0x1800191db  mov     ebx, eax
0x1800191dd  test    eax, eax
0x1800191df  js      short loc_1800191E8
0x1800191e1  cmp     [rsp+6C0h+var_6A0], 0
0x1800191e6  jnz     short loc_180019209
0x1800191e8  xor     r8d, r8d; int
0x1800191eb  xor     edx, edx; int
0x1800191ed  mov     rcx, rdi; this
0x1800191f0  call    ?_DisplayBitlockerWarning@CIndexSettingsPage@@AEAAJHH@Z; CIndexSettingsPage::_DisplayBitlockerWarning(int,int)
0x1800191f5  mov     ebx, eax
0x1800191f7  cmp     eax, 1
0x1800191fa  jnz     short loc_180019209
0x1800191fc  xor     eax, eax
0x1800191fe  mov     [r14], ax
0x180019202  jmp     short loc_180019209
0x180019204  mov     ebx, 1
0x180019209  mov     rcx, rsi; pv
0x18001920c  call    cs:__imp_CoTaskMemFree
0x180019212  mov     rcx, [rsp+6C0h+ppidl]; pv
0x180019217  call    cs:__imp_CoTaskMemFree
0x18001921d  mov     eax, ebx
0x18001921f  mov     rcx, [rbp+5C0h+var_20]
0x180019226  xor     rcx, rsp; StackCookie
0x180019229  call    __security_check_cookie
0x18001922e  lea     r11, [rsp+6C0h+var_10]
0x180019236  mov     rbx, [r11+28h]
0x18001923a  mov     rsi, [r11+30h]
0x18001923e  mov     rsp, r11
0x180019241  pop     r14
0x180019243  pop     rdi
0x180019244  pop     rbp
0x180019245  retn
```
