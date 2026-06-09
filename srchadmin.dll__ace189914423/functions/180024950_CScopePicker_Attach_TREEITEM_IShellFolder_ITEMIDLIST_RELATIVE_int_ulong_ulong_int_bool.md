# CScopePicker::_Attach(_TREEITEM *,IShellFolder *,_ITEMIDLIST_RELATIVE *,int,ulong,ulong,int,bool)

- ea: `0x180024950`
- end: `0x180024c6e`
- name: `?_Attach@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAUIShellFolder@@PEAU_ITEMIDLIST_RELATIVE@@HKKH_N@Z`
- size: `798`
- prototype: `int(CScopePicker *__hidden this, struct _TREEITEM *, struct IShellFolder *, struct _ITEMIDLIST_RELATIVE *, int, unsigned int, unsigned int, int, bool)`
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180024de8`
- `0x180025b24`

## callees

- `0x180005cc0`
- `0x18000687c`
- `0x18001a7fc`
- `0x180024234`
- `0x180024950`
- `0x180024f0c`
- `0x1800251d0`
- `0x180026b10`
- `0x18002cda8`
- `0x18002d17c`
- `0x180032010`

## import_xrefs

- `SHELL32!__imp_ILFindLastID` at `0x180024a42`
- `SHELL32!__imp_ILFindLastID` at `0x180024a42`
- `SHELL32!__imp_ILCombine` at `0x1800249a5`
- `SHELL32!__imp_ILCombine` at `0x1800249dd`
- `SHELL32!__imp_ILCombine` at `0x1800249a5`
- `SHELL32!__imp_ILCombine` at `0x1800249dd`
- `SHELL32!__imp_ILFree` at `0x1800249eb`
- `SHELL32!__imp_ILFree` at `0x180024c44`
- `SHELL32!__imp_ILFree` at `0x1800249eb`
- `SHELL32!__imp_ILFree` at `0x180024c44`
- `SHLWAPI!StrRetToBufW` at `0x180024a7e`
- `SHLWAPI!StrRetToBufW` at `0x180024a7e`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180024be6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SendMessageW` at `0x180024be6`

## pseudocode

