# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x180066ce8`
- end: `0x180066f7c`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `660`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, bool)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180013d28`
- `0x180018c9c`
- `0x180067658`

## callees

- `0x180006eb8`
- `0x180066c10`
- `0x180066ce8`
- `0x1800772c0`
- `0x180078010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180066e5f`
- `SHELL32!SHBindToObject` at `0x180066e5f`
- `SHELL32!SHParseDisplayName` at `0x180066e23`
- `SHELL32!SHParseDisplayName` at `0x180066e23`
- `SHELL32!__imp_ILClone` at `0x180066ef2`
- `SHELL32!__imp_ILClone` at `0x180066ef2`
- `SHELL32!__imp_ILCombine` at `0x180066eb1`
- `SHELL32!__imp_ILCombine` at `0x180066eb1`
- `SHELL32!__imp_ILFree` at `0x180066ecf`
- `SHELL32!__imp_ILFree` at `0x180066f19`
- `SHELL32!__imp_ILFree` at `0x180066f44`
- `SHELL32!__imp_ILFree` at `0x180066ecf`
- `SHELL32!__imp_ILFree` at `0x180066f19`
- `SHELL32!__imp_ILFree` at `0x180066f44`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180066dad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180066dad`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180066d3e`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180066d3e`

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
0x180066ce8  push    rbp
0x180066cea  push    rbx
0x180066ceb  push    rsi
0x180066cec  push    rdi
0x180066ced  push    r12
0x180066cef  push    r14
0x180066cf1  push    r15
0x180066cf3  lea     rbp, [rsp-180h]
0x180066cfb  sub     rsp, 280h
0x180066d02  mov     rax, cs:__security_cookie
0x180066d09  xor     rax, rsp
0x180066d0c  mov     [rbp+1B0h+var_40], rax
0x180066d13  mov     rax, r8
0x180066d16  movzx   r15d, r9b
0x180066d1a  mov     r14, rdx
0x180066d1d  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x180066d22  mov     rdi, rcx
0x180066d25  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x180066d2c  xor     r12d, r12d
0x180066d2f  lea     rdx, SID_STopLevelBrowser; guidService
0x180066d36  mov     rcx, rax; punk
0x180066d39  mov     [rsp+2B0h+ppvOut], r12
0x180066d3e  call    cs:__imp_IUnknown_QueryService
0x180066d44  test    eax, eax
0x180066d46  js      loc_180066F5B
0x180066d4c  mov     [rsp+2B0h+ppidl], r12
0x180066d51  test    rdi, rdi
0x180066d54  jz      short loc_180066D5E
0x180066d56  mov     al, 1
0x180066d58  cmp     [rdi], r12w
0x180066d5c  jnz     short loc_180066D61
0x180066d5e  mov     al, r12b
0x180066d61  test    r14, r14
0x180066d64  jz      short loc_180066D6F
0x180066d66  mov     sil, 1
0x180066d69  cmp     [r14], r12w
0x180066d6d  jnz     short loc_180066D72
0x180066d6f  mov     sil, r12b
0x180066d72  test    al, al
0x180066d74  jnz     short loc_180066D8A
0x180066d76  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x180066d7b  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x180066d80  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x180066d85  jmp     loc_180066E29
0x180066d8a  xor     edx, edx; pUnkOuter
0x180066d8c  mov     [rsp+2B0h+pidl2], r12
0x180066d91  lea     rax, [rsp+2B0h+pidl2]
0x180066d96  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x180066d9d  mov     [rsp+2B0h+ppv], rax; ppv
0x180066da2  lea     rcx, CLSID_OpenControlPanel; rclsid
0x180066da9  lea     r8d, [rdx+1]; dwClsContext
0x180066dad  call    cs:__imp_CoCreateInstance
0x180066db3  mov     ebx, eax
0x180066db5  test    eax, eax
0x180066db7  js      loc_180066F11
0x180066dbd  mov     rcx, [rsp+2B0h+pidl2]
0x180066dc2  lea     r8, [rsp+2B0h+pszName]
0x180066dc7  mov     r9d, 104h
0x180066dcd  mov     rdx, rdi
0x180066dd0  mov     rax, [rcx]
0x180066dd3  mov     rax, [rax+20h]
0x180066dd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ddc  mov     ebx, eax
0x180066dde  test    eax, eax
0x180066de0  jns     short loc_180066DF6
0x180066de2  mov     r8, rdi; unsigned __int16 *
0x180066de5  lea     rcx, [rsp+2B0h+pszName]; unsigned __int16 *
0x180066dea  mov     edx, 104h; unsigned __int64
0x180066def  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180066df4  mov     ebx, eax
0x180066df6  mov     rcx, [rsp+2B0h+pidl2]
0x180066dfb  mov     rax, [rcx]
0x180066dfe  mov     rax, [rax+10h]
0x180066e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066e07  test    ebx, ebx
0x180066e09  js      loc_180066F11
0x180066e0f  xor     r9d, r9d; sfgaoIn
0x180066e12  mov     [rsp+2B0h+ppv], r12; psfgaoOut
0x180066e17  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x180066e1c  xor     edx, edx; pbc
0x180066e1e  lea     rcx, [rsp+2B0h+pszName]; pszName
0x180066e23  call    cs:__imp_SHParseDisplayName
0x180066e29  mov     ebx, eax
0x180066e2b  mov     rdi, r12
0x180066e2e  test    eax, eax
0x180066e30  js      loc_180066F14
0x180066e36  test    sil, sil
0x180066e39  jz      loc_180066EE8
0x180066e3f  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x180066e44  lea     rax, [rsp+2B0h+var_258]
0x180066e49  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180066e50  mov     [rsp+2B0h+ppv], rax; ppv
0x180066e55  xor     r8d, r8d; pbc
0x180066e58  mov     [rsp+2B0h+var_258], r12
0x180066e5d  xor     ecx, ecx; psf
0x180066e5f  call    cs:__imp_SHBindToObject
0x180066e65  mov     ebx, eax
0x180066e67  test    eax, eax
0x180066e69  js      loc_180066F14
0x180066e6f  mov     rcx, [rsp+2B0h+var_258]
0x180066e74  lea     rdx, [rsp+2B0h+pidl2]
0x180066e79  mov     [rsp+2B0h+pidl2], r12
0x180066e7e  mov     r9, r14
0x180066e81  mov     [rsp+2B0h+var_280], r12
0x180066e86  xor     r8d, r8d
0x180066e89  mov     [rsp+2B0h+var_288], rdx
0x180066e8e  xor     edx, edx
0x180066e90  mov     rax, [rcx]
0x180066e93  mov     [rsp+2B0h+ppv], r12
0x180066e98  mov     rax, [rax+18h]
0x180066e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ea1  mov     ebx, eax
0x180066ea3  test    eax, eax
0x180066ea5  js      short loc_180066ED5
0x180066ea7  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x180066eac  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x180066eb1  call    cs:__imp_ILCombine
0x180066eb7  mov     rcx, rax
0x180066eba  mov     rdi, rax
0x180066ebd  neg     rcx
0x180066ec0  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x180066ec5  sbb     ebx, ebx
0x180066ec7  not     ebx
0x180066ec9  and     ebx, 8007000Eh
0x180066ecf  call    cs:__imp_ILFree
0x180066ed5  mov     rcx, [rsp+2B0h+var_258]
0x180066eda  mov     rdx, [rcx]
0x180066edd  mov     rax, [rdx+10h]
0x180066ee1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ee6  jmp     short loc_180066F14
0x180066ee8  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180066eed  test    rcx, rcx
0x180066ef0  jz      short loc_180066F0A
0x180066ef2  call    cs:__imp_ILClone
0x180066ef8  mov     rdi, rax
0x180066efb  neg     rax
0x180066efe  sbb     ebx, ebx
0x180066f00  not     ebx
0x180066f02  and     ebx, 8007000Eh
0x180066f08  jmp     short loc_180066F14
0x180066f0a  mov     ebx, 80070057h
0x180066f0f  jmp     short loc_180066F14
0x180066f11  mov     rdi, r12
0x180066f14  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x180066f19  call    cs:__imp_ILFree
0x180066f1f  test    ebx, ebx
0x180066f21  js      short loc_180066F4A
0x180066f23  mov     rcx, [rsp+2B0h+ppvOut]
0x180066f28  mov     r8d, r15d
0x180066f2b  shl     r8d, 1Eh
0x180066f2f  mov     rdx, rdi
0x180066f32  inc     r8d
0x180066f35  mov     rax, [rcx]
0x180066f38  mov     rax, [rax+58h]
0x180066f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f41  mov     rcx, rdi; pidl
0x180066f44  call    cs:__imp_ILFree
0x180066f4a  mov     rcx, [rsp+2B0h+ppvOut]
0x180066f4f  mov     rax, [rcx]
0x180066f52  mov     rax, [rax+10h]
0x180066f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066f5b  mov     rcx, [rbp+1B0h+var_40]
0x180066f62  xor     rcx, rsp; StackCookie
0x180066f65  call    __security_check_cookie
0x180066f6a  add     rsp, 280h
0x180066f71  pop     r15
0x180066f73  pop     r14
0x180066f75  pop     r12
0x180066f77  pop     rdi
0x180066f78  pop     rsi
0x180066f79  pop     rbx
0x180066f7a  pop     rbp
0x180066f7b  retn
```
