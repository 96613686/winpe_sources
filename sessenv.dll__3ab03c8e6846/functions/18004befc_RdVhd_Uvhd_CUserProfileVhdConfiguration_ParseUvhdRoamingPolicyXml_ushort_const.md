# RdVhd::Uvhd::CUserProfileVhdConfiguration::ParseUvhdRoamingPolicyXml(ushort const *)

- ea: `0x18004befc`
- end: `0x18004c70b`
- name: `?ParseUvhdRoamingPolicyXml@CUserProfileVhdConfiguration@Uvhd@RdVhd@@AEAAJPEBG@Z`
- size: `2063`
- prototype: `__int64 __fastcall(RdVhd::Uvhd::CUserProfileVhdConfiguration *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004bb9c`

## callees

- `0x180012d7c`
- `0x18002b5dc`
- `0x1800488e4`
- `0x180048b28`
- `0x18004b77c`
- `0x18004befc`
- `0x18004c714`
- `0x180057984`
- `0x18005d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c128`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c247`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c2eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c30d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c32f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c40e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c128`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c247`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c2eb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c30d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c32f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18004c40e`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18004c2cd`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18004c2cd`
- `XmlLite!CreateXmlReader` at `0x18004bf85`
- `XmlLite!CreateXmlReader` at `0x18004bf85`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18004c031`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateMemStream` at `0x18004c031`

## string_xrefs

- `0x18004bf5a`: `szRoamingPolicyXml`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUserProfileVhdConfiguration::ParseUvhdRoamingPolicyXml(
        RdVhd::Uvhd::CUserProfileVhdConfiguration *this,
        const unsigned __int16 *a2)
{
  HRESULT v4; // ebx
  RdVhd::Uvhd::CUvhdDiskManager *v5; // rcx
  __int64 v6; // rdx
  int v7; // eax
  RdVhd::Uvhd::CRemappedPath *v8; // rsi
  RdVhd::Uvhd::CRemappedPath *v9; // r14
  int i; // r15d
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  int v17; // eax
  RdVhd::Uvhd::CRemappedPath *v18; // rax
  RdVhd::Uvhd::CRemappedPath *v19; // rax
  unsigned int v20; // edi
  unsigned int v21; // edx
  void *ppvObject; // [rsp+20h] [rbp-20h] BYREF
  __int64 v24; // [rsp+28h] [rbp-18h] BYREF
  RdVhd::Uvhd::CRemappedPath *v25; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+38h] [rbp-8h] BYREF
  unsigned int v27; // [rsp+88h] [rbp+48h] BYREF
  unsigned __int64 cbInit; // [rsp+90h] [rbp+50h] BYREF
  IStream *v29; // [rsp+98h] [rbp+58h] BYREF

  v24 = 0;
  v27 = 0;
  v25 = 0;
  ppvObject = 0;
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        WPP_e8dd23dccea833ec9363436debfb788c_Traceguids,
        L"szRoamingPolicyXml");
    }
    v4 = -2147024809;
    goto LABEL_144;
  }
  v4 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(void *, __int64, _QWORD))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4, 0), v4 < 0) )
  {
    ATL::CComPtrBase<IXmlReader>::Release(&ppvObject);
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_144;
    }
    v6 = 28;
    goto LABEL_142;
  }
  v4 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 29;
      goto LABEL_142;
    }
    goto LABEL_144;
  }
  v29 = 0;
  cbInit = 0;
  v4 = StringCbLengthW(a2, 0xFFFFFFFE, &cbInit);
  if ( v4 >= 0 )
  {
    v29 = SHCreateMemStream((const BYTE *)a2, cbInit);
    if ( v29 )
      v4 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, v29);
    else
      v4 = -2147467259;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
  if ( v4 < 0 )
  {
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 30;
      goto LABEL_142;
    }
    goto LABEL_144;
  }
