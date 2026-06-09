# CMACAddressControl::GrantAccessToMACAddress(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,sockaddr_storage const *,ushort const *,ushort const *,ulong *)

- ea: `0x140043c90`
- end: `0x1400440d9`
- name: `?GrantAccessToMACAddress@CMACAddressControl@@AEAAJPEBGAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@PEBUsockaddr_storage@@00PEAK@Z`
- size: `1097`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400686d0`
- `0x14006982c`

## callees

- `0x140009070`
- `0x14000b3b0`
- `0x14000c920`
- `0x14000e3c8`
- `0x1400106b0`
- `0x1400313b8`
- `0x140034e14`
- `0x14003510c`
- `0x1400357b4`
- `0x140036e40`
- `0x14003ca4c`
- `0x14003f17c`
- `0x140043c90`
- `0x1400440e0`
- `0x140045f20`
- `0x140047798`
- `0x14004f094`
- `0x140068808`
- `0x140069538`
- `0x140069ed0`
- `0x140099060`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140043d9f`
- `KERNEL32!EnterCriticalSection` at `0x140043d9f`
- `KERNEL32!CompareStringOrdinal` at `0x140043fdd`
- `KERNEL32!CompareStringOrdinal` at `0x140043fdd`
- `KERNEL32!GetTickCount` at `0x140043dac`
- `KERNEL32!GetTickCount` at `0x140043dac`
- `IPHLPAPI!GetBestInterfaceEx` at `0x140043e95`
- `IPHLPAPI!GetBestInterfaceEx` at `0x140043e95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMACAddressControl::GrantAccessToMACAddress(
        CMACAddressControl *a1,
        const unsigned __int16 *a2,
        __int64 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        const unsigned __int16 *lpString2,
        _DWORD *a7)
{
  CWMCService *v10; // rcx
  signed int v11; // edi
  PVOID *v12; // rax
  DWORD TickCount; // ebx
  int Device; // eax
  int v15; // eax
  unsigned int v16; // r8d
  signed int BestInterface; // eax
  bool v18; // sf
  __int64 v19; // rcx
  int DeviceAuthorization; // eax
  DWORD pdwBestIfIndex[2]; // [rsp+50h] [rbp-61h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-59h] BYREF
  _BYTE v24[8]; // [rsp+60h] [rbp-51h] BYREF
  __int64 v25; // [rsp+68h] [rbp-49h] BYREF
  int v26; // [rsp+70h] [rbp-41h] BYREF
  CMACAddressControl *v27; // [rsp+78h] [rbp-39h]
  void **v28; // [rsp+80h] [rbp-31h] BYREF
  __int64 v29; // [rsp+88h] [rbp-29h] BYREF
  _DWORD *v30; // [rsp+90h] [rbp-21h]
  struct _GUID v31; // [rsp+98h] [rbp-19h] BYREF

  v27 = a1;
  v30 = a7;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_SSqSSq(*((_QWORD *)WPP_GLOBAL_Control + 2), *a3, a4, (__int64)a5, (__int64)lpString2, (char)a7);
  }
  *a7 = 0;
  if ( (unsigned __int8)ATL::operator==(a3, L"RME_LIVE_LIBRARY_OWNER_PSEUDO_MAC_ADDR") )
  {
    v11 = 0;
LABEL_58:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_59;
  }
  if ( (unsigned int)CWMCService::IsWMPNSSContextCurrentlyEnabled(v10) )
  {
    v11 = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)v27 + 1);
    v26 = 1;
    TickCount = GetTickCount();
    *(_DWORD *)ATL::CAtlMap<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,unsigned long,CLocaleStringElementTraitsI<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>,CLocaleCharTraits<unsigned short>>,ATL::CElementTraits<unsigned long>>::operator[](
                 (char *)v27 + 344,
                 *a3) = TickCount;
    CRendererDevicesDB::CRendererDevicesDB((CRendererDevicesDB *)v24, a2);
    if ( (unsigned int)CDevicesDB::IsExistingDevice((CDevicesDB *)v24, (const unsigned __int16 *)*a3) )
    {
LABEL_43:
      if ( lpString2 && *lpString2 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(pdwBestIfIndex);
        if ( (unsigned int)CDevicesDB::GetDeviceProperty((CDevicesDB *)v24)
          || CompareStringOrdinal(*(LPCWCH *)pdwBestIfIndex, -1, lpString2, -1, 0) != 2 )
        {
          CDevicesDB::SetDeviceProperty((CDevicesDB *)v24, (const unsigned __int16 *)*a3, L"FriendlyName", lpString2);
        }
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(pdwBestIfIndex);
      }
      goto LABEL_49;
    }
    Device = CDevicesDB::CreateDevice((CDevicesDB *)v24, (const unsigned __int16 *)*a3);
    v11 = Device;
    if ( Device > 0 )
      v11 = (unsigned __int16)Device | 0x80070000;
    if ( v11 < 0 )
    {
      v23 = 0;
LABEL_52:
      CMACAddressControl::ReleaseManagerLock(v27, &v26);
      if ( v23 != 1 )
      {
        v11 = -2147024891;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids);
        }
      }
      ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(&v25);
      goto LABEL_58;
    }
    v15 = CDevicesDB::SetDeviceProperty((CDevicesDB *)v24, (const unsigned __int16 *)*a3, L"IsControlPoint", L"1");
    v11 = v15;
    if ( v15 > 0 )
      v11 = (unsigned __int16)v15 | 0x80070000;
    if ( v11 < 0 )
    {
LABEL_49:
      v23 = 0;
      if ( v11 >= 0 )
      {
        DeviceAuthorization = CDevicesDB::GetDeviceAuthorization((CDevicesDB *)v24, (const unsigned __int16 *)*a3, &v23);
        v11 = DeviceAuthorization;
        if ( DeviceAuthorization > 0 )
          v11 = (unsigned __int16)DeviceAuthorization | 0x80070000;
      }
      goto LABEL_52;
    }
    if ( !a4 )
    {
LABEL_34:
      if ( a5 && *a5 )
        CDevicesDB::SetDeviceProperty((CDevicesDB *)v24, (const unsigned __int16 *)*a3, L"IPAddress", a5);
      *v30 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids);
      }
      goto LABEL_43;
    }
    v28 = &CNetworkInterfaces::`vftable';
    v29 = 0;
    if ( (int)CNetworkInterfaces::Initialize((CNetworkInterfaces *)&v28) >= 0 )
    {
      v31 = 0;
      pdwBestIfIndex[0] = 0;
      if ( *(_WORD *)a4 == 23 && (v16 = *(_DWORD *)(a4 + 24)) != 0 )
      {
        pdwBestIfIndex[0] = *(_DWORD *)(a4 + 24);
      }
      else
      {
        BestInterface = GetBestInterfaceEx((struct sockaddr *)a4, pdwBestIfIndex);
        v18 = BestInterface < 0;
        if ( BestInterface )
        {
          if ( BestInterface > 0 )
            v18 = 1;
          if ( v18 )
            goto LABEL_33;
        }
        v16 = pdwBestIfIndex[0];
      }
      if ( CNetworkInterfaces::_FindInterfaceUsingIndex((CNetworkInterfaces *)&v28, *(_WORD *)a4, v16, &v31) >= 0 )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsOS<unsigned short>>>(pdwBestIfIndex);
        if ( (int)CMACAddressControl::GetNetworkId(v19, &v31, pdwBestIfIndex) >= 0 )
          CDevicesDB::SetDeviceProperty(
            (CDevicesDB *)v24,
            (const unsigned __int16 *)*a3,
            L"NetworkID",
            *(const unsigned __int16 **)pdwBestIfIndex);
        ATL::CSimpleStringT<unsigned short,0>::~CSimpleStringT<unsigned short,0>(pdwBestIfIndex);
      }
    }
