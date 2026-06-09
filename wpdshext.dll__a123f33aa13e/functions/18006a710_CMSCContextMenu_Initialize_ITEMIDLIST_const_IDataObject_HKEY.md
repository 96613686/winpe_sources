# CMSCContextMenu::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x18006a710`
- end: `0x18006a872`
- name: `?Initialize@CMSCContextMenu@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(CMSCContextMenu *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x18002e42c`
- `0x18002ff5c`
- `0x180035590`
- `0x1800361ba`
- `0x1800628cc`
- `0x180062e70`
- `0x18006a710`
- `0x18006aae0`
- `0x18006ac50`

## import_xrefs

- `KERNEL32!GetDriveTypeW` at `0x18006a7c8`
- `KERNEL32!GetDriveTypeW` at `0x18006a7c8`
- `SHELL32!SHGetPathFromIDListW` at `0x18006a7b9`
- `SHELL32!SHGetPathFromIDListW` at `0x18006a7b9`
- `SHELL32!__imp_ILFree` at `0x18006a809`
- `SHELL32!__imp_ILFree` at `0x18006a809`

## pseudocode

```c
__int64 __fastcall CMSCContextMenu::Initialize(
        CMSCContextMenu *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  int PIDL; // ebx
  _DWORD *v7; // rcx
  const ITEMIDLIST *v8; // rax
  ITEMIDLIST *v9; // rdi
  _DWORD *v11; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v12; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h]
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v15[264]; // [rsp+250h] [rbp+150h] BYREF

  v13 = 0;
  v11 = 0;
  v12 = 0;
  memset_0(pszPath, 0, 0x208u);
  memset_0(v15, 0, 0x208u);
  PIDL = SHGetItemArrayFromDataObj(a3, &v12, &v11);
  if ( PIDL < 0 )
    goto LABEL_11;
  v7 = v11;
  PIDL = -2147467259;
  if ( *v11 == 1 )
  {
    v8 = (const ITEMIDLIST *)IDA_ILClone(v11, 0);
    v9 = (ITEMIDLIST *)v8;
    if ( v8 )
    {
      if ( SHGetPathFromIDListW(v8, pszPath) )
      {
        if ( GetDriveTypeW(pszPath) == 2 )
        {
          PIDL = CMSCContextMenu::_MapDriveToPnPDevicePath((CMSCContextMenu *)((char *)this - 8), pszPath, v15, 260);
          if ( PIDL >= 0 )
            PIDL = CMSCContextMenu::_CreatePIDL((CMSCContextMenu *)((char *)this - 8), v15);
        }
      }
      ILFree(v9);
    }
  }
  ReleaseStgMediumHGLOBAL(v7, &v12);
  if ( PIDL < 0 )
  {
LABEL_11:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids,
        (unsigned int)PIDL);
  }
  return (unsigned int)PIDL;
}

```

## disassembly