LABEL_23:
  while ( 2 )
  {
    if ( v4 != 1 )
    {
      LODWORD(cbInit) = 0;
      v4 = -2147023728;
      while ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
      {
        v7 = (*(__int64 (__fastcall **)(void *, unsigned __int64 *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &cbInit);
        v4 = v7;
        if ( v7 < 0 )
          break;
        if ( v7 == 1 )
          goto LABEL_23;
        if ( (_DWORD)cbInit == 1 )
          goto LABEL_32;
      }
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 31;
          goto LABEL_142;
        }
        goto LABEL_144;
      }
      if ( v4 == 1 )
        break;
LABEL_32:
      v4 = (*(__int64 (__fastcall **)(void *, __int64 *, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &v24,
             &v27);
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 32;
          goto LABEL_142;
        }
        goto LABEL_144;
      }
      if ( (unsigned int)_o__wcsnicmp(v24, L"UvhdRoamingPolicy", v27) )
        continue;
    }
    break;
  }
  v8 = 0;
  v9 = 0;
  for ( i = 0; ; i = 2 )
  {
    while ( 1 )
    {
LABEL_35:
      if ( v4 == 1 )
        goto LABEL_144;
      LODWORD(cbInit) = 0;
      v4 = -2147023728;
      while ( !(*(unsigned int (__fastcall **)(void *))(*(_QWORD *)ppvObject + 200LL))(ppvObject) )
      {
        v11 = (*(__int64 (__fastcall **)(void *, unsigned __int64 *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &cbInit);
        v4 = v11;
        if ( v11 < 0 )
          break;
        if ( v11 == 1 )
          goto LABEL_35;
        if ( (_DWORD)cbInit == 1 )
          goto LABEL_52;
      }
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_144;
        }
        v6 = 33;
LABEL_142:
        v14 = (unsigned int)v4;
        goto LABEL_143;
      }
      if ( v4 == 1 )
        goto LABEL_144;
LABEL_52:
      v26 = 0;
      LODWORD(cbInit) = 0;
      v4 = (*(__int64 (__fastcall **)(void *, __int64 *, unsigned int *))(*(_QWORD *)ppvObject + 112LL))(
             ppvObject,
             &v24,
             &v27);
      if ( v4 < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 34;
          goto LABEL_142;
        }
        goto LABEL_144;
      }
      if ( !(unsigned int)_o__wcsnicmp(v24, L"RoamingMode", v27) )
      {
        v14 = 0;
        LODWORD(v29) = 0;
        while ( 1 )
        {
          do
          {
            if ( (_DWORD)v14 == 1 )
              goto LABEL_63;
            v15 = (*(__int64 (__fastcall **)(void *, IStream **))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v29);
            v14 = (unsigned int)v15;
            v4 = v15;
            if ( v15 < 0 )
              goto LABEL_106;
          }
          while ( v15 == 1 );
          if ( (_DWORD)v29 == 3 )
            break;
          v12 = (unsigned int)((_DWORD)v29 - 4);
          if ( (_DWORD)v29 == 4 )
            break;
          if ( (_DWORD)v29 == 15 )
          {
            v4 = 1;
            goto LABEL_64;
          }
        }
        v14 = (*(unsigned int (__fastcall **)(void *, __int64 *, unsigned __int64 *, _QWORD))(*(_QWORD *)ppvObject
                                                                                            + 128LL))(
                ppvObject,
                &v26,
                &cbInit,
                (unsigned int)v15);
LABEL_63:
        v4 = v14;
        if ( (int)v14 >= 0 )
        {
LABEL_64:
          *((_DWORD *)this + 7) = _o__wtol(v26, v12, v13, v14);
          continue;
        }
LABEL_106:
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_144;
        }
        v6 = 35;
LABEL_143:
        WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_e8dd23dccea833ec9363436debfb788c_Traceguids, v14);
        goto LABEL_144;
      }
      if ( (unsigned int)_o__wcsnicmp(v24, L"Include", v27) )
        break;
      i = 1;
    }
    if ( (unsigned int)_o__wcsnicmp(v24, L"Exclude", v27) )
      break;
  }
  if ( !(unsigned int)_o__wcsnicmp(v24, L"File", v27) )
  {
    v14 = 0;
    LODWORD(v29) = 0;
    while ( (_DWORD)v14 != 1 )
    {
      v16 = (*(__int64 (__fastcall **)(void *, IStream **))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v29);
      v14 = (unsigned int)v16;
      v4 = v16;
      if ( v16 < 0 )
        goto LABEL_110;
      if ( v16 != 1 )
      {
        if ( (_DWORD)v29 == 3 || (_DWORD)v29 == 4 )
        {
          v14 = (*(unsigned int (__fastcall **)(void *, __int64 *, unsigned __int64 *, _QWORD))(*(_QWORD *)ppvObject
                                                                                              + 128LL))(
                  ppvObject,
                  &v26,
                  &cbInit,
                  (unsigned int)v16);
          break;
        }
        if ( (_DWORD)v29 == 15 )
          goto LABEL_80;
      }
    }
    v4 = v14;
    if ( (int)v14 >= 0 )
    {
LABEL_80:
      v4 = RdVhd::Uvhd::CRemappedPath::CreateInstance(v26, 1, &v25, v14);
      if ( v4 >= 0 )
        goto LABEL_97;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v6 = 37;
        goto LABEL_142;
      }
      goto LABEL_144;
    }
