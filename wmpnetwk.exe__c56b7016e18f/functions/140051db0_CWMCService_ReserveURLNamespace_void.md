# CWMCService::ReserveURLNamespace(void)

- ea: `0x140051db0`
- end: `0x140052246`
- name: `?ReserveURLNamespace@CWMCService@@AEAAKXZ`
- size: `1174`
- prototype: `__int64 __fastcall(const unsigned __int16 **this)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x14004e7c0`

## callees

- `0x14000b3b0`
- `0x14000c920`
- `0x1400151f0`
- `0x140018df0`
- `0x140038f58`
- `0x14003f17c`
- `0x1400447f0`
- `0x140044834`
- `0x140045f20`
- `0x140047798`
- `0x1400488f4`
- `0x14004a79c`
- `0x14004a834`
- `0x14004b074`
- `0x14004b650`
- `0x14004bf30`
- `0x140051bc0`
- `0x140051db0`
- `0x1400538b0`
- `0x140053c70`

## import_xrefs

- `ADVAPI32!ConvertStringSidToSidW` at `0x140051e95`
- `ADVAPI32!ConvertStringSidToSidW` at `0x140051e95`
- `KERNEL32!LocalFree` at `0x140051fc8`
- `KERNEL32!LocalFree` at `0x140051fc8`
- `HTTPAPI!HttpInitialize` at `0x14005206c`
- `HTTPAPI!HttpInitialize` at `0x14005206c`
- `HTTPAPI!HttpTerminate` at `0x1400520e1`
- `HTTPAPI!HttpTerminate` at `0x1400520e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CWMCService::ReserveURLNamespace(const unsigned __int16 **this)
{
  BOOL v2; // eax
  bool v3; // r8
  BOOL v4; // edi
  ULONG v5; // ebx
  const struct _SID *v6; // rbx
  const unsigned __int16 *v7; // r8
  BOOL v8; // edi
  unsigned int v9; // eax
  ULONG v10; // eax
  unsigned int v11; // edx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rcx
  PVOID *v14; // r10
  unsigned int v15; // eax
  HTTPAPI_VERSION Version[2]; // [rsp+30h] [rbp-D0h] BYREF
  PSID Sid; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v19[8]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v22; // [rsp+68h] [rbp-98h]
  int v23; // [rsp+6Ch] [rbp-94h]
  __int128 v24; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  struct _EVENT_DESCRIPTOR v27; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v28[9]; // [rsp+A0h] [rbp-60h] BYREF
  char v29; // [rsp+ECh] [rbp-14h]
  int v30; // [rsp+F0h] [rbp-10h]
  _BYTE v31[8]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v32[8]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v33[8]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v34[16]; // [rsp+110h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 150, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids);
  v20[0] = &ATL::CSecurityDesc::`vftable';
  v20[1] = 0;
  v21[1] = 0;
  v22 = 0;
  v23 = 2;
  v21[0] = &ATL::CDacl::`vftable';
  v24 = 0;
  v25 = 0;
  v26 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v19);
  Version[0] = (HTTPAPI_VERSION)1;
  Sid = 0;
  v27 = 0;
  v2 = ConvertStringSidToSidW(L"S-1-5-80-2375682873-768044350-3534595160-1005545032-2873800392", &Sid);
  v4 = v2;
  v5 = !v2 ? 0x538 : 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)(v2 ? 5 : 2) )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      151,
      &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
      !v2 ? 0x538 : 0);
  }
  v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL;
  if ( v4 )
  {
    v6 = (const struct _SID *)Sid;
    v28[0] = &ATL::CSid::`vftable';
    v29 = 0;
    v30 = 7;
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v31);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v32);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v33);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(v34);
    if ( !ATL::CSid::LoadAccount((ATL::CSid *)v28, v6, v7) )
      ATL::AtlThrowLastWin32();
    v8 = ATL::CDacl::AddAllowedAce((ATL::CDacl *)v21, (const struct ATL::CSid *)v28, 0xF003Fu, 3u);
    ATL::CSid::~CSid((ATL::CSid *)v28);
    v5 = !v8 ? 0x538 : 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= (unsigned int)(v8 ? 5 : 2) )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        152,
        &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        !v8 ? 0x538 : 0);
    }
    LocalFree(Sid);
    Sid = 0;
    v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL;
  }
  if ( v5 )
    goto LABEL_40;
  ATL::CSecurityDesc::SetDacl((ATL::CSecurityDesc *)v20, (const struct ATL::CDacl *)v21, v3);
  if ( !(unsigned __int8)ATL::CSecurityDesc::ToString(v20, v19) )
    v5 = 1336;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v9 = 5;
    if ( v5 )
      v9 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v9 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v5);
  }
  v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL;
  if ( v5 )
    goto LABEL_40;
  v10 = HttpInitialize(Version[0], 2u, 0);
  v5 = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v11 = 5;
    if ( v10 )
      v11 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v11 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v10);
  }
  v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_HTTPINITIALIZE;
  if ( v5 )
    goto LABEL_40;
  v12 = (unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(v19, 0);
  ReserveHTTPPrefix(v13, v12);
  v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_RESERVEHTTP;
  v5 = HttpTerminate(2u, 0);
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v15 = 5;
    if ( v5 )
      v15 = 2;
    if ( *((unsigned __int8 *)WPP_GLOBAL_Control + 25) >= v15 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v5);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v27 = (struct _EVENT_DESCRIPTOR)WMC_E_SERVICE_INSTALL_FAILED_HTTPTERMINATE;
  if ( v5 )
  {
LABEL_40:
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(Version);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::Format(
      Version,
      L"%lu",
      v5);
    CNTService::LogEvent(
      (CNTService *)this,
      &v27,
      this[5],
      *(const unsigned __int16 **)&Version[0].HttpApiMajorVersion,
      0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        156,
        (unsigned int)&WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids,
        (unsigned int)this[5],
        v5);
    }
    ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(Version);
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v14 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v14 + 28) & 1) != 0
    && *((unsigned __int8 *)v14 + 25) >= (unsigned int)(v5 != 0 ? 2 : 5) )
  {
    WPP_SF_d(v14[2], 157, &WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids, v5);
  }
  ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(v19);
  ATL::CDacl::~CDacl((ATL::CDacl *)v21);
  v20[0] = &ATL::CSecurityDesc::`vftable';
  ATL::CSecurityDesc::Clear((ATL::CSecurityDesc *)v20);
  return v5;
}

```

