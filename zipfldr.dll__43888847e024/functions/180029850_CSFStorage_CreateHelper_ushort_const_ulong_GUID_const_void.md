# CSFStorage::_CreateHelper(ushort const *,ulong,_GUID const &,void * *)

- ea: `0x180029850`
- end: `0x18002998e`
- name: `?_CreateHelper@CSFStorage@@AEAAJPEBGKAEBU_GUID@@PEAPEAX@Z`
- size: `318`
- prototype: `__int64 __usercall@<rax>(CSFStorage *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18006dd60`
- `0x18006dd80`

## callees

- `0x1800248e0`
- `0x180029850`
- `0x180036f50`
- `0x18006e76c`
- `0x180071010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x1800298aa`
- `SHELL32!__imp_ILFree` at `0x180029955`
- `SHELL32!__imp_ILFree` at `0x1800298aa`
- `SHELL32!__imp_ILFree` at `0x180029955`
- `SHLWAPI!__imp_MapWin32ErrorToSTG` at `0x18002996d`
- `SHLWAPI!__imp_MapWin32ErrorToSTG` at `0x18002996d`
- `ole32!CreateBindCtx` at `0x1800298c8`
- `ole32!CreateBindCtx` at `0x1800298c8`

## pseudocode

```c
__int64 __fastcall CSFStorage::_CreateHelper(
        CSFStorage *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT v9; // ebx
  LPBC ppbc; // [rsp+30h] [rbp-20h] BYREF
  LPITEMIDLIST pidl[2]; // [rsp+38h] [rbp-18h] BYREF

  pidl[0] = 0;
  *a5 = 0;
  if ( (a3 & 0x1000) != 0 || (int)CSFStorage::_ParseAndVerify(this, a2, 0, (struct _ITEMID_CHILD **)pidl) < 0 )
  {
    ppbc = 0;
    v9 = CreateBindCtx(0, &ppbc);
    if ( v9 >= 0 )
    {
      pidl[0] = (LPITEMIDLIST)16;
      pidl[1] = (LPITEMIDLIST)4096;
      v9 = ((__int64 (__fastcall *)(LPBC, LPITEMIDLIST *))ppbc->lpVtbl->SetBindOptions)(ppbc, pidl);
      if ( v9 >= 0 )
      {
        pidl[0] = 0;
        v9 = CSFStorage::_ParseAndVerify(this, a2, ppbc, (struct _ITEMID_CHILD **)pidl);
        if ( v9 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(CSFStorage *, LPITEMIDLIST, _QWORD, const struct _GUID *, void **))(*(_QWORD *)this + 168LL))(
                 this,
                 pidl[0],
                 a3,
                 a4,
                 a5);
          ILFree(pidl[0]);
        }
        ((void (__fastcall *)(LPBC))ppbc->lpVtbl->Release)(ppbc);
      }
      else
      {
        SafeRelease<INewMenuClient>(&ppbc);
      }
    }
  }
  else
  {
    ILFree(pidl[0]);
    v9 = -2147024713;
  }
  return MapWin32ErrorToSTG((unsigned int)v9);
}

```

## disassembly