LABEL_110:
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 36;
      goto LABEL_143;
    }
    goto LABEL_144;
  }
  if ( (unsigned int)_o__wcsnicmp(v24, L"Folder", v27) )
  {
    v4 = -798752755;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 40;
      goto LABEL_142;
    }
    goto LABEL_144;
  }
  v14 = 0;
  LODWORD(v29) = 0;
  while ( (_DWORD)v14 != 1 )
  {
    v17 = (*(__int64 (__fastcall **)(void *, IStream **))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v29);
    v14 = (unsigned int)v17;
    v4 = v17;
    if ( v17 < 0 )
      goto LABEL_122;
    if ( v17 != 1 )
    {
      if ( (_DWORD)v29 == 3 || (_DWORD)v29 == 4 )
      {
        v14 = (*(unsigned int (__fastcall **)(void *, __int64 *, unsigned __int64 *, _QWORD))(*(_QWORD *)ppvObject
                                                                                            + 128LL))(
                ppvObject,
                &v26,
                &cbInit,
                (unsigned int)v17);
        break;
      }
      if ( (_DWORD)v29 == 15 )
        goto LABEL_96;
    }
  }
  v4 = v14;
  if ( (int)v14 < 0 )
  {
LABEL_122:
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_144;
    }
    v6 = 38;
    goto LABEL_143;
  }
LABEL_96:
  v4 = RdVhd::Uvhd::CRemappedPath::CreateInstance(v26, 2, &v25, v14);
  if ( v4 >= 0 )
  {
LABEL_97:
    if ( i == 1 )
    {
      if ( v8 )
      {
        v18 = v25;
        *((_QWORD *)v8 + 6) = v25;
        v8 = v18;
      }
      else
      {
        v8 = v25;
        *((_QWORD *)this + 4) = v25;
      }
    }
    else
    {
      if ( i != 2 )
      {
        v4 = -798687219;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v6 = 41;
          goto LABEL_142;
        }
        goto LABEL_144;
      }
      if ( v9 )
      {
        v19 = v25;
        *((_QWORD *)v9 + 6) = v25;
        v9 = v19;
      }
      else
      {
        v9 = v25;
        *((_QWORD *)this + 5) = v25;
      }
    }
    v25 = 0;
    goto LABEL_35;
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v6 = 39;
    goto LABEL_142;
  }
LABEL_144:
  v20 = 0;
  if ( v4 < 0 )
    v20 = v4;
  ATL::CComPtrBase<IXmlReader>::Release(&ppvObject);
  if ( v25 )
    RdVhd::Uvhd::CRemappedPath::`scalar deleting destructor'(v25, v21);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&ppvObject);
  return v20;
}

```

