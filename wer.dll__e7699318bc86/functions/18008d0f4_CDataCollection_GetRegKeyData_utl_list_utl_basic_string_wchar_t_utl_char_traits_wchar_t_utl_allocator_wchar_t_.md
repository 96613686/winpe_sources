# CDataCollection::GetRegKeyData(utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,int,void *)

- ea: `0x18008d0f4`
- end: `0x18008d553`
- name: `?GetRegKeyData@CDataCollection@@AEAAJAEAV?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@HPEAX@Z`
- size: `1119`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004ee3c`

## callees

- `0x180004bb4`
- `0x18000716c`
- `0x18000bc10`
- `0x18000bfbc`
- `0x18000d75c`
- `0x18000dad0`
- `0x18000ea64`
- `0x180013a20`
- `0x18001c650`
- `0x18001c6d8`
- `0x18001f5bc`
- `0x18001fe24`
- `0x18002b7a4`
- `0x1800376c8`
- `0x180050db0`
- `0x18008af84`
- `0x18008afb8`
- `0x18008aff0`
- `0x18008d0f4`
- `0x18009b868`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2eb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008d3bf`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008d3bf`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d3fa`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18008d3fa`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008d2e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18008d2e1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d26e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d292`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d36f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d26e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d292`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18008d36f`

## pseudocode

