# UtilRegGetString(HKEY__ *,ushort const *,ushort const *,ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *,bool,bool)

- ea: `0x180012b0c`
- end: `0x180012ca6`
- name: `?UtilRegGetString@@YAJPEAUHKEY__@@PEBG11PEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@_N3@Z`
- size: `410`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, DWORD)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011af0`

## callees

- `0x180005c80`
- `0x180009580`
- `0x1800096a8`
- `0x1800098f8`
- `0x180009a78`
- `0x18000aea4`
- `0x18000af28`
- `0x18000f764`
- `0x180012b0c`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180012c62`
- `msvcrt!wcsnlen` at `0x180012c62`
- `ADVAPI32!RegGetValueW` at `0x180012bd3`
- `ADVAPI32!RegGetValueW` at `0x180012c33`
- `ADVAPI32!RegGetValueW` at `0x180012bd3`
- `ADVAPI32!RegGetValueW` at `0x180012c33`
- `ADVAPI32!RegOpenKeyExW` at `0x180012b91`
- `ADVAPI32!RegOpenKeyExW` at `0x180012b91`

## string_xrefs

- `0x180012ba3`: `StorePath`
- `0x180012c15`: `StorePath`

## pseudocode

```c
__int64 __fastcall UtilRegGetString(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, DWORD pcbData)
{
  __int64 v6; // rdi
  unsigned int v7; // ebx
  HKEY *phkResult; // rax
  HKEY v9; // rbx
  LSTATUS ValueW; // eax
  _WORD *v11; // rcx
  size_t v12; // rax
  PVOID pvData[4]; // [rsp+40h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+28h] BYREF

  pcbData = 0;
  hkey = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(pvData);
  v6 = a5;
  if ( a5 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             pvData,
                             &lParam) )
    {
LABEL_4:
      v7 = -2147024882;
LABEL_11:
      v11 = *(_WORD **)v6;
      *(_QWORD *)(v6 + 8) = *(_QWORD *)v6;
      *v11 = 0;
      goto LABEL_14;
    }
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\Windows Error Reporting",
            0,
            0x101u,
            phkResult) )
    {
      v9 = hkey;
      pcbData = 0;
      if ( !RegGetValueW(hkey, 0, L"StorePath", 2u, 0, 0, &pcbData) )
      {
        pvData[1] = pvData[0];
        *(_WORD *)pvData[0] = 0;
        if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::resize(
                                 pvData,
                                 ((unsigned __int64)pcbData >> 1) + 1) )
          goto LABEL_4;
        ValueW = RegGetValueW(v9, 0, L"StorePath", 2u, 0, pvData[0], &pcbData);
        v7 = ValueW;
        if ( ValueW )
        {
          if ( ValueW > 0 )
            v7 = (unsigned __int16)ValueW | 0x80070000;
          goto LABEL_11;
        }
        v12 = wcsnlen((const wchar_t *)pvData[0], (unsigned __int64)pcbData >> 1);
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::erase(
          pvData,
          v12);
      }
    }
    v7 = 0;
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      v6,
      pvData);
    goto LABEL_14;
  }
  v7 = -2147024809;
LABEL_14:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(pvData);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hkey);
  return v7;
}

```

## disassembly