## disassembly

```asm
0x18004befc  mov     [rsp-38h+arg_0], rbx
0x18004bf01  push    rbp
0x18004bf02  push    rsi
0x18004bf03  push    rdi
0x18004bf04  push    r12
0x18004bf06  push    r13
0x18004bf08  push    r14
0x18004bf0a  push    r15
0x18004bf0c  mov     rbp, rsp
0x18004bf0f  sub     rsp, 40h
0x18004bf13  xor     r12d, r12d
0x18004bf16  mov     rsi, rdx
0x18004bf19  mov     [rbp+var_18], r12
0x18004bf1d  mov     r13, rcx
0x18004bf20  mov     [rbp+arg_8], r12d
0x18004bf24  mov     [rbp+var_10], r12
0x18004bf28  mov     [rbp+ppvObject], r12
0x18004bf2c  test    rdx, rdx
0x18004bf2f  jnz     short loc_18004BF77
0x18004bf31  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bf38  lea     rax, WPP_GLOBAL_Control
0x18004bf3f  cmp     rcx, rax
0x18004bf42  jz      short loc_18004BF6D
0x18004bf44  lea     edi, [rdx+4]
0x18004bf47  test    [rcx+1Ch], dil
0x18004bf4b  jz      short loc_18004BF6D
0x18004bf4d  cmp     byte ptr [rcx+19h], 2
0x18004bf51  jb      short loc_18004BF6D
0x18004bf53  mov     rcx, [rcx+10h]
0x18004bf57  lea     edx, [rsi+1Bh]
0x18004bf5a  lea     r9, aSzroamingpolic; "szRoamingPolicyXml"
0x18004bf61  lea     r8, WPP_e8dd23dccea833ec9363436debfb788c_Traceguids
0x18004bf68  call    WPP_SF_S
0x18004bf6d  mov     ebx, 80070057h
0x18004bf72  jmp     loc_18004C6C9
0x18004bf77  xor     r8d, r8d; pMalloc
0x18004bf7a  lea     rdx, [rbp+ppvObject]; ppvObject
0x18004bf7e  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18004bf85  call    cs:__imp_CreateXmlReader
0x18004bf8b  mov     ebx, eax
0x18004bf8d  mov     edi, 4
0x18004bf92  test    eax, eax
0x18004bf94  js      loc_18004C689
0x18004bf9a  mov     rcx, [rbp+ppvObject]
0x18004bf9e  xor     r8d, r8d
0x18004bfa1  mov     edx, edi
0x18004bfa3  mov     rax, [rcx]
0x18004bfa6  mov     rax, [rax+28h]
0x18004bfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfaf  mov     ebx, eax
0x18004bfb1  test    eax, eax
0x18004bfb3  js      loc_18004C689
0x18004bfb9  mov     rcx, [rbp+ppvObject]
0x18004bfbd  lea     r14d, [rdi-3]
0x18004bfc1  mov     r8d, r14d
0x18004bfc4  mov     edx, r14d
0x18004bfc7  mov     rax, [rcx]
0x18004bfca  mov     rax, [rax+28h]
0x18004bfce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bfd3  mov     ebx, eax
0x18004bfd5  test    eax, eax
0x18004bfd7  jns     short loc_18004C00C
0x18004bfd9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004bfe0  lea     rax, WPP_GLOBAL_Control
0x18004bfe7  cmp     rcx, rax
0x18004bfea  jz      loc_18004C6C9
0x18004bff0  test    [rcx+1Ch], dil
0x18004bff4  jz      loc_18004C6C9
0x18004bffa  cmp     byte ptr [rcx+19h], 2
0x18004bffe  jb      loc_18004C6C9
0x18004c004  lea     edx, [rdi+19h]
0x18004c007  jmp     loc_18004C6B6
0x18004c00c  lea     r8, [rbp+cbInit]; unsigned __int64 *
0x18004c010  mov     [rbp+arg_18], r12
0x18004c014  mov     edx, 0FFFFFFFEh; unsigned __int64
0x18004c019  mov     [rbp+cbInit], r12
0x18004c01d  mov     rcx, rsi; unsigned __int16 *
0x18004c020  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004c025  mov     ebx, eax
0x18004c027  test    eax, eax
0x18004c029  js      short loc_18004C05C
0x18004c02b  mov     edx, dword ptr [rbp+cbInit]; cbInit
0x18004c02e  mov     rcx, rsi; pInit
0x18004c031  call    cs:__imp_SHCreateMemStream
0x18004c037  mov     [rbp+arg_18], rax
0x18004c03b  mov     rdx, rax
0x18004c03e  test    rax, rax
0x18004c041  jnz     short loc_18004C04A
0x18004c043  mov     ebx, 80004005h
0x18004c048  jmp     short loc_18004C05C
0x18004c04a  mov     rcx, [rbp+ppvObject]
0x18004c04e  mov     rax, [rcx]
0x18004c051  mov     rax, [rax+18h]
0x18004c055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c05a  mov     ebx, eax
0x18004c05c  lea     rcx, [rbp+arg_18]
0x18004c060  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004c065  test    ebx, ebx
0x18004c067  jns     short loc_18004C09E
0x18004c069  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c070  lea     rax, WPP_GLOBAL_Control
0x18004c077  cmp     rcx, rax
0x18004c07a  jz      loc_18004C6C9
0x18004c080  test    [rcx+1Ch], dil
0x18004c084  jz      loc_18004C6C9
0x18004c08a  cmp     byte ptr [rcx+19h], 2
0x18004c08e  jb      loc_18004C6C9
0x18004c094  mov     edx, 1Eh
0x18004c099  jmp     loc_18004C6B6
0x18004c09e  cmp     ebx, r14d
0x18004c0a1  jz      loc_18004C136
0x18004c0a7  mov     dword ptr [rbp+cbInit], r12d
0x18004c0ab  mov     ebx, 80070490h
0x18004c0b0  mov     rcx, [rbp+ppvObject]
0x18004c0b4  mov     rax, [rcx]
0x18004c0b7  mov     rax, [rax+0C8h]
0x18004c0be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0c3  test    eax, eax
0x18004c0c5  jnz     short loc_18004C0EE
0x18004c0c7  mov     rcx, [rbp+ppvObject]
0x18004c0cb  lea     rdx, [rbp+cbInit]
0x18004c0cf  mov     rax, [rcx]
0x18004c0d2  mov     rax, [rax+30h]
0x18004c0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c0db  mov     ebx, eax
0x18004c0dd  test    eax, eax
0x18004c0df  js      short loc_18004C0EE
0x18004c0e1  cmp     eax, r14d
0x18004c0e4  jz      short loc_18004C09E
0x18004c0e6  cmp     dword ptr [rbp+cbInit], r14d
0x18004c0ea  jnz     short loc_18004C0B0
0x18004c0ec  jmp     short loc_18004C0FB
0x18004c0ee  test    ebx, ebx
0x18004c0f0  js      loc_18004C1C8
0x18004c0f6  cmp     ebx, r14d
0x18004c0f9  jz      short loc_18004C136
0x18004c0fb  mov     rcx, [rbp+ppvObject]
0x18004c0ff  lea     r8, [rbp+arg_8]
0x18004c103  lea     rdx, [rbp+var_18]
0x18004c107  mov     rax, [rcx]
0x18004c10a  mov     rax, [rax+70h]
0x18004c10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c113  mov     ebx, eax
0x18004c115  test    eax, eax
0x18004c117  js      short loc_18004C193
0x18004c119  mov     r8d, [rbp+arg_8]
0x18004c11d  lea     rdx, aUvhdroamingpol; "UvhdRoamingPolicy"
0x18004c124  mov     rcx, [rbp+var_18]
0x18004c128  call    cs:__imp__o__wcsnicmp
0x18004c12e  test    eax, eax
0x18004c130  jnz     loc_18004C09E
0x18004c136  mov     rsi, r12
0x18004c139  mov     r14, r12
0x18004c13c  mov     r15d, r12d
0x18004c13f  cmp     ebx, 1
0x18004c142  jz      loc_18004C6C9
0x18004c148  mov     dword ptr [rbp+cbInit], r12d
0x18004c14c  mov     ebx, 80070490h
0x18004c151  mov     rcx, [rbp+ppvObject]
0x18004c155  mov     rax, [rcx]
0x18004c158  mov     rax, [rax+0C8h]
0x18004c15f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c164  test    eax, eax
0x18004c166  jnz     loc_18004C1FD
0x18004c16c  mov     rcx, [rbp+ppvObject]
0x18004c170  lea     rdx, [rbp+cbInit]
0x18004c174  mov     rax, [rcx]
0x18004c177  mov     rax, [rax+30h]
0x18004c17b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c180  mov     ebx, eax
0x18004c182  test    eax, eax
0x18004c184  js      short loc_18004C1FD
0x18004c186  cmp     eax, 1
0x18004c189  jz      short loc_18004C13F
0x18004c18b  cmp     dword ptr [rbp+cbInit], 1
0x18004c18f  jnz     short loc_18004C151
0x18004c191  jmp     short loc_18004C20E
0x18004c193  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c19a  lea     rax, WPP_GLOBAL_Control
0x18004c1a1  cmp     rcx, rax
0x18004c1a4  jz      loc_18004C6C9
0x18004c1aa  test    [rcx+1Ch], dil
0x18004c1ae  jz      loc_18004C6C9
0x18004c1b4  cmp     byte ptr [rcx+19h], 2
0x18004c1b8  jb      loc_18004C6C9
0x18004c1be  mov     edx, 20h ; ' '
0x18004c1c3  jmp     loc_18004C6B6
0x18004c1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c1cf  lea     rax, WPP_GLOBAL_Control
0x18004c1d6  cmp     rcx, rax
0x18004c1d9  jz      loc_18004C6C9
0x18004c1df  test    [rcx+1Ch], dil
0x18004c1e3  jz      loc_18004C6C9
0x18004c1e9  cmp     byte ptr [rcx+19h], 2
0x18004c1ed  jb      loc_18004C6C9
0x18004c1f3  mov     edx, 1Fh
0x18004c1f8  jmp     loc_18004C6B6
0x18004c1fd  test    ebx, ebx
0x18004c1ff  js      loc_18004C663
0x18004c205  cmp     ebx, 1
0x18004c208  jz      loc_18004C6C9
0x18004c20e  mov     rcx, [rbp+ppvObject]
0x18004c212  lea     r8, [rbp+arg_8]
0x18004c216  mov     [rbp+var_8], r12
0x18004c21a  lea     rdx, [rbp+var_18]
0x18004c21e  mov     dword ptr [rbp+cbInit], r12d
0x18004c222  mov     rax, [rcx]
0x18004c225  mov     rax, [rax+70h]
0x18004c229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c22e  mov     ebx, eax
0x18004c230  test    eax, eax
0x18004c232  js      loc_18004C63D
0x18004c238  mov     r8d, [rbp+arg_8]
0x18004c23c  lea     rdx, aRoamingmode; "RoamingMode"
0x18004c243  mov     rcx, [rbp+var_18]
0x18004c247  call    cs:__imp__o__wcsnicmp
0x18004c24d  test    eax, eax
0x18004c24f  jnz     loc_18004C2DC
0x18004c255  mov     r9d, r12d
0x18004c258  mov     dword ptr [rbp+arg_18], r12d
0x18004c25c  cmp     r9d, 1
0x18004c260  jz      short loc_18004C2BD
0x18004c262  mov     rcx, [rbp+ppvObject]
0x18004c266  lea     rdx, [rbp+arg_18]
0x18004c26a  mov     rax, [rcx]
0x18004c26d  mov     rax, [rax+30h]
0x18004c271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c276  mov     r9d, eax
0x18004c279  mov     ebx, eax
0x18004c27b  test    eax, eax
0x18004c27d  js      loc_18004C4F8
0x18004c283  cmp     eax, 1
0x18004c286  jz      short loc_18004C25C
0x18004c288  mov     edx, dword ptr [rbp+arg_18]
0x18004c28b  sub     edx, 3
0x18004c28e  jz      short loc_18004C29F
0x18004c290  sub     edx, 1
0x18004c293  jz      short loc_18004C29F
0x18004c295  cmp     edx, 0Bh
0x18004c298  jnz     short loc_18004C25C
0x18004c29a  lea     ebx, [rdx-0Ah]
0x18004c29d  jmp     short loc_18004C2C9
0x18004c29f  mov     rcx, [rbp+ppvObject]
0x18004c2a3  lea     r8, [rbp+cbInit]
0x18004c2a7  lea     rdx, [rbp+var_8]
0x18004c2ab  mov     rax, [rcx]
0x18004c2ae  mov     rax, [rax+80h]
0x18004c2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c2ba  mov     r9d, eax
0x18004c2bd  mov     ebx, r9d
0x18004c2c0  test    r9d, r9d
0x18004c2c3  js      loc_18004C4F8
0x18004c2c9  mov     rcx, [rbp+var_8]
0x18004c2cd  call    cs:__imp__o__wtol
0x18004c2d3  mov     [r13+1Ch], eax
0x18004c2d7  jmp     loc_18004C13F
0x18004c2dc  mov     r8d, [rbp+arg_8]
0x18004c2e0  lea     rdx, aInclude; "Include"
0x18004c2e7  mov     rcx, [rbp+var_18]
0x18004c2eb  call    cs:__imp__o__wcsnicmp
0x18004c2f1  test    eax, eax
0x18004c2f3  jnz     short loc_18004C2FE
0x18004c2f5  lea     r15d, [rax+1]
0x18004c2f9  jmp     loc_18004C13F
0x18004c2fe  mov     r8d, [rbp+arg_8]
0x18004c302  lea     rdx, aExclude; "Exclude"
0x18004c309  mov     rcx, [rbp+var_18]
0x18004c30d  call    cs:__imp__o__wcsnicmp
0x18004c313  test    eax, eax
0x18004c315  jnz     short loc_18004C320
0x18004c317  lea     r15d, [rax+2]
0x18004c31b  jmp     loc_18004C13F
0x18004c320  mov     r8d, [rbp+arg_8]
0x18004c324  lea     rdx, aFile; "File"
0x18004c32b  mov     rcx, [rbp+var_18]
0x18004c32f  call    cs:__imp__o__wcsnicmp
0x18004c335  test    eax, eax
0x18004c337  jnz     loc_18004C3FF
0x18004c33d  mov     r9d, r12d
0x18004c340  mov     dword ptr [rbp+arg_18], r12d
0x18004c344  cmp     r9d, 1
0x18004c348  jz      short loc_18004C3A2
0x18004c34a  mov     rcx, [rbp+ppvObject]
0x18004c34e  lea     rdx, [rbp+arg_18]
0x18004c352  mov     rax, [rcx]
0x18004c355  mov     rax, [rax+30h]
0x18004c359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c35e  mov     r9d, eax
0x18004c361  mov     ebx, eax
0x18004c363  test    eax, eax
0x18004c365  js      loc_18004C52D
0x18004c36b  cmp     eax, 1
0x18004c36e  jz      short loc_18004C344
0x18004c370  mov     edx, dword ptr [rbp+arg_18]
0x18004c373  sub     edx, 3
0x18004c376  jz      short loc_18004C384
0x18004c378  sub     edx, 1
0x18004c37b  jz      short loc_18004C384
0x18004c37d  cmp     edx, 0Bh
0x18004c380  jnz     short loc_18004C344
  ... truncated ...
```
