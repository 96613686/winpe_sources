# _DoStoragePropertySheet(PROPSHEETPARAMS *,IDataObject *,HWND__ *,ushort const *)

- ea: `0x180068a34`
- end: `0x180068d52`
- name: `?_DoStoragePropertySheet@@YAXPEAUPROPSHEETPARAMS@@PEAUIDataObject@@PEAUHWND__@@PEBG@Z`
- size: `798`
- prototype: `void(struct PROPSHEETPARAMS *, struct IDataObject *, HWND, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180069520`

## callees

- `0x180035590`
- `0x1800361ba`
- `0x180050e70`
- `0x18005fb88`
- `0x180061c1c`
- `0x180062108`
- `0x1800628cc`
- `0x180068a34`
- `0x18006e494`
- `0x180078010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180068cfa`
- `KERNEL32!LocalFree` at `0x180068d0b`
- `KERNEL32!LocalFree` at `0x180068cfa`
- `KERNEL32!LocalFree` at `0x180068d0b`
- `KERNEL32!GlobalFree` at `0x180068d14`
- `KERNEL32!GlobalFree` at `0x180068d14`
- `KERNEL32!LocalAlloc` at `0x180068ae6`
- `KERNEL32!LocalAlloc` at `0x180068b58`
- `KERNEL32!LocalAlloc` at `0x180068ae6`
- `KERNEL32!LocalAlloc` at `0x180068b58`
- `SHELL32!SHGetFileInfoW` at `0x180068c49`
- `SHELL32!SHGetFileInfoW` at `0x180068c49`
- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x180068cab`
- `SHELL32!__imp_SHAddFromPropSheetExtArray` at `0x180068cab`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x180068d22`
- `SHELL32!__imp_SHDestroyPropSheetExtArray` at `0x180068d22`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x180068be7`
- `SHELL32!__imp_SHReplaceFromPropSheetExtArray` at `0x180068be7`

## pseudocode

```c
void __fastcall _DoStoragePropertySheet(
        struct PROPSHEETPARAMS *a1,
        struct IDataObject *a2,
        HWND a3,
        const unsigned __int16 *a4)
{
  struct PROPSHEETPARAMS *v6; // r13
  _QWORD *v8; // rdi
  HPSXA v9; // r14
  int v10; // eax
  _DWORD *v11; // rsi
  HKEY v12; // rcx
  __int64 v13; // r8
  UINT nPages; // ecx
  __int64 v15; // r15
  HLOCAL v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r13
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 PropertySheetPageW; // rax
  __int64 i; // r15
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  HGLOBAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  struct PROPSHEETPARAMS *v26; // [rsp+38h] [rbp-C8h]
  struct _PROPSHEETHEADERW_V2 lParam; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v28[14]; // [rsp+A0h] [rbp-60h] BYREF
  SHFILEINFOW psfi; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v30[100]; // [rsp+3D0h] [rbp+2D0h] BYREF

  v26 = a1;
  v6 = a1;
  v8 = 0;
  memset_0(v30, 0, sizeof(v30));
  hMem = 0;
  v9 = 0;
  memset_0(&psfi, 0, sizeof(psfi));
  memset_0(v28, 0, 0x68u);
  memset_0(&lParam, 0, sizeof(lParam));
  v10 = DataObj_CopyHIDA(a2, (struct _IDA **)&hMem);
  v11 = hMem;
  if ( v10 >= 0 )
  {
    v8 = LocalAlloc(0x40u, 8LL * *(unsigned int *)hMem);
    if ( v8 )
    {
      v9 = _SHCreatePropSheetExtArrayEx(v12, L"WPDPropSheet.Storage", v13, a2);
      lParam.hInstance = g_hInst;
      nPages = 0;
      lParam.pszCaption = a4;
      lParam.nPages = 0;
      v15 = 0;
      *(_QWORD *)&lParam.dwSize = 0x200008100000060LL;
      lParam.hwndParent = a3;
      lParam.ppsp = (LPCPROPSHEETPAGEW)v30;
      while ( (unsigned int)v15 < *v11 )
      {
        v16 = LocalAlloc(0x40u, 0x248u);
        v8[v15] = v16;
        if ( !v16 )
          goto LABEL_22;
        *(_QWORD *)(v8[v15] + 24LL) = IDA_ILClone(v11, (unsigned int)v15);
        v17 = v8[v15];
        if ( !*(_QWORD *)(v17 + 24) )
          goto LABEL_22;
        *(_QWORD *)(v17 + 8) = *(_QWORD *)v6;
        v18 = v8[v15];
        v19 = *(_QWORD *)(v18 + 8);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
        _InterlockedIncrement((volatile signed __int32 *)v18);
        *(_DWORD *)(v8[v15] + 52LL) = DataObj_GetDWORD(a2, g_cfWPD_ATTRIBUTES);
        if ( v9
          && SHReplaceFromPropSheetExtArray(
               v9,
               ((unsigned __int16)v15 << 16) | 2,
               _AddExtendedPropPage,
               (LPARAM)&lParam) )
        {
          nPages = lParam.nPages;
        }
        else
        {
          v28[1] = g_hInst;
          v28[0] = 104;
          v28[6] = v8[v15];
          v28[5] = StorageDlgProc;
          v28[2] = 827;
          if ( *v11 > 1u && SHGetFileInfoW(*(LPCWSTR *)(v8[v15] + 24LL), 0, &psfi, 0x2B8u, 0x208u) )
          {
            HIDWORD(v28[0]) |= 8u;
            v28[4] = psfi.szDisplayName;
          }
          nPages = lParam.nPages;
          if ( lParam.nPages < 0x64 )
          {
            v20 = lParam.nPages;
            PropertySheetPageW = IsolationAwareCreatePropertySheetPageW(v28);
            nPages = lParam.nPages + 1;
            v30[v20] = PropertySheetPageW;
            lParam.nPages = nPages;
          }
        }
        v6 = v26;
        v15 = (unsigned int)(v15 + 1);
      }
      if ( nPages )
      {
        if ( v9 )
          SHAddFromPropSheetExtArray(v9, _AddExtendedPropPage, (LPARAM)&lParam);
        ShellPropertySheet(&lParam);
      }
    }
  }
LABEL_22:
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
0x180068a34  mov     [rsp-8+arg_0], rbx
0x180068a39  push    rbp
0x180068a3a  push    rsi
0x180068a3b  push    rdi
0x180068a3c  push    r12
0x180068a3e  push    r13
0x180068a40  push    r14
0x180068a42  push    r15
0x180068a44  lea     rbp, [rsp-600h]
0x180068a4c  sub     rsp, 700h
0x180068a53  mov     rax, cs:__security_cookie
0x180068a5a  xor     rax, rsp
0x180068a5d  mov     [rbp+630h+var_40], rax
0x180068a64  mov     rbx, r8
0x180068a67  mov     [rsp+730h+var_6F8], rcx
0x180068a6c  mov     r12, rdx
0x180068a6f  mov     r13, rcx
0x180068a72  xor     edx, edx; Val
0x180068a74  lea     rcx, [rbp+630h+var_360]; void *
0x180068a7b  mov     r8d, 320h; Size
0x180068a81  mov     r15, r9
0x180068a84  xor     edi, edi
0x180068a86  call    memset_0
0x180068a8b  xor     edx, edx; Val
0x180068a8d  mov     [rsp+730h+hMem], rdi
0x180068a92  mov     r8d, 2B8h; Size
0x180068a98  lea     rcx, [rbp+630h+psfi]; void *
0x180068a9c  xor     r14d, r14d
0x180068a9f  call    memset_0
0x180068aa4  xor     edx, edx; Val
0x180068aa6  lea     r8d, [rdi+68h]; Size
0x180068aaa  lea     rcx, [rbp+630h+var_690]; void *
0x180068aae  call    memset_0
0x180068ab3  xor     edx, edx; Val
0x180068ab5  lea     r8d, [rdi+60h]; Size
0x180068ab9  lea     rcx, [rsp+730h+lParam]; void *
0x180068abe  call    memset_0
0x180068ac3  lea     rdx, [rsp+730h+hMem]; struct _IDA **
0x180068ac8  mov     rcx, r12; struct IDataObject *
0x180068acb  call    ?DataObj_CopyHIDA@@YAJPEAUIDataObject@@PEAPEAU_IDA@@@Z; DataObj_CopyHIDA(IDataObject *,_IDA * *)
0x180068ad0  mov     rsi, [rsp+730h+hMem]
0x180068ad5  test    eax, eax
0x180068ad7  js      loc_180068CBB
0x180068add  mov     edx, [rsi]
0x180068adf  lea     ecx, [rdi+40h]; uFlags
0x180068ae2  shl     rdx, 3; uBytes
0x180068ae6  call    cs:__imp_LocalAlloc
0x180068aec  mov     rdi, rax
0x180068aef  test    rax, rax
0x180068af2  jz      loc_180068CBB
0x180068af8  mov     r9, r12; struct IDataObject *
0x180068afb  lea     rdx, aWpdpropsheetSt; "WPDPropSheet.Storage"
0x180068b02  call    ?_SHCreatePropSheetExtArrayEx@@YAPEAUHPSXA__@@PEAUHKEY__@@PEBGIPEAUIDataObject@@@Z; _SHCreatePropSheetExtArrayEx(HKEY__ *,ushort const *,uint,IDataObject *)
0x180068b07  mov     rcx, cs:g_hInst
0x180068b0e  mov     r14, rax
0x180068b11  mov     [rsp+730h+var_6E0], rcx
0x180068b16  lea     rax, [rbp+630h+var_360]
0x180068b1d  xor     ecx, ecx
0x180068b1f  mov     [rsp+730h+var_6D0], r15
0x180068b24  mov     [rsp+730h+var_6C8], ecx
0x180068b28  xor     r15d, r15d
0x180068b2b  mov     dword ptr [rsp+730h+lParam], 60h ; '`'
0x180068b33  mov     dword ptr [rsp+730h+lParam+4], 2000081h
0x180068b3b  mov     [rsp+730h+var_6E8], rbx
0x180068b40  mov     [rsp+730h+var_6B8], rax
0x180068b45  cmp     r15d, [rsi]
0x180068b48  jnb     loc_180068C93
0x180068b4e  mov     edx, 248h; uBytes
0x180068b53  mov     ecx, 40h ; '@'; uFlags
0x180068b58  call    cs:__imp_LocalAlloc
0x180068b5e  mov     [rdi+r15*8], rax
0x180068b62  test    rax, rax
0x180068b65  jz      loc_180068CBB
0x180068b6b  mov     edx, r15d
0x180068b6e  mov     rcx, rsi
0x180068b71  call    IDA_ILClone
0x180068b76  mov     rcx, [rdi+r15*8]
0x180068b7a  mov     [rcx+18h], rax
0x180068b7e  mov     rcx, [rdi+r15*8]
0x180068b82  cmp     qword ptr [rcx+18h], 0
0x180068b87  jz      loc_180068CBB
0x180068b8d  mov     rax, [r13+0]
0x180068b91  mov     [rcx+8], rax
0x180068b95  mov     r13, [rdi+r15*8]
0x180068b99  mov     rcx, [r13+8]
0x180068b9d  test    rcx, rcx
0x180068ba0  jz      short loc_180068BAE
0x180068ba2  mov     rax, [rcx]
0x180068ba5  mov     rax, [rax+8]
0x180068ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068bae  lock inc dword ptr [r13+0]
0x180068bb3  movzx   edx, cs:?g_cfWPD_ATTRIBUTES@@3GA; ushort g_cfWPD_ATTRIBUTES
0x180068bba  mov     rcx, r12
0x180068bbd  call    DataObj_GetDWORD
0x180068bc2  mov     rcx, [rdi+r15*8]
0x180068bc6  mov     [rcx+34h], eax
0x180068bc9  test    r14, r14
0x180068bcc  jz      short loc_180068BFA
0x180068bce  movzx   edx, r15w
0x180068bd2  lea     r9, [rsp+730h+lParam]; lParam
0x180068bd7  shl     edx, 10h
0x180068bda  lea     r8, ?_AddExtendedPropPage@@YAHPEAU_PSP@@_J@Z; lpfnReplaceWith
0x180068be1  or      edx, 2; uPageID
0x180068be4  mov     rcx, r14; hpsxa
0x180068be7  call    cs:__imp_SHReplaceFromPropSheetExtArray
0x180068bed  test    eax, eax
0x180068bef  jz      short loc_180068BFA
0x180068bf1  mov     ecx, [rsp+730h+var_6C8]
0x180068bf5  jmp     loc_180068C86
0x180068bfa  mov     rax, cs:g_hInst
0x180068c01  mov     [rbp+630h+var_688], rax
0x180068c05  mov     [rbp+630h+var_690], 68h ; 'h'
0x180068c0d  mov     rax, [rdi+r15*8]
0x180068c11  mov     [rbp+630h+var_660], rax
0x180068c15  lea     rax, ?StorageDlgProc@@YA_JPEAUHWND__@@I_K_J@Z; StorageDlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180068c1c  mov     [rbp+630h+var_668], rax
0x180068c20  mov     [rbp+630h+var_680], 33Bh
0x180068c28  cmp     dword ptr [rsi], 1
0x180068c2b  jbe     short loc_180068C60
0x180068c2d  mov     rcx, [rdi+r15*8]
0x180068c31  lea     r8, [rbp+630h+psfi]; psfi
0x180068c35  mov     r9d, 2B8h; cbFileInfo
0x180068c3b  mov     [rsp+730h+uFlags], 208h; uFlags
0x180068c43  xor     edx, edx; dwFileAttributes
0x180068c45  mov     rcx, [rcx+18h]; pszPath
0x180068c49  call    cs:__imp_SHGetFileInfoW
0x180068c4f  test    rax, rax
0x180068c52  jz      short loc_180068C60
0x180068c54  or      dword ptr [rbp+630h+var_690+4], 8
0x180068c58  lea     rax, [rbp+630h+psfi.szDisplayName]
0x180068c5c  mov     [rbp+630h+var_670], rax
0x180068c60  mov     ecx, [rsp+730h+var_6C8]
0x180068c64  cmp     ecx, 64h ; 'd'
0x180068c67  jnb     short loc_180068C86
0x180068c69  mov     ebx, ecx
0x180068c6b  lea     rcx, [rbp+630h+var_690]
0x180068c6f  call    IsolationAwareCreatePropertySheetPageW
0x180068c74  mov     ecx, [rsp+730h+var_6C8]
0x180068c78  inc     ecx
0x180068c7a  mov     [rbp+rbx*8+630h+var_360], rax
0x180068c82  mov     [rsp+730h+var_6C8], ecx
0x180068c86  mov     r13, [rsp+730h+var_6F8]
0x180068c8b  inc     r15d
0x180068c8e  jmp     loc_180068B45
0x180068c93  test    ecx, ecx
0x180068c95  jz      short loc_180068CBB
0x180068c97  test    r14, r14
0x180068c9a  jz      short loc_180068CB1
0x180068c9c  lea     r8, [rsp+730h+lParam]; lParam
0x180068ca1  mov     rcx, r14; hpsxa
0x180068ca4  lea     rdx, ?_AddExtendedPropPage@@YAHPEAU_PSP@@_J@Z; lpfnAddPage
0x180068cab  call    cs:__imp_SHAddFromPropSheetExtArray
0x180068cb1  lea     rcx, [rsp+730h+lParam]; struct _PROPSHEETHEADERW_V2 *
0x180068cb6  call    ?ShellPropertySheet@@YA_JPEBU_PROPSHEETHEADERW_V2@@@Z; ShellPropertySheet(_PROPSHEETHEADERW_V2 const *)
0x180068cbb  test    rsi, rsi
0x180068cbe  jz      short loc_180068D1A
0x180068cc0  test    rdi, rdi
0x180068cc3  jz      short loc_180068D11
0x180068cc5  xor     r15d, r15d
0x180068cc8  cmp     [rsi], r15d
0x180068ccb  jbe     short loc_180068D08
0x180068ccd  mov     rbx, [rdi+r15*8]
0x180068cd1  test    rbx, rbx
0x180068cd4  jz      short loc_180068D00
0x180068cd6  mov     rcx, [rbx+8]
0x180068cda  test    rcx, rcx
0x180068cdd  jz      short loc_180068CEB
0x180068cdf  mov     rax, [rcx]
0x180068ce2  mov     rax, [rax+10h]
0x180068ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ceb  or      eax, 0FFFFFFFFh
0x180068cee  lock xadd [rbx], eax
0x180068cf2  cmp     eax, 1
0x180068cf5  jnz     short loc_180068D00
0x180068cf7  mov     rcx, rbx; hMem
0x180068cfa  call    cs:__imp_LocalFree
0x180068d00  inc     r15d
0x180068d03  cmp     r15d, [rsi]
0x180068d06  jb      short loc_180068CCD
0x180068d08  mov     rcx, rdi; hMem
0x180068d0b  call    cs:__imp_LocalFree
0x180068d11  mov     rcx, rsi; hMem
0x180068d14  call    cs:__imp_GlobalFree
0x180068d1a  test    r14, r14
0x180068d1d  jz      short loc_180068D28
0x180068d1f  mov     rcx, r14; hpsxa
0x180068d22  call    cs:__imp_SHDestroyPropSheetExtArray
0x180068d28  mov     rcx, [rbp+630h+var_40]
0x180068d2f  xor     rcx, rsp; StackCookie
0x180068d32  call    __security_check_cookie
0x180068d37  mov     rbx, [rsp+730h+arg_0]
0x180068d3f  add     rsp, 700h
0x180068d46  pop     r15
0x180068d48  pop     r14
0x180068d4a  pop     r13
0x180068d4c  pop     r12
0x180068d4e  pop     rdi
0x180068d4f  pop     rsi
0x180068d50  pop     rbp
0x180068d51  retn
```
