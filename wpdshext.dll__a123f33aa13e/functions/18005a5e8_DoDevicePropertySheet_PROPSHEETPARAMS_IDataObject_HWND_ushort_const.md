# _DoDevicePropertySheet(PROPSHEETPARAMS *,IDataObject *,HWND__ *,ushort const *)

- ea: `0x18005a5e8`
- end: `0x18005a994`
- name: `?_DoDevicePropertySheet@@YAXPEAUPROPSHEETPARAMS@@PEAUIDataObject@@PEAUHWND__@@PEBG@Z`
- size: `940`
- prototype: `void(struct PROPSHEETPARAMS *, struct IDataObject *, HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18005a4d0`

## callees

- `0x180014dd0`
- `0x1800285c8`
- `0x180035590`
- `0x1800361ba`
- `0x180050e70`
- `0x18005a5e8`
- `0x18005fb88`
- `0x180061c1c`
- `0x1800628cc`
- `0x18006e494`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18005a93c`
- `KERNEL32!LocalFree` at `0x18005a94d`
- `KERNEL32!LocalFree` at `0x18005a93c`
- `KERNEL32!LocalFree` at `0x18005a94d`
- `KERNEL32!GlobalFree` at `0x18005a956`
- `KERNEL32!GlobalFree` at `0x18005a956`
- `KERNEL32!LocalAlloc` at `0x18005a69d`
- `KERNEL32!LocalAlloc` at `0x18005a718`
- `KERNEL32!LocalAlloc` at `0x18005a69d`
- `KERNEL32!LocalAlloc` at `0x18005a718`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005a7eb`
- `SHLWAPI!__imp_ShellMessageBoxW` at `0x18005a7eb`
- `SHELL32!SHGetFileInfoW` at `0x18005a7c0`
- `SHELL32!SHGetFileInfoW` at `0x18005a874`
- `SHELL32!SHGetFileInfoW` at `0x18005a7c0`
- `SHELL32!SHGetFileInfoW` at `0x18005a874`
- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x18005a8ed`
- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x18005a8ed`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x18005a964`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x18005a964`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18005a814`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x18005a814`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall _DoDevicePropertySheet(
        struct PROPSHEETPARAMS *a1,
        struct IDataObject *a2,
        HWND a3,
        const unsigned __int16 *a4)
{
  struct PROPSHEETPARAMS *v7; // r13
  _QWORD *v8; // rdi
  HPSXA v9; // r15
  int v10; // eax
  _DWORD *v11; // rsi
  HKEY v12; // rcx
  __int64 v13; // r8
  UINT v14; // eax
  __int64 v15; // r14
  HLOCAL v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r13
  __int64 v20; // rcx
  __int64 nPages; // rbx
  __int64 i; // r14
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  struct PROPSHEETPARAMS *v26; // [rsp+38h] [rbp-C8h]
  struct _PROPSHEETHEADERW_V2 lParam; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v28[14]; // [rsp+A0h] [rbp-60h] BYREF
  SHFILEINFOW psfi; // [rsp+110h] [rbp+10h] BYREF
  SHFILEINFOW v30; // [rsp+3D0h] [rbp+2D0h] BYREF
  _QWORD v31[100]; // [rsp+690h] [rbp+590h] BYREF

  v7 = a1;
  v26 = a1;
  v8 = 0;
  memset_0(v31, 0, sizeof(v31));
  hMem = 0;
  v9 = 0;
  memset_0(&v30, 0, sizeof(v30));
  memset_0(v28, 0, 0x68u);
  memset_0(&lParam, 0, sizeof(lParam));
  v10 = DataObj_CopyHIDA(a2, (struct _IDA **)&hMem);
  v11 = hMem;
  if ( v10 >= 0 )
  {
    v8 = LocalAlloc(0x40u, 8LL * *(unsigned int *)hMem);
    if ( v8 )
    {
      v9 = _SHCreatePropSheetExtArrayEx(v12, L"WPDPropSheet.Device", v13, a2);
      *(_QWORD *)&lParam.dwSize = 0x200008100000060LL;
      lParam.hwndParent = a3;
      lParam.hInstance = g_hInst;
      lParam.pszCaption = a4;
      v14 = 0;
      lParam.nPages = 0;
      lParam.ppsp = (LPCPROPSHEETPAGEW)v31;
      v15 = 0;
      while ( (unsigned int)v15 < *v11 )
      {
        hMem = 0;
        v16 = LocalAlloc(0x40u, 0x468u);
        v8[v15] = v16;
        if ( !v16
          || (*(_QWORD *)(v8[v15] + 32LL) = IDA_ILClone(v11, (unsigned int)v15), v18 = v8[v15], !*(_QWORD *)(v18 + 32)) )
        {
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&hMem);
          goto LABEL_25;
        }
        *(_QWORD *)(v18 + 8) = *(_QWORD *)v7;
        v19 = v8[v15];
        v20 = *(_QWORD *)(v19 + 8);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 8LL))(v20);
        _InterlockedIncrement((volatile signed __int32 *)v19);
        if ( (unsigned int)SHBindToIDList(
                             *(_QWORD *)(v8[v15] + 32LL),
                             v17,
                             &GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c,
                             &hMem) == -2147024891 )
        {
          memset_0(&psfi, 0, sizeof(psfi));
          if ( SHGetFileInfoW(*(LPCWSTR *)(v8[v15] + 32LL), 0, &psfi, 0x2B8u, 0x208u) )
            ShellMessageBoxW(g_hInst, a3, (LPCWSTR)0xB4, psfi.szDisplayName, 0x10030u);
        }
        else if ( !v9
               || !SHReplaceFromPropSheetExtArray(
                     v9,
                     ((unsigned __int16)v15 << 16) | 1,
                     _AddExtendedPropPage,
                     (LPARAM)&lParam) )
        {
          v28[0] = 104;
          v28[1] = g_hInst;
          v28[6] = v8[v15];
          v28[2] = 808;
          v28[5] = DeviceDlgProc;
          if ( *v11 > 1u && SHGetFileInfoW(*(LPCWSTR *)(v8[v15] + 32LL), 0, &v30, 0x2B8u, 0x208u) )
          {
            HIDWORD(v28[0]) |= 8u;
            v28[4] = v30.szDisplayName;
          }
          if ( lParam.nPages < 0x64 )
          {
            nPages = lParam.nPages;
            v31[nPages] = IsolationAwareCreatePropertySheetPageW(v28);
            ++lParam.nPages;
          }
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&hMem);
        v15 = (unsigned int)(v15 + 1);
        v14 = lParam.nPages;
        v7 = v26;
      }
      if ( v14 )
      {
        if ( v9 )
          SHAddFromPropSheetExtArray(v9, _AddExtendedPropPage, (LPARAM)&lParam);
        ShellPropertySheet(&lParam);
      }
    }
  }
