# PublisherConfigWriter::Save(void)

- ea: `0x140009b58`
- end: `0x14000a457`
- name: `?Save@PublisherConfigWriter@@QEAAXXZ`
- size: `2303`
- prototype: `void __fastcall(PublisherConfigWriter *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14001663c`

## callees

- `0x140006db0`
- `0x140009b58`
- `0x14000a4d8`
- `0x14001a814`
- `0x14001b668`
- `0x14001b6d0`
- `0x140021b00`
- `0x140022cec`
- `0x140031810`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000a0cc`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x14000a0cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a1c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a434`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a1c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000a434`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140009d21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140009f36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a170`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a1ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a3af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140009d21`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140009f36`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a170`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a1ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14000a3af`

## string_xrefs

- `0x140009e74`: `HelpLink`

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
  unsigned int RegKey; // eax
  unsigned int v17; // ebx
  unsigned __int64 i; // r12
  __int64 v19; // r15
  void *v20; // rbx
  HKEY *v21; // rax
  unsigned int v22; // ebx
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // ebx
  unsigned int v26; // eax
  unsigned int v27; // ebx
  __int16 *pExceptionObject; // [rsp+40h] [rbp-59h] BYREF
  __int64 v29; // [rsp+48h] [rbp-51h]
  __int64 v30; // [rsp+50h] [rbp-49h]
  unsigned int v31; // [rsp+58h] [rbp-41h]
  __int64 v32; // [rsp+5Ch] [rbp-3Dh]
  char v33; // [rsp+64h] [rbp-35h]
  BYTE Data[8]; // [rsp+68h] [rbp-31h] BYREF
  HKEY v35; // [rsp+70h] [rbp-29h] BYREF
  __int64 v36; // [rsp+78h] [rbp-21h]
  HKEY hKey[2]; // [rsp+80h] [rbp-19h] BYREF
  _QWORD v38[2]; // [rsp+90h] [rbp-9h] BYREF
  wchar_t v39[8]; // [rsp+A0h] [rbp+7h] BYREF

  if ( *((_BYTE *)this + 329) )
  {
    v35 = (HKEY)*((_QWORD *)this + 34);
    v36 = (__int64)(*((_QWORD *)this + 35) - (_QWORD)v35) >> 1;
    v2 = RegWriteStringValueNoThrow(*(_QWORD *)this, &ValueName, &v35);
    v3 = v2;
    if ( v2 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v2);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v3;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 330) )
  {
    v35 = (HKEY)*((_QWORD *)this + 18);
    v36 = (__int64)(*((_QWORD *)this + 19) - (_QWORD)v35) >> 1;
    v4 = RegWriteExpandStringValueNoThrow(*(_QWORD *)this, L"ResourceFileName", &v35);
    v5 = v4;
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v4);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v5;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 331) )
  {
    v6 = RegSetValueExW(
           *(HKEY *)this,
           L"MessageFileName",
           0,
           2u,
           *((const BYTE **)this + 22),
           2 * ((__int64)(*((_QWORD *)this + 23) - *((_QWORD *)this + 22)) >> 1) + 2);
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v6);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v7;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 332) )
  {
    v35 = (HKEY)*((_QWORD *)this + 26);
    v36 = (__int64)(*((_QWORD *)this + 27) - (_QWORD)v35) >> 1;
    v8 = RegWriteExpandStringValueNoThrow(*(_QWORD *)this, L"ParameterFileName", &v35);
    v9 = v8;
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v8);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v9;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 333) )
  {
    v35 = (HKEY)*((_QWORD *)this + 30);
    v36 = (__int64)(*((_QWORD *)this + 31) - (_QWORD)v35) >> 1;
    v10 = RegWriteStringValueNoThrow(*(_QWORD *)this, L"HelpLink", &v35);
    v11 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v10);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v11;
      v32 = -1;
      v33 = 0;
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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v12);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v13;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
  }
  if ( *((_BYTE *)this + 334) )
  {
    v35 = 0;
    RegDeleteKeyRecursive(*(HKEY *)this, L"ChannelReferences", *((void **)this + 1));
    v14 = (void *)*((_QWORD *)this + 1);
    v15 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v35);
    RegKey = CreateRegKey(*(HKEY *)this, L"ChannelReferences", 0x2001Fu, 0, v15, 0, v14);
    v17 = RegKey;
    if ( RegKey )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, RegKey);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v17;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    for ( i = 0; ; ++i )
    {
      v19 = *((_QWORD *)this + 38);
      if ( i >= 0xAAAAAAAAAAAAAAABuLL * ((*((_QWORD *)this + 39) - v19) >> 4) )
        break;
      hKey[0] = 0;
      _o__itow_s(*(unsigned int *)(v19 + 48 * i + 36), v39, 8);
      v20 = (void *)*((_QWORD *)this + 1);
      v21 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(hKey);
      v22 = CreateRegKey(v35, v39, 2u, 0, v21, 0, v20);
      if ( v22 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v22);
        }
        pExceptionObject = word_14003838A;
        v29 = 0;
        v30 = 0;
        v31 = v22;
        v32 = -1;
        v33 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      v38[0] = *(_QWORD *)(v19 + 48 * i);
      v38[1] = (__int64)(*(_QWORD *)(v19 + 48 * i + 8) - v38[0]) >> 1;
      v23 = RegWriteStringValueNoThrow(hKey[0], &ValueName, v38);
      if ( v23 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v23);
        }
        pExceptionObject = word_14003838A;
        v29 = 0;
        v30 = 0;
        v31 = v23;
        v32 = -1;
        v33 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_DWORD *)Data = *(_DWORD *)(v19 + 48 * i + 32);
      v24 = RegSetValueExW(hKey[0], L"Id", 0, 4u, Data, 4u);
      if ( v24 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v24);
        }
        pExceptionObject = word_14003838A;
        v29 = 0;
        v30 = 0;
        v31 = v24;
        v32 = -1;
        v33 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      *(_DWORD *)Data = *(_DWORD *)(v19 + 48 * i + 40);
      v25 = RegSetValueExW(hKey[0], L"Flags", 0, 4u, Data, 4u);
      if ( v25 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v25);
        }
        pExceptionObject = word_14003838A;
        v29 = 0;
        v30 = 0;
        v31 = v25;
        v32 = -1;
        v33 = 0;
        throw (EvtException *)&pExceptionObject;
      }
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
    }
    *(_DWORD *)Data = -1431655765 * ((*((_QWORD *)this + 39) - v19) >> 4);
    v26 = RegSetValueExW(v35, L"Count", 0, 4u, Data, 4u);
    v27 = v26;
    if ( v26 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids, v26);
      }
      pExceptionObject = word_14003838A;
      v29 = 0;
      v30 = 0;
      v31 = v27;
      v32 = -1;
      v33 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( v35 )
      RegCloseKey(v35);
  }
}

