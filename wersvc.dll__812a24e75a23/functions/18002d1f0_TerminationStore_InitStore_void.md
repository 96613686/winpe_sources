# TerminationStore::InitStore(void)

- ea: `0x18002d1f0`
- end: `0x18002d9cf`
- name: `?InitStore@TerminationStore@@AEAAJXZ`
- size: `2015`
- prototype: `__int64 __fastcall(TerminationStore *__hidden this)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001938c`
- `0x18001e054`

## callees

- `0x1800029f4`
- `0x180002a00`
- `0x180002a24`
- `0x1800035e8`
- `0x180003cf8`
- `0x180003d6c`
- `0x1800064a4`
- `0x180006900`
- `0x180007cc8`
- `0x18000cb10`
- `0x180011648`
- `0x180011bf8`
- `0x180013548`
- `0x18002ccf8`
- `0x18002d084`
- `0x18002d1f0`
- `0x18002d9d8`
- `0x18002dad8`
- `0x18002db20`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d54a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d6c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d766`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d9bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d284`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d2f2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d54a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d6c0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d766`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d7e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d85a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d8c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d943`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002d9bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d2d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18002d2d2`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d258`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d4d9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d258`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002d4d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d462`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18002d462`

## string_xrefs

- `0x18002d266`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d33d`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d530`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d741`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d7bd`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d840`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d8d3`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`
- `0x18002d95e`: `onecore\windows\feedback\core\common\libex\terminationstore.cpp`

## pseudocode

