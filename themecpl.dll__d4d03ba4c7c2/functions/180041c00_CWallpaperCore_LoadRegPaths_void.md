# CWallpaperCore::_LoadRegPaths(void)

- ea: `0x180041c00`
- end: `0x180041df2`
- name: `?_LoadRegPaths@CWallpaperCore@@AEAAJXZ`
- size: `498`
- prototype: `__int64 __fastcall(CWallpaperCore *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b8e8`

## callees

- `0x18003fed4`
- `0x180041c00`
- `0x18004e89c`
- `0x180054e70`
- `0x18005501c`
- `0x180057010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180041cc1`
- `SHELL32!SHCreateShellItemArrayFromIDLists` at `0x180041cc1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041cfc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180041cfc`

## pseudocode

```c
__int64 __fastcall CWallpaperCore::_LoadRegPaths(struct _DPA **this)
{
  HDPA v2; // rax
  int ImageFileExtensionFilterCondition; // ebx
  int i; // esi
  struct _DPA *v6; // rcx
  int v7; // eax
  _QWORD *Ptr; // r15
  __int64 v9; // rcx
  LPCITEMIDLIST *v10; // rdx
  __int64 v11; // rax
  struct ICondition *v12; // r14
  GUID v13; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF
  IShellItemArray *ppsiItemArray; // [rsp+88h] [rbp+48h] BYREF
  struct ICondition *v16; // [rsp+90h] [rbp+50h] BYREF

  if ( this[12] || (v2 = DPA_Create(1), (this[12] = v2) != 0) )
  {
    ImageFileExtensionFilterCondition = CWallpaperCore::_EnumeratePathsFromKey(
                                          (CWallpaperCore *)this,
                                          HKEY_CURRENT_USER);
    if ( ImageFileExtensionFilterCondition >= 0 )
    {
      ImageFileExtensionFilterCondition = CWallpaperCore::_EnumeratePathsFromKey(
                                            (CWallpaperCore *)this,
                                            HKEY_LOCAL_MACHINE);
      if ( ImageFileExtensionFilterCondition >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          v6 = this[12];
          v7 = v6 ? *(_DWORD *)v6 : 0;
          if ( i >= v7 || ImageFileExtensionFilterCondition < 0 )
            break;
          Ptr = DPA_GetPtr(v6, i);
          Ptr[134] = 0;
          ppsiItemArray = 0;
          v9 = Ptr[133];
          v10 = *(LPCITEMIDLIST **)(v9 + 8);
          if ( v9 )
            LODWORD(v9) = *(_DWORD *)v9;
          ImageFileExtensionFilterCondition = SHCreateShellItemArrayFromIDLists(v9, v10, &ppsiItemArray);
          if ( ImageFileExtensionFilterCondition >= 0 )
          {
            ppv = 0;
            ImageFileExtensionFilterCondition = CoCreateInstance(
                                                  &CLSID_SearchFolderItemFactory,
                                                  0,
                                                  1u,
                                                  &GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2,
                                                  &ppv);
            if ( ImageFileExtensionFilterCondition >= 0 )
            {
              ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, IShellItemArray *))(*(_QWORD *)ppv + 88LL))(
                                                    ppv,
                                                    ppsiItemArray);
              if ( ImageFileExtensionFilterCondition >= 0 )
              {
                v11 = *(_QWORD *)ppv;
                v13 = FOLDERTYPEID_Pictures;
                ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, GUID *))(v11 + 32))(ppv, &v13);
                if ( ImageFileExtensionFilterCondition >= 0 )
                {
                  v16 = 0;
                  ImageFileExtensionFilterCondition = GetImageFileExtensionFilterCondition(&v16);
                  if ( ImageFileExtensionFilterCondition >= 0 )
                  {
                    v12 = v16;
                    ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, struct ICondition *))(*(_QWORD *)ppv + 96LL))(
                                                          ppv,
                                                          v16);
                    if ( ImageFileExtensionFilterCondition >= 0 )
                    {
                      ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 24LL))(
                                                            ppv,
                                                            (__int64)Ptr + 540);
                      if ( ImageFileExtensionFilterCondition >= 0 )
                        ImageFileExtensionFilterCondition = (*(__int64 (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 112LL))(
                                                              ppv,
                                                              Ptr + 134);
                    }
                    ((void (__fastcall *)(struct ICondition *))v12->lpVtbl->Release)(v12);
                  }
                }
              }
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            ((void (__fastcall *)(IShellItemArray *))ppsiItemArray->lpVtbl->Release)(ppsiItemArray);
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return (unsigned int)ImageFileExtensionFilterCondition;
}

```