```

## disassembly

```asm
0x140009b58  push    rbp
0x140009b5a  push    rbx
0x140009b5b  push    rdi
0x140009b5c  push    r12
0x140009b5e  push    r13
0x140009b60  push    r15
0x140009b62  lea     rbp, [rsp-2Fh]
0x140009b67  sub     rsp, 0C8h
0x140009b6e  mov     rax, cs:__security_cookie
0x140009b75  xor     rax, rsp
0x140009b78  mov     [rbp+57h+var_40], rax
0x140009b7c  mov     rdi, rcx
0x140009b7f  xor     r13d, r13d
0x140009b82  cmp     [rcx+149h], r13b
0x140009b89  jz      loc_140009C2F
0x140009b8f  mov     rax, [rcx+110h]
0x140009b96  mov     [rbp+57h+var_80], rax
0x140009b9a  mov     rcx, [rcx+118h]
0x140009ba1  sub     rcx, rax
0x140009ba4  sar     rcx, 1
0x140009ba7  mov     [rbp+57h+var_78], rcx
0x140009bab  lea     r8, [rbp+57h+var_80]
0x140009baf  lea     rdx, ValueName
0x140009bb6  mov     rcx, [rdi]
0x140009bb9  call    ?RegWriteStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x140009bbe  mov     ebx, eax
0x140009bc0  test    eax, eax
0x140009bc2  jz      short loc_140009C2F
0x140009bc4  lea     rcx, WPP_GLOBAL_Control
0x140009bcb  mov     r10, cs:WPP_GLOBAL_Control
0x140009bd2  cmp     r10, rcx
0x140009bd5  jz      short loc_140009BFC
0x140009bd7  test    byte ptr [r10+1Ch], 4
0x140009bdc  jz      short loc_140009BFC
0x140009bde  cmp     byte ptr [r10+19h], 2
0x140009be3  jb      short loc_140009BFC
0x140009be5  lea     edx, [r13+0Ch]
0x140009be9  mov     r9d, eax
0x140009bec  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009bf3  mov     rcx, [r10+10h]
0x140009bf7  call    WPP_SF_d
0x140009bfc  lea     rax, word_14003838A
0x140009c03  mov     [rbp+57h+pExceptionObject], rax
0x140009c07  mov     [rbp+57h+var_A8], r13
0x140009c0b  mov     [rbp+57h+var_A0], r13
0x140009c0f  mov     [rbp+57h+var_98], ebx
0x140009c12  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009c1a  mov     [rbp+57h+var_8C], r13b
0x140009c1e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009c25  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009c29  call    _CxxThrowException_0
0x140009c2f  cmp     [rdi+14Ah], r13b
0x140009c36  jz      loc_140009CDD
0x140009c3c  mov     rax, [rdi+90h]
0x140009c43  mov     [rbp+57h+var_80], rax
0x140009c47  mov     rcx, [rdi+98h]
0x140009c4e  sub     rcx, rax
0x140009c51  sar     rcx, 1
0x140009c54  mov     [rbp+57h+var_78], rcx
0x140009c58  lea     r8, [rbp+57h+var_80]
0x140009c5c  lea     rdx, aResourcefilena; "ResourceFileName"
0x140009c63  mov     rcx, [rdi]
0x140009c66  call    ?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x140009c6b  mov     ebx, eax
0x140009c6d  test    eax, eax
0x140009c6f  jz      short loc_140009CDD
0x140009c71  lea     rcx, WPP_GLOBAL_Control
0x140009c78  mov     r10, cs:WPP_GLOBAL_Control
0x140009c7f  cmp     r10, rcx
0x140009c82  jz      short loc_140009CAA
0x140009c84  test    byte ptr [r10+1Ch], 4
0x140009c89  jz      short loc_140009CAA
0x140009c8b  cmp     byte ptr [r10+19h], 2
0x140009c90  jb      short loc_140009CAA
0x140009c92  mov     edx, 0Dh
0x140009c97  mov     r9d, eax
0x140009c9a  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009ca1  mov     rcx, [r10+10h]
0x140009ca5  call    WPP_SF_d
0x140009caa  lea     rax, word_14003838A
0x140009cb1  mov     [rbp+57h+pExceptionObject], rax
0x140009cb5  mov     [rbp+57h+var_A8], r13
0x140009cb9  mov     [rbp+57h+var_A0], r13
0x140009cbd  mov     [rbp+57h+var_98], ebx
0x140009cc0  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009cc8  mov     [rbp+57h+var_8C], r13b
0x140009ccc  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009cd3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009cd7  call    _CxxThrowException_0
0x140009cdd  cmp     [rdi+14Bh], r13b
0x140009ce4  jz      loc_140009D99
0x140009cea  mov     rcx, [rdi+0B0h]
0x140009cf1  mov     rax, [rdi+0B8h]
0x140009cf8  sub     rax, rcx
0x140009cfb  sar     rax, 1
0x140009cfe  lea     eax, ds:2[rax*2]
0x140009d05  mov     [rsp+0F0h+cbData], eax; cbData
0x140009d09  mov     [rsp+0F0h+lpData], rcx; lpData
0x140009d0e  mov     r9d, 2; dwType
0x140009d14  xor     r8d, r8d; Reserved
0x140009d17  lea     rdx, aMessagefilenam; "MessageFileName"
0x140009d1e  mov     rcx, [rdi]; hKey
0x140009d21  call    cs:__imp_RegSetValueExW
0x140009d27  mov     ebx, eax
0x140009d29  test    eax, eax
0x140009d2b  jz      short loc_140009D99
0x140009d2d  lea     rcx, WPP_GLOBAL_Control
0x140009d34  mov     r10, cs:WPP_GLOBAL_Control
0x140009d3b  cmp     r10, rcx
0x140009d3e  jz      short loc_140009D66
0x140009d40  test    byte ptr [r10+1Ch], 4
0x140009d45  jz      short loc_140009D66
0x140009d47  cmp     byte ptr [r10+19h], 2
0x140009d4c  jb      short loc_140009D66
0x140009d4e  mov     edx, 0Eh
0x140009d53  mov     r9d, eax
0x140009d56  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009d5d  mov     rcx, [r10+10h]
0x140009d61  call    WPP_SF_d
0x140009d66  lea     rax, word_14003838A
0x140009d6d  mov     [rbp+57h+pExceptionObject], rax
0x140009d71  mov     [rbp+57h+var_A8], r13
0x140009d75  mov     [rbp+57h+var_A0], r13
0x140009d79  mov     [rbp+57h+var_98], ebx
0x140009d7c  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009d84  mov     [rbp+57h+var_8C], r13b
0x140009d88  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009d8f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009d93  call    _CxxThrowException_0
0x140009d99  cmp     [rdi+14Ch], r13b
0x140009da0  jz      loc_140009E47
0x140009da6  mov     rax, [rdi+0D0h]
0x140009dad  mov     [rbp+57h+var_80], rax
0x140009db1  mov     rcx, [rdi+0D8h]
0x140009db8  sub     rcx, rax
0x140009dbb  sar     rcx, 1
0x140009dbe  mov     [rbp+57h+var_78], rcx
0x140009dc2  lea     r8, [rbp+57h+var_80]
0x140009dc6  lea     rdx, aParameterfilen; "ParameterFileName"
0x140009dcd  mov     rcx, [rdi]
0x140009dd0  call    ?RegWriteExpandStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteExpandStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x140009dd5  mov     ebx, eax
0x140009dd7  test    eax, eax
0x140009dd9  jz      short loc_140009E47
0x140009ddb  lea     rcx, WPP_GLOBAL_Control
0x140009de2  mov     r10, cs:WPP_GLOBAL_Control
0x140009de9  cmp     r10, rcx
0x140009dec  jz      short loc_140009E14
0x140009dee  test    byte ptr [r10+1Ch], 4
0x140009df3  jz      short loc_140009E14
0x140009df5  cmp     byte ptr [r10+19h], 2
0x140009dfa  jb      short loc_140009E14
0x140009dfc  mov     edx, 0Fh
0x140009e01  mov     r9d, eax
0x140009e04  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009e0b  mov     rcx, [r10+10h]
0x140009e0f  call    WPP_SF_d
0x140009e14  lea     rax, word_14003838A
0x140009e1b  mov     [rbp+57h+pExceptionObject], rax
0x140009e1f  mov     [rbp+57h+var_A8], r13
0x140009e23  mov     [rbp+57h+var_A0], r13
0x140009e27  mov     [rbp+57h+var_98], ebx
0x140009e2a  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009e32  mov     [rbp+57h+var_8C], r13b
0x140009e36  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009e3d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009e41  call    _CxxThrowException_0
0x140009e47  cmp     [rdi+14Dh], r13b
0x140009e4e  jz      loc_140009EF5
0x140009e54  mov     rax, [rdi+0F0h]
0x140009e5b  mov     [rbp+57h+var_80], rax
0x140009e5f  mov     rcx, [rdi+0F8h]
0x140009e66  sub     rcx, rax
0x140009e69  sar     rcx, 1
0x140009e6c  mov     [rbp+57h+var_78], rcx
0x140009e70  lea     r8, [rbp+57h+var_80]
0x140009e74  lea     rdx, aHelplink; "HelpLink"
0x140009e7b  mov     rcx, [rdi]
0x140009e7e  call    ?RegWriteStringValueNoThrow@@YAJPEAUHKEY__@@PEB_WV?$basic_cstring_view@_WU?$char_traits@_W@utl@@@tlx@@@Z; RegWriteStringValueNoThrow(HKEY__ *,wchar_t const *,tlx::basic_cstring_view<wchar_t,utl::char_traits<wchar_t>>)
0x140009e83  mov     ebx, eax
0x140009e85  test    eax, eax
0x140009e87  jz      short loc_140009EF5
0x140009e89  lea     rcx, WPP_GLOBAL_Control
0x140009e90  mov     r10, cs:WPP_GLOBAL_Control
0x140009e97  cmp     r10, rcx
0x140009e9a  jz      short loc_140009EC2
0x140009e9c  test    byte ptr [r10+1Ch], 4
0x140009ea1  jz      short loc_140009EC2
0x140009ea3  cmp     byte ptr [r10+19h], 2
0x140009ea8  jb      short loc_140009EC2
0x140009eaa  mov     edx, 10h
0x140009eaf  mov     r9d, eax
0x140009eb2  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009eb9  mov     rcx, [r10+10h]
0x140009ebd  call    WPP_SF_d
0x140009ec2  lea     rax, word_14003838A
0x140009ec9  mov     [rbp+57h+pExceptionObject], rax
0x140009ecd  mov     [rbp+57h+var_A8], r13
0x140009ed1  mov     [rbp+57h+var_A0], r13
0x140009ed5  mov     [rbp+57h+var_98], ebx
0x140009ed8  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009ee0  mov     [rbp+57h+var_8C], r13b
0x140009ee4  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009eeb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009eef  call    _CxxThrowException_0
0x140009ef5  cmp     [rdi+14Fh], r13b
0x140009efc  jz      loc_140009FAE
0x140009f02  mov     eax, r13d
0x140009f05  cmp     [rdi+148h], r13b
0x140009f0c  setnz   al
0x140009f0f  mov     dword ptr [rbp+57h+Data], eax
0x140009f12  mov     [rsp+0F0h+cbData], 4; cbData
0x140009f1a  lea     rax, [rbp+57h+Data]
0x140009f1e  mov     [rsp+0F0h+lpData], rax; lpData
0x140009f23  mov     r9d, 4; dwType
0x140009f29  xor     r8d, r8d; Reserved
0x140009f2c  lea     rdx, aEnabled; "Enabled"
0x140009f33  mov     rcx, [rdi]; hKey
0x140009f36  call    cs:__imp_RegSetValueExW
0x140009f3c  mov     ebx, eax
0x140009f3e  test    eax, eax
0x140009f40  jz      short loc_140009FAE
0x140009f42  lea     rcx, WPP_GLOBAL_Control
0x140009f49  mov     r10, cs:WPP_GLOBAL_Control
0x140009f50  cmp     r10, rcx
0x140009f53  jz      short loc_140009F7B
0x140009f55  test    byte ptr [r10+1Ch], 4
0x140009f5a  jz      short loc_140009F7B
0x140009f5c  cmp     byte ptr [r10+19h], 2
0x140009f61  jb      short loc_140009F7B
0x140009f63  mov     edx, 11h
0x140009f68  mov     r9d, eax
0x140009f6b  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x140009f72  mov     rcx, [r10+10h]
0x140009f76  call    WPP_SF_d
0x140009f7b  lea     rax, word_14003838A
0x140009f82  mov     [rbp+57h+pExceptionObject], rax
0x140009f86  mov     [rbp+57h+var_A8], r13
0x140009f8a  mov     [rbp+57h+var_A0], r13
0x140009f8e  mov     [rbp+57h+var_98], ebx
0x140009f91  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x140009f99  mov     [rbp+57h+var_8C], r13b
0x140009f9d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140009fa4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140009fa8  call    _CxxThrowException_0
0x140009fae  cmp     [rdi+14Eh], r13b
0x140009fb5  jz      loc_14000A43A
0x140009fbb  mov     [rbp+57h+var_80], r13
0x140009fbf  mov     r8, [rdi+8]; void *
0x140009fc3  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x140009fca  mov     rcx, [rdi]; HKEY
0x140009fcd  call    ?RegDeleteKeyRecursive@@YAJPEAUHKEY__@@PEB_WPEAX@Z; RegDeleteKeyRecursive(HKEY__ *,wchar_t const *,void *)
0x140009fd2  mov     rbx, [rdi+8]
0x140009fd6  lea     rcx, [rbp+57h+var_80]
0x140009fda  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140009fdf  mov     [rsp+0F0h+var_C0], rbx; void *
0x140009fe4  mov     qword ptr [rsp+0F0h+cbData], r13; unsigned int *
0x140009fe9  mov     [rsp+0F0h+lpData], rax; HKEY *
0x140009fee  xor     r9d, r9d; struct _SECURITY_ATTRIBUTES *
0x140009ff1  mov     r8d, 2001Fh; unsigned int
0x140009ff7  lea     rdx, aChannelreferen_0; "ChannelReferences"
0x140009ffe  mov     rcx, [rdi]; HKEY
0x14000a001  call    ?CreateRegKey@@YAJPEAUHKEY__@@PEB_WKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU1@PEAKPEAX@Z; CreateRegKey(HKEY__ *,wchar_t const *,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *,void *)
0x14000a006  mov     ebx, eax
0x14000a008  test    eax, eax
0x14000a00a  jz      short loc_14000A078
0x14000a00c  lea     rcx, WPP_GLOBAL_Control
0x14000a013  mov     r10, cs:WPP_GLOBAL_Control
0x14000a01a  cmp     r10, rcx
0x14000a01d  jz      short loc_14000A045
0x14000a01f  test    byte ptr [r10+1Ch], 4
0x14000a024  jz      short loc_14000A045
0x14000a026  cmp     byte ptr [r10+19h], 2
0x14000a02b  jb      short loc_14000A045
0x14000a02d  mov     edx, 12h
0x14000a032  mov     r9d, eax
0x14000a035  lea     r8, WPP_06fac479fca53b99d55b1e2801ac1dd1_Traceguids
0x14000a03c  mov     rcx, [r10+10h]
0x14000a040  call    WPP_SF_d
0x14000a045  lea     rax, word_14003838A
0x14000a04c  mov     [rbp+57h+pExceptionObject], rax
0x14000a050  mov     [rbp+57h+var_A8], r13
0x14000a054  mov     [rbp+57h+var_A0], r13
0x14000a058  mov     [rbp+57h+var_98], ebx
0x14000a05b  mov     [rbp+57h+var_94], 0FFFFFFFFFFFFFFFFh
0x14000a063  mov     [rbp+57h+var_8C], r13b
0x14000a067  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000a06e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000a072  call    _CxxThrowException_0
0x14000a078  mov     r12, r13
0x14000a07b  mov     rdx, 0AAAAAAAAAAAAAAABh
0x14000a085  mov     r15, [rdi+130h]
0x14000a08c  mov     rcx, [rdi+138h]
0x14000a093  mov     rax, rcx
0x14000a096  sub     rax, r15
0x14000a099  sar     rax, 4
0x14000a09d  imul    rax, rdx
0x14000a0a1  cmp     r12, rax
0x14000a0a4  jnb     loc_14000A37C
0x14000a0aa  lea     r13, [r12+r12*2]
  ... truncated ...
```