LABEL_25:
  if ( v11 )
  {
    if ( v8 )
    {
      for ( i = 0; (unsigned int)i < *v11; i = (unsigned int)(i + 1) )
      {
        v23 = (_QWORD *)v8[i];
        if ( v23 )
        {
          v24 = v23[1];
          if ( v24 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)v23, 0xFFFFFFFF) == 1 )
            LocalFree(v23);
        }
      }
      LocalFree(v8);
    }
    GlobalFree(v11);
  }
  if ( v9 )
    SHDestroyPropSheetExtArray(v9);
}

```

## disassembly

```asm
0x18005a5e8  mov     [rsp-8+arg_0], rbx
0x18005a5ed  push    rbp
0x18005a5ee  push    rsi
0x18005a5ef  push    rdi
0x18005a5f0  push    r12
0x18005a5f2  push    r13
0x18005a5f4  push    r14
0x18005a5f6  push    r15
0x18005a5f8  lea     rbp, [rsp-8C0h]
0x18005a600  sub     rsp, 9C0h
0x18005a607  mov     rax, cs:__security_cookie
0x18005a60e  xor     rax, rsp
0x18005a611  mov     [rbp+8F0h+var_40], rax
0x18005a618  mov     r14, r9
0x18005a61b  mov     r12, r8
0x18005a61e  mov     rbx, rdx
0x18005a621  mov     r13, rcx
0x18005a624  mov     [rsp+9F0h+var_9B8], rcx
0x18005a629  xor     edi, edi
0x18005a62b  xor     edx, edx; Val
0x18005a62d  mov     r8d, 320h; Size
0x18005a633  lea     rcx, [rbp+8F0h+var_360]; void *
0x18005a63a  call    memset_0
0x18005a63f  mov     [rsp+9F0h+hMem], rdi
0x18005a644  xor     r15d, r15d
0x18005a647  xor     edx, edx; Val
0x18005a649  mov     r8d, 2B8h; Size
0x18005a64f  lea     rcx, [rbp+8F0h+var_620]; void *
0x18005a656  call    memset_0
0x18005a65b  xor     edx, edx; Val
0x18005a65d  lea     r8d, [rdi+68h]; Size
0x18005a661  lea     rcx, [rbp+8F0h+var_950]; void *
0x18005a665  call    memset_0
0x18005a66a  xor     edx, edx; Val
0x18005a66c  lea     r8d, [rdi+60h]; Size
0x18005a670  lea     rcx, [rsp+9F0h+lParam]; void *
0x18005a675  call    memset_0
0x18005a67a  lea     rdx, [rsp+9F0h+hMem]; struct _IDA **
0x18005a67f  mov     rcx, rbx; struct IDataObject *
0x18005a682  call    ?DataObj_CopyHIDA@@YAJPEAUIDataObject@@PEAPEAU_IDA@@@Z; DataObj_CopyHIDA(IDataObject *,_IDA * *)
0x18005a687  mov     rsi, [rsp+9F0h+hMem]
0x18005a68c  test    eax, eax
0x18005a68e  js      loc_18005A8FD
0x18005a694  mov     edx, [rsi]
0x18005a696  shl     rdx, 3; uBytes
0x18005a69a  lea     ecx, [rdi+40h]; uFlags
0x18005a69d  call    cs:__imp_LocalAlloc
0x18005a6a3  mov     rdi, rax
0x18005a6a6  test    rax, rax
0x18005a6a9  jz      loc_18005A8FD
0x18005a6af  mov     r9, rbx; struct IDataObject *
0x18005a6b2  lea     rdx, aWpdpropsheetDe; "WPDPropSheet.Device"
0x18005a6b9  call    ?_SHCreatePropSheetExtArrayEx@@YAPEAUHPSXA__@@PEAUHKEY__@@PEBGIPEAUIDataObject@@@Z; _SHCreatePropSheetExtArrayEx(HKEY__ *,ushort const *,uint,IDataObject *)
0x18005a6be  mov     r15, rax
0x18005a6c1  mov     dword ptr [rsp+9F0h+lParam], 60h ; '`'
0x18005a6c9  mov     dword ptr [rsp+9F0h+lParam+4], 2000081h
0x18005a6d1  mov     [rsp+9F0h+var_9A8], r12
0x18005a6d6  mov     rcx, cs:g_hInst
0x18005a6dd  mov     [rsp+9F0h+var_9A0], rcx
0x18005a6e2  mov     [rsp+9F0h+var_990], r14
0x18005a6e7  xor     eax, eax
0x18005a6e9  mov     [rsp+9F0h+var_988], eax
0x18005a6ed  lea     rcx, [rbp+8F0h+var_360]
0x18005a6f4  mov     [rsp+9F0h+var_978], rcx
0x18005a6f9  xor     r14d, r14d
0x18005a6fc  cmp     r14d, [rsi]
0x18005a6ff  jnb     loc_18005A8D5
0x18005a705  mov     [rsp+9F0h+hMem], 0
0x18005a70e  mov     edx, 468h; uBytes
0x18005a713  mov     ecx, 40h ; '@'; uFlags
0x18005a718  call    cs:__imp_LocalAlloc
0x18005a71e  mov     [rdi+r14*8], rax
0x18005a722  test    rax, rax
0x18005a725  jz      loc_18005A8C9
0x18005a72b  mov     edx, r14d
0x18005a72e  mov     rcx, rsi
0x18005a731  call    IDA_ILClone
0x18005a736  mov     rcx, [rdi+r14*8]
0x18005a73a  mov     [rcx+20h], rax
0x18005a73e  mov     rcx, [rdi+r14*8]
0x18005a742  cmp     qword ptr [rcx+20h], 0
0x18005a747  jz      loc_18005A8C9
0x18005a74d  mov     rax, [r13+0]
0x18005a751  mov     [rcx+8], rax
0x18005a755  mov     r13, [rdi+r14*8]
0x18005a759  mov     rcx, [r13+8]
0x18005a75d  test    rcx, rcx
0x18005a760  jz      short loc_18005A76E
0x18005a762  mov     rax, [rcx]
0x18005a765  mov     rax, [rax+8]
0x18005a769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a76e  lock inc dword ptr [r13+0]
0x18005a773  mov     rcx, [rdi+r14*8]
0x18005a777  lea     r9, [rsp+9F0h+hMem]
0x18005a77c  lea     r8, _GUID_625e2df8_6392_4cf0_9ad1_3cfa5f17775c
0x18005a783  mov     rcx, [rcx+20h]
0x18005a787  call    SHBindToIDList
0x18005a78c  cmp     eax, 80070005h
0x18005a791  jnz     short loc_18005A7F6
0x18005a793  mov     r13d, 2B8h
0x18005a799  mov     r8d, r13d; Size
0x18005a79c  xor     edx, edx; Val
0x18005a79e  lea     rcx, [rbp+8F0h+psfi]; void *
0x18005a7a2  call    memset_0
0x18005a7a7  mov     rcx, [rdi+r14*8]
0x18005a7ab  mov     [rsp+9F0h+uFlags], 208h; uFlags
0x18005a7b3  mov     r9d, r13d; cbFileInfo
0x18005a7b6  lea     r8, [rbp+8F0h+psfi]; psfi
0x18005a7ba  xor     edx, edx; dwFileAttributes
0x18005a7bc  mov     rcx, [rcx+20h]; pszPath
0x18005a7c0  call    cs:__imp_SHGetFileInfoW
0x18005a7c6  test    rax, rax
0x18005a7c9  jz      loc_18005A8AE
0x18005a7cf  mov     [rsp+9F0h+uFlags], 10030h; fuStyle
0x18005a7d7  lea     r9, [rbp+8F0h+psfi.szDisplayName]; lpcTitle
0x18005a7db  mov     r8d, 0B4h; lpcText
0x18005a7e1  mov     rdx, r12; hWnd
0x18005a7e4  mov     rcx, cs:g_hInst; hAppInst
0x18005a7eb  call    cs:__imp_ShellMessageBoxW
0x18005a7f1  jmp     loc_18005A8AE
0x18005a7f6  test    r15, r15
0x18005a7f9  jz      short loc_18005A822
0x18005a7fb  movzx   edx, r14w
0x18005a7ff  shl     edx, 10h
0x18005a802  or      edx, 1; uPageID
0x18005a805  lea     r9, [rsp+9F0h+lParam]; lParam
0x18005a80a  lea     r8, ?_AddExtendedPropPage@@YAHPEAU_PSP@@_J@Z; lpfnReplaceWith
0x18005a811  mov     rcx, r15; hpsxa
0x18005a814  call    cs:__imp_SHReplaceFromPropSheetExtArray
0x18005a81a  test    eax, eax
0x18005a81c  jnz     loc_18005A8AE
0x18005a822  mov     [rbp+8F0h+var_950], 68h ; 'h'
0x18005a82a  mov     rax, cs:g_hInst
0x18005a831  mov     [rbp+8F0h+var_948], rax
0x18005a835  mov     rax, [rdi+r14*8]
0x18005a839  mov     [rbp+8F0h+var_920], rax
0x18005a83d  mov     [rbp+8F0h+var_940], 328h
0x18005a845  lea     rax, ?DeviceDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; DeviceDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18005a84c  mov     [rbp+8F0h+var_928], rax
0x18005a850  cmp     dword ptr [rsi], 1
0x18005a853  jbe     short loc_18005A88E
0x18005a855  mov     rcx, [rdi+r14*8]
0x18005a859  mov     [rsp+9F0h+uFlags], 208h; uFlags
0x18005a861  mov     r9d, 2B8h; cbFileInfo
0x18005a867  lea     r8, [rbp+8F0h+var_620]; psfi
0x18005a86e  xor     edx, edx; dwFileAttributes
0x18005a870  mov     rcx, [rcx+20h]; pszPath
0x18005a874  call    cs:__imp_SHGetFileInfoW
0x18005a87a  test    rax, rax
0x18005a87d  jz      short loc_18005A88E
0x18005a87f  or      dword ptr [rbp+8F0h+var_950+4], 8
0x18005a883  lea     rax, [rbp+8F0h+var_620.szDisplayName]
0x18005a88a  mov     [rbp+8F0h+var_930], rax
0x18005a88e  cmp     [rsp+9F0h+var_988], 64h ; 'd'
0x18005a893  jnb     short loc_18005A8AE
0x18005a895  mov     ebx, [rsp+9F0h+var_988]
0x18005a899  lea     rcx, [rbp+8F0h+var_950]
0x18005a89d  call    IsolationAwareCreatePropertySheetPageW
0x18005a8a2  mov     [rbp+rbx*8+8F0h+var_360], rax
0x18005a8aa  inc     [rsp+9F0h+var_988]
0x18005a8ae  lea     rcx, [rsp+9F0h+hMem]
0x18005a8b3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a8b8  inc     r14d
0x18005a8bb  mov     eax, [rsp+9F0h+var_988]
0x18005a8bf  mov     r13, [rsp+9F0h+var_9B8]
0x18005a8c4  jmp     loc_18005A6FC
0x18005a8c9  lea     rcx, [rsp+9F0h+hMem]
0x18005a8ce  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a8d3  jmp     short loc_18005A8FD
0x18005a8d5  test    eax, eax
0x18005a8d7  jz      short loc_18005A8FD
0x18005a8d9  test    r15, r15
0x18005a8dc  jz      short loc_18005A8F3
0x18005a8de  lea     r8, [rsp+9F0h+lParam]; lParam
0x18005a8e3  lea     rdx, ?_AddExtendedPropPage@@YAHPEAU_PSP@@_J@Z; lpfnAddPage
0x18005a8ea  mov     rcx, r15; hpsxa
0x18005a8ed  call    cs:__imp_SHAddFromPropSheetExtArray
0x18005a8f3  lea     rcx, [rsp+9F0h+lParam]; struct _PROPSHEETHEADERW_V2 *
0x18005a8f8  call    ?ShellPropertySheet@@YA_JPEBU_PROPSHEETHEADERW_V2@@@Z; ShellPropertySheet(_PROPSHEETHEADERW_V2 const *)
0x18005a8fd  test    rsi, rsi
0x18005a900  jz      short loc_18005A95C
0x18005a902  test    rdi, rdi
0x18005a905  jz      short loc_18005A953
0x18005a907  xor     r14d, r14d
0x18005a90a  cmp     [rsi], r14d
0x18005a90d  jbe     short loc_18005A94A
0x18005a90f  mov     rbx, [rdi+r14*8]
0x18005a913  test    rbx, rbx
0x18005a916  jz      short loc_18005A942
0x18005a918  mov     rcx, [rbx+8]
0x18005a91c  test    rcx, rcx
0x18005a91f  jz      short loc_18005A92D
0x18005a921  mov     rax, [rcx]
0x18005a924  mov     rax, [rax+10h]
0x18005a928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a92d  or      eax, 0FFFFFFFFh
0x18005a930  lock xadd [rbx], eax
0x18005a934  cmp     eax, 1
0x18005a937  jnz     short loc_18005A942
0x18005a939  mov     rcx, rbx; hMem
0x18005a93c  call    cs:__imp_LocalFree
0x18005a942  inc     r14d
0x18005a945  cmp     r14d, [rsi]
0x18005a948  jb      short loc_18005A90F
0x18005a94a  mov     rcx, rdi; hMem
0x18005a94d  call    cs:__imp_LocalFree
0x18005a953  mov     rcx, rsi; hMem
0x18005a956  call    cs:__imp_GlobalFree
0x18005a95c  test    r15, r15
0x18005a95f  jz      short loc_18005A96A
0x18005a961  mov     rcx, r15; hpsxa
0x18005a964  call    cs:__imp_SHDestroyPropSheetExtArray
0x18005a96a  mov     rcx, [rbp+8F0h+var_40]
0x18005a971  xor     rcx, rsp; StackCookie
0x18005a974  call    __security_check_cookie
0x18005a979  mov     rbx, [rsp+9F0h+arg_0]
0x18005a981  add     rsp, 9C0h
0x18005a988  pop     r15
0x18005a98a  pop     r14
0x18005a98c  pop     r13
0x18005a98e  pop     r12
0x18005a990  pop     rdi
0x18005a991  pop     rsi
0x18005a992  pop     rbp
0x18005a993  retn
```
