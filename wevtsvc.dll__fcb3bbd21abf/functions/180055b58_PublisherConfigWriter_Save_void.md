# PublisherConfigWriter::Save(void)

- ea: `0x180055b58`
- end: `0x18005643c`
- name: `?Save@PublisherConfigWriter@@QEAAXXZ`
- size: `2276`
- prototype: `void __fastcall(PublisherConfigWriter *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180054cdc`
- `0x18005afd8`

## callees

- `0x180006770`
- `0x180017b98`
- `0x180055b58`
- `0x18005c2d4`
- `0x1800778a4`
- `0x180092008`
- `0x18009aee0`
- `0x1800be098`
- `0x1800be1b4`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800560c0`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800560c0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055f31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005615f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005619a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056392`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180055f31`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005615f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005619a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056392`

## string_xrefs

- `0x180055e6f`: `HelpLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PublisherConfigWriter::Save(PublisherConfigWriter *this)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  unsigned int v12; // eax
  unsigned int v13; // ebx
  void *v14; // rbx
  HKEY *v15; // rax
  struct _SECURITY_ATTRIBUTES *const v16; // r9
  unsigned int RegKey; // eax
  unsigned int v18; // ebx
  unsigned __int64 i; // r15
  __int64 v20; // r14
  void *v21; // rbx
  HKEY *v22; // rax
  struct _SECURITY_ATTRIBUTES *const v23; // r9
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // ebx
  unsigned int v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // ebx
  const wchar_t *pExceptionObject; // [rsp+40h] [rbp-49h] BYREF
  __int64 v31; // [rsp+48h] [rbp-41h]
  __int64 v32; // [rsp+50h] [rbp-39h]
  unsigned int v33; // [rsp+58h] [rbp-31h]
  __int64 v34; // [rsp+5Ch] [rbp-2Dh]
  char v35; // [rsp+64h] [rbp-25h]
  BYTE Data[8]; // [rsp+68h] [rbp-21h] BYREF
  HKEY v37; // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+78h] [rbp-11h]
  HKEY hKey[2]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v40[2]; // [rsp+90h] [rbp+7h] BYREF
  wchar_t v41[8]; // [rsp+A0h] [rbp+17h] BYREF

  if ( *((_BYTE *)this + 329) )
  {
    v37 = (HKEY)*((_QWORD *)this + 34);
    v38 = (__int64)(*((_QWORD *)this + 35) - (_QWORD)v37) >> 1;
    v2 = RegWriteStringValueNoThrow(*(_QWORD *)this, &pszFormat, &v37);
    v3 = v2;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v2);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v3;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 330) )
  {
    v37 = (HKEY)*((_QWORD *)this + 18);
    v38 = (__int64)(*((_QWORD *)this + 19) - (_QWORD)v37) >> 1;
    v4 = RegWriteExpandStringValueNoThrow(*(_QWORD *)this, L"ResourceFileName", &v37);
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v4);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v5;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 331) )
  {
    v37 = (HKEY)*((_QWORD *)this + 22);
    v38 = (__int64)(*((_QWORD *)this + 23) - (_QWORD)v37) >> 1;
    v6 = RegWriteExpandStringValueNoThrow(*(_QWORD *)this, L"MessageFileName", &v37);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v6);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v7;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 332) )
  {
    v37 = (HKEY)*((_QWORD *)this + 26);
    v38 = (__int64)(*((_QWORD *)this + 27) - (_QWORD)v37) >> 1;
    v8 = RegWriteExpandStringValueNoThrow(*(_QWORD *)this, L"ParameterFileName", &v37);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v8);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v9;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 333) )
  {
    v37 = (HKEY)*((_QWORD *)this + 30);
    v38 = (__int64)(*((_QWORD *)this + 31) - (_QWORD)v37) >> 1;
    v10 = RegWriteStringValueNoThrow(*(_QWORD *)this, L"HelpLink", &v37);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v10);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v11;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 335) )
  {
    *(_DWORD *)Data = *((_BYTE *)this + 328) != 0;
    v12 = RegSetValueExW(*(HKEY *)this, L"Enabled", 0, 4u, Data, 4u);
    v13 = v12;
    if ( v12 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v12);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v13;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 334) )
  {
    v37 = 0;
    RegDeleteKeyRecursive(*(HKEY *)this, L"ChannelReferences", *((void **)this + 1));
    v14 = (void *)*((_QWORD *)this + 1);
    v15 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v37);
    RegKey = CreateRegKey(*(HKEY *)this, L"ChannelReferences", 0x2001Fu, v16, v15, 0, v14);
    v18 = RegKey;
    if ( RegKey )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, RegKey);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v18;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    for ( i = 0; ; ++i )
    {
      v20 = *((_QWORD *)this + 38);
      if ( i >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 39) - v20) >> 4) )
        break;
      hKey[0] = 0;
      _o__itow_s(*(unsigned int *)(v20 + 48 * i + 36), v41, 8);
      v21 = (void *)*((_QWORD *)this + 1);
      v22 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
      v24 = CreateRegKey(v37, v41, 2u, v23, v22, 0, v21);
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v24);
        }
        pExceptionObject = &byte_1800EC961;
        v31 = 0;
        v32 = 0;
        v33 = v24;
        v34 = -1;
        v35 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      v40[0] = *(_QWORD *)(v20 + 48 * i);
      v40[1] = (__int64)(*(_QWORD *)(v20 + 48 * i + 8) - v40[0]) >> 1;
      v25 = RegWriteStringValueNoThrow(hKey[0], &pszFormat, v40);
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v25);
        }
        pExceptionObject = &byte_1800EC961;
        v31 = 0;
        v32 = 0;
        v33 = v25;
        v34 = -1;
        v35 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_DWORD *)Data = *(_DWORD *)(v20 + 48 * i + 32);
      v26 = RegSetValueExW(hKey[0], L"Id", 0, 4u, Data, 4u);
      if ( v26 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v26);
        }
        pExceptionObject = &byte_1800EC961;
        v31 = 0;
        v32 = 0;
        v33 = v26;
        v34 = -1;
        v35 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_DWORD *)Data = *(_DWORD *)(v20 + 48 * i + 40);
      v27 = RegSetValueExW(hKey[0], L"Flags", 0, 4u, Data, 4u);
      if ( v27 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v27);
        }
        pExceptionObject = &byte_1800EC961;
        v31 = 0;
        v32 = 0;
        v33 = v27;
        v34 = -1;
        v35 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
    }
    *(_DWORD *)Data = -1431655765 * ((*((_QWORD *)this + 39) - v20) >> 4);
    v28 = RegSetValueExW(v37, L"Count", 0, 4u, Data, 4u);
    v29 = v28;
    if ( v28 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids, v28);
      }
      pExceptionObject = &byte_1800EC961;
      v31 = 0;
      v32 = 0;
      v33 = v29;
      v34 = -1;
      v35 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v37);
  }
}

```

