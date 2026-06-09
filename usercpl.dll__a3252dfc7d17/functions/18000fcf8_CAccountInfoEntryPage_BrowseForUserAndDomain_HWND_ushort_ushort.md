# CAccountInfoEntryPage::_BrowseForUserAndDomain(HWND__ *,ushort * *,ushort * *)

- ea: `0x18000fcf8`
- end: `0x18000ffab`
- name: `?_BrowseForUserAndDomain@CAccountInfoEntryPage@@AEAAJPEAUHWND__@@PEAPEAG1@Z`
- size: `691`
- prototype: `__int64 __fastcall(CAccountInfoEntryPage *this, HWND, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000f840`

## callees

- `0x18000fcf8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000fea3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000ff1d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000ff2f`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000fea3`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000ff1d`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18000ff2f`
- `SHLWAPI!StrChrW` at `0x18000feda`
- `SHLWAPI!StrChrW` at `0x18000ff07`
- `SHLWAPI!StrChrW` at `0x18000feda`
- `SHLWAPI!StrChrW` at `0x18000ff07`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18000fec4`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18000fec4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ff41`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fdb8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000fdb8`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fef2`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000fef2`
- `KERNEL32!GlobalLock` at `0x18000fe7b`
- `KERNEL32!GlobalLock` at `0x18000fe7b`
- `KERNEL32!GlobalUnlock` at `0x18000ff52`
- `KERNEL32!GlobalUnlock` at `0x18000ff52`
- `USER32!RegisterClipboardFormatW` at `0x18000fe2e`
- `USER32!RegisterClipboardFormatW` at `0x18000fe2e`

## pseudocode

