# ChannelConfigReader::GetChannelAccessSddl(void)

- ea: `0x140006de0`
- end: `0x140007306`
- name: `?GetChannelAccessSddl@ChannelConfigReader@@QEBA?AV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@XZ`
- size: `1318`
- prototype: `__int64 __fastcall(ChannelConfigReader *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1400073ec`

## callees

- `0x140004ae0`
- `0x140005600`
- `0x140005620`
- `0x140006cd0`
- `0x140006db0`
- `0x140006de0`
- `0x140007fd0`
- `0x140008b40`
- `0x14000d6e8`
- `0x140015878`
- `0x14001915c`
- `0x140019348`
- `0x14001aec0`
- `0x14001b1f8`
- `0x140022cec`
- `0x14002bc70`
- `0x14002c768`
- `0x14002f6c8`
- `0x140031810`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006fc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000722f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x140006fc7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x14000722f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007251`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007251`

## string_xrefs

- `0x140006f3a`: `ChannelAccess`
- `0x140006ff5`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
LPCWSTR *__fastcall ChannelConfigReader::GetChannelAccessSddl(ChannelConfigReader *this, LPCWSTR *a2)
{
  char v4; // r12
  const struct _EVT_VARIANT *Property; // rax
  const char *v6; // r8
  HKEY v7; // rcx
  unsigned int v8; // eax
  const char *v9; // r8
  unsigned int v10; // ebx
  bool v11; // r14
  unsigned int StringValueNoThrow; // eax
  const char *v13; // r8
  unsigned int v14; // ebx
  PSECURITY_DESCRIPTOR *v15; // rax
  wchar_t *v16; // r15
  __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned int EventlogServiceRegPath; // ebx
  const char *v20; // r8
  const char *v21; // r8
  void *v22; // rbx
  HKEY *v23; // rax
  PSECURITY_DESCRIPTOR *v24; // rax
  enum _EVT_CHANNEL_ISOLATION_TYPE Isolation; // eax
  __int64 v26; // r8
  const char *v27; // r8
  wchar_t *v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h]
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v32; // [rsp+78h] [rbp+Fh]
  __int64 v33; // [rsp+7Ch] [rbp+13h]
  char v34; // [rsp+84h] [rbp+1Bh]
  HKEY hKey; // [rsp+D0h] [rbp+67h] BYREF
  LPCWSTR *v36; // [rsp+D8h] [rbp+6Fh]
  HKEY v37; // [rsp+E0h] [rbp+77h] BYREF

  v36 = a2;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(a2);
  v4 = 1;
  if ( *((_BYTE *)this + 128) )
  {
    Property = ChannelPolicy::GetProperty((ChannelConfigReader *)((char *)this + 64), EvtChannelConfigAccess);
    if ( Property )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a2,
                               Property->Int64Val,
                               Property->Count) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v6, 580);
        throw (EvtException *)pExceptionObject;
      }
      goto LABEL_25;
    }
  }
  v7 = *(HKEY *)this;
  if ( *((_BYTE *)this + 140) != 1 )
  {
    StringValueNoThrow = RegReadStringValueNoThrow(v7);
    v14 = StringValueNoThrow;
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
            WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
            StringValueNoThrow);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v14, v13, 618);
        throw (EvtException *)pExceptionObject;
      }
      goto LABEL_12;
    }
LABEL_25:
    hKey = 0;
    v15 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&hKey);
    v11 = ConvertStringSecurityDescriptorToSecurityDescriptorW(*a2, 1u, v15, 0);
    tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&hKey);
    goto LABEL_26;
  }
  v8 = RegReadStringValueNoThrow(v7);
  v10 = v8;
  if ( !v8 )
    goto LABEL_25;
  if ( v8 != 2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, v8);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v10, v9, 602);
    throw (EvtException *)pExceptionObject;
  }
LABEL_12:
  v11 = 0;
