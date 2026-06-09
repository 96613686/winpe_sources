# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x180051958`
- end: `0x180051c23`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `715`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800522bc`

## callees

- `0x180002280`
- `0x18000809c`
- `0x180051880`
- `0x180051958`
- `0x180057010`

## import_xrefs

- `SHELL32!SHParseDisplayName` at `0x180051a9f`
- `SHELL32!SHParseDisplayName` at `0x180051a9f`
- `SHELL32!SHBindToObject` at `0x180051ae1`
- `SHELL32!SHBindToObject` at `0x180051ae1`
- `SHELL32!__imp_ILClone` at `0x180051b86`
- `SHELL32!__imp_ILClone` at `0x180051b86`
- `SHELL32!__imp_ILCombine` at `0x180051b39`
- `SHELL32!__imp_ILCombine` at `0x180051b39`
- `SHELL32!__imp_ILFree` at `0x180051b5d`
- `SHELL32!__imp_ILFree` at `0x180051bb3`
- `SHELL32!__imp_ILFree` at `0x180051be4`
- `SHELL32!__imp_ILFree` at `0x180051b5d`
- `SHELL32!__imp_ILFree` at `0x180051bb3`
- `SHELL32!__imp_ILFree` at `0x180051be4`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800519ae`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800519ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051a23`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051a23`

## pseudocode

```c
void __fastcall CNavigateButton::Navigate(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  char v7; // al
  char v8; // si
  HRESULT CplRoot; // eax
  HRESULT Instance; // ebx
  ITEMIDLIST *v11; // rdi
  LPCITEMIDLIST pidl2; // [rsp+40h] [rbp-C0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+48h] [rbp-B8h] BYREF
  void *ppvOut; // [rsp+50h] [rbp-B0h] BYREF
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
  if ( !a1 || (v7 = 1, !*a1) )
    v7 = 0;
  if ( !a2 || (v8 = 1, !*a2) )
    v8 = 0;
  if ( !v7 )
  {
    CplRoot = CNavigateButton::GetCplRoot((struct IShellBrowser *)ppvOut, &ppidl);
    goto LABEL_15;
  }
  pidl2 = 0;
  Instance = CoCreateInstance(
               &CLSID_OpenControlPanel,
               0,
               1u,
               &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1,
               (LPVOID *)&pidl2);
  if ( Instance >= 0 )
  {
    Instance = (*(__int64 (__fastcall **)(LPCITEMIDLIST, const unsigned __int16 *, WCHAR *, __int64))(*(_QWORD *)&pidl2->mkid.cb + 32LL))(
                 pidl2,
                 a1,
                 pszName,
                 260);
    if ( Instance < 0 )
      Instance = StringCchCopyW(pszName, 0x104u, a1);
    (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl2->mkid.cb + 16LL))(pidl2);
    if ( Instance >= 0 )
    {
      CplRoot = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
LABEL_15:
      Instance = CplRoot;
      v11 = 0;
      if ( CplRoot >= 0 )
      {
        if ( v8 )
        {
          ppv = 0;
          Instance = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
          if ( Instance >= 0 )
          {
            pidl2 = 0;
            Instance = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                         ppv,
                         0,
                         0,
                         a2,
                         0,
                         &pidl2,
                         0);
            if ( Instance >= 0 )
            {
              v11 = ILCombine(ppidl, pidl2);
              Instance = v11 == 0 ? 0x8007000E : 0;
              ILFree((LPITEMIDLIST)pidl2);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
          }
        }
        else if ( ppidl )
        {
          v11 = ILClone(ppidl);
          Instance = v11 == 0 ? 0x8007000E : 0;
        }
        else
        {
          Instance = -2147024809;
        }
      }
      goto LABEL_25;
    }
  }
  v11 = 0;
LABEL_25:
  ILFree(ppidl);
  if ( Instance >= 0 )
  {
    (*(void (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
      ppvOut,
      v11,
      (unsigned int)((v4 << 30) + 1));
    ILFree(v11);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
}

```

## disassembly