LABEL_33:
    v11 = 0;
    v28 = &CNetworkInterfaces::`vftable';
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    goto LABEL_34;
  }
  v11 = -2147024891;
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return (unsigned int)v11;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids);
    goto LABEL_58;
  }
LABEL_59:
  if ( v12 != &WPP_GLOBAL_Control
    && (*((_BYTE *)v12 + 28) & 1) != 0
    && *((unsigned __int8 *)v12 + 25) >= ((v11 >> 31) & 0xFFFFFFFD) + 5 )
  {
    WPP_SF_d(v12[2], 58, &WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140043c90  push    rbp
0x140043c92  push    rbx
0x140043c93  push    rsi
0x140043c94  push    rdi
0x140043c95  push    r12
0x140043c97  push    r13
0x140043c99  push    r14
0x140043c9b  push    r15
0x140043c9d  lea     rbp, [rsp-7]
0x140043ca2  sub     rsp, 0B8h
0x140043ca9  mov     rax, cs:__security_cookie
0x140043cb0  xor     rax, rsp
0x140043cb3  mov     [rbp+3Fh+var_48], rax
0x140043cb7  mov     r14, r9
0x140043cba  mov     rsi, r8
0x140043cbd  mov     r15, rdx
0x140043cc0  mov     [rbp+3Fh+var_78], rcx
0x140043cc4  mov     r13, [rbp+3Fh+arg_20]
0x140043cc8  mov     r12, [rbp+3Fh+lpString2]
0x140043ccc  mov     rbx, qword ptr [rbp+3Fh+arg_30]
0x140043cd0  mov     [rbp+3Fh+var_60], rbx
0x140043cd4  lea     rax, WPP_GLOBAL_Control
0x140043cdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140043ce2  cmp     rcx, rax
0x140043ce5  jz      short loc_140043D1B
0x140043ce7  test    byte ptr [rcx+1Ch], 1
0x140043ceb  jz      short loc_140043D1B
0x140043ced  cmp     byte ptr [rcx+19h], 5
0x140043cf1  jb      short loc_140043D1B
0x140043cf3  mov     qword ptr [rsp+0F0h+var_B0], rbx; char
0x140043cf8  mov     [rsp+0F0h+var_B8], r12; __int64
0x140043cfd  mov     [rsp+0F0h+var_C0], r13; __int64
0x140043d02  mov     qword ptr [rsp+0F0h+var_C8], r9; char
0x140043d07  mov     rax, [r8]
0x140043d0a  mov     qword ptr [rsp+0F0h+bIgnoreCase], rax; __int64
0x140043d0f  mov     r9, rdx
0x140043d12  mov     rcx, [rcx+10h]; LoggerHandle
0x140043d16  call    WPP_SF_SSqSSq
0x140043d1b  mov     dword ptr [rbx], 0
0x140043d21  lea     rdx, aRmeLiveLibrary; "RME_LIVE_LIBRARY_OWNER_PSEUDO_MAC_ADDR"
0x140043d28  mov     rcx, rsi
0x140043d2b  call    ??8ATL@@YA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@0@PEBG@Z; ATL::operator==(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> const &,ushort const *)
0x140043d30  test    al, al
0x140043d32  jz      short loc_140043D42
0x140043d34  xor     edi, edi
0x140043d36  lea     r14, WPP_GLOBAL_Control
0x140043d3d  jmp     loc_14004407A
0x140043d42  call    ?IsWMPNSSContextCurrentlyEnabled@CWMCService@@QEAAHXZ; CWMCService::IsWMPNSSContextCurrentlyEnabled(void)
0x140043d47  test    eax, eax
0x140043d49  jnz     short loc_140043D95
0x140043d4b  mov     edi, 80070005h
0x140043d50  mov     rax, cs:WPP_GLOBAL_Control
0x140043d57  lea     r14, WPP_GLOBAL_Control
0x140043d5e  cmp     rax, r14
0x140043d61  jz      loc_1400440B7
0x140043d67  test    byte ptr [rax+1Ch], 2
0x140043d6b  jz      loc_140044081
0x140043d71  cmp     byte ptr [rax+19h], 5
0x140043d75  jb      loc_140044081
0x140043d7b  mov     edx, 37h ; '7'
0x140043d80  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x140043d87  mov     rcx, [rax+10h]
0x140043d8b  call    WPP_SF_
0x140043d90  jmp     loc_14004407A
0x140043d95  xor     edi, edi
0x140043d97  mov     rcx, [rbp+3Fh+var_78]
0x140043d9b  add     rcx, 28h ; '('; lpCriticalSection
0x140043d9f  call    cs:__imp_EnterCriticalSection
0x140043da5  mov     [rbp+3Fh+var_80], 1
0x140043dac  call    cs:__imp_GetTickCount
0x140043db2  mov     ebx, eax
0x140043db4  mov     rcx, [rbp+3Fh+var_78]
0x140043db8  add     rcx, 158h
0x140043dbf  mov     rdx, [rsi]
0x140043dc2  call    ??A?$CAtlMap@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@KV?$CLocaleStringElementTraitsI@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@V?$CLocaleCharTraits@G@@@@V?$CElementTraits@K@2@@ATL@@QEAAAEAKPEBG@Z; ATL::CAtlMap<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,ulong,CLocaleStringElementTraitsI<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>,CLocaleCharTraits<ushort>>,ATL::CElementTraits<ulong>>::operator[](ushort const *)
0x140043dc7  mov     [rax], ebx
0x140043dc9  mov     rdx, r15; unsigned __int16 *
0x140043dcc  lea     rcx, [rbp+3Fh+var_90]; this
0x140043dd0  call    ??0CRendererDevicesDB@@QEAA@PEBG@Z; CRendererDevicesDB::CRendererDevicesDB(ushort const *)
0x140043dd5  nop
0x140043dd6  mov     rdx, [rsi]; unsigned __int16 *
0x140043dd9  lea     rcx, [rbp+3Fh+var_90]; this
0x140043ddd  call    ?IsExistingDevice@CDevicesDB@@QEAAHPEBG@Z; CDevicesDB::IsExistingDevice(ushort const *)
0x140043de2  xor     ebx, ebx
0x140043de4  mov     r15d, 80070000h
0x140043dea  test    eax, eax
0x140043dec  jnz     loc_140043F94
0x140043df2  mov     rdx, [rsi]; unsigned __int16 *
0x140043df5  lea     rcx, [rbp+3Fh+var_90]; this
0x140043df9  call    ?CreateDevice@CDevicesDB@@QEAAJPEBG@Z; CDevicesDB::CreateDevice(ushort const *)
0x140043dfe  mov     edi, eax
0x140043e00  test    eax, eax
0x140043e02  jle     short loc_140043E0A
0x140043e04  movzx   edi, ax
0x140043e07  or      edi, r15d
0x140043e0a  test    edi, edi
0x140043e0c  js      loc_140043F85
0x140043e12  lea     r9, a1_0; "1"
0x140043e19  lea     r8, aIscontrolpoint; "IsControlPoint"
0x140043e20  mov     rdx, [rsi]; unsigned __int16 *
0x140043e23  lea     rcx, [rbp+3Fh+var_90]; this
0x140043e27  call    ?SetDeviceProperty@CDevicesDB@@QEAAJPEBG00@Z; CDevicesDB::SetDeviceProperty(ushort const *,ushort const *,ushort const *)
0x140043e2c  mov     edi, eax
0x140043e2e  test    eax, eax
0x140043e30  jle     short loc_140043E38
0x140043e32  movzx   edi, ax
0x140043e35  or      edi, r15d
0x140043e38  test    edi, edi
0x140043e3a  js      loc_140043F79
0x140043e40  test    r14, r14
0x140043e43  jz      loc_140043F17
0x140043e49  lea     r15, ??_7CNetworkInterfaces@@6B@; const CNetworkInterfaces::`vftable'
0x140043e50  mov     [rbp+3Fh+var_70], r15
0x140043e54  mov     [rbp+3Fh+var_68], rbx
0x140043e58  lea     rcx, [rbp+3Fh+var_70]; this
0x140043e5c  call    ?Initialize@CNetworkInterfaces@@MEAAJXZ; CNetworkInterfaces::Initialize(void)
0x140043e61  nop
0x140043e62  test    eax, eax
0x140043e64  js      loc_140043F02
0x140043e6a  xorps   xmm0, xmm0
0x140043e6d  movups  xmmword ptr [rbp+3Fh+var_58.Data1], xmm0
0x140043e71  mov     [rbp+3Fh+pdwBestIfIndex], ebx
0x140043e74  mov     eax, 17h
0x140043e79  cmp     ax, [r14]
0x140043e7d  jnz     short loc_140043E8E
0x140043e7f  mov     r8d, [r14+18h]
0x140043e83  test    r8d, r8d
0x140043e86  jz      short loc_140043E8E
0x140043e88  mov     [rbp+3Fh+pdwBestIfIndex], r8d
0x140043e8c  jmp     short loc_140043EB1
0x140043e8e  lea     rdx, [rbp+3Fh+pdwBestIfIndex]; pdwBestIfIndex
0x140043e92  mov     rcx, r14; pDestAddr
0x140043e95  call    cs:__imp_GetBestInterfaceEx
0x140043e9b  test    eax, eax
0x140043e9d  jz      short loc_140043EAD
0x140043e9f  jle     short loc_140043EAB
0x140043ea1  movzx   eax, ax
0x140043ea4  or      eax, 80070000h
0x140043ea9  test    eax, eax
0x140043eab  js      short loc_140043F02
0x140043ead  mov     r8d, [rbp+3Fh+pdwBestIfIndex]; unsigned int
0x140043eb1  lea     r9, [rbp+3Fh+var_58]; struct _GUID *
0x140043eb5  movzx   edx, word ptr [r14]; unsigned __int16
0x140043eb9  lea     rcx, [rbp+3Fh+var_70]; this
0x140043ebd  call    ?_FindInterfaceUsingIndex@CNetworkInterfaces@@IEAAJGKPEAU_GUID@@@Z; CNetworkInterfaces::_FindInterfaceUsingIndex(ushort,ulong,_GUID *)
0x140043ec2  test    eax, eax
0x140043ec4  js      short loc_140043F02
0x140043ec6  lea     rcx, [rbp+3Fh+pdwBestIfIndex]
0x140043eca  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140043ecf  nop
0x140043ed0  lea     r8, [rbp+3Fh+pdwBestIfIndex]
0x140043ed4  lea     rdx, [rbp+3Fh+var_58]
0x140043ed8  call    ?GetNetworkId@CMACAddressControl@@QEAAJAEBU_GUID@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CMACAddressControl::GetNetworkId(_GUID const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140043edd  test    eax, eax
0x140043edf  js      short loc_140043EF9
0x140043ee1  mov     r9, qword ptr [rbp+3Fh+pdwBestIfIndex]; unsigned __int16 *
0x140043ee5  lea     r8, aNetworkid; "NetworkID"
0x140043eec  mov     rdx, [rsi]; unsigned __int16 *
0x140043eef  lea     rcx, [rbp+3Fh+var_90]; this
0x140043ef3  call    ?SetDeviceProperty@CDevicesDB@@QEAAJPEBG00@Z; CDevicesDB::SetDeviceProperty(ushort const *,ushort const *,ushort const *)
0x140043ef8  nop
0x140043ef9  lea     rcx, [rbp+3Fh+pdwBestIfIndex]
0x140043efd  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140043f02  mov     edi, ebx
0x140043f04  mov     [rbp+3Fh+var_70], r15
0x140043f08  lea     rcx, [rbp+3Fh+var_68]
0x140043f0c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140043f11  mov     r15d, 80070000h
0x140043f17  test    r13, r13
0x140043f1a  jz      short loc_140043F39
0x140043f1c  cmp     bx, [r13+0]
0x140043f21  jz      short loc_140043F39
0x140043f23  mov     r9, r13; unsigned __int16 *
0x140043f26  lea     r8, aIpaddress; "IPAddress"
0x140043f2d  mov     rdx, [rsi]; unsigned __int16 *
0x140043f30  lea     rcx, [rbp+3Fh+var_90]; this
0x140043f34  call    ?SetDeviceProperty@CDevicesDB@@QEAAJPEBG00@Z; CDevicesDB::SetDeviceProperty(ushort const *,ushort const *,ushort const *)
0x140043f39  mov     rax, [rbp+3Fh+var_60]
0x140043f3d  mov     dword ptr [rax], 1
0x140043f43  mov     rcx, cs:WPP_GLOBAL_Control
0x140043f4a  lea     r14, WPP_GLOBAL_Control
0x140043f51  cmp     rcx, r14
0x140043f54  jz      short loc_140043F9B
0x140043f56  test    byte ptr [rcx+1Ch], 2
0x140043f5a  jz      short loc_140043F9B
0x140043f5c  cmp     byte ptr [rcx+19h], 5
0x140043f60  jb      short loc_140043F9B
0x140043f62  mov     edx, 38h ; '8'
0x140043f67  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x140043f6e  mov     rcx, [rcx+10h]
0x140043f72  call    WPP_SF_
0x140043f77  jmp     short loc_140043F9B
0x140043f79  lea     r14, WPP_GLOBAL_Control
0x140043f80  jmp     loc_140044008
0x140043f85  mov     [rbp+3Fh+var_98], ebx
0x140043f88  lea     r14, WPP_GLOBAL_Control
0x140043f8f  jmp     loc_14004402B
0x140043f94  lea     r14, WPP_GLOBAL_Control
0x140043f9b  test    r12, r12
0x140043f9e  jz      short loc_140044008
0x140043fa0  cmp     bx, [r12]
0x140043fa5  jz      short loc_140044008
0x140043fa7  lea     rcx, [rbp+3Fh+pdwBestIfIndex]
0x140043fab  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>>(void)
0x140043fb0  nop
0x140043fb1  lea     r9, [rbp+3Fh+pdwBestIfIndex]
0x140043fb5  lea     r8, aFriendlyname_0; "FriendlyName"
0x140043fbc  mov     rdx, [rsi]
0x140043fbf  lea     rcx, [rbp+3Fh+var_90]; this
0x140043fc3  call    ?GetDeviceProperty@CDevicesDB@@QEAAJPEBG0AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsOS@G@ATL@@@ATL@@@ATL@@@Z; CDevicesDB::GetDeviceProperty(ushort const *,ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsOS<ushort>>> &)
0x140043fc8  test    eax, eax
0x140043fca  jnz     short loc_140043FE8
0x140043fcc  mov     [rsp+0F0h+bIgnoreCase], ebx; bIgnoreCase
0x140043fd0  or      edx, 0FFFFFFFFh; cchCount1
0x140043fd3  mov     r9d, edx; cchCount2
0x140043fd6  mov     r8, r12; lpString2
0x140043fd9  mov     rcx, qword ptr [rbp+3Fh+pdwBestIfIndex]; lpString1
0x140043fdd  call    cs:__imp_CompareStringOrdinal
0x140043fe3  cmp     eax, 2
0x140043fe6  jz      short loc_140043FFF
0x140043fe8  mov     r9, r12; unsigned __int16 *
0x140043feb  lea     r8, aFriendlyname_0; "FriendlyName"
0x140043ff2  mov     rdx, [rsi]; unsigned __int16 *
0x140043ff5  lea     rcx, [rbp+3Fh+var_90]; this
0x140043ff9  call    ?SetDeviceProperty@CDevicesDB@@QEAAJPEBG00@Z; CDevicesDB::SetDeviceProperty(ushort const *,ushort const *,ushort const *)
0x140043ffe  nop
0x140043fff  lea     rcx, [rbp+3Fh+pdwBestIfIndex]
0x140044003  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x140044008  mov     [rbp+3Fh+var_98], ebx
0x14004400b  test    edi, edi
0x14004400d  js      short loc_14004402B
0x14004400f  lea     r8, [rbp+3Fh+var_98]; unsigned int *
0x140044013  mov     rdx, [rsi]; unsigned __int16 *
0x140044016  lea     rcx, [rbp+3Fh+var_90]; this
0x14004401a  call    ?GetDeviceAuthorization@CDevicesDB@@UEAAJPEBGAEAK@Z; CDevicesDB::GetDeviceAuthorization(ushort const *,ulong &)
0x14004401f  mov     edi, eax
0x140044021  test    eax, eax
0x140044023  jle     short loc_14004402B
0x140044025  movzx   edi, ax
0x140044028  or      edi, r15d
0x14004402b  lea     rdx, [rbp+3Fh+var_80]; int *
0x14004402f  mov     rcx, [rbp+3Fh+var_78]; this
0x140044033  call    ?ReleaseManagerLock@CMACAddressControl@@AEAAXAEAH@Z; CMACAddressControl::ReleaseManagerLock(int &)
0x140044038  cmp     [rbp+3Fh+var_98], 1
0x14004403c  jz      short loc_140044071
0x14004403e  mov     edi, 80070005h
0x140044043  mov     rcx, cs:WPP_GLOBAL_Control
0x14004404a  cmp     rcx, r14
0x14004404d  jz      short loc_140044071
0x14004404f  test    byte ptr [rcx+1Ch], 2
0x140044053  jz      short loc_140044071
0x140044055  cmp     byte ptr [rcx+19h], 5
0x140044059  jb      short loc_140044071
0x14004405b  mov     edx, 39h ; '9'
0x140044060  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x140044067  mov     rcx, [rcx+10h]
0x14004406b  call    WPP_SF_
0x140044070  nop
0x140044071  lea     rcx, [rbp+3Fh+var_88]
0x140044075  call    ??1?$CSimpleStringT@G$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<ushort,0>::~CSimpleStringT<ushort,0>(void)
0x14004407a  mov     rax, cs:WPP_GLOBAL_Control
0x140044081  cmp     rax, r14
0x140044084  jz      short loc_1400440B7
0x140044086  test    byte ptr [rax+1Ch], 1
0x14004408a  jz      short loc_1400440B7
0x14004408c  mov     edx, edi
0x14004408e  sar     edx, 1Fh
0x140044091  and     edx, 0FFFFFFFDh
0x140044094  add     edx, 5
0x140044097  movzx   ecx, byte ptr [rax+19h]
0x14004409b  cmp     ecx, edx
0x14004409d  jb      short loc_1400440B7
0x14004409f  mov     edx, 3Ah ; ':'
0x1400440a4  mov     r9d, edi
0x1400440a7  lea     r8, WPP_6b9cd232ff85337f7587051b4c371d3d_Traceguids
0x1400440ae  mov     rcx, [rax+10h]
0x1400440b2  call    WPP_SF_d
0x1400440b7  mov     eax, edi
0x1400440b9  mov     rcx, [rbp+3Fh+var_48]
0x1400440bd  xor     rcx, rsp; StackCookie
0x1400440c0  call    __security_check_cookie
0x1400440c5  add     rsp, 0B8h
0x1400440cc  pop     r15
0x1400440ce  pop     r14
0x1400440d0  pop     r13
0x1400440d2  pop     r12
0x1400440d4  pop     rdi
0x1400440d5  pop     rsi
0x1400440d6  pop     rbx
0x1400440d7  pop     rbp
0x1400440d8  retn
```
