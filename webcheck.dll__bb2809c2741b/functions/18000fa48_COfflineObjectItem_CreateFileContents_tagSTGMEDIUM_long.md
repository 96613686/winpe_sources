# COfflineObjectItem::_CreateFileContents(tagSTGMEDIUM *,long)

- ea: `0x18000fa48`
- end: `0x18000fbb0`
- name: `?_CreateFileContents@COfflineObjectItem@@QEAAJPEAUtagSTGMEDIUM@@J@Z`
- size: `360`
- prototype: `__int64 __fastcall(COfflineObjectItem *__hidden this, struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ee80`

## callees

- `0x18000fa48`
- `0x18002a010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18000fa86`
- `ole32!CreateStreamOnHGlobal` at `0x18000fa86`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000facb`
- `SHELL32!__imp_SHCoCreateInstance` at `0x18000facb`

## pseudocode

```c
__int64 __fastcall COfflineObjectItem::_CreateFileContents(COfflineObjectItem *this, struct tagSTGMEDIUM *a2, int a3)
{
  int v3; // edi
  union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *p_hBitmap; // r14
  HRESULT StreamOnHGlobal; // ebx
  __int64 v7; // rdx
  __int64 v9; // [rsp+30h] [rbp-38h] BYREF
  __int64 v10; // [rsp+38h] [rbp-30h]
  void *ppv; // [rsp+88h] [rbp+20h] BYREF

  v3 = a3;
  if ( a3 == -1 )
  {
    if ( *((_DWORD *)this + 14) != 1 )
      return 2147500037LL;
    v3 = 0;
  }
  p_hBitmap = (union tagSTGMEDIUM::$7B772CC839E5463FC51219F893F364BB *)&a2->hBitmap;
  a2->tymed = 4;
  a2->pUnkForRelease = 0;
  StreamOnHGlobal = CreateStreamOnHGlobal(0, 1, &a2->pstm);
  if ( StreamOnHGlobal >= 0 )
  {
    v10 = 0;
    ppv = 0;
    StreamOnHGlobal = SHCoCreateInstance(0, &CLSID_InternetShortcut, 0, &IID_IUniformResourceLocatorW, &ppv);
    if ( StreamOnHGlobal >= 0 )
    {
      v7 = *(_QWORD *)(*((_QWORD *)this + 8) + 8LL * v3);
      StreamOnHGlobal = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppv + 24LL))(
                          ppv,
                          *(_QWORD *)(v7 + 200) + 8LL + v7,
                          1);
      if ( StreamOnHGlobal >= 0 )
      {
        v9 = 0;
        StreamOnHGlobal = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(ppv, &IID_IPersistStream, &v9);
        if ( StreamOnHGlobal >= 0 )
        {
          StreamOnHGlobal = (*(__int64 (__fastcall **)(__int64, HBITMAP, __int64))(*(_QWORD *)v9 + 48LL))(
                              v9,
                              p_hBitmap->hBitmap,
                              1);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
        }
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    (*(void (__fastcall **)(HBITMAP, __int64, _QWORD, _QWORD))(*(_QWORD *)p_hBitmap->hBitmap + 40LL))(
      p_hBitmap->hBitmap,
      v10,
      0,
      0);
  }
  return (unsigned int)StreamOnHGlobal;
}