```c
__int64 __fastcall CAccountInfoEntryPage::_BrowseForUserAndDomain(
        CAccountInfoEntryPage *this,
        HWND a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  HRESULT v7; // ebx
  int v8; // eax
  __int64 v9; // rcx
  LPVOID v10; // rax
  const WCHAR *v11; // rcx
  LPWSTR v12; // rdi
  const WCHAR *v13; // rax
  const WCHAR *v14; // rbx
  const WCHAR *v15; // rax
  const WCHAR *v16; // rsi
  PWSTR v17; // rax
  LPWSTR v18; // rcx
  LPWSTR ppwsz; // [rsp+30h] [rbp-99h] BYREF
  __int64 v21; // [rsp+38h] [rbp-91h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-89h] BYREF
  __int128 v23; // [rsp+48h] [rbp-81h] BYREF
  __int128 v24; // [rsp+58h] [rbp-71h]
  HGLOBAL hMem[2]; // [rsp+68h] [rbp-61h] BYREF
  __int64 v26; // [rsp+78h] [rbp-51h]
  _QWORD v27[4]; // [rsp+80h] [rbp-49h] BYREF
  int v28; // [rsp+A0h] [rbp-29h]
  __int64 v29; // [rsp+A4h] [rbp-25h]
  int v30; // [rsp+ACh] [rbp-1Dh]
  _DWORD v31[3]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v32; // [rsp+BCh] [rbp-Dh]
  int v33; // [rsp+C4h] [rbp-5h]
  int v34; // [rsp+C8h] [rbp-1h]
  int v35; // [rsp+CCh] [rbp+3h]
  __int64 v36; // [rsp+D0h] [rbp+7h]
  __int64 v37; // [rsp+D8h] [rbp+Fh]
  int v38; // [rsp+E0h] [rbp+17h]
  int v39; // [rsp+E4h] [rbp+1Bh]

  v31[0] = 56;
  *a3 = 0;
  *a4 = 0;
  v35 = 0;
  v39 = 0;
  v31[2] = 2;
  v32 = 2;
  v31[1] = 888;
  v27[3] = v31;
  v34 = -2147483647;
  v33 = 0;
  v37 = 0;
  v36 = 0;
  v38 = -2147467259;
  v27[0] = 48;
  v27[2] = 1;
  v29 = 0;
  v30 = 0;
  v27[1] = 0;
  v28 = 0;
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_DsObjectPicker, 0, 1u, &IID_IDsObjectPicker, &ppv);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v27);
    if ( v7 >= 0 )
    {
      v21 = 0;
      v8 = (*(__int64 (__fastcall **)(LPVOID, HWND, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, a2, &v21);
      v9 = v21;
      if ( v8 || !v21 )
      {
        v7 = -2147467259;
      }
      else
      {
        v23 = 0;
        v24 = 0;
        LOWORD(v23) = RegisterClipboardFormatW(L"CFSTR_DSOP_DS_SELECTION_LIST");
        *(_QWORD *)&v24 = 0xFFFFFFFF00000001uLL;
        v26 = 0;
        DWORD2(v24) = 1;
        *(_OWORD *)hMem = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, HGLOBAL *))(*(_QWORD *)v21 + 24LL))(v21, &v23, hMem);
        if ( v7 >= 0 )
        {
          v10 = GlobalLock(hMem[1]);
          if ( v10 )
          {
            v7 = 0;
            if ( *(_DWORD *)v10 )
            {
              v11 = (const WCHAR *)*((_QWORD *)v10 + 2);
              ppwsz = 0;
              v7 = SHStrDupW(v11, &ppwsz);
              if ( v7 >= 0 && !StrCmpNICW(ppwsz, L"WinNT://", 8) )
              {
                v12 = ppwsz;
                v13 = StrChrW(ppwsz + 8, 0x2Fu);
                v14 = v13;
                if ( v13 )
                {
                  v15 = CharNextW(v13);
                  *v14 = 0;
                  v16 = v15;
                  v17 = StrChrW(v15, 0x2Fu);
                  if ( v17 )
                    *v17 = 0;
                  v7 = SHStrDupW(v12 + 8, a4);
                  if ( v7 >= 0 )
                    v7 = SHStrDupW(v16, a3);
                }
                else
                {
                  v7 = -2147418113;
                }
              }
              v18 = ppwsz;
              ppwsz = 0;
              CoTaskMemFree(v18);
            }
          }
          else
          {
            v7 = -2147418113;
          }
          GlobalUnlock(hMem[1]);
        }
        v9 = v21;
      }
      if ( v9 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000fcf8  push    rbp
0x18000fcfa  push    rbx
0x18000fcfb  push    rsi
0x18000fcfc  push    rdi
0x18000fcfd  push    r12
0x18000fcff  push    r14
0x18000fd01  push    r15
0x18000fd03  lea     rbp, [rsp-27h]
0x18000fd08  sub     rsp, 0F0h
0x18000fd0f  mov     rax, cs:__security_cookie
0x18000fd16  xor     rax, rsp
0x18000fd19  mov     [rbp+57h+var_38], rax
0x18000fd1d  xor     r12d, r12d
0x18000fd20  mov     [rbp+57h+var_70], 38h ; '8'
0x18000fd27  mov     [r8], r12
0x18000fd2a  lea     rcx, CLSID_DsObjectPicker; rclsid
0x18000fd31  mov     r15, r9
0x18000fd34  mov     [r9], r12
0x18000fd37  mov     r14, r8
0x18000fd3a  mov     [rbp+57h+var_54], r12d
0x18000fd3e  lea     eax, [r12+2]
0x18000fd43  mov     [rbp+57h+var_3C], r12d
0x18000fd47  lea     esi, [rax-1]
0x18000fd4a  mov     [rbp+57h+var_68], eax
0x18000fd4d  mov     [rbp+57h+var_64], rax
0x18000fd51  lea     r9, IID_IDsObjectPicker; riid
0x18000fd58  lea     rax, [rbp+57h+var_70]
0x18000fd5c  mov     [rbp+57h+var_6C], 378h
0x18000fd63  mov     [rbp+57h+var_88], rax
0x18000fd67  mov     rdi, rdx
0x18000fd6a  lea     rax, [rsp+120h+var_E0]
0x18000fd6f  mov     [rbp+57h+var_58], 80000001h
0x18000fd76  mov     r8d, esi; dwClsContext
0x18000fd79  mov     [rsp+120h+ppv], rax; ppv
0x18000fd7e  xor     edx, edx; pUnkOuter
0x18000fd80  mov     [rbp+57h+var_5C], r12d
0x18000fd84  mov     [rbp+57h+var_48], r12
0x18000fd88  mov     [rbp+57h+var_50], r12
0x18000fd8c  mov     [rbp+57h+var_40], 80004005h
0x18000fd93  mov     [rbp+57h+var_A0], 30h ; '0'
0x18000fd9b  mov     [rbp+57h+var_90], 1
0x18000fda3  mov     [rbp+57h+var_7C], r12
0x18000fda7  mov     [rbp+57h+var_74], r12d
0x18000fdab  mov     [rbp+57h+var_98], r12
0x18000fdaf  mov     [rbp+57h+var_80], r12d
0x18000fdb3  mov     [rsp+120h+var_E0], r12
0x18000fdb8  call    cs:__imp_CoCreateInstance
0x18000fdbe  mov     ebx, eax
0x18000fdc0  test    eax, eax
0x18000fdc2  js      loc_18000FF75
0x18000fdc8  mov     rcx, [rsp+120h+var_E0]
0x18000fdcd  lea     rdx, [rbp+57h+var_A0]
0x18000fdd1  mov     rax, [rcx]
0x18000fdd4  mov     rax, [rax+18h]
0x18000fdd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fddd  mov     ebx, eax
0x18000fddf  test    eax, eax
0x18000fde1  js      loc_18000FF75
0x18000fde7  mov     rcx, [rsp+120h+var_E0]
0x18000fdec  lea     r8, [rsp+120h+var_E8]
0x18000fdf1  mov     [rsp+120h+var_E8], r12
0x18000fdf6  mov     rdx, rdi
0x18000fdf9  mov     rax, [rcx]
0x18000fdfc  mov     rax, [rax+20h]
0x18000fe00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe05  mov     rcx, [rsp+120h+var_E8]
0x18000fe0a  test    eax, eax
0x18000fe0c  jnz     loc_18000FF5F
0x18000fe12  test    rcx, rcx
0x18000fe15  jz      loc_18000FF5F
0x18000fe1b  xorps   xmm0, xmm0
0x18000fe1e  lea     rcx, szFormat; "CFSTR_DSOP_DS_SELECTION_LIST"
0x18000fe25  movups  [rsp+120h+var_D8], xmm0
0x18000fe2a  movups  [rbp+57h+var_C8], xmm0
0x18000fe2e  call    cs:__imp_RegisterClipboardFormatW
0x18000fe34  mov     rcx, [rsp+120h+var_E8]
0x18000fe39  lea     r8, [rbp+57h+hMem]
0x18000fe3d  mov     word ptr [rsp+120h+var_D8], ax
0x18000fe42  lea     rdx, [rsp+120h+var_D8]
0x18000fe47  xor     eax, eax
0x18000fe49  mov     dword ptr [rbp+57h+var_C8], esi
0x18000fe4c  mov     [rbp+57h+var_A8], rax
0x18000fe50  xorps   xmm0, xmm0
0x18000fe53  mov     dword ptr [rbp+57h+var_C8+4], 0FFFFFFFFh
0x18000fe5a  mov     dword ptr [rbp+57h+var_C8+8], esi
0x18000fe5d  movups  xmmword ptr [rbp+57h+hMem], xmm0
0x18000fe61  mov     rax, [rcx]
0x18000fe64  mov     rax, [rax+18h]
0x18000fe68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe6d  mov     ebx, eax
0x18000fe6f  test    eax, eax
0x18000fe71  js      loc_18000FF58
0x18000fe77  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18000fe7b  call    cs:__imp_GlobalLock
0x18000fe81  test    rax, rax
0x18000fe84  jz      loc_18000FF49
0x18000fe8a  mov     ebx, r12d
0x18000fe8d  cmp     [rax], esi
0x18000fe8f  jb      loc_18000FF4E
0x18000fe95  mov     rcx, [rax+10h]; psz
0x18000fe99  lea     rdx, [rsp+120h+ppwsz]; ppwsz
0x18000fe9e  mov     [rsp+120h+ppwsz], r12
0x18000fea3  call    cs:__imp_SHStrDupW
0x18000fea9  mov     ebx, eax
0x18000feab  test    eax, eax
0x18000fead  js      loc_18000FF37
0x18000feb3  mov     rcx, [rsp+120h+ppwsz]; pszStr1
0x18000feb8  lea     r8d, [r12+8]; nChar
0x18000febd  lea     rdx, aWinnt; "WinNT://"
0x18000fec4  call    cs:__imp_StrCmpNICW
0x18000feca  test    eax, eax
0x18000fecc  jnz     short loc_18000FF37
0x18000fece  mov     rdi, [rsp+120h+ppwsz]
0x18000fed3  lea     edx, [rsi+2Eh]; wMatch
0x18000fed6  lea     rcx, [rdi+10h]; pszStart
0x18000feda  call    cs:__imp_StrChrW
0x18000fee0  mov     rbx, rax
0x18000fee3  test    rax, rax
0x18000fee6  jnz     short loc_18000FEEF
0x18000fee8  mov     ebx, 8000FFFFh
0x18000feed  jmp     short loc_18000FF37
0x18000feef  mov     rcx, rbx; lpsz
0x18000fef2  call    cs:__imp_CharNextW
0x18000fef8  mov     edx, 2Fh ; '/'; wMatch
0x18000fefd  mov     [rbx], r12w
0x18000ff01  mov     rcx, rax; pszStart
0x18000ff04  mov     rsi, rax
0x18000ff07  call    cs:__imp_StrChrW
0x18000ff0d  test    rax, rax
0x18000ff10  jz      short loc_18000FF16
0x18000ff12  mov     [rax], r12w
0x18000ff16  mov     rdx, r15; ppwsz
0x18000ff19  lea     rcx, [rdi+10h]; psz
0x18000ff1d  call    cs:__imp_SHStrDupW
0x18000ff23  mov     ebx, eax
0x18000ff25  test    eax, eax
0x18000ff27  js      short loc_18000FF37
0x18000ff29  mov     rdx, r14; ppwsz
0x18000ff2c  mov     rcx, rsi; psz
0x18000ff2f  call    cs:__imp_SHStrDupW
0x18000ff35  mov     ebx, eax
0x18000ff37  mov     rcx, [rsp+120h+ppwsz]; pv
0x18000ff3c  mov     [rsp+120h+ppwsz], r12
0x18000ff41  call    cs:__imp_CoTaskMemFree
0x18000ff47  jmp     short loc_18000FF4E
0x18000ff49  mov     ebx, 8000FFFFh
0x18000ff4e  mov     rcx, [rbp+57h+hMem+8]; hMem
0x18000ff52  call    cs:__imp_GlobalUnlock
0x18000ff58  mov     rcx, [rsp+120h+var_E8]
0x18000ff5d  jmp     short loc_18000FF64
0x18000ff5f  mov     ebx, 80004005h
0x18000ff64  test    rcx, rcx
0x18000ff67  jz      short loc_18000FF75
0x18000ff69  mov     rax, [rcx]
0x18000ff6c  mov     rax, [rax+10h]
0x18000ff70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff75  mov     rcx, [rsp+120h+var_E0]
0x18000ff7a  test    rcx, rcx
0x18000ff7d  jz      short loc_18000FF8B
0x18000ff7f  mov     rax, [rcx]
0x18000ff82  mov     rax, [rax+10h]
0x18000ff86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff8b  mov     eax, ebx
0x18000ff8d  mov     rcx, [rbp+57h+var_38]
0x18000ff91  xor     rcx, rsp; StackCookie
0x18000ff94  call    __security_check_cookie
0x18000ff99  add     rsp, 0F0h
0x18000ffa0  pop     r15
0x18000ffa2  pop     r14
0x18000ffa4  pop     r12
0x18000ffa6  pop     rdi
0x18000ffa7  pop     rsi
0x18000ffa8  pop     rbx
0x18000ffa9  pop     rbp
0x18000ffaa  retn
```
