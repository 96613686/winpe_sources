# CWorkspace::SaveSSPInstalledAppsRegistry(HKEY__ *,void *)

- ea: `0x180036c9c`
- end: `0x180037083`
- name: `?SaveSSPInstalledAppsRegistry@CWorkspace@@QEAAJPEAUHKEY__@@PEAX@Z`
- size: `999`
- prototype: `int(CWorkspace *__hidden this, HKEY, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update`

## callers

- `0x180034ffc`

## callees

- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18001ead4`
- `0x180020a68`
- `0x180028ca0`
- `0x180028d04`
- `0x180036c9c`
- `0x18003add8`

## import_xrefs

- `ADVAPI32!RegCreateKeyTransactedW` at `0x180036df1`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180036efa`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180036df1`
- `ADVAPI32!RegCreateKeyTransactedW` at `0x180036efa`
- `ADVAPI32!RegCloseKey` at `0x180037017`
- `ADVAPI32!RegCloseKey` at `0x180037051`
- `ADVAPI32!RegCloseKey` at `0x180037061`
- `ADVAPI32!RegCloseKey` at `0x180037017`
- `ADVAPI32!RegCloseKey` at `0x180037051`
- `ADVAPI32!RegCloseKey` at `0x180037061`
- `ADVAPI32!RegSetValueExW` at `0x180036fa2`
- `ADVAPI32!RegSetValueExW` at `0x180036fa2`
- `KERNEL32!RegDeleteTreeW` at `0x180036d30`
- `KERNEL32!RegDeleteTreeW` at `0x180036d30`

## string_xrefs

- `0x180036d26`: `SSPInstalledApps`
- `0x180036de7`: `SSPInstalledApps`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CWorkspace::SaveSSPInstalledAppsRegistry(CWorkspace *this, HKEY a2, void *a3)
{
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // ebx
  unsigned int v8; // esi
  unsigned int v9; // eax
  __int64 v10; // r8
  unsigned int v11; // esi
  unsigned int v12; // eax
  char *v13; // rsi
  __int64 v14; // rax
  __int64 v15; // r14
  const WCHAR *v16; // rax
  unsigned int v17; // esi
  unsigned int v18; // eax
  unsigned int v19; // esi
  unsigned int v20; // eax
  DWORD dwDisposition; // [rsp+64h] [rbp-54h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v24[8]; // [rsp+70h] [rbp-48h] BYREF
  HKEY hKey[2]; // [rsp+78h] [rbp-40h] BYREF
  _BYTE v26[8]; // [rsp+88h] [rbp-30h] BYREF
  _BYTE v27[16]; // [rsp+90h] [rbp-28h] BYREF
  BOOL Data; // [rsp+D8h] [rbp+20h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  phkResult = 0;
  dwDisposition = 0;
  Data = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v7 = RegDeleteTreeW(a2, L"SSPInstalledApps");
  if ( (v7 & 0xFFFFFFFD) != 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v7 > 0 )
        v8 = (unsigned __int16)v7 | 0x80070000;
      else
        v8 = v7;
      v9 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 117, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v9, v8);
    }
    if ( v7 > 0 )
      v7 = (unsigned __int16)v7 | 0x80070000;
  }
  else
  {
    v7 = RegCreateKeyTransactedW(a2, L"SSPInstalledApps", 0, 0, 0, 0x2001Fu, 0, hKey, &dwDisposition, a3, 0);
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v7 > 0 )
          v11 = (unsigned __int16)v7 | 0x80070000;
        else
          v11 = v7;
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v12, v11);
      }
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
    else
    {
      v13 = (char *)this + 272;
      std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
        (char *)this + 272,
        v24,
        v10);
      while ( 1 )
      {
        v14 = std::vector<unsigned int>::begin(v13, v26);
        if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                                 v24,
                                 v14) )
        {
          v7 = 0;
          goto LABEL_52;
        }
        v15 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(v24);
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v15);
        v7 = RegCreateKeyTransactedW(hKey[0], v16, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0, a3, 0);
        if ( v7 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v7 > 0 )
              v17 = (unsigned __int16)v7 | 0x80070000;
            else
              v17 = v7;
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              119,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v18,
              v17);
          }
          if ( v7 > 0 )
            v7 = (unsigned __int16)v7 | 0x80070000;
          goto LABEL_52;
        }
        Data = *(_BYTE *)(v15 + 32) != 0;
        v7 = RegSetValueExW(phkResult, 0, 0, 4u, (const BYTE *)&Data, 4u);
        if ( v7 )
          break;
        RegCloseKey(phkResult);
        phkResult = 0;
        std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(
          v24,
          v27);
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        if ( v7 > 0 )
          v19 = (unsigned __int16)v7 | 0x80070000;
        else
          v19 = v7;
        v20 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 120, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v20, v19);
      }
      if ( v7 > 0 )
        v7 = (unsigned __int16)v7 | 0x80070000;
    }
  }
LABEL_52:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180036c9c  mov     rax, rsp
0x180036c9f  push    r12
0x180036ca1  push    r14
0x180036ca3  push    r15
0x180036ca5  sub     rsp, 0A0h
0x180036cac  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180036cb4  mov     [rax+8], rbx
0x180036cb8  mov     [rax+10h], rsi
0x180036cbc  mov     r15, r8
0x180036cbf  mov     rsi, rdx
0x180036cc2  mov     r14, rcx
0x180036cc5  mov     qword ptr [rax-40h], 0
0x180036ccd  mov     qword ptr [rax-50h], 0
0x180036cd5  mov     dword ptr [rax-54h], 0
0x180036cdc  mov     dword ptr [rax+20h], 0
0x180036ce3  lea     r12, WPP_GLOBAL_Control
0x180036cea  mov     rax, cs:WPP_GLOBAL_Control
0x180036cf1  cmp     rax, r12
0x180036cf4  jz      short loc_180036D26
0x180036cf6  test    byte ptr [rax+1Ch], 1
0x180036cfa  jz      short loc_180036D26
0x180036cfc  cmp     byte ptr [rax+19h], 4
0x180036d00  jb      short loc_180036D26
0x180036d02  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036d07  mov     edx, 74h ; 't'
0x180036d0c  mov     r9d, eax
0x180036d0f  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180036d16  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d1d  mov     rcx, [rcx+10h]
0x180036d21  call    WPP_SF_D
0x180036d26  lea     rdx, aSspinstalledap; "SSPInstalledApps"
0x180036d2d  mov     rcx, rsi; hKey
0x180036d30  call    cs:__imp_RegDeleteTreeW
0x180036d36  mov     ebx, eax
0x180036d38  test    eax, 0FFFFFFFDh
0x180036d3d  jz      short loc_180036DA6
0x180036d3f  mov     rax, cs:WPP_GLOBAL_Control
0x180036d46  cmp     rax, r12
0x180036d49  jz      short loc_180036D90
0x180036d4b  test    byte ptr [rax+1Ch], 8
0x180036d4f  jz      short loc_180036D90
0x180036d51  cmp     byte ptr [rax+19h], 2
0x180036d55  jb      short loc_180036D90
0x180036d57  test    ebx, ebx
0x180036d59  jg      short loc_180036D5F
0x180036d5b  mov     esi, ebx
0x180036d5d  jmp     short loc_180036D68
0x180036d5f  movzx   esi, bx
0x180036d62  or      esi, 80070000h
0x180036d68  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036d6d  mov     edx, 75h ; 'u'
0x180036d72  mov     [rsp+0B8h+dwOptions], esi
0x180036d76  mov     r9d, eax
0x180036d79  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180036d80  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d87  mov     rcx, [rcx+10h]
0x180036d8b  call    WPP_SF_Dd
0x180036d90  test    ebx, ebx
0x180036d92  jle     short loc_180036D9D
0x180036d94  movzx   ebx, bx
0x180036d97  or      ebx, 80070000h
0x180036d9d  mov     [rsp+0B8h+var_58], ebx
0x180036da1  jmp     loc_180037047
0x180036da6  mov     [rsp+0B8h+pExtendedParemeter], 0; pExtendedParemeter
0x180036daf  mov     [rsp+0B8h+hTransaction], r15; hTransaction
0x180036db4  lea     rax, [rsp+0B8h+dwDisposition]
0x180036db9  mov     [rsp+0B8h+lpdwDisposition], rax; lpdwDisposition
0x180036dbe  lea     rax, [rsp+0B8h+hKey]
0x180036dc3  mov     [rsp+0B8h+phkResult], rax; phkResult
0x180036dc8  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036dd1  mov     [rsp+0B8h+samDesired], 2001Fh; samDesired
0x180036dd9  mov     [rsp+0B8h+dwOptions], 0; dwOptions
0x180036de1  xor     r9d, r9d; lpClass
0x180036de4  xor     r8d, r8d; Reserved
0x180036de7  lea     rdx, aSspinstalledap; "SSPInstalledApps"
0x180036dee  mov     rcx, rsi; hKey
0x180036df1  call    cs:__imp_RegCreateKeyTransactedW
0x180036df7  mov     ebx, eax
0x180036df9  test    eax, eax
0x180036dfb  jz      short loc_180036E64
0x180036dfd  mov     rax, cs:WPP_GLOBAL_Control
0x180036e04  cmp     rax, r12
0x180036e07  jz      short loc_180036E4E
0x180036e09  test    byte ptr [rax+1Ch], 8
0x180036e0d  jz      short loc_180036E4E
0x180036e0f  cmp     byte ptr [rax+19h], 2
0x180036e13  jb      short loc_180036E4E
0x180036e15  test    ebx, ebx
0x180036e17  jg      short loc_180036E1D
0x180036e19  mov     esi, ebx
0x180036e1b  jmp     short loc_180036E26
0x180036e1d  movzx   esi, bx
0x180036e20  or      esi, 80070000h
0x180036e26  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036e2b  mov     edx, 76h ; 'v'
0x180036e30  mov     [rsp+0B8h+dwOptions], esi
0x180036e34  mov     r9d, eax
0x180036e37  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180036e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180036e45  mov     rcx, [rcx+10h]
0x180036e49  call    WPP_SF_Dd
0x180036e4e  test    ebx, ebx
0x180036e50  jle     short loc_180036E5B
0x180036e52  movzx   ebx, bx
0x180036e55  or      ebx, 80070000h
0x180036e5b  mov     [rsp+0B8h+var_58], ebx
0x180036e5f  jmp     loc_180037047
0x180036e64  lea     rsi, [r14+110h]
0x180036e6b  lea     rdx, [rsp+0B8h+var_48]
0x180036e70  mov     rcx, rsi
0x180036e73  call    ?begin@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(void)
0x180036e78  lea     rdx, [rsp+0B8h+var_30]
0x180036e80  mov     rcx, rsi
0x180036e83  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x180036e88  mov     rdx, rax
0x180036e8b  lea     rcx, [rsp+0B8h+var_48]
0x180036e90  call    ??9?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>> const &)
0x180036e95  test    al, al
0x180036e97  jz      loc_18003703D
0x180036e9d  lea     rcx, [rsp+0B8h+var_48]
0x180036ea2  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x180036ea7  mov     r14, rax
0x180036eaa  mov     rcx, rax
0x180036ead  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180036eb2  mov     [rsp+0B8h+pExtendedParemeter], 0; pExtendedParemeter
0x180036ebb  mov     [rsp+0B8h+hTransaction], r15; hTransaction
0x180036ec0  mov     [rsp+0B8h+lpdwDisposition], 0; lpdwDisposition
0x180036ec9  lea     rcx, [rsp+0B8h+var_50]
0x180036ece  mov     [rsp+0B8h+phkResult], rcx; phkResult
0x180036ed3  mov     [rsp+0B8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180036edc  mov     [rsp+0B8h+samDesired], 2001Fh; samDesired
0x180036ee4  mov     [rsp+0B8h+dwOptions], 0; dwOptions
0x180036eec  xor     r9d, r9d; lpClass
0x180036eef  xor     r8d, r8d; Reserved
0x180036ef2  mov     rdx, rax; lpSubKey
0x180036ef5  mov     rcx, [rsp+0B8h+hKey]; hKey
0x180036efa  call    cs:__imp_RegCreateKeyTransactedW
0x180036f00  mov     ebx, eax
0x180036f02  test    eax, eax
0x180036f04  jz      short loc_180036F6D
0x180036f06  mov     rax, cs:WPP_GLOBAL_Control
0x180036f0d  cmp     rax, r12
0x180036f10  jz      short loc_180036F57
0x180036f12  test    byte ptr [rax+1Ch], 8
0x180036f16  jz      short loc_180036F57
0x180036f18  cmp     byte ptr [rax+19h], 2
0x180036f1c  jb      short loc_180036F57
0x180036f1e  test    ebx, ebx
0x180036f20  jg      short loc_180036F26
0x180036f22  mov     esi, ebx
0x180036f24  jmp     short loc_180036F2F
0x180036f26  movzx   esi, bx
0x180036f29  or      esi, 80070000h
0x180036f2f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036f34  mov     edx, 77h ; 'w'
0x180036f39  mov     [rsp+0B8h+dwOptions], esi
0x180036f3d  mov     r9d, eax
0x180036f40  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180036f47  mov     rcx, cs:WPP_GLOBAL_Control
0x180036f4e  mov     rcx, [rcx+10h]
0x180036f52  call    WPP_SF_Dd
0x180036f57  test    ebx, ebx
0x180036f59  jle     short loc_180036F64
0x180036f5b  movzx   ebx, bx
0x180036f5e  or      ebx, 80070000h
0x180036f64  mov     [rsp+0B8h+var_58], ebx
0x180036f68  jmp     loc_180037047
0x180036f6d  xor     eax, eax
0x180036f6f  cmp     [r14+20h], al
0x180036f73  setnz   al
0x180036f76  mov     [rsp+0B8h+Data], eax
0x180036f7d  mov     [rsp+0B8h+samDesired], 4; cbData
0x180036f85  lea     rax, [rsp+0B8h+Data]
0x180036f8d  mov     qword ptr [rsp+0B8h+dwOptions], rax; lpData
0x180036f92  mov     r9d, 4; dwType
0x180036f98  xor     r8d, r8d; Reserved
0x180036f9b  xor     edx, edx; lpValueName
0x180036f9d  mov     rcx, [rsp+0B8h+var_50]; hKey
0x180036fa2  call    cs:__imp_RegSetValueExW
0x180036fa8  mov     ebx, eax
0x180036faa  test    eax, eax
0x180036fac  jz      short loc_180037012
0x180036fae  mov     rax, cs:WPP_GLOBAL_Control
0x180036fb5  cmp     rax, r12
0x180036fb8  jz      short loc_180036FFF
0x180036fba  test    byte ptr [rax+1Ch], 8
0x180036fbe  jz      short loc_180036FFF
0x180036fc0  cmp     byte ptr [rax+19h], 2
0x180036fc4  jb      short loc_180036FFF
0x180036fc6  test    ebx, ebx
0x180036fc8  jg      short loc_180036FCE
0x180036fca  mov     esi, ebx
0x180036fcc  jmp     short loc_180036FD7
0x180036fce  movzx   esi, bx
0x180036fd1  or      esi, 80070000h
0x180036fd7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180036fdc  mov     edx, 78h ; 'x'
0x180036fe1  mov     [rsp+0B8h+dwOptions], esi
0x180036fe5  mov     r9d, eax
0x180036fe8  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180036fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180036ff6  mov     rcx, [rcx+10h]
0x180036ffa  call    WPP_SF_Dd
0x180036fff  test    ebx, ebx
0x180037001  jle     short loc_18003700C
0x180037003  movzx   ebx, bx
0x180037006  or      ebx, 80070000h
0x18003700c  mov     [rsp+0B8h+var_58], ebx
0x180037010  jmp     short loc_180037047
0x180037012  mov     rcx, [rsp+0B8h+var_50]; hKey
0x180037017  call    cs:__imp_RegCloseKey
0x18003701d  mov     [rsp+0B8h+var_50], 0
0x180037026  lea     rdx, [rsp+0B8h+var_28]
0x18003702e  lea     rcx, [rsp+0B8h+var_48]
0x180037033  call    ??E?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VTS_WORKSPACE_DOWNLOAD_INFO@@@std@@@std@@@std@@@std@@QEAA?AV01@H@Z; std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,TS_WORKSPACE_DOWNLOAD_INFO>>>>::operator++(int)
0x180037038  jmp     loc_180036E78
0x18003703d  xor     ebx, ebx
0x18003703f  jmp     short loc_180037047
0x180037041  jmp     short $+2
0x180037043  mov     ebx, [rsp+0B8h+var_58]
0x180037047  mov     rcx, [rsp+0B8h+var_50]; hKey
0x18003704c  test    rcx, rcx
0x18003704f  jz      short loc_180037057
0x180037051  call    cs:__imp_RegCloseKey
0x180037057  mov     rcx, [rsp+0B8h+hKey]; hKey
0x18003705c  test    rcx, rcx
0x18003705f  jz      short loc_180037067
0x180037061  call    cs:__imp_RegCloseKey
0x180037067  mov     eax, ebx
0x180037069  lea     r11, [rsp+0B8h+var_18]
0x180037071  mov     rbx, [r11+20h]
0x180037075  mov     rsi, [r11+28h]
0x180037079  mov     rsp, r11
0x18003707c  pop     r15
0x18003707e  pop     r14
0x180037080  pop     r12
0x180037082  retn
```