```c
__int64 __fastcall TerminationStore::InitStore(TerminationStore *this)
{
  HKEY *phkResult; // rax
  unsigned int Key; // eax
  __int64 v4; // rdx
  unsigned int v5; // ebx
  LPWSTR v7; // rcx
  __int64 v8; // rsi
  __int64 v9; // rax
  bool v10; // cf
  unsigned __int64 v11; // rax
  _QWORD *v12; // rax
  void *v13; // rbx
  DWORD v14; // r14d
  __int64 v15; // rdx
  unsigned int v16; // eax
  HKEY *v17; // rax
  LSTATUS v18; // eax
  __int64 v19; // r8
  char *v20; // rcx
  void *v21; // rax
  void *v22; // rbx
  TerminationStore *v23; // rcx
  int v24; // eax
  __int64 v25; // r8
  void *v26; // rcx
  __int64 *v27; // rsi
  _QWORD *v28; // rax
  _QWORD *v29; // rcx
  __int64 v30; // r15
  unsigned __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  char *v33; // rcx
  _QWORD *v34; // r8
  __int64 v35; // rdx
  void **v36; // rax
  _QWORD *v37; // rbx
  _QWORD *v38; // rbx
  unsigned int v39; // esi
  _QWORD *v40; // rbx
  unsigned int dwOptions; // [rsp+20h] [rbp-89h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-89h]
  int dwOptionsb; // [rsp+20h] [rbp-89h]
  HKEY v44; // [rsp+60h] [rbp-49h] BYREF
  void *v45; // [rsp+68h] [rbp-41h] BYREF
  void *v46; // [rsp+70h] [rbp-39h] BYREF
  LPWSTR lpName; // [rsp+78h] [rbp-31h] BYREF
  WCHAR *v48; // [rsp+80h] [rbp-29h]
  _QWORD v49[2]; // [rsp+88h] [rbp-21h] BYREF
  _QWORD v50[3]; // [rsp+98h] [rbp-11h] BYREF
  char v51; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  DWORD cSubKeys; // [rsp+110h] [rbp+67h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+118h] [rbp+6Fh] BYREF
  DWORD cchName; // [rsp+120h] [rbp+77h] BYREF
  HKEY hKey; // [rsp+128h] [rbp+7Fh] BYREF

  if ( *(_BYTE *)this )
    return 0;
  hKey = 0;
  phkResult = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  Key = RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\Windows Error Reporting\\TermReason",
          0,
          0,
          1u,
          0xF003Fu,
          0,
          phkResult,
          0);
  if ( Key )
  {
    v4 = 72;
LABEL_4:
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v4,
           (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
           (const char *)Key,
           dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    return v5;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  Key = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( Key )
  {
    v4 = 87;
    goto LABEL_4;
  }
  if ( !cSubKeys )
    goto LABEL_10;
  lpName = (LPWSTR)v49;
  v48 = (WCHAR *)v49;
  LOWORD(v49[0]) = 0;
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(&lpName) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x60,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    v7 = lpName;
    if ( lpName != (LPWSTR)v49 )
      goto LABEL_87;
    goto LABEL_88;
  }
  v8 = cSubKeys;
  v9 = 32LL * cSubKeys;
  if ( !is_mul_ok(cSubKeys, 0x20u) )
    v9 = -1;
  v10 = __CFADD__(v9, 8);
  v11 = v9 + 8;
  if ( v10 )
    v11 = -1;
  v12 = operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v12 )
  {
    v45 = 0;
LABEL_84:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x65,
      (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
      (const char *)0x8007000ELL,
      dwOptions);
    if ( v45 )
    {
      `eh vector destructor iterator'(
        (char *)v45,
        32,
        *((_QWORD *)v45 - 1),
        (void (__fastcall *)(char *))utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
      operator delete[]((char *)v45 - 8, (const struct std::nothrow_t *)(32LL * *((_QWORD *)v45 - 1) + 8));
    }
    goto LABEL_86;
  }
  *v12 = v8;
  v13 = v12 + 1;
  `eh vector constructor iterator'(
    v12 + 1,
    0x20u,
    (unsigned int)v8,
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,
    (void (*)(void *))utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
  v45 = v13;
  if ( !v13 )
    goto LABEL_84;
  v50[0] = &v45;
  v50[1] = &hKey;
  v50[2] = &cSubKeys;
  v51 = 1;
  v14 = 0;
  if ( !cSubKeys )
    goto LABEL_56;
  while ( 1 )
  {
    if ( lpName == (LPWSTR)v49 )
      v15 = 7;
    else
      v15 = (__int64)(v49[0] - (_QWORD)lpName) >> 1;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(&lpName, v15);
    cchName = v48 - lpName + 1;
    v16 = RegEnumKeyExW(hKey, v14, lpName, &cchName, 0, 0, 0, 0);
    if ( v16 == 259 )
      goto LABEL_56;
    if ( v16 )
    {
      v39 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x83,
              (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
              (const char *)v16,
              dwOptionsa);
      tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
      if ( v45 )
      {
        v40 = (char *)v45 - 8;
        `eh vector destructor iterator'(
          (char *)v45,
          32,
          *((_QWORD *)v45 - 1),
          (void (__fastcall *)(char *))utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
        operator delete[](v40, (const struct std::nothrow_t *)(32LL * *v40 + 8));
      }
      if ( lpName != (LPWSTR)v49 )
        operator delete(lpName, (const struct std::nothrow_t *)&std::nothrow);
      if ( hKey )
        RegCloseKey(hKey);
      return v39;
    }
    if ( cchName > (unsigned __int64)(v48 - lpName) )
      __int2c();
    v48 = &lpName[cchName];
    *v48 = 0;
    v44 = 0;
    v17 = tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v44);
    v18 = RegCreateKeyExW(hKey, lpName, 0, 0, 1u, 0xF003Fu, 0, v17, 0);
    if ( v18 < 0 )
      break;
    if ( TerminationStore::KeyIsValidItem(retaddr, v44, lpName) )
    {
      v21 = operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
      v22 = v21;
      if ( !v21 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9E,
          (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
          (const char *)0x8007000ELL,
          dwOptionsb);
        if ( v44 )
          RegCloseKey(v44);
        tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
        v20 = (char *)v45;
        if ( v45 )
          goto LABEL_73;
        goto LABEL_86;
      }
      memset_0(v21, 0, 0x88u);
      v46 = v22;
      v24 = TerminationStore::ConvertKeyToItem(v23, v44, lpName, (struct TerminationItem *)v22);
      if ( v24 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(retaddr, (void *)0xA0, v25, (const char *)(unsigned int)v24);
        if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                (__int64)v45 + 32 * v14,
                lpName,
                v48 - lpName) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA4,
            (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
            (const char *)0x8007000ELL,
            dwOptionsb);
          operator delete(v22, (const struct std::nothrow_t *)0x88);
          if ( v44 )
            RegCloseKey(v44);
          tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
          v20 = (char *)v45;
          if ( !v45 )
            goto LABEL_86;
LABEL_73:
          v38 = (char *)v45 - 8;
          `eh vector destructor iterator'(
            v20,
            32,
            *((_QWORD *)v45 - 1),
            (void (__fastcall *)(char *))utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
          operator delete[](v38, (const struct std::nothrow_t *)(32LL * *v38 + 8));
          goto LABEL_86;
        }
        v26 = v22;
LABEL_52:
        operator delete(v26, (const struct std::nothrow_t *)0x88);
        goto LABEL_53;
      }
      v27 = (__int64 *)((char *)this + 8);
      v28 = (_QWORD *)*((_QWORD *)this + 2);
      v29 = (_QWORD *)*((_QWORD *)this + 3);
      if ( v28 == v29 )
      {
        v30 = *v27;
        v31 = ((__int64)v29 - *v27) >> 3;
        v32 = 7 * (v31 >> 2) + 8;
        if ( v32 > 0xFFFFFFFFFFFFFFFLL )
          v32 = 0xFFFFFFFFFFFFFFFLL;
        if ( v31 >= v32
          || !utl::vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>::_SetCapacity(
                (__int64)this + 8,
                v32) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
            (const char *)0x8007000ELL,
            dwOptionsb);
          if ( v22 )
            operator delete(v22, (const struct std::nothrow_t *)0x88);
          if ( v44 )
            RegCloseKey(v44);
          tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
          v20 = (char *)v45;
          if ( v45 )
            goto LABEL_73;
LABEL_86:
          v7 = lpName;
          if ( lpName != (LPWSTR)v49 )
LABEL_87:
            operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
LABEL_88:
          if ( hKey )
            RegCloseKey(hKey);
          return 2147942414LL;
        }
        v33 = (char *)&v46 - v30;
        v34 = (_QWORD *)*((_QWORD *)this + 2);
        v35 = *v27;
        if ( (char *)&v46 - v30 >= (char *)v34 - *((_QWORD *)this + 1) )
        {
          v36 = &v46;
        }
        else
        {
          v36 = (void **)&v33[v35];
          v22 = *(void **)&v33[v35];
        }
        *v36 = 0;
        *v34 = v22;
        v26 = v46;
      }
      else
      {
        v26 = 0;
        *v28 = v22;
      }
      *((_QWORD *)this + 2) += 8LL;
      if ( v26 )
        goto LABEL_52;
    }
    else if ( !utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                 (__int64)v45 + 32 * v14,
                 lpName,
                 v48 - lpName) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x98,
        (unsigned int)"onecore\\windows\\feedback\\core\\common\\libex\\terminationstore.cpp",
        (const char *)0x8007000ELL,
        dwOptionsb);
      if ( v44 )
        RegCloseKey(v44);
      tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
      v20 = (char *)v45;
      if ( !v45 )
        goto LABEL_86;
      goto LABEL_73;
    }
LABEL_53:
    if ( v44 )
      RegCloseKey(v44);
    if ( ++v14 >= cSubKeys )
      goto LABEL_56;
  }
  wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x8F, v19, (const char *)(unsigned int)v18);
  if ( v44 )
    RegCloseKey(v44);
LABEL_56:
  *(_BYTE *)this = 1;
  tlx::_UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___::__UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___(v50);
  if ( v45 )
  {
    v37 = (char *)v45 - 8;
    `eh vector destructor iterator'(
      (char *)v45,
      32,
      *((_QWORD *)v45 - 1),
      (void (__fastcall *)(char *))utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>);
    operator delete[](v37, (const struct std::nothrow_t *)(32LL * *v37 + 8));
  }
  if ( lpName != (LPWSTR)v49 )
    operator delete(lpName, (const struct std::nothrow_t *)&std::nothrow);
