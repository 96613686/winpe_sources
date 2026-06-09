# CWallpaperCore::_SelectionHelper(IShellItem *,IShellFolder *,bool)

- ea: `0x180042dc0`
- end: `0x180042f79`
- name: `?_SelectionHelper@CWallpaperCore@@AEAAJPEAUIShellItem@@PEAUIShellFolder@@_N@Z`
- size: `441`
- prototype: `int(CWallpaperCore *__hidden this, struct IShellItem *, struct IShellFolder *, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18003d150`
- `0x180042204`
- `0x180042c08`

## callees

- `0x180002280`
- `0x18000d164`
- `0x180042dc0`
- `0x180057010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x180042f16`
- `SHELL32!SHGetIDListFromObject` at `0x180042f16`
- `SHELL32!__imp_ILFindLastID` at `0x180042ead`
- `SHELL32!__imp_ILFindLastID` at `0x180042f33`
- `SHELL32!__imp_ILFindLastID` at `0x180042ead`
- `SHELL32!__imp_ILFindLastID` at `0x180042f33`
- `SHELL32!__imp_ILFree` at `0x180042ecd`
- `SHELL32!__imp_ILFree` at `0x180042f53`
- `SHELL32!__imp_ILFree` at `0x180042ecd`
- `SHELL32!__imp_ILFree` at `0x180042f53`
- `ole32!CreateBindCtx` at `0x180042df6`
- `ole32!CreateBindCtx` at `0x180042df6`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_SelectionHelper(
        CWallpaperCore *this,
        IUnknown *a2,
        struct IShellFolder *a3,
        bool a4)
{
  HRESULT (__stdcall *ParseDisplayName)(IShellFolder *, HWND, IBindCtx *, LPWSTR, ULONG *, LPITEMIDLIST *, ULONG *); // rax
  HRESULT v9; // ebx
  CBrowserFrame *v10; // rbx
  const struct _ITEMID_CHILD *v11; // rax
  CBrowserFrame *v12; // rbx
  const struct _ITEMID_CHILD *ID; // rax
  LPBC ppbc; // [rsp+40h] [rbp-20h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+48h] [rbp-18h] BYREF

  ppbc = 0;
  if ( CreateBindCtx(0, &ppbc) < 0 )
  {
LABEL_9:
    pidl[0] = 0;
    v9 = SHGetIDListFromObject(a2, pidl);
    if ( v9 >= 0 )
    {
      v12 = (CBrowserFrame *)*((_QWORD *)this + 21);
      ID = (const struct _ITEMID_CHILD *)ILFindLastID(pidl[0]);
      v9 = CBrowserFrame::SelectItem(v12, ID, a4);
      ILFree(pidl[0]);
    }
    return (unsigned int)v9;
  }
  pidl[0] = (LPITEMIDLIST)16;
  pidl[1] = (LPITEMIDLIST)4096;
  if ( ((int (__fastcall *)(LPBC, LPITEMIDLIST *))ppbc->lpVtbl->SetBindOptions)(ppbc, pidl) < 0
    || ((int (__fastcall *)(LPBC, const wchar_t *, IUnknown *))ppbc->lpVtbl->RegisterObjectParam)(
         ppbc,
         L"ParseOriginalItem",
         a2) < 0 )
  {
    ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
    ppbc = 0;
    goto LABEL_9;
  }
  ParseDisplayName = a3->lpVtbl->ParseDisplayName;
  pidl[0] = 0;
  v9 = ((__int64 (__fastcall *)(struct IShellFolder *, _QWORD, LPBC, const WCHAR *, _QWORD, LPITEMIDLIST *, _QWORD))ParseDisplayName)(
         a3,
         0,
         ppbc,
         &cchOriginalDestLength,
         0,
         pidl,
         0);
  if ( v9 >= 0 )
  {
    v10 = (CBrowserFrame *)*((_QWORD *)this + 21);
    v11 = (const struct _ITEMID_CHILD *)ILFindLastID(pidl[0]);
    v9 = CBrowserFrame::SelectItem(v10, v11, a4);
    ILFree(pidl[0]);
  }
  ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
  if ( v9 < 0 )
    goto LABEL_9;
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180042dc0  push    rbp
0x180042dc2  push    rbx
0x180042dc3  push    rsi
0x180042dc4  push    rdi
0x180042dc5  push    r14
0x180042dc7  mov     rbp, rsp
0x180042dca  sub     rsp, 60h
0x180042dce  mov     rax, cs:__security_cookie
0x180042dd5  xor     rax, rsp
0x180042dd8  mov     [rbp+var_8], rax
0x180042ddc  mov     rdi, rdx
0x180042ddf  mov     [rbp+ppbc], 0
0x180042de7  mov     rsi, rcx
0x180042dea  lea     rdx, [rbp+ppbc]; ppbc
0x180042dee  xor     ecx, ecx; reserved
0x180042df0  mov     r14b, r9b
0x180042df3  mov     rbx, r8
0x180042df6  call    cs:__imp_CreateBindCtx
0x180042dfd  nop     dword ptr [rax+rax+00h]
0x180042e02  test    eax, eax
0x180042e04  js      loc_180042F07
0x180042e0a  mov     rcx, [rbp+ppbc]
0x180042e0e  lea     rdx, [rbp+pidl]
0x180042e12  xor     eax, eax
0x180042e14  mov     dword ptr [rbp+pidl], 10h
0x180042e1b  mov     [rbp+pidl+4], rax
0x180042e1f  mov     [rbp+pidl+8], 1000h
0x180042e27  mov     rax, [rcx]
0x180042e2a  mov     rax, [rax+30h]
0x180042e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e33  test    eax, eax
0x180042e35  js      loc_180042EEF
0x180042e3b  mov     rcx, [rbp+ppbc]
0x180042e3f  lea     rdx, aParseoriginali; "ParseOriginalItem"
0x180042e46  mov     r8, rdi
0x180042e49  mov     rax, [rcx]
0x180042e4c  mov     rax, [rax+48h]
0x180042e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e55  test    eax, eax
0x180042e57  js      loc_180042EEF
0x180042e5d  mov     rax, [rbx]
0x180042e60  lea     rcx, [rbp+pidl]
0x180042e64  mov     r8, [rbp+ppbc]
0x180042e68  lea     r9, cchOriginalDestLength
0x180042e6f  mov     [rsp+60h+var_30], 0
0x180042e78  xor     edx, edx
0x180042e7a  mov     [rsp+60h+var_38], rcx
0x180042e7f  mov     rcx, rbx
0x180042e82  mov     rax, [rax+18h]
0x180042e86  mov     [rbp+pidl], 0
0x180042e8e  mov     [rsp+60h+var_40], 0
0x180042e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e9c  mov     ebx, eax
0x180042e9e  test    eax, eax
0x180042ea0  js      short loc_180042ED9
0x180042ea2  mov     rcx, [rbp+pidl]; pidl
0x180042ea6  mov     rbx, [rsi+0A8h]
0x180042ead  call    cs:__imp_ILFindLastID
0x180042eb4  nop     dword ptr [rax+rax+00h]
0x180042eb9  mov     r8b, r14b; bool
0x180042ebc  mov     rcx, rbx; this
0x180042ebf  mov     rdx, rax; struct _ITEMID_CHILD *
0x180042ec2  call    ?SelectItem@CBrowserFrame@@QEAAJPEFBU_ITEMID_CHILD@@_N@Z; CBrowserFrame::SelectItem(_ITEMID_CHILD const *,bool)
0x180042ec7  mov     rcx, [rbp+pidl]; pidl
0x180042ecb  mov     ebx, eax
0x180042ecd  call    cs:__imp_ILFree
0x180042ed4  nop     dword ptr [rax+rax+00h]
0x180042ed9  mov     rcx, [rbp+ppbc]
0x180042edd  mov     rax, [rcx]
0x180042ee0  mov     rax, [rax+10h]
0x180042ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee9  test    ebx, ebx
0x180042eeb  js      short loc_180042F07
0x180042eed  jmp     short loc_180042F5F
0x180042eef  mov     rcx, [rbp+ppbc]
0x180042ef3  mov     rax, [rcx]
0x180042ef6  mov     rax, [rax+10h]
0x180042efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042eff  mov     [rbp+ppbc], 0
0x180042f07  lea     rdx, [rbp+pidl]; ppidl
0x180042f0b  mov     [rbp+pidl], 0
0x180042f13  mov     rcx, rdi; punk
0x180042f16  call    cs:__imp_SHGetIDListFromObject
0x180042f1d  nop     dword ptr [rax+rax+00h]
0x180042f22  mov     ebx, eax
0x180042f24  test    eax, eax
0x180042f26  js      short loc_180042F5F
0x180042f28  mov     rcx, [rbp+pidl]; pidl
0x180042f2c  mov     rbx, [rsi+0A8h]
0x180042f33  call    cs:__imp_ILFindLastID
0x180042f3a  nop     dword ptr [rax+rax+00h]
0x180042f3f  mov     r8b, r14b; bool
0x180042f42  mov     rcx, rbx; this
0x180042f45  mov     rdx, rax; struct _ITEMID_CHILD *
0x180042f48  call    ?SelectItem@CBrowserFrame@@QEAAJPEFBU_ITEMID_CHILD@@_N@Z; CBrowserFrame::SelectItem(_ITEMID_CHILD const *,bool)
0x180042f4d  mov     rcx, [rbp+pidl]; pidl
0x180042f51  mov     ebx, eax
0x180042f53  call    cs:__imp_ILFree
0x180042f5a  nop     dword ptr [rax+rax+00h]
0x180042f5f  mov     eax, ebx
0x180042f61  mov     rcx, [rbp+var_8]
0x180042f65  xor     rcx, rsp; StackCookie
0x180042f68  call    __security_check_cookie
0x180042f6d  add     rsp, 60h
0x180042f71  pop     r14
0x180042f73  pop     rdi
0x180042f74  pop     rsi
0x180042f75  pop     rbx
0x180042f76  pop     rbp
0x180042f77  retn
```
