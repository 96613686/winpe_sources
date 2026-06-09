# SelectPicture(HWND__ *,ushort *,ulong)

- ea: `0x180051c4c`
- end: `0x180052016`
- name: `?SelectPicture@@YAJPEAUHWND__@@PEAGK@Z`
- size: `970`
- prototype: `int(HWND, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180053424`

## callees

- `0x180002818`
- `0x1800045e4`
- `0x180024c58`
- `0x180051c4c`
- `0x180063f0c`
- `0x180091eaa`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180051fdb`
- `KERNEL32!LocalFree` at `0x180051fdb`
- `ole32!CoTaskMemFree` at `0x180051feb`
- `ole32!CoTaskMemFree` at `0x180051feb`
- `ole32!CoCreateInstance` at `0x180051db7`
- `ole32!CoCreateInstance` at `0x180051db7`
- `USER32!LoadStringW` at `0x180051d18`
- `USER32!LoadStringW` at `0x180051d35`
- `USER32!LoadStringW` at `0x180051d54`
- `USER32!LoadStringW` at `0x180051d73`
- `USER32!LoadStringW` at `0x180051d18`
- `USER32!LoadStringW` at `0x180051d35`
- `USER32!LoadStringW` at `0x180051d54`
- `USER32!LoadStringW` at `0x180051d73`

## pseudocode

```c
__int64 __fastcall SelectPicture(HWND a1, unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  int KnownFolderFromFolderID; // eax
  bool v6; // sf
  LPVOID v7; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v10; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v11; // [rsp+40h] [rbp-C0h] BYREF
  int v12; // [rsp+44h] [rbp-BCh] BYREF
  struct IKnownFolder *v13; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v16[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v17[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR v18[264]; // [rsp+480h] [rbp+380h] BYREF
  WCHAR Buffer[520]; // [rsp+690h] [rbp+590h] BYREF

  ppv = 0;
  v10 = 0;
  v13 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(v16, 0, 0x208u);
  memset_0(v17, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  pv = 0;
  hMem = 0;
  v11 = 0;
  v12 = 0;
  LoadStringW(hinstMapiX, 0xB3Bu, Buffer, 520);
  LoadStringW(hinstMapiX, 0xB3Cu, v16, 260);
  LoadStringW(hinstMapiX, 0xB3Du, v17, 260);
  LoadStringW(hinstMapiX, 0xB3Eu, v18, 260);
  v4 = FilterSpecFromMultiSz(Buffer, (struct _COMDLG_FILTERSPEC **)&hMem, &v11);
  if ( v4 >= 0 )
  {
    v4 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 1u, &GUID_d57c7288_d4ad_4768_be02_9d969532d960, &ppv);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 136LL))(ppv, v16);
      if ( v4 >= 0 )
      {
        v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 152LL))(ppv, v17);
        if ( v4 >= 0 )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, WCHAR *))(*(_QWORD *)ppv + 144LL))(ppv, v18);
          if ( v4 >= 0 )
          {
            v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, HLOCAL))(*(_QWORD *)ppv + 32LL))(ppv, v11, hMem);
            if ( v4 >= 0 )
            {
              KnownFolderFromFolderID = GetKnownFolderFromFolderID(&FOLDERID_Pictures, &v13);
              v6 = KnownFolderFromFolderID < 0;
              if ( KnownFolderFromFolderID )
              {
                OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
                v6 = (int)GetKnownFolderFromFolderID(&FOLDERID_Documents, &v13) < 0;
              }
              if ( !v6 )
              {
                if ( ((int (__fastcall *)(struct IKnownFolder *, _QWORD, GUID *, __int64 *))v13->lpVtbl->GetShellItem)(
                       v13,
                       0,
                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                       &v10) >= 0 )
                  (*(void (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 88LL))(ppv, v10);
                OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
              }
              v4 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1);
              if ( v4 >= 0 )
              {
                v4 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 80LL))(ppv, &v12);
                if ( v4 >= 0 )
                {
                  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 72LL))(ppv, v12 | 0x40u);
                  if ( v4 >= 0 )
                  {
                    v4 = (*(__int64 (__fastcall **)(LPVOID, HWND))(*(_QWORD *)ppv + 24LL))(ppv, a1);
                    if ( v4 >= 0 )
                    {
                      v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 160LL))(ppv, &v10);
                      if ( v4 >= 0 )
                      {
                        v4 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v10 + 40LL))(
                               v10,
                               2147844096LL,
                               &pv);
                        if ( v4 >= 0 )
                          v4 = StringCchCopyW(a2, 0x104u, (const unsigned __int16 *)pv);
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
  v7 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v10);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v13);
  if ( hMem )
    LocalFree(hMem);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180051c4c  mov     [rsp-8+arg_10], rbx