## disassembly

```asm
0x180055b58  mov     [rsp-8+arg_8], rbx
0x180055b5d  mov     [rsp-8+arg_10], rdi
0x180055b62  push    rbp
0x180055b63  push    r12
0x180055b65  push    r13
0x180055b67  push    r14
0x180055b69  push    r15
0x180055b6b  lea     rbp, [rsp-37h]
0x180055b70  sub     rsp, 0C0h
0x180055b77  mov     rax, cs:__security_cookie
0x180055b7e  xor     rax, rsp
0x180055b81  mov     [rbp+57h+var_30], rax
0x180055b85  mov     rdi, rcx
0x180055b88  xor     r13d, r13d
0x180055b8b  cmp     [rcx+149h], r13b
0x180055b92  jz      loc_180055C38
0x180055b98  mov     rax, [rcx+110h]
0x180055b9f  mov     [rbp+57h+var_70], rax
0x180055ba3  mov     rcx, [rcx+118h]
0x180055baa  sub     rcx, rax
0x180055bad  sar     rcx, 1
0x180055bb0  mov     [rbp+57h+var_68], rcx
0x180055bb4  lea     r8, [rbp+57h+var_70]
0x180055bb8  lea     rdx, pszFormat
0x180055bbf  mov     rcx, [rdi]
0x180055bc2  call    ?RegWriteStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180055bc7  mov     ebx, eax
0x180055bc9  test    eax, eax
0x180055bcb  jz      short loc_180055C38
0x180055bcd  lea     rcx, WPP_GLOBAL_Control
0x180055bd4  mov     r10, cs:WPP_GLOBAL_Control
0x180055bdb  cmp     r10, rcx
0x180055bde  jz      short loc_180055C05
0x180055be0  test    byte ptr [r10+1Ch], 4
0x180055be5  jz      short loc_180055C05
0x180055be7  cmp     byte ptr [r10+19h], 2
0x180055bec  jb      short loc_180055C05
0x180055bee  lea     edx, [r13+0Ch]
0x180055bf2  mov     r9d, eax
0x180055bf5  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055bfc  mov     rcx, [r10+10h]
0x180055c00  call    WPP_SF_d
0x180055c05  lea     rax, byte_1800EC961
0x180055c0c  mov     [rbp+57h+pExceptionObject], rax
0x180055c10  mov     [rbp+57h+var_98], r13
0x180055c14  mov     [rbp+57h+var_90], r13
0x180055c18  mov     [rbp+57h+var_88], ebx
0x180055c1b  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055c23  mov     [rbp+57h+var_7C], r13b
0x180055c27  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055c2e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055c32  call    _CxxThrowException_0
0x180055c38  cmp     [rdi+14Ah], r13b
0x180055c3f  jz      loc_180055CE6
0x180055c45  mov     rax, [rdi+90h]
0x180055c4c  mov     [rbp+57h+var_70], rax
0x180055c50  mov     rcx, [rdi+98h]
0x180055c57  sub     rcx, rax
0x180055c5a  sar     rcx, 1
0x180055c5d  mov     [rbp+57h+var_68], rcx
0x180055c61  lea     r8, [rbp+57h+var_70]
0x180055c65  lea     rdx, aResourcefilena; "ResourceFileName"
0x180055c6c  mov     rcx, [rdi]
0x180055c6f  call    ?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180055c74  mov     ebx, eax
0x180055c76  test    eax, eax
0x180055c78  jz      short loc_180055CE6
0x180055c7a  lea     rcx, WPP_GLOBAL_Control
0x180055c81  mov     r10, cs:WPP_GLOBAL_Control
0x180055c88  cmp     r10, rcx
0x180055c8b  jz      short loc_180055CB3
0x180055c8d  test    byte ptr [r10+1Ch], 4
0x180055c92  jz      short loc_180055CB3
0x180055c94  cmp     byte ptr [r10+19h], 2
0x180055c99  jb      short loc_180055CB3
0x180055c9b  mov     edx, 0Dh
0x180055ca0  mov     r9d, eax
0x180055ca3  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055caa  mov     rcx, [r10+10h]
0x180055cae  call    WPP_SF_d
0x180055cb3  lea     rax, byte_1800EC961
0x180055cba  mov     [rbp+57h+pExceptionObject], rax
0x180055cbe  mov     [rbp+57h+var_98], r13
0x180055cc2  mov     [rbp+57h+var_90], r13
0x180055cc6  mov     [rbp+57h+var_88], ebx
0x180055cc9  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055cd1  mov     [rbp+57h+var_7C], r13b
0x180055cd5  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055cdc  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055ce0  call    _CxxThrowException_0
0x180055ce6  cmp     [rdi+14Bh], r13b
0x180055ced  jz      loc_180055D94
0x180055cf3  mov     rax, [rdi+0B0h]
0x180055cfa  mov     [rbp+57h+var_70], rax
0x180055cfe  mov     rcx, [rdi+0B8h]
0x180055d05  sub     rcx, rax
0x180055d08  sar     rcx, 1
0x180055d0b  mov     [rbp+57h+var_68], rcx
0x180055d0f  lea     r8, [rbp+57h+var_70]
0x180055d13  lea     rdx, aMessagefilenam; "MessageFileName"
0x180055d1a  mov     rcx, [rdi]
0x180055d1d  call    ?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180055d22  mov     ebx, eax
0x180055d24  test    eax, eax
0x180055d26  jz      short loc_180055D94
0x180055d28  lea     rcx, WPP_GLOBAL_Control
0x180055d2f  mov     r10, cs:WPP_GLOBAL_Control
0x180055d36  cmp     r10, rcx
0x180055d39  jz      short loc_180055D61
0x180055d3b  test    byte ptr [r10+1Ch], 4
0x180055d40  jz      short loc_180055D61
0x180055d42  cmp     byte ptr [r10+19h], 2
0x180055d47  jb      short loc_180055D61
0x180055d49  mov     edx, 0Eh
0x180055d4e  mov     r9d, eax
0x180055d51  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055d58  mov     rcx, [r10+10h]
0x180055d5c  call    WPP_SF_d
0x180055d61  lea     rax, byte_1800EC961
0x180055d68  mov     [rbp+57h+pExceptionObject], rax
0x180055d6c  mov     [rbp+57h+var_98], r13
0x180055d70  mov     [rbp+57h+var_90], r13
0x180055d74  mov     [rbp+57h+var_88], ebx
0x180055d77  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055d7f  mov     [rbp+57h+var_7C], r13b
0x180055d83  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055d8a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055d8e  call    _CxxThrowException_0
0x180055d94  cmp     [rdi+14Ch], r13b
0x180055d9b  jz      loc_180055E42
0x180055da1  mov     rax, [rdi+0D0h]
0x180055da8  mov     [rbp+57h+var_70], rax
0x180055dac  mov     rcx, [rdi+0D8h]
0x180055db3  sub     rcx, rax
0x180055db6  sar     rcx, 1
0x180055db9  mov     [rbp+57h+var_68], rcx
0x180055dbd  lea     r8, [rbp+57h+var_70]
0x180055dc1  lea     rdx, aParameterfilen; "ParameterFileName"
0x180055dc8  mov     rcx, [rdi]
0x180055dcb  call    ?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180055dd0  mov     ebx, eax
0x180055dd2  test    eax, eax
0x180055dd4  jz      short loc_180055E42
0x180055dd6  lea     rcx, WPP_GLOBAL_Control
0x180055ddd  mov     r10, cs:WPP_GLOBAL_Control
0x180055de4  cmp     r10, rcx
0x180055de7  jz      short loc_180055E0F
0x180055de9  test    byte ptr [r10+1Ch], 4
0x180055dee  jz      short loc_180055E0F
0x180055df0  cmp     byte ptr [r10+19h], 2
0x180055df5  jb      short loc_180055E0F
0x180055df7  mov     edx, 0Fh
0x180055dfc  mov     r9d, eax
0x180055dff  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055e06  mov     rcx, [r10+10h]
0x180055e0a  call    WPP_SF_d
0x180055e0f  lea     rax, byte_1800EC961
0x180055e16  mov     [rbp+57h+pExceptionObject], rax
0x180055e1a  mov     [rbp+57h+var_98], r13
0x180055e1e  mov     [rbp+57h+var_90], r13
0x180055e22  mov     [rbp+57h+var_88], ebx
0x180055e25  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055e2d  mov     [rbp+57h+var_7C], r13b
0x180055e31  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055e38  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055e3c  call    _CxxThrowException_0
0x180055e42  cmp     [rdi+14Dh], r13b
0x180055e49  jz      loc_180055EF0
0x180055e4f  mov     rax, [rdi+0F0h]
0x180055e56  mov     [rbp+57h+var_70], rax
0x180055e5a  mov     rcx, [rdi+0F8h]
0x180055e61  sub     rcx, rax
0x180055e64  sar     rcx, 1
0x180055e67  mov     [rbp+57h+var_68], rcx
0x180055e6b  lea     r8, [rbp+57h+var_70]
0x180055e6f  lea     rdx, aHelplink; "HelpLink"
0x180055e76  mov     rcx, [rdi]
0x180055e79  call    ?RegWriteStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x180055e7e  mov     ebx, eax
0x180055e80  test    eax, eax
0x180055e82  jz      short loc_180055EF0
0x180055e84  lea     rcx, WPP_GLOBAL_Control
0x180055e8b  mov     r10, cs:WPP_GLOBAL_Control
0x180055e92  cmp     r10, rcx
0x180055e95  jz      short loc_180055EBD
0x180055e97  test    byte ptr [r10+1Ch], 4
0x180055e9c  jz      short loc_180055EBD
0x180055e9e  cmp     byte ptr [r10+19h], 2
0x180055ea3  jb      short loc_180055EBD
0x180055ea5  mov     edx, 10h
0x180055eaa  mov     r9d, eax
0x180055ead  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055eb4  mov     rcx, [r10+10h]
0x180055eb8  call    WPP_SF_d
0x180055ebd  lea     rax, byte_1800EC961
0x180055ec4  mov     [rbp+57h+pExceptionObject], rax
0x180055ec8  mov     [rbp+57h+var_98], r13
0x180055ecc  mov     [rbp+57h+var_90], r13
0x180055ed0  mov     [rbp+57h+var_88], ebx
0x180055ed3  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055edb  mov     [rbp+57h+var_7C], r13b
0x180055edf  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055ee6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055eea  call    _CxxThrowException_0
0x180055ef0  cmp     [rdi+14Fh], r13b
0x180055ef7  jz      loc_180055FA9
0x180055efd  mov     eax, r13d
0x180055f00  cmp     [rdi+148h], r13b
0x180055f07  setnz   al
0x180055f0a  mov     dword ptr [rbp+57h+Data], eax
0x180055f0d  mov     [rsp+0E0h+cbData], 4; cbData
0x180055f15  lea     rax, [rbp+57h+Data]
0x180055f19  mov     [rsp+0E0h+lpData], rax; lpData
0x180055f1e  mov     r9d, 4; dwType
0x180055f24  xor     r8d, r8d; Reserved
0x180055f27  lea     rdx, aEnabled; "Enabled"
0x180055f2e  mov     rcx, [rdi]; hKey
0x180055f31  call    cs:__imp_RegSetValueExW
0x180055f37  mov     ebx, eax
0x180055f39  test    eax, eax
0x180055f3b  jz      short loc_180055FA9
0x180055f3d  lea     rcx, WPP_GLOBAL_Control
0x180055f44  mov     r10, cs:WPP_GLOBAL_Control
0x180055f4b  cmp     r10, rcx
0x180055f4e  jz      short loc_180055F76
0x180055f50  test    byte ptr [r10+1Ch], 4
0x180055f55  jz      short loc_180055F76
0x180055f57  cmp     byte ptr [r10+19h], 2
0x180055f5c  jb      short loc_180055F76
0x180055f5e  mov     edx, 11h
0x180055f63  mov     r9d, eax
0x180055f66  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180055f6d  mov     rcx, [r10+10h]
0x180055f71  call    WPP_SF_d
0x180055f76  lea     rax, byte_1800EC961
0x180055f7d  mov     [rbp+57h+pExceptionObject], rax
0x180055f81  mov     [rbp+57h+var_98], r13
0x180055f85  mov     [rbp+57h+var_90], r13
0x180055f89  mov     [rbp+57h+var_88], ebx
0x180055f8c  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x180055f94  mov     [rbp+57h+var_7C], r13b
0x180055f98  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180055f9f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180055fa3  call    _CxxThrowException_0
0x180055fa9  cmp     [rdi+14Eh], r13b
0x180055fb0  jz      loc_180056413
0x180055fb6  mov     [rbp+57h+var_70], r13
0x180055fba  mov     r8, [rdi+8]; void *
0x180055fbe  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x180055fc5  mov     rcx, [rdi]; HKEY
0x180055fc8  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x180055fcd  mov     rbx, [rdi+8]
0x180055fd1  lea     rcx, [rbp+57h+var_70]
0x180055fd5  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180055fda  mov     [rsp+0E0h+var_B0], rbx; void *
0x180055fdf  mov     qword ptr [rsp+0E0h+cbData], r13; unsigned int *
0x180055fe4  mov     [rsp+0E0h+lpData], rax; HKEY *
0x180055fe9  mov     r8d, 2001Fh; unsigned int
0x180055fef  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x180055ff6  mov     rcx, [rdi]; HKEY
0x180055ff9  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x180055ffe  mov     ebx, eax
0x180056000  test    eax, eax
0x180056002  jz      short loc_180056070
0x180056004  lea     rcx, WPP_GLOBAL_Control
0x18005600b  mov     r10, cs:WPP_GLOBAL_Control
0x180056012  cmp     r10, rcx
0x180056015  jz      short loc_18005603D
0x180056017  test    byte ptr [r10+1Ch], 4
0x18005601c  jz      short loc_18005603D
0x18005601e  cmp     byte ptr [r10+19h], 2
0x180056023  jb      short loc_18005603D
0x180056025  mov     edx, 12h
0x18005602a  mov     r9d, eax
0x18005602d  lea     r8, WPP_32a4d2a278393f6e99a506f14c1270e2_Traceguids
0x180056034  mov     rcx, [r10+10h]
0x180056038  call    WPP_SF_d
0x18005603d  lea     rax, byte_1800EC961
0x180056044  mov     [rbp+57h+pExceptionObject], rax
0x180056048  mov     [rbp+57h+var_98], r13
0x18005604c  mov     [rbp+57h+var_90], r13
0x180056050  mov     [rbp+57h+var_88], ebx
0x180056053  mov     [rbp+57h+var_84], 0FFFFFFFFFFFFFFFFh
0x18005605b  mov     [rbp+57h+var_7C], r13b
0x18005605f  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180056066  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18005606a  call    _CxxThrowException_0
0x180056070  mov     r15, r13
0x180056073  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18005607d  mov     r14, [rdi+130h]
0x180056084  mov     rcx, [rdi+138h]
0x18005608b  mov     rax, rcx
0x18005608e  sub     rax, r14
0x180056091  sar     rax, 4
0x180056095  imul    rax, rdx
0x180056099  cmp     r15, rax
0x18005609c  jnb     loc_18005635F
0x1800560a2  lea     r12, [r15+r15*2]
0x1800560a6  add     r12, r12
0x1800560a9  mov     [rbp+57h+hKey], r13
  ... truncated ...
```
