# CIndexedLocationsBasket::ConsumeOrphanRoot(ushort const *)

- ea: `0x180014ab0`
- end: `0x180014bbf`
- name: `?ConsumeOrphanRoot@CIndexedLocationsBasket@@UEAAJPEBG@Z`
- size: `271`
- prototype: `__int64 __fastcall(CIndexedLocationsBasket *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180003ac8`
- `0x180005cc0`
- `0x18000d424`
- `0x180014ab0`
- `0x180016aa0`
- `0x18002c980`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x180014b90`
- `SHELL32!__imp_ILFree` at `0x180014b90`
- `SHLWAPI!UrlIsW` at `0x180014aec`
- `SHLWAPI!UrlIsW` at `0x180014aec`
- `SHLWAPI!PathCreateFromUrlW` at `0x180014b2e`
- `SHLWAPI!PathCreateFromUrlW` at `0x180014b2e`

## pseudocode

```c
__int64 __fastcall CIndexedLocationsBasket::ConsumeOrphanRoot(
        CIndexedLocationsBasket *this,
        const unsigned __int16 *a2)
{
  HRESULT AbsPidlFromPath; // ebx
  bool v5; // al
  DWORD pcchPath; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  AbsPidlFromPath = 0;
  if ( !UrlIsW(a2, URLIS_FILEURL) )
    return (unsigned int)AbsPidlFromPath;
  pidl = 0;
  AbsPidlFromPath = CShellWrappers::GetAbsPidlFromPath(
                      (CIndexedLocationsBasket *)((char *)this + 40),
                      a2,
                      (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
  if ( AbsPidlFromPath < 0 )
  {
    v5 = 1;
  }
  else
  {
    pcchPath = 260;
    AbsPidlFromPath = PathCreateFromUrlW(a2, pszPath, &pcchPath, 0);
    if ( AbsPidlFromPath < 0 )
    {
LABEL_9:
      ILFree(pidl);
      return (unsigned int)AbsPidlFromPath;
    }
    v5 = IsVolumeInaccessible(pszPath[0]);
  }
  if ( !v5 )
    goto LABEL_9;
  pcchPath = 0;
  AbsPidlFromPath = CShellWrappers::GetOfflineDisplayProperties(
                      (CIndexedLocationsBasket *)((char *)this + 40),
                      a2,
                      pszPath,
                      (int *)&pcchPath);
  if ( AbsPidlFromPath >= 0 )
    CIndexedLocationsBasket::_InsertListViewItem(
      (CIndexedLocationsBasket *)((char *)this - 8),
      pcchPath,
      pszPath,
      a2,
      pcchPath);
  return (unsigned int)AbsPidlFromPath;
}

```

## disassembly

```asm
0x180014ab0  mov     [rsp-8+arg_10], rbx
0x180014ab5  mov     [rsp-8+arg_18], rsi
0x180014aba  push    rbp
0x180014abb  push    rdi
0x180014abc  push    r14
0x180014abe  lea     rbp, [rsp-160h]
0x180014ac6  sub     rsp, 260h
0x180014acd  mov     rax, cs:__security_cookie
0x180014ad4  xor     rax, rsp
0x180014ad7  mov     [rbp+170h+var_20], rax
0x180014ade  mov     rdi, rdx
0x180014ae1  mov     r14, rcx
0x180014ae4  xor     ebx, ebx
0x180014ae6  mov     rcx, rdi; pszUrl
0x180014ae9  lea     edx, [rbx+3]; UrlIs
0x180014aec  call    cs:__imp_UrlIsW
0x180014af2  test    eax, eax
0x180014af4  jz      loc_180014B96
0x180014afa  lea     r8, [rsp+270h+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180014aff  mov     [rsp+270h+pidl], rbx
0x180014b04  mov     rdx, rdi; unsigned __int16 *
0x180014b07  lea     rcx, [r14+28h]; this
0x180014b0b  call    ?GetAbsPidlFromPath@CShellWrappers@@QEAAJPEBGPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CShellWrappers::GetAbsPidlFromPath(ushort const *,_ITEMIDLIST_ABSOLUTE * *)
0x180014b10  mov     ebx, eax
0x180014b12  test    eax, eax
0x180014b14  js      short loc_180014B46
0x180014b16  xor     r9d, r9d; dwFlags
0x180014b19  mov     [rsp+270h+pcchPath], 104h
0x180014b21  lea     r8, [rsp+270h+pcchPath]; pcchPath
0x180014b26  mov     rcx, rdi; pszUrl
0x180014b29  lea     rdx, [rsp+270h+pszPath]; pszPath
0x180014b2e  call    cs:__imp_PathCreateFromUrlW
0x180014b34  mov     ebx, eax
0x180014b36  test    eax, eax
0x180014b38  js      short loc_180014B8B
0x180014b3a  movzx   ecx, [rsp+270h+pszPath]; unsigned __int16
0x180014b3f  call    ?IsVolumeInaccessible@@YA_NG@Z; IsVolumeInaccessible(ushort)
0x180014b44  jmp     short loc_180014B48
0x180014b46  mov     al, 1
0x180014b48  test    al, al
0x180014b4a  jz      short loc_180014B8B
0x180014b4c  lea     r9, [rsp+270h+pcchPath]; int *
0x180014b51  mov     [rsp+270h+pcchPath], 0
0x180014b59  lea     r8, [rsp+270h+pszPath]; unsigned __int16 *
0x180014b5e  mov     rdx, rdi; unsigned __int16 *
0x180014b61  lea     rcx, [r14+28h]; this
0x180014b65  call    ?GetOfflineDisplayProperties@CShellWrappers@@QEBAJPEBGPEAGPEAH@Z; CShellWrappers::GetOfflineDisplayProperties(ushort const *,ushort *,int *)
0x180014b6a  mov     ebx, eax
0x180014b6c  test    eax, eax
0x180014b6e  js      short loc_180014B96
0x180014b70  mov     edx, [rsp+270h+pcchPath]; int
0x180014b74  lea     rcx, [r14-8]; this
0x180014b78  mov     r9, rdi; unsigned __int16 *
0x180014b7b  mov     [rsp+270h+var_250], edx; int
0x180014b7f  lea     r8, [rsp+270h+pszPath]; unsigned __int16 *
0x180014b84  call    ?_InsertListViewItem@CIndexedLocationsBasket@@AEAAXHPEBG0H@Z; CIndexedLocationsBasket::_InsertListViewItem(int,ushort const *,ushort const *,int)
0x180014b89  jmp     short loc_180014B96
0x180014b8b  mov     rcx, [rsp+270h+pidl]; pidl
0x180014b90  call    cs:__imp_ILFree
0x180014b96  mov     eax, ebx
0x180014b98  mov     rcx, [rbp+170h+var_20]
0x180014b9f  xor     rcx, rsp; StackCookie
0x180014ba2  call    __security_check_cookie
0x180014ba7  lea     r11, [rsp+270h+var_10]
0x180014baf  mov     rbx, [r11+30h]
0x180014bb3  mov     rsi, [r11+38h]
0x180014bb7  mov     rsp, r11
0x180014bba  pop     r14
0x180014bbc  pop     rdi
0x180014bbd  pop     rbp
0x180014bbe  retn
```
