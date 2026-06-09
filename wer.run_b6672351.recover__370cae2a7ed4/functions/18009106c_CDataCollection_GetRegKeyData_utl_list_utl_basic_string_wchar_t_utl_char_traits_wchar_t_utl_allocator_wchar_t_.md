# CDataCollection::GetRegKeyData(utl::list<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>> &,int,void *)

- ea: `0x18009106c`
- end: `0x1800914f6`
- name: `?GetRegKeyData@CDataCollection@@AEAAJAEAV?$list@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@HPEAX@Z`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180051270`

## callees

- `0x180004c64`
- `0x18000cf50`
- `0x18000d40c`
- `0x18000db80`
- `0x18000ed68`
- `0x1800172c0`
- `0x18001c368`
- `0x18001cb20`
- `0x18001e0d0`
- `0x180020190`
- `0x180020680`
- `0x180025560`
- `0x18002d180`
- `0x180039784`
- `0x180053300`
- `0x18008ee54`
- `0x18008ee8c`
- `0x18008eec8`
- `0x18009106c`
- `0x1800a00f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091275`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091275`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091355`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180091355`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180091396`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180091396`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180091265`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180091265`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800911e6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180091210`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800912ff`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800911e6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180091210`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800912ff`

## pseudocode

```c
__int64 __fastcall CDataCollection::GetRegKeyData(__int64 a1, __int64 **a2, int a3, void *a4)
{
  unsigned int v8; // edi
  _QWORD *v9; // rcx
  __int64 v10; // rax
  wchar_t *v11; // rcx
  int Key; // eax
  CDataCollection *v13; // rcx
  DWORD LastError; // eax
  DWORD v15; // r8d
  DWORD v16; // r9d
  DWORD i; // r14d
  __int64 v18; // rdi
  __int64 v19; // rcx
  __int64 *v20; // rdi
  __int64 v21; // rcx
  __int64 v22; // r8
  char v23; // al
  __int64 **v24; // rax
  __int64 *v25; // rcx
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v34; // [rsp+80h] [rbp-80h] BYREF
  LPCVOID lpBuffer[4]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v36[40]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[264]; // [rsp+D0h] [rbp-30h] BYREF

  hKey = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(lpBuffer);
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
  else if ( *a2 == (__int64 *)a2 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids, 2147500037LL);
    v8 = -2147467259;
  }
  else
  {
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(lpBuffer, *a2 + 2);
    v9 = (_QWORD *)(*a2)[1];
    v10 = **a2;
    *v9 = v10;
    *(_QWORD *)(v10 + 8) = v9;
    utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>();
    v11 = (wchar_t *)lpBuffer[0];
    a2[2] = (__int64 *)((char *)a2[2] - 1);
    Key = CRegSetting::GetKey(v11);
    v8 = Key;
    if ( Key >= 0 )
    {
      WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
      WriteFile(a4, lpBuffer[0], 2 * (((char *)lpBuffer[1] - (char *)lpBuffer[0]) >> 1), &NumberOfBytesWritten, 0);
      if ( RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0) )
      {
        LastError = GetLastError();
        v8 = ERROR_HR_FROM_WIN32(LastError);
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids);
      }
      else
      {
        v15 = cValues;
        v16 = cbMaxValueNameLen + 1;
        if ( cbMaxValueNameLen + 1 < 0xB )
          v16 = 11;
        cbMaxValueNameLen = v16;
        if ( cValues )
        {
          WriteFile(a4, L"\r\n", 4u, &NumberOfBytesWritten, 0);
          v15 = cValues;
          v16 = cbMaxValueNameLen;
        }
        CDataCollection::WriteValuesForRegKey(v13, hKey, v15, v16, cbMaxValueLen, a4);
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
            utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v36);
            v18 = -1;
            do
              ++v18;
            while ( Name[v18] );
            if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(v36)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                    v36,
                                    (void *)lpBuffer[0])
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                                    v36,
                                    92)
              && (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                    v36,
                                    Name) )
            {
              v20 = *a2;
              utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                v19,
                &v34);
              if ( !v34
                || (v23 = utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(
                            v21,
                            v34 + 16,
                            v36),
                    LOBYTE(v22) = 1,
                    !v23) )
              {
                LOBYTE(v22) = 0;
              }
              v24 = (__int64 **)utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(
                                  v21,
                                  &v34,
                                  v22);
              if ( v24 )
              {
                v25 = (__int64 *)v20[1];
                v24[1] = v25;
                *v24 = v20;
                *v25 = (__int64)v24;
                v20[1] = (__int64)v24;
                a2[2] = (__int64 *)((char *)a2[2] + 1);
              }
              utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(&v34);
            }
            utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v36);
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
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpBuffer);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  return v8;
}

```