```

## disassembly

```asm
0x18000fa48  push    rbx
0x18000fa4a  push    rsi
0x18000fa4b  push    rdi
0x18000fa4c  push    r14
0x18000fa4e  sub     rsp, 48h
0x18000fa52  mov     edi, r8d
0x18000fa55  mov     rsi, rcx
0x18000fa58  cmp     r8d, 0FFFFFFFFh
0x18000fa5c  jnz     short loc_18000FA6A
0x18000fa5e  cmp     dword ptr [rcx+38h], 1
0x18000fa62  jnz     loc_18000FBA9
0x18000fa68  xor     edi, edi
0x18000fa6a  lea     r14, [rdx+8]
0x18000fa6e  mov     dword ptr [rdx], 4
0x18000fa74  mov     qword ptr [rdx+10h], 0
0x18000fa7c  mov     r8, r14; ppstm
0x18000fa7f  mov     edx, 1; fDeleteOnRelease
0x18000fa84  xor     ecx, ecx; hGlobal
0x18000fa86  call    cs:__imp_CreateStreamOnHGlobal
0x18000fa8c  mov     ebx, eax
0x18000fa8e  test    eax, eax
0x18000fa90  js      loc_18000FB9D
0x18000fa96  lea     rax, [rsp+68h+arg_18]
0x18000fa9e  mov     [rsp+68h+var_30], 0
0x18000faa7  lea     r9, IID_IUniformResourceLocatorW; riid
0x18000faae  mov     [rsp+68h+ppv], rax; ppv
0x18000fab3  xor     r8d, r8d; pUnkOuter
0x18000fab6  mov     [rsp+68h+arg_18], 0
0x18000fac2  lea     rdx, CLSID_InternetShortcut; pclsid
0x18000fac9  xor     ecx, ecx; pszCLSID
0x18000facb  call    cs:__imp_SHCoCreateInstance
0x18000fad1  mov     ebx, eax
0x18000fad3  test    eax, eax
0x18000fad5  js      loc_18000FB83
0x18000fadb  mov     rax, [rsi+40h]
0x18000fadf  movsxd  rcx, edi
0x18000fae2  mov     rdx, [rax+rcx*8]
0x18000fae6  mov     rcx, [rsp+68h+arg_18]
0x18000faee  mov     rax, [rdx+0C8h]
0x18000faf5  mov     r8, [rcx]
0x18000faf8  add     rax, 8
0x18000fafc  add     rdx, rax
0x18000faff  mov     rax, [r8+18h]
0x18000fb03  mov     r8d, 1
0x18000fb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb0e  mov     ebx, eax
0x18000fb10  test    eax, eax
0x18000fb12  js      short loc_18000FB6F
0x18000fb14  mov     rcx, [rsp+68h+arg_18]
0x18000fb1c  lea     r8, [rsp+68h+var_38]
0x18000fb21  mov     [rsp+68h+var_38], 0
0x18000fb2a  lea     rdx, IID_IPersistStream
0x18000fb31  mov     rax, [rcx]
0x18000fb34  mov     rax, [rax]
0x18000fb37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb3c  mov     ebx, eax
0x18000fb3e  test    eax, eax
0x18000fb40  js      short loc_18000FB6F
0x18000fb42  mov     rcx, [rsp+68h+var_38]
0x18000fb47  mov     r8d, 1
0x18000fb4d  mov     rdx, [r14]
0x18000fb50  mov     rax, [rcx]
0x18000fb53  mov     rax, [rax+30h]
0x18000fb57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb5c  mov     rcx, [rsp+68h+var_38]
0x18000fb61  mov     ebx, eax
0x18000fb63  mov     rax, [rcx]
0x18000fb66  mov     rax, [rax+10h]
0x18000fb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb6f  mov     rcx, [rsp+68h+arg_18]
0x18000fb77  mov     rax, [rcx]
0x18000fb7a  mov     rax, [rax+10h]
0x18000fb7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb83  mov     rcx, [r14]
0x18000fb86  xor     r9d, r9d
0x18000fb89  mov     rdx, [rsp+68h+var_30]
0x18000fb8e  xor     r8d, r8d
0x18000fb91  mov     rax, [rcx]
0x18000fb94  mov     rax, [rax+28h]
0x18000fb98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb9d  mov     eax, ebx
0x18000fb9f  add     rsp, 48h
0x18000fba3  pop     r14
0x18000fba5  pop     rdi
0x18000fba6  pop     rsi
0x18000fba7  pop     rbx
0x18000fba8  retn
0x18000fba9  mov     eax, 80004005h
0x18000fbae  jmp     short loc_18000FB9F
```