```c
__int64 __fastcall CDataCollection::GetRegKeyData(__int64 a1, __int64 *a2, int a3, void *a4)
{
  unsigned int v8; // edi
  __int64 v9; // rdx
  _QWORD *v10; // rcx
  __int64 v11; // rax
  wchar_t *v12; // rcx
  int Key; // eax
  CDataCollection *v14; // rcx
  DWORD LastError; // eax
  DWORD v16; // r8d
  DWORD v17; // r9d
  DWORD i; // r14d
  __int64 v19; // rdi
  __int64 v20; // rcx
  _QWORD *v21; // rdi
  __int64 v22; // rcx
  char v23; // al
  char v24; // r8
  _QWORD *v25; // rax
  _QWORD *v26; // rcx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  char *v35; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+90h] [rbp-70h]
  _QWORD v38[5]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&lpBuffer);
  cValues = 0;
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cSubKeys = 0;
  NumberOfBytesWritten = 0;
  if ( a4 == (void *)-1LL )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
    v8 = -2147024809;
  }
  else if ( (__int64 *)*a2 == a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147500037LL);
    v8 = -2147467259;
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(&lpBuffer, *a2 + 16);
    v9 = *a2;
    v10 = *(_QWORD **)(*a2 + 8);
    v11 = *(_QWORD *)*a2;
    *v10 = v11;
    *(_QWORD *)(v11 + 8) = v10;
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
      (__int64)v10,
      v9);
    v12 = (wchar_t *)lpBuffer;
    --a2[2];
    Key = CRegSetting::GetKey(v12);
    v8 = Key;
    if ( Key >= 0 )
    {
      WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
      WriteFile(a4, lpBuffer, 2 * ((v37 - (__int64)lpBuffer) >> 1), &NumberOfBytesWritten, 0);
      if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
      }
      else
      {
        v16 = cValues;
        v17 = cbMaxValueNameLen + 1;
        if ( cbMaxValueNameLen + 1 < 0xB )
          v17 = 11;
        cbMaxValueNameLen = v17;
        if ( cValues )
        {
          WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
          v16 = cValues;
          v17 = cbMaxValueNameLen;
        }
        CDataCollection::WriteValuesForRegKey(v14, hKey, v16, v17, cbMaxValueLen, a4);
        if ( a3 )
        {
          cchName = 0;
          for ( i = 0; i < cSubKeys; ++i )
          {
            if ( !WaitForSingleObject(*(HANDLE *)(a1 + 16), 0) )
            {
              v8 = -2145681407;
              goto LABEL_46;
            }
            cchName = 260;
            if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0)
              && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
              && (WPP_GLOBAL_Control[14] & 1) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
            }
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v38);
            v19 = -1;
            do
              ++v19;
            while ( Name[v19] );
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(v38)
              && utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                   (__int64)v38,
                   lpBuffer,
                   (v37 - (__int64)lpBuffer) >> 1)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                    v38,
                                    92)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v38,
                                    Name,
                                    v19) )
            {
              v21 = (_QWORD *)*a2;
              utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                v20,
                &v35);
              if ( !v35
                || (v23 = utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                            v22,
                            v35 + 16,
                            v38),
                    v24 = 1,
                    !v23) )
              {
                v24 = 0;
              }
              v25 = (_QWORD *)utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                                v22,
                                (__int64 *)&v35,
                                v24);
              if ( v25 )
              {
                v26 = (_QWORD *)v21[1];
                v25[1] = v26;
                *v25 = v21;
                *v26 = v25;
                v21[1] = v25;
                ++a2[2];
              }
              utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>((LPVOID *)&v35);
            }
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v38);
          }
        }
        v8 = 0;
      }
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids,
        (unsigned int)Key);
    }
  }
LABEL_46:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpBuffer);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18008d0f4  push    rbp
0x18008d0f6  push    rbx
0x18008d0f7  push    rsi
0x18008d0f8  push    rdi
0x18008d0f9  push    r12
0x18008d0fb  push    r14
0x18008d0fd  push    r15
0x18008d0ff  lea     rbp, [rsp-1F0h]
0x18008d107  sub     rsp, 2F0h
0x18008d10e  mov     rax, cs:__security_cookie
0x18008d115  xor     rax, rsp
0x18008d118  mov     [rbp+220h+var_40], rax
0x18008d11f  mov     r15, rcx
0x18008d122  xor     r12d, r12d
0x18008d125  lea     rcx, [rbp+220h+lpBuffer]; void *
0x18008d129  mov     [rsp+320h+hKey], r12
0x18008d12e  mov     rbx, r9
0x18008d131  mov     r14d, r8d
0x18008d134  mov     rsi, rdx
0x18008d137  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008d13c  mov     [rsp+320h+cValues], r12d
0x18008d141  mov     [rsp+320h+cbMaxValueNameLen], r12d
0x18008d146  mov     [rsp+320h+cbMaxValueLen], r12d
0x18008d14b  mov     [rsp+320h+cSubKeys], r12d
0x18008d150  mov     [rsp+320h+NumberOfBytesWritten], r12d
0x18008d155  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18008d159  jnz     short loc_18008D193
0x18008d15b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d162  lea     rbx, WPP_GLOBAL_Control
0x18008d169  cmp     rcx, rbx
0x18008d16c  jz      short loc_18008D189
0x18008d16e  test    byte ptr [rcx+1Ch], 1
0x18008d172  jz      short loc_18008D189
0x18008d174  mov     rcx, [rcx+10h]
0x18008d178  lea     edx, [r12+20h]
0x18008d17d  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d184  call    WPP_SF_
0x18008d189  mov     edi, 80070057h
0x18008d18e  jmp     loc_18008D51D
0x18008d193  mov     rdx, [rsi]
0x18008d196  cmp     rdx, rsi
0x18008d199  jnz     short loc_18008D1D9
0x18008d19b  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d1a2  lea     rbx, WPP_GLOBAL_Control
0x18008d1a9  cmp     rcx, rbx
0x18008d1ac  jz      short loc_18008D1CF
0x18008d1ae  test    byte ptr [rcx+1Ch], 1
0x18008d1b2  jz      short loc_18008D1CF
0x18008d1b4  mov     rcx, [rcx+10h]
0x18008d1b8  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d1bf  mov     edx, 21h ; '!'
0x18008d1c4  mov     r9d, 80004005h
0x18008d1ca  call    WPP_SF_d
0x18008d1cf  mov     edi, 80004005h
0x18008d1d4  jmp     loc_18008D51D
0x18008d1d9  add     rdx, 10h
0x18008d1dd  lea     rcx, [rbp+220h+lpBuffer]
0x18008d1e1  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008d1e6  mov     rdx, [rsi]
0x18008d1e9  mov     rcx, [rdx+8]
0x18008d1ed  mov     rax, [rdx]
0x18008d1f0  mov     [rcx], rax
0x18008d1f3  mov     [rax+8], rcx
0x18008d1f7  call    ??$_DeleteNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> *)
0x18008d1fc  mov     rcx, [rbp+220h+lpBuffer]; Str
0x18008d200  lea     r8, [rsp+320h+hKey]
0x18008d205  dec     qword ptr [rsi+10h]
0x18008d209  call    ?GetKey@CRegSetting@@SAJPEB_WKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; CRegSetting::GetKey(wchar_t const *,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x18008d20e  mov     edi, eax
0x18008d210  test    eax, eax
0x18008d212  jns     short loc_18008D252
0x18008d214  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d21b  lea     rbx, WPP_GLOBAL_Control
0x18008d222  cmp     rcx, rbx
0x18008d225  jz      loc_18008D51D
0x18008d22b  test    byte ptr [rcx+1Ch], 1
0x18008d22f  jz      loc_18008D51D
0x18008d235  mov     rcx, [rcx+10h]
0x18008d239  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d240  mov     edx, 22h ; '"'
0x18008d245  mov     r9d, eax
0x18008d248  call    WPP_SF_d
0x18008d24d  jmp     loc_18008D51D
0x18008d252  mov     edi, 4
0x18008d257  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d25c  mov     r8d, edi; nNumberOfBytesToWrite
0x18008d25f  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d264  lea     rdx, asc_1800B2BE0; "\r\n"
0x18008d26b  mov     rcx, rbx; hFile
0x18008d26e  call    cs:__imp_WriteFile
0x18008d274  mov     r8, [rbp+220h+var_290]
0x18008d278  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d27d  mov     rdx, [rbp+220h+lpBuffer]; lpBuffer
0x18008d281  mov     rcx, rbx; hFile
0x18008d284  sub     r8, rdx
0x18008d287  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d28c  sar     r8, 1
0x18008d28f  add     r8d, r8d; nNumberOfBytesToWrite
0x18008d292  call    cs:__imp_WriteFile
0x18008d298  mov     rcx, [rsp+320h+hKey]; hKey
0x18008d29d  lea     rax, [rsp+320h+cbMaxValueLen]
0x18008d2a2  mov     [rsp+320h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18008d2a7  xor     r9d, r9d; lpReserved
0x18008d2aa  mov     [rsp+320h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18008d2af  xor     r8d, r8d; lpcchClass
0x18008d2b2  mov     [rsp+320h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18008d2b7  xor     edx, edx; lpClass
0x18008d2b9  lea     rax, [rsp+320h+cbMaxValueNameLen]
0x18008d2be  mov     [rsp+320h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18008d2c3  lea     rax, [rsp+320h+cValues]
0x18008d2c8  mov     [rsp+320h+lpcValues], rax; lpcValues
0x18008d2cd  lea     rax, [rsp+320h+cSubKeys]
0x18008d2d2  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18008d2d7  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18008d2dc  mov     [rsp+320h+lpOverlapped], rax; lpcSubKeys
0x18008d2e1  call    cs:__imp_RegQueryInfoKeyW
0x18008d2e7  test    eax, eax
0x18008d2e9  jz      short loc_18008D335
0x18008d2eb  call    cs:__imp_GetLastError
0x18008d2f1  mov     ecx, eax; unsigned int
0x18008d2f3  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x18008d2f8  mov     edi, eax
0x18008d2fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d301  lea     rbx, WPP_GLOBAL_Control
0x18008d308  cmp     rcx, rbx
0x18008d30b  jz      loc_18008D51D
0x18008d311  test    byte ptr [rcx+1Ch], 1
0x18008d315  jz      loc_18008D51D
0x18008d31b  mov     rcx, [rcx+10h]
0x18008d31f  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d326  mov     edx, 23h ; '#'
0x18008d32b  call    WPP_SF_
0x18008d330  jmp     loc_18008D51D
0x18008d335  mov     r9d, [rsp+320h+cbMaxValueNameLen]
0x18008d33a  mov     eax, 0Bh
0x18008d33f  mov     r8d, [rsp+320h+cValues]
0x18008d344  inc     r9d
0x18008d347  cmp     r9d, eax
0x18008d34a  cmovb   r9d, eax
0x18008d34e  mov     [rsp+320h+cbMaxValueNameLen], r9d
0x18008d353  test    r8d, r8d
0x18008d356  jz      short loc_18008D37F
0x18008d358  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18008d35d  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18008d362  mov     r8d, edi; nNumberOfBytesToWrite
0x18008d365  lea     rdx, asc_1800B2BE0; "\r\n"
0x18008d36c  mov     rcx, rbx; hFile
0x18008d36f  call    cs:__imp_WriteFile
0x18008d375  mov     r8d, [rsp+320h+cValues]; unsigned int
0x18008d37a  mov     r9d, [rsp+320h+cbMaxValueNameLen]; unsigned int
0x18008d37f  mov     eax, [rsp+320h+cbMaxValueLen]
0x18008d383  mov     rdx, [rsp+320h+hKey]; HKEY
0x18008d388  mov     [rsp+320h+lpcbMaxSubKeyLen], rbx; void *
0x18008d38d  mov     dword ptr [rsp+320h+lpOverlapped], eax; unsigned int
0x18008d391  call    ?WriteValuesForRegKey@CDataCollection@@AEAAJPEAUHKEY__@@KKKPEAX@Z; CDataCollection::WriteValuesForRegKey(HKEY__ *,ulong,ulong,ulong,void *)
0x18008d396  test    r14d, r14d
0x18008d399  jz      loc_18008D51A
0x18008d39f  mov     [rsp+320h+cchName], r12d
0x18008d3a4  lea     rbx, WPP_GLOBAL_Control
0x18008d3ab  mov     r14d, r12d
0x18008d3ae  cmp     r14d, [rsp+320h+cSubKeys]
0x18008d3b3  jnb     loc_18008D51A
0x18008d3b9  mov     rcx, [r15+10h]; hHandle
0x18008d3bd  xor     edx, edx; dwMilliseconds
0x18008d3bf  call    cs:__imp_WaitForSingleObject
0x18008d3c5  test    eax, eax
0x18008d3c7  jz      loc_18008D513
0x18008d3cd  mov     rcx, [rsp+320h+hKey]; hKey
0x18008d3d2  lea     r9, [rsp+320h+cchName]; lpcchName
0x18008d3d7  mov     [rsp+320h+lpcValues], r12; lpftLastWriteTime
0x18008d3dc  lea     r8, [rbp+220h+Name]; lpName
0x18008d3e0  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcchClass
0x18008d3e5  mov     edx, r14d; dwIndex
0x18008d3e8  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpClass
0x18008d3ed  mov     [rsp+320h+lpOverlapped], r12; lpReserved
0x18008d3f2  mov     [rsp+320h+cchName], 104h
0x18008d3fa  call    cs:__imp_RegEnumKeyExW
0x18008d400  test    eax, eax
0x18008d402  jz      short loc_18008D42B
0x18008d404  mov     rcx, cs:WPP_GLOBAL_Control
0x18008d40b  cmp     rcx, rbx
0x18008d40e  jz      short loc_18008D42B
0x18008d410  test    byte ptr [rcx+1Ch], 1
0x18008d414  jz      short loc_18008D42B
0x18008d416  mov     rcx, [rcx+10h]
0x18008d41a  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x18008d421  mov     edx, 24h ; '$'
0x18008d426  call    WPP_SF_
0x18008d42b  lea     rcx, [rbp+220h+var_278]; void *
0x18008d42f  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18008d434  lea     rax, [rbp+220h+Name]
0x18008d438  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18008d43c  inc     rdi
0x18008d43f  cmp     [rax+rdi*2], r12w
0x18008d444  jnz     short loc_18008D43C
0x18008d446  mov     rdx, [rbp+220h+var_290]
0x18008d44a  lea     rcx, [rbp+220h+var_278]
0x18008d44e  sub     rdx, [rbp+220h+lpBuffer]
0x18008d452  sar     rdx, 1
0x18008d455  inc     rdx
0x18008d458  add     rdx, rdi
0x18008d45b  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x18008d460  test    al, al
0x18008d462  jz      loc_18008D502
0x18008d468  mov     r8, [rbp+220h+var_290]
0x18008d46c  lea     rcx, [rbp+220h+var_278]
0x18008d470  mov     rdx, [rbp+220h+lpBuffer]
0x18008d474  sub     r8, rdx
0x18008d477  sar     r8, 1
0x18008d47a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x18008d47f  test    al, al
0x18008d481  jz      short loc_18008D502
0x18008d483  mov     edx, 5Ch ; '\'
0x18008d488  lea     rcx, [rbp+220h+var_278]
0x18008d48c  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x18008d491  test    al, al
0x18008d493  jz      short loc_18008D502
0x18008d495  mov     r8, rdi
0x18008d498  lea     rdx, [rbp+220h+Name]
0x18008d49c  lea     rcx, [rbp+220h+var_278]
0x18008d4a0  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x18008d4a5  test    al, al
0x18008d4a7  jz      short loc_18008D502
0x18008d4a9  mov     rdi, [rsi]
0x18008d4ac  lea     rdx, [rbp+220h+var_2A0]
0x18008d4b0  call    ??$_NewNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x18008d4b5  mov     rdx, [rbp+220h+var_2A0]
0x18008d4b9  test    rdx, rdx
0x18008d4bc  jz      short loc_18008D4D2
0x18008d4be  add     rdx, 10h
0x18008d4c2  lea     r8, [rbp+220h+var_278]
0x18008d4c6  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@?$allocator_traits@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAV31@@Z; utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18008d4cb  mov     r8b, 1
0x18008d4ce  test    al, al
0x18008d4d0  jnz     short loc_18008D4D5
0x18008d4d2  mov     r8b, r12b
0x18008d4d5  lea     rdx, [rbp+220h+var_2A0]
0x18008d4d9  call    ??$_NewNodeCommit@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>> &,bool)
0x18008d4de  test    rax, rax
0x18008d4e1  jz      short loc_18008D4F9
0x18008d4e3  mov     rcx, [rdi+8]
0x18008d4e7  mov     [rax+8], rcx
0x18008d4eb  mov     [rax], rdi
0x18008d4ee  mov     [rcx], rax
0x18008d4f1  mov     [rdi+8], rax
0x18008d4f5  inc     qword ptr [rsi+10h]
0x18008d4f9  lea     rcx, [rbp+220h+var_2A0]; void *
0x18008d4fd  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x18008d502  lea     rcx, [rbp+220h+var_278]; void *
0x18008d506  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008d50b  inc     r14d
0x18008d50e  jmp     loc_18008D3AE
0x18008d513  mov     edi, 801B8001h
0x18008d518  jmp     short loc_18008D51D
0x18008d51a  mov     edi, r12d
0x18008d51d  lea     rcx, [rbp+220h+lpBuffer]; void *
0x18008d521  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18008d526  lea     rcx, [rsp+320h+hKey]
0x18008d52b  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x18008d530  mov     eax, edi
0x18008d532  mov     rcx, [rbp+220h+var_40]
0x18008d539  xor     rcx, rsp; StackCookie
0x18008d53c  call    __security_check_cookie
0x18008d541  add     rsp, 2F0h
0x18008d548  pop     r15
0x18008d54a  pop     r14
0x18008d54c  pop     r12
0x18008d54e  pop     rdi
0x18008d54f  pop     rsi
0x18008d550  pop     rbx
0x18008d551  pop     rbp
0x18008d552  retn
```