```asm
0x180051958  push    rbp
0x18005195a  push    rbx
0x18005195b  push    rsi
0x18005195c  push    rdi
0x18005195d  push    r12
0x18005195f  push    r14
0x180051961  push    r15
0x180051963  lea     rbp, [rsp-180h]
0x18005196b  sub     rsp, 280h
0x180051972  mov     rax, cs:__security_cookie
0x180051979  xor     rax, rsp
0x18005197c  mov     [rbp+1B0h+var_40], rax
0x180051983  mov     rax, r8
0x180051986  movzx   r15d, r9b
0x18005198a  mov     r14, rdx
0x18005198d  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x180051992  mov     rdi, rcx
0x180051995  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18005199c  xor     r12d, r12d
0x18005199f  lea     rdx, SID_STopLevelBrowser; guidService
0x1800519a6  mov     rcx, rax; punk
0x1800519a9  mov     [rsp+2B0h+ppvOut], r12
0x1800519ae  call    cs:__imp_IUnknown_QueryService
0x1800519b5  nop     dword ptr [rax+rax+00h]
0x1800519ba  test    eax, eax
0x1800519bc  js      loc_180051C01
0x1800519c2  mov     [rsp+2B0h+ppidl], r12
0x1800519c7  test    rdi, rdi
0x1800519ca  jz      short loc_1800519D4
0x1800519cc  mov     al, 1
0x1800519ce  cmp     [rdi], r12w
0x1800519d2  jnz     short loc_1800519D7
0x1800519d4  mov     al, r12b
0x1800519d7  test    r14, r14
0x1800519da  jz      short loc_1800519E5
0x1800519dc  mov     sil, 1
0x1800519df  cmp     [r14], r12w
0x1800519e3  jnz     short loc_1800519E8
0x1800519e5  mov     sil, r12b
0x1800519e8  test    al, al
0x1800519ea  jnz     short loc_180051A00
0x1800519ec  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x1800519f1  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x1800519f6  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x1800519fb  jmp     loc_180051AAB
0x180051a00  xor     edx, edx; pUnkOuter
0x180051a02  mov     [rsp+2B0h+pidl2], r12
0x180051a07  lea     rax, [rsp+2B0h+pidl2]
0x180051a0c  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180051a13  mov     [rsp+2B0h+ppv], rax; ppv
0x180051a18  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180051a1f  lea     r8d, [rdx+1]; dwClsContext
0x180051a23  call    cs:__imp_CoCreateInstance
0x180051a2a  nop     dword ptr [rax+rax+00h]
0x180051a2f  mov     ebx, eax
0x180051a31  test    eax, eax
0x180051a33  js      loc_180051BAB
0x180051a39  mov     rcx, [rsp+2B0h+pidl2]
0x180051a3e  lea     r8, [rsp+2B0h+pszName]
0x180051a43  mov     r9d, 104h
0x180051a49  mov     rdx, rdi
0x180051a4c  mov     rax, [rcx]
0x180051a4f  mov     rax, [rax+20h]
0x180051a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a58  mov     ebx, eax
0x180051a5a  test    eax, eax
0x180051a5c  jns     short loc_180051A72
0x180051a5e  mov     r8, rdi; unsigned __int16 *
0x180051a61  lea     rcx, [rsp+2B0h+pszName]; unsigned __int16 *
0x180051a66  mov     edx, 104h; unsigned __int64
0x180051a6b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180051a70  mov     ebx, eax
0x180051a72  mov     rcx, [rsp+2B0h+pidl2]
0x180051a77  mov     rax, [rcx]
0x180051a7a  mov     rax, [rax+10h]
0x180051a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051a83  test    ebx, ebx
0x180051a85  js      loc_180051BAB
0x180051a8b  xor     r9d, r9d; sfgaoIn
0x180051a8e  mov     [rsp+2B0h+ppv], r12; psfgaoOut
0x180051a93  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x180051a98  xor     edx, edx; pbc
0x180051a9a  lea     rcx, [rsp+2B0h+pszName]; pszName
0x180051a9f  call    cs:__imp_SHParseDisplayName
0x180051aa6  nop     dword ptr [rax+rax+00h]
0x180051aab  mov     ebx, eax
0x180051aad  mov     rdi, r12
0x180051ab0  test    eax, eax
0x180051ab2  js      loc_180051BAE
0x180051ab8  test    sil, sil
0x180051abb  jz      loc_180051B7C
0x180051ac1  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x180051ac6  lea     rax, [rsp+2B0h+var_258]
0x180051acb  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180051ad2  mov     [rsp+2B0h+ppv], rax; ppv
0x180051ad7  xor     r8d, r8d; pbc
0x180051ada  mov     [rsp+2B0h+var_258], r12
0x180051adf  xor     ecx, ecx; psf
0x180051ae1  call    cs:__imp_SHBindToObject
0x180051ae8  nop     dword ptr [rax+rax+00h]
0x180051aed  mov     ebx, eax
0x180051aef  test    eax, eax
0x180051af1  js      loc_180051BAE
0x180051af7  mov     rcx, [rsp+2B0h+var_258]
0x180051afc  lea     rdx, [rsp+2B0h+pidl2]
0x180051b01  mov     [rsp+2B0h+pidl2], r12
0x180051b06  mov     r9, r14
0x180051b09  mov     [rsp+2B0h+var_280], r12
0x180051b0e  xor     r8d, r8d
0x180051b11  mov     [rsp+2B0h+var_288], rdx
0x180051b16  xor     edx, edx
0x180051b18  mov     rax, [rcx]
0x180051b1b  mov     [rsp+2B0h+ppv], r12
0x180051b20  mov     rax, [rax+18h]
0x180051b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b29  mov     ebx, eax
0x180051b2b  test    eax, eax
0x180051b2d  js      short loc_180051B69
0x180051b2f  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x180051b34  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x180051b39  call    cs:__imp_ILCombine
0x180051b40  nop     dword ptr [rax+rax+00h]
0x180051b45  mov     rcx, rax
0x180051b48  mov     rdi, rax
0x180051b4b  neg     rcx
0x180051b4e  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x180051b53  sbb     ebx, ebx
0x180051b55  not     ebx
0x180051b57  and     ebx, 8007000Eh
0x180051b5d  call    cs:__imp_ILFree
0x180051b64  nop     dword ptr [rax+rax+00h]
0x180051b69  mov     rcx, [rsp+2B0h+var_258]
0x180051b6e  mov     rdx, [rcx]
0x180051b71  mov     rax, [rdx+10h]
0x180051b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051b7a  jmp     short loc_180051BAE
0x180051b7c  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180051b81  test    rcx, rcx
0x180051b84  jz      short loc_180051BA4
0x180051b86  call    cs:__imp_ILClone
0x180051b8d  nop     dword ptr [rax+rax+00h]
0x180051b92  mov     rdi, rax
0x180051b95  neg     rax
0x180051b98  sbb     ebx, ebx
0x180051b9a  not     ebx
0x180051b9c  and     ebx, 8007000Eh
0x180051ba2  jmp     short loc_180051BAE
0x180051ba4  mov     ebx, 80070057h
0x180051ba9  jmp     short loc_180051BAE
0x180051bab  mov     rdi, r12
0x180051bae  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180051bb3  call    cs:__imp_ILFree
0x180051bba  nop     dword ptr [rax+rax+00h]
0x180051bbf  test    ebx, ebx
0x180051bc1  js      short loc_180051BF0
0x180051bc3  mov     rcx, [rsp+2B0h+ppvOut]
0x180051bc8  mov     r8d, r15d
0x180051bcb  shl     r8d, 1Eh
0x180051bcf  mov     rdx, rdi
0x180051bd2  inc     r8d
0x180051bd5  mov     rax, [rcx]
0x180051bd8  mov     rax, [rax+58h]
0x180051bdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051be1  mov     rcx, rdi; pidl
0x180051be4  call    cs:__imp_ILFree
0x180051beb  nop     dword ptr [rax+rax+00h]
0x180051bf0  mov     rcx, [rsp+2B0h+ppvOut]
0x180051bf5  mov     rax, [rcx]
0x180051bf8  mov     rax, [rax+10h]
0x180051bfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c01  mov     rcx, [rbp+1B0h+var_40]
0x180051c08  xor     rcx, rsp; StackCookie
0x180051c0b  call    __security_check_cookie
0x180051c10  add     rsp, 280h
0x180051c17  pop     r15
0x180051c19  pop     r14
0x180051c1b  pop     r12
0x180051c1d  pop     rdi
0x180051c1e  pop     rsi
0x180051c1f  pop     rbx
0x180051c20  pop     rbp
0x180051c21  retn
```
