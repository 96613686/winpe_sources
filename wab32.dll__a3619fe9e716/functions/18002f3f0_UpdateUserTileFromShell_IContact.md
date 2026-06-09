# UpdateUserTileFromShell(IContact *)

- ea: `0x18002f3f0`
- end: `0x18002f583`
- name: `?UpdateUserTileFromShell@@YAJPEAUIContact@@@Z`
- size: `403`
- prototype: `__int64 __fastcall(struct IContact *)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18000eef0`
- `0x18002f0d8`
- `0x18002f1c0`

## callees

- `0x180002818`
- `0x180006f7c`
- `0x180008f74`
- `0x18000eef0`
- `0x180014944`
- `0x18002f3f0`
- `0x18006c0e8`
- `0x180091ef0`
- `0x180093010`

## import_xrefs

- `MSOERT2!OpenFileStreamShareW` at `0x18002f4c2`
- `MSOERT2!OpenFileStreamShareW` at `0x18002f4c2`
- `ole32!CoTaskMemFree` at `0x18002f520`
- `ole32!CoTaskMemFree` at `0x18002f520`
- `ole32!CoCreateInstance` at `0x18002f469`
- `ole32!CoCreateInstance` at `0x18002f469`

## pseudocode

```c
__int64 __fastcall UpdateUserTileFromShell(struct IContact *a1)
{
  HRESULT ImageType; // ebx
  LPVOID v2; // rcx
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-C8h] BYREF
  struct IStream *v6; // [rsp+40h] [rbp-C0h] BYREF
  struct IContact *v7; // [rsp+48h] [rbp-B8h] BYREF
  int v8; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v9[24]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v10[264]; // [rsp+70h] [rbp-90h] BYREF

  v7 = a1;
  STRW::STRW((STRW *)&v8, v10, 0x104u);
  pv = 0;
  v6 = 0;
  ppv = 0;
  ImageType = CoCreateInstance(&CLSID_UserTileStore, 0, 1u, &GUID_fb69bc98_66a0_47ba_8b1d_f79b9e842bbc, &ppv);
  if ( ImageType >= 0 )
  {
    ImageType = (*(__int64 (__fastcall **)(LPVOID, _QWORD, LPVOID *))(*(_QWORD *)ppv + 40LL))(ppv, 0, &pv);
    if ( ImageType >= 0 )
    {
      v6 = 0;
      ImageType = OpenFileStreamShareW(pv, 3, 0x80000000LL, 5, &v6);
      if ( ImageType >= 0 )
      {
        ImageType = GetImageType((const unsigned __int16 *)pv, (struct STRW *)&v8);
        if ( ImageType >= 0 )
        {
          ImageType = SetUserTile(v7, v6, (const struct STRW *)&v8);
          if ( ImageType >= 0 )
          {
            ImageType = TryToSaveContact(&v7, 6u, 0x30u, 0);
            if ( ImageType >= 0 )
              ImageType = 0;
          }
        }
      }
    }
  }
  CoTaskMemFree(pv);
  v2 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v2 + 16LL))(v2);
  }
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v6);
  v8 = 0;
  BUFFER::ReleaseStorage((BUFFER *)v9);
  return (unsigned int)ImageType;
}

```

## disassembly

