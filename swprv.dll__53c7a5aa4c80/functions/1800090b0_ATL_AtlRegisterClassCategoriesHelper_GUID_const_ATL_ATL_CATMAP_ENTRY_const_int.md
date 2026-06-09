# ATL::AtlRegisterClassCategoriesHelper(_GUID const &,ATL::_ATL_CATMAP_ENTRY const *,int)

- ea: `0x1800090b0`
- end: `0x1800093eb`
- name: `?AtlRegisterClassCategoriesHelper@ATL@@YAJAEBU_GUID@@PEBU_ATL_CATMAP_ENTRY@1@H@Z`
- size: `827`
- prototype: `__int64 __fastcall(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000bed8`
- `0x18000ceec`
- `0x18000d5c0`

## callees

- `0x180001580`
- `0x1800036c4`
- `0x180005764`
- `0x180007f50`
- `0x180008e8c`
- `0x1800090b0`
- `0x1800096c4`
- `0x180009cec`
- `0x18000b618`
- `0x18004b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800091f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000920f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000930c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800091f5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000920f`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x1800092f1`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18000930c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800091db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800092d6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800091db`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800092d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000929a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000936b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000929a`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000936b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009138`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009138`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800091bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800091bf`

## string_xrefs

- `0x1800091d0`: `CLSID\`
- `0x1800092c8`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::AtlRegisterClassCategoriesHelper(GUID *rguid, const struct ATL::_ATL_CATMAP_ENTRY *a2, int a3)
{
  const struct ATL::_ATL_CATMAP_ENTRY *v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned int v8; // edi
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HKEY v12; // rdi
  LSTATUS v13; // ebx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  LSTATUS v17; // ebx
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v22[3]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v23; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v24; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[128]; // [rsp+C0h] [rbp-40h] BYREF
  OLECHAR sz[64]; // [rsp+1C0h] [rbp+C0h] BYREF

  ppv = 0;
  v4 = a2;
  v24 = 0;
  if ( a2
    && !(unsigned int)InlineIsEqualGUID(rguid, &GUID_NULL)
    && CoCreateInstance(&CLSID_StdComponentCategoriesMgr, 0, 1u, &GUID_0002e012_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    while ( *(_DWORD *)v4 )
    {
      v24 = *(_OWORD *)*((_QWORD *)v4 + 1);
      v6 = *(_QWORD *)ppv;
      if ( a3 )
      {
        if ( *(_DWORD *)v4 == 1 )
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 40))(ppv, rguid, 1, &v24);
        else
          v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 56))(ppv, rguid, 1, &v24);
        v8 = v7;
        if ( v7 < 0 )
          goto LABEL_26;
      }
      else if ( *(_DWORD *)v4 == 1 )
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 48))(ppv, rguid, 1, &v24);
      }
      else
      {
        (*(void (__fastcall **)(LPVOID, GUID *, __int64, __int128 *))(v6 + 64))(ppv, rguid, 1, &v24);
      }
      v4 = (const struct ATL::_ATL_CATMAP_ENTRY *)((char *)v4 + 16);
    }
    if ( !a3 )
    {
      StringFromGUID2(rguid, sz, 64);
      v23 = 0;
      v9 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v9);
      v10 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v10);
      v11 = _o_wcscat_s(SubKey, 128, L"\\Required Categories");
      ATL::AtlCrtErrorCheck(v11);
      v12 = HKEY_CLASSES_ROOT;
      v22[1] = 0;
      v22[0] = 0xFFFFFFFF80000000uLL;
      v22[2] = 0;
      memset(hKey, 0, sizeof(hKey));
      cSubKeys = 0;
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, HKEY_CLASSES_ROOT, SubKey, 0x20019u) )
      {
        v13 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v13 && !cSubKeys )
        {
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
          v12 = (HKEY)v22[0];
        }
      }
      v14 = _o_wcscpy_s(SubKey, 128, L"CLSID\\");
      ATL::AtlCrtErrorCheck(v14);
      v15 = _o_wcscat_s(SubKey, 128, sz);
      ATL::AtlCrtErrorCheck(v15);
      v16 = _o_wcscat_s(SubKey, 128, L"\\Implemented Categories");
      ATL::AtlCrtErrorCheck(v16);
      if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)hKey, v12, SubKey, 0x20019u) )
      {
        v17 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
        if ( !v17 && !cSubKeys )
          ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v22, SubKey);
      }
      ATL::CRegKey::Close((ATL::CRegKey *)hKey);
      ATL::CRegKey::Close((ATL::CRegKey *)v22);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v23);
    }
  }
  v8 = 0;
LABEL_26:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&ppv);
  return v8;
}

```

## disassembly

