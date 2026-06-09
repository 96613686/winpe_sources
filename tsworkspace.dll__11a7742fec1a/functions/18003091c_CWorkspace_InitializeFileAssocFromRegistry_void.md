# CWorkspace::InitializeFileAssocFromRegistry(void)

- ea: `0x18003091c`
- end: `0x180030dbe`
- name: `?InitializeFileAssocFromRegistry@CWorkspace@@IEAAJXZ`
- size: `1186`
- prototype: `__int64 __fastcall(CWorkspace *__hidden this)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030dc4`

## callees

- `0x180005500`
- `0x1800055d0`
- `0x18000b1d8`
- `0x18000c3a0`
- `0x18000d8d4`
- `0x18000ec54`
- `0x18000ec94`
- `0x18000ece0`
- `0x18000fed8`
- `0x18001e41c`
- `0x18001e610`
- `0x18001ead4`
- `0x180020a68`
- `0x180025950`
- `0x1800277e4`
- `0x18002847c`
- `0x180028ca0`
- `0x180028cb0`
- `0x18003091c`
- `0x18003add8`
- `0x18003cb1c`
- `0x180053c00`
- `0x18005417c`
- `0x18009a520`
- `0x1800a3010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180030d7f`
- `ADVAPI32!RegCloseKey` at `0x180030d7f`
- `ADVAPI32!RegEnumKeyExW` at `0x180030b45`
- `ADVAPI32!RegEnumKeyExW` at `0x180030b45`
- `ADVAPI32!RegOpenKeyExW` at `0x180030a20`
- `ADVAPI32!RegOpenKeyExW` at `0x180030a20`

## string_xrefs