LABEL_10:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x18002d1f0  push    rbp
0x18002d1f2  push    rbx
0x18002d1f3  push    rsi
0x18002d1f4  push    rdi
0x18002d1f5  push    r12
0x18002d1f7  push    r13
0x18002d1f9  push    r14
0x18002d1fb  push    r15
0x18002d1fd  lea     rbp, [rsp-1Fh]
0x18002d202  sub     rsp, 0C8h
0x18002d209  mov     r12, rcx
0x18002d20c  xor     r13d, r13d
0x18002d20f  cmp     [rcx], r13b
0x18002d212  jnz     loc_18002D2F8
0x18002d218  mov     [rbp+57h+hKey], r13
0x18002d21c  lea     rcx, [rbp+57h+hKey]
0x18002d220  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002d225  mov     [rsp+100h+lpdwDisposition], r13; lpdwDisposition
0x18002d22a  mov     [rsp+100h+phkResult], rax; phkResult
0x18002d22f  mov     [rsp+100h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002d234  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x18002d23c  mov     [rsp+100h+dwOptions], 1; unsigned int
0x18002d244  xor     r9d, r9d; lpClass
0x18002d247  xor     r8d, r8d; Reserved
0x18002d24a  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows\\Windows E"...
0x18002d251  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d258  call    cs:__imp_RegCreateKeyExW
0x18002d25e  test    eax, eax
0x18002d260  jz      short loc_18002D28E
0x18002d262  lea     edx, [r13+48h]; void *
0x18002d266  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002d26d  mov     r9d, eax; char *
0x18002d270  mov     rcx, [rbp+5Fh]; this
0x18002d274  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18002d279  mov     ebx, eax
0x18002d27b  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d27f  test    rcx, rcx
0x18002d282  jz      short loc_18002D28A
0x18002d284  call    cs:__imp_RegCloseKey
0x18002d28a  mov     eax, ebx
0x18002d28c  jmp     short loc_18002D2FA
0x18002d28e  mov     [rbp+57h+cSubKeys], r13d
0x18002d292  mov     [rbp+57h+cbMaxSubKeyLen], r13d
0x18002d296  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002d29b  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002d2a0  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18002d2a5  mov     [rsp+100h+lpdwDisposition], r13; lpcbMaxValueNameLen
0x18002d2aa  mov     [rsp+100h+phkResult], r13; lpcValues
0x18002d2af  mov     [rsp+100h+lpSecurityAttributes], r13; lpcbMaxClassLen
0x18002d2b4  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x18002d2b8  mov     qword ptr [rsp+100h+samDesired], rax; lpcbMaxSubKeyLen
0x18002d2bd  lea     rax, [rbp+57h+cSubKeys]
0x18002d2c1  mov     qword ptr [rsp+100h+dwOptions], rax; int
0x18002d2c6  xor     r9d, r9d; lpReserved
0x18002d2c9  xor     r8d, r8d; lpcchClass
0x18002d2cc  xor     edx, edx; lpClass
0x18002d2ce  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d2d2  call    cs:__imp_RegQueryInfoKeyW
0x18002d2d8  test    eax, eax
0x18002d2da  jz      short loc_18002D2E3
0x18002d2dc  mov     edx, 57h ; 'W'
0x18002d2e1  jmp     short loc_18002D266
0x18002d2e3  cmp     [rbp+57h+cSubKeys], r13d
0x18002d2e7  jnz     short loc_18002D30E
0x18002d2e9  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d2ed  test    rcx, rcx
0x18002d2f0  jz      short loc_18002D2F8
0x18002d2f2  call    cs:__imp_RegCloseKey
0x18002d2f8  xor     eax, eax
0x18002d2fa  add     rsp, 0C8h
0x18002d301  pop     r15
0x18002d303  pop     r14
0x18002d305  pop     r13
0x18002d307  pop     r12
0x18002d309  pop     rdi
0x18002d30a  pop     rsi
0x18002d30b  pop     rbx
0x18002d30c  pop     rbp
0x18002d30d  retn
0x18002d30e  lea     rax, [rbp+57h+var_78]
0x18002d312  mov     [rbp+57h+lpName], rax
0x18002d316  lea     rax, [rbp+57h+var_78]
0x18002d31a  mov     [rbp+57h+var_80], rax
0x18002d31e  mov     word ptr [rbp+57h+var_78], r13w
0x18002d323  mov     edx, [rbp+57h+cbMaxSubKeyLen]
0x18002d326  lea     rcx, [rbp+57h+lpName]
0x18002d32a  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18002d32f  test    al, al
0x18002d331  jnz     short loc_18002D36C
0x18002d333  mov     rcx, [rbp+5Fh]; this
0x18002d337  mov     r9d, 8007000Eh; char *
0x18002d33d  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002d344  mov     edx, 60h ; '`'; void *
0x18002d349  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d34e  nop
0x18002d34f  lea     rax, [rbp+57h+var_78]
0x18002d353  mov     rcx, [rbp+57h+lpName]
0x18002d357  cmp     rcx, rax
0x18002d35a  jz      loc_18002D9B6
0x18002d360  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002d367  jmp     loc_18002D9B0
0x18002d36c  mov     esi, [rbp+57h+cSubKeys]
0x18002d36f  mov     eax, 20h ; ' '
0x18002d374  mul     rsi
0x18002d377  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002d37e  cmovb   rax, rcx
0x18002d382  add     rax, 8
0x18002d386  cmovb   rax, rcx
0x18002d38a  lea     rdi, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18002d391  mov     rdx, rdi; struct std::nothrow_t *
0x18002d394  mov     rcx, rax; unsigned __int64
0x18002d397  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002d39c  lea     r15, ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18002d3a3  test    rax, rax
0x18002d3a6  jz      loc_18002D950
0x18002d3ac  mov     [rax], rsi
0x18002d3af  lea     rbx, [rax+8]
0x18002d3b3  mov     qword ptr [rsp+100h+dwOptions], r15; void (*)(void *)
0x18002d3b8  lea     r9, ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x18002d3bf  mov     r8d, esi; unsigned __int64
0x18002d3c2  mov     edx, 20h ; ' '; unsigned __int64
0x18002d3c7  mov     rcx, rbx; void *
0x18002d3ca  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18002d3cf  mov     [rbp+57h+var_98], rbx
0x18002d3d3  test    rbx, rbx
0x18002d3d6  jz      loc_18002D954
0x18002d3dc  lea     rax, [rbp+57h+var_98]
0x18002d3e0  mov     [rbp+57h+var_68], rax
0x18002d3e4  lea     rax, [rbp+57h+hKey]
0x18002d3e8  mov     [rbp+57h+var_60], rax
0x18002d3ec  lea     rax, [rbp+57h+cSubKeys]
0x18002d3f0  mov     [rbp+57h+var_58], rax
0x18002d3f4  mov     [rbp+57h+var_50], 1
0x18002d3f8  mov     r14d, r13d
0x18002d3fb  cmp     [rbp+57h+cSubKeys], r13d
0x18002d3ff  jbe     loc_18002D6DA
0x18002d405  mov     r15d, 88h
0x18002d40b  lea     rax, [rbp+57h+var_78]
0x18002d40f  cmp     [rbp+57h+lpName], rax
0x18002d413  jnz     short loc_18002D41C
0x18002d415  mov     edx, 7
0x18002d41a  jmp     short loc_18002D427
0x18002d41c  mov     rdx, [rbp+57h+var_78]
0x18002d420  sub     rdx, [rbp+57h+lpName]
0x18002d424  sar     rdx, 1
0x18002d427  lea     rcx, [rbp+57h+lpName]
0x18002d42b  call    ?resize@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::resize(unsigned __int64,wchar_t)
0x18002d430  mov     rax, [rbp+57h+var_80]
0x18002d434  mov     r8, [rbp+57h+lpName]; lpName
0x18002d438  sub     rax, r8
0x18002d43b  sar     rax, 1
0x18002d43e  inc     eax
0x18002d440  mov     [rbp+57h+cchName], eax
0x18002d443  mov     [rsp+100h+phkResult], r13; lpftLastWriteTime
0x18002d448  mov     [rsp+100h+lpSecurityAttributes], r13; lpcchClass
0x18002d44d  mov     qword ptr [rsp+100h+samDesired], r13; lpClass
0x18002d452  mov     qword ptr [rsp+100h+dwOptions], r13; unsigned int
0x18002d457  lea     r9, [rbp+57h+cchName]; lpcchName
0x18002d45b  mov     edx, r14d; dwIndex
0x18002d45e  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d462  call    cs:__imp_RegEnumKeyExW
0x18002d468  cmp     eax, 103h
0x18002d46d  jz      loc_18002D6D3
0x18002d473  test    eax, eax
0x18002d475  jnz     loc_18002D8CC
0x18002d47b  mov     ecx, [rbp+57h+cchName]
0x18002d47e  mov     rax, [rbp+57h+var_80]
0x18002d482  mov     rdx, [rbp+57h+lpName]
0x18002d486  sub     rax, rdx
0x18002d489  sar     rax, 1
0x18002d48c  cmp     rcx, rax
0x18002d48f  jbe     short loc_18002D493
0x18002d491  int     2Ch; Windows NT - assertion failure
0x18002d493  lea     rcx, [rdx+rcx*2]
0x18002d497  mov     [rbp+57h+var_80], rcx
0x18002d49b  mov     [rcx], r13w
0x18002d49f  mov     [rbp+57h+var_A0], r13
0x18002d4a3  lea     rcx, [rbp+57h+var_A0]
0x18002d4a7  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18002d4ac  mov     [rsp+100h+lpdwDisposition], r13; lpdwDisposition
0x18002d4b1  mov     [rsp+100h+phkResult], rax; phkResult
0x18002d4b6  mov     [rsp+100h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18002d4bb  mov     [rsp+100h+samDesired], 0F003Fh; samDesired
0x18002d4c3  mov     [rsp+100h+dwOptions], 1; int
0x18002d4cb  xor     r9d, r9d; lpClass
0x18002d4ce  xor     r8d, r8d; Reserved
0x18002d4d1  mov     rdx, [rbp+57h+lpName]; lpSubKey
0x18002d4d5  mov     rcx, [rbp+57h+hKey]; hKey
0x18002d4d9  call    cs:__imp_RegCreateKeyExW
0x18002d4df  mov     rcx, [rbp+5Fh]; this
0x18002d4e3  test    eax, eax
0x18002d4e5  js      loc_18002D8A7
0x18002d4eb  mov     r8, [rbp+57h+lpName]; wchar_t *
0x18002d4ef  mov     rdx, [rbp+57h+var_A0]; HKEY
0x18002d4f3  call    ?KeyIsValidItem@TerminationStore@@AEAA_NPEAUHKEY__@@PEB_W@Z; TerminationStore::KeyIsValidItem(HKEY__ *,wchar_t const *)
0x18002d4f8  test    al, al
0x18002d4fa  jnz     loc_18002D597
0x18002d500  mov     r8, [rbp+57h+var_80]
0x18002d504  mov     rdx, [rbp+57h+lpName]
0x18002d508  sub     r8, rdx
0x18002d50b  sar     r8, 1
0x18002d50e  mov     ecx, r14d
0x18002d511  shl     rcx, 5
0x18002d515  add     rcx, [rbp+57h+var_98]
0x18002d519  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002d51e  test    al, al
0x18002d520  jnz     loc_18002D6B7
0x18002d526  mov     rcx, [rbp+5Fh]; this
0x18002d52a  mov     r9d, 8007000Eh; char *
0x18002d530  lea     r8, aOnecoreWindows_3; "onecore\\windows\\feedback\\core\\commo"...
0x18002d537  mov     edx, 98h; void *
0x18002d53c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d541  mov     rcx, [rbp+57h+var_A0]; hKey
0x18002d545  test    rcx, rcx
0x18002d548  jz      short loc_18002D550
0x18002d54a  call    cs:__imp_RegCloseKey
0x18002d550  lea     rcx, [rbp+57h+var_68]
0x18002d554  call    tlx___UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e_______UndoSolo__lambda_aeb820e62f78e2265e0b39de628cb12e___
0x18002d559  mov     rcx, [rbp+57h+var_98]; void *
0x18002d55d  test    rcx, rcx
0x18002d560  jz      loc_18002D9A0
0x18002d566  lea     rbx, [rcx-8]
0x18002d56a  lea     r9, ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; void (*)(void *)
0x18002d571  mov     r8, [rbx]; unsigned __int64
0x18002d574  mov     edx, 20h ; ' '; unsigned __int64
0x18002d579  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18002d57e  mov     rdx, [rbx]
0x18002d581  shl     rdx, 5
0x18002d585  add     rdx, 8; struct std::nothrow_t *
0x18002d589  mov     rcx, rbx; void *
0x18002d58c  call    ??_V@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete[](void *,std::nothrow_t const &)
0x18002d591  nop
0x18002d592  jmp     loc_18002D9A0
0x18002d597  mov     rdx, rdi; struct std::nothrow_t *
0x18002d59a  mov     rcx, r15; unsigned __int64
0x18002d59d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d5a2  mov     rbx, rax
0x18002d5a5  test    rax, rax
0x18002d5a8  jz      loc_18002D836
0x18002d5ae  mov     r8, r15; Size
0x18002d5b1  xor     edx, edx; Val
0x18002d5b3  mov     rcx, rax; void *
0x18002d5b6  call    memset_0
0x18002d5bb  mov     [rbp+57h+var_90], rbx
0x18002d5bf  mov     r9, rbx; struct TerminationItem *
0x18002d5c2  mov     r8, [rbp+57h+lpName]; wchar_t *
0x18002d5c6  mov     rdx, [rbp+57h+var_A0]; HKEY
0x18002d5ca  call    ?ConvertKeyToItem@TerminationStore@@AEAAJPEAUHKEY__@@PEB_WPEAUTerminationItem@@@Z; TerminationStore::ConvertKeyToItem(HKEY__ *,wchar_t const *,TerminationItem *)
0x18002d5cf  mov     rcx, [rbp+5Fh]; this
0x18002d5d3  test    eax, eax
0x18002d5d5  jns     short loc_18002D612
0x18002d5d7  mov     r9d, eax; char *
0x18002d5da  mov     edx, 0A0h; void *
0x18002d5df  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002d5e4  mov     r8, [rbp+57h+var_80]
0x18002d5e8  mov     rdx, [rbp+57h+lpName]
0x18002d5ec  sub     r8, rdx
0x18002d5ef  sar     r8, 1
0x18002d5f2  mov     ecx, r14d
0x18002d5f5  shl     rcx, 5
0x18002d5f9  add     rcx, [rbp+57h+var_98]
0x18002d5fd  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18002d602  test    al, al
0x18002d604  jz      loc_18002D737
0x18002d60a  mov     rcx, rbx
0x18002d60d  jmp     loc_18002D6AF
0x18002d612  lea     rsi, [r12+8]
0x18002d617  mov     rax, [rsi+8]
0x18002d61b  mov     rcx, [rsi+10h]
0x18002d61f  cmp     rax, rcx
0x18002d622  jz      short loc_18002D62C
0x18002d624  mov     rcx, r13
0x18002d627  mov     [rax], rbx
0x18002d62a  jmp     short loc_18002D6A5
0x18002d62c  mov     r15, [rsi]
0x18002d62f  sub     rcx, r15
0x18002d632  sar     rcx, 3
0x18002d636  mov     rax, rcx
0x18002d639  shr     rax, 2
0x18002d63d  imul    rdx, rax, 7
0x18002d641  add     rdx, 8
0x18002d645  mov     rax, 0FFFFFFFFFFFFFFFh
0x18002d64f  cmp     rdx, rax
0x18002d652  cmova   rdx, rax
0x18002d656  cmp     rcx, rdx
0x18002d659  jnb     loc_18002D7B3
0x18002d65f  mov     rcx, rsi
0x18002d662  call    ?_SetCapacity@?$vector@V?$unique_ptr@UTerminationItem@@U?$default_delete@UTerminationItem@@@utl@@@utl@@V?$allocator@V?$unique_ptr@UTerminationItem@@U?$default_delete@UTerminationItem@@@utl@@@utl@@@2@@utl@@AEAA_N_K@Z; utl::vector<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>,utl::allocator<utl::unique_ptr<TerminationItem,utl::default_delete<TerminationItem>>>>::_SetCapacity(unsigned __int64)
0x18002d667  test    al, al
0x18002d669  jz      loc_18002D7B3
0x18002d66f  lea     rcx, [rbp+57h+var_90]
0x18002d673  sub     rcx, r15
0x18002d676  mov     r8, [rsi+8]
0x18002d67a  mov     rdx, [rsi]
0x18002d67d  mov     rax, r8
0x18002d680  sub     rax, rdx
0x18002d683  cmp     rcx, rax
0x18002d686  jnb     short loc_18002D691
0x18002d688  lea     rax, [rcx+rdx]
0x18002d68c  mov     rbx, [rax]
  ... truncated ...
```
