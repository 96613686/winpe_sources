# ChannelConfigReader::GetChannelAccessSddl(void)

- ea: `0x180057870`
- end: `0x180057dc6`
- name: `?GetChannelAccessSddl@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ`
- size: `1366`
- prototype: `__int64 __fastcall(ChannelConfigReader *this)`
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180057e30`
- `0x1800840c8`

## callees

- `0x180006600`
- `0x180006770`
- `0x180009260`
- `0x180014bd0`
- `0x180017b60`
- `0x180017b98`
- `0x180017e28`
- `0x18002c6f4`
- `0x18002d204`
- `0x18002d6dc`
- `0x18003ee78`
- `0x180047fd8`
- `0x1800573b4`
- `0x180057870`
- `0x180074cf0`
- `0x180083f2c`
- `0x180089878`
- `0x180092008`
- `0x1800d334c`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180057a81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180057ce0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180057a81`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180057ce0`

## string_xrefs

- `0x1800579e8`: `ChannelAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPCWSTR *__fastcall ChannelConfigReader::GetChannelAccessSddl(ChannelConfigReader *this, LPCWSTR *a2)
{
  const struct _EVT_VARIANT *Property; // rax
  HKEY v5; // rcx
  unsigned int v6; // eax
  int v7; // ebx
  bool v8; // r14
  unsigned int StringValueNoThrow; // eax
  int v10; // ebx
  PSECURITY_DESCRIPTOR *v11; // rax
  wchar_t *v12; // r15
  __int64 v13; // rbx
  char v14; // r12
  __int64 v15; // rcx
  unsigned int EventlogServiceRegPath; // ebx
  void *v17; // rbx
  HKEY *v18; // rax
  PSECURITY_DESCRIPTOR *v19; // rax
  enum _EVT_CHANNEL_ISOLATION_TYPE Isolation; // eax
  __int64 v21; // r8
  wchar_t *v23; // [rsp+40h] [rbp-29h] BYREF
  __int64 v24; // [rsp+48h] [rbp-21h]
  __int128 pExceptionObject; // [rsp+60h] [rbp-9h] BYREF
  __int64 v26; // [rsp+70h] [rbp+7h]
  int v27; // [rsp+78h] [rbp+Fh]
  __int64 v28; // [rsp+7Ch] [rbp+13h]
  char v29; // [rsp+84h] [rbp+1Bh]
  HKEY hKey; // [rsp+D0h] [rbp+67h] BYREF
  LPCWSTR *v31; // [rsp+D8h] [rbp+6Fh]
  HKEY v32; // [rsp+E0h] [rbp+77h] BYREF

  v31 = a2;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2);
  if ( *((_BYTE *)this + 128) )
  {
    Property = ChannelPolicy::GetProperty((ChannelConfigReader *)((char *)this + 64), EvtChannelConfigAccess);
    if ( Property )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a2,
                               Property->Int64Val) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids, 14);
        }
        pExceptionObject = 0;
        v26 = 0;
        v27 = 14;
        v28 = 0x244FFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
      goto LABEL_25;
    }
  }
  v5 = *(HKEY *)this;
  if ( *((_BYTE *)this + 140) != 1 )
  {
    StringValueNoThrow = RegReadStringValueNoThrow(v5);
    v10 = StringValueNoThrow;
    if ( StringValueNoThrow )
    {
      if ( StringValueNoThrow != 2 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids,
            StringValueNoThrow);
        }
        pExceptionObject = 0;
        v26 = 0;
        v27 = v10;
        v28 = 0x26AFFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
      goto LABEL_12;
    }
LABEL_25:
    hKey = 0;
    v11 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&hKey);
    v8 = ConvertStringSecurityDescriptorToSecurityDescriptorW(*a2, 1u, v11, 0);
    tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&hKey);
    goto LABEL_26;
  }
  v6 = RegReadStringValueNoThrow(v5);
  v7 = v6;
  if ( !v6 )
    goto LABEL_25;
  if ( v6 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids, v6);
    }
    pExceptionObject = 0;
    v26 = 0;
    v27 = v7;
    v28 = 0x25AFFFFFFFFLL;
    throw (EvtException *)&pExceptionObject;
  }
LABEL_12:
  v8 = 0;