```asm
0x180012b0c  mov     [rsp-8+arg_0], rbx
0x180012b11  mov     [rsp-8+arg_8], rdi
0x180012b16  mov     [rsp-8+hkey], r9
0x180012b1b  push    rbp
0x180012b1c  mov     rbp, rsp
0x180012b1f  sub     rsp, 60h
0x180012b23  lea     rcx, [rbp+var_20]; void *
0x180012b27  mov     [rbp+arg_28], 0
0x180012b2e  mov     [rbp+hkey], 0
0x180012b36  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180012b3b  mov     rdi, [rbp+arg_20]
0x180012b3f  test    rdi, rdi
0x180012b42  jnz     short loc_180012B4E
0x180012b44  mov     ebx, 80070057h
0x180012b49  jmp     loc_180012C82
0x180012b4e  lea     rdx, lParam
0x180012b55  lea     rcx, [rbp+var_20]
0x180012b59  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180012b5e  test    al, al
0x180012b60  jnz     short loc_180012B6C
0x180012b62  mov     ebx, 8007000Eh
0x180012b67  jmp     loc_180012C4A
0x180012b6c  lea     rcx, [rbp+hkey]
0x180012b70  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180012b75  mov     r9d, 101h; samDesired
0x180012b7b  mov     [rsp+60h+phkResult], rax; phkResult
0x180012b80  xor     r8d, r8d; ulOptions
0x180012b83  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\Windows E"...
0x180012b8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180012b91  call    cs:__imp_RegOpenKeyExW
0x180012b97  test    eax, eax
0x180012b99  jnz     loc_180012C74
0x180012b9f  mov     rbx, [rbp+hkey]
0x180012ba3  lea     r8, Value; "StorePath"
0x180012baa  mov     [rbp+arg_28], eax
0x180012bad  mov     r9d, 2; dwFlags
0x180012bb3  lea     rax, [rbp+arg_28]
0x180012bb7  xor     edx, edx; lpSubKey
0x180012bb9  mov     [rsp+60h+pcbData], rax; pcbData
0x180012bbe  mov     rcx, rbx; hkey
0x180012bc1  mov     [rsp+60h+pvData], 0; pvData
0x180012bca  mov     [rsp+60h+phkResult], 0; pdwType
0x180012bd3  call    cs:__imp_RegGetValueW
0x180012bd9  test    eax, eax
0x180012bdb  jnz     loc_180012C74
0x180012be1  mov     rcx, [rbp+var_20]
0x180012be5  mov     [rbp+var_18], rcx
0x180012be9  mov     [rcx], ax
0x180012bec  lea     rcx, [rbp+var_20]
0x180012bf0  mov     edx, [rbp+arg_28]
0x180012bf3  shr     rdx, 1
0x180012bf6  inc     rdx
0x180012bf9  call    ?resize@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_N_KG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::resize(unsigned __int64,ushort)
0x180012bfe  test    al, al
0x180012c00  jz      loc_180012B62
0x180012c06  lea     rax, [rbp+arg_28]
0x180012c0a  mov     r9d, 2; dwFlags
0x180012c10  mov     [rsp+60h+pcbData], rax; pcbData
0x180012c15  lea     r8, Value; "StorePath"
0x180012c1c  mov     rax, [rbp+var_20]
0x180012c20  xor     edx, edx; lpSubKey
0x180012c22  mov     [rsp+60h+pvData], rax; pvData
0x180012c27  mov     rcx, rbx; hkey
0x180012c2a  mov     [rsp+60h+phkResult], 0; pdwType
0x180012c33  call    cs:__imp_RegGetValueW
0x180012c39  mov     ebx, eax
0x180012c3b  test    eax, eax
0x180012c3d  jz      short loc_180012C58
0x180012c3f  jle     short loc_180012C4A
0x180012c41  movzx   ebx, ax
0x180012c44  or      ebx, 80070000h
0x180012c4a  mov     rcx, [rdi]
0x180012c4d  xor     eax, eax
0x180012c4f  mov     [rdi+8], rcx
0x180012c53  mov     [rcx], ax
0x180012c56  jmp     short loc_180012C82
0x180012c58  mov     edx, [rbp+arg_28]
0x180012c5b  mov     rcx, [rbp+var_20]; Source
0x180012c5f  shr     rdx, 1; MaxCount
0x180012c62  call    cs:__imp_wcsnlen
0x180012c68  mov     rdx, rax
0x180012c6b  lea     rcx, [rbp+var_20]
0x180012c6f  call    ?erase@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV12@_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::erase(unsigned __int64)
0x180012c74  xor     ebx, ebx
0x180012c76  lea     rdx, [rbp+var_20]
0x180012c7a  mov     rcx, rdi
0x180012c7d  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x180012c82  lea     rcx, [rbp+var_20]
0x180012c86  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180012c8b  lea     rcx, [rbp+hkey]
0x180012c8f  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180012c94  mov     rdi, [rsp+60h+arg_8]
0x180012c99  mov     eax, ebx
0x180012c9b  mov     rbx, [rsp+60h+arg_0]
0x180012ca0  add     rsp, 60h
0x180012ca4  pop     rbp
0x180012ca5  retn
```