0x180051c51  push    rbp
0x180051c52  push    rsi
0x180051c53  push    r14
0x180051c55  lea     rbp, [rsp-9B0h]
0x180051c5d  sub     rsp, 0AB0h
0x180051c64  mov     rax, cs:__security_cookie
0x180051c6b  xor     rax, rsp
0x180051c6e  mov     [rbp+9C0h+var_20], rax
0x180051c75  mov     r14, rdx
0x180051c78  mov     [rsp+0AC0h+var_A90], 0
0x180051c81  mov     rsi, rcx
0x180051c84  mov     [rsp+0AC0h+var_A88], 0
0x180051c8d  xor     edx, edx; Val
0x180051c8f  mov     [rsp+0AC0h+var_A78], 0
0x180051c98  lea     rcx, [rbp+9C0h+Buffer]; void *
0x180051c9f  mov     r8d, 410h; Size
0x180051ca5  call    memset_0
0x180051caa  mov     ebx, 208h
0x180051caf  lea     rcx, [rsp+0AC0h+var_A60]; void *
0x180051cb4  mov     r8d, ebx; Size
0x180051cb7  xor     edx, edx; Val
0x180051cb9  call    memset_0
0x180051cbe  mov     r8d, ebx; Size
0x180051cc1  lea     rcx, [rbp+9C0h+var_850]; void *
0x180051cc8  xor     edx, edx; Val
0x180051cca  call    memset_0
0x180051ccf  mov     r8d, ebx; Size
0x180051cd2  lea     rcx, [rbp+9C0h+var_640]; void *
0x180051cd9  xor     edx, edx; Val
0x180051cdb  call    memset_0
0x180051ce0  mov     rcx, cs:hinstMapiX; hInstance
0x180051ce7  lea     r8, [rbp+9C0h+Buffer]; lpBuffer
0x180051cee  mov     r9d, ebx; cchBufferMax
0x180051cf1  mov     [rsp+0AC0h+pv], 0
0x180051cfa  mov     edx, 0B3Bh; uID
0x180051cff  mov     [rsp+0AC0h+hMem], 0
0x180051d08  mov     [rsp+0AC0h+var_A80], 0
0x180051d10  mov     [rsp+0AC0h+var_A7C], 0
0x180051d18  call    cs:__imp_LoadStringW
0x180051d1e  mov     rcx, cs:hinstMapiX; hInstance
0x180051d25  lea     r8, [rsp+0AC0h+var_A60]; lpBuffer
0x180051d2a  mov     r9d, 104h; cchBufferMax
0x180051d30  mov     edx, 0B3Ch; uID
0x180051d35  call    cs:__imp_LoadStringW
0x180051d3b  mov     rcx, cs:hinstMapiX; hInstance
0x180051d42  lea     r8, [rbp+9C0h+var_850]; lpBuffer
0x180051d49  mov     r9d, 104h; cchBufferMax
0x180051d4f  mov     edx, 0B3Dh; uID
0x180051d54  call    cs:__imp_LoadStringW
0x180051d5a  mov     rcx, cs:hinstMapiX; hInstance
0x180051d61  lea     r8, [rbp+9C0h+var_640]; lpBuffer
0x180051d68  mov     r9d, 104h; cchBufferMax
0x180051d6e  mov     edx, 0B3Eh; uID
0x180051d73  call    cs:__imp_LoadStringW
0x180051d79  lea     r8, [rsp+0AC0h+var_A80]; unsigned int *
0x180051d7e  lea     rdx, [rsp+0AC0h+hMem]; struct _COMDLG_FILTERSPEC **
0x180051d83  lea     rcx, [rbp+9C0h+Buffer]; unsigned __int16 *
0x180051d8a  call    ?FilterSpecFromMultiSz@@YAJPEBGPEAPEAU_COMDLG_FILTERSPEC@@PEAI@Z; FilterSpecFromMultiSz(ushort const *,_COMDLG_FILTERSPEC * *,uint *)
0x180051d8f  mov     ebx, eax
0x180051d91  test    eax, eax
0x180051d93  js      loc_180051F9B
0x180051d99  xor     edx, edx; pUnkOuter
0x180051d9b  lea     rax, [rsp+0AC0h+var_A90]
0x180051da0  lea     r9, _GUID_d57c7288_d4ad_4768_be02_9d969532d960; riid
0x180051da7  mov     [rsp+0AC0h+ppv], rax; ppv
0x180051dac  lea     rcx, CLSID_FileOpenDialog; rclsid
0x180051db3  lea     r8d, [rdx+1]; dwClsContext
0x180051db7  call    cs:__imp_CoCreateInstance
0x180051dbd  mov     ebx, eax
0x180051dbf  test    eax, eax
0x180051dc1  js      loc_180051F9B
0x180051dc7  mov     rcx, [rsp+0AC0h+var_A90]
0x180051dcc  lea     rdx, [rsp+0AC0h+var_A60]
0x180051dd1  mov     rax, [rcx]
0x180051dd4  mov     rax, [rax+88h]
0x180051ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051de0  mov     ebx, eax
0x180051de2  test    eax, eax
0x180051de4  js      loc_180051F9B
0x180051dea  mov     rcx, [rsp+0AC0h+var_A90]
0x180051def  lea     rdx, [rbp+9C0h+var_850]
0x180051df6  mov     rax, [rcx]
0x180051df9  mov     rax, [rax+98h]
0x180051e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e05  mov     ebx, eax
0x180051e07  test    eax, eax
0x180051e09  js      loc_180051F9B
0x180051e0f  mov     rcx, [rsp+0AC0h+var_A90]
0x180051e14  lea     rdx, [rbp+9C0h+var_640]
0x180051e1b  mov     rax, [rcx]
0x180051e1e  mov     rax, [rax+90h]
0x180051e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e2a  mov     ebx, eax
0x180051e2c  test    eax, eax
0x180051e2e  js      loc_180051F9B
0x180051e34  mov     rcx, [rsp+0AC0h+var_A90]
0x180051e39  mov     r8, [rsp+0AC0h+hMem]
0x180051e3e  mov     edx, [rsp+0AC0h+var_A80]
0x180051e42  mov     rax, [rcx]
0x180051e45  mov     rax, [rax+20h]
0x180051e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e4e  mov     ebx, eax
0x180051e50  test    eax, eax
0x180051e52  js      loc_180051F9B
0x180051e58  lea     rdx, [rsp+0AC0h+var_A78]; struct IKnownFolder **
0x180051e5d  lea     rcx, FOLDERID_Pictures; struct _GUID *
0x180051e64  call    ?GetKnownFolderFromFolderID@@YAJAEBU_GUID@@PEAPEAUIKnownFolder@@@Z; GetKnownFolderFromFolderID(_GUID const &,IKnownFolder * *)
0x180051e69  test    eax, eax
0x180051e6b  jz      short loc_180051E8A
0x180051e6d  lea     rcx, [rsp+0AC0h+var_A78]
0x180051e72  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180051e77  lea     rdx, [rsp+0AC0h+var_A78]; struct IKnownFolder **
0x180051e7c  lea     rcx, FOLDERID_Documents; struct _GUID *
0x180051e83  call    ?GetKnownFolderFromFolderID@@YAJAEBU_GUID@@PEAPEAUIKnownFolder@@@Z; GetKnownFolderFromFolderID(_GUID const &,IKnownFolder * *)
0x180051e88  test    eax, eax
0x180051e8a  js      short loc_180051ECF
0x180051e8c  mov     rcx, [rsp+0AC0h+var_A78]
0x180051e91  lea     r9, [rsp+0AC0h+var_A88]
0x180051e96  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x180051e9d  xor     edx, edx
0x180051e9f  mov     rax, [rcx]
0x180051ea2  mov     rax, [rax+28h]
0x180051ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eab  test    eax, eax
0x180051ead  js      short loc_180051EC5
0x180051eaf  mov     rcx, [rsp+0AC0h+var_A90]
0x180051eb4  mov     rdx, [rsp+0AC0h+var_A88]
0x180051eb9  mov     rax, [rcx]
0x180051ebc  mov     rax, [rax+58h]
0x180051ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ec5  lea     rcx, [rsp+0AC0h+var_A88]
0x180051eca  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180051ecf  mov     rcx, [rsp+0AC0h+var_A90]
0x180051ed4  mov     edx, 1
0x180051ed9  mov     rax, [rcx]
0x180051edc  mov     rax, [rax+28h]
0x180051ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051ee5  mov     ebx, eax
0x180051ee7  test    eax, eax
0x180051ee9  js      loc_180051F9B
0x180051eef  mov     rcx, [rsp+0AC0h+var_A90]
0x180051ef4  lea     rdx, [rsp+0AC0h+var_A7C]
0x180051ef9  mov     rax, [rcx]
0x180051efc  mov     rax, [rax+50h]
0x180051f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f05  mov     ebx, eax
0x180051f07  test    eax, eax
0x180051f09  js      loc_180051F9B
0x180051f0f  mov     rcx, [rsp+0AC0h+var_A90]
0x180051f14  mov     edx, [rsp+0AC0h+var_A7C]
0x180051f18  or      edx, 40h
0x180051f1b  mov     rax, [rcx]
0x180051f1e  mov     rax, [rax+48h]
0x180051f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f27  mov     ebx, eax
0x180051f29  test    eax, eax
0x180051f2b  js      short loc_180051F9B
0x180051f2d  mov     rcx, [rsp+0AC0h+var_A90]
0x180051f32  mov     rdx, rsi
0x180051f35  mov     rax, [rcx]
0x180051f38  mov     rax, [rax+18h]
0x180051f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f41  mov     ebx, eax
0x180051f43  test    eax, eax
0x180051f45  js      short loc_180051F9B
0x180051f47  mov     rcx, [rsp+0AC0h+var_A90]
0x180051f4c  lea     rdx, [rsp+0AC0h+var_A88]
0x180051f51  mov     rax, [rcx]
0x180051f54  mov     rax, [rax+0A0h]
0x180051f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f60  mov     ebx, eax
0x180051f62  test    eax, eax
0x180051f64  js      short loc_180051F9B
0x180051f66  mov     rcx, [rsp+0AC0h+var_A88]
0x180051f6b  lea     r8, [rsp+0AC0h+pv]
0x180051f70  mov     edx, 80058000h
0x180051f75  mov     rax, [rcx]
0x180051f78  mov     rax, [rax+28h]
0x180051f7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f81  mov     ebx, eax
0x180051f83  test    eax, eax
0x180051f85  js      short loc_180051F9B
0x180051f87  mov     r8, [rsp+0AC0h+pv]; unsigned __int16 *
0x180051f8c  mov     edx, 104h; unsigned __int64
0x180051f91  mov     rcx, r14; unsigned __int16 *
0x180051f94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180051f99  mov     ebx, eax
0x180051f9b  mov     rcx, [rsp+0AC0h+var_A90]
0x180051fa0  test    rcx, rcx
0x180051fa3  jz      short loc_180051FBA
0x180051fa5  mov     [rsp+0AC0h+var_A90], 0
0x180051fae  mov     rax, [rcx]
0x180051fb1  mov     rax, [rax+10h]
0x180051fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051fba  lea     rcx, [rsp+0AC0h+var_A88]
0x180051fbf  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180051fc4  lea     rcx, [rsp+0AC0h+var_A78]
0x180051fc9  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x180051fce  cmp     [rsp+0AC0h+hMem], 0
0x180051fd4  jz      short loc_180051FE1
0x180051fd6  mov     rcx, [rsp+0AC0h+hMem]; hMem
0x180051fdb  call    cs:__imp_LocalFree
0x180051fe1  mov     rcx, [rsp+0AC0h+pv]; pv
0x180051fe6  test    rcx, rcx
0x180051fe9  jz      short loc_180051FF1
0x180051feb  call    cs:__imp_CoTaskMemFree
0x180051ff1  mov     eax, ebx
0x180051ff3  mov     rcx, [rbp+9C0h+var_20]
0x180051ffa  xor     rcx, rsp; StackCookie
0x180051ffd  call    __security_check_cookie
0x180052002  mov     rbx, [rsp+0AC0h+arg_10]
0x18005200a  add     rsp, 0AB0h
0x180052011  pop     r14
0x180052013  pop     rsi
0x180052014  pop     rbp
0x180052015  retn
```
