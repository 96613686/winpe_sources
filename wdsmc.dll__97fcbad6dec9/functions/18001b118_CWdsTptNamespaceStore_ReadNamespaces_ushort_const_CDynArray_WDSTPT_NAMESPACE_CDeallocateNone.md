# CWdsTptNamespaceStore::ReadNamespaces(ushort const *,CDynArray<_WDSTPT_NAMESPACE *,CDeallocateNone> * *)

- ea: `0x18001b118`
- end: `0x18001b8ae`
- name: `?ReadNamespaces@CWdsTptNamespaceStore@@QEAAKPEBGPEAPEAV?$CDynArray@PEAU_WDSTPT_NAMESPACE@@VCDeallocateNone@@@@@Z`
- size: `1942`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180005f18`

## callees

- `0x18001a9a8`
- `0x18001aab4`
- `0x18001abcc`
- `0x18001b118`
- `0x18002218c`
- `0x180022210`
- `0x1800224d4`
- `0x180022590`
- `0x1800242a4`
- `0x180025850`
- `0x180026694`
- `0x1800266a0`
- `0x180026d3a`
- `0x180026d46`
- `0x180026d70`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b4f0`
- `KERNEL32!GetLastError` at `0x18001b4f0`
- `KERNEL32!LeaveCriticalSection` at `0x18001b5d2`
- `KERNEL32!LeaveCriticalSection` at `0x18001b895`
- `KERNEL32!LeaveCriticalSection` at `0x18001b5d2`
- `KERNEL32!LeaveCriticalSection` at `0x18001b895`
- `KERNEL32!EnterCriticalSection` at `0x18001b146`
- `KERNEL32!EnterCriticalSection` at `0x18001b1f0`
- `KERNEL32!EnterCriticalSection` at `0x18001b146`
- `KERNEL32!EnterCriticalSection` at `0x18001b1f0`
- `KERNEL32!FileTimeToSystemTime` at `0x18001b4e6`
- `KERNEL32!FileTimeToSystemTime` at `0x18001b4e6`
- `ADVAPI32!RegCloseKey` at `0x18001b5c4`
- `ADVAPI32!RegCloseKey` at `0x18001b5c4`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b233`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b233`

## string_xrefs

- `0x18001b384`: `Configuration`
- `0x18001b7cd`: `CWdsTptNamespaceStore::ReadNamespaces:\nError: Failed to retrieve namespaces on the server with error 0x%lx.\n`
- `0x18001b6ca`: `CWdsTptNamespaceStore::ReadNamespaces:\nWarning: Failed to retrieve data for the namespace %s 0x%lx.\n`
- `0x18001b795`: `CWdsTptNamespaceStore::ReadNamespaces:\nWarning: Failed to retrieve data for a total of %u namespaces on the server.\n`

## pseudocode

