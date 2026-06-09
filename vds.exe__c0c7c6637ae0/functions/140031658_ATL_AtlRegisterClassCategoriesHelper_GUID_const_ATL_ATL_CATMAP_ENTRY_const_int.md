# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x140031658`
- end: `0x1400319a4`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `844`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140022020`
- `0x140034d84`
- `0x1400360f4`
- `0x14003618c`

## callees

- `0x1400064c0`
- `0x140012c48`
- `0x14002f8c8`
- `0x140031410`
- `0x140031658`
- `0x140031c24`
- `0x140032e6c`
- `0x140033f10`
- `0x140052e80`
- `0x140056010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140031790`
- `msvcrt!wcscpy_s` at `0x14003188b`
- `msvcrt!wcscpy_s` at `0x140031790`
- `msvcrt!wcscpy_s` at `0x14003188b`
- `msvcrt!wcscat_s` at `0x1400317aa`
- `msvcrt!wcscat_s` at `0x1400317c4`
- `msvcrt!wcscat_s` at `0x1400318a6`
- `msvcrt!wcscat_s` at `0x1400318c1`
- `msvcrt!wcscat_s` at `0x1400317aa`
- `msvcrt!wcscat_s` at `0x1400317c4`
- `msvcrt!wcscat_s` at `0x1400318a6`
- `msvcrt!wcscat_s` at `0x1400318c1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140031774`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x140031774`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400316ed`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400316ed`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003184f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140031920`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x14003184f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x140031920`

## string_xrefs

- `0x14003177e`: `CLSID\`
- `0x14003187d`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rdi
  __int64 v7; // rax
  int v8; // eax
  unsigned int v9; // ebx
  errno_t v10; // eax
  errno_t v11; // eax
  errno_t v12; // eax
  HKEY v13; // rdi
  LSTATUS v14; // ebx
  errno_t v15; // eax
  errno_t v16; // eax
  errno_t v17; // eax
  LSTATUS v18; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD *v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  v4 = a2;
  ppv = 0;
  v24 = 0;
  if ( !a2 || (unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL) )
  {
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    return 0;
  }
  else
  {
    if ( CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      while ( *(_DWORD *)v4 )
      {
        v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
        v7 = *(_QWORD *)ppv;
        if ( a3 )
        {
          if ( *(_DWORD *)v4 == 1 )
            v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 40))(ppv, rguid, 1, &v24);
          else
            v8 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 56))(ppv, rguid, 1, &v24);
          v9 = v8;
          if ( v8 < 0 )
            goto LABEL_27;
        }
        else if ( *(_DWORD *)v4 == 1 )
        {
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 48))(ppv, rguid, 1, &v24);
        }
        else
        {
          (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v7 + 64))(ppv, rguid, 1, &v24);
        }
        v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
      }
      if ( !a3 )
      {
        StringFromGUID2(rguid, sz, 64);
        v23 = 0;
        v10 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
        ATL::AtlCrtErrorCheck(v10);
        v11 = wcscat_s(Destination, 0x80u, sz);
        ATL::AtlCrtErrorCheck(v11);
        v12 = wcscat_s(Destination, 0x80u, L"\\Required Categories");
        ATL::AtlCrtErrorCheck(v12);
        v13 = HKEY_CLASSES_ROOT;
        v22[0] = 0xFFFFFFFF80000000uLL;
        v22[1] = 0;
        v22[2] = 0;
        memset(hKey, 0, sizeof(hKey));
        cSubKeys = 0;
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, Destination, 0x20019u) )
        {
          v14 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          if ( !v14 && !cSubKeys )
          {
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
            v13 = (HKEY)v22[0];
          }
        }
        v15 = wcscpy_s(Destination, 0x80u, L"CLSID\\");
        ATL::AtlCrtErrorCheck(v15);
        v16 = wcscat_s(Destination, 0x80u, sz);
        ATL::AtlCrtErrorCheck(v16);
        v17 = wcscat_s(Destination, 0x80u, L"\\Implemented Categories");
        ATL::AtlCrtErrorCheck(v17);
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v13, Destination, 0x20019u) )
        {
          v18 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          if ( !v18 && !cSubKeys )
            ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, Destination);
        }
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        ATL::CRegKey::Close((ATL::CRegKey *)v22);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
      }
    }
    v9 = 0;
LABEL_27:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
    return v9;
  }
}

```

## disassembly

