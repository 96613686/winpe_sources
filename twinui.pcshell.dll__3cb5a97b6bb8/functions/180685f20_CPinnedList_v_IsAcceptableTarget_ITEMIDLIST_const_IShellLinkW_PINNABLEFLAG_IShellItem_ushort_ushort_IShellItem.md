# CPinnedList::v_IsAcceptableTarget(_ITEMIDLIST const *,IShellLinkW *,PINNABLEFLAG,IShellItem * *,ushort * *,ushort * *,IShellItem * *)

- ea: `0x180685f20`
- end: `0x180686259`
- name: `?v_IsAcceptableTarget@CPinnedList@@MEAAHPEFBU_ITEMIDLIST@@PEAUIShellLinkW@@W4PINNABLEFLAG@@PEAPEAUIShellItem@@PEAPEAG43@Z`
- size: `825`
- prototype: `int __high(const struct _ITEMIDLIST *, struct IShellLinkW *, enum PINNABLEFLAG, struct IShellItem **, unsigned __int16 **, unsigned __int16 **, struct IShellItem **)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x18005a710`
- `0x1802cd974`
- `0x180356360`
- `0x1805f565c`
- `0x1806780b0`
- `0x18067c118`
- `0x180684990`
- `0x180685f20`
- `0x1806fa010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806861ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1806861ac`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1806860d6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1806860d6`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180686165`
- `api-ms-win-core-url-l1-1-0!PathIsURLW` at `0x180686165`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18068606d`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x18068606d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1806860ee`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180686102`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x1806860ee`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x180686102`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180685ff5`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromIDList` at `0x180685ff5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_BOOL8 __fastcall CPinnedList::v_IsAcceptableTarget(
        __int64 a1,
        const ITEMIDLIST *a2,
        IUnknown *a3,
        char a4,
        _QWORD *a5,
        _QWORD *a6,
        _QWORD *a7,
        _QWORD *a8)
{
  BOOL v11; // ebx
  int v12; // edi
  struct IShellItem **v13; // r8
  int TaskbarPinnableItem; // eax
  void *lpVtbl; // rcx
  BOOL v16; // ebx
  WCHAR *v17; // rcx
  const WCHAR *ExtensionW; // rax
  const WCHAR *v19; // rdi
  int v20; // edi
  CPinnedList *v21; // rcx
  __int64 v22; // rax
  IUnknown **p_ppunk; // [rsp+20h] [rbp-E0h]
  void *ppv; // [rsp+30h] [rbp-D0h] BYREF
  IUnknown *ppunk; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v27; // [rsp+40h] [rbp-C0h] BYREF
  struct IShellItem v28; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR v29[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  v11 = 1;
  if ( a8 )
    *a8 = 0;
  if ( a6 )
    *a6 = 0;
  if ( a5 )
    *a5 = 0;
  *a7 = 0;
  LODWORD(ppv) = 1073807360;
  if ( (int)SHGetNameAndFlagsW(a2, 0x8000u, pszPath, a4, (unsigned int *)&ppv) >= 0 )
  {
    v12 = (int)ppv;
    if ( ((unsigned int)ppv & 0x40000000) == 0 )
      return (a4 & 1) == 0;
    v11 = 0;
    ppv = 0;
    if ( SHCreateItemFromIDList(a2, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) < 0 )
      return v11;
    v28.lpVtbl = 0;
    Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v28);
    TaskbarPinnableItem = TaskbarPinHelper::GetTaskbarPinnableItem((TaskbarPinHelper *)ppv, &v28, v13);
    lpVtbl = ppv;
    if ( TaskbarPinnableItem >= 0 )
    {
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      lpVtbl = v28.lpVtbl;
      v28.lpVtbl = 0;
      ppv = lpVtbl;
    }
    v16 = (v12 & 0x10000) != 0;
    v29[0] = 0;
    ppunk = 0;
    if ( (v12 & 0x10000) == 0 )
      goto LABEL_19;
    if ( a3 )
    {
      IUnknown_Set(&ppunk, a3);
    }
    else
    {
      p_ppunk = &ppunk;
      if ( (*(int (__fastcall **)(void *, _QWORD, const GUID *, GUID *))(*(_QWORD *)lpVtbl + 24LL))(
             lpVtbl,
             0,
             &BHID_SFUIObject,
             &GUID_000214f9_0000_0000_c000_000000000046) < 0 )
        goto LABEL_18;
    }
    if ( (int)CPinnedList::GetAppPathFromShortcut(
                (struct IShellLinkW *)ppunk,
                (struct IShellItem *)ppv,
                0x4000u,
                v29,
                (int)p_ppunk) >= 0 )
    {
LABEL_19:
      if ( (a4 & 1) != 0 )
      {
        v17 = v29;
        if ( !v16 )
          v17 = pszPath;
        ExtensionW = PathFindExtensionW(v17);
        v19 = ExtensionW;
        if ( ExtensionW )
        {
          if ( StrCmpICW(ExtensionW, L".EXE") && StrCmpICW(v19, L".MSC") )
            goto LABEL_36;
        }
      }
      if ( (a4 & 2) == 0 )
        goto LABEL_37;
      if ( v29[0] != 58 || v29[1] != 58 || v29[2] != 123 || (v20 = 1, !v29[3]) )
        v20 = 0;
      if ( !CPinnedList::_IsLocalHardDisk((CPinnedList *)lpVtbl, pszPath)
        || v16 && !v20 && !CPinnedList::_IsLocalHardDisk(v21, v29) && !PathIsURLW(v29) )
      {
LABEL_36:
        v11 = 0;
      }
      else
      {
LABEL_37:
        v11 = 1;
        if ( (a4 & 8) != 0 )
        {
          v11 = 0;
          v27 = 0;
          if ( CoCreateInstance(
                 &CLSID_StartMenuCacheAndAppResolver,
                 0,
                 3u,
                 &GUID_de25675a_72de_44b4_9373_05170450c140,
                 &v27) >= 0 )
          {
            v22 = *(_QWORD *)v27;
            if ( ppunk )
              v11 = (*(int (__fastcall **)(LPVOID, IUnknown *, void *))(v22 + 88))(v27, ppunk, ppv) >= 0;
            else
              v11 = (*(int (__fastcall **)(LPVOID, void *))(v22 + 80))(v27, ppv) >= 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
          }
        }
      }
      SafeRelease<IShellItemArray>(&ppunk);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(&v28);
      return v11;
    }
LABEL_18:
    v16 = 0;
    goto LABEL_19;
  }
  return v11;
}