```c
__int64 __fastcall CScopePicker::_Attach(
        HWND *this,
        struct _TREEITEM *a2,
        struct IShellFolder *a3,
        const ITEMIDLIST *a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        bool a9)
{
  CShellWrappers *v12; // rcx
  struct _ITEMIDLIST_ABSOLUTE *v13; // r15
  int PidlAbs; // esi
  int v15; // eax
  struct IShellFolder *v16; // rsi
  const ITEMIDLIST *ID; // rdi
  HRESULT DisplayNameFromAbsPidl; // eax
  char *v19; // rax
  STreeNodeState *v20; // rdi
  unsigned int v21; // r14d
  HWND v22; // rcx
  LRESULT v23; // rax
  unsigned int v24; // edx
  __int64 v25; // r8
  LPCITEMIDLIST pidl1; // [rsp+30h] [rbp-D0h] BYREF
  int v28; // [rsp+38h] [rbp-C8h] BYREF
  int v29; // [rsp+3Ch] [rbp-C4h]
  struct IShellFolder *v30; // [rsp+40h] [rbp-C0h]
  const ITEMIDLIST *v31; // [rsp+48h] [rbp-B8h]
  LPARAM lParam[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+74h] [rbp-8Ch]
  WCHAR *v36; // [rsp+78h] [rbp-88h]
  int v37; // [rsp+84h] [rbp-7Ch]
  int v38; // [rsp+88h] [rbp-78h]
  int v39; // [rsp+8Ch] [rbp-74h]
  STreeNodeState *v40; // [rsp+90h] [rbp-70h]
  STRRET pstr; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR pszBuf[264]; // [rsp+1C0h] [rbp+C0h] BYREF

  v31 = a4;
  v30 = a3;
  if ( a2 == (struct _TREEITEM *)-65536LL )
  {
    v29 = 1;
    v13 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(0, a4);
  }
  else
  {
    pidl1 = 0;
    PidlAbs = CScopePicker::_GetPidlAbs((CScopePicker *)this, a2, (struct _ITEMIDLIST_ABSOLUTE **)&pidl1);
    if ( PidlAbs < 0 )
    {
      v13 = 0;
      v28 = -1;
      goto LABEL_30;
    }
    v29 = 0;
    v13 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(pidl1, a4);
    ILFree((LPITEMIDLIST)pidl1);
  }
  LODWORD(pidl1) = 0;
  if ( (a7 & 0x8000) == 0 )
  {
    v15 = CScopePicker::_CheckChildren((CScopePicker *)this, v13);
    PidlAbs = v15;
    if ( v15 )
    {
      if ( v15 < 0 )
        goto LABEL_14;
    }
    else
    {
      LODWORD(pidl1) = 1;
    }
  }
  v16 = v30;
  if ( !v30 )
  {
    DisplayNameFromAbsPidl = CShellWrappers::GetDisplayNameFromAbsPidl(v12, v13, pszBuf, 1);
    goto LABEL_13;
  }
  memset_0(&pstr, 0, sizeof(pstr));
  ID = ILFindLastID(a4);
  PidlAbs = ((__int64 (__fastcall *)(struct IShellFolder *, const ITEMIDLIST *, _QWORD, STRRET *))v16->lpVtbl->GetDisplayNameOf)(
              v16,
              ID,
              0,
              &pstr);
  if ( PidlAbs >= 0 )
  {
    DisplayNameFromAbsPidl = StrRetToBufW(&pstr, ID, pszBuf, 0x104u);
LABEL_13:
    PidlAbs = DisplayNameFromAbsPidl;
  }
LABEL_14:
  v28 = -1;
  if ( PidlAbs >= 0 )
  {
    PidlAbs = CShellWrappers::GetIconFromAbsPidl((CShellWrappers *)(this + 218), v13, &v28);
    if ( PidlAbs >= 0 )
    {
      v19 = (char *)operator new(0x30u);
      v30 = (struct IShellFolder *)v19;
      v20 = (STreeNodeState *)v19;
      if ( v19 )
      {
        *(_QWORD *)v19 = 0;
        *((_QWORD *)v19 + 1) = 0;
        *((_QWORD *)v19 + 2) = 0;
        *((_DWORD *)v19 + 6) = 0;
        *(_QWORD *)(v19 + 28) = 1;
        *((_DWORD *)v19 + 9) = 0;
        v19[44] = 0;
        *(_QWORD *)v19 = v31;
        *((_DWORD *)v19 + 9) = a8;
        *((_DWORD *)v19 + 10) = v29;
        v19[44] = a9;
        *((_DWORD *)v19 + 5) = a6;
        *((_DWORD *)v19 + 6) = a7;
        memset_0(lParam, 0, 0x60u);
        lParam[0] = (LPARAM)a2;
        lParam[1] = -65534;
        v33 = 103;
        if ( (a6 & 0x2000) != 0
          || (a6 & 2) != 0 && a2 != (struct _TREEITEM *)-65536LL
          || (v21 = a7 & 0x8000, (a7 & 0x8000) != 0) )
        {
          v33 = 111;
          v35 = 4;
          v34 = 4;
          v21 = a7 & 0x8000;
        }
        v22 = this[3];
        v36 = pszBuf;
        v39 = (int)pidl1;
        v37 = v28;
        v38 = v28;
        v40 = v20;
        v23 = SendMessageW(v22, 0x1132u, 0, (LPARAM)lParam);
        if ( v23 )
        {
          PidlAbs = 0;
          if ( v21 )
            v25 = 0;
          else
            v25 = (unsigned int)(a5 != 0) + 1;
          CScopePicker::_UpdateStateIcon(this, v23, v25);
        }
        else
        {
          PidlAbs = -2147467259;
          STreeNodeState::`scalar deleting destructor'(v20, v24);
        }
      }
      else
      {
        PidlAbs = -2147024882;
      }
    }
  }