```asm
0x140031658  mov     [rsp-8+arg_10], rbx
0x14003165d  mov     [rsp-8+arg_18], rsi
0x140031662  push    rbp
0x140031663  push    rdi
0x140031664  push    r12
0x140031666  push    r14
0x140031668  push    r15
0x14003166a  lea     rbp, [rsp-150h]
0x140031672  sub     rsp, 250h
0x140031679  mov     rax, cs:__security_cookie
0x140031680  xor     rax, rsp
0x140031683  mov     [rbp+170h+var_30], rax
0x14003168a  mov     r14d, r8d
0x14003168d  mov     rdi, rdx
0x140031690  mov     rsi, rcx
0x140031693  xor     r15d, r15d
0x140031696  mov     [rsp+270h+var_208], r15
0x14003169b  xorps   xmm0, xmm0
0x14003169e  movups  [rbp+170h+var_1C8], xmm0
0x1400316a2  test    rdx, rdx
0x1400316a5  jnz     short loc_1400316B8
0x1400316a7  lea     rcx, [rsp+270h+var_208]
0x1400316ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1400316b1  xor     eax, eax
0x1400316b3  jmp     loc_140031979
0x1400316b8  lea     rdx, GUID_NULL; struct _GUID *
0x1400316bf  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x1400316c4  test    eax, eax
0x1400316c6  jz      short loc_1400316CA
0x1400316c8  jmp     short loc_1400316A7
0x1400316ca  lea     rax, [rsp+270h+var_208]
0x1400316cf  mov     [rsp+270h+ppv], rax; ppv
0x1400316d4  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x1400316db  mov     r12d, 1
0x1400316e1  mov     r8d, r12d; dwClsContext
0x1400316e4  xor     edx, edx; pUnkOuter
0x1400316e6  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x1400316ed  call    cs:__imp_CoCreateInstance
0x1400316f3  test    eax, eax
0x1400316f5  jns     short loc_1400316FC
0x1400316f7  jmp     loc_14003196A
0x1400316fc  cmp     [rdi], r15d
0x1400316ff  jz      short loc_14003175D
0x140031701  mov     rax, [rdi+8]
0x140031705  movups  xmm0, xmmword ptr [rax]
0x140031708  movdqu  [rbp+170h+var_1C8], xmm0
0x14003170d  mov     rcx, [rsp+270h+var_208]
0x140031712  lea     r9, [rbp+170h+var_1C8]
0x140031716  mov     r8d, r12d
0x140031719  mov     rdx, rsi
0x14003171c  mov     rax, [rcx]
0x14003171f  test    r14d, r14d
0x140031722  jz      short loc_140031743
0x140031724  cmp     [rdi], r12d
0x140031727  jnz     short loc_14003172F
0x140031729  mov     rax, [rax+28h]
0x14003172d  jmp     short loc_140031733
0x14003172f  mov     rax, [rax+38h]
0x140031733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031738  mov     ebx, eax
0x14003173a  test    eax, eax
0x14003173c  jns     short loc_140031757
0x14003173e  jmp     loc_14003196D
0x140031743  cmp     [rdi], r12d
0x140031746  jnz     short loc_14003174E
0x140031748  mov     rax, [rax+30h]
0x14003174c  jmp     short loc_140031752
0x14003174e  mov     rax, [rax+40h]
0x140031752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140031757  add     rdi, 10h
0x14003175b  jmp     short loc_1400316FC
0x14003175d  test    r14d, r14d
0x140031760  jnz     loc_14003196A
0x140031766  lea     r8d, [r14+40h]; cchMax
0x14003176a  lea     rdx, [rbp+170h+sz]; lpsz
0x140031771  mov     rcx, rsi; rguid
0x140031774  call    cs:__imp_StringFromGUID2
0x14003177a  mov     [rbp+170h+var_1D0], r15
0x14003177e  lea     r8, aClsid; "CLSID\\"
0x140031785  mov     esi, 80h
0x14003178a  mov     edx, esi; SizeInWords
0x14003178c  lea     rcx, [rbp+170h+Destination]; Destination
0x140031790  call    cs:__imp_wcscpy_s
0x140031796  mov     ecx, eax; int
0x140031798  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14003179d  lea     r8, [rbp+170h+sz]; Source
0x1400317a4  mov     edx, esi; SizeInWords
0x1400317a6  lea     rcx, [rbp+170h+Destination]; Destination
0x1400317aa  call    cs:__imp_wcscat_s
0x1400317b0  mov     ecx, eax; int
0x1400317b2  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400317b7  lea     r8, aRequiredCatego; "\\Required Categories"
0x1400317be  mov     edx, esi; SizeInWords
0x1400317c0  lea     rcx, [rbp+170h+Destination]; Destination
0x1400317c4  call    cs:__imp_wcscat_s
0x1400317ca  mov     ecx, eax; int
0x1400317cc  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400317d1  mov     rdi, 0FFFFFFFF80000000h
0x1400317d8  mov     [rbp+170h+var_1E8], rdi
0x1400317dc  mov     [rbp+170h+var_1E0], r15
0x1400317e0  mov     [rbp+170h+var_1D8], r15
0x1400317e4  mov     [rsp+270h+hKey], r15
0x1400317e9  mov     [rsp+270h+var_1F8], r15
0x1400317ee  mov     [rbp+170h+var_1F0], r15
0x1400317f2  mov     [rsp+270h+cSubKeys], r15d
0x1400317f7  mov     r14d, 20019h
0x1400317fd  mov     r9d, r14d; unsigned int
0x140031800  lea     r8, [rbp+170h+Destination]; lpSubKey
0x140031804  mov     rdx, rdi; hKey
0x140031807  lea     rcx, [rsp+270h+hKey]; this
0x14003180c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x140031811  test    eax, eax
0x140031813  jnz     short loc_14003187D
0x140031815  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14003181a  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14003181f  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x140031824  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x140031829  mov     [rsp+270h+lpcValues], r15; lpcValues
0x14003182e  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140031833  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140031838  lea     rax, [rsp+270h+cSubKeys]
0x14003183d  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x140031842  xor     r9d, r9d; lpReserved
0x140031845  xor     r8d, r8d; lpcchClass
0x140031848  xor     edx, edx; lpClass
0x14003184a  mov     rcx, [rsp+270h+hKey]; hKey
0x14003184f  call    cs:__imp_RegQueryInfoKeyW
0x140031855  mov     ebx, eax
0x140031857  lea     rcx, [rsp+270h+hKey]; this
0x14003185c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140031861  test    ebx, ebx
0x140031863  jnz     short loc_14003187D
0x140031865  cmp     [rsp+270h+cSubKeys], r15d
0x14003186a  jnz     short loc_14003187D
0x14003186c  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x140031870  lea     rcx, [rbp+170h+var_1E8]; this
0x140031874  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140031879  mov     rdi, [rbp+170h+var_1E8]
0x14003187d  lea     r8, aClsid; "CLSID\\"
0x140031884  mov     rdx, rsi; SizeInWords
0x140031887  lea     rcx, [rbp+170h+Destination]; Destination
0x14003188b  call    cs:__imp_wcscpy_s
0x140031891  mov     ecx, eax; int
0x140031893  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140031898  lea     r8, [rbp+170h+sz]; Source
0x14003189f  mov     rdx, rsi; SizeInWords
0x1400318a2  lea     rcx, [rbp+170h+Destination]; Destination
0x1400318a6  call    cs:__imp_wcscat_s
0x1400318ac  mov     ecx, eax; int
0x1400318ae  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400318b3  lea     r8, aImplementedCat; "\\Implemented Categories"
0x1400318ba  mov     rdx, rsi; SizeInWords
0x1400318bd  lea     rcx, [rbp+170h+Destination]; Destination
0x1400318c1  call    cs:__imp_wcscat_s
0x1400318c7  mov     ecx, eax; int
0x1400318c9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1400318ce  mov     r9d, r14d; unsigned int
0x1400318d1  lea     r8, [rbp+170h+Destination]; lpSubKey
0x1400318d5  mov     rdx, rdi; hKey
0x1400318d8  lea     rcx, [rsp+270h+hKey]; this
0x1400318dd  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1400318e2  test    eax, eax
0x1400318e4  jnz     short loc_14003194B
0x1400318e6  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1400318eb  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1400318f0  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1400318f5  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1400318fa  mov     [rsp+270h+lpcValues], r15; lpcValues
0x1400318ff  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x140031904  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x140031909  lea     rax, [rsp+270h+cSubKeys]
0x14003190e  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x140031913  xor     r9d, r9d; lpReserved
0x140031916  xor     r8d, r8d; lpcchClass
0x140031919  xor     edx, edx; lpClass
0x14003191b  mov     rcx, [rsp+270h+hKey]; hKey
0x140031920  call    cs:__imp_RegQueryInfoKeyW
0x140031926  mov     ebx, eax
0x140031928  lea     rcx, [rsp+270h+hKey]; this
0x14003192d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140031932  test    ebx, ebx
0x140031934  jnz     short loc_14003194B
0x140031936  cmp     [rsp+270h+cSubKeys], r15d
0x14003193b  jnz     short loc_14003194B
0x14003193d  lea     rdx, [rbp+170h+Destination]; unsigned __int16 *
0x140031941  lea     rcx, [rbp+170h+var_1E8]; this
0x140031945  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x14003194a  nop
0x14003194b  lea     rcx, [rsp+270h+hKey]; this
0x140031950  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x140031955  nop
0x140031956  lea     rcx, [rbp+170h+var_1E8]; this
0x14003195a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14003195f  nop
0x140031960  lea     rcx, [rbp+170h+var_1D0]
0x140031964  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140031969  nop
0x14003196a  mov     ebx, r15d
0x14003196d  lea     rcx, [rsp+270h+var_208]
0x140031972  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x140031977  mov     eax, ebx
0x140031979  mov     rcx, [rbp+170h+var_30]
0x140031980  xor     rcx, rsp; StackCookie
0x140031983  call    __security_check_cookie
0x140031988  lea     r11, [rsp+270h+var_20]
0x140031990  mov     rbx, [r11+40h]
0x140031994  mov     rsi, [r11+48h]
0x140031998  mov     rsp, r11
0x14003199b  pop     r15
0x14003199d  pop     r14
0x14003199f  pop     r12
0x1400319a1  pop     rdi
0x1400319a2  pop     rbp
0x1400319a3  retn
```
