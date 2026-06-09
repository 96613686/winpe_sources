# CSrchAdminSSO::_DeleteIndexedMapiItems(void)

- ea: `0x18002e590`
- end: `0x18002e8ac`
- name: `?_DeleteIndexedMapiItems@CSrchAdminSSO@@AEAAJXZ`
- size: `796`
- prototype: `__int64 __fastcall(CSrchAdminSSO *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180002750`

## callees

- `0x1800038ac`
- `0x180005cc0`
- `0x18000de7c`
- `0x18002e590`
- `0x18002ea48`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e750`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e799`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e7f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e750`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e799`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002e7f9`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e5d4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002e5d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e837`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e837`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e852`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002e852`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CSrchAdminSSO::_DeleteIndexedMapiItems(CSrchAdminSSO *this)
{
  unsigned int v1; // ebx
  int SIDString; // edi
  CSrchAdminSSO *v3; // rcx
  __int64 v4; // r9
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  WCHAR *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rcx
  __int64 v14; // rax
  PCNZWCH lpString1; // [rsp+30h] [rbp-29h] BYREF
  PCNZWCH lpString2; // [rsp+38h] [rbp-21h] BYREF
  __int64 v18; // [rsp+40h] [rbp-19h] BYREF
  __int64 v19; // [rsp+48h] [rbp-11h] BYREF
  __int64 v20; // [rsp+50h] [rbp-9h] BYREF
  CSrchAdminSSO *v21; // [rsp+58h] [rbp-1h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp+7h] BYREF
  wchar_t v23[4]; // [rsp+68h] [rbp+Fh] BYREF
  WCHAR String2[12]; // [rsp+70h] [rbp+17h] BYREF

  v1 = 0;
  ppv = 0;
  SIDString = CoCreateInstance(
                &GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39,
                0,
                0x15u,
                &GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69,
                &ppv);
  v3 = 0;
  v21 = 0;
  if ( SIDString >= 0 )
  {
    SIDString = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *, CSrchAdminSSO **))(*(_QWORD *)ppv + 80LL))(
                  ppv,
                  L"SystemIndex",
                  &v21);
    v3 = v21;
  }
  v18 = 0;
  if ( SIDString >= 0 )
    SIDString = (*(__int64 (__fastcall **)(CSrchAdminSSO *, __int64 *))(*(_QWORD *)v3 + 224LL))(v3, &v18);
  wcscpy(String2, L"mapi://{");
  wcscpy(v23, L"}/");
  lpString2 = 0;
  if ( SIDString >= 0 )
    SIDString = CSrchAdminSSO::_GetSIDString(v3, (unsigned __int16 **)&lpString2);
  v20 = 0;
  if ( SIDString >= 0 )
  {
    SIDString = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 48LL))(v18, &v20);
    if ( SIDString >= 0 && !v20 )
      SIDString = 1;
  }
  v19 = 0;
  while ( !SIDString )
  {
    SIDString = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v20 + 24LL))(
                  v20,
                  1,
                  &v19,
                  0);
    if ( SIDString )
      break;
    lpString1 = 0;
    SIDString = (*(__int64 (__fastcall **)(__int64, PCNZWCH *))(*(_QWORD *)v19 + 48LL))(v19, &lpString1);
    if ( SIDString >= 0 )
    {
      v4 = -1;
      do
        ++v4;
      while ( String2[v4] );
      v5 = -1;
      do
        ++v5;
      while ( v23[v5] );
      v6 = -1;
      do
        ++v6;
      while ( lpString2[v6] );
      v7 = v6 + v4 + v5;
      v8 = (WCHAR *)lpString1;
      v9 = -1;
      do
        ++v9;
      while ( lpString1[v9] );
      if ( v9 == v7 )
      {
        if ( CompareStringW(0x7Fu, 1u, lpString1, v4, String2, -1) == 2 )
        {
          v10 = -1;
          do
            ++v10;
          while ( lpString2[v10] );
          v11 = -1;
          do
            ++v11;
          while ( String2[v11] );
          if ( CompareStringW(0x7Fu, 1u, &lpString1[v11], v10, lpString2, -1) == 2 )
          {
            v12 = -1;
            do
              ++v12;
            while ( v23[v12] );
            v13 = -1;
            do
              ++v13;
            while ( String2[v13] );
            v14 = -1;
            do
              ++v14;
            while ( lpString2[v14] );
            if ( CompareStringW(0x7Fu, 1u, &lpString1[v14 + v13], v12, v23, -1) == 2 )
            {
              SIDString = (*(__int64 (__fastcall **)(__int64, PCNZWCH))(*(_QWORD *)v18 + 40LL))(v18, lpString1);
              if ( SIDString >= 0 )
                SIDString = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v18 + 128LL))(v18);
            }
          }
        }
        v8 = (WCHAR *)lpString1;
      }
      CoTaskMemFree(v8);
    }
    ATL::CComPtrBase<ISearchRoot>::Release(&v19);
  }
  LocalFree((HLOCAL)lpString2);
  if ( SIDString != 1 )
    v1 = SIDString;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v20);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppv);
  return v1;
}

```

