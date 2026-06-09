# SHInvokeCommandOnContextMenu2(HWND__ *,IUnknown *,IContextMenu *,ulong,uint,char const *,ushort const *,tagPOINT const *)

- ea: `0x18000b4a0`
- end: `0x18000b6b0`
- name: `?SHInvokeCommandOnContextMenu2@@YAJPEAUHWND__@@PEAUIUnknown@@PEAUIContextMenu@@KIPEBDPEBGPEBUtagPOINT@@@Z`
- size: `528`
- prototype: `int(HWND, struct IUnknown *, struct IContextMenu *, unsigned int, unsigned int, const char *, const unsigned __int16 *, const struct tagPOINT *)`
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024bf0`
- `0x180024c30`
- `0x180024c70`
- `0x180024d70`
- `0x180024db0`

## callees

- `0x18000b4a0`
- `0x180012550`
- `0x180013066`
- `0x180023714`
- `0x180037010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000b515`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000b671`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000b515`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x18000b671`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000b63c`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x18000b63c`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18000b531`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupA` at `0x18000b531`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b67c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b67c`
- `USER32!CreatePopupMenu` at `0x18000b4f2`
- `USER32!CreatePopupMenu` at `0x18000b4f2`
- `USER32!GetMenuDefaultItem` at `0x18000b59e`
- `USER32!GetMenuDefaultItem` at `0x18000b59e`
- `USER32!DestroyMenu` at `0x18000b685`
- `USER32!DestroyMenu` at `0x18000b685`

## pseudocode

```c
__int64 __fastcall SHInvokeCommandOnContextMenu2(
        HWND a1,
        struct IUnknown *a2,
        IUnknown *a3,
        int a4,
        unsigned int a5,
        const char *psz,
        const unsigned __int16 *pwszSrc,
        const struct tagPOINT *a8)
{
  unsigned __int64 v8; // rbx
  HMENU PopupMenu; // r12
  int v12; // edi
  unsigned int v13; // r8d
  UINT MenuDefaultItem; // eax
  int v15; // ecx
  int v16; // ecx
  int v17; // eax
  CHAR *v18; // rcx
  LPWSTR ppwsz[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v23; // [rsp+60h] [rbp-A0h] BYREF
  int v24; // [rsp+64h] [rbp-9Ch] BYREF
  HWND v25; // [rsp+68h] [rbp-98h]
  const char *v26; // [rsp+70h] [rbp-90h]
  CHAR *v27; // [rsp+80h] [rbp-80h]
  int v28; // [rsp+88h] [rbp-78h]
  LPWSTR v29; // [rsp+A0h] [rbp-60h]
  const unsigned __int16 *v30; // [rsp+B0h] [rbp-50h]
  __int64 v31; // [rsp+C0h] [rbp-40h]
  CHAR pszDst[272]; // [rsp+D0h] [rbp-30h] BYREF

  v8 = (unsigned __int64)psz;
  PopupMenu = CreatePopupMenu();
  if ( !PopupMenu )
    return (unsigned int)-2147024882;
  if ( a2 )
    IUnknown_SetSite(a3, a2);
  ppwsz[0] = 0;
  if ( psz && SHStrDupA(psz, ppwsz) >= 0 )
    IContextMenu_SetInvokeVerbs((struct IContextMenu *)a3, (const unsigned __int16 *const *const)ppwsz, v13);
  v12 = ((__int64 (__fastcall *)(IUnknown *, HMENU, _QWORD, __int64, int, unsigned int))a3->lpVtbl[1].QueryInterface)(
          a3,
          PopupMenu,
          0,
          1,
          0x7FFF,
          a5 | (psz != 0 ? 2048 : 1));
  if ( v12 >= 0 )
  {
    if ( psz )
      goto LABEL_13;
    MenuDefaultItem = GetMenuDefaultItem(PopupMenu, 0, 0);
    if ( MenuDefaultItem != -1 )
    {
      v8 = (unsigned __int16)(MenuDefaultItem - 1);
LABEL_13:
      v23 = 104;
      memset_0(&v24, 0, 0x64u);
      if ( ppwsz[0] || pwszSrc )
        v15 = 0x4000;
      else
        v15 = 0;
      v16 = a4 | v15;
      v24 = v16;
      v25 = a1;
      v26 = (const char *)v8;
      v28 = 1;
      v30 = pwszSrc;
      v29 = ppwsz[0];
      if ( a8 )
      {
        v31 = (__int64)*a8;
        v24 = v16 | 0x20000000;
      }
      if ( pwszSrc )
      {
        v17 = SHUnicodeToAnsi(pwszSrc, pszDst, 260);
        v18 = pszDst;
        if ( v17 < 0 )
          v18 = v27;
        v27 = v18;
      }
      v12 = ((__int64 (__fastcall *)(IUnknown *, int *))a3->lpVtbl[1].AddRef)(a3, &v23);
      goto LABEL_24;
    }
    v12 = -2147467259;
  }
LABEL_24:
  if ( a2 )
    IUnknown_SetSite(a3, 0);
  CoTaskMemFree(ppwsz[0]);
  DestroyMenu(PopupMenu);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000b4a0  push    rbp
0x18000b4a2  push    rbx
0x18000b4a3  push    rsi
0x18000b4a4  push    rdi
0x18000b4a5  push    r12
0x18000b4a7  push    r13
0x18000b4a9  push    r14
0x18000b4ab  push    r15
0x18000b4ad  lea     rbp, [rsp-0F8h]
0x18000b4b5  sub     rsp, 1F8h
0x18000b4bc  mov     rax, cs:__security_cookie
0x18000b4c3  xor     rax, rsp
0x18000b4c6  mov     [rbp+130h+var_50], rax
0x18000b4cd  mov     rbx, [rbp+130h+psz]
0x18000b4d4  mov     rsi, r8
0x18000b4d7  mov     r14, [rbp+130h+pwszSrc]
0x18000b4de  mov     r15, rdx
0x18000b4e1  mov     r13, [rbp+130h+arg_38]
0x18000b4e8  mov     [rsp+230h+var_1F0], r9d
0x18000b4ed  mov     [rsp+230h+var_1E8], rcx
0x18000b4f2  call    cs:__imp_CreatePopupMenu
0x18000b4f8  mov     r12, rax
0x18000b4fb  test    rax, rax
0x18000b4fe  jnz     short loc_18000B50A
0x18000b500  mov     edi, 8007000Eh
0x18000b505  jmp     loc_18000B68B
0x18000b50a  test    r15, r15
0x18000b50d  jz      short loc_18000B51B
0x18000b50f  mov     rdx, r15; punkSite
0x18000b512  mov     rcx, rsi; punk
0x18000b515  call    cs:__imp_IUnknown_SetSite
0x18000b51b  mov     [rsp+230h+ppwsz], 0
0x18000b524  test    rbx, rbx
0x18000b527  jz      short loc_18000B548
0x18000b529  lea     rdx, [rsp+230h+ppwsz]; ppwsz
0x18000b52e  mov     rcx, rbx; psz
0x18000b531  call    cs:__imp_SHStrDupA
0x18000b537  test    eax, eax
0x18000b539  js      short loc_18000B548
0x18000b53b  lea     rdx, [rsp+230h+ppwsz]; unsigned __int16 **
0x18000b540  mov     rcx, rsi; struct IContextMenu *
0x18000b543  call    ?IContextMenu_SetInvokeVerbs@@YAJPEAUIContextMenu@@QEBQEBGI@Z; IContextMenu_SetInvokeVerbs(IContextMenu *,ushort const * const * const,uint)
0x18000b548  mov     r10, [rsi]
0x18000b54b  mov     rax, rbx
0x18000b54e  neg     rax
0x18000b551  mov     rdx, r12
0x18000b554  mov     eax, 1
0x18000b559  sbb     ecx, ecx
0x18000b55b  mov     r9d, eax
0x18000b55e  and     ecx, 7FFh
0x18000b564  xor     r8d, r8d
0x18000b567  add     ecx, eax
0x18000b569  mov     rax, [r10+18h]
0x18000b56d  or      ecx, [rbp+130h+arg_20]
0x18000b573  mov     [rsp+230h+var_208], ecx
0x18000b577  mov     rcx, rsi
0x18000b57a  mov     [rsp+230h+var_210], 7FFFh
0x18000b582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b587  mov     edi, eax
0x18000b589  test    eax, eax
0x18000b58b  js      loc_18000B667
0x18000b591  test    rbx, rbx
0x18000b594  jnz     short loc_18000B5BE
0x18000b596  xor     r8d, r8d; gmdiFlags
0x18000b599  xor     edx, edx; fByPos
0x18000b59b  mov     rcx, r12; hMenu
0x18000b59e  call    cs:__imp_GetMenuDefaultItem
0x18000b5a4  cmp     eax, 0FFFFFFFFh
0x18000b5a7  jz      short loc_18000B5B4
0x18000b5a9  lea     edi, [rbx+1]
0x18000b5ac  sub     ax, di
0x18000b5af  movzx   ebx, ax
0x18000b5b2  jmp     short loc_18000B5C3
0x18000b5b4  mov     edi, 80004005h
0x18000b5b9  jmp     loc_18000B667
0x18000b5be  mov     edi, 1
0x18000b5c3  xor     edx, edx; Val
0x18000b5c5  mov     [rsp+230h+var_1D0], 68h ; 'h'
0x18000b5cd  lea     rcx, [rsp+230h+var_1CC]; void *
0x18000b5d2  lea     r8d, [rdx+64h]; Size
0x18000b5d6  call    memset_0
0x18000b5db  mov     rax, [rsp+230h+ppwsz]
0x18000b5e0  test    rax, rax
0x18000b5e3  jnz     short loc_18000B5EE
0x18000b5e5  test    r14, r14
0x18000b5e8  jnz     short loc_18000B5EE
0x18000b5ea  xor     ecx, ecx
0x18000b5ec  jmp     short loc_18000B5F3
0x18000b5ee  mov     ecx, 4000h
0x18000b5f3  or      ecx, [rsp+230h+var_1F0]
0x18000b5f7  mov     rdx, [rsp+230h+var_1E8]
0x18000b5fc  mov     [rsp+230h+var_1CC], ecx
0x18000b600  mov     [rsp+230h+var_1C8], rdx
0x18000b605  mov     [rsp+230h+var_1C0], rbx
0x18000b60a  mov     [rbp+130h+var_1A8], edi
0x18000b60d  mov     [rbp+130h+var_180], r14
0x18000b611  mov     [rbp+130h+var_190], rax
0x18000b615  test    r13, r13
0x18000b618  jz      short loc_18000B62A
0x18000b61a  mov     rax, [r13+0]
0x18000b61e  bts     ecx, 1Dh
0x18000b622  mov     [rbp+130h+var_170], rax
0x18000b626  mov     [rsp+230h+var_1CC], ecx
0x18000b62a  test    r14, r14
0x18000b62d  jz      short loc_18000B651
0x18000b62f  mov     r8d, 104h; cchBuf
0x18000b635  lea     rdx, [rbp+130h+pszDst]; pszDst
0x18000b639  mov     rcx, r14; pwszSrc
0x18000b63c  call    cs:__imp_SHUnicodeToAnsi
0x18000b642  test    eax, eax
0x18000b644  lea     rcx, [rbp+130h+pszDst]
0x18000b648  cmovs   rcx, [rbp+130h+var_1B0]
0x18000b64d  mov     [rbp+130h+var_1B0], rcx
0x18000b651  mov     rax, [rsi]
0x18000b654  lea     rdx, [rsp+230h+var_1D0]
0x18000b659  mov     rcx, rsi
0x18000b65c  mov     rax, [rax+20h]
0x18000b660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b665  mov     edi, eax
0x18000b667  test    r15, r15
0x18000b66a  jz      short loc_18000B677
0x18000b66c  xor     edx, edx; punkSite
0x18000b66e  mov     rcx, rsi; punk
0x18000b671  call    cs:__imp_IUnknown_SetSite
0x18000b677  mov     rcx, [rsp+230h+ppwsz]; pv
0x18000b67c  call    cs:__imp_CoTaskMemFree
0x18000b682  mov     rcx, r12; hMenu
0x18000b685  call    cs:__imp_DestroyMenu
0x18000b68b  mov     eax, edi
0x18000b68d  mov     rcx, [rbp+130h+var_50]
0x18000b694  xor     rcx, rsp; StackCookie
0x18000b697  call    __security_check_cookie
0x18000b69c  add     rsp, 1F8h
0x18000b6a3  pop     r15
0x18000b6a5  pop     r14
0x18000b6a7  pop     r13
0x18000b6a9  pop     r12
0x18000b6ab  pop     rdi
0x18000b6ac  pop     rsi
0x18000b6ad  pop     rbx
0x18000b6ae  pop     rbp
0x18000b6af  retn
```