LABEL_26:
  v12 = (wchar_t *)*((_QWORD *)this + 4);
  v13 = (__int64)(*((_QWORD *)this + 5) - (_QWORD)v12) >> 1;
  v23 = v12;
  v24 = v13;
  v14 = IsSecurityChannel(&v23);
  if ( !v8 )
  {
    v23 = v12;
    v24 = v13;
    if ( (unsigned __int8)IsCoreChannel(&v23) )
      goto LABEL_51;
    v32 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v23);
    EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v15, &v32, &v23);
    if ( EventlogServiceRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids,
          EventlogServiceRegPath);
      }
      *(_QWORD *)&pExceptionObject = &word_1800EC961;
      *((_QWORD *)&pExceptionObject + 1) = 0;
      v26 = 0;
      v27 = EventlogServiceRegPath;
      v28 = -1;
      v29 = 0;
      throw (EvtException *)&pExceptionObject;
    }
    if ( ChannelConfigReader::GetIsolation(this) == EvtChannelIsolationTypeSystem )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&v23) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids, 14);
        }
        pExceptionObject = 0;
        v26 = 0;
        v27 = 14;
        v28 = 0x28BFFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
    }
    else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(&v23) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids, 14);
      }
      pExceptionObject = 0;
      v26 = 0;
      v27 = 14;
      v28 = 0x292FFFFFFFFLL;
      throw (EvtException *)&pExceptionObject;
    }
    hKey = 0;
    v17 = (void *)*((_QWORD *)this + 3);
    v18 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( !OpenRegKey(v32, v23, 0x20019u, v18, v17) && !(unsigned int)RegReadStringValueNoThrow(hKey) )
    {
      v32 = 0;
      v19 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v32);
      v8 = ConvertStringSecurityDescriptorToSecurityDescriptorW(*a2, 1u, v19, 0);
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v32);
    }
    tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&v23);
    if ( !v8 )
    {
LABEL_51:
      Isolation = ChannelConfigReader::GetIsolation(this);
      LOBYTE(v21) = v14;
      GetDefaultSDDL(&v23, (unsigned int)Isolation, v21);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a2,
                               v23) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids, 14);
        }
        pExceptionObject = 0;
        v26 = 0;
        v27 = 14;
        v28 = 0x2B1FFFFFFFFLL;
        throw (EvtException *)&pExceptionObject;
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180057870  mov     [rsp-8+arg_18], rbx
0x180057875  mov     [rsp-8+arg_8], rdx
0x18005787a  push    rbp
0x18005787b  push    rsi
0x18005787c  push    rdi
0x18005787d  push    r12
0x18005787f  push    r13
0x180057881  push    r14
0x180057883  push    r15
0x180057885  lea     rbp, [rsp-27h]
0x18005788a  sub     rsp, 90h
0x180057891  mov     rdi, rdx
0x180057894  mov     rsi, rcx
0x180057897  xor     r13d, r13d
0x18005789a  mov     [rbp+57h+var_90], r13d
0x18005789e  mov     rcx, rdx; void *
0x1800578a1  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x1800578a6  lea     r14d, [r13+1]
0x1800578aa  mov     [rbp+57h+var_90], r14d
0x1800578ae  cmp     [rsi+80h], r13b
0x1800578b5  jz      loc_18005794B
0x1800578bb  lea     rcx, [rsi+40h]; this
0x1800578bf  lea     edx, [r13+5]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x1800578c3  call    ?GetProperty@ChannelPolicy@@QEBAPEBU_EVT_VARIANT@@W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; ChannelPolicy::GetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x1800578c8  test    rax, rax
0x1800578cb  jz      short loc_18005794B
0x1800578cd  mov     r8d, [rax+8]
0x1800578d1  mov     rdx, [rax]
0x1800578d4  mov     rcx, rdi
0x1800578d7  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800578dc  test    al, al
0x1800578de  jnz     loc_180057A68
0x1800578e4  lea     rax, WPP_GLOBAL_Control
0x1800578eb  lea     ebx, [r13+0Eh]
0x1800578ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578f6  cmp     rcx, rax
0x1800578f9  jz      short loc_18005791D
0x1800578fb  test    byte ptr [rcx+1Ch], 4
0x1800578ff  jz      short loc_18005791D
0x180057901  cmp     byte ptr [rcx+19h], 2
0x180057905  jb      short loc_18005791D
0x180057907  lea     edx, [rbx+1Ah]
0x18005790a  mov     r9d, ebx
0x18005790d  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x180057914  mov     rcx, [rcx+10h]
0x180057918  call    WPP_SF_d
0x18005791d  xorps   xmm0, xmm0
0x180057920  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180057925  mov     [rbp+57h+var_50], r13
0x180057929  mov     [rbp+57h+var_48], ebx
0x18005792c  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x180057933  mov     dword ptr [rbp+57h+var_44+4], 244h
0x18005793a  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180057941  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057945  call    _CxxThrowException_0
0x18005794b  mov     r9, rdi
0x18005794e  xor     edx, edx
0x180057950  mov     rcx, [rsi]; hKey
0x180057953  cmp     [rsi+8Ch], r14b
0x18005795a  jnz     loc_1800579E8
0x180057960  lea     r8, aCustomsd; "CustomSD"
0x180057967  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x18005796c  mov     ebx, eax
0x18005796e  test    eax, eax
0x180057970  jz      loc_180057A68
0x180057976  cmp     eax, 2
0x180057979  jnz     short loc_180057983
0x18005797b  mov     r14b, r13b
0x18005797e  jmp     loc_180057A96
0x180057983  lea     rax, WPP_GLOBAL_Control
0x18005798a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057991  cmp     rcx, rax
0x180057994  jz      short loc_1800579BA
0x180057996  test    byte ptr [rcx+1Ch], 4
0x18005799a  jz      short loc_1800579BA
0x18005799c  cmp     byte ptr [rcx+19h], 2
0x1800579a0  jb      short loc_1800579BA
0x1800579a2  mov     edx, 29h ; ')'
0x1800579a7  mov     r9d, ebx
0x1800579aa  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x1800579b1  mov     rcx, [rcx+10h]
0x1800579b5  call    WPP_SF_d
0x1800579ba  xorps   xmm0, xmm0
0x1800579bd  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800579c2  mov     [rbp+57h+var_50], r13
0x1800579c6  mov     [rbp+57h+var_48], ebx
0x1800579c9  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x1800579d0  mov     dword ptr [rbp+57h+var_44+4], 25Ah
0x1800579d7  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800579de  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800579e2  call    _CxxThrowException_0
0x1800579e8  lea     r8, aChannelaccess; "ChannelAccess"
0x1800579ef  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x1800579f4  mov     ebx, eax
0x1800579f6  test    eax, eax
0x1800579f8  jz      short loc_180057A68
0x1800579fa  cmp     eax, 2
0x1800579fd  jz      loc_18005797B
0x180057a03  lea     rax, WPP_GLOBAL_Control
0x180057a0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a11  cmp     rcx, rax
0x180057a14  jz      short loc_180057A3A
0x180057a16  test    byte ptr [rcx+1Ch], 4
0x180057a1a  jz      short loc_180057A3A
0x180057a1c  cmp     byte ptr [rcx+19h], 2
0x180057a20  jb      short loc_180057A3A
0x180057a22  mov     edx, 2Ah ; '*'
0x180057a27  mov     r9d, ebx
0x180057a2a  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x180057a31  mov     rcx, [rcx+10h]
0x180057a35  call    WPP_SF_d
0x180057a3a  xorps   xmm0, xmm0
0x180057a3d  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180057a42  mov     [rbp+57h+var_50], r13
0x180057a46  mov     [rbp+57h+var_48], ebx
0x180057a49  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x180057a50  mov     dword ptr [rbp+57h+var_44+4], 26Ah
0x180057a57  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180057a5e  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057a62  call    _CxxThrowException_0
0x180057a68  mov     [rbp+57h+hKey], r13
0x180057a6c  lea     rcx, [rbp+57h+hKey]
0x180057a70  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x180057a75  xor     r9d, r9d; SecurityDescriptorSize
0x180057a78  mov     r8, rax; SecurityDescriptor
0x180057a7b  mov     edx, r14d; StringSDRevision
0x180057a7e  mov     rcx, [rdi]; StringSecurityDescriptor
0x180057a81  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180057a87  test    eax, eax
0x180057a89  setnz   r14b
0x180057a8d  lea     rcx, [rbp+57h+hKey]
0x180057a91  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x180057a96  mov     r15, [rsi+20h]
0x180057a9a  mov     rbx, [rsi+28h]
0x180057a9e  sub     rbx, r15
0x180057aa1  sar     rbx, 1
0x180057aa4  mov     [rbp+57h+var_80], r15
0x180057aa8  mov     [rbp+57h+var_78], rbx
0x180057aac  lea     rcx, [rbp+57h+var_80]
0x180057ab0  call    ?IsSecurityChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsSecurityChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180057ab5  mov     r12b, al
0x180057ab8  test    r14b, r14b
0x180057abb  jnz     loc_180057DA7
0x180057ac1  mov     [rbp+57h+var_80], r15
0x180057ac5  mov     [rbp+57h+var_78], rbx
0x180057ac9  lea     rcx, [rbp+57h+var_80]
0x180057acd  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x180057ad2  test    al, al
0x180057ad4  jnz     loc_180057D15
0x180057ada  mov     [rbp+57h+arg_10], r13
0x180057ade  lea     rcx, [rbp+57h+var_80]; void *
0x180057ae2  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180057ae7  nop
0x180057ae8  lea     r8, [rbp+57h+var_80]
0x180057aec  lea     rdx, [rbp+57h+arg_10]
0x180057af0  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180057af5  mov     ebx, eax
0x180057af7  test    eax, eax
0x180057af9  jz      short loc_180057B65
0x180057afb  lea     rax, WPP_GLOBAL_Control
0x180057b02  mov     rcx, cs:WPP_GLOBAL_Control
0x180057b09  cmp     rcx, rax
0x180057b0c  jz      short loc_180057B32
0x180057b0e  test    byte ptr [rcx+1Ch], 4
0x180057b12  jz      short loc_180057B32
0x180057b14  cmp     byte ptr [rcx+19h], 2
0x180057b18  jb      short loc_180057B32
0x180057b1a  mov     edx, 2Bh ; '+'
0x180057b1f  mov     r9d, ebx
0x180057b22  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x180057b29  mov     rcx, [rcx+10h]
0x180057b2d  call    WPP_SF_d
0x180057b32  lea     rax, word_1800EC961
0x180057b39  mov     qword ptr [rbp+57h+pExceptionObject], rax
0x180057b3d  mov     qword ptr [rbp+57h+pExceptionObject+8], r13
0x180057b41  mov     [rbp+57h+var_50], r13
0x180057b45  mov     [rbp+57h+var_48], ebx
0x180057b48  mov     [rbp+57h+var_44], 0FFFFFFFFFFFFFFFFh
0x180057b50  mov     [rbp+57h+var_3C], r13b
0x180057b54  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180057b5b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057b5f  call    _CxxThrowException_0
0x180057b65  mov     rcx, rsi; this
0x180057b68  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x180057b6d  mov     r15d, 1
0x180057b73  lea     rcx, [rbp+57h+var_80]
0x180057b77  cmp     eax, r15d
0x180057b7a  jnz     short loc_180057BFB
0x180057b7c  lea     r8d, [r15+6]
0x180057b80  lea     rdx, aSystem_0; "\\System"
0x180057b87  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180057b8c  test    al, al
0x180057b8e  jnz     loc_180057C79
0x180057b94  lea     rax, WPP_GLOBAL_Control
0x180057b9b  lea     ebx, [r15+0Dh]
0x180057b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ba6  cmp     rcx, rax
0x180057ba9  jz      short loc_180057BCD
0x180057bab  test    byte ptr [rcx+1Ch], 4
0x180057baf  jz      short loc_180057BCD
0x180057bb1  cmp     byte ptr [rcx+19h], 2
0x180057bb5  jb      short loc_180057BCD
0x180057bb7  lea     edx, [rbx+1Eh]
0x180057bba  mov     r9d, ebx
0x180057bbd  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x180057bc4  mov     rcx, [rcx+10h]
0x180057bc8  call    WPP_SF_d
0x180057bcd  xorps   xmm0, xmm0
0x180057bd0  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180057bd5  mov     [rbp+57h+var_50], r13
0x180057bd9  mov     [rbp+57h+var_48], ebx
0x180057bdc  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x180057be3  mov     dword ptr [rbp+57h+var_44+4], 28Bh
0x180057bea  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180057bf1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057bf5  call    _CxxThrowException_0
0x180057bfb  mov     r8d, 0Ch
0x180057c01  lea     rdx, aApplication_0; "\\Application"
0x180057c08  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x180057c0d  test    al, al
0x180057c0f  jnz     short loc_180057C79
0x180057c11  lea     rax, WPP_GLOBAL_Control
0x180057c18  mov     ebx, 0Eh
0x180057c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x180057c24  cmp     rcx, rax
0x180057c27  jz      short loc_180057C4B
0x180057c29  test    byte ptr [rcx+1Ch], 4
0x180057c2d  jz      short loc_180057C4B
0x180057c2f  cmp     byte ptr [rcx+19h], 2
0x180057c33  jb      short loc_180057C4B
0x180057c35  lea     edx, [rbx+1Fh]
0x180057c38  mov     r9d, ebx
0x180057c3b  lea     r8, WPP_fce5aba9dfe23a011ef02d9d3a753056_Traceguids
0x180057c42  mov     rcx, [rcx+10h]
0x180057c46  call    WPP_SF_d
0x180057c4b  xorps   xmm0, xmm0
0x180057c4e  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180057c53  mov     [rbp+57h+var_50], r13
0x180057c57  mov     [rbp+57h+var_48], ebx
0x180057c5a  mov     dword ptr [rbp+57h+var_44], 0FFFFFFFFh
0x180057c61  mov     dword ptr [rbp+57h+var_44+4], 292h
0x180057c68  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180057c6f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180057c73  call    _CxxThrowException_0
0x180057c79  mov     [rbp+57h+hKey], r13
0x180057c7d  mov     rbx, [rsi+18h]
0x180057c81  lea     rcx, [rbp+57h+hKey]
0x180057c85  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180057c8a  mov     [rsp+0C0h+var_A0], rbx; void *
0x180057c8f  mov     r9, rax; HKEY *
0x180057c92  mov     r8d, 20019h; unsigned int
0x180057c98  mov     rdx, [rbp+57h+var_80]; wchar_t *
0x180057c9c  mov     rcx, [rbp+57h+arg_10]; HKEY
0x180057ca0  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x180057ca5  test    eax, eax
0x180057ca7  jnz     short loc_180057CF9
0x180057ca9  mov     r9, rdi
0x180057cac  lea     r8, aCustomsd; "CustomSD"
0x180057cb3  lea     rdx, pszFormat
0x180057cba  mov     rcx, [rbp+57h+hKey]; hKey
0x180057cbe  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x180057cc3  test    eax, eax
0x180057cc5  jnz     short loc_180057CF9
0x180057cc7  mov     [rbp+57h+arg_10], r13
0x180057ccb  lea     rcx, [rbp+57h+arg_10]
0x180057ccf  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x180057cd4  xor     r9d, r9d; SecurityDescriptorSize
0x180057cd7  mov     r8, rax; SecurityDescriptor
0x180057cda  mov     edx, r15d; StringSDRevision
0x180057cdd  mov     rcx, [rdi]; StringSecurityDescriptor
0x180057ce0  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180057ce6  movzx   r14d, r14b
0x180057cea  test    eax, eax
0x180057cec  cmovnz  r14d, r15d
0x180057cf0  lea     rcx, [rbp+57h+arg_10]
0x180057cf4  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x180057cf9  lea     rcx, [rbp+57h+hKey]
0x180057cfd  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180057d02  nop
0x180057d03  lea     rcx, [rbp+57h+var_80]; void *
0x180057d07  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180057d0c  test    r14b, r14b
0x180057d0f  jnz     loc_180057DA7
0x180057d15  mov     rcx, rsi; this
0x180057d18  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x180057d1d  mov     edx, eax
0x180057d1f  mov     r8b, r12b
0x180057d22  lea     rcx, [rbp+57h+var_80]
0x180057d26  call    ?GetDefaultSDDL@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_N@Z; GetDefaultSDDL(ulong,bool)
0x180057d2b  mov     r8, [rbp+57h+var_78]
0x180057d2f  mov     rdx, [rbp+57h+var_80]
0x180057d33  mov     rcx, rdi
0x180057d36  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x180057d3b  test    al, al
0x180057d3d  jnz     short loc_180057DA7
0x180057d3f  lea     rax, WPP_GLOBAL_Control
0x180057d46  mov     ebx, 0Eh
0x180057d4b  mov     rcx, cs:WPP_GLOBAL_Control
0x180057d52  cmp     rcx, rax
0x180057d55  jz      short loc_180057D79
  ... truncated ...
```