```c
__int64 __fastcall CWdsTptNamespaceStore::ReadNamespaces(__int64 a1, __int64 a2, _QWORD *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r14
  unsigned int v6; // r13d
  unsigned __int16 *v7; // r15
  char *v8; // rbx
  unsigned int v9; // esi
  _QWORD *v10; // rax
  _QWORD *v11; // rdi
  CRegKey *v12; // r12
  const char *v13; // rdx
  char *v14; // rsi
  unsigned int Value; // r14d
  const char *v16; // rdx
  char *v17; // rax
  unsigned __int16 *v18; // rax
  const char *v19; // rdx
  const char *v20; // rdx
  const char *v21; // rdx
  const char *v22; // rdx
  const char *v23; // rdx
  const char *v24; // rdx
  const char *v25; // rdx
  const char *v26; // rdx
  const char *v27; // rdx
  struct _SYSTEMTIME *v28; // rdx
  const char *v29; // rdx
  void *v30; // rcx
  void *v31; // rcx
  void *v32; // rcx
  void *v33; // rcx
  void *v34; // rcx
  const char *v35; // rdx
  const char *v36; // rdx
  unsigned int v37; // ecx
  int v38; // eax
  unsigned int v39; // r13d
  unsigned __int64 v40; // rax
  void *v41; // rax
  void *v42; // r12
  void *v43; // rcx
  void *v44; // rcx
  void *v45; // rcx
  void *v46; // rcx
  void *v47; // rcx
  void *v48; // rcx
  void *v49; // rcx
  void *v50; // rcx
  void *v51; // rcx
  void *v52; // rcx
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+30h] [rbp-38h]
  void *v55; // [rsp+38h] [rbp-30h] BYREF
  FILETIME FileTime; // [rsp+40h] [rbp-28h] BYREF
  FILETIME v57; // [rsp+48h] [rbp-20h] BYREF
  CRegKey *v58; // [rsp+50h] [rbp-18h]
  HKEY hKey; // [rsp+B0h] [rbp+48h] BYREF
  __int64 v60; // [rsp+B8h] [rbp+50h]
  _QWORD *v61; // [rsp+C0h] [rbp+58h]
  LPCWSTR lpSubKey; // [rsp+C8h] [rbp+60h] BYREF

  v61 = a3;
  v60 = a2;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v6 = 0;
  v55 = 0;
  v7 = 0;
  lpSubKey = 0;
  v8 = 0;
  if ( !a3 )
  {
    v9 = 87;
    goto LABEL_117;
  }
  v10 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
  }
  else
  {
    v11 = 0;
  }
  if ( !v11 )
  {
    v9 = 8;
    goto LABEL_117;
  }
  v12 = (CRegKey *)(a1 + 48);
  v58 = (CRegKey *)(a1 + 48);
  v9 = CRegKey::EnumKeyFirst((CRegKey *)(a1 + 48), &v55);
  if ( ElValidateWin32(v9, v13, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x6A7u) )
    goto LABEL_97;
  LODWORD(v60) = 0;
  while ( 1 )
  {
    v9 = CRegKey::EnumKeyNext(v12, v55, (unsigned __int16 **)&lpSubKey);
    if ( v9 )
      break;
    EnterCriticalSection(v3);
    hKey = 0;
    v14 = 0;
    v57 = 0;
    v7 = (unsigned __int16 *)lpSubKey;
    if ( !lpSubKey || !*lpSubKey )
    {
      Value = 87;
      goto LABEL_37;
    }
    Value = RegOpenKeyExW(*(HKEY *)v12, lpSubKey, 0, 0x20119u, &hKey);
    if ( ElValidateWin32(Value, v16, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x5F5u) )
      goto LABEL_37;
    v17 = (char *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
    v14 = v17;
    if ( !v17 )
    {
      Value = 8;
      goto LABEL_50;
    }
    memset_0(v17, 0, 0x70u);
    v18 = WcsDup(v7);
    *((_QWORD *)v14 + 2) = v18;
    if ( v18 )
    {
      Value = CRegKey::GetValue((CRegKey *)&hKey, L"Type", 4u, v14 + 8, 4u);
      if ( !ElValidateWin32(Value, v19, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x615u) )
      {
        Value = CRegKey::GetValueSz((CRegKey *)&hKey, L"FriendlyName", (unsigned __int16 **)v14 + 3);
        if ( !ElValidateWin32(Value, v20, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x619u) )
        {
          Value = CRegKey::GetValueSz((CRegKey *)&hKey, L"Description", (unsigned __int16 **)v14 + 4);
          if ( !ElValidateWin32(Value, v21, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x61Du) )
          {
            Value = CRegKey::GetValueSz((CRegKey *)&hKey, L"ContentProvider", (unsigned __int16 **)v14 + 5);
            if ( !ElValidateWin32(Value, v22, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x621u) )
            {
              Value = CRegKey::GetValueSz((CRegKey *)&hKey, L"Configuration", (unsigned __int16 **)v14 + 6);
              if ( !ElValidateWin32(Value, v23, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x625u) )
              {
                Value = CRegKey::GetValue((CRegKey *)&hKey, L"SessionStartType", 4u, v14 + 80, 4u);
                if ( !ElValidateWin32(Value, v24, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x62Cu) )
                {
                  Value = CRegKey::GetValue((CRegKey *)&hKey, L"SessionFlags", 4u, v14 + 84, 4u);
                  if ( !ElValidateWin32(Value, v25, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x630u) )
                  {
                    Value = CRegKey::GetValue((CRegKey *)&hKey, L"MinClients", 4u, v14 + 88, 4u);
                    if ( !ElValidateWin32(
                            Value,
                            v26,
                            "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp",
                            0x634u) )
                    {
                      if ( (v14[84] & 2) == 0 )
                        goto LABEL_34;
                      Value = CRegKey::GetValue((CRegKey *)&hKey, L"StartTime", 0xBu, &v57, 8u);
                      if ( !ElValidateWin32(
                              Value,
                              v27,
                              "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp",
                              0x641u) )
                      {
                        v28 = (struct _SYSTEMTIME *)(v14 + 92);
                        FileTime = 0;
                        Value = 0;
                        if ( v14 == (char *)-92LL )
                        {
                          Value = 87;
                        }
                        else
                        {
                          FileTime = v57;
                          if ( !FileTimeToSystemTime(&FileTime, v28) )
                          {
                            Value = GetLastError();
                            if ( Value == 87 )
                              Value = 13;
                          }
                        }
                        if ( !ElValidateWin32(
                                Value,
                                (const char *)v28,
                                "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp",
                                0x645u) )
                        {
LABEL_34:
                          Value = CWdsTptNamespaceStore::ValidateNamespace((struct _WDSTPT_NAMESPACE *)v14);
                          if ( !ElValidateWin32(
                                  Value,
                                  v29,
                                  "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp",
                                  0x650u) )
                            v8 = v14;
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
LABEL_37:
      if ( !Value )
        goto LABEL_50;
      goto LABEL_38;
    }
    Value = 8;
LABEL_38:
    if ( v14 )
    {
      v30 = (void *)*((_QWORD *)v14 + 2);
      if ( v30 )
      {
        operator delete(v30);
        *((_QWORD *)v14 + 2) = 0;
      }
      v31 = (void *)*((_QWORD *)v14 + 3);
      if ( v31 )
      {
        operator delete(v31);
        *((_QWORD *)v14 + 3) = 0;
      }
      v32 = (void *)*((_QWORD *)v14 + 4);
      if ( v32 )
      {
        operator delete(v32);
        *((_QWORD *)v14 + 4) = 0;
      }
      v33 = (void *)*((_QWORD *)v14 + 5);
      if ( v33 )
      {
        operator delete(v33);
        *((_QWORD *)v14 + 5) = 0;
      }
      v34 = (void *)*((_QWORD *)v14 + 6);
      if ( v34 )
      {
        operator delete(v34);
        *((_QWORD *)v14 + 6) = 0;
      }
      operator delete(v14);
    }
LABEL_50:
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    LeaveCriticalSection(lpCriticalSection);
    if ( ElValidateWin32(Value, v35, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x6E1u) )
      goto LABEL_68;
    v37 = *((_DWORD *)v11 + 2);
    v9 = 0;
    if ( *((_DWORD *)v11 + 3) != v37 )
    {
LABEL_65:
      *(_QWORD *)(*v11 + 8LL * (unsigned int)(*((_DWORD *)v11 + 3))++) = v8;
      goto LABEL_66;
    }
    v38 = v37 >> 1;
    if ( v37 >> 1 < 0x20 )
      v38 = 32;
    v36 = (const char *)(v37 + v38);
    if ( (unsigned int)v36 < v37 )
    {
      v9 = (unsigned int)v36 < v37 ? 0x216 : 0;
    }
    else
    {
      v39 = v37 + v38;
      v40 = 8LL * (unsigned int)v36;
      if ( !is_mul_ok((unsigned int)v36, 8u) )
        v40 = -1;
      v41 = operator new[](v40, (const struct std::nothrow_t *)&std::nothrow);
      v42 = v41;
      if ( !v41 )
      {
        v9 = 8;
        goto LABEL_66;
      }
      memmove_0(v41, (const void *)*v11, 8LL * *((unsigned int *)v11 + 2));
      operator delete((void *)*v11);
      *v11 = v42;
      *((_DWORD *)v11 + 2) = v39;
    }
    if ( !v9 )
      goto LABEL_65;
LABEL_66:
    if ( ElValidateWin32(v9, v36, "base\\eco\\wds\\wdsnsstore\\src\\wdstptnamespacestore.cpp", 0x6F3u) )
    {
      v3 = lpCriticalSection;
      goto LABEL_97;
    }
    v6 = v60;
    v8 = 0;
LABEL_68:
    if ( Value )
    {
      if ( g_ErrLibTraceFunction )
        g_ErrLibTraceFunction(
          L"CWdsTptNamespaceStore::ReadNamespaces:\nWarning: Failed to retrieve data for the namespace %s 0x%lx.\n",
          v7,
          Value);
      LODWORD(v60) = ++v6;
    }
    if ( v7 )
    {
      operator delete(v7);
      lpSubKey = 0;
    }
    v3 = lpCriticalSection;
    v12 = v58;
    if ( v8 )
    {
      v43 = (void *)*((_QWORD *)v8 + 2);
      if ( v43 )
      {
        operator delete(v43);
        *((_QWORD *)v8 + 2) = 0;
      }
      v44 = (void *)*((_QWORD *)v8 + 3);
      if ( v44 )
      {
        operator delete(v44);
        *((_QWORD *)v8 + 3) = 0;
      }
      v45 = (void *)*((_QWORD *)v8 + 4);
      if ( v45 )
      {
        operator delete(v45);
        *((_QWORD *)v8 + 4) = 0;
      }
      v46 = (void *)*((_QWORD *)v8 + 5);
      if ( v46 )
      {
        operator delete(v46);
        *((_QWORD *)v8 + 5) = 0;
      }
      v47 = (void *)*((_QWORD *)v8 + 6);
      if ( v47 )
      {
        operator delete(v47);
        *((_QWORD *)v8 + 6) = 0;
      }
      operator delete(v8);
      v8 = 0;
    }
  }
  if ( v9 == 259 )
  {
    v9 = 0;
    if ( !v6 )
      goto LABEL_93;
    if ( g_ErrLibTraceFunction )
      g_ErrLibTraceFunction(
        L"CWdsTptNamespaceStore::ReadNamespaces:\n"
         "Warning: Failed to retrieve data for a total of %u namespaces on the server.\n",
        v6);
    if ( *((_DWORD *)v11 + 3) )
    {
LABEL_93:
      *v61 = v11;
      v11 = 0;
    }
    else
    {
      v9 = 13;
    }
  }
  else if ( g_ErrLibTraceFunction )
  {
    g_ErrLibTraceFunction(
      L"CWdsTptNamespaceStore::ReadNamespaces:\nError: Failed to retrieve namespaces on the server with error 0x%lx.\n",
      v9);
  }
  v7 = (unsigned __int16 *)lpSubKey;
LABEL_97:
  if ( v55 )
    operator delete(v55);
  if ( v7 )
    operator delete(v7);
  if ( v8 )
  {
    v48 = (void *)*((_QWORD *)v8 + 2);
    if ( v48 )
    {
      operator delete(v48);
      *((_QWORD *)v8 + 2) = 0;
    }
    v49 = (void *)*((_QWORD *)v8 + 3);
    if ( v49 )
    {
      operator delete(v49);
      *((_QWORD *)v8 + 3) = 0;
    }
    v50 = (void *)*((_QWORD *)v8 + 4);
    if ( v50 )
    {
      operator delete(v50);
      *((_QWORD *)v8 + 4) = 0;
    }
    v51 = (void *)*((_QWORD *)v8 + 5);
    if ( v51 )
    {
      operator delete(v51);
      *((_QWORD *)v8 + 5) = 0;
    }
    v52 = (void *)*((_QWORD *)v8 + 6);
    if ( v52 )
    {
      operator delete(v52);
      *((_QWORD *)v8 + 6) = 0;
    }
    operator delete(v8);
  }
  if ( v11 )
  {
    CWdsTptNamespaceStore::FreeNamespaceList(v11);
    if ( *v11 )
    {
      operator delete((void *)*v11);
      v11[1] = 0;
      *v11 = 0;
    }
    operator delete(v11);
  }
LABEL_117:
  LeaveCriticalSection(v3);
  return v9;
}

```