```asm
0x18002f3f0  mov     [rsp-8+arg_8], rbx
0x18002f3f5  push    rbp
0x18002f3f6  lea     rbp, [rsp-190h]
0x18002f3fe  sub     rsp, 290h
0x18002f405  mov     rax, cs:__security_cookie
0x18002f40c  xor     rax, rsp
0x18002f40f  mov     [rbp+190h+var_10], rax
0x18002f416  mov     [rsp+290h+var_248], rcx
0x18002f41b  lea     rdx, [rsp+290h+var_220]; unsigned __int16 *
0x18002f420  lea     rcx, [rsp+290h+var_240]; this
0x18002f425  mov     r8d, 104h; unsigned int
0x18002f42b  call    ??0STRW@@QEAA@PEAGK@Z; STRW::STRW(ushort *,ulong)
0x18002f430  xor     edx, edx; pUnkOuter
0x18002f432  mov     [rsp+290h+pv], 0
0x18002f43b  lea     rax, [rsp+290h+var_258]
0x18002f440  mov     [rsp+290h+var_250], 0
0x18002f449  lea     r9, _GUID_fb69bc98_66a0_47ba_8b1d_f79b9e842bbc; riid
0x18002f450  mov     [rsp+290h+var_258], 0
0x18002f459  lea     rcx, CLSID_UserTileStore; rclsid
0x18002f460  mov     [rsp+290h+ppv], rax; ppv
0x18002f465  lea     r8d, [rdx+1]; dwClsContext
0x18002f469  call    cs:__imp_CoCreateInstance
0x18002f46f  mov     ebx, eax
0x18002f471  test    eax, eax
0x18002f473  js      loc_18002F51B
0x18002f479  mov     rcx, [rsp+290h+var_258]
0x18002f47e  lea     r8, [rsp+290h+pv]
0x18002f483  xor     edx, edx
0x18002f485  mov     rax, [rcx]
0x18002f488  mov     rax, [rax+28h]
0x18002f48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f491  mov     ebx, eax
0x18002f493  test    eax, eax
0x18002f495  js      loc_18002F51B
0x18002f49b  mov     rcx, [rsp+290h+pv]
0x18002f4a0  lea     rax, [rsp+290h+var_250]
0x18002f4a5  mov     edx, 3
0x18002f4aa  mov     [rsp+290h+var_250], 0
0x18002f4b3  mov     r8d, 80000000h
0x18002f4b9  mov     [rsp+290h+ppv], rax
0x18002f4be  lea     r9d, [rdx+2]
0x18002f4c2  call    cs:__imp_OpenFileStreamShareW
0x18002f4c8  mov     ebx, eax
0x18002f4ca  test    eax, eax
0x18002f4cc  js      short loc_18002F51B
0x18002f4ce  mov     rcx, [rsp+290h+pv]; unsigned __int16 *
0x18002f4d3  lea     rdx, [rsp+290h+var_240]; struct STRW *
0x18002f4d8  call    ?GetImageType@@YAJPEBGPEAVSTRW@@@Z; GetImageType(ushort const *,STRW *)
0x18002f4dd  mov     ebx, eax
0x18002f4df  test    eax, eax
0x18002f4e1  js      short loc_18002F51B
0x18002f4e3  mov     rdx, [rsp+290h+var_250]; struct IStream *
0x18002f4e8  lea     r8, [rsp+290h+var_240]; struct STRW *
0x18002f4ed  mov     rcx, [rsp+290h+var_248]; struct IContact *
0x18002f4f2  call    ?SetUserTile@@YAJPEAUIContact@@PEAUIStream@@PEBVSTRW@@@Z; SetUserTile(IContact *,IStream *,STRW const *)
0x18002f4f7  mov     ebx, eax
0x18002f4f9  test    eax, eax
0x18002f4fb  js      short loc_18002F51B
0x18002f4fd  xor     r9d, r9d; int *
0x18002f500  lea     rcx, [rsp+290h+var_248]; struct IContact **
0x18002f505  lea     edx, [r9+6]; unsigned int
0x18002f509  lea     r8d, [r9+30h]; unsigned int
0x18002f50d  call    ?TryToSaveContact@@YAJPEAPEAUIContact@@KKPEAH@Z; TryToSaveContact(IContact * *,ulong,ulong,int *)
0x18002f512  mov     ebx, eax
0x18002f514  xor     eax, eax
0x18002f516  test    ebx, ebx
0x18002f518  cmovns  ebx, eax
0x18002f51b  mov     rcx, [rsp+290h+pv]; pv
0x18002f520  call    cs:__imp_CoTaskMemFree
0x18002f526  mov     rcx, [rsp+290h+var_258]
0x18002f52b  test    rcx, rcx
0x18002f52e  jz      short loc_18002F545
0x18002f530  mov     [rsp+290h+var_258], 0
0x18002f539  mov     rax, [rcx]
0x18002f53c  mov     rax, [rax+10h]
0x18002f540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f545  lea     rcx, [rsp+290h+var_250]
0x18002f54a  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18002f54f  lea     rcx, [rsp+290h+var_238]; this
0x18002f554  mov     [rsp+290h+var_240], 0
0x18002f55c  call    ?ReleaseStorage@BUFFER@@QEAAXXZ; BUFFER::ReleaseStorage(void)
0x18002f561  mov     eax, ebx
0x18002f563  mov     rcx, [rbp+190h+var_10]
0x18002f56a  xor     rcx, rsp; StackCookie
0x18002f56d  call    __security_check_cookie
0x18002f572  mov     rbx, [rsp+290h+arg_8]
0x18002f57a  add     rsp, 290h
0x18002f581  pop     rbp
0x18002f582  retn
```