```

## disassembly

```asm
0x180685f20  mov     [rsp-8+arg_0], rbx
0x180685f25  mov     [rsp-8+arg_18], rsi
0x180685f2a  push    rbp
0x180685f2b  push    rdi
0x180685f2c  push    r12
0x180685f2e  push    r14
0x180685f30  push    r15
0x180685f32  lea     rbp, [rsp-380h]
0x180685f3a  sub     rsp, 480h
0x180685f41  mov     rax, cs:__security_cookie
0x180685f48  xor     rax, rsp
0x180685f4b  mov     [rbp+3A0h+var_30], rax
0x180685f52  mov     esi, r9d
0x180685f55  mov     r15, r8
0x180685f58  mov     r14, rdx
0x180685f5b  mov     rcx, [rbp+3A0h+arg_20]
0x180685f62  mov     rax, [rbp+3A0h+arg_28]
0x180685f69  mov     r8, [rbp+3A0h+arg_30]
0x180685f70  mov     rdx, [rbp+3A0h+arg_38]
0x180685f77  mov     ebx, 1
0x180685f7c  xor     r12d, r12d
0x180685f7f  test    rdx, rdx
0x180685f82  jz      short loc_180685F87
0x180685f84  mov     [rdx], r12
0x180685f87  test    rax, rax
0x180685f8a  jz      short loc_180685F8F
0x180685f8c  mov     [rax], r12
0x180685f8f  test    rcx, rcx
0x180685f92  jz      short loc_180685F97
0x180685f94  mov     [rcx], r12
0x180685f97  mov     [r8], r12
0x180685f9a  mov     dword ptr [rsp+4A0h+ppv], 40010000h
0x180685fa2  lea     rax, [rsp+4A0h+ppv]
0x180685fa7  mov     [rsp+4A0h+var_480], rax; unsigned int *
0x180685fac  lea     r8, [rbp+3A0h+pszPath]; unsigned __int16 *
0x180685fb3  mov     edx, 8000h; unsigned int
0x180685fb8  mov     rcx, r14; pidl
0x180685fbb  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x180685fc0  test    eax, eax
0x180685fc2  js      loc_18068622C
0x180685fc8  mov     edi, dword ptr [rsp+4A0h+ppv]
0x180685fcc  bt      edi, 1Eh
0x180685fd0  jb      short loc_180685FDE
0x180685fd2  mov     ebx, esi
0x180685fd4  not     ebx
0x180685fd6  and     ebx, 1
0x180685fd9  jmp     loc_18068622C
0x180685fde  mov     ebx, r12d
0x180685fe1  mov     [rsp+4A0h+ppv], r12
0x180685fe6  lea     r8, [rsp+4A0h+ppv]; ppv
0x180685feb  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180685ff2  mov     rcx, r14; pidl
0x180685ff5  call    cs:__imp_SHCreateItemFromIDList
0x180685ffb  test    eax, eax
0x180685ffd  js      loc_18068622C
0x180686003  mov     [rsp+4A0h+var_458.lpVtbl], r12
0x180686008  lea     rcx, [rsp+4A0h+var_458]
0x18068600d  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x180686012  lea     rdx, [rsp+4A0h+var_458]; struct IShellItem *
0x180686017  mov     rcx, [rsp+4A0h+ppv]; this
0x18068601c  call    ?GetTaskbarPinnableItem@TaskbarPinHelper@@YAJPEAUIShellItem@@PEAPEAU2@@Z; TaskbarPinHelper::GetTaskbarPinnableItem(IShellItem *,IShellItem * *)
0x180686021  mov     rcx, [rsp+4A0h+ppv]
0x180686026  test    eax, eax
0x180686028  js      short loc_180686045
0x18068602a  mov     rax, [rcx]
0x18068602d  mov     rax, [rax+10h]
0x180686031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180686036  mov     rcx, [rsp+4A0h+var_458.lpVtbl]
0x18068603b  mov     [rsp+4A0h+var_458.lpVtbl], r12
0x180686040  mov     [rsp+4A0h+ppv], rcx
0x180686045  bt      edi, 10h
0x180686049  mov     ebx, r12d
0x18068604c  setb    bl
0x18068604f  mov     [rsp+4A0h+var_450], r12w
0x180686055  mov     [rsp+4A0h+ppunk], r12
0x18068605a  bt      edi, 10h
0x18068605e  jnb     short loc_1806860C0
0x180686060  test    r15, r15
0x180686063  jz      short loc_180686075
0x180686065  mov     rdx, r15; punk
0x180686068  lea     rcx, [rsp+4A0h+ppunk]; ppunk
0x18068606d  call    cs:__imp_IUnknown_Set
0x180686073  jmp     short loc_18068609F
0x180686075  mov     rax, [rcx]
0x180686078  lea     rdx, [rsp+4A0h+ppunk]
0x18068607d  mov     [rsp+4A0h+var_480], rdx; int
0x180686082  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x180686089  lea     r8, BHID_SFUIObject
0x180686090  xor     edx, edx
0x180686092  mov     rax, [rax+18h]
0x180686096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18068609b  test    eax, eax
0x18068609d  js      short loc_1806860BD
0x18068609f  lea     r9, [rsp+4A0h+var_450]; unsigned __int16 *
0x1806860a4  mov     r8d, 4000h; unsigned int
0x1806860aa  mov     rdx, [rsp+4A0h+ppv]; struct IShellItem *
0x1806860af  mov     rcx, [rsp+4A0h+ppunk]; struct IShellLinkW *
0x1806860b4  call    ?GetAppPathFromShortcut@CPinnedList@@SAJPEAUIShellLinkW@@PEAUIShellItem@@KPEAGH@Z; CPinnedList::GetAppPathFromShortcut(IShellLinkW *,IShellItem *,ulong,ushort *,int)
0x1806860b9  test    eax, eax
0x1806860bb  jns     short loc_1806860C0
0x1806860bd  mov     ebx, r12d
0x1806860c0  test    sil, 1
0x1806860c4  jz      short loc_18068610C
0x1806860c6  test    ebx, ebx
0x1806860c8  lea     rcx, [rsp+4A0h+var_450]
0x1806860cd  jnz     short loc_1806860D6
0x1806860cf  lea     rcx, [rbp+3A0h+pszPath]; pszPath
0x1806860d6  call    cs:__imp_PathFindExtensionW
0x1806860dc  mov     rdi, rax
0x1806860df  test    rax, rax
0x1806860e2  jz      short loc_18068610C
0x1806860e4  lea     rdx, pszStr2; ".EXE"
0x1806860eb  mov     rcx, rax; pszStr1
0x1806860ee  call    cs:__imp_StrCmpICW
0x1806860f4  test    eax, eax
0x1806860f6  jz      short loc_18068610C
0x1806860f8  lea     rdx, aMsc; ".MSC"
0x1806860ff  mov     rcx, rdi; pszStr1
0x180686102  call    cs:__imp_StrCmpICW
0x180686108  test    eax, eax
0x18068610a  jnz     short loc_18068616F
0x18068610c  test    sil, 2
0x180686110  jz      short loc_180686177
0x180686112  cmp     [rsp+4A0h+var_450], 3Ah ; ':'
0x180686118  jnz     short loc_180686137
0x18068611a  cmp     [rsp+4A0h+var_44E], 3Ah ; ':'
0x180686120  jnz     short loc_180686137
0x180686122  cmp     [rsp+4A0h+var_44C], 7Bh ; '{'
0x180686128  jnz     short loc_180686137
0x18068612a  cmp     [rsp+4A0h+var_44A], r12w
0x180686130  mov     edi, 1
0x180686135  jnz     short loc_18068613A
0x180686137  mov     edi, r12d
0x18068613a  lea     rdx, [rbp+3A0h+pszPath]; unsigned __int16 *
0x180686141  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x180686146  test    eax, eax
0x180686148  jz      short loc_18068616F
0x18068614a  test    ebx, ebx
0x18068614c  jz      short loc_180686177
0x18068614e  test    edi, edi
0x180686150  jnz     short loc_180686177
0x180686152  lea     rdx, [rsp+4A0h+var_450]; unsigned __int16 *
0x180686157  call    ?_IsLocalHardDisk@CPinnedList@@IEAAHPEBG@Z; CPinnedList::_IsLocalHardDisk(ushort const *)
0x18068615c  test    eax, eax
0x18068615e  jnz     short loc_180686177
0x180686160  lea     rcx, [rsp+4A0h+var_450]; pszPath
0x180686165  call    cs:__imp_PathIsURLW
0x18068616b  test    eax, eax
0x18068616d  jnz     short loc_180686177
0x18068616f  mov     ebx, r12d
0x180686172  jmp     loc_180686206
0x180686177  mov     ebx, 1
0x18068617c  test    sil, 8
0x180686180  jz      loc_180686206
0x180686186  mov     ebx, r12d
0x180686189  mov     [rsp+4A0h+var_460], r12
0x18068618e  lea     rax, [rsp+4A0h+var_460]
0x180686193  mov     [rsp+4A0h+var_480], rax; ppv
0x180686198  lea     r9, _GUID_de25675a_72de_44b4_9373_05170450c140; riid
0x18068619f  xor     edx, edx; pUnkOuter
0x1806861a1  lea     r8d, [rdx+3]; dwClsContext
0x1806861a5  lea     rcx, CLSID_StartMenuCacheAndAppResolver; rclsid
0x1806861ac  call    cs:__imp_CoCreateInstance
0x1806861b2  test    eax, eax
0x1806861b4  js      short loc_180686206
0x1806861b6  mov     rdx, [rsp+4A0h+ppunk]
0x1806861bb  mov     rcx, [rsp+4A0h+var_460]
0x1806861c0  mov     rax, [rcx]
0x1806861c3  test    rdx, rdx
0x1806861c6  jz      short loc_1806861DF
0x1806861c8  mov     r8, [rsp+4A0h+ppv]
0x1806861cd  mov     rax, [rax+58h]
0x1806861d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806861d6  mov     ebx, eax
0x1806861d8  not     ebx
0x1806861da  shr     ebx, 1Fh
0x1806861dd  jmp     short loc_1806861F5
0x1806861df  mov     rdx, [rsp+4A0h+ppv]
0x1806861e4  mov     rax, [rax+50h]
0x1806861e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1806861ed  mov     ebx, r12d
0x1806861f0  test    eax, eax
0x1806861f2  setns   bl
0x1806861f5  mov     rcx, [rsp+4A0h+var_460]
0x1806861fa  mov     rax, [rcx]
0x1806861fd  mov     rax, [rax+10h]
0x180686201  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180686206  lea     rcx, [rsp+4A0h+ppunk]
0x18068620b  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x180686210  mov     rcx, [rsp+4A0h+ppv]
0x180686215  mov     rdx, [rcx]
0x180686218  mov     rax, [rdx+10h]
0x18068621c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180686221  nop
0x180686222  lea     rcx, [rsp+4A0h+var_458]
0x180686227  call    ?InternalRelease@?$ComPtr@UIWICBitmapEncoder@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IWICBitmapEncoder>::InternalRelease(void)
0x18068622c  mov     eax, ebx
0x18068622e  mov     rcx, [rbp+3A0h+var_30]
0x180686235  xor     rcx, rsp; StackCookie
0x180686238  call    __security_check_cookie
0x18068623d  lea     r11, [rsp+4A0h+var_20]
0x180686245  mov     rbx, [r11+30h]
0x180686249  mov     rsi, [r11+48h]
0x18068624d  mov     rsp, r11
0x180686250  pop     r15
0x180686252  pop     r14
0x180686254  pop     r12
0x180686256  pop     rdi
0x180686257  pop     rbp
0x180686258  retn
```