## disassembly

```asm
0x18009106c  push    rbp
0x18009106e  push    rbx
0x18009106f  push    rsi
0x180091070  push    rdi
0x180091071  push    r12
0x180091073  push    r14
0x180091075  push    r15
0x180091077  lea     rbp, [rsp-1F0h]
0x18009107f  sub     rsp, 2F0h
0x180091086  mov     rax, cs:__security_cookie
0x18009108d  xor     rax, rsp
0x180091090  mov     [rbp+220h+var_40], rax
0x180091097  mov     r15, rcx
0x18009109a  xor     r12d, r12d
0x18009109d  lea     rcx, [rbp+220h+lpBuffer]; void *
0x1800910a1  mov     [rsp+320h+hKey], r12
0x1800910a6  mov     rbx, r9
0x1800910a9  mov     r14d, r8d
0x1800910ac  mov     rsi, rdx
0x1800910af  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800910b4  mov     [rsp+320h+cValues], r12d
0x1800910b9  mov     [rsp+320h+cbMaxValueNameLen], r12d
0x1800910be  mov     [rsp+320h+cbMaxValueLen], r12d
0x1800910c3  mov     [rsp+320h+cSubKeys], r12d
0x1800910c8  mov     [rsp+320h+NumberOfBytesWritten], r12d
0x1800910cd  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800910d1  jnz     short loc_18009110B
0x1800910d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800910da  lea     rbx, WPP_GLOBAL_Control
0x1800910e1  cmp     rcx, rbx
0x1800910e4  jz      short loc_180091101
0x1800910e6  test    byte ptr [rcx+1Ch], 1
0x1800910ea  jz      short loc_180091101
0x1800910ec  mov     rcx, [rcx+10h]
0x1800910f0  lea     edx, [r12+20h]
0x1800910f5  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800910fc  call    WPP_SF_
0x180091101  mov     edi, 80070057h
0x180091106  jmp     loc_1800914BF
0x18009110b  mov     rdx, [rsi]
0x18009110e  cmp     rdx, rsi
0x180091111  jnz     short loc_180091151
0x180091113  mov     rcx, cs:WPP_GLOBAL_Control
0x18009111a  lea     rbx, WPP_GLOBAL_Control
0x180091121  cmp     rcx, rbx
0x180091124  jz      short loc_180091147
0x180091126  test    byte ptr [rcx+1Ch], 1
0x18009112a  jz      short loc_180091147
0x18009112c  mov     rcx, [rcx+10h]
0x180091130  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x180091137  mov     edx, 21h ; '!'
0x18009113c  mov     r9d, 80004005h
0x180091142  call    WPP_SF_d
0x180091147  mov     edi, 80004005h
0x18009114c  jmp     loc_1800914BF
0x180091151  add     rdx, 10h
0x180091155  lea     rcx, [rbp+220h+lpBuffer]
0x180091159  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18009115e  mov     rdx, [rsi]
0x180091161  mov     rcx, [rdx+8]
0x180091165  mov     rax, [rdx]
0x180091168  mov     [rcx], rax
0x18009116b  mov     [rax+8], rcx
0x18009116f  call    ??$_DeleteNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAXPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_DeleteNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> *)
0x180091174  mov     rcx, [rbp+220h+lpBuffer]; Str
0x180091178  lea     r8, [rsp+320h+hKey]
0x18009117d  dec     qword ptr [rsi+10h]
0x180091181  call    ?GetKey@CRegSetting@@SAJPEB_WKPEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@@Z; CRegSetting::GetKey(wchar_t const *,ulong,tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> *)
0x180091186  mov     edi, eax
0x180091188  test    eax, eax
0x18009118a  jns     short loc_1800911CA
0x18009118c  mov     rcx, cs:WPP_GLOBAL_Control
0x180091193  lea     rbx, WPP_GLOBAL_Control
0x18009119a  cmp     rcx, rbx
0x18009119d  jz      loc_1800914BF
0x1800911a3  test    byte ptr [rcx+1Ch], 1
0x1800911a7  jz      loc_1800914BF
0x1800911ad  mov     rcx, [rcx+10h]
0x1800911b1  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800911b8  mov     edx, 22h ; '"'
0x1800911bd  mov     r9d, eax
0x1800911c0  call    WPP_SF_d
0x1800911c5  jmp     loc_1800914BF
0x1800911ca  mov     edi, 4
0x1800911cf  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x1800911d4  mov     r8d, edi; nNumberOfBytesToWrite
0x1800911d7  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800911dc  lea     rdx, asc_1800B7AF0; "\r\n"
0x1800911e3  mov     rcx, rbx; hFile
0x1800911e6  call    cs:__imp_WriteFile
0x1800911ed  nop     dword ptr [rax+rax+00h]
0x1800911f2  mov     r8, [rbp+220h+var_290]
0x1800911f6  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800911fb  mov     rdx, [rbp+220h+lpBuffer]; lpBuffer
0x1800911ff  mov     rcx, rbx; hFile
0x180091202  sub     r8, rdx
0x180091205  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x18009120a  sar     r8, 1
0x18009120d  add     r8d, r8d; nNumberOfBytesToWrite
0x180091210  call    cs:__imp_WriteFile
0x180091217  nop     dword ptr [rax+rax+00h]
0x18009121c  mov     rcx, [rsp+320h+hKey]; hKey
0x180091221  lea     rax, [rsp+320h+cbMaxValueLen]
0x180091226  mov     [rsp+320h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18009122b  xor     r9d, r9d; lpReserved
0x18009122e  mov     [rsp+320h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180091233  xor     r8d, r8d; lpcchClass
0x180091236  mov     [rsp+320h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x18009123b  xor     edx, edx; lpClass
0x18009123d  lea     rax, [rsp+320h+cbMaxValueNameLen]
0x180091242  mov     [rsp+320h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180091247  lea     rax, [rsp+320h+cValues]
0x18009124c  mov     [rsp+320h+lpcValues], rax; lpcValues
0x180091251  lea     rax, [rsp+320h+cSubKeys]
0x180091256  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18009125b  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x180091260  mov     [rsp+320h+lpOverlapped], rax; lpcSubKeys
0x180091265  call    cs:__imp_RegQueryInfoKeyW
0x18009126c  nop     dword ptr [rax+rax+00h]
0x180091271  test    eax, eax
0x180091273  jz      short loc_1800912C5
0x180091275  call    cs:__imp_GetLastError
0x18009127c  nop     dword ptr [rax+rax+00h]
0x180091281  mov     ecx, eax; unsigned int
0x180091283  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180091288  mov     edi, eax
0x18009128a  mov     rcx, cs:WPP_GLOBAL_Control
0x180091291  lea     rbx, WPP_GLOBAL_Control
0x180091298  cmp     rcx, rbx
0x18009129b  jz      loc_1800914BF
0x1800912a1  test    byte ptr [rcx+1Ch], 1
0x1800912a5  jz      loc_1800914BF
0x1800912ab  mov     rcx, [rcx+10h]
0x1800912af  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800912b6  mov     edx, 23h ; '#'
0x1800912bb  call    WPP_SF_
0x1800912c0  jmp     loc_1800914BF
0x1800912c5  mov     r9d, [rsp+320h+cbMaxValueNameLen]
0x1800912ca  mov     eax, 0Bh
0x1800912cf  mov     r8d, [rsp+320h+cValues]
0x1800912d4  inc     r9d
0x1800912d7  cmp     r9d, eax
0x1800912da  cmovb   r9d, eax
0x1800912de  mov     [rsp+320h+cbMaxValueNameLen], r9d
0x1800912e3  test    r8d, r8d
0x1800912e6  jz      short loc_180091315
0x1800912e8  lea     r9, [rsp+320h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800912ed  mov     [rsp+320h+lpOverlapped], r12; lpOverlapped
0x1800912f2  mov     r8d, edi; nNumberOfBytesToWrite
0x1800912f5  lea     rdx, asc_1800B7AF0; "\r\n"
0x1800912fc  mov     rcx, rbx; hFile
0x1800912ff  call    cs:__imp_WriteFile
0x180091306  nop     dword ptr [rax+rax+00h]
0x18009130b  mov     r8d, [rsp+320h+cValues]; unsigned int
0x180091310  mov     r9d, [rsp+320h+cbMaxValueNameLen]; unsigned int
0x180091315  mov     eax, [rsp+320h+cbMaxValueLen]
0x180091319  mov     rdx, [rsp+320h+hKey]; HKEY
0x18009131e  mov     [rsp+320h+lpcbMaxSubKeyLen], rbx; void *
0x180091323  mov     dword ptr [rsp+320h+lpOverlapped], eax; unsigned int
0x180091327  call    ?WriteValuesForRegKey@CDataCollection@@AEAAJPEAUHKEY__@@KKKPEAX@Z; CDataCollection::WriteValuesForRegKey(HKEY__ *,ulong,ulong,ulong,void *)
0x18009132c  test    r14d, r14d
0x18009132f  jz      loc_1800914BC
0x180091335  mov     [rsp+320h+cchName], r12d
0x18009133a  lea     rbx, WPP_GLOBAL_Control
0x180091341  mov     r14d, r12d
0x180091344  cmp     r14d, [rsp+320h+cSubKeys]
0x180091349  jnb     loc_1800914BC
0x18009134f  mov     rcx, [r15+10h]; hHandle
0x180091353  xor     edx, edx; dwMilliseconds
0x180091355  call    cs:__imp_WaitForSingleObject
0x18009135c  nop     dword ptr [rax+rax+00h]
0x180091361  test    eax, eax
0x180091363  jz      loc_1800914B5
0x180091369  mov     rcx, [rsp+320h+hKey]; hKey
0x18009136e  lea     r9, [rsp+320h+cchName]; lpcchName
0x180091373  mov     [rsp+320h+lpcValues], r12; lpftLastWriteTime
0x180091378  lea     r8, [rbp+220h+Name]; lpName
0x18009137c  mov     [rsp+320h+lpcbMaxClassLen], r12; lpcchClass
0x180091381  mov     edx, r14d; dwIndex
0x180091384  mov     [rsp+320h+lpcbMaxSubKeyLen], r12; lpClass
0x180091389  mov     [rsp+320h+lpOverlapped], r12; lpReserved
0x18009138e  mov     [rsp+320h+cchName], 104h
0x180091396  call    cs:__imp_RegEnumKeyExW
0x18009139d  nop     dword ptr [rax+rax+00h]
0x1800913a2  test    eax, eax
0x1800913a4  jz      short loc_1800913CD
0x1800913a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800913ad  cmp     rcx, rbx
0x1800913b0  jz      short loc_1800913CD
0x1800913b2  test    byte ptr [rcx+1Ch], 1
0x1800913b6  jz      short loc_1800913CD
0x1800913b8  mov     rcx, [rcx+10h]
0x1800913bc  lea     r8, WPP_f5cfe0c545c835cc3022fec6aeec9c25_Traceguids
0x1800913c3  mov     edx, 24h ; '$'
0x1800913c8  call    WPP_SF_
0x1800913cd  lea     rcx, [rbp+220h+var_278]; void *
0x1800913d1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800913d6  lea     rax, [rbp+220h+Name]
0x1800913da  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800913de  inc     rdi
0x1800913e1  cmp     [rax+rdi*2], r12w
0x1800913e6  jnz     short loc_1800913DE
0x1800913e8  mov     rdx, [rbp+220h+var_290]
0x1800913ec  lea     rcx, [rbp+220h+var_278]
0x1800913f0  sub     rdx, [rbp+220h+lpBuffer]
0x1800913f4  sar     rdx, 1
0x1800913f7  inc     rdx
0x1800913fa  add     rdx, rdi
0x1800913fd  call    ?reserve@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::reserve(unsigned __int64)
0x180091402  test    al, al
0x180091404  jz      loc_1800914A4
0x18009140a  mov     r8, [rbp+220h+var_290]
0x18009140e  lea     rcx, [rbp+220h+var_278]
0x180091412  mov     rdx, [rbp+220h+lpBuffer]
0x180091416  sub     r8, rdx
0x180091419  sar     r8, 1
0x18009141c  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180091421  test    al, al
0x180091423  jz      short loc_1800914A4
0x180091425  mov     edx, 5Ch ; '\'
0x18009142a  lea     rcx, [rbp+220h+var_278]
0x18009142e  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180091433  test    al, al
0x180091435  jz      short loc_1800914A4
0x180091437  mov     r8, rdi
0x18009143a  lea     rdx, [rbp+220h+Name]
0x18009143e  lea     rcx, [rbp+220h+var_278]
0x180091442  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180091447  test    al, al
0x180091449  jz      short loc_1800914A4
0x18009144b  mov     rdi, [rsi]
0x18009144e  lea     rdx, [rbp+220h+var_2A0]
0x180091452  call    ??$_NewNode@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAA?AU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@XZ; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNode<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(void)
0x180091457  mov     rdx, [rbp+220h+var_2A0]
0x18009145b  test    rdx, rdx
0x18009145e  jz      short loc_180091474
0x180091460  add     rdx, 10h
0x180091464  lea     r8, [rbp+220h+var_278]
0x180091468  call    ??$construct@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V12@@?$allocator_traits@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@SA_NAEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@1@$$QEAV31@@Z; utl::allocator_traits<utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::construct<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>(utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>> &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x18009146d  mov     r8b, 1
0x180091470  test    al, al
0x180091472  jnz     short loc_180091477
0x180091474  mov     r8b, r12b
0x180091477  lea     rdx, [rbp+220h+var_2A0]
0x18009147b  call    ??$_NewNodeCommit@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@?$_ContainerBase@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@2@@utl@@IEAAPEAU?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@1@AEAU?$_UninitializedAllocation@V?$allocator@U?$_DlistNode@V?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@utl@@@utl@@@1@_N@Z; utl::_ContainerBase<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>,utl::allocator<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>::_NewNodeCommit<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>(utl::_UninitializedAllocation<utl::allocator<utl::_DlistNode<utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>>>> &,bool)
0x180091480  test    rax, rax
0x180091483  jz      short loc_18009149B
0x180091485  mov     rcx, [rdi+8]
0x180091489  mov     [rax+8], rcx
0x18009148d  mov     [rax], rdi
0x180091490  mov     [rcx], rax
0x180091493  mov     [rdi+8], rax
0x180091497  inc     qword ptr [rsi+10h]
0x18009149b  lea     rcx, [rbp+220h+var_2A0]; void *
0x18009149f  call    ??1?$unique_ptr@$$BY0A@PEAVCZipReadStream@@U?$default_delete@$$BY0A@PEAVCZipReadStream@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>::~unique_ptr<CZipReadStream * [0],utl::default_delete<CZipReadStream * [0]>>(void)
0x1800914a4  lea     rcx, [rbp+220h+var_278]; void *
0x1800914a8  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800914ad  inc     r14d
0x1800914b0  jmp     loc_180091344
0x1800914b5  mov     edi, 801B8001h
0x1800914ba  jmp     short loc_1800914BF
0x1800914bc  mov     edi, r12d
0x1800914bf  lea     rcx, [rbp+220h+lpBuffer]; void *
0x1800914c3  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800914c8  lea     rcx, [rsp+320h+hKey]
0x1800914cd  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x1800914d2  mov     eax, edi
0x1800914d4  mov     rcx, [rbp+220h+var_40]
0x1800914db  xor     rcx, rsp; StackCookie
0x1800914de  call    __security_check_cookie
0x1800914e3  add     rsp, 2F0h
0x1800914ea  pop     r15
0x1800914ec  pop     r14
0x1800914ee  pop     r12
0x1800914f0  pop     rdi
0x1800914f1  pop     rsi
0x1800914f2  pop     rbx
0x1800914f3  pop     rbp
0x1800914f4  retn
```