```asm
0x1800090b0  mov     [rsp-8+arg_10], rbx
0x1800090b5  mov     [rsp-8+arg_18], rsi
0x1800090ba  push    rbp
0x1800090bb  push    rdi
0x1800090bc  push    r12
0x1800090be  push    r14
0x1800090c0  push    r15
0x1800090c2  lea     rbp, [rsp-150h]
0x1800090ca  sub     rsp, 250h
0x1800090d1  mov     rax, cs:__security_cookie
0x1800090d8  xor     rax, rsp
0x1800090db  mov     [rbp+170h+var_30], rax
0x1800090e2  xor     r15d, r15d
0x1800090e5  xorps   xmm0, xmm0
0x1800090e8  mov     [rsp+270h+var_208], r15
0x1800090ed  mov     r14d, r8d
0x1800090f0  mov     rbx, rdx
0x1800090f3  mov     rsi, rcx
0x1800090f6  movups  [rbp+170h+var_1C8], xmm0
0x1800090fa  test    rdx, rdx
0x1800090fd  jz      loc_1800093B1
0x180009103  lea     rdx, GUID_NULL; struct _GUID *
0x18000910a  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000910f  test    eax, eax
0x180009111  jnz     loc_1800093B1
0x180009117  lea     rax, [rsp+270h+var_208]
0x18000911c  xor     edx, edx; pUnkOuter
0x18000911e  lea     r12d, [r15+1]
0x180009122  mov     [rsp+270h+ppv], rax; ppv
0x180009127  mov     r8d, r12d; dwClsContext
0x18000912a  lea     r9, _GUID_0002e012_0000_0000_c000_000000000046; riid
0x180009131  lea     rcx, CLSID_StdComponentCategoriesMgr; rclsid
0x180009138  call    cs:__imp_CoCreateInstance
0x18000913e  test    eax, eax
0x180009140  js      loc_1800093B1
0x180009146  cmp     [rbx], r15d
0x180009149  jz      short loc_1800091A8
0x18000914b  mov     rax, [rbx+8]
0x18000914f  lea     r9, [rbp+170h+var_1C8]
0x180009153  mov     rcx, [rsp+270h+var_208]
0x180009158  mov     r8d, r12d
0x18000915b  mov     rdx, rsi
0x18000915e  movups  xmm0, xmmword ptr [rax]
0x180009161  movdqu  [rbp+170h+var_1C8], xmm0
0x180009166  mov     rax, [rcx]
0x180009169  test    r14d, r14d
0x18000916c  jz      short loc_18000918E
0x18000916e  cmp     [rbx], r12d
0x180009171  jnz     short loc_180009179
0x180009173  mov     rax, [rax+28h]
0x180009177  jmp     short loc_18000917D
0x180009179  mov     rax, [rax+38h]
0x18000917d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009182  mov     edi, eax
0x180009184  test    eax, eax
0x180009186  js      loc_1800093B4
0x18000918c  jmp     short loc_1800091A2
0x18000918e  cmp     [rbx], r12d
0x180009191  jnz     short loc_180009199
0x180009193  mov     rax, [rax+30h]
0x180009197  jmp     short loc_18000919D
0x180009199  mov     rax, [rax+40h]
0x18000919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a2  add     rbx, 10h
0x1800091a6  jmp     short loc_180009146
0x1800091a8  test    r14d, r14d
0x1800091ab  jnz     loc_1800093B1
0x1800091b1  lea     r8d, [r14+40h]; cchMax
0x1800091b5  mov     rcx, rsi; rguid
0x1800091b8  lea     rdx, [rbp+170h+sz]; lpsz
0x1800091bf  call    cs:__imp_StringFromGUID2
0x1800091c5  mov     esi, 80h
0x1800091ca  mov     [rbp+170h+var_1D0], r15
0x1800091ce  mov     edx, esi
0x1800091d0  lea     r8, aClsid; "CLSID\\"
0x1800091d7  lea     rcx, [rbp+170h+SubKey]
0x1800091db  call    cs:__imp__o_wcscpy_s
0x1800091e1  mov     ecx, eax; int
0x1800091e3  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800091e8  lea     r8, [rbp+170h+sz]
0x1800091ef  mov     edx, esi
0x1800091f1  lea     rcx, [rbp+170h+SubKey]
0x1800091f5  call    cs:__imp__o_wcscat_s
0x1800091fb  mov     ecx, eax; int
0x1800091fd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009202  lea     r8, aRequiredCatego; "\\Required Categories"
0x180009209  mov     edx, esi
0x18000920b  lea     rcx, [rbp+170h+SubKey]
0x18000920f  call    cs:__imp__o_wcscat_s
0x180009215  mov     ecx, eax; int
0x180009217  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000921c  mov     rdi, 0FFFFFFFF80000000h
0x180009223  mov     [rbp+170h+var_1E0], r15
0x180009227  mov     r14d, 20019h
0x18000922d  mov     [rbp+170h+var_1E8], rdi
0x180009231  mov     r9d, r14d; unsigned int
0x180009234  mov     [rbp+170h+var_1D8], r15
0x180009238  mov     rdx, rdi; hKey
0x18000923b  mov     [rsp+270h+hKey], r15
0x180009240  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180009244  mov     [rsp+270h+var_1F8], r15
0x180009249  lea     rcx, [rsp+270h+hKey]; this
0x18000924e  mov     [rbp+170h+var_1F0], r15
0x180009252  mov     [rsp+270h+cSubKeys], r15d
0x180009257  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000925c  test    eax, eax
0x18000925e  jnz     short loc_1800092C8
0x180009260  mov     rcx, [rsp+270h+hKey]; hKey
0x180009265  lea     rax, [rsp+270h+cSubKeys]
0x18000926a  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000926f  xor     r9d, r9d; lpReserved
0x180009272  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009277  xor     r8d, r8d; lpcchClass
0x18000927a  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18000927f  xor     edx, edx; lpClass
0x180009281  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009286  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000928b  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009290  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009295  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000929a  call    cs:__imp_RegQueryInfoKeyW
0x1800092a0  lea     rcx, [rsp+270h+hKey]; this
0x1800092a5  mov     ebx, eax
0x1800092a7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800092ac  test    ebx, ebx
0x1800092ae  jnz     short loc_1800092C8
0x1800092b0  cmp     [rsp+270h+cSubKeys], r15d
0x1800092b5  jnz     short loc_1800092C8
0x1800092b7  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x1800092bb  lea     rcx, [rbp+170h+var_1E8]; this
0x1800092bf  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800092c4  mov     rdi, [rbp+170h+var_1E8]
0x1800092c8  lea     r8, aClsid; "CLSID\\"
0x1800092cf  mov     rdx, rsi
0x1800092d2  lea     rcx, [rbp+170h+SubKey]
0x1800092d6  call    cs:__imp__o_wcscpy_s
0x1800092dc  mov     ecx, eax; int
0x1800092de  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800092e3  lea     r8, [rbp+170h+sz]
0x1800092ea  mov     rdx, rsi
0x1800092ed  lea     rcx, [rbp+170h+SubKey]
0x1800092f1  call    cs:__imp__o_wcscat_s
0x1800092f7  mov     ecx, eax; int
0x1800092f9  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800092fe  lea     r8, aImplementedCat; "\\Implemented Categories"
0x180009305  mov     rdx, rsi
0x180009308  lea     rcx, [rbp+170h+SubKey]
0x18000930c  call    cs:__imp__o_wcscat_s
0x180009312  mov     ecx, eax; int
0x180009314  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180009319  mov     r9d, r14d; unsigned int
0x18000931c  lea     r8, [rbp+170h+SubKey]; lpSubKey
0x180009320  mov     rdx, rdi; hKey
0x180009323  lea     rcx, [rsp+270h+hKey]; this
0x180009328  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000932d  test    eax, eax
0x18000932f  jnz     short loc_180009395
0x180009331  mov     rcx, [rsp+270h+hKey]; hKey
0x180009336  lea     rax, [rsp+270h+cSubKeys]
0x18000933b  mov     [rsp+270h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009340  xor     r9d, r9d; lpReserved
0x180009343  mov     [rsp+270h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009348  xor     r8d, r8d; lpcchClass
0x18000934b  mov     [rsp+270h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180009350  xor     edx, edx; lpClass
0x180009352  mov     [rsp+270h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180009357  mov     [rsp+270h+lpcValues], r15; lpcValues
0x18000935c  mov     [rsp+270h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009361  mov     [rsp+270h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009366  mov     [rsp+270h+ppv], rax; lpcSubKeys
0x18000936b  call    cs:__imp_RegQueryInfoKeyW
0x180009371  lea     rcx, [rsp+270h+hKey]; this
0x180009376  mov     ebx, eax
0x180009378  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000937d  test    ebx, ebx
0x18000937f  jnz     short loc_180009395
0x180009381  cmp     [rsp+270h+cSubKeys], r15d
0x180009386  jnz     short loc_180009395
0x180009388  lea     rdx, [rbp+170h+SubKey]; unsigned __int16 *
0x18000938c  lea     rcx, [rbp+170h+var_1E8]; this
0x180009390  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180009395  lea     rcx, [rsp+270h+hKey]; this
0x18000939a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000939f  lea     rcx, [rbp+170h+var_1E8]; this
0x1800093a3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800093a8  lea     rcx, [rbp+170h+var_1D0]
0x1800093ac  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800093b1  mov     edi, r15d
0x1800093b4  lea     rcx, [rsp+270h+var_208]
0x1800093b9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800093be  mov     eax, edi
0x1800093c0  mov     rcx, [rbp+170h+var_30]
0x1800093c7  xor     rcx, rsp; StackCookie
0x1800093ca  call    __security_check_cookie
0x1800093cf  lea     r11, [rsp+270h+var_20]
0x1800093d7  mov     rbx, [r11+40h]
0x1800093db  mov     rsi, [r11+48h]
0x1800093df  mov     rsp, r11
0x1800093e2  pop     r15
0x1800093e4  pop     r14
0x1800093e6  pop     r12
0x1800093e8  pop     rdi
0x1800093e9  pop     rbp
0x1800093ea  retn
```
