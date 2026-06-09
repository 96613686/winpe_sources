# CThumbnailMoniker::_NonLocalFSInitFallback(IShellItem *,IPropertyStore *,unsigned __int64 *,ushort * *)

- ea: `0x1800085c0`
- end: `0x180008813`
- name: `?_NonLocalFSInitFallback@CThumbnailMoniker@@AEBAJPEAUIShellItem@@PEAUIPropertyStore@@PEA_KPEAPEAG@Z`
- size: `595`
- prototype: `int(CThumbnailMoniker *__hidden this, struct IShellItem *, struct IPropertyStore *, unsigned __int64 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180009ed0`
- `0x18000a300`

## callees

- `0x180003624`
- `0x180008324`
- `0x1800085c0`
- `0x18000881c`
- `0x180021e40`
- `0x180035830`
- `0x180049010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800086ef`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x1800086ef`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180008796`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x180008796`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180008788`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCW` at `0x180008788`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000877c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008723`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000877c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000866f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000866f`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CThumbnailMoniker::_NonLocalFSInitFallback(
        CThumbnailMoniker *this,
        struct IShellItem *a2,
        struct IPropertyStore *a3,
        unsigned __int64 *a4,
        unsigned __int16 **a5)
{
  int v9; // ebx
  int v10; // edi
  __int64 cchDest; // r9
  unsigned __int16 *v12; // rbx
  LPWSTR v13; // rcx
  const unsigned __int16 *v15; // rsi
  unsigned __int16 *v16[2]; // [rsp+30h] [rbp-51h] BYREF
  PROPERTYKEY v17; // [rsp+40h] [rbp-41h] BYREF
  LPWSTR lpDestStr; // [rsp+60h] [rbp-21h] BYREF
  int v19; // [rsp+68h] [rbp-19h] BYREF
  struct _FILETIME v20; // [rsp+70h] [rbp-11h] BYREF
  PROPVARIANT pvar[3]; // [rsp+78h] [rbp-9h] BYREF

  *a5 = 0;
  *a4 = 0;
  v20 = 0;
  if ( !a3 )
    goto LABEL_6;
  v16[0] = (unsigned __int16 *)a3;
  ((void (__fastcall *)(struct IPropertyStore *))a3->lpVtbl->AddRef)(a3);
  v20 = 0;
  LOWORD(pvar[0]) = 0;
  v17 = PKEY_DateModified;
  v9 = ((__int64 (__fastcall *)(struct IPropertyStore *, PROPERTYKEY *, PROPVARIANT *))a3->lpVtbl->GetValue)(
         a3,
         &v17,
         pvar);
  if ( v9 >= 0 )
  {
    if ( LOWORD(pvar[0]) )
    {
      if ( LOWORD(pvar[0]) == 64 )
        v20 = (struct _FILETIME)pvar[1];
      else
        v9 = -2147352571;
    }
    else
    {
      v9 = -2147023728;
    }
  }
  PropVariantClear(pvar);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v16);
  if ( v9 < 0 )
LABEL_6:
    GetShellItemLastModifiedTime(a2, &v20);
  lpDestStr = 0;
  v10 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, LPWSTR *))a2->lpVtbl->GetDisplayName)(
          a2,
          2147647488LL,
          &lpDestStr);
  if ( v10 >= 0 )
  {
    cchDest = -1;
    do
      ++cchDest;
    while ( lpDestStr[cchDest] );
    LCMapStringW(0x7Fu, 0x200u, lpDestStr, cchDest, lpDestStr, cchDest);
    v19 = 0;
    v12 = 0;
    v16[0] = 0;
    v10 = ((__int64 (__fastcall *)(struct IShellItem *, __int64, int *))a2->lpVtbl->GetAttributes)(a2, 0x40000000, &v19);
    if ( v10 < 0 )
      goto LABEL_11;
    if ( (v19 & 0x40000000) == 0 || PathIsUNCW(lpDestStr) || PathIsRootW(lpDestStr) )
    {
      v15 = lpDestStr;
      lpDestStr = 0;
      CoTaskMemFree(0);
    }
    else
    {
      if ( *((_DWORD *)this + 6) )
      {
        v10 = -2147467259;
        goto LABEL_11;
      }
      v10 = CThumbnailMoniker::_NormalizeUrl(a3, lpDestStr, v16);
      if ( v10 < 0 )
      {
        v12 = v16[0];
        goto LABEL_11;
      }
      v15 = v16[0];
    }
    *a4 = GetCRC64KeyFromUrlAndFileTime(v15, v20);
    v12 = 0;
    *a5 = (unsigned __int16 *)v15;
LABEL_11:
    CoTaskMemFree(v12);
  }
  v13 = lpDestStr;
  lpDestStr = 0;
  CoTaskMemFree(v13);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800085c0  mov     [rsp-8+arg_0], rbx
0x1800085c5  push    rbp
0x1800085c6  push    rsi
0x1800085c7  push    rdi
0x1800085c8  push    r12
0x1800085ca  push    r13
0x1800085cc  push    r14
0x1800085ce  push    r15
0x1800085d0  lea     rbp, [rsp-1Fh]
0x1800085d5  sub     rsp, 0A0h
0x1800085dc  mov     rax, cs:__security_cookie
0x1800085e3  xor     rax, rsp
0x1800085e6  mov     [rbp+4Fh+var_40], rax
0x1800085ea  mov     r15, r9
0x1800085ed  mov     r14, r8
0x1800085f0  mov     rsi, rdx
0x1800085f3  mov     r13, rcx
0x1800085f6  mov     r12, [rbp+4Fh+arg_20]
0x1800085fa  xor     edi, edi
0x1800085fc  mov     [r12], rdi
0x180008600  mov     [r9], rdi
0x180008603  mov     qword ptr [rbp+4Fh+var_60.dwLowDateTime], rdi
0x180008607  test    r8, r8
0x18000860a  jz      short loc_180008683
0x18000860c  mov     [rbp+4Fh+var_A0], r8
0x180008610  mov     rax, [r8]
0x180008613  mov     rcx, r8
0x180008616  mov     rax, [rax+8]
0x18000861a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000861f  nop
0x180008620  movups  xmm0, xmmword ptr cs:PKEY_DateModified.fmtid.Data1
0x180008627  mov     ecx, cs:PKEY_DateModified.pid
0x18000862d  mov     qword ptr [rbp+4Fh+var_60.dwLowDateTime], rdi
0x180008631  mov     word ptr [rbp+4Fh+pvar], di
0x180008635  movaps  [rbp+4Fh+var_90], xmm0
0x180008639  mov     [rbp+4Fh+var_80], ecx
0x18000863c  mov     rax, [r14]
0x18000863f  lea     r8, [rbp+4Fh+pvar]
0x180008643  lea     rdx, [rbp+4Fh+var_90]
0x180008647  mov     rcx, r14
0x18000864a  mov     rax, [rax+28h]
0x18000864e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008653  mov     ebx, eax
0x180008655  movzx   eax, word ptr [rbp+4Fh+pvar]
0x180008659  test    ebx, ebx
0x18000865b  js      short loc_18000866B
0x18000865d  test    ax, ax
0x180008660  jnz     loc_1800087E4
0x180008666  mov     ebx, 80070490h
0x18000866b  lea     rcx, [rbp+4Fh+pvar]; pvar
0x18000866f  call    cs:__imp_PropVariantClear
0x180008675  nop
0x180008676  lea     rcx, [rbp+4Fh+var_A0]
0x18000867a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000867f  test    ebx, ebx
0x180008681  jns     short loc_180008691
0x180008683  lea     rdx, [rbp+4Fh+var_60]; struct _FILETIME *
0x180008687  mov     rcx, rsi; struct IShellItem *
0x18000868a  call    ?GetShellItemLastModifiedTime@@YAJPEAUIShellItem@@PEAU_FILETIME@@@Z; GetShellItemLastModifiedTime(IShellItem *,_FILETIME *)
0x18000868f  mov     ebx, eax
0x180008691  mov     eax, edi
0x180008693  test    ebx, ebx
0x180008695  cmovns  eax, ebx
0x180008698  test    eax, eax
0x18000869a  js      loc_18000873E
0x1800086a0  mov     [rbp+4Fh+var_70], rdi
0x1800086a4  mov     rax, [rsi]
0x1800086a7  lea     r8, [rbp+4Fh+var_70]
0x1800086ab  mov     edx, 80028000h
0x1800086b0  mov     rcx, rsi
0x1800086b3  mov     rax, [rax+28h]
0x1800086b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086bc  mov     edi, eax
0x1800086be  test    eax, eax
0x1800086c0  js      short loc_18000872A
0x1800086c2  mov     r8, [rbp+4Fh+var_70]; lpSrcStr
0x1800086c6  mov     r9, 0FFFFFFFFFFFFFFFFh
0x1800086cd  nop     dword ptr [rax]
0x1800086d0  inc     r9; cchSrc
0x1800086d3  cmp     word ptr [r8+r9*2], 0
0x1800086d9  jnz     short loc_1800086D0
0x1800086db  mov     [rsp+0D0h+cchDest], r9d; cchDest
0x1800086e0  mov     [rsp+0D0h+lpDestStr], r8; lpDestStr
0x1800086e5  mov     edx, 200h; dwMapFlags
0x1800086ea  mov     ecx, 7Fh; Locale
0x1800086ef  call    cs:__imp_LCMapStringW
0x1800086f5  mov     [rbp+4Fh+var_68], 0
0x1800086fc  xor     ebx, ebx
0x1800086fe  mov     [rbp+4Fh+var_A0], rbx
0x180008702  mov     rax, [rsi]
0x180008705  lea     r8, [rbp+4Fh+var_68]
0x180008709  mov     edx, 40000000h
0x18000870e  mov     rcx, rsi
0x180008711  mov     rax, [rax+30h]
0x180008715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000871a  mov     edi, eax
0x18000871c  test    eax, eax
0x18000871e  jns     short loc_180008765
0x180008720  mov     rcx, rbx; pv
0x180008723  call    cs:__imp_CoTaskMemFree
0x180008729  nop
0x18000872a  mov     rcx, [rbp+4Fh+var_70]; pv
0x18000872e  mov     [rbp+4Fh+var_70], 0
0x180008736  call    cs:__imp_CoTaskMemFree
0x18000873c  mov     eax, edi
0x18000873e  mov     rcx, [rbp+4Fh+var_40]
0x180008742  xor     rcx, rsp; StackCookie
0x180008745  call    __security_check_cookie
0x18000874a  mov     rbx, [rsp+0D0h+arg_0]
0x180008752  add     rsp, 0A0h
0x180008759  pop     r15
0x18000875b  pop     r14
0x18000875d  pop     r13
0x18000875f  pop     r12
0x180008761  pop     rdi
0x180008762  pop     rsi
0x180008763  pop     rbp
0x180008764  retn
0x180008765  test    [rbp+4Fh+var_68], 40000000h
0x18000876c  jnz     short loc_180008784
0x18000876e  mov     rsi, [rbp+4Fh+var_70]
0x180008772  mov     [rbp+4Fh+var_70], 0
0x18000877a  xor     ecx, ecx; pv
0x18000877c  call    cs:__imp_CoTaskMemFree
0x180008782  jmp     short loc_1800087C0
0x180008784  mov     rcx, [rbp+4Fh+var_70]; pszPath
0x180008788  call    cs:__imp_PathIsUNCW
0x18000878e  test    eax, eax
0x180008790  jnz     short loc_18000876E
0x180008792  mov     rcx, [rbp+4Fh+var_70]; pszPath
0x180008796  call    cs:__imp_PathIsRootW
0x18000879c  test    eax, eax
0x18000879e  jnz     short loc_18000876E
0x1800087a0  cmp     [r13+18h], eax
0x1800087a4  jnz     short loc_1800087DA
0x1800087a6  lea     r8, [rbp+4Fh+var_A0]; unsigned __int16 **
0x1800087aa  mov     rdx, [rbp+4Fh+var_70]; lpLocalPath
0x1800087ae  mov     rcx, r14; struct IPropertyStore *
0x1800087b1  call    ?_NormalizeUrl@CThumbnailMoniker@@CAJPEAUIPropertyStore@@PEBGPEAPEAG@Z; CThumbnailMoniker::_NormalizeUrl(IPropertyStore *,ushort const *,ushort * *)
0x1800087b6  mov     edi, eax
0x1800087b8  test    eax, eax
0x1800087ba  js      short loc_180008809
0x1800087bc  mov     rsi, [rbp+4Fh+var_A0]
0x1800087c0  mov     rdx, qword ptr [rbp+4Fh+var_60.dwLowDateTime]; struct _FILETIME
0x1800087c4  mov     rcx, rsi; unsigned __int16 *
0x1800087c7  call    ?GetCRC64KeyFromUrlAndFileTime@@YA_KPEBGU_FILETIME@@@Z; GetCRC64KeyFromUrlAndFileTime(ushort const *,_FILETIME)
0x1800087cc  mov     [r15], rax
0x1800087cf  xor     ebx, ebx
0x1800087d1  mov     [r12], rsi
0x1800087d5  jmp     loc_180008720
0x1800087da  mov     edi, 80004005h
0x1800087df  jmp     loc_180008720
0x1800087e4  test    ebx, ebx
0x1800087e6  js      loc_18000866B
0x1800087ec  cmp     ax, 40h ; '@'
0x1800087f0  jnz     short loc_1800087FF
0x1800087f2  mov     rax, [rbp+4Fh+var_50]
0x1800087f6  mov     qword ptr [rbp+4Fh+var_60.dwLowDateTime], rax
0x1800087fa  jmp     loc_18000866B
0x1800087ff  mov     ebx, 80020005h
0x180008804  jmp     loc_18000866B
0x180008809  mov     rbx, [rbp+4Fh+var_A0]
0x18000880d  jmp     loc_180008720
```