## disassembly

```asm
0x18002e590  push    rbp
0x18002e592  push    rbx
0x18002e593  push    rsi
0x18002e594  push    rdi
0x18002e595  push    r14
0x18002e597  lea     rbp, [rsp-37h]
0x18002e59c  sub     rsp, 90h
0x18002e5a3  mov     rax, cs:__security_cookie
0x18002e5aa  xor     rax, rsp
0x18002e5ad  mov     [rbp+57h+var_28], rax
0x18002e5b1  xor     ebx, ebx
0x18002e5b3  mov     [rbp+57h+var_50], rbx
0x18002e5b7  lea     rax, [rbp+57h+var_50]
0x18002e5bb  mov     [rsp+0B0h+ppv], rax; ppv
0x18002e5c0  lea     r9, _GUID_ab310581_ac80_11d1_8df3_00c04fb6ef69; riid
0x18002e5c7  xor     edx, edx; pUnkOuter
0x18002e5c9  lea     r8d, [rbx+15h]; dwClsContext
0x18002e5cd  lea     rcx, _GUID_7d096c5f_ac08_4f1f_beb7_5c22c517ce39; rclsid
0x18002e5d4  call    cs:__imp_CoCreateInstance
0x18002e5da  mov     edi, eax
0x18002e5dc  mov     ecx, ebx
0x18002e5de  mov     [rbp+57h+var_58], rbx
0x18002e5e2  test    eax, eax
0x18002e5e4  js      short loc_18002E607
0x18002e5e6  mov     rcx, [rbp+57h+var_50]
0x18002e5ea  mov     rax, [rcx]
0x18002e5ed  lea     r8, [rbp+57h+var_58]
0x18002e5f1  lea     rdx, aSystemindex; "SystemIndex"
0x18002e5f8  mov     rax, [rax+50h]
0x18002e5fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e601  mov     edi, eax
0x18002e603  mov     rcx, [rbp+57h+var_58]
0x18002e607  mov     [rbp+57h+var_70], rbx
0x18002e60b  test    edi, edi
0x18002e60d  js      short loc_18002E624
0x18002e60f  mov     rax, [rcx]
0x18002e612  lea     rdx, [rbp+57h+var_70]
0x18002e616  mov     rax, [rax+0E0h]
0x18002e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e622  mov     edi, eax
0x18002e624  movups  xmm0, xmmword ptr cs:aMapi; "mapi://{"
0x18002e62b  movups  xmmword ptr [rbp+57h+String2], xmm0
0x18002e62f  movzx   eax, word ptr cs:aMapi+10h; ""
0x18002e636  mov     [rbp+57h+var_30], ax
0x18002e63a  mov     eax, dword ptr cs:asc_1800387A4; "}/"
0x18002e640  mov     dword ptr [rbp+57h+var_48], eax
0x18002e643  movzx   eax, word ptr cs:asc_1800387A4+4; ""
0x18002e64a  mov     word ptr [rbp+57h+var_48+4], ax
0x18002e64e  mov     [rbp+57h+lpString2], rbx
0x18002e652  test    edi, edi
0x18002e654  js      short loc_18002E661
0x18002e656  lea     rdx, [rbp+57h+lpString2]; unsigned __int16 **
0x18002e65a  call    ?_GetSIDString@CSrchAdminSSO@@AEAAJPEAPEAG@Z; CSrchAdminSSO::_GetSIDString(ushort * *)
0x18002e65f  mov     edi, eax
0x18002e661  mov     [rbp+57h+var_60], rbx
0x18002e665  mov     r14d, 1
0x18002e66b  test    edi, edi
0x18002e66d  js      short loc_18002E691
0x18002e66f  mov     rcx, [rbp+57h+var_70]
0x18002e673  mov     rax, [rcx]
0x18002e676  lea     rdx, [rbp+57h+var_60]
0x18002e67a  mov     rax, [rax+30h]
0x18002e67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e683  mov     edi, eax
0x18002e685  test    eax, eax
0x18002e687  js      short loc_18002E691
0x18002e689  cmp     [rbp+57h+var_60], rbx
0x18002e68d  cmovz   edi, r14d
0x18002e691  mov     [rbp+57h+var_68], rbx
0x18002e695  test    edi, edi
0x18002e697  jnz     loc_18002E84E
0x18002e69d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002e6a1  mov     rcx, [rbp+57h+var_60]
0x18002e6a5  mov     rax, [rcx]
0x18002e6a8  xor     r9d, r9d
0x18002e6ab  lea     r8, [rbp+57h+var_68]
0x18002e6af  mov     edx, r14d
0x18002e6b2  mov     rax, [rax+18h]
0x18002e6b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6bb  mov     edi, eax
0x18002e6bd  test    eax, eax
0x18002e6bf  jnz     loc_18002E84E
0x18002e6c5  mov     [rbp+57h+lpString1], rbx
0x18002e6c9  mov     rcx, [rbp+57h+var_68]
0x18002e6cd  mov     rax, [rcx]
0x18002e6d0  lea     rdx, [rbp+57h+lpString1]
0x18002e6d4  mov     rax, [rax+30h]
0x18002e6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e6dd  mov     edi, eax
0x18002e6df  test    eax, eax
0x18002e6e1  js      loc_18002E83D
0x18002e6e7  lea     rax, [rbp+57h+String2]
0x18002e6eb  mov     r9, rsi
0x18002e6ee  inc     r9; cchCount1
0x18002e6f1  cmp     [rax+r9*2], bx
0x18002e6f6  jnz     short loc_18002E6EE
0x18002e6f8  lea     rcx, [rbp+57h+var_48]
0x18002e6fc  mov     rax, rsi
0x18002e6ff  inc     rax
0x18002e702  cmp     [rcx+rax*2], bx
0x18002e706  jnz     short loc_18002E6FF
0x18002e708  mov     rdx, [rbp+57h+lpString2]
0x18002e70c  mov     rcx, rsi
0x18002e70f  inc     rcx
0x18002e712  cmp     [rdx+rcx*2], bx
0x18002e716  jnz     short loc_18002E70F
0x18002e718  lea     rdx, [r9+rax]
0x18002e71c  add     rdx, rcx
0x18002e71f  mov     rcx, [rbp+57h+lpString1]
0x18002e723  mov     rax, rsi
0x18002e726  inc     rax
0x18002e729  cmp     [rcx+rax*2], bx
0x18002e72d  jnz     short loc_18002E726
0x18002e72f  cmp     rax, rdx
0x18002e732  jnz     loc_18002E837
0x18002e738  mov     [rsp+0B0h+cchCount2], esi; cchCount2
0x18002e73c  lea     rax, [rbp+57h+String2]
0x18002e740  mov     [rsp+0B0h+ppv], rax; lpString2
0x18002e745  mov     r8, rcx; lpString1
0x18002e748  mov     edx, r14d; dwCmpFlags
0x18002e74b  mov     ecx, 7Fh; Locale
0x18002e750  call    cs:__imp_CompareStringW
0x18002e756  cmp     eax, 2
0x18002e759  jnz     loc_18002E833
0x18002e75f  mov     rdx, [rbp+57h+lpString2]
0x18002e763  mov     r9, rsi
0x18002e766  inc     r9; cchCount1
0x18002e769  cmp     [rdx+r9*2], bx
0x18002e76e  jnz     short loc_18002E766
0x18002e770  lea     rax, [rbp+57h+String2]
0x18002e774  mov     rcx, rsi
0x18002e777  inc     rcx
0x18002e77a  cmp     [rax+rcx*2], bx
0x18002e77e  jnz     short loc_18002E777
0x18002e780  mov     rax, [rbp+57h+lpString1]
0x18002e784  lea     r8, [rax+rcx*2]; lpString1
0x18002e788  mov     [rsp+0B0h+cchCount2], esi; cchCount2
0x18002e78c  mov     [rsp+0B0h+ppv], rdx; lpString2
0x18002e791  mov     edx, r14d; dwCmpFlags
0x18002e794  mov     ecx, 7Fh; Locale
0x18002e799  call    cs:__imp_CompareStringW
0x18002e79f  cmp     eax, 2
0x18002e7a2  jnz     loc_18002E833
0x18002e7a8  lea     rax, [rbp+57h+var_48]
0x18002e7ac  mov     r9, rsi
0x18002e7af  inc     r9; cchCount1
0x18002e7b2  cmp     [rax+r9*2], bx
0x18002e7b7  jnz     short loc_18002E7AF
0x18002e7b9  lea     rax, [rbp+57h+String2]
0x18002e7bd  mov     rcx, rsi
0x18002e7c0  inc     rcx
0x18002e7c3  cmp     [rax+rcx*2], bx
0x18002e7c7  jnz     short loc_18002E7C0
0x18002e7c9  mov     rdx, [rbp+57h+lpString2]
0x18002e7cd  mov     rax, rsi
0x18002e7d0  inc     rax
0x18002e7d3  cmp     [rdx+rax*2], bx
0x18002e7d7  jnz     short loc_18002E7D0
0x18002e7d9  add     rcx, rax
0x18002e7dc  mov     rax, [rbp+57h+lpString1]
0x18002e7e0  lea     r8, [rax+rcx*2]; lpString1
0x18002e7e4  mov     [rsp+0B0h+cchCount2], esi; cchCount2
0x18002e7e8  lea     rax, [rbp+57h+var_48]
0x18002e7ec  mov     [rsp+0B0h+ppv], rax; lpString2
0x18002e7f1  mov     edx, r14d; dwCmpFlags
0x18002e7f4  mov     ecx, 7Fh; Locale
0x18002e7f9  call    cs:__imp_CompareStringW
0x18002e7ff  cmp     eax, 2
0x18002e802  jnz     short loc_18002E833
0x18002e804  mov     rcx, [rbp+57h+var_70]
0x18002e808  mov     rax, [rcx]
0x18002e80b  mov     rdx, [rbp+57h+lpString1]
0x18002e80f  mov     rax, [rax+28h]
0x18002e813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e818  mov     edi, eax
0x18002e81a  test    eax, eax
0x18002e81c  js      short loc_18002E833
0x18002e81e  mov     rcx, [rbp+57h+var_70]
0x18002e822  mov     rax, [rcx]
0x18002e825  mov     rax, [rax+80h]
0x18002e82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e831  mov     edi, eax
0x18002e833  mov     rcx, [rbp+57h+lpString1]; pv
0x18002e837  call    cs:__imp_CoTaskMemFree
0x18002e83d  lea     rcx, [rbp+57h+var_68]
0x18002e841  call    ?Release@?$CComPtrBase@UISearchRoot@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISearchRoot>::Release(void)
0x18002e846  test    edi, edi
0x18002e848  jz      loc_18002E6A1
0x18002e84e  mov     rcx, [rbp+57h+lpString2]; hMem
0x18002e852  call    cs:__imp_LocalFree
0x18002e858  nop
0x18002e859  cmp     edi, r14d
0x18002e85c  cmovnz  ebx, edi
0x18002e85f  lea     rcx, [rbp+57h+var_68]
0x18002e863  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e868  nop
0x18002e869  lea     rcx, [rbp+57h+var_60]
0x18002e86d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e872  nop
0x18002e873  lea     rcx, [rbp+57h+var_70]
0x18002e877  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e87c  nop
0x18002e87d  lea     rcx, [rbp+57h+var_58]
0x18002e881  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e886  nop
0x18002e887  lea     rcx, [rbp+57h+var_50]
0x18002e88b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002e890  mov     eax, ebx
0x18002e892  mov     rcx, [rbp+57h+var_28]
0x18002e896  xor     rcx, rsp; StackCookie
0x18002e899  call    __security_check_cookie
0x18002e89e  add     rsp, 90h
0x18002e8a5  pop     r14
0x18002e8a7  pop     rdi
0x18002e8a8  pop     rsi
0x18002e8a9  pop     rbx
0x18002e8aa  pop     rbp
0x18002e8ab  retn
```