## disassembly

```asm
0x180041c00  push    rbp
0x180041c02  push    rbx
0x180041c03  push    rsi
0x180041c04  push    rdi
0x180041c05  push    r12
0x180041c07  push    r14
0x180041c09  push    r15
0x180041c0b  mov     rbp, rsp
0x180041c0e  sub     rsp, 40h
0x180041c12  cmp     qword ptr [rcx+60h], 0
0x180041c17  mov     rdi, rcx
0x180041c1a  jnz     short loc_180041C46
0x180041c1c  mov     ecx, 1; cItemGrow
0x180041c21  call    DPA_Create
0x180041c26  mov     [rdi+60h], rax
0x180041c2a  test    rax, rax
0x180041c2d  jnz     short loc_180041C46
0x180041c2f  mov     ebx, 8007000Eh
0x180041c34  mov     eax, ebx
0x180041c36  add     rsp, 40h
0x180041c3a  pop     r15
0x180041c3c  pop     r14
0x180041c3e  pop     r12
0x180041c40  pop     rdi
0x180041c41  pop     rsi
0x180041c42  pop     rbx
0x180041c43  pop     rbp
0x180041c44  retn
0x180041c46  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x180041c4d  mov     rcx, rdi; this
0x180041c50  call    ?_EnumeratePathsFromKey@CWallpaperCore@@AEAAJPEAUHKEY__@@@Z; CWallpaperCore::_EnumeratePathsFromKey(HKEY__ *)
0x180041c55  mov     ebx, eax
0x180041c57  test    eax, eax
0x180041c59  js      short loc_180041C34
0x180041c5b  mov     rdx, 0FFFFFFFF80000002h; HKEY
0x180041c62  mov     rcx, rdi; this
0x180041c65  call    ?_EnumeratePathsFromKey@CWallpaperCore@@AEAAJPEAUHKEY__@@@Z; CWallpaperCore::_EnumeratePathsFromKey(HKEY__ *)
0x180041c6a  mov     ebx, eax
0x180041c6c  test    eax, eax
0x180041c6e  js      short loc_180041C34
0x180041c70  xor     esi, esi
0x180041c72  mov     rcx, [rdi+60h]; hdpa
0x180041c76  test    rcx, rcx
0x180041c79  jz      short loc_180041C7F
0x180041c7b  mov     eax, [rcx]
0x180041c7d  jmp     short loc_180041C81
0x180041c7f  xor     eax, eax
0x180041c81  cmp     esi, eax
0x180041c83  jge     short loc_180041C34
0x180041c85  test    ebx, ebx
0x180041c87  js      short loc_180041C34
0x180041c89  movsxd  rdx, esi; i
0x180041c8c  call    DPA_GetPtr
0x180041c91  mov     r15, rax
0x180041c94  lea     r12, [rax+430h]
0x180041c9b  mov     qword ptr [r12], 0
0x180041ca3  mov     [rbp+ppsiItemArray], 0
0x180041cab  mov     rcx, [rax+428h]
0x180041cb2  mov     rdx, [rcx+8]; rgpidl
0x180041cb6  test    rcx, rcx
0x180041cb9  jz      short loc_180041CBD
0x180041cbb  mov     ecx, [rcx]; cidl
0x180041cbd  lea     r8, [rbp+ppsiItemArray]; ppsiItemArray
0x180041cc1  call    cs:__imp_SHCreateShellItemArrayFromIDLists
0x180041cc8  nop     dword ptr [rax+rax+00h]
0x180041ccd  mov     ebx, eax
0x180041ccf  test    eax, eax
0x180041cd1  js      loc_180041DEB
0x180041cd7  xor     edx, edx; pUnkOuter
0x180041cd9  mov     [rbp+arg_0], 0
0x180041ce1  lea     rax, [rbp+arg_0]
0x180041ce5  lea     r9, _GUID_a0ffbc28_5482_4366_be27_3e81e78e06c2; riid
0x180041cec  mov     [rsp+40h+ppv], rax; ppv
0x180041cf1  lea     rcx, CLSID_SearchFolderItemFactory; rclsid
0x180041cf8  lea     r8d, [rdx+1]; dwClsContext
0x180041cfc  call    cs:__imp_CoCreateInstance
0x180041d03  nop     dword ptr [rax+rax+00h]
0x180041d08  mov     ebx, eax
0x180041d0a  test    eax, eax
0x180041d0c  js      loc_180041DDB
0x180041d12  mov     rcx, [rbp+arg_0]
0x180041d16  mov     rdx, [rbp+ppsiItemArray]
0x180041d1a  mov     rax, [rcx]
0x180041d1d  mov     rax, [rax+58h]
0x180041d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d26  mov     ebx, eax
0x180041d28  test    eax, eax
0x180041d2a  js      loc_180041DCB
0x180041d30  mov     rcx, [rbp+arg_0]
0x180041d34  lea     rdx, [rbp+var_10]
0x180041d38  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_Pictures.Data1
0x180041d3f  mov     rax, [rcx]
0x180041d42  movdqu  [rbp+var_10], xmm0
0x180041d47  mov     rax, [rax+20h]
0x180041d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d50  mov     ebx, eax
0x180041d52  test    eax, eax
0x180041d54  js      short loc_180041DCB
0x180041d56  lea     rcx, [rbp+arg_10]; struct ICondition **
0x180041d5a  mov     [rbp+arg_10], 0
0x180041d62  call    ?GetImageFileExtensionFilterCondition@@YAJPEAPEAUICondition@@@Z; GetImageFileExtensionFilterCondition(ICondition * *)
0x180041d67  mov     ebx, eax
0x180041d69  test    eax, eax
0x180041d6b  js      short loc_180041DCB
0x180041d6d  mov     rcx, [rbp+arg_0]
0x180041d71  mov     r14, [rbp+arg_10]
0x180041d75  mov     rdx, r14
0x180041d78  mov     rax, [rcx]
0x180041d7b  mov     rax, [rax+60h]
0x180041d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041d84  mov     ebx, eax
0x180041d86  test    eax, eax
0x180041d88  js      short loc_180041DBC
0x180041d8a  mov     rcx, [rbp+arg_0]
0x180041d8e  lea     rdx, [r15+21Ch]
0x180041d95  mov     rax, [rcx]
0x180041d98  mov     rax, [rax+18h]
0x180041d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041da1  mov     ebx, eax
0x180041da3  test    eax, eax
0x180041da5  js      short loc_180041DBC
0x180041da7  mov     rcx, [rbp+arg_0]
0x180041dab  mov     rdx, r12
0x180041dae  mov     rax, [rcx]
0x180041db1  mov     rax, [rax+70h]
0x180041db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dba  mov     ebx, eax
0x180041dbc  mov     rax, [r14]
0x180041dbf  mov     rcx, r14
0x180041dc2  mov     rax, [rax+10h]
0x180041dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041dcb  mov     rcx, [rbp+arg_0]
0x180041dcf  mov     rax, [rcx]
0x180041dd2  mov     rax, [rax+10h]
0x180041dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041ddb  mov     rcx, [rbp+ppsiItemArray]
0x180041ddf  mov     rax, [rcx]
0x180041de2  mov     rax, [rax+10h]
0x180041de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041deb  inc     esi
0x180041ded  jmp     loc_180041C72
```
