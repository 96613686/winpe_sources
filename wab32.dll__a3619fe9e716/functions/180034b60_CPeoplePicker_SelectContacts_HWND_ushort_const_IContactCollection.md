# CPeoplePicker::SelectContacts(HWND__ *,ushort const *,IContactCollection * *)

- ea: `0x180034b60`
- end: `0x180034f44`
- name: `?SelectContacts@CPeoplePicker@@SAJPEAUHWND__@@PEBGPEAPEAUIContactCollection@@@Z`
- size: `996`
- prototype: `__int64 __fastcall(HWND, const unsigned __int16 *, struct IContactCollection **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180058d50`

## callees

- `0x18000161c`
- `0x180002818`
- `0x180024c58`
- `0x180034b60`
- `0x180063f0c`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180034f01`
- `KERNEL32!LocalFree` at `0x180034f01`
- `ole32!CoCreateInstance` at `0x180034ca4`
- `ole32!CoCreateInstance` at `0x180034ca4`
- `USER32!LoadStringW` at `0x180034c25`
- `USER32!LoadStringW` at `0x180034c46`
- `USER32!LoadStringW` at `0x180034c60`
- `USER32!LoadStringW` at `0x180034c25`
- `USER32!LoadStringW` at `0x180034c46`
- `USER32!LoadStringW` at `0x180034c60`

## pseudocode

```c
__int64 __fastcall CPeoplePicker::SelectContacts(HWND a1, const unsigned __int16 *a2, struct IContactCollection **a3)
{
  _DWORD *v6; // rdi
  HRESULT v7; // ebx
  __int64 v8; // rdx
  _DWORD *v9; // rax
  __int64 v10; // rcx
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v14; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v16; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  struct IKnownFolder *v18[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v19[200]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v20[200]; // [rsp+200h] [rbp+100h] BYREF
  WCHAR Buffer[264]; // [rsp+390h] [rbp+290h] BYREF

  ppv = 0;
  v16 = 0;
  v18[0] = 0;
  v17 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(v20, 0, sizeof(v20));
  memset_0(v19, 0, sizeof(v19));
  v6 = 0;
  hMem = 0;
  v12 = 0;
  v14 = 0;
  LoadStringW(hinstMapiX, 0x3Eu, Buffer, 260);
  LoadStringW(hinstMapiX, 0xFBFu, v20, 200);
  LoadStringW(hinstMapiX, 0xFC0u, v19, 200);
  v7 = FilterSpecFromMultiSz(Buffer, (struct _COMDLG_FILTERSPEC **)&hMem, &v12);
  if ( v7 >= 0 )
  {
    v7 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 1u, &GUID_d57c7288_d4ad_4768_be02_9d969532d960, &ppv);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 136LL))(ppv, a2);
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 144LL))(ppv, v19);
        if ( v7 >= 0 )
        {
          v7 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 152LL))(ppv, v20);
          if ( v7 >= 0 )
          {
            v7 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, HLOCAL))(*(_QWORD *)ppv + 32LL))(ppv, v12, hMem);
            if ( v7 >= 0 )
            {
              if ( (int)GetKnownFolderFromFolderID(&FOLDERID_Contacts, v18) >= 0
                && ((int (__fastcall *)(struct IKnownFolder *, _QWORD, GUID *, __int64 *))v18[0]->lpVtbl->GetShellItem)(
                     v18[0],
                     0,
                     &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                     &v17) >= 0 )
              {
                (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 96LL))(ppv, v17);
              }
              v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1);
              if ( v7 >= 0 )
              {
                v7 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *))(*(_QWORD *)ppv + 80LL))(ppv, &v14);
                if ( v7 >= 0 )
                {
                  v8 = v14;
                  LODWORD(v8) = v14 | 0x200;
                  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 72LL))(ppv, v8);
                  if ( v7 >= 0 )
                  {
                    v7 = (*(__int64 (__fastcall **)(LPVOID, HWND))(*(_QWORD *)ppv + 24LL))(ppv, a1);
                    if ( v7 >= 0 )
                    {
                      v7 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 216LL))(ppv, &v16);
                      if ( v7 >= 0 )
                      {
                        v9 = operator new(0x28u);
                        v6 = v9;
                        if ( v9 )
                        {
                          v10 = v16;
                          *(_QWORD *)v9 = &CPeoplePicker::CFileCollection::`vftable';
                          v9[2] = 1;
                          *((_QWORD *)v9 + 2) = v10;
                          *((_QWORD *)v9 + 3) = 0;
                          v9[8] = -1;
                          v9[9] = 0;
                          v12 = 0;
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
                          if ( (*(int (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)v6 + 2) + 56LL))(
                                 *((_QWORD *)v6 + 2),
                                 &v12) >= 0 )
                            v6[9] = v12;
                          v7 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IContactCollection **))v6)(
                                 v6,
                                 &GUID_b6afa338_d779_11d9_8bde_f66bad1e3f3a,
                                 a3);
                          if ( v7 >= 0 )
                            v7 = 0;
                        }
                        else
                        {
                          v7 = -2147024882;
                          v6 = 0;
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v16);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v17);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(v18);
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v6 + 16LL))(v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180034b60  mov     [rsp-8+arg_18], rbx
0x180034b65  push    rbp
0x180034b66  push    rdi
0x180034b67  push    r12
0x180034b69  push    r14
0x180034b6b  push    r15
0x180034b6d  lea     rbp, [rsp-4B0h]
0x180034b75  sub     rsp, 5B0h
0x180034b7c  mov     rax, cs:__security_cookie
0x180034b83  xor     rax, rsp
0x180034b86  mov     [rbp+4D0h+var_30], rax
0x180034b8d  mov     r12, r8
0x180034b90  mov     [rsp+5D0h+var_598], 0
0x180034b99  mov     r14, rdx
0x180034b9c  mov     [rsp+5D0h+var_580], 0
0x180034ba5  mov     r15, rcx
0x180034ba8  mov     [rsp+5D0h+var_570], 0
0x180034bb1  xor     edx, edx; Val
0x180034bb3  mov     [rsp+5D0h+var_578], 0
0x180034bbc  mov     r8d, 208h; Size
0x180034bc2  lea     rcx, [rbp+4D0h+Buffer]; void *
0x180034bc9  call    memset_0
0x180034bce  mov     ebx, 190h
0x180034bd3  lea     rcx, [rbp+4D0h+var_3D0]; void *
0x180034bda  mov     r8d, ebx; Size
0x180034bdd  xor     edx, edx; Val
0x180034bdf  call    memset_0
0x180034be4  mov     r8d, ebx; Size
0x180034be7  lea     rcx, [rsp+5D0h+var_560]; void *
0x180034bec  xor     edx, edx; Val
0x180034bee  call    memset_0
0x180034bf3  mov     rcx, cs:hinstMapiX; hInstance
0x180034bfa  lea     r8, [rbp+4D0h+Buffer]; lpBuffer
0x180034c01  xor     edi, edi
0x180034c03  mov     [rsp+5D0h+hMem], 0
0x180034c0c  mov     r9d, 104h; cchBufferMax
0x180034c12  mov     [rsp+5D0h+var_5A0], 0
0x180034c1a  mov     [rsp+5D0h+var_590], 0
0x180034c22  lea     edx, [rdi+3Eh]; uID
0x180034c25  call    cs:__imp_LoadStringW
0x180034c2b  mov     rcx, cs:hinstMapiX; hInstance
0x180034c32  lea     r8, [rbp+4D0h+var_3D0]; lpBuffer
0x180034c39  mov     ebx, 0C8h
0x180034c3e  mov     edx, 0FBFh; uID
0x180034c43  mov     r9d, ebx; cchBufferMax
0x180034c46  call    cs:__imp_LoadStringW
0x180034c4c  mov     rcx, cs:hinstMapiX; hInstance
0x180034c53  lea     r8, [rsp+5D0h+var_560]; lpBuffer
0x180034c58  mov     r9d, ebx; cchBufferMax
0x180034c5b  mov     edx, 0FC0h; uID
0x180034c60  call    cs:__imp_LoadStringW
0x180034c66  lea     r8, [rsp+5D0h+var_5A0]; unsigned int *
0x180034c6b  lea     rdx, [rsp+5D0h+hMem]; struct _COMDLG_FILTERSPEC **
0x180034c70  lea     rcx, [rbp+4D0h+Buffer]; unsigned __int16 *
0x180034c77  call    ?FilterSpecFromMultiSz@@YAJPEBGPEAPEAU_COMDLG_FILTERSPEC@@PEAI@Z; FilterSpecFromMultiSz(ushort const *,_COMDLG_FILTERSPEC * *,uint *)
0x180034c7c  mov     ebx, eax
0x180034c7e  test    eax, eax
0x180034c80  js      loc_180034ED6
0x180034c86  lea     rax, [rsp+5D0h+var_598]
0x180034c8b  xor     edx, edx; pUnkOuter
0x180034c8d  lea     r9, _GUID_d57c7288_d4ad_4768_be02_9d969532d960; riid
0x180034c94  mov     [rsp+5D0h+ppv], rax; ppv
0x180034c99  lea     r8d, [rdi+1]; dwClsContext
0x180034c9d  lea     rcx, CLSID_FileOpenDialog; rclsid
0x180034ca4  call    cs:__imp_CoCreateInstance
0x180034caa  mov     ebx, eax
0x180034cac  test    eax, eax
0x180034cae  js      loc_180034ED6
0x180034cb4  mov     rcx, [rsp+5D0h+var_598]
0x180034cb9  mov     rdx, r14
0x180034cbc  mov     rax, [rcx]
0x180034cbf  mov     rax, [rax+88h]
0x180034cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ccb  mov     ebx, eax
0x180034ccd  test    eax, eax
0x180034ccf  js      loc_180034ED6
0x180034cd5  mov     rcx, [rsp+5D0h+var_598]
0x180034cda  lea     rdx, [rsp+5D0h+var_560]
0x180034cdf  mov     rax, [rcx]
0x180034ce2  mov     rax, [rax+90h]
0x180034ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034cee  mov     ebx, eax
0x180034cf0  test    eax, eax
0x180034cf2  js      loc_180034ED6
0x180034cf8  mov     rcx, [rsp+5D0h+var_598]
0x180034cfd  lea     rdx, [rbp+4D0h+var_3D0]
0x180034d04  mov     rax, [rcx]
0x180034d07  mov     rax, [rax+98h]
0x180034d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d13  mov     ebx, eax
0x180034d15  test    eax, eax
0x180034d17  js      loc_180034ED6
0x180034d1d  mov     rcx, [rsp+5D0h+var_598]
0x180034d22  mov     r8, [rsp+5D0h+hMem]
0x180034d27  mov     edx, [rsp+5D0h+var_5A0]
0x180034d2b  mov     rax, [rcx]
0x180034d2e  mov     rax, [rax+20h]
0x180034d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d37  mov     ebx, eax
0x180034d39  test    eax, eax
0x180034d3b  js      loc_180034ED6
0x180034d41  lea     rdx, [rsp+5D0h+var_570]; struct IKnownFolder **
0x180034d46  lea     rcx, FOLDERID_Contacts; struct _GUID *
0x180034d4d  call    ?GetKnownFolderFromFolderID@@YAJAEBU_GUID@@PEAPEAUIKnownFolder@@@Z; GetKnownFolderFromFolderID(_GUID const &,IKnownFolder * *)
0x180034d52  test    eax, eax
0x180034d54  js      short loc_180034D8F
0x180034d56  mov     rcx, [rsp+5D0h+var_570]
0x180034d5b  lea     r9, [rsp+5D0h+var_578]
0x180034d60  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180034d67  xor     edx, edx
0x180034d69  mov     rax, [rcx]
0x180034d6c  mov     rax, [rax+28h]
0x180034d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d75  test    eax, eax
0x180034d77  js      short loc_180034D8F
0x180034d79  mov     rcx, [rsp+5D0h+var_598]
0x180034d7e  mov     rdx, [rsp+5D0h+var_578]
0x180034d83  mov     rax, [rcx]
0x180034d86  mov     rax, [rax+60h]
0x180034d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034d8f  mov     rcx, [rsp+5D0h+var_598]
0x180034d94  mov     r14d, 1
0x180034d9a  mov     edx, r14d
0x180034d9d  mov     rax, [rcx]
0x180034da0  mov     rax, [rax+28h]
0x180034da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034da9  mov     ebx, eax
0x180034dab  test    eax, eax
0x180034dad  js      loc_180034ED6
0x180034db3  mov     rcx, [rsp+5D0h+var_598]
0x180034db8  lea     rdx, [rsp+5D0h+var_590]
0x180034dbd  mov     rax, [rcx]
0x180034dc0  mov     rax, [rax+50h]
0x180034dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dc9  mov     ebx, eax
0x180034dcb  test    eax, eax
0x180034dcd  js      loc_180034ED6
0x180034dd3  mov     rcx, [rsp+5D0h+var_598]
0x180034dd8  mov     edx, [rsp+5D0h+var_590]
0x180034ddc  bts     edx, 9
0x180034de0  mov     rax, [rcx]
0x180034de3  mov     rax, [rax+48h]
0x180034de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dec  mov     ebx, eax
0x180034dee  test    eax, eax
0x180034df0  js      loc_180034ED6
0x180034df6  mov     rcx, [rsp+5D0h+var_598]
0x180034dfb  mov     rdx, r15
0x180034dfe  mov     rax, [rcx]
0x180034e01  mov     rax, [rax+18h]
0x180034e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e0a  mov     ebx, eax
0x180034e0c  test    eax, eax
0x180034e0e  js      loc_180034ED6
0x180034e14  mov     rcx, [rsp+5D0h+var_598]
0x180034e19  lea     rdx, [rsp+5D0h+var_580]
0x180034e1e  mov     rax, [rcx]
0x180034e21  mov     rax, [rax+0D8h]
0x180034e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e2d  mov     ebx, eax
0x180034e2f  test    eax, eax
0x180034e31  js      loc_180034ED6
0x180034e37  lea     ecx, [r14+27h]; Size
0x180034e3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034e40  mov     rdi, rax
0x180034e43  test    rax, rax
0x180034e46  jz      loc_180034ECF
0x180034e4c  mov     rcx, [rsp+5D0h+var_580]
0x180034e51  lea     rax, ??_7CFileCollection@CPeoplePicker@@6B@; const CPeoplePicker::CFileCollection::`vftable'
0x180034e58  mov     [rdi], rax
0x180034e5b  mov     [rdi+8], r14d
0x180034e5f  mov     [rdi+10h], rcx
0x180034e63  mov     qword ptr [rdi+18h], 0
0x180034e6b  mov     dword ptr [rdi+20h], 0FFFFFFFFh
0x180034e72  mov     dword ptr [rdi+24h], 0
0x180034e79  mov     [rsp+5D0h+var_5A0], 0
0x180034e81  mov     rax, [rcx]
0x180034e84  mov     rax, [rax+8]
0x180034e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034e8d  mov     rcx, [rdi+10h]
0x180034e91  lea     rdx, [rsp+5D0h+var_5A0]
0x180034e96  mov     rax, [rcx]
0x180034e99  mov     rax, [rax+38h]
0x180034e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ea2  test    eax, eax
0x180034ea4  js      short loc_180034EAD
0x180034ea6  mov     eax, [rsp+5D0h+var_5A0]
0x180034eaa  mov     [rdi+24h], eax
0x180034ead  mov     rax, [rdi]
0x180034eb0  lea     rdx, _GUID_b6afa338_d779_11d9_8bde_f66bad1e3f3a
0x180034eb7  mov     r8, r12
0x180034eba  mov     rcx, rdi
0x180034ebd  mov     rax, [rax]
0x180034ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ec5  mov     ebx, eax
0x180034ec7  test    eax, eax
0x180034ec9  js      short loc_180034ED6
0x180034ecb  xor     ebx, ebx
0x180034ecd  jmp     short loc_180034ED6
0x180034ecf  mov     ebx, 8007000Eh
0x180034ed4  xor     edi, edi
0x180034ed6  lea     rcx, [rsp+5D0h+var_580]
0x180034edb  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034ee0  lea     rcx, [rsp+5D0h+var_578]
0x180034ee5  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034eea  lea     rcx, [rsp+5D0h+var_570]
0x180034eef  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180034ef4  cmp     [rsp+5D0h+hMem], 0
0x180034efa  jz      short loc_180034F07
0x180034efc  mov     rcx, [rsp+5D0h+hMem]; hMem
0x180034f01  call    cs:__imp_LocalFree
0x180034f07  test    rdi, rdi
0x180034f0a  jz      short loc_180034F1B
0x180034f0c  mov     rax, [rdi]
0x180034f0f  mov     rcx, rdi
0x180034f12  mov     rax, [rax+10h]
0x180034f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034f1b  mov     eax, ebx
0x180034f1d  mov     rcx, [rbp+4D0h+var_30]
0x180034f24  xor     rcx, rsp; StackCookie
0x180034f27  call    __security_check_cookie
0x180034f2c  mov     rbx, [rsp+5D0h+arg_18]
0x180034f34  add     rsp, 5B0h
0x180034f3b  pop     r15
0x180034f3d  pop     r14
0x180034f3f  pop     r12
0x180034f41  pop     rdi
0x180034f42  pop     rbp
0x180034f43  retn
```