- `0x180030c9b`: `CWorkspaceFileAssociation::CreateInstance failed`
- `0x180030d1b`: `CWorkspaceFileAssociation::InitializeFromRegistry failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CWorkspace::InitializeFileAssocFromRegistry(CWorkspace *this)
{
  signed int v2; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  char *v4; // r15
  __int64 v5; // rax
  __int64 v6; // rax
  const WCHAR *v7; // rax
  LSTATUS v8; // esi
  __int64 v9; // r8
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  DWORD v13; // r14d
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rax
  const unsigned __int16 *v21; // rax
  unsigned int v22; // eax
  LPWSTR lpClass; // [rsp+28h] [rbp-300h]
  struct CWorkspaceFileAssociation *v25; // [rsp+48h] [rbp-2E0h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-2D8h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-2D0h] BYREF
  DWORD v28; // [rsp+60h] [rbp-2C8h]
  _BYTE v29[8]; // [rsp+68h] [rbp-2C0h] BYREF
  _BYTE v30[16]; // [rsp+70h] [rbp-2B8h] BYREF
  __int64 v31; // [rsp+80h] [rbp-2A8h]
  _BYTE v32[32]; // [rsp+88h] [rbp-2A0h] BYREF
  _BYTE v33[40]; // [rsp+A8h] [rbp-280h] BYREF
  WCHAR Name[268]; // [rsp+D0h] [rbp-258h] BYREF

  v31 = -2;
  hKey = 0;
  std::set<std::wstring>::set<std::wstring>(v30);
  v25 = 0;
  cchName = 260;
  v2 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      107,
      WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
      CurrentThreadActivityIdPrefix);
  }
  v4 = (char *)this + 744;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this + 93) + 24LL))((char *)this + 744);
  v5 = std::operator+<unsigned short>(v33, (char *)this + 488, L"\\");
  v6 = std::operator+<unsigned short>(v32, v5, L"ProgIds");
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v6);
  v8 = RegOpenKeyExW(HKEY_CURRENT_USER, v7, 0, 0x20019u, &hKey);
  std::wstring::~wstring(v32);
  std::wstring::~wstring(v33);
  if ( v8 == 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v10 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v10);
    }
  }
  else if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      if ( v8 > 0 )
        v11 = (unsigned __int16)v8 | 0x80070000;
      else
        v11 = v8;
      v12 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 109, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids, v12, v11);
    }
    if ( v8 > 0 )
      v2 = (unsigned __int16)v8 | 0x80070000;
    else
      v2 = v8;
  }
  else
  {
    v13 = 0;
    v28 = 0;
    while ( v8 != 259 )
    {
      Name[0] = 0;
      cchName = 260;
      v14 = RegEnumKeyExW(hKey, v13, Name, &cchName, 0, 0, 0, 0);
      v8 = v14;
      if ( v14 )
      {
        if ( v14 != 259 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            if ( v14 > 0 )
              v15 = (unsigned __int16)v14 | 0x80070000;
            else
              v15 = v14;
            v16 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
              v16,
              v15);
          }
          if ( v8 > 0 )
            v2 = (unsigned __int16)v8 | 0x80070000;
          else
            v2 = v8;
          goto LABEL_53;
        }
      }
      else
      {
        v17 = std::wstring::wstring(v33, Name);
        std::set<std::wstring>::insert(v30, v32, v17);
        std::wstring::~wstring(v33);
      }
      v28 = ++v13;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(
      v30,
      v29,
      v9);
    while ( 1 )
    {
      v18 = std::vector<unsigned int>::begin(v30, v32);
      if ( !(unsigned __int8)std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(
                               v29,
                               v18) )
      {
        v2 = 0;
        goto LABEL_53;
      }
      if ( v25 )
      {
        TCntPtr<CConfigManager>::SafeRelease(&v25);
        v25 = 0;
        TCntPtr<CConfigManager>::SafeAddRef(&v25);
      }
      v2 = CWorkspaceFileAssociation::CreateInstance(&v25);
      if ( v2 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          LODWORD(lpClass) = v2;
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
            v19,
            (__int64)"CWorkspaceFileAssociation::CreateInstance failed",
            lpClass);
        }
        goto LABEL_53;
      }
      v20 = std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(v29);
      v21 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
      v2 = CWorkspaceFileAssociation::InitializeFromRegistry(v25, hKey, v21);
      if ( v2 < 0 )
        break;
      (*(void (__fastcall **)(char *, struct CWorkspaceFileAssociation *))(*(_QWORD *)v4 + 8LL))(v4, v25);
      std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator++(v29);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v22 = RdpWppGetCurrentThreadActivityIdPrefix();
      LODWORD(lpClass) = v2;
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        112,
        (unsigned int)WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids,
        v22,
        (__int64)"CWorkspaceFileAssociation::InitializeFromRegistry failed",
        lpClass);
    }
  }
LABEL_53:
  if ( hKey )
    RegCloseKey(hKey);
  ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(&v25);
  std::set<std::wstring>::~set<std::wstring>(v30);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003091c  push    rbx
0x18003091e  push    rsi
0x18003091f  push    rdi
0x180030920  push    r12
0x180030922  push    r14
0x180030924  push    r15
0x180030926  sub     rsp, 2F8h
0x18003092d  mov     [rsp+328h+var_2A8], 0FFFFFFFFFFFFFFFEh
0x180030939  mov     rax, cs:__security_cookie
0x180030940  xor     rax, rsp
0x180030943  mov     [rsp+328h+var_40], rax
0x18003094b  mov     rsi, rcx
0x18003094e  xor     edi, edi
0x180030950  mov     [rsp+328h+hKey], rdi
0x180030955  lea     rcx, [rsp+328h+var_2B8]
0x18003095a  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x18003095f  nop
0x180030960  mov     [rsp+328h+var_2E0], rdi
0x180030965  mov     [rsp+328h+cchName], 104h
0x18003096d  lea     r12, WPP_GLOBAL_Control
0x180030974  mov     rax, cs:WPP_GLOBAL_Control
0x18003097b  lea     ebx, [rdi+1]
0x18003097e  cmp     rax, r12
0x180030981  jz      short loc_1800309B1
0x180030983  test    [rax+1Ch], bl
0x180030986  jz      short loc_1800309B1
0x180030988  cmp     byte ptr [rax+19h], 4
0x18003098c  jb      short loc_1800309B1
0x18003098e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030993  lea     edx, [rdi+6Bh]
0x180030996  mov     r9d, eax
0x180030999  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x1800309a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800309a7  mov     rcx, [rcx+10h]
0x1800309ab  call    WPP_SF_D
0x1800309b0  nop
0x1800309b1  lea     r15, [rsi+2E8h]
0x1800309b8  mov     rax, [r15]
0x1800309bb  mov     rcx, r15
0x1800309be  mov     rax, [rax+18h]
0x1800309c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800309c7  lea     rdx, [rsi+1E8h]
0x1800309ce  lea     r8, SubStr; "\\"
0x1800309d5  lea     rcx, [rsp+328h+var_280]
0x1800309dd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@PEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const *)
0x1800309e2  nop
0x1800309e3  lea     r8, aProgids; "ProgIds"
0x1800309ea  mov     rdx, rax
0x1800309ed  lea     rcx, [rsp+328h+var_2A0]
0x1800309f5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@PEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const *)
0x1800309fa  nop
0x1800309fb  mov     rcx, rax
0x1800309fe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030a03  lea     rcx, [rsp+328h+hKey]
0x180030a08  mov     [rsp+328h+phkResult], rcx; phkResult
0x180030a0d  mov     r9d, 20019h; samDesired
0x180030a13  xor     r8d, r8d; ulOptions
0x180030a16  mov     rdx, rax; lpSubKey
0x180030a19  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180030a20  call    cs:__imp_RegOpenKeyExW
0x180030a26  mov     esi, eax
0x180030a28  lea     rcx, [rsp+328h+var_2A0]; void *
0x180030a30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030a35  nop
0x180030a36  lea     rcx, [rsp+328h+var_280]; void *
0x180030a3e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030a43  cmp     esi, 2
0x180030a46  jnz     short loc_180030A8A
0x180030a48  mov     rax, cs:WPP_GLOBAL_Control
0x180030a4f  cmp     rax, r12
0x180030a52  jz      short loc_180030A81
0x180030a54  test    [rax+1Ch], bl
0x180030a57  jz      short loc_180030A81
0x180030a59  cmp     [rax+19h], sil
0x180030a5d  jb      short loc_180030A81
0x180030a5f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030a64  lea     edx, [rsi+6Ah]
0x180030a67  mov     r9d, eax
0x180030a6a  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180030a78  mov     rcx, [rcx+10h]
0x180030a7c  call    WPP_SF_D
0x180030a81  mov     [rsp+328h+var_2E8], ebx
0x180030a85  jmp     loc_180030D75
0x180030a8a  test    esi, esi
0x180030a8c  jz      short loc_180030AF9
0x180030a8e  mov     rax, cs:WPP_GLOBAL_Control
0x180030a95  cmp     rax, r12
0x180030a98  jz      short loc_180030ADF
0x180030a9a  test    byte ptr [rax+1Ch], 8
0x180030a9e  jz      short loc_180030ADF
0x180030aa0  cmp     byte ptr [rax+19h], 2
0x180030aa4  jb      short loc_180030ADF
0x180030aa6  test    esi, esi
0x180030aa8  jg      short loc_180030AAE
0x180030aaa  mov     ebx, esi
0x180030aac  jmp     short loc_180030AB7
0x180030aae  movzx   ebx, si
0x180030ab1  or      ebx, 80070000h
0x180030ab7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030abc  mov     edx, 6Dh ; 'm'
0x180030ac1  mov     dword ptr [rsp+328h+phkResult], ebx
0x180030ac5  mov     r9d, eax
0x180030ac8  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ad6  mov     rcx, [rcx+10h]
0x180030ada  call    WPP_SF_Dd
0x180030adf  test    esi, esi
0x180030ae1  jg      short loc_180030AE7
0x180030ae3  mov     ebx, esi
0x180030ae5  jmp     short loc_180030AF0
0x180030ae7  movzx   ebx, si
0x180030aea  or      ebx, 80070000h
0x180030af0  mov     [rsp+328h+var_2E8], ebx
0x180030af4  jmp     loc_180030D75
0x180030af9  mov     r14d, edi
0x180030afc  mov     [rsp+328h+var_2C8], edi
0x180030b00  cmp     esi, 103h
0x180030b06  jz      loc_180030C0B
0x180030b0c  mov     [rsp+328h+Name], di
0x180030b14  mov     [rsp+328h+cchName], 104h
0x180030b1c  mov     [rsp+328h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180030b21  mov     [rsp+328h+lpcchClass], rdi; lpcchClass
0x180030b26  mov     [rsp+328h+lpClass], rdi; lpClass
0x180030b2b  mov     [rsp+328h+phkResult], rdi; lpReserved
0x180030b30  lea     r9, [rsp+328h+cchName]; lpcchName
0x180030b35  lea     r8, [rsp+328h+Name]; lpName
0x180030b3d  mov     edx, r14d; dwIndex
0x180030b40  mov     rcx, [rsp+328h+hKey]; hKey
0x180030b45  call    cs:__imp_RegEnumKeyExW
0x180030b4b  mov     esi, eax
0x180030b4d  test    eax, eax
0x180030b4f  jz      short loc_180030BC5
0x180030b51  cmp     eax, 103h
0x180030b56  jz      short loc_180030BC3
0x180030b58  mov     rax, cs:WPP_GLOBAL_Control
0x180030b5f  cmp     rax, r12
0x180030b62  jz      short loc_180030BA9
0x180030b64  test    byte ptr [rax+1Ch], 8
0x180030b68  jz      short loc_180030BA9
0x180030b6a  cmp     byte ptr [rax+19h], 2
0x180030b6e  jb      short loc_180030BA9
0x180030b70  test    esi, esi
0x180030b72  jg      short loc_180030B78
0x180030b74  mov     ebx, esi
0x180030b76  jmp     short loc_180030B81
0x180030b78  movzx   ebx, si
0x180030b7b  or      ebx, 80070000h
0x180030b81  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030b86  mov     edx, 6Eh ; 'n'
0x180030b8b  mov     dword ptr [rsp+328h+phkResult], ebx
0x180030b8f  mov     r9d, eax
0x180030b92  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030b99  mov     rcx, cs:WPP_GLOBAL_Control
0x180030ba0  mov     rcx, [rcx+10h]
0x180030ba4  call    WPP_SF_Dd
0x180030ba9  test    esi, esi
0x180030bab  jg      short loc_180030BB1
0x180030bad  mov     ebx, esi
0x180030baf  jmp     short loc_180030BBA
0x180030bb1  movzx   ebx, si
0x180030bb4  or      ebx, 80070000h
0x180030bba  mov     [rsp+328h+var_2E8], ebx
0x180030bbe  jmp     loc_180030D75
0x180030bc3  jmp     short loc_180030BFE
0x180030bc5  lea     rdx, [rsp+328h+Name]
0x180030bcd  lea     rcx, [rsp+328h+var_280]
0x180030bd5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180030bda  nop
0x180030bdb  mov     r8, rax
0x180030bde  lea     rdx, [rsp+328h+var_2A0]
0x180030be6  lea     rcx, [rsp+328h+var_2B8]
0x180030beb  call    ?insert@?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::set<std::wstring>::insert(std::wstring &&)
0x180030bf0  nop
0x180030bf1  lea     rcx, [rsp+328h+var_280]; void *
0x180030bf9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030bfe  add     r14d, ebx
0x180030c01  mov     [rsp+328h+var_2C8], r14d
0x180030c06  jmp     loc_180030B00
0x180030c0b  lea     rdx, [rsp+328h+var_2C0]
0x180030c10  lea     rcx, [rsp+328h+var_2B8]
0x180030c15  call    ?begin@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UResourceTypeInfo@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ResourceTypeInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ResourceTypeInfo>>,0>>::begin(void)
0x180030c1a  lea     rdx, [rsp+328h+var_2A0]
0x180030c22  lea     rcx, [rsp+328h+var_2B8]
0x180030c27  call    ?begin@?$vector@IV?$allocator@_N@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@XZ; std::vector<uint>::begin(void)
0x180030c2c  mov     rdx, rax
0x180030c2f  lea     rcx, [rsp+328h+var_2C0]
0x180030c34  call    ??9?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>>::operator!=(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,bool>>>> const &)
0x180030c39  test    al, al
0x180030c3b  jz      loc_180030D67
0x180030c41  cmp     [rsp+328h+var_2E0], rdi
0x180030c46  jz      short loc_180030C61
0x180030c48  lea     rcx, [rsp+328h+var_2E0]
0x180030c4d  call    ?SafeRelease@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeRelease(void)
0x180030c52  mov     [rsp+328h+var_2E0], rdi
0x180030c57  lea     rcx, [rsp+328h+var_2E0]
0x180030c5c  call    ?SafeAddRef@?$TCntPtr@VCConfigManager@@@@AEAAXXZ; TCntPtr<CConfigManager>::SafeAddRef(void)
0x180030c61  lea     rcx, [rsp+328h+var_2E0]; struct CWorkspaceFileAssociation **
0x180030c66  call    ?CreateInstance@CWorkspaceFileAssociation@@SAJPEAPEAV1@@Z; CWorkspaceFileAssociation::CreateInstance(CWorkspaceFileAssociation * *)
0x180030c6b  mov     ebx, eax
0x180030c6d  mov     [rsp+328h+var_2E8], eax
0x180030c71  test    eax, eax
0x180030c73  jns     short loc_180030CC7
0x180030c75  mov     rax, cs:WPP_GLOBAL_Control
0x180030c7c  cmp     rax, r12
0x180030c7f  jz      short loc_180030CC2
0x180030c81  test    byte ptr [rax+1Ch], 8
0x180030c85  jz      short loc_180030CC2
0x180030c87  cmp     byte ptr [rax+19h], 2
0x180030c8b  jb      short loc_180030CC2
0x180030c8d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030c92  mov     edx, 6Fh ; 'o'
0x180030c97  mov     dword ptr [rsp+328h+lpClass], ebx
0x180030c9b  lea     rcx, aCworkspacefile_1; "CWorkspaceFileAssociation::CreateInstan"...
0x180030ca2  mov     [rsp+328h+phkResult], rcx
0x180030ca7  mov     r9d, eax
0x180030caa  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180030cb8  mov     rcx, [rcx+10h]
0x180030cbc  call    WPP_SF_DsD
0x180030cc1  nop
0x180030cc2  jmp     loc_180030D75
0x180030cc7  lea     rcx, [rsp+328h+var_2C0]
0x180030ccc  call    ??C?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEBAPEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator->(void)
0x180030cd1  mov     rcx, rax
0x180030cd4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030cd9  mov     r8, rax; unsigned __int16 *
0x180030cdc  mov     rdx, [rsp+328h+hKey]; HKEY
0x180030ce1  mov     rcx, [rsp+328h+var_2E0]; this
0x180030ce6  call    ?InitializeFromRegistry@CWorkspaceFileAssociation@@QEAAJPEAUHKEY__@@PEBG@Z; CWorkspaceFileAssociation::InitializeFromRegistry(HKEY__ *,ushort const *)
0x180030ceb  mov     ebx, eax
0x180030ced  mov     [rsp+328h+var_2E8], eax
0x180030cf1  test    eax, eax
0x180030cf3  jns     short loc_180030D44
0x180030cf5  mov     rax, cs:WPP_GLOBAL_Control
0x180030cfc  cmp     rax, r12
0x180030cff  jz      short loc_180030D42
0x180030d01  test    byte ptr [rax+1Ch], 8
0x180030d05  jz      short loc_180030D42
0x180030d07  cmp     byte ptr [rax+19h], 2
0x180030d0b  jb      short loc_180030D42
0x180030d0d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180030d12  mov     edx, 70h ; 'p'
0x180030d17  mov     dword ptr [rsp+328h+lpClass], ebx
0x180030d1b  lea     rcx, aCworkspacefile_6; "CWorkspaceFileAssociation::InitializeFr"...
0x180030d22  mov     [rsp+328h+phkResult], rcx
0x180030d27  mov     r9d, eax
0x180030d2a  lea     r8, WPP_f0913c8960533a51b69146b4f6d8f653_Traceguids
0x180030d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180030d38  mov     rcx, [rcx+10h]
0x180030d3c  call    WPP_SF_DsD
0x180030d41  nop
0x180030d42  jmp     short loc_180030D75
0x180030d44  mov     rax, [r15]
0x180030d47  mov     rdx, [rsp+328h+var_2E0]
0x180030d4c  mov     rcx, r15
0x180030d4f  mov     rax, [rax+8]
0x180030d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d58  lea     rcx, [rsp+328h+var_2C0]
0x180030d5d  call    ??E?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>>::operator++(void)
0x180030d62  jmp     loc_180030C1A
0x180030d67  mov     ebx, edi
0x180030d69  mov     [rsp+328h+var_2E8], ebx
0x180030d6d  jmp     short loc_180030D75
0x180030d6f  jmp     short $+2
0x180030d71  mov     ebx, [rsp+328h+var_2E8]
0x180030d75  mov     rcx, [rsp+328h+hKey]; hKey
0x180030d7a  test    rcx, rcx
0x180030d7d  jz      short loc_180030D86
0x180030d7f  call    cs:__imp_RegCloseKey
0x180030d85  nop
0x180030d86  lea     rcx, [rsp+328h+var_2E0]
0x180030d8b  call    ??1?$ComPlainSmartPtr@VCRadcXmlIcon@@@@QEAA@XZ; ComPlainSmartPtr<CRadcXmlIcon>::~ComPlainSmartPtr<CRadcXmlIcon>(void)
0x180030d90  nop
0x180030d91  lea     rcx, [rsp+328h+var_2B8]
0x180030d96  call    ??1?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::~set<std::wstring>(void)
0x180030d9b  mov     eax, ebx
0x180030d9d  mov     rcx, [rsp+328h+var_40]
0x180030da5  xor     rcx, rsp; StackCookie
0x180030da8  call    __security_check_cookie
0x180030dad  add     rsp, 2F8h
0x180030db4  pop     r15
0x180030db6  pop     r14
0x180030db8  pop     r12
0x180030dba  pop     rdi
0x180030dbb  pop     rsi
0x180030dbc  pop     rbx
0x180030dbd  retn
```