```asm
0x18006a710  mov     [rsp-8+arg_8], rbx
0x18006a715  push    rbp
0x18006a716  push    rsi
0x18006a717  push    rdi
0x18006a718  lea     rbp, [rsp-370h]
0x18006a720  sub     rsp, 470h
0x18006a727  mov     rax, cs:__security_cookie
0x18006a72e  xor     rax, rsp
0x18006a731  mov     [rbp+380h+var_20], rax
0x18006a738  xor     eax, eax
0x18006a73a  mov     rbx, r8
0x18006a73d  mov     rsi, rcx
0x18006a740  mov     [rsp+480h+var_448], rax
0x18006a745  xorps   xmm0, xmm0
0x18006a748  mov     [rsp+480h+var_460], rax
0x18006a74d  mov     edi, 208h
0x18006a752  lea     rcx, [rsp+480h+pszPath]; void *
0x18006a757  mov     r8d, edi; Size
0x18006a75a  xor     edx, edx; Val
0x18006a75c  movups  [rsp+480h+var_458], xmm0
0x18006a761  call    memset_0
0x18006a766  mov     r8d, edi; Size
0x18006a769  lea     rcx, [rbp+380h+var_230]; void *
0x18006a770  xor     edx, edx; Val
0x18006a772  call    memset_0
0x18006a777  lea     r8, [rsp+480h+var_460]
0x18006a77c  mov     rcx, rbx
0x18006a77f  lea     rdx, [rsp+480h+var_458]
0x18006a784  call    SHGetItemArrayFromDataObj
0x18006a789  mov     ebx, eax
0x18006a78b  test    eax, eax
0x18006a78d  js      loc_18006A81D
0x18006a793  mov     rcx, [rsp+480h+var_460]
0x18006a798  mov     ebx, 80004005h
0x18006a79d  cmp     dword ptr [rcx], 1
0x18006a7a0  jnz     short loc_18006A80F
0x18006a7a2  xor     edx, edx
0x18006a7a4  call    IDA_ILClone
0x18006a7a9  mov     rdi, rax
0x18006a7ac  test    rax, rax
0x18006a7af  jz      short loc_18006A80F
0x18006a7b1  lea     rdx, [rsp+480h+pszPath]; pszPath
0x18006a7b6  mov     rcx, rax; pidl
0x18006a7b9  call    cs:__imp_SHGetPathFromIDListW
0x18006a7bf  test    eax, eax
0x18006a7c1  jz      short loc_18006A806
0x18006a7c3  lea     rcx, [rsp+480h+pszPath]; lpRootPathName
0x18006a7c8  call    cs:__imp_GetDriveTypeW
0x18006a7ce  cmp     eax, 2
0x18006a7d1  jnz     short loc_18006A806
0x18006a7d3  mov     r9d, 104h; unsigned int
0x18006a7d9  lea     r8, [rbp+380h+var_230]; unsigned __int16 *
0x18006a7e0  lea     rdx, [rsp+480h+pszPath]; unsigned __int16 *
0x18006a7e5  lea     rcx, [rsi-8]; this
0x18006a7e9  call    ?_MapDriveToPnPDevicePath@CMSCContextMenu@@AEAAJPEBGPEAGI@Z; CMSCContextMenu::_MapDriveToPnPDevicePath(ushort const *,ushort *,uint)
0x18006a7ee  mov     ebx, eax
0x18006a7f0  test    eax, eax
0x18006a7f2  js      short loc_18006A806
0x18006a7f4  lea     rdx, [rbp+380h+var_230]; unsigned __int16 *
0x18006a7fb  lea     rcx, [rsi-8]; this
0x18006a7ff  call    ?_CreatePIDL@CMSCContextMenu@@AEAAJPEBG@Z; CMSCContextMenu::_CreatePIDL(ushort const *)
0x18006a804  mov     ebx, eax
0x18006a806  mov     rcx, rdi; pidl
0x18006a809  call    cs:__imp_ILFree
0x18006a80f  lea     rdx, [rsp+480h+var_458]
0x18006a814  call    ReleaseStgMediumHGLOBAL
0x18006a819  test    ebx, ebx
0x18006a81b  jns     short loc_18006A84E
0x18006a81d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a824  lea     rax, WPP_GLOBAL_Control
0x18006a82b  cmp     rcx, rax
0x18006a82e  jz      short loc_18006A84E
0x18006a830  test    byte ptr [rcx+1Ch], 2
0x18006a834  jz      short loc_18006A84E
0x18006a836  mov     rcx, [rcx+10h]
0x18006a83a  lea     r8, WPP_e3383bc4167e3a1fca8723e1fe0517f0_Traceguids
0x18006a841  mov     edx, 0Bh
0x18006a846  mov     r9d, ebx
0x18006a849  call    WPP_SF_d
0x18006a84e  mov     eax, ebx
0x18006a850  mov     rcx, [rbp+380h+var_20]
0x18006a857  xor     rcx, rsp; StackCookie
0x18006a85a  call    __security_check_cookie
0x18006a85f  mov     rbx, [rsp+480h+arg_8]
0x18006a867  add     rsp, 470h
0x18006a86e  pop     rdi
0x18006a86f  pop     rsi
0x18006a870  pop     rbp
0x18006a871  retn
```