LABEL_30:
  ILFree((LPITEMIDLIST)v13);
  return (unsigned int)PidlAbs;
}

```

## disassembly

```asm
0x180024950  push    rbp
0x180024952  push    rsi
0x180024953  push    rdi
0x180024954  push    r12
0x180024956  push    r13
0x180024958  push    r14
0x18002495a  push    r15
0x18002495c  lea     rbp, [rsp-2E0h]
0x180024964  sub     rsp, 3E0h
0x18002496b  mov     rax, cs:__security_cookie
0x180024972  xor     rax, rsp
0x180024975  mov     [rbp+310h+var_40], rax
0x18002497c  mov     [rsp+410h+var_3C8], r9
0x180024981  mov     rdi, r9
0x180024984  mov     [rsp+410h+var_3D0], r8
0x180024989  mov     r14, rdx
0x18002498c  mov     r13, rcx
0x18002498f  cmp     rdx, 0FFFFFFFFFFFF0000h
0x180024996  jnz     short loc_1800249B0
0x180024998  mov     rdx, r9; pidl2
0x18002499b  mov     [rsp+410h+var_3D4], 1
0x1800249a3  xor     ecx, ecx; pidl1
0x1800249a5  call    cs:__imp_ILCombine
0x1800249ab  mov     r15, rax
0x1800249ae  jmp     short loc_1800249F1
0x1800249b0  lea     r8, [rsp+410h+pidl1]; struct _ITEMIDLIST_ABSOLUTE **
0x1800249b5  mov     [rsp+410h+pidl1], 0
0x1800249be  call    ?_GetPidlAbs@CScopePicker@@AEAAJPEAU_TREEITEM@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_GetPidlAbs(_TREEITEM *,_ITEMIDLIST_ABSOLUTE * *)
0x1800249c3  mov     esi, eax
0x1800249c5  test    eax, eax
0x1800249c7  js      loc_180024C36
0x1800249cd  mov     rcx, [rsp+410h+pidl1]; pidl1
0x1800249d2  mov     rdx, rdi; pidl2
0x1800249d5  mov     [rsp+410h+var_3D4], 0
0x1800249dd  call    cs:__imp_ILCombine
0x1800249e3  mov     rcx, [rsp+410h+pidl1]; pidl
0x1800249e8  mov     r15, rax
0x1800249eb  call    cs:__imp_ILFree
0x1800249f1  mov     r12d, [rbp+310h+arg_30]
0x1800249f8  mov     dword ptr [rsp+410h+pidl1], 0
0x180024a00  bt      r12d, 0Fh
0x180024a05  jb      short loc_180024A24
0x180024a07  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180024a0a  mov     rcx, r13; this
0x180024a0d  call    ?_CheckChildren@CScopePicker@@AEAAJPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CScopePicker::_CheckChildren(_ITEMIDLIST_ABSOLUTE *)
0x180024a12  mov     esi, eax
0x180024a14  test    eax, eax
0x180024a16  jnz     short loc_180024A22
0x180024a18  mov     dword ptr [rsp+410h+pidl1], 1
0x180024a20  jmp     short loc_180024A24
0x180024a22  js      short loc_180024A9D
0x180024a24  mov     rsi, [rsp+410h+var_3D0]
0x180024a29  test    rsi, rsi
0x180024a2c  jz      short loc_180024A86
0x180024a2e  xor     edx, edx; Val
0x180024a30  lea     rcx, [rbp+310h+pstr]; void *
0x180024a34  mov     r8d, 110h; Size
0x180024a3a  call    memset_0
0x180024a3f  mov     rcx, rdi; pidl
0x180024a42  call    cs:__imp_ILFindLastID
0x180024a48  mov     rcx, [rsi]
0x180024a4b  lea     r9, [rbp+310h+pstr]
0x180024a4f  mov     rdi, rax
0x180024a52  xor     r8d, r8d
0x180024a55  mov     rdx, rdi
0x180024a58  mov     rax, [rcx+58h]
0x180024a5c  mov     rcx, rsi
0x180024a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a64  mov     esi, eax
0x180024a66  test    eax, eax
0x180024a68  js      short loc_180024A9D
0x180024a6a  mov     r9d, 104h; cchBuf
0x180024a70  lea     r8, [rbp+310h+pszBuf]; pszBuf
0x180024a77  mov     rdx, rdi; pidl
0x180024a7a  lea     rcx, [rbp+310h+pstr]; pstr
0x180024a7e  call    cs:__imp_StrRetToBufW
0x180024a84  jmp     short loc_180024A9B
0x180024a86  mov     r9d, 1; int
0x180024a8c  lea     r8, [rbp+310h+pszBuf]; unsigned __int16 *
0x180024a93  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180024a96  call    ?GetDisplayNameFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAGH@Z; CShellWrappers::GetDisplayNameFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,ushort *,int)
0x180024a9b  mov     esi, eax
0x180024a9d  mov     [rsp+410h+var_3D8], 0FFFFFFFFh
0x180024aa5  test    esi, esi
0x180024aa7  js      loc_180024C41
0x180024aad  lea     rcx, [r13+6D0h]; this
0x180024ab4  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180024ab7  lea     r8, [rsp+410h+var_3D8]; int *
0x180024abc  call    ?GetIconFromAbsPidl@CShellWrappers@@QEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAH@Z; CShellWrappers::GetIconFromAbsPidl(_ITEMIDLIST_ABSOLUTE const *,int *)
0x180024ac1  mov     esi, eax
0x180024ac3  test    eax, eax
0x180024ac5  js      loc_180024C41
0x180024acb  mov     ecx, 30h ; '0'; unsigned __int64
0x180024ad0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180024ad5  mov     [rsp+410h+var_3D0], rax
0x180024ada  mov     rdi, rax
0x180024add  test    rax, rax
0x180024ae0  jz      loc_180024C20
0x180024ae6  mov     qword ptr [rax], 0
0x180024aed  mov     qword ptr [rax+8], 0
0x180024af5  mov     qword ptr [rax+10h], 0
0x180024afd  mov     dword ptr [rax+18h], 0
0x180024b04  mov     qword ptr [rax+1Ch], 1
0x180024b0c  mov     dword ptr [rax+24h], 0
0x180024b13  mov     byte ptr [rax+2Ch], 0
0x180024b17  test    rax, rax
0x180024b1a  jz      loc_180024C22
0x180024b20  mov     rax, [rsp+410h+var_3C8]
0x180024b25  lea     rcx, [rsp+410h+lParam]; void *
0x180024b2a  mov     esi, [rbp+310h+arg_28]
0x180024b30  xor     edx, edx; Val
0x180024b32  mov     [rdi], rax
0x180024b35  mov     eax, [rbp+310h+arg_38]
0x180024b3b  mov     [rdi+24h], eax
0x180024b3e  mov     eax, [rsp+410h+var_3D4]
0x180024b42  lea     r8d, [rdx+60h]; Size
0x180024b46  mov     [rdi+28h], eax
0x180024b49  mov     al, [rbp+310h+arg_40]
0x180024b4f  mov     [rdi+2Ch], al
0x180024b52  mov     [rdi+14h], esi
0x180024b55  mov     [rdi+18h], r12d
0x180024b59  call    memset_0
0x180024b5e  mov     [rsp+410h+lParam], r14
0x180024b63  mov     [rsp+410h+var_3B8], 0FFFFFFFFFFFF0002h
0x180024b6c  mov     [rsp+410h+var_3B0], 67h ; 'g'
0x180024b74  bt      esi, 0Dh
0x180024b78  jb      short loc_180024B95
0x180024b7a  test    sil, 2
0x180024b7e  jz      short loc_180024B89
0x180024b80  cmp     r14, 0FFFFFFFFFFFF0000h
0x180024b87  jnz     short loc_180024B95
0x180024b89  mov     r14d, r12d
0x180024b8c  and     r14d, 8000h
0x180024b93  jz      short loc_180024BB4
0x180024b95  mov     eax, 4
0x180024b9a  mov     [rsp+410h+var_3B0], 6Fh ; 'o'
0x180024ba2  mov     r14d, r12d
0x180024ba5  mov     [rsp+410h+var_39C], eax
0x180024ba9  mov     [rsp+410h+var_3A0], eax
0x180024bad  and     r14d, 8000h
0x180024bb4  mov     rcx, [r13+18h]; hWnd
0x180024bb8  lea     rax, [rbp+310h+pszBuf]
0x180024bbf  mov     [rsp+410h+var_398], rax
0x180024bc4  lea     r9, [rsp+410h+lParam]; lParam
0x180024bc9  mov     eax, dword ptr [rsp+410h+pidl1]
0x180024bcd  xor     r8d, r8d; wParam
0x180024bd0  mov     [rbp+310h+var_384], eax
0x180024bd3  mov     edx, 1132h; Msg
0x180024bd8  mov     eax, [rsp+410h+var_3D8]
0x180024bdc  mov     [rbp+310h+var_38C], eax
0x180024bdf  mov     [rbp+310h+var_388], eax
0x180024be2  mov     [rbp+310h+var_380], rdi
0x180024be6  call    cs:__imp_SendMessageW
0x180024bec  test    rax, rax
0x180024bef  jz      short loc_180024C19
0x180024bf1  xor     esi, esi
0x180024bf3  mov     rdx, rax
0x180024bf6  mov     rcx, r13
0x180024bf9  test    r14d, r14d
0x180024bfc  jz      short loc_180024C03
0x180024bfe  xor     r8d, r8d
0x180024c01  jmp     short loc_180024C12
0x180024c03  neg     [rbp+310h+arg_20]
0x180024c09  sbb     r8d, r8d
0x180024c0c  neg     r8d
0x180024c0f  inc     r8d
0x180024c12  call    ?_UpdateStateIcon@CScopePicker@@AEAAXPEAU_TREEITEM@@W4_TREE_ITEM_CHECK@@@Z; CScopePicker::_UpdateStateIcon(_TREEITEM *,_TREE_ITEM_CHECK)
0x180024c17  jmp     short loc_180024C41
0x180024c19  mov     esi, 80004005h
0x180024c1e  jmp     short loc_180024C2C
0x180024c20  xor     edi, edi
0x180024c22  mov     esi, 8007000Eh
0x180024c27  test    rdi, rdi
0x180024c2a  jz      short loc_180024C41
0x180024c2c  mov     rcx, rdi; this
0x180024c2f  call    ??_GSTreeNodeState@@QEAAPEAXI@Z; STreeNodeState::`scalar deleting destructor'(uint)
0x180024c34  jmp     short loc_180024C41
0x180024c36  xor     r15d, r15d
0x180024c39  mov     [rsp+410h+var_3D8], 0FFFFFFFFh
0x180024c41  mov     rcx, r15; pidl
0x180024c44  call    cs:__imp_ILFree
0x180024c4a  mov     eax, esi
0x180024c4c  mov     rcx, [rbp+310h+var_40]
0x180024c53  xor     rcx, rsp; StackCookie
0x180024c56  call    __security_check_cookie
0x180024c5b  add     rsp, 3E0h
0x180024c62  pop     r15
0x180024c64  pop     r14
0x180024c66  pop     r13
0x180024c68  pop     r12
0x180024c6a  pop     rdi
0x180024c6b  pop     rsi
0x180024c6c  pop     rbp
0x180024c6d  retn
```
