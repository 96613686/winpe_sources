# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x18001b6b8`
- end: `0x18001b8d2`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001cbb4`

## callees

- `0x180001d60`
- `0x18001a79c`
- `0x18001b6b8`
- `0x18001c590`
- `0x18001e010`

## import_xrefs

- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001b70e`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18001b70e`
- `SHELL32!SHBindToObject` at `0x18001b7ba`
- `SHELL32!SHBindToObject` at `0x18001b7ba`
- `SHELL32!SHParseDisplayName` at `0x18001b77e`
- `SHELL32!SHParseDisplayName` at `0x18001b77e`
- `SHELL32!__imp_ILClone` at `0x18001b84d`
- `SHELL32!__imp_ILClone` at `0x18001b84d`
- `SHELL32!__imp_ILCombine` at `0x18001b80c`
- `SHELL32!__imp_ILCombine` at `0x18001b80c`
- `SHELL32!__imp_ILFree` at `0x18001b82a`
- `SHELL32!__imp_ILFree` at `0x18001b86f`
- `SHELL32!__imp_ILFree` at `0x18001b89a`
- `SHELL32!__imp_ILFree` at `0x18001b82a`
- `SHELL32!__imp_ILFree` at `0x18001b86f`
- `SHELL32!__imp_ILFree` at `0x18001b89a`

## pseudocode

```c
void __fastcall CNavigateButton::Navigate(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  unsigned int v7; // r8d
  char v8; // al
  char v9; // si
  HRESULT CplRoot; // eax
  HRESULT v11; // ebx
  ITEMIDLIST *v12; // rdi
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a4;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a3,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
    return;
  ppidl = 0;
  if ( !a1 || (v8 = 1, !*a1) )
    v8 = 0;
  if ( !a2 || (v9 = 1, !*a2) )
    v9 = 0;
  if ( !v8 )
  {
    CplRoot = CNavigateButton::GetCplRoot((struct IShellBrowser *)ppvOut, &ppidl);
LABEL_12:
    v11 = CplRoot;
    goto LABEL_13;
  }
  v11 = TranslateCplCanonicalName(a1, pszName, v7);
  if ( v11 >= 0 )
  {
    CplRoot = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    goto LABEL_12;
  }
LABEL_13:
  v12 = 0;
  if ( v11 >= 0 )
  {
    if ( v9 )
    {
      ppv = 0;
      v11 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( v11 >= 0 )
      {
        pidl2 = 0;
        v11 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                0,
                a2,
                0,
                &pidl2,
                0);
        if ( v11 >= 0 )
        {
          v12 = ILCombine(ppidl, pidl2);
          v11 = v12 == 0 ? 0x8007000E : 0;
          ILFree((LPITEMIDLIST)pidl2);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else if ( ppidl )
    {
      v12 = ILClone(ppidl);
      v11 = v12 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v11 = -2147024809;
    }
  }
  ILFree(ppidl);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
      ppvOut,
      v12,
      (unsigned int)((v4 << 30) + 1));
    ILFree(v12);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
}

```

## disassembly

```asm
0x18001b6b8  push    rbp
0x18001b6ba  push    rbx
0x18001b6bb  push    rsi
0x18001b6bc  push    rdi
0x18001b6bd  push    r12
0x18001b6bf  push    r14
0x18001b6c1  push    r15
0x18001b6c3  lea     rbp, [rsp-180h]
0x18001b6cb  sub     rsp, 280h
0x18001b6d2  mov     rax, cs:__security_cookie
0x18001b6d9  xor     rax, rsp
0x18001b6dc  mov     [rbp+1B0h+var_40], rax
0x18001b6e3  mov     rax, r8
0x18001b6e6  movzx   r15d, r9b
0x18001b6ea  mov     r14, rdx
0x18001b6ed  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x18001b6f2  mov     rbx, rcx
0x18001b6f5  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18001b6fc  xor     r12d, r12d
0x18001b6ff  lea     rdx, SID_STopLevelBrowser; guidService
0x18001b706  mov     rcx, rax; punk
0x18001b709  mov     [rsp+2B0h+ppvOut], r12
0x18001b70e  call    cs:__imp_IUnknown_QueryService
0x18001b714  test    eax, eax
0x18001b716  js      loc_18001B8B1
0x18001b71c  mov     [rsp+2B0h+ppidl], r12
0x18001b721  test    rbx, rbx
0x18001b724  jz      short loc_18001B72E
0x18001b726  mov     al, 1
0x18001b728  cmp     [rbx], r12w
0x18001b72c  jnz     short loc_18001B731
0x18001b72e  mov     al, r12b
0x18001b731  test    r14, r14
0x18001b734  jz      short loc_18001B73F
0x18001b736  mov     sil, 1
0x18001b739  cmp     [r14], r12w
0x18001b73d  jnz     short loc_18001B742
0x18001b73f  mov     sil, r12b
0x18001b742  test    al, al
0x18001b744  jnz     short loc_18001B757
0x18001b746  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x18001b74b  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x18001b750  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18001b755  jmp     short loc_18001B784
0x18001b757  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x18001b75c  mov     rcx, rbx; unsigned __int16 *
0x18001b75f  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18001b764  mov     ebx, eax
0x18001b766  test    eax, eax
0x18001b768  js      short loc_18001B786
0x18001b76a  xor     r9d, r9d; sfgaoIn
0x18001b76d  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x18001b772  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x18001b777  xor     edx, edx; pbc
0x18001b779  lea     rcx, [rsp+2B0h+pszName]; pszName
0x18001b77e  call    cs:__imp_SHParseDisplayName
0x18001b784  mov     ebx, eax
0x18001b786  mov     rdi, r12
0x18001b789  test    ebx, ebx
0x18001b78b  js      loc_18001B86A
0x18001b791  test    sil, sil
0x18001b794  jz      loc_18001B843
0x18001b79a  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x18001b79f  lea     rax, [rsp+2B0h+ppv]
0x18001b7a4  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18001b7ab  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x18001b7b0  xor     r8d, r8d; pbc
0x18001b7b3  mov     [rsp+2B0h+ppv], r12
0x18001b7b8  xor     ecx, ecx; psf
0x18001b7ba  call    cs:__imp_SHBindToObject
0x18001b7c0  mov     ebx, eax
0x18001b7c2  test    eax, eax
0x18001b7c4  js      loc_18001B86A
0x18001b7ca  mov     rcx, [rsp+2B0h+ppv]
0x18001b7cf  lea     rdx, [rsp+2B0h+pidl2]
0x18001b7d4  mov     [rsp+2B0h+pidl2], r12
0x18001b7d9  mov     r9, r14
0x18001b7dc  mov     [rsp+2B0h+var_280], r12
0x18001b7e1  xor     r8d, r8d
0x18001b7e4  mov     [rsp+2B0h+var_288], rdx
0x18001b7e9  xor     edx, edx
0x18001b7eb  mov     rax, [rcx]
0x18001b7ee  mov     [rsp+2B0h+psfgaoOut], r12
0x18001b7f3  mov     rax, [rax+18h]
0x18001b7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7fc  mov     ebx, eax
0x18001b7fe  test    eax, eax
0x18001b800  js      short loc_18001B830
0x18001b802  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x18001b807  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x18001b80c  call    cs:__imp_ILCombine
0x18001b812  mov     rcx, rax
0x18001b815  mov     rdi, rax
0x18001b818  neg     rcx
0x18001b81b  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x18001b820  sbb     ebx, ebx
0x18001b822  not     ebx
0x18001b824  and     ebx, 8007000Eh
0x18001b82a  call    cs:__imp_ILFree
0x18001b830  mov     rcx, [rsp+2B0h+ppv]
0x18001b835  mov     rdx, [rcx]
0x18001b838  mov     rax, [rdx+10h]
0x18001b83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b841  jmp     short loc_18001B86A
0x18001b843  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18001b848  test    rcx, rcx
0x18001b84b  jz      short loc_18001B865
0x18001b84d  call    cs:__imp_ILClone
0x18001b853  mov     rdi, rax
0x18001b856  neg     rax
0x18001b859  sbb     ebx, ebx
0x18001b85b  not     ebx
0x18001b85d  and     ebx, 8007000Eh
0x18001b863  jmp     short loc_18001B86A
0x18001b865  mov     ebx, 80070057h
0x18001b86a  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18001b86f  call    cs:__imp_ILFree
0x18001b875  test    ebx, ebx
0x18001b877  js      short loc_18001B8A0
0x18001b879  mov     rcx, [rsp+2B0h+ppvOut]
0x18001b87e  mov     r8d, r15d
0x18001b881  shl     r8d, 1Eh
0x18001b885  mov     rdx, rdi
0x18001b888  inc     r8d
0x18001b88b  mov     rax, [rcx]
0x18001b88e  mov     rax, [rax+58h]
0x18001b892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b897  mov     rcx, rdi; pidl
0x18001b89a  call    cs:__imp_ILFree
0x18001b8a0  mov     rcx, [rsp+2B0h+ppvOut]
0x18001b8a5  mov     rax, [rcx]
0x18001b8a8  mov     rax, [rax+10h]
0x18001b8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8b1  mov     rcx, [rbp+1B0h+var_40]
0x18001b8b8  xor     rcx, rsp; StackCookie
0x18001b8bb  call    __security_check_cookie
0x18001b8c0  add     rsp, 280h
0x18001b8c7  pop     r15
0x18001b8c9  pop     r14
0x18001b8cb  pop     r12
0x18001b8cd  pop     rdi
0x18001b8ce  pop     rsi
0x18001b8cf  pop     rbx
0x18001b8d0  pop     rbp
0x18001b8d1  retn
```