LABEL_26:
  v16 = (wchar_t *)*((_QWORD *)this + 4);
  v17 = (__int64)(*((_QWORD *)this + 5) - (_QWORD)v16) >> 1;
  if ( v17 != 8
    || (unsigned int)tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(
                       *((_QWORD *)this + 4),
                       L"Security",
                       8) )
  {
    v4 = 0;
  }
  if ( !v11 )
  {
    v29 = v16;
    v30 = v17;
    if ( (unsigned __int8)IsCoreChannel(&v29) )
      goto LABEL_56;
    v37 = 0;
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v29);
    EventlogServiceRegPath = RegistryPaths::GetEventlogServiceRegPath(v18, &v37, &v29);
    if ( EventlogServiceRegPath )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids,
          EventlogServiceRegPath);
      }
      pExceptionObject[0] = word_14003838A;
      pExceptionObject[1] = 0;
      pExceptionObject[2] = 0;
      v32 = EventlogServiceRegPath;
      v33 = -1;
      v34 = 0;
      throw (EvtException *)pExceptionObject;
    }
    if ( ChannelConfigReader::GetIsolation(this) == EvtChannelIsolationTypeSystem )
    {
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                               &v29,
                               L"\\System",
                               7) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v20, 651);
        throw (EvtException *)pExceptionObject;
      }
    }
    else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                  &v29,
                                  L"\\Application",
                                  12) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
      }
      EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v21, 658);
      throw (EvtException *)pExceptionObject;
    }
    hKey = 0;
    v22 = (void *)*((_QWORD *)this + 3);
    v23 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( !OpenRegKey(v37, v29, 0x20019u, v23, v22) && !(unsigned int)RegReadStringValueNoThrow(hKey) )
    {
      v37 = 0;
      v24 = (PSECURITY_DESCRIPTOR *)tlx::replace<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v37);
      v11 = ConvertStringSecurityDescriptorToSecurityDescriptorW(*a2, 1u, v24, 0);
      tlx::unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&void * LocalFree(void *),0>>(&v37);
    }
    if ( hKey )
      RegCloseKey(hKey);
    utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(&v29);
    if ( !v11 )
    {
LABEL_56:
      Isolation = ChannelConfigReader::GetIsolation(this);
      LOBYTE(v26) = v4;
      GetDefaultSDDL(&v29, (unsigned int)Isolation, v26);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a2,
                               v29,
                               v30) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids, 14);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, 0xEu, v27, 689);
        throw (EvtException *)pExceptionObject;
      }
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140006de0  mov     [rsp-8+arg_8], rdx
0x140006de5  push    rbp
0x140006de6  push    rbx
0x140006de7  push    rsi
0x140006de8  push    rdi
0x140006de9  push    r12
0x140006deb  push    r14
0x140006ded  push    r15
0x140006def  lea     rbp, [rsp-27h]
0x140006df4  sub     rsp, 90h
0x140006dfb  mov     rdi, rdx
0x140006dfe  mov     rsi, rcx
0x140006e01  mov     [rbp+57h+var_90], 0
0x140006e08  mov     rcx, rdx
0x140006e0b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140006e10  mov     r12d, 1
0x140006e16  mov     [rbp+57h+var_90], r12d
0x140006e1a  cmp     byte ptr [rsi+80h], 0
0x140006e21  jz      loc_140006EAD
0x140006e27  lea     rcx, [rsi+40h]; this
0x140006e2b  lea     edx, [r12+4]; enum _EVT_CHANNEL_CONFIG_PROPERTY_ID
0x140006e30  call    ?GetProperty@ChannelPolicy@@QEBAPEBU_EVT_VARIANT@@W4_EVT_CHANNEL_CONFIG_PROPERTY_ID@@@Z; ChannelPolicy::GetProperty(_EVT_CHANNEL_CONFIG_PROPERTY_ID)
0x140006e35  test    rax, rax
0x140006e38  jz      short loc_140006EAD
0x140006e3a  mov     r8d, [rax+8]
0x140006e3e  mov     rdx, [rax]
0x140006e41  mov     rcx, rdi
0x140006e44  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140006e49  test    al, al
0x140006e4b  jnz     loc_140006FAA
0x140006e51  lea     rax, WPP_GLOBAL_Control
0x140006e58  lea     ebx, [r12+0Dh]
0x140006e5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e64  cmp     rcx, rax
0x140006e67  jz      short loc_140006E8B
0x140006e69  test    byte ptr [rcx+1Ch], 4
0x140006e6d  jz      short loc_140006E8B
0x140006e6f  cmp     byte ptr [rcx+19h], 2
0x140006e73  jb      short loc_140006E8B
0x140006e75  lea     edx, [rbx+1Ah]
0x140006e78  mov     r9d, ebx
0x140006e7b  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140006e82  mov     rcx, [rcx+10h]
0x140006e86  call    WPP_SF_d
0x140006e8b  mov     r9d, 244h; int
0x140006e91  mov     edx, ebx; unsigned int
0x140006e93  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140006e97  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140006e9c  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006ea3  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006ea7  call    _CxxThrowException_0
0x140006ead  mov     r9, rdi
0x140006eb0  xor     edx, edx
0x140006eb2  mov     rcx, [rsi]; hKey
0x140006eb5  cmp     [rsi+8Ch], r12b
0x140006ebc  jnz     short loc_140006F3A
0x140006ebe  lea     r8, aCustomsd; "CustomSD"
0x140006ec5  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140006eca  mov     ebx, eax
0x140006ecc  test    eax, eax
0x140006ece  jz      loc_140006FAA
0x140006ed4  cmp     eax, 2
0x140006ed7  jnz     short loc_140006EE1
0x140006ed9  xor     r14b, r14b
0x140006edc  jmp     loc_140006FDC
0x140006ee1  lea     rax, WPP_GLOBAL_Control
0x140006ee8  mov     rcx, cs:WPP_GLOBAL_Control
0x140006eef  cmp     rcx, rax
0x140006ef2  jz      short loc_140006F18
0x140006ef4  test    byte ptr [rcx+1Ch], 4
0x140006ef8  jz      short loc_140006F18
0x140006efa  cmp     byte ptr [rcx+19h], 2
0x140006efe  jb      short loc_140006F18
0x140006f00  mov     edx, 29h ; ')'
0x140006f05  mov     r9d, ebx
0x140006f08  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140006f0f  mov     rcx, [rcx+10h]
0x140006f13  call    WPP_SF_d
0x140006f18  mov     r9d, 25Ah; int
0x140006f1e  mov     edx, ebx; unsigned int
0x140006f20  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140006f24  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140006f29  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006f30  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006f34  call    _CxxThrowException_0
0x140006f3a  lea     r8, aChannelaccess_0; "ChannelAccess"
0x140006f41  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x140006f46  mov     ebx, eax
0x140006f48  test    eax, eax
0x140006f4a  jz      short loc_140006FAA
0x140006f4c  cmp     eax, 2
0x140006f4f  jz      short loc_140006ED9
0x140006f51  lea     rax, WPP_GLOBAL_Control
0x140006f58  mov     rcx, cs:WPP_GLOBAL_Control
0x140006f5f  cmp     rcx, rax
0x140006f62  jz      short loc_140006F88
0x140006f64  test    byte ptr [rcx+1Ch], 4
0x140006f68  jz      short loc_140006F88
0x140006f6a  cmp     byte ptr [rcx+19h], 2
0x140006f6e  jb      short loc_140006F88
0x140006f70  mov     edx, 2Ah ; '*'
0x140006f75  mov     r9d, ebx
0x140006f78  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140006f7f  mov     rcx, [rcx+10h]
0x140006f83  call    WPP_SF_d
0x140006f88  mov     r9d, 26Ah; int
0x140006f8e  mov     edx, ebx; unsigned int
0x140006f90  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140006f94  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140006f99  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140006fa0  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140006fa4  call    _CxxThrowException_0
0x140006faa  mov     [rbp+57h+hKey], 0
0x140006fb2  lea     rcx, [rbp+57h+hKey]
0x140006fb6  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x140006fbb  xor     r9d, r9d; SecurityDescriptorSize
0x140006fbe  mov     r8, rax; SecurityDescriptor
0x140006fc1  mov     edx, r12d; StringSDRevision
0x140006fc4  mov     rcx, [rdi]; StringSecurityDescriptor
0x140006fc7  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140006fcd  test    eax, eax
0x140006fcf  setnz   r14b
0x140006fd3  lea     rcx, [rbp+57h+hKey]
0x140006fd7  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x140006fdc  mov     r15, [rsi+20h]
0x140006fe0  mov     rbx, [rsi+28h]
0x140006fe4  sub     rbx, r15
0x140006fe7  sar     rbx, 1
0x140006fea  mov     r8d, 8
0x140006ff0  cmp     rbx, r8
0x140006ff3  jnz     short loc_140007008
0x140006ff5  lea     rdx, aSecurity; "Security"
0x140006ffc  mov     rcx, r15
0x140006fff  call    ?compare@?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@SAHPEB_W0_K@Z; tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>::compare(wchar_t const *,wchar_t const *,unsigned __int64)
0x140007004  test    eax, eax
0x140007006  jz      short loc_14000700B
0x140007008  xor     r12b, r12b
0x14000700b  test    r14b, r14b
0x14000700e  jnz     loc_1400072F0
0x140007014  mov     [rbp+57h+var_80], r15
0x140007018  mov     [rbp+57h+var_78], rbx
0x14000701c  lea     rcx, [rbp+57h+var_80]
0x140007020  call    ?IsCoreChannel@@YA_NV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; IsCoreChannel(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x140007025  test    al, al
0x140007027  jnz     loc_14000726A
0x14000702d  mov     [rbp+57h+arg_10], 0
0x140007035  lea     rcx, [rbp+57h+var_80]
0x140007039  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x14000703e  nop
0x14000703f  lea     r8, [rbp+57h+var_80]
0x140007043  lea     rdx, [rbp+57h+arg_10]
0x140007047  call    ?GetEventlogServiceRegPath@RegistryPaths@@QEBAKAEAPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegistryPaths::GetEventlogServiceRegPath(HKEY__ * &,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14000704c  mov     ebx, eax
0x14000704e  test    eax, eax
0x140007050  jz      short loc_1400070C4
0x140007052  lea     rax, WPP_GLOBAL_Control
0x140007059  mov     rcx, cs:WPP_GLOBAL_Control
0x140007060  cmp     rcx, rax
0x140007063  jz      short loc_140007089
0x140007065  test    byte ptr [rcx+1Ch], 4
0x140007069  jz      short loc_140007089
0x14000706b  cmp     byte ptr [rcx+19h], 2
0x14000706f  jb      short loc_140007089
0x140007071  mov     edx, 2Bh ; '+'
0x140007076  mov     r9d, ebx
0x140007079  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140007080  mov     rcx, [rcx+10h]
0x140007084  call    WPP_SF_d
0x140007089  lea     rax, word_14003838A
0x140007090  mov     [rbp+57h+pExceptionObject], rax
0x140007094  mov     [rbp+57h+var_58], 0
0x14000709c  mov     [rbp+57h+var_50], 0
0x1400070a4  mov     [rbp+57h+var_48], ebx
0x1400070a7  mov     [rbp+57h+var_44], 0FFFFFFFFFFFFFFFFh
0x1400070af  mov     [rbp+57h+var_3C], 0
0x1400070b3  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400070ba  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400070be  call    _CxxThrowException_0
0x1400070c4  mov     rcx, rsi; this
0x1400070c7  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x1400070cc  mov     r15d, 1
0x1400070d2  lea     rcx, [rbp+57h+var_80]
0x1400070d6  cmp     eax, r15d
0x1400070d9  jnz     short loc_14000714E
0x1400070db  lea     r8d, [r15+6]
0x1400070df  lea     rdx, aSystem_0; "\\System"
0x1400070e6  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x1400070eb  test    al, al
0x1400070ed  jnz     loc_1400071C0
0x1400070f3  lea     rax, WPP_GLOBAL_Control
0x1400070fa  lea     ebx, [r15+0Dh]
0x1400070fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140007105  cmp     rcx, rax
0x140007108  jz      short loc_14000712C
0x14000710a  test    byte ptr [rcx+1Ch], 4
0x14000710e  jz      short loc_14000712C
0x140007110  cmp     byte ptr [rcx+19h], 2
0x140007114  jb      short loc_14000712C
0x140007116  lea     edx, [rbx+1Eh]
0x140007119  mov     r9d, ebx
0x14000711c  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140007123  mov     rcx, [rcx+10h]
0x140007127  call    WPP_SF_d
0x14000712c  mov     r9d, 28Bh; int
0x140007132  mov     edx, ebx; unsigned int
0x140007134  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140007138  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x14000713d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140007144  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140007148  call    _CxxThrowException_0
0x14000714e  mov     r8d, 0Ch
0x140007154  lea     rdx, aApplication_0; "\\Application"
0x14000715b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140007160  test    al, al
0x140007162  jnz     short loc_1400071C0
0x140007164  lea     rax, WPP_GLOBAL_Control
0x14000716b  mov     ebx, 0Eh
0x140007170  mov     rcx, cs:WPP_GLOBAL_Control
0x140007177  cmp     rcx, rax
0x14000717a  jz      short loc_14000719E
0x14000717c  test    byte ptr [rcx+1Ch], 4
0x140007180  jz      short loc_14000719E
0x140007182  cmp     byte ptr [rcx+19h], 2
0x140007186  jb      short loc_14000719E
0x140007188  lea     edx, [rbx+1Fh]
0x14000718b  mov     r9d, ebx
0x14000718e  lea     r8, WPP_c48059e15e75394e52a4a5bf0b0c8bc4_Traceguids
0x140007195  mov     rcx, [rcx+10h]
0x140007199  call    WPP_SF_d
0x14000719e  mov     r9d, 292h; int
0x1400071a4  mov     edx, ebx; unsigned int
0x1400071a6  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1400071aa  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x1400071af  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1400071b6  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1400071ba  call    _CxxThrowException_0
0x1400071c0  mov     [rbp+57h+hKey], 0
0x1400071c8  mov     rbx, [rsi+18h]
0x1400071cc  lea     rcx, [rbp+57h+hKey]
0x1400071d0  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400071d5  mov     [rsp+0C0h+var_A0], rbx; void *
0x1400071da  mov     r9, rax; HKEY *
0x1400071dd  mov     r8d, 20019h; unsigned int
0x1400071e3  mov     rdx, [rbp+57h+var_80]; wchar_t *
0x1400071e7  mov     rcx, [rbp+57h+arg_10]; HKEY
0x1400071eb  call    ?OpenRegKey@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@PEAX@Z; OpenRegKey(HKEY__ *,wchar_t const *,ulong,HKEY__ * *,void *)
0x1400071f0  test    eax, eax
0x1400071f2  jnz     short loc_140007248
0x1400071f4  mov     r9, rdi
0x1400071f7  lea     r8, aCustomsd; "CustomSD"
0x1400071fe  lea     rdx, ValueName
0x140007205  mov     rcx, [rbp+57h+hKey]; hKey
0x140007209  call    ?RegReadStringValueNoThrow@@YAJPEAUHKEY__@@PEB_W1AEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; RegReadStringValueNoThrow(HKEY__ *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)
0x14000720e  test    eax, eax
0x140007210  jnz     short loc_140007248
0x140007212  mov     [rbp+57h+arg_10], 0
0x14000721a  lea     rcx, [rbp+57h+arg_10]
0x14000721e  call    ??$replace@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>> &)
0x140007223  xor     r9d, r9d; SecurityDescriptorSize
0x140007226  mov     r8, rax; SecurityDescriptor
0x140007229  mov     edx, r15d; StringSDRevision
0x14000722c  mov     rcx, [rdi]; StringSecurityDescriptor
0x14000722f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x140007235  movzx   r14d, r14b
0x140007239  test    eax, eax
0x14000723b  cmovnz  r14d, r15d
0x14000723f  lea     rcx, [rbp+57h+arg_10]
0x140007243  call    ??1?$unique_any@U?$handle_traits@PEAX$$A6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>::~unique_any<tlx::handle_traits<void *,void * (void *),&LocalFree(void *),0>>(void)
0x140007248  mov     rcx, [rbp+57h+hKey]; hKey
0x14000724c  test    rcx, rcx
0x14000724f  jz      short loc_140007258
0x140007251  call    cs:__imp_RegCloseKey
0x140007257  nop
0x140007258  lea     rcx, [rbp+57h+var_80]
0x14000725c  call    ??1?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::~basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x140007261  test    r14b, r14b
0x140007264  jnz     loc_1400072F0
0x14000726a  mov     rcx, rsi; this
0x14000726d  call    ?GetIsolation@ChannelConfigReader@@QEBA?AW4_EVT_CHANNEL_ISOLATION_TYPE@@XZ; ChannelConfigReader::GetIsolation(void)
0x140007272  mov     edx, eax
0x140007274  mov     r8b, r12b
0x140007277  lea     rcx, [rbp+57h+var_80]
0x14000727b  call    ?GetDefaultSDDL@@YA?AV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@K_N@Z; GetDefaultSDDL(ulong,bool)
0x140007280  mov     r8, [rbp+57h+var_78]
0x140007284  mov     rdx, [rbp+57h+var_80]
0x140007288  mov     rcx, rdi
0x14000728b  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140007290  test    al, al
0x140007292  jnz     short loc_1400072F0
0x140007294  lea     rax, WPP_GLOBAL_Control
0x14000729b  mov     ebx, 0Eh
0x1400072a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400072a7  cmp     rcx, rax
0x1400072aa  jz      short loc_1400072CE
0x1400072ac  test    byte ptr [rcx+1Ch], 4
0x1400072b0  jz      short loc_1400072CE
0x1400072b2  cmp     byte ptr [rcx+19h], 2
0x1400072b6  jb      short loc_1400072CE
0x1400072b8  lea     edx, [rbx+20h]
0x1400072bb  mov     r9d, ebx
  ... truncated ...
```