## disassembly

```asm
0x18001b118  mov     [rsp-40h+arg_10], r8
0x18001b11d  mov     [rsp-40h+arg_8], rdx
0x18001b122  push    rbp
0x18001b123  push    rbx
0x18001b124  push    rsi
0x18001b125  push    rdi
0x18001b126  push    r12
0x18001b128  push    r13
0x18001b12a  push    r14
0x18001b12c  push    r15
0x18001b12e  mov     rbp, rsp
0x18001b131  sub     rsp, 68h
0x18001b135  lea     r14, [rcx+8]
0x18001b139  mov     rsi, rcx
0x18001b13c  mov     rcx, r14; lpCriticalSection
0x18001b13f  mov     [rbp+lpCriticalSection], r14
0x18001b143  mov     r12, r8
0x18001b146  call    cs:__imp_EnterCriticalSection
0x18001b14c  xor     r13d, r13d
0x18001b14f  mov     [rbp+var_30], r13
0x18001b153  mov     r15d, r13d
0x18001b156  mov     [rbp+lpSubKey], r13
0x18001b15a  mov     ebx, r13d
0x18001b15d  test    r12, r12
0x18001b160  jnz     short loc_18001B16B
0x18001b162  lea     esi, [r13+57h]
0x18001b166  jmp     loc_18001B892
0x18001b16b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b172  mov     ecx, 18h; unsigned __int64
0x18001b177  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b17c  mov     rdi, rax
0x18001b17f  test    rax, rax
0x18001b182  jz      short loc_18001B18D
0x18001b184  mov     [rax], r13
0x18001b187  mov     [rax+8], r13
0x18001b18b  jmp     short loc_18001B190
0x18001b18d  mov     rdi, r13
0x18001b190  test    rdi, rdi
0x18001b193  jnz     short loc_18001B19D
0x18001b195  lea     esi, [rdi+8]
0x18001b198  jmp     loc_18001B892
0x18001b19d  lea     r12, [rsi+30h]
0x18001b1a1  mov     rcx, r12; this
0x18001b1a4  mov     [rbp+var_18], r12
0x18001b1a8  lea     rdx, [rbp+var_30]; void **
0x18001b1ac  call    ?EnumKeyFirst@CRegKey@@QEAAKPEAPEAX@Z; CRegKey::EnumKeyFirst(void * *)
0x18001b1b1  mov     r9d, 6A7h; unsigned int
0x18001b1b7  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b1be  mov     ecx, eax; unsigned int
0x18001b1c0  mov     esi, eax
0x18001b1c2  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b1c7  test    eax, eax
0x18001b1c9  jnz     loc_18001B7E2
0x18001b1cf  mov     dword ptr [rbp+arg_8], r15d
0x18001b1d3  mov     rdx, [rbp+var_30]; void *
0x18001b1d7  lea     r8, [rbp+lpSubKey]; unsigned __int16 **
0x18001b1db  mov     rcx, r12; this
0x18001b1de  call    ?EnumKeyNext@CRegKey@@QEAAKPEAXPEAPEAG@Z; CRegKey::EnumKeyNext(void *,ushort * *)
0x18001b1e3  mov     esi, eax
0x18001b1e5  test    eax, eax
0x18001b1e7  jnz     loc_18001B773
0x18001b1ed  mov     rcx, r14; lpCriticalSection
0x18001b1f0  call    cs:__imp_EnterCriticalSection
0x18001b1f6  mov     [rbp+hKey], r15
0x18001b1fa  mov     rsi, r15
0x18001b1fd  mov     [rbp+var_20], r15
0x18001b201  xor     eax, eax
0x18001b203  mov     r15, [rbp+lpSubKey]
0x18001b207  test    r15, r15
0x18001b20a  jz      loc_18001B546
0x18001b210  cmp     [r15], ax
0x18001b214  jz      loc_18001B546
0x18001b21a  mov     rcx, [r12]; hKey
0x18001b21e  lea     rax, [rbp+hKey]
0x18001b222  mov     r9d, 20119h; samDesired
0x18001b228  mov     [rsp+68h+phkResult], rax; phkResult
0x18001b22d  xor     r8d, r8d; ulOptions
0x18001b230  mov     rdx, r15; lpSubKey
0x18001b233  call    cs:__imp_RegOpenKeyExW
0x18001b239  mov     r9d, 5F5h; unsigned int
0x18001b23f  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b246  mov     ecx, eax; unsigned int
0x18001b248  mov     r14d, eax
0x18001b24b  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b250  xor     r12d, r12d
0x18001b253  test    eax, eax
0x18001b255  jnz     loc_18001B54F
0x18001b25b  lea     r14d, [r12+70h]
0x18001b260  mov     ecx, r14d; unsigned __int64
0x18001b263  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b26a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001b26f  mov     rsi, rax
0x18001b272  test    rax, rax
0x18001b275  jnz     short loc_18001B281
0x18001b277  lea     r14d, [r12+8]
0x18001b27c  jmp     loc_18001B5BB
0x18001b281  mov     r8, r14; Size
0x18001b284  xor     edx, edx; Val
0x18001b286  mov     rcx, rsi; void *
0x18001b289  call    memset_0
0x18001b28e  mov     rcx, r15; Src
0x18001b291  call    ?WcsDup@@YAPEAGPEBG@Z; WcsDup(ushort const *)
0x18001b296  mov     [rsi+10h], rax
0x18001b29a  test    rax, rax
0x18001b29d  jnz     short loc_18001B2A8
0x18001b29f  lea     r14d, [rax+8]
0x18001b2a3  jmp     loc_18001B554
0x18001b2a8  mov     eax, 4
0x18001b2ad  lea     r9, [rsi+8]; void *
0x18001b2b1  mov     r8d, eax; unsigned int
0x18001b2b4  mov     dword ptr [rsp+68h+phkResult], eax; unsigned int
0x18001b2b8  lea     rdx, aType; "Type"
0x18001b2bf  lea     rcx, [rbp+hKey]; this
0x18001b2c3  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001b2c8  mov     r9d, 615h; unsigned int
0x18001b2ce  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b2d5  mov     ecx, eax; unsigned int
0x18001b2d7  mov     r14d, eax
0x18001b2da  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b2df  test    eax, eax
0x18001b2e1  jnz     loc_18001B54F
0x18001b2e7  lea     r8, [rsi+18h]; unsigned __int16 **
0x18001b2eb  lea     rdx, aFriendlyname; "FriendlyName"
0x18001b2f2  lea     rcx, [rbp+hKey]; this
0x18001b2f6  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18001b2fb  mov     r9d, 619h; unsigned int
0x18001b301  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b308  mov     ecx, eax; unsigned int
0x18001b30a  mov     r14d, eax
0x18001b30d  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b312  test    eax, eax
0x18001b314  jnz     loc_18001B54F
0x18001b31a  lea     r8, [rsi+20h]; unsigned __int16 **
0x18001b31e  lea     rdx, aDescription; "Description"
0x18001b325  lea     rcx, [rbp+hKey]; this
0x18001b329  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18001b32e  mov     r9d, 61Dh; unsigned int
0x18001b334  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b33b  mov     ecx, eax; unsigned int
0x18001b33d  mov     r14d, eax
0x18001b340  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b345  test    eax, eax
0x18001b347  jnz     loc_18001B54F
0x18001b34d  lea     r8, [rsi+28h]; unsigned __int16 **
0x18001b351  lea     rdx, aContentprovide; "ContentProvider"
0x18001b358  lea     rcx, [rbp+hKey]; this
0x18001b35c  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18001b361  mov     r9d, 621h; unsigned int
0x18001b367  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b36e  mov     ecx, eax; unsigned int
0x18001b370  mov     r14d, eax
0x18001b373  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b378  test    eax, eax
0x18001b37a  jnz     loc_18001B54F
0x18001b380  lea     r8, [rsi+30h]; unsigned __int16 **
0x18001b384  lea     rdx, aConfiguration; "Configuration"
0x18001b38b  lea     rcx, [rbp+hKey]; this
0x18001b38f  call    ?GetValueSz@CRegKey@@QEAAKPEBGPEAPEAG@Z; CRegKey::GetValueSz(ushort const *,ushort * *)
0x18001b394  mov     r9d, 625h; unsigned int
0x18001b39a  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b3a1  mov     ecx, eax; unsigned int
0x18001b3a3  mov     r14d, eax
0x18001b3a6  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b3ab  test    eax, eax
0x18001b3ad  jnz     loc_18001B54F
0x18001b3b3  mov     eax, 4
0x18001b3b8  lea     r9, [rsi+50h]; void *
0x18001b3bc  mov     r8d, eax; unsigned int
0x18001b3bf  mov     dword ptr [rsp+68h+phkResult], eax; unsigned int
0x18001b3c3  lea     rdx, aSessionstartty; "SessionStartType"
0x18001b3ca  lea     rcx, [rbp+hKey]; this
0x18001b3ce  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001b3d3  mov     r9d, 62Ch; unsigned int
0x18001b3d9  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b3e0  mov     ecx, eax; unsigned int
0x18001b3e2  mov     r14d, eax
0x18001b3e5  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b3ea  test    eax, eax
0x18001b3ec  jnz     loc_18001B54F
0x18001b3f2  mov     eax, 4
0x18001b3f7  lea     r9, [rsi+54h]; void *
0x18001b3fb  mov     r8d, eax; unsigned int
0x18001b3fe  mov     dword ptr [rsp+68h+phkResult], eax; unsigned int
0x18001b402  lea     rdx, aSessionflags; "SessionFlags"
0x18001b409  lea     rcx, [rbp+hKey]; this
0x18001b40d  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001b412  mov     r9d, 630h; unsigned int
0x18001b418  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b41f  mov     ecx, eax; unsigned int
0x18001b421  mov     r14d, eax
0x18001b424  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b429  test    eax, eax
0x18001b42b  jnz     loc_18001B54F
0x18001b431  mov     eax, 4
0x18001b436  lea     r9, [rsi+58h]; void *
0x18001b43a  mov     r8d, eax; unsigned int
0x18001b43d  mov     dword ptr [rsp+68h+phkResult], eax; unsigned int
0x18001b441  lea     rdx, aMinclients; "MinClients"
0x18001b448  lea     rcx, [rbp+hKey]; this
0x18001b44c  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001b451  mov     r9d, 634h; unsigned int
0x18001b457  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b45e  mov     ecx, eax; unsigned int
0x18001b460  mov     r14d, eax
0x18001b463  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b468  test    eax, eax
0x18001b46a  jnz     loc_18001B54F
0x18001b470  test    byte ptr [rsi+54h], 2
0x18001b474  jz      loc_18001B51E
0x18001b47a  lea     r9, [rbp+var_20]; void *
0x18001b47e  mov     dword ptr [rsp+68h+phkResult], 8; unsigned int
0x18001b486  lea     r8d, [rax+0Bh]; unsigned int
0x18001b48a  lea     rdx, aStarttime; "StartTime"
0x18001b491  lea     rcx, [rbp+hKey]; this
0x18001b495  call    ?GetValue@CRegKey@@QEAAKPEBGKPEAXK@Z; CRegKey::GetValue(ushort const *,ulong,void *,ulong)
0x18001b49a  mov     r9d, 641h; unsigned int
0x18001b4a0  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b4a7  mov     ecx, eax; unsigned int
0x18001b4a9  mov     r14d, eax
0x18001b4ac  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b4b1  test    eax, eax
0x18001b4b3  jnz     loc_18001B54F
0x18001b4b9  xor     eax, eax
0x18001b4bb  lea     rdx, [rsi+5Ch]; lpSystemTime
0x18001b4bf  mov     qword ptr [rbp+FileTime.dwLowDateTime], rax
0x18001b4c3  mov     r14d, r12d
0x18001b4c6  test    rdx, rdx
0x18001b4c9  jnz     short loc_18001B4D1
0x18001b4cb  lea     r14d, [rax+57h]
0x18001b4cf  jmp     short loc_18001B505
0x18001b4d1  mov     rcx, [rbp+var_20]
0x18001b4d5  mov     rax, rcx
0x18001b4d8  mov     [rbp+FileTime.dwLowDateTime], ecx
0x18001b4db  shr     rax, 20h
0x18001b4df  lea     rcx, [rbp+FileTime]; lpFileTime
0x18001b4e3  mov     [rbp+FileTime.dwHighDateTime], eax
0x18001b4e6  call    cs:__imp_FileTimeToSystemTime
0x18001b4ec  test    eax, eax
0x18001b4ee  jnz     short loc_18001B505
0x18001b4f0  call    cs:__imp_GetLastError
0x18001b4f6  mov     r14d, eax
0x18001b4f9  cmp     eax, 57h ; 'W'
0x18001b4fc  mov     eax, 0Dh
0x18001b501  cmovz   r14d, eax
0x18001b505  mov     r9d, 645h; unsigned int
0x18001b50b  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b512  mov     ecx, r14d; unsigned int
0x18001b515  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b51a  test    eax, eax
0x18001b51c  jnz     short loc_18001B54F
0x18001b51e  mov     rcx, rsi; struct _WDSTPT_NAMESPACE *
0x18001b521  call    ?ValidateNamespace@CWdsTptNamespaceStore@@SAKPEAU_WDSTPT_NAMESPACE@@@Z; CWdsTptNamespaceStore::ValidateNamespace(_WDSTPT_NAMESPACE *)
0x18001b526  mov     r9d, 650h; unsigned int
0x18001b52c  lea     r8, aBaseEcoWdsWdsn; "base\\eco\\wds\\wdsnsstore\\src\\wdstpt"...
0x18001b533  mov     ecx, eax; unsigned int
0x18001b535  mov     r14d, eax
0x18001b538  call    ?ElValidateWin32@@YAKKPEBD0K@Z; ElValidateWin32(ulong,char const *,char const *,ulong)
0x18001b53d  test    eax, eax
0x18001b53f  jnz     short loc_18001B54F
0x18001b541  mov     rbx, rsi
0x18001b544  jmp     short loc_18001B54F
0x18001b546  mov     r14d, 57h ; 'W'
0x18001b54c  xor     r12d, r12d
0x18001b54f  test    r14d, r14d
0x18001b552  jz      short loc_18001B5BB
0x18001b554  test    rsi, rsi
0x18001b557  jz      short loc_18001B5BB
0x18001b559  mov     rcx, [rsi+10h]; void *
0x18001b55d  test    rcx, rcx
0x18001b560  jz      short loc_18001B56B
0x18001b562  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b567  mov     [rsi+10h], r12
0x18001b56b  mov     rcx, [rsi+18h]; void *
0x18001b56f  test    rcx, rcx
0x18001b572  jz      short loc_18001B57D
0x18001b574  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b579  mov     [rsi+18h], r12
0x18001b57d  mov     rcx, [rsi+20h]; void *
0x18001b581  test    rcx, rcx
0x18001b584  jz      short loc_18001B58F
0x18001b586  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b58b  mov     [rsi+20h], r12
0x18001b58f  mov     rcx, [rsi+28h]; void *
0x18001b593  test    rcx, rcx
0x18001b596  jz      short loc_18001B5A1
0x18001b598  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b59d  mov     [rsi+28h], r12
0x18001b5a1  mov     rcx, [rsi+30h]; void *
0x18001b5a5  test    rcx, rcx
0x18001b5a8  jz      short loc_18001B5B3
0x18001b5aa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b5af  mov     [rsi+30h], r12
0x18001b5b3  mov     rcx, rsi; void *
0x18001b5b6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001b5bb  mov     rcx, [rbp+hKey]; hKey
0x18001b5bf  test    rcx, rcx
0x18001b5c2  jz      short loc_18001B5CE
0x18001b5c4  call    cs:__imp_RegCloseKey
0x18001b5ca  mov     [rbp+hKey], r12
0x18001b5ce  mov     rcx, [rbp+lpCriticalSection]; lpCriticalSection
  ... truncated ...
```
