# CSendTo::_DoesDestSupportZip(IDataObject *)

- ea: `0x18004580c`
- end: `0x180045a2a`
- name: `?_DoesDestSupportZip@CSendTo@@AEAAHPEAUIDataObject@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(CSendTo *__hidden this, struct IDataObject *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180045a30`

## callees

- `0x180036f50`
- `0x18004580c`
- `0x180048858`
- `0x180071010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x180045999`
- `SHELL32!SHBindToObject` at `0x180045999`
- `SHELL32!__imp_ILFree` at `0x180045a06`
- `SHELL32!__imp_ILFree` at `0x180045a06`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180045852`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800458b0`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x180045852`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x1800458b0`

## pseudocode

```c
_BOOL8 __fastcall CSendTo::_DoesDestSupportZip(CSendTo *this, struct IDataObject *a2)
{
  BOOL v4; // ebx
  IUnknown *v5; // rcx
  int v6; // ebx
  int v7; // ebx
  void *ppvOut; // [rsp+30h] [rbp-20h] BYREF
  LPCITEMIDLIST pidl; // [rsp+38h] [rbp-18h] BYREF
  void *ppv; // [rsp+40h] [rbp-10h] BYREF

  ppvOut = 0;
  v4 = 1;
  if ( IUnknown_QueryService(
         *((IUnknown **)this + 1),
         &IID_IFolderView,
         &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d,
         &ppvOut) < 0
    || (v4 = (*(int (__fastcall **)(void *, const WCHAR *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, L".zip") >= 0,
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut),
        v4) )
  {
    v5 = (IUnknown *)*((_QWORD *)this + 1);
    ppv = 0;
    if ( IUnknown_QueryService(v5, &IID_IFolderView, &GUID_cde725b0_ccc9_4519_917e_325d72fab4ce, &ppv) < 0 )
      goto LABEL_9;
    pidl = 0;
    if ( (*(int (__fastcall **)(void *, GUID *, LPCITEMIDLIST *))(*(_QWORD *)ppv + 40LL))(
           ppv,
           &GUID_000214e6_0000_0000_c000_000000000046,
           &pidl) >= 0 )
    {
      if ( (*(int (__fastcall **)(LPCITEMIDLIST, _QWORD, GUID *, void **))(*(_QWORD *)&pidl->mkid.cb + 64LL))(
             pidl,
             0,
             &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d,
             &ppvOut) >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(void *, const WCHAR *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, L".zip");
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
        v4 = v6 >= 0;
      }
      (*(void (__fastcall **)(LPCITEMIDLIST))(*(_QWORD *)&pidl->mkid.cb + 16LL))(pidl);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v4 )
    {
LABEL_9:
      pidl = 0;
      if ( (int)DataObj_GetFolderIDList(a2, &pidl) >= 0 )
      {
        ppv = 0;
        if ( SHBindToObject(0, pidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv) >= 0 )
        {
          if ( (*(int (__fastcall **)(void *, _QWORD, GUID *, void **))(*(_QWORD *)ppv + 64LL))(
                 ppv,
                 0,
                 &GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d,
                 &ppvOut) >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(void *, const WCHAR *))(*(_QWORD *)ppvOut + 24LL))(ppvOut, L".zip");
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
            v4 = v7 >= 0;
          }
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        ILFree((LPITEMIDLIST)pidl);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18004580c  mov     [rsp-18h+arg_10], rbx
0x180045811  push    rbp
0x180045812  push    rsi
0x180045813  push    rdi
0x180045814  mov     rbp, rsp
0x180045817  sub     rsp, 50h
0x18004581b  mov     rax, cs:__security_cookie
0x180045822  xor     rax, rsp
0x180045825  mov     [rbp+var_8], rax
0x180045829  mov     rsi, rdx
0x18004582c  mov     [rbp+ppvOut], 0
0x180045834  mov     rdi, rcx
0x180045837  lea     rdx, IID_IFolderView; guidService
0x18004583e  mov     rcx, [rcx+8]; punk
0x180045842  lea     r9, [rbp+ppvOut]; ppvOut
0x180045846  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d; riid
0x18004584d  mov     ebx, 1
0x180045852  call    cs:__imp_IUnknown_QueryService
0x180045858  test    eax, eax
0x18004585a  js      short loc_180045892
0x18004585c  mov     rcx, [rbp+ppvOut]
0x180045860  lea     rdx, pszStr2; ".zip"
0x180045867  mov     rax, [rcx]
0x18004586a  mov     rax, [rax+18h]
0x18004586e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045873  mov     rcx, [rbp+ppvOut]
0x180045877  mov     ebx, eax
0x180045879  not     ebx
0x18004587b  shr     ebx, 1Fh
0x18004587e  mov     rax, [rcx]
0x180045881  mov     rax, [rax+10h]
0x180045885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004588a  test    ebx, ebx
0x18004588c  jz      loc_180045A0C
0x180045892  mov     rcx, [rdi+8]; punk
0x180045896  lea     r9, [rbp+var_10]; ppvOut
0x18004589a  lea     r8, _GUID_cde725b0_ccc9_4519_917e_325d72fab4ce; riid
0x1800458a1  mov     [rbp+var_10], 0
0x1800458a9  lea     rdx, IID_IFolderView; guidService
0x1800458b0  call    cs:__imp_IUnknown_QueryService
0x1800458b6  test    eax, eax
0x1800458b8  js      loc_18004595C
0x1800458be  mov     rcx, [rbp+var_10]
0x1800458c2  lea     r8, [rbp+pidl]
0x1800458c6  mov     [rbp+pidl], 0
0x1800458ce  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046
0x1800458d5  mov     rax, [rcx]
0x1800458d8  mov     rax, [rax+28h]
0x1800458dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800458e1  test    eax, eax
0x1800458e3  js      short loc_180045944
0x1800458e5  mov     rcx, [rbp+pidl]
0x1800458e9  lea     r9, [rbp+ppvOut]
0x1800458ed  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d
0x1800458f4  xor     edx, edx
0x1800458f6  mov     rax, [rcx]
0x1800458f9  mov     rax, [rax+40h]
0x1800458fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045902  test    eax, eax
0x180045904  js      short loc_180045934
0x180045906  mov     rcx, [rbp+ppvOut]
0x18004590a  lea     rdx, pszStr2; ".zip"
0x180045911  mov     rax, [rcx]
0x180045914  mov     rax, [rax+18h]
0x180045918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004591d  mov     rcx, [rbp+ppvOut]
0x180045921  mov     ebx, eax
0x180045923  mov     rax, [rcx]
0x180045926  mov     rax, [rax+10h]
0x18004592a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004592f  not     ebx
0x180045931  shr     ebx, 1Fh
0x180045934  mov     rcx, [rbp+pidl]
0x180045938  mov     rax, [rcx]
0x18004593b  mov     rax, [rax+10h]
0x18004593f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045944  mov     rcx, [rbp+var_10]
0x180045948  mov     rax, [rcx]
0x18004594b  mov     rax, [rax+10h]
0x18004594f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045954  test    ebx, ebx
0x180045956  jz      loc_180045A0C
0x18004595c  lea     rdx, [rbp+pidl]
0x180045960  mov     [rbp+pidl], 0
0x180045968  mov     rcx, rsi
0x18004596b  call    DataObj_GetFolderIDList
0x180045970  test    eax, eax
0x180045972  js      loc_180045A0C
0x180045978  mov     rdx, [rbp+pidl]; pidl
0x18004597c  lea     rax, [rbp+var_10]
0x180045980  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180045987  mov     [rsp+50h+ppv], rax; ppv
0x18004598c  xor     r8d, r8d; pbc
0x18004598f  mov     [rbp+var_10], 0
0x180045997  xor     ecx, ecx; psf
0x180045999  call    cs:__imp_SHBindToObject
0x18004599f  test    eax, eax
0x1800459a1  js      short loc_180045A02
0x1800459a3  mov     rcx, [rbp+var_10]
0x1800459a7  lea     r9, [rbp+ppvOut]
0x1800459ab  lea     r8, _GUID_24d16ee5_10f5_4de3_8766_d23779ba7a6d
0x1800459b2  xor     edx, edx
0x1800459b4  mov     rax, [rcx]
0x1800459b7  mov     rax, [rax+40h]
0x1800459bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459c0  test    eax, eax
0x1800459c2  js      short loc_1800459F2
0x1800459c4  mov     rcx, [rbp+ppvOut]
0x1800459c8  lea     rdx, pszStr2; ".zip"
0x1800459cf  mov     rax, [rcx]
0x1800459d2  mov     rax, [rax+18h]
0x1800459d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459db  mov     rcx, [rbp+ppvOut]
0x1800459df  mov     ebx, eax
0x1800459e1  mov     rax, [rcx]
0x1800459e4  mov     rax, [rax+10h]
0x1800459e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800459ed  not     ebx
0x1800459ef  shr     ebx, 1Fh
0x1800459f2  mov     rcx, [rbp+var_10]
0x1800459f6  mov     rdx, [rcx]
0x1800459f9  mov     rax, [rdx+10h]
0x1800459fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045a02  mov     rcx, [rbp+pidl]; pidl
0x180045a06  call    cs:__imp_ILFree
0x180045a0c  mov     eax, ebx
0x180045a0e  mov     rcx, [rbp+var_8]
0x180045a12  xor     rcx, rsp; StackCookie
0x180045a15  call    __security_check_cookie
0x180045a1a  mov     rbx, [rsp+50h+arg_10]
0x180045a22  add     rsp, 50h
0x180045a26  pop     rdi
0x180045a27  pop     rsi
0x180045a28  pop     rbp
0x180045a29  retn
```