## disassembly

```asm
0x140051db0  mov     [rsp-8+arg_8], rbx
0x140051db5  mov     [rsp-8+arg_10], rsi
0x140051dba  push    rbp
0x140051dbb  push    rdi
0x140051dbc  push    r12
0x140051dbe  push    r13
0x140051dc0  push    r14
0x140051dc2  lea     rbp, [rsp-30h]
0x140051dc7  sub     rsp, 130h
0x140051dce  mov     rax, cs:__security_cookie
0x140051dd5  xor     rax, rsp
0x140051dd8  mov     [rbp+50h+var_30], rax
0x140051ddc  mov     rsi, rcx
0x140051ddf  lea     r13, WPP_GLOBAL_Control
0x140051de6  mov     ebx, 1
0x140051deb  lea     r12, WPP_2bf5d2a285bb3b5db5446f7e5dd5f28b_Traceguids
0x140051df2  mov     rcx, cs:WPP_GLOBAL_Control
0x140051df9  cmp     rcx, r13
0x140051dfc  jz      short loc_140051E14
0x140051dfe  test    [rcx+1Ch], bl
0x140051e01  jz      short loc_140051E14
0x140051e03  mov     edx, 96h
0x140051e08  mov     r8, r12
0x140051e0b  mov     rcx, [rcx+10h]
0x140051e0f  call    WPP_SF_
0x140051e14  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x140051e1b  mov     [rsp+150h+var_108], rax
0x140051e20  mov     [rsp+150h+var_100], 0
0x140051e29  mov     [rsp+150h+var_F0], 0
0x140051e32  mov     [rsp+150h+var_E8], 0
0x140051e37  mov     r14d, 2
0x140051e3d  mov     [rsp+150h+var_E4], r14d
0x140051e42  lea     rax, ??_7CDacl@ATL@@6B@; const ATL::CDacl::`vftable'
0x140051e49  mov     [rsp+150h+var_F8], rax
0x140051e4e  xorps   xmm0, xmm0
0x140051e51  movdqu  [rsp+150h+var_E0], xmm0
0x140051e57  mov     [rbp+50h+var_D0], 0
0x140051e5f  mov     [rbp+50h+var_C8], 0
0x140051e66  lea     rcx, [rsp+150h+var_110]
0x140051e6b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140051e70  nop
0x140051e71  mov     dword ptr [rsp+150h+Version.HttpApiMajorVersion], 1
0x140051e79  mov     [rsp+150h+Sid], 0
0x140051e82  xorps   xmm0, xmm0
0x140051e85  movups  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x140051e89  lea     rdx, [rsp+150h+Sid]; Sid
0x140051e8e  lea     rcx, StringSid; "S-1-5-80-2375682873-768044350-353459516"...
0x140051e95  call    cs:__imp_ConvertStringSidToSidW
0x140051e9b  mov     edi, eax
0x140051e9d  mov     ecx, eax
0x140051e9f  neg     ecx
0x140051ea1  sbb     ebx, ebx
0x140051ea3  not     ebx
0x140051ea5  and     ebx, 538h
0x140051eab  mov     rcx, cs:WPP_GLOBAL_Control
0x140051eb2  cmp     rcx, r13
0x140051eb5  jz      short loc_140051EE7
0x140051eb7  test    [rcx+1Ch], r14b
0x140051ebb  jz      short loc_140051EE7
0x140051ebd  neg     eax
0x140051ebf  sbb     edx, edx
0x140051ec1  and     edx, 3
0x140051ec4  add     edx, r14d
0x140051ec7  movzx   eax, byte ptr [rcx+19h]
0x140051ecb  cmp     eax, edx
0x140051ecd  jb      short loc_140051EE7
0x140051ecf  mov     edx, 97h
0x140051ed4  mov     dword ptr [rsp+150h+var_130], edi
0x140051ed8  mov     r9d, ebx
0x140051edb  mov     r8, r12
0x140051ede  mov     rcx, [rcx+10h]
0x140051ee2  call    WPP_SF_Dd
0x140051ee7  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL
0x140051eee  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x140051ef3  test    edi, edi
0x140051ef5  jz      loc_140051FE3
0x140051efb  mov     rbx, [rsp+150h+Sid]
0x140051f00  lea     rax, ??_7CSid@ATL@@6B@; const ATL::CSid::`vftable'
0x140051f07  mov     [rbp+50h+var_B0], rax
0x140051f0b  mov     [rbp+50h+var_64], 0
0x140051f0f  mov     [rbp+50h+var_60], 7
0x140051f16  lea     rcx, [rbp+50h+var_58]
0x140051f1a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140051f1f  nop
0x140051f20  lea     rcx, [rbp+50h+var_50]
0x140051f24  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140051f29  nop
0x140051f2a  lea     rcx, [rbp+50h+var_48]
0x140051f2e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140051f33  nop
0x140051f34  lea     rcx, [rbp+50h+var_40]
0x140051f38  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140051f3d  nop
0x140051f3e  mov     rdx, rbx; struct _SID *
0x140051f41  lea     rcx, [rbp+50h+var_B0]; this
0x140051f45  call    ?LoadAccount@CSid@ATL@@QEAA_NPEBU_SID@@PEBG@Z; ATL::CSid::LoadAccount(_SID const *,ushort const *)
0x140051f4a  test    al, al
0x140051f4c  jnz     short loc_140051F54
0x140051f4e  call    ?AtlThrowLastWin32@ATL@@YAXXZ; ATL::AtlThrowLastWin32(void)
0x140051f54  mov     r9b, 3; unsigned __int8
0x140051f57  mov     r8d, 0F003Fh; unsigned int
0x140051f5d  lea     rdx, [rbp+50h+var_B0]; struct ATL::CSid *
0x140051f61  lea     rcx, [rsp+150h+var_F8]; this
0x140051f66  call    ?AddAllowedAce@CDacl@ATL@@QEAA_NAEBVCSid@2@KE@Z; ATL::CDacl::AddAllowedAce(ATL::CSid const &,ulong,uchar)
0x140051f6b  movzx   edi, al
0x140051f6e  lea     rcx, [rbp+50h+var_B0]; this
0x140051f72  call    ??1CSid@ATL@@UEAA@XZ; ATL::CSid::~CSid(void)
0x140051f77  mov     eax, edi
0x140051f79  neg     eax
0x140051f7b  sbb     ebx, ebx
0x140051f7d  not     ebx
0x140051f7f  and     ebx, 538h
0x140051f85  mov     rcx, cs:WPP_GLOBAL_Control
0x140051f8c  cmp     rcx, r13
0x140051f8f  jz      short loc_140051FC3
0x140051f91  test    [rcx+1Ch], r14b
0x140051f95  jz      short loc_140051FC3
0x140051f97  mov     eax, edi
0x140051f99  neg     eax
0x140051f9b  sbb     edx, edx
0x140051f9d  and     edx, 3
0x140051fa0  add     edx, r14d
0x140051fa3  movzx   eax, byte ptr [rcx+19h]
0x140051fa7  cmp     eax, edx
0x140051fa9  jb      short loc_140051FC3
0x140051fab  mov     edx, 98h
0x140051fb0  mov     dword ptr [rsp+150h+var_130], edi
0x140051fb4  mov     r9d, ebx
0x140051fb7  mov     r8, r12
0x140051fba  mov     rcx, [rcx+10h]
0x140051fbe  call    WPP_SF_Dd
0x140051fc3  mov     rcx, [rsp+150h+Sid]; hMem
0x140051fc8  call    cs:__imp_LocalFree
0x140051fce  mov     [rsp+150h+Sid], 0
0x140051fd7  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL
0x140051fde  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x140051fe3  mov     edi, 5
0x140051fe8  test    ebx, ebx
0x140051fea  jnz     loc_14005213B
0x140051ff0  lea     rdx, [rsp+150h+var_F8]; struct ATL::CDacl *
0x140051ff5  lea     rcx, [rsp+150h+var_108]; this
0x140051ffa  call    ?SetDacl@CSecurityDesc@ATL@@QEAAXAEBVCDacl@2@_N@Z; ATL::CSecurityDesc::SetDacl(ATL::CDacl const &,bool)
0x140051fff  lea     rdx, [rsp+150h+var_110]
0x140052004  lea     rcx, [rsp+150h+var_108]
0x140052009  call    ?ToString@CSecurityDesc@ATL@@QEBA_NPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@2@K@Z; ATL::CSecurityDesc::ToString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> *,ulong)
0x14005200e  test    al, al
0x140052010  mov     eax, 538h
0x140052015  cmovz   ebx, eax
0x140052018  mov     rcx, cs:WPP_GLOBAL_Control
0x14005201f  cmp     rcx, r13
0x140052022  jz      short loc_14005204E
0x140052024  test    [rcx+1Ch], r14b
0x140052028  jz      short loc_14005204E
0x14005202a  movzx   edx, byte ptr [rcx+19h]
0x14005202e  mov     eax, edi
0x140052030  test    ebx, ebx
0x140052032  cmovnz  eax, r14d
0x140052036  cmp     edx, eax
0x140052038  jb      short loc_14005204E
0x14005203a  mov     edx, 99h
0x14005203f  mov     r9d, ebx
0x140052042  mov     r8, r12
0x140052045  mov     rcx, [rcx+10h]
0x140052049  call    WPP_SF_d
0x14005204e  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_CREATEHTTPACL
0x140052055  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x14005205a  test    ebx, ebx
0x14005205c  jnz     loc_14005213B
0x140052062  xor     r8d, r8d; pReserved
0x140052065  mov     edx, r14d; Flags
0x140052068  mov     ecx, dword ptr [rsp+150h+Version.HttpApiMajorVersion]; Version
0x14005206c  call    cs:__imp_HttpInitialize
0x140052072  mov     ebx, eax
0x140052074  mov     rcx, cs:WPP_GLOBAL_Control
0x14005207b  cmp     rcx, r13
0x14005207e  jz      short loc_1400520AC
0x140052080  test    [rcx+1Ch], r14b
0x140052084  jz      short loc_1400520AC
0x140052086  movzx   r8d, byte ptr [rcx+19h]
0x14005208b  mov     edx, edi
0x14005208d  test    eax, eax
0x14005208f  cmovnz  edx, r14d
0x140052093  cmp     r8d, edx
0x140052096  jb      short loc_1400520AC
0x140052098  mov     edx, 9Ah
0x14005209d  mov     r9d, eax
0x1400520a0  mov     r8, r12
0x1400520a3  mov     rcx, [rcx+10h]
0x1400520a7  call    WPP_SF_d
0x1400520ac  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_HTTPINITIALIZE
0x1400520b3  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x1400520b8  test    ebx, ebx
0x1400520ba  jnz     short loc_14005213B
0x1400520bc  xor     edx, edx
0x1400520be  lea     rcx, [rsp+150h+var_110]
0x1400520c3  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x1400520c8  mov     rdx, rax; unsigned __int16 *
0x1400520cb  call    ?ReserveHTTPPrefix@@YAKPEAG0@Z; ReserveHTTPPrefix(ushort *,ushort *)
0x1400520d0  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_RESERVEHTTP
0x1400520d7  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x1400520dc  xor     edx, edx; pReserved
0x1400520de  mov     ecx, r14d; Flags
0x1400520e1  call    cs:__imp_HttpTerminate
0x1400520e7  mov     ebx, eax
0x1400520e9  mov     r10, cs:WPP_GLOBAL_Control
0x1400520f0  cmp     r10, r13
0x1400520f3  jz      short loc_140052127
0x1400520f5  test    [r10+1Ch], r14b
0x1400520f9  jz      short loc_140052127
0x1400520fb  movzx   edx, byte ptr [r10+19h]
0x140052100  mov     eax, edi
0x140052102  test    ebx, ebx
0x140052104  cmovnz  eax, r14d
0x140052108  cmp     edx, eax
0x14005210a  jb      short loc_140052127
0x14005210c  mov     edx, 9Bh
0x140052111  mov     r9d, ebx
0x140052114  mov     r8, r12
0x140052117  mov     rcx, [r10+10h]
0x14005211b  call    WPP_SF_d
0x140052120  mov     r10, cs:WPP_GLOBAL_Control
0x140052127  movups  xmm0, cs:WMC_E_SERVICE_INSTALL_FAILED_HTTPTERMINATE
0x14005212e  movdqu  xmmword ptr [rbp+50h+var_C0.Id], xmm0
0x140052133  test    ebx, ebx
0x140052135  jz      loc_1400521BB
0x14005213b  lea     rcx, [rsp+150h+Version]
0x140052140  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140052145  nop
0x140052146  mov     r8d, ebx
0x140052149  lea     rdx, aLu; "%lu"
0x140052150  lea     rcx, [rsp+150h+Version]
0x140052155  call    ?Format@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::Format(ushort const *,...)
0x14005215a  mov     [rsp+150h+var_130], 0; unsigned __int16 *
0x140052163  mov     r9, qword ptr [rsp+150h+Version.HttpApiMajorVersion]; unsigned __int16 *
0x140052168  mov     r8, [rsi+28h]; unsigned __int16 *
0x14005216c  lea     rdx, [rbp+50h+var_C0]; struct _EVENT_DESCRIPTOR *
0x140052170  mov     rcx, rsi; this
0x140052173  call    ?LogEvent@CNTService@@QEAAXAEBU_EVENT_DESCRIPTOR@@PEBG11@Z; CNTService::LogEvent(_EVENT_DESCRIPTOR const &,ushort const *,ushort const *,ushort const *)
0x140052178  mov     rcx, cs:WPP_GLOBAL_Control
0x14005217f  cmp     rcx, r13
0x140052182  jz      short loc_1400521AA
0x140052184  test    [rcx+1Ch], r14b
0x140052188  jz      short loc_1400521AA
0x14005218a  cmp     [rcx+19h], r14b
0x14005218e  jb      short loc_1400521AA
0x140052190  mov     edx, 9Ch
0x140052195  mov     dword ptr [rsp+150h+var_130], ebx
0x140052199  mov     r9, [rsi+28h]
0x14005219d  mov     r8, r12
0x1400521a0  mov     rcx, [rcx+10h]
0x1400521a4  call    WPP_SF_Sd
0x1400521a9  nop
0x1400521aa  lea     rcx, [rsp+150h+Version]
0x1400521af  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400521b4  mov     r10, cs:WPP_GLOBAL_Control
0x1400521bb  cmp     r10, r13
0x1400521be  jz      short loc_1400521F0
0x1400521c0  test    byte ptr [r10+1Ch], 1
0x1400521c5  jz      short loc_1400521F0
0x1400521c7  movzx   edx, byte ptr [r10+19h]
0x1400521cc  mov     eax, ebx
0x1400521ce  neg     eax
0x1400521d0  sbb     ecx, ecx
0x1400521d2  and     ecx, 0FFFFFFFDh
0x1400521d5  add     ecx, edi
0x1400521d7  cmp     edx, ecx
0x1400521d9  jb      short loc_1400521F0
0x1400521db  mov     edx, 9Dh
0x1400521e0  mov     r9d, ebx
0x1400521e3  mov     r8, r12
0x1400521e6  mov     rcx, [r10+10h]
0x1400521ea  call    WPP_SF_d
0x1400521ef  nop
0x1400521f0  lea     rcx, [rsp+150h+var_110]
0x1400521f5  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x1400521fa  nop
0x1400521fb  lea     rcx, [rsp+150h+var_F8]; this
0x140052200  call    ??1CDacl@ATL@@UEAA@XZ; ATL::CDacl::~CDacl(void)
0x140052205  nop
0x140052206  lea     rax, ??_7CSecurityDesc@ATL@@6B@; const ATL::CSecurityDesc::`vftable'
0x14005220d  mov     [rsp+150h+var_108], rax
0x140052212  lea     rcx, [rsp+150h+var_108]; this
0x140052217  call    ?Clear@CSecurityDesc@ATL@@MEAAXXZ; ATL::CSecurityDesc::Clear(void)
0x14005221c  mov     eax, ebx
0x14005221e  mov     rcx, [rbp+50h+var_30]
0x140052222  xor     rcx, rsp; StackCookie
0x140052225  call    __security_check_cookie
0x14005222a  lea     r11, [rsp+150h+var_20]
0x140052232  mov     rbx, [r11+38h]
0x140052236  mov     rsi, [r11+40h]
0x14005223a  mov     rsp, r11
0x14005223d  pop     r14
0x14005223f  pop     r13
0x140052241  pop     r12
0x140052243  pop     rdi
0x140052244  pop     rbp
0x140052245  retn
```