```asm
0x180029850  push    rbp
0x180029852  push    rbx
0x180029853  push    rsi
0x180029854  push    rdi
0x180029855  push    r12
0x180029857  push    r14
0x180029859  push    r15
0x18002985b  mov     rbp, rsp
0x18002985e  sub     rsp, 50h
0x180029862  mov     rax, cs:__security_cookie
0x180029869  xor     rax, rsp
0x18002986c  mov     [rbp+var_8], rax
0x180029870  mov     r15, [rbp+arg_20]
0x180029874  mov     r12, r9
0x180029877  mov     [rbp+pidl], 0
0x18002987f  mov     r14d, r8d
0x180029882  mov     rsi, rdx
0x180029885  mov     rdi, rcx
0x180029888  mov     qword ptr [r15], 0
0x18002988f  bt      r8d, 0Ch
0x180029894  jb      short loc_1800298BA
0x180029896  lea     r9, [rbp+pidl]; struct _ITEMID_CHILD **
0x18002989a  xor     r8d, r8d; struct IBindCtx *
0x18002989d  call    ?_ParseAndVerify@CSFStorage@@AEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMID_CHILD@@@Z; CSFStorage::_ParseAndVerify(ushort const *,IBindCtx *,_ITEMID_CHILD * *)
0x1800298a2  test    eax, eax
0x1800298a4  js      short loc_1800298BA
0x1800298a6  mov     rcx, [rbp+pidl]; pidl
0x1800298aa  call    cs:__imp_ILFree
0x1800298b0  mov     ebx, 800700B7h
0x1800298b5  jmp     loc_18002996B
0x1800298ba  lea     rdx, [rbp+ppbc]; ppbc
0x1800298be  mov     [rbp+ppbc], 0
0x1800298c6  xor     ecx, ecx; reserved
0x1800298c8  call    cs:__imp_CreateBindCtx
0x1800298ce  mov     ebx, eax
0x1800298d0  test    eax, eax
0x1800298d2  js      loc_18002996B
0x1800298d8  mov     rcx, [rbp+ppbc]
0x1800298dc  lea     rdx, [rbp+pidl]
0x1800298e0  mov     [rbp+pidl], 10h
0x1800298e8  mov     [rbp+var_10], 1000h
0x1800298f0  mov     rax, [rcx]
0x1800298f3  mov     rax, [rax+30h]
0x1800298f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298fc  mov     ebx, eax
0x1800298fe  test    eax, eax
0x180029900  jns     short loc_18002990D
0x180029902  lea     rcx, [rbp+ppbc]
0x180029906  call    ??$SafeRelease@UINewMenuClient@@@@YAXPEAPEAUINewMenuClient@@@Z; SafeRelease<INewMenuClient>(INewMenuClient * *)
0x18002990b  jmp     short loc_18002996B
0x18002990d  mov     r8, [rbp+ppbc]; struct IBindCtx *
0x180029911  lea     r9, [rbp+pidl]; struct _ITEMID_CHILD **
0x180029915  mov     rdx, rsi; unsigned __int16 *
0x180029918  mov     [rbp+pidl], 0
0x180029920  mov     rcx, rdi; this
0x180029923  call    ?_ParseAndVerify@CSFStorage@@AEAAJPEBGPEAUIBindCtx@@PEAPEAU_ITEMID_CHILD@@@Z; CSFStorage::_ParseAndVerify(ushort const *,IBindCtx *,_ITEMID_CHILD * *)
0x180029928  mov     ebx, eax
0x18002992a  test    eax, eax
0x18002992c  js      short loc_18002995B
0x18002992e  mov     rax, [rdi]
0x180029931  mov     r9, r12
0x180029934  mov     rdx, [rbp+pidl]
0x180029938  mov     r8d, r14d
0x18002993b  mov     rcx, rdi
0x18002993e  mov     [rsp+50h+var_30], r15
0x180029943  mov     rax, [rax+0A8h]
0x18002994a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002994f  mov     rcx, [rbp+pidl]; pidl
0x180029953  mov     ebx, eax
0x180029955  call    cs:__imp_ILFree
0x18002995b  mov     rcx, [rbp+ppbc]
0x18002995f  mov     rax, [rcx]
0x180029962  mov     rax, [rax+10h]
0x180029966  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002996b  mov     ecx, ebx
0x18002996d  call    cs:__imp_MapWin32ErrorToSTG
0x180029973  mov     rcx, [rbp+var_8]
0x180029977  xor     rcx, rsp; StackCookie
0x18002997a  call    __security_check_cookie
0x18002997f  add     rsp, 50h
0x180029983  pop     r15
0x180029985  pop     r14
0x180029987  pop     r12
0x180029989  pop     rdi
0x18002998a  pop     rsi
0x18002998b  pop     rbx
0x18002998c  pop     rbp
0x18002998d  retn
```
