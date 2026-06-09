# IppConfigureForFamily(ushort,IP_CONFIG_ACTION,_GUID const &,ushort const *)

- ea: `0x18008444c`
- end: `0x180084c58`
- name: `?IppConfigureForFamily@@YAJGW4IP_CONFIG_ACTION@@AEBU_GUID@@PEBG@Z`
- size: `2060`
- prototype: `int __high(unsigned __int16, enum IP_CONFIG_ACTION, const struct _GUID *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `24`
- tags: `registry_config, loader_planting`

## callers

- `0x1800d2ab0`
- `0x1800d2b6c`

## callees

- `0x18001b9d4`
- `0x18001c3c0`
- `0x1800288c4`
- `0x180029ca0`
- `0x180039d04`
- `0x18008444c`
- `0x180084c60`
- `0x1800a9e18`
- `0x1800ba438`
- `0x1800ba588`
- `0x1800ba678`
- `0x18010680c`
- `0x1801ac23c`
- `0x1801ac2ac`
- `0x1801ac5b4`
- `0x1801ac68c`
- `0x1801ac6bc`
- `0x1801ac778`
- `0x1801ac7d0`
- `0x1801acab0`
- `0x1801acb7c`
- `0x1801acc54`
- `0x1801acd10`
- `0x1801acde0`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringExW` at `0x180084904`
- `ntdll!RtlIpv4AddressToStringExW` at `0x180084904`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800849b4`
- `ntdll!RtlIpv6AddressToStringExW` at `0x1800849b4`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180084630`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180084630`

## string_xrefs

- `0x1800844cf`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18008454d`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x1800845c3`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x180084608`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x180084645`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x1800846ef`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18008478c`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x1800847b4`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x1800847e6`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x18008485e`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x180084920`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x1800849cc`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x180084abe`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`
- `0x180084c0d`: `onecoreuap\net\wlan\autocfg\server\ipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall IppConfigureForFamily(unsigned __int16 a1, int a2, const struct _GUID *a3)
{
  unsigned int v6; // r13d
  int v7; // r12d
  const char *v8; // r9
  bool IsDhcpEnabled; // r15
  int v10; // eax
  unsigned int v11; // esi
  __int64 result; // rax
  int v13; // eax
  wil::details::in1diag3 *v14; // rcx
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // esi
  int v18; // eax
  unsigned int v19; // esi
  _DWORD *v20; // rax
  unsigned int v21; // eax
  unsigned int v22; // ebx
  char *v23; // r15
  int v24; // esi
  int v25; // eax
  wil::details::in1diag3 *v26; // rcx
  __int64 v27; // rdx
  char *v28; // r15
  int v29; // esi
  int v30; // eax
  wil::details::in1diag3 *v31; // rcx
  __int64 v32; // rdx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  char *v35; // r15
  unsigned int v36; // ebx
  unsigned __int64 v37; // rsi
  __int16 v38; // r14
  ULONG v39; // eax
  unsigned int v40; // eax
  unsigned int v41; // ebx
  unsigned int v42; // eax
  _QWORD *v43; // rsi
  unsigned __int64 v44; // r14
  int v45; // eax
  unsigned int v46; // r14d
  unsigned int v47; // ebx
  unsigned int v48; // [rsp+20h] [rbp-98h]
  _DWORD *v49; // [rsp+30h] [rbp-88h] BYREF
  NET_LUID InterfaceLuid; // [rsp+38h] [rbp-80h] BYREF
  ULONG AddressStringLength; // [rsp+40h] [rbp-78h] BYREF
  __int128 v52; // [rsp+48h] [rbp-70h] BYREF
  __int64 v53; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v54; // [rsp+60h] [rbp-58h] BYREF
  _QWORD *v55; // [rsp+68h] [rbp-50h] BYREF
  unsigned __int64 v56; // [rsp+70h] [rbp-48h]
  __int64 v57; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v6 = 0;
  v7 = 0;
  AddressStringLength = 0;
  try
  {
    TryGetProfileIpConfig();
    if ( !v49 )
      return 0;
    if ( v49[1] )
    {
      if ( !a2 )
      {
        IsDhcpEnabled = IppIsDhcpEnabled(a1, a3);
        v10 = IpEnableDhcp(a1, a3, 0);
        v11 = v10;
        if ( v10 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x147,
            (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
            (const char *)(unsigned int)v10,
            v48);
          std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
          return v11;
        }
        if ( IsDhcpEnabled )
        {
          v13 = IpSetDhcpOffDueToStaticIp(a1, a3, 1);
          v14 = retaddr;
          if ( v13 < 0 )
          {
            v15 = 333;
LABEL_21:
            wil::details::in1diag3::_Log_Hr(
              v14,
              (void *)v15,
              (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
              (const char *)(unsigned int)v13,
              v48);
            goto LABEL_22;
          }
        }
        goto LABEL_22;
      }
    }
    else if ( v49[5] && !a2 )
    {
      v16 = IpEnableDhcp(a1, a3, 1);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x154,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
          (const char *)(unsigned int)v16,
          v48);
        std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
        return v17;
      }
      v13 = IpSetDhcpOffDueToStaticIp(a1, a3, 0);
      v14 = retaddr;
      if ( v13 < 0 )
      {
        v15 = 341;
        goto LABEL_21;
      }
LABEL_22:
      v20 = v49;
      if ( v49[1] )
      {
        InterfaceLuid.Value = 0;
        v21 = ConvertInterfaceGuidToLuid(a3, &InterfaceLuid);
        if ( v21 )
        {
          v22 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x168,
                  (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                  (const char *)v21,
                  v48);
          std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
          return v22;
        }
        v20 = v49;
        if ( !v49[1] || !v49[2] )
        {
          v34 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x16B,
                  (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                  (const char *)0x57,
                  v48);
          std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
          return v34;
        }
        v23 = (char *)v49 + (unsigned int)v49[2];
        v24 = 0;
        while ( a2 )
        {
          if ( a2 == 1 )
          {
            v25 = IppCleanAddress(InterfaceLuid, (const struct _WLAN_PROFILE_IP_ADDRESS_ENTRY *)&v23[136 * v24]);
            v26 = retaddr;
            if ( v25 < 0 )
            {
              v27 = 373;
LABEL_34:
              wil::details::in1diag3::_Log_Hr(
                v26,
                (void *)v27,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                (const char *)(unsigned int)v25,
                v48);
            }
LABEL_35:
            v20 = v49;
          }
          if ( (unsigned int)++v24 >= v20[1] )
          {
            if ( !v20[3] || !v20[4] )
            {
              v33 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x17A,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                      (const char *)0x57,
                      v48);
              std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
              return v33;
            }
            v28 = (char *)v20 + (unsigned int)v20[4];
            v29 = 0;
            while ( a2 )
            {
              if ( a2 == 1 )
              {
                v30 = IppCleanGateway(
                        InterfaceLuid,
                        (const struct _WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY *)&v28[136 * v29]);
                v31 = retaddr;
                if ( v30 < 0 )
                {
                  v32 = 388;
LABEL_46:
                  wil::details::in1diag3::_Log_Hr(
                    v31,
                    (void *)v32,
                    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                    (const char *)(unsigned int)v30,
                    v48);
                }
LABEL_47:
                v20 = v49;
              }
              if ( (unsigned int)++v29 >= v20[3] )
                goto LABEL_52;
            }
            v30 = IppApplyGateway(InterfaceLuid, (const struct _WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY *)&v28[136 * v29]);
            v31 = retaddr;
            if ( v30 < 0 )
            {
              v32 = 384;
              goto LABEL_46;
            }
            goto LABEL_47;
          }
        }
        v25 = IppApplyAddress(InterfaceLuid, (const struct _WLAN_PROFILE_IP_ADDRESS_ENTRY *)&v23[136 * v24]);
        v26 = retaddr;
        if ( v25 < 0 )
        {
          v27 = 369;
          goto LABEL_34;
        }
        goto LABEL_35;
      }
LABEL_52:
      if ( v20[5] )
      {
        if ( !v20[6] )
        {
          v47 = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x18C,
                  (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                  (const char *)0x57,
                  v48);
          std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
          return v47;
        }
        v35 = (char *)v20 + (unsigned int)v20[6];
        if ( *v20 == 2 )
        {
          if ( !v20[6] )
          {
            v36 = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x191,
                    (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                    (const char *)0x57,
                    v48);
            std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
            return v36;
          }
          v56 = (unsigned __int64)&v20[32 * (unsigned __int64)(unsigned int)v20[5]] + (unsigned int)v20[6];
        }
        else
        {
          v56 = 0;
        }
        v52 = 0;
        v53 = 0;
        if ( !a2 )
        {
          while ( 1 )
          {
            if ( v6 >= v20[5] )
              goto LABEL_86;
            v37 = (unsigned __int64)v6 << 7;
            v38 = *(_WORD *)&v35[v37];
            if ( v38 == a1 )
              break;
LABEL_85:
            ++v6;
          }
          v39 = 22;
          if ( v38 != 2 )
            v39 = 65;
          AddressStringLength = v39;
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&InterfaceLuid);
          v7 |= 1u;
          if ( v38 == 2 )
          {
            v40 = RtlIpv4AddressToStringExW(
                    (const struct in_addr *)&v35[v37 + 4],
                    0,
                    (PWSTR)InterfaceLuid.Value,
                    &AddressStringLength);
            if ( v40 )
            {
              v41 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1A8,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                      (const char *)v40,
                      v48);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&InterfaceLuid);
              if ( (_QWORD)v52 )
              {
                std::_Destroy_range<std::allocator<std::unique_ptr<DnsConfig>>>(v52, *((__int64 *)&v52 + 1));
                std::_Deallocate<16>((void *)v52, (const struct std::nothrow_t *)((v53 - v52) & 0xFFFFFFFFFFFFFFF8uLL));
                v52 = 0;
                v53 = 0;
              }
LABEL_68:
              std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
              return v41;
            }
          }
          else
          {
            if ( v38 != 23 )
            {
LABEL_84:
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&InterfaceLuid);
              v20 = v49;
              goto LABEL_85;
            }
            v42 = RtlIpv6AddressToStringExW(
                    (const struct in6_addr *)&v35[v37 + 8],
                    *(_DWORD *)&v35[v37 + 24],
                    0,
                    (PWSTR)InterfaceLuid.Value,
                    &AddressStringLength);
            if ( v42 )
            {
              v41 = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)0x1AE,
                      (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                      (const char *)v42,
                      v48);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&InterfaceLuid);
              if ( (_QWORD)v52 )
              {
                std::_Destroy_range<std::allocator<std::unique_ptr<DnsConfig>>>(v52, *((__int64 *)&v52 + 1));
                std::_Deallocate<16>((void *)v52, (const struct std::nothrow_t *)((v53 - v52) & 0xFFFFFFFFFFFFFFF8uLL));
                v52 = 0;
                v53 = 0;
              }
              goto LABEL_68;
            }
          }
          v43 = operator new(0x18u);
          v43[1] = 0;
          *v43 = 0;
          v43[2] = 0;
          v55 = v43;
          v7 |= 4u;
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            v43,
            &InterfaceLuid);
          *((_DWORD *)v43 + 2) = 0;
          v44 = v56;
          if ( v56 )
          {
            wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v54);
            v57 = 4104LL * v6;
            v45 = StringCchCopyW(v54, 0x800u, (const unsigned __int16 *)(v57 + v44 + 8));
            v46 = v45;
            if ( v45 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1BE,
                (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                (const char *)(unsigned int)v45,
                v48);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
              std::unique_ptr<DnsConfig>::~unique_ptr<DnsConfig>(&v55);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&InterfaceLuid);
              if ( (_QWORD)v52 )
              {
                std::_Destroy_range<std::allocator<std::unique_ptr<DnsConfig>>>(v52, *((__int64 *)&v52 + 1));
                std::_Deallocate<16>((void *)v52, (const struct std::nothrow_t *)((v53 - v52) & 0xFFFFFFFFFFFFFFF8uLL));
                v52 = 0;
                v53 = 0;
              }
              std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
              return v46;
            }
            v7 |= 8u;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
              v43 + 2,
              &v54);
            *((_DWORD *)v43 + 2) = *(_DWORD *)(v57 + v56 + 4);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v54);
          }
          if ( *((_QWORD *)&v52 + 1) == v53 )
          {
            std::vector<std::unique_ptr<DnsConfig>>::_Emplace_reallocate<std::unique_ptr<DnsConfig>>(
              (__int64 *)&v52,
              *((__int64 *)&v52 + 1),
              (__int64 *)&v55);
          }
          else
          {
            v55 = 0;
            **((_QWORD **)&v52 + 1) = v43;
            *((_QWORD *)&v52 + 1) += 8LL;
          }
          std::unique_ptr<DnsConfig>::~unique_ptr<DnsConfig>(&v55);
          goto LABEL_84;
        }
LABEL_86:
        IppApplyDnsServerList(a1, a3, &v52);
        if ( (_QWORD)v52 )
        {
          std::_Destroy_range<std::allocator<std::unique_ptr<DnsConfig>>>(v52, *((__int64 *)&v52 + 1));
          std::_Deallocate<16>((void *)v52, (const struct std::nothrow_t *)((v53 - v52) & 0xFFFFFFFFFFFFFFF8uLL));
        }
      }
      std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
      return 0;
    }
    if ( IpGetDhcpOffDueToStaticIp(a1, a3) )
    {
      v18 = IpEnableDhcp(a1, a3, 1);
      v19 = v18;
      if ( v18 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x160,
          (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
          (const char *)(unsigned int)v18,
          v48);
        std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&int FreeWLMem(void *)>>(&v49);
        return v19;
      }
      v13 = IpSetDhcpOffDueToStaticIp(a1, a3, 0);
      v14 = retaddr;
      if ( v13 < 0 )
      {
        v15 = 353;
        goto LABEL_21;
      }
    }
    goto LABEL_22;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1CD,
                           (unsigned int)"onecoreuap\\net\\wlan\\autocfg\\server\\ipconfig.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x18008444c  push    rbx
0x18008444e  push    rsi
0x18008444f  push    rdi
0x180084450  push    r12
0x180084452  push    r13
0x180084454  push    r14
0x180084456  push    r15
0x180084458  sub     rsp, 80h
0x18008445f  mov     rbx, r8
0x180084462  mov     r14d, edx
0x180084465  movzx   edi, cx
0x180084468  xor     r13d, r13d
0x18008446b  mov     r12d, r13d
0x18008446e  mov     [rsp+0B8h+AddressStringLength], r13d
0x180084473  movzx   edx, cx
0x180084476  lea     rcx, [rsp+0B8h+var_88]
0x18008447b  call    ?TryGetProfileIpConfig@@YA?AV?$unique_ptr@U_WLAN_PROFILE_IP_CONFIGURATION@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@GAEBU_GUID@@QEBG@Z; TryGetProfileIpConfig(ushort,_GUID const &,ushort const * const)
0x180084480  nop
0x180084481  mov     rax, [rsp+0B8h+var_88]
0x180084486  test    rax, rax
0x180084489  jz      loc_180084C3C
0x18008448f  cmp     [rax+4], r13d
0x180084493  jbe     loc_180084523
0x180084499  test    r14d, r14d
0x18008449c  jnz     loc_180084595
0x1800844a2  mov     rdx, rbx; struct _GUID *
0x1800844a5  movzx   ecx, di; unsigned __int16
0x1800844a8  call    ?IppIsDhcpEnabled@@YA_NGAEBU_GUID@@@Z; IppIsDhcpEnabled(ushort,_GUID const &)
0x1800844ad  mov     r15b, al
0x1800844b0  xor     r8d, r8d; bool
0x1800844b3  mov     rdx, rbx; struct _GUID *
0x1800844b6  movzx   ecx, di; unsigned __int16
0x1800844b9  call    ?IpEnableDhcp@@YAJGAEBU_GUID@@_N@Z; IpEnableDhcp(ushort,_GUID const &,bool)
0x1800844be  mov     esi, eax
0x1800844c0  test    eax, eax
0x1800844c2  jns     short loc_1800844F2
0x1800844c4  mov     rcx, [rsp+0B8h]; this
0x1800844cc  mov     r9d, eax; char *
0x1800844cf  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800844d6  mov     edx, 147h; void *
0x1800844db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800844e0  nop
0x1800844e1  lea     rcx, [rsp+0B8h+var_88]
0x1800844e6  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x1800844eb  mov     eax, esi
0x1800844ed  jmp     loc_180084C44
0x1800844f2  test    r15b, r15b
0x1800844f5  jz      loc_180084614
0x1800844fb  mov     r8b, 1; bool
0x1800844fe  mov     rdx, rbx; struct _GUID *
0x180084501  movzx   ecx, di; unsigned __int16
0x180084504  call    ?IpSetDhcpOffDueToStaticIp@@YAJGAEBU_GUID@@_N@Z; IpSetDhcpOffDueToStaticIp(ushort,_GUID const &,bool)
0x180084509  mov     rcx, [rsp+0B8h]
0x180084511  test    eax, eax
0x180084513  jns     loc_180084614
0x180084519  mov     edx, 14Dh
0x18008451e  jmp     loc_180084605
0x180084523  cmp     [rax+14h], r13d
0x180084527  jbe     short loc_180084595
0x180084529  test    r14d, r14d
0x18008452c  jnz     short loc_180084595
0x18008452e  mov     r8b, 1; bool
0x180084531  mov     rdx, rbx; struct _GUID *
0x180084534  movzx   ecx, di; unsigned __int16
0x180084537  call    ?IpEnableDhcp@@YAJGAEBU_GUID@@_N@Z; IpEnableDhcp(ushort,_GUID const &,bool)
0x18008453c  mov     esi, eax
0x18008453e  test    eax, eax
0x180084540  jns     short loc_180084570
0x180084542  mov     rcx, [rsp+0B8h]; this
0x18008454a  mov     r9d, eax; char *
0x18008454d  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180084554  mov     edx, 154h; void *
0x180084559  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008455e  nop
0x18008455f  lea     rcx, [rsp+0B8h+var_88]
0x180084564  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x180084569  mov     eax, esi
0x18008456b  jmp     loc_180084C44
0x180084570  xor     r8d, r8d; bool
0x180084573  mov     rdx, rbx; struct _GUID *
0x180084576  movzx   ecx, di; unsigned __int16
0x180084579  call    ?IpSetDhcpOffDueToStaticIp@@YAJGAEBU_GUID@@_N@Z; IpSetDhcpOffDueToStaticIp(ushort,_GUID const &,bool)
0x18008457e  mov     rcx, [rsp+0B8h]
0x180084586  test    eax, eax
0x180084588  jns     loc_180084614
0x18008458e  mov     edx, 155h
0x180084593  jmp     short loc_180084605
0x180084595  mov     rdx, rbx; struct _GUID *
0x180084598  movzx   ecx, di; unsigned __int16
0x18008459b  call    ?IpGetDhcpOffDueToStaticIp@@YA_NGAEBU_GUID@@@Z; IpGetDhcpOffDueToStaticIp(ushort,_GUID const &)
0x1800845a0  test    al, al
0x1800845a2  jz      short loc_180084614
0x1800845a4  mov     r8b, 1; bool
0x1800845a7  mov     rdx, rbx; struct _GUID *
0x1800845aa  movzx   ecx, di; unsigned __int16
0x1800845ad  call    ?IpEnableDhcp@@YAJGAEBU_GUID@@_N@Z; IpEnableDhcp(ushort,_GUID const &,bool)
0x1800845b2  mov     esi, eax
0x1800845b4  test    eax, eax
0x1800845b6  jns     short loc_1800845E6
0x1800845b8  mov     rcx, [rsp+0B8h]; this
0x1800845c0  mov     r9d, eax; char *
0x1800845c3  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800845ca  mov     edx, 160h; void *
0x1800845cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800845d4  nop
0x1800845d5  lea     rcx, [rsp+0B8h+var_88]
0x1800845da  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x1800845df  mov     eax, esi
0x1800845e1  jmp     loc_180084C44
0x1800845e6  xor     r8d, r8d; bool
0x1800845e9  mov     rdx, rbx; struct _GUID *
0x1800845ec  movzx   ecx, di; unsigned __int16
0x1800845ef  call    ?IpSetDhcpOffDueToStaticIp@@YAJGAEBU_GUID@@_N@Z; IpSetDhcpOffDueToStaticIp(ushort,_GUID const &,bool)
0x1800845f4  mov     rcx, [rsp+0B8h]; this
0x1800845fc  test    eax, eax
0x1800845fe  jns     short loc_180084614
0x180084600  mov     edx, 161h; void *
0x180084605  mov     r9d, eax; char *
0x180084608  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18008460f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180084614  mov     rax, [rsp+0B8h+var_88]
0x180084619  cmp     [rax+4], r13d
0x18008461d  jbe     loc_18008480A
0x180084623  mov     qword ptr [rsp+0B8h+InterfaceLuid], r13
0x180084628  lea     rdx, [rsp+0B8h+InterfaceLuid]; InterfaceLuid
0x18008462d  mov     rcx, rbx; InterfaceGuid
0x180084630  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180084636  test    eax, eax
0x180084638  jz      short loc_180084669
0x18008463a  mov     rcx, [rsp+0B8h]; this
0x180084642  mov     r9d, eax; char *
0x180084645  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x18008464c  mov     edx, 168h; void *
0x180084651  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180084656  mov     ebx, eax
0x180084658  lea     rcx, [rsp+0B8h+var_88]
0x18008465d  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x180084662  mov     eax, ebx
0x180084664  jmp     loc_180084C44
0x180084669  mov     rax, [rsp+0B8h+var_88]
0x18008466e  mov     ecx, [rax+4]
0x180084671  test    ecx, ecx
0x180084673  jz      loc_1800847D8
0x180084679  cmp     [rax+8], r13d
0x18008467d  jz      loc_1800847D8
0x180084683  mov     r15d, [rax+8]
0x180084687  add     r15, rax
0x18008468a  mov     esi, r13d
0x18008468d  test    ecx, ecx
0x18008468f  jz      short loc_180084707
0x180084691  test    r14d, r14d
0x180084694  jnz     short loc_1800846BF
0x180084696  mov     eax, esi
0x180084698  imul    rdx, rax, 88h
0x18008469f  add     rdx, r15; struct _WLAN_PROFILE_IP_ADDRESS_ENTRY *
0x1800846a2  mov     rcx, qword ptr [rsp+0B8h+InterfaceLuid]; union _NET_LUID_LH
0x1800846a7  call    ?IppApplyAddress@@YAJT_NET_LUID_LH@@AEBU_WLAN_PROFILE_IP_ADDRESS_ENTRY@@@Z; IppApplyAddress(_NET_LUID_LH,_WLAN_PROFILE_IP_ADDRESS_ENTRY const &)
0x1800846ac  mov     rcx, [rsp+0B8h]
0x1800846b4  test    eax, eax
0x1800846b6  jns     short loc_1800846FB
0x1800846b8  mov     edx, 171h
0x1800846bd  jmp     short loc_1800846EC
0x1800846bf  cmp     r14d, 1
0x1800846c3  jnz     short loc_180084700
0x1800846c5  mov     eax, esi
0x1800846c7  imul    rdx, rax, 88h
0x1800846ce  add     rdx, r15; struct _WLAN_PROFILE_IP_ADDRESS_ENTRY *
0x1800846d1  mov     rcx, qword ptr [rsp+0B8h+InterfaceLuid]; union _NET_LUID_LH
0x1800846d6  call    ?IppCleanAddress@@YAJT_NET_LUID_LH@@AEBU_WLAN_PROFILE_IP_ADDRESS_ENTRY@@@Z; IppCleanAddress(_NET_LUID_LH,_WLAN_PROFILE_IP_ADDRESS_ENTRY const &)
0x1800846db  mov     rcx, [rsp+0B8h]; this
0x1800846e3  test    eax, eax
0x1800846e5  jns     short loc_1800846FB
0x1800846e7  mov     edx, 175h; void *
0x1800846ec  mov     r9d, eax; char *
0x1800846ef  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800846f6  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800846fb  mov     rax, [rsp+0B8h+var_88]
0x180084700  inc     esi
0x180084702  cmp     esi, [rax+4]
0x180084705  jb      short loc_180084691
0x180084707  mov     ecx, [rax+0Ch]
0x18008470a  test    ecx, ecx
0x18008470c  jz      loc_1800847A6
0x180084712  cmp     [rax+10h], r13d
0x180084716  jz      loc_1800847A6
0x18008471c  mov     r15d, [rax+10h]
0x180084720  add     r15, rax
0x180084723  mov     esi, r13d
0x180084726  test    ecx, ecx
0x180084728  jz      loc_18008480A
0x18008472e  test    r14d, r14d
0x180084731  jnz     short loc_18008475C
0x180084733  mov     eax, esi
0x180084735  imul    rdx, rax, 88h
0x18008473c  add     rdx, r15; struct _WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY *
0x18008473f  mov     rcx, qword ptr [rsp+0B8h+InterfaceLuid]; union _NET_LUID_LH
0x180084744  call    ?IppApplyGateway@@YAJT_NET_LUID_LH@@AEBU_WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY@@@Z; IppApplyGateway(_NET_LUID_LH,_WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY const &)
0x180084749  mov     rcx, [rsp+0B8h]
0x180084751  test    eax, eax
0x180084753  jns     short loc_180084798
0x180084755  mov     edx, 180h
0x18008475a  jmp     short loc_180084789
0x18008475c  cmp     r14d, 1
0x180084760  jnz     short loc_18008479D
0x180084762  mov     eax, esi
0x180084764  imul    rdx, rax, 88h
0x18008476b  add     rdx, r15; struct _WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY *
0x18008476e  mov     rcx, qword ptr [rsp+0B8h+InterfaceLuid]; union _NET_LUID_LH
0x180084773  call    ?IppCleanGateway@@YAJT_NET_LUID_LH@@AEBU_WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY@@@Z; IppCleanGateway(_NET_LUID_LH,_WLAN_PROFILE_GATEWAY_ADDRESS_ENTRY const &)
0x180084778  mov     rcx, [rsp+0B8h]; this
0x180084780  test    eax, eax
0x180084782  jns     short loc_180084798
0x180084784  mov     edx, 184h; void *
0x180084789  mov     r9d, eax; char *
0x18008478c  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180084793  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180084798  mov     rax, [rsp+0B8h+var_88]
0x18008479d  inc     esi
0x18008479f  cmp     esi, [rax+0Ch]
0x1800847a2  jb      short loc_18008472E
0x1800847a4  jmp     short loc_18008480A
0x1800847a6  mov     rcx, [rsp+0B8h]; this
0x1800847ae  mov     r9d, 57h ; 'W'; char *
0x1800847b4  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800847bb  mov     edx, 17Ah; void *
0x1800847c0  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800847c5  mov     ebx, eax
0x1800847c7  lea     rcx, [rsp+0B8h+var_88]
0x1800847cc  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x1800847d1  mov     eax, ebx
0x1800847d3  jmp     loc_180084C44
0x1800847d8  mov     rcx, [rsp+0B8h]; this
0x1800847e0  mov     r9d, 57h ; 'W'; char *
0x1800847e6  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x1800847ed  mov     edx, 16Bh; void *
0x1800847f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800847f7  mov     ebx, eax
0x1800847f9  lea     rcx, [rsp+0B8h+var_88]
0x1800847fe  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x180084803  mov     eax, ebx
0x180084805  jmp     loc_180084C44
0x18008480a  cmp     [rax+14h], r13d
0x18008480e  jbe     loc_180084C2E
0x180084814  cmp     [rax+18h], r13d
0x180084818  jz      loc_180084BFF
0x18008481e  mov     r15d, [rax+18h]
0x180084822  add     r15, rax
0x180084825  mov     edx, 2
0x18008482a  cmp     [rax], edx
0x18008482c  jnz     short loc_180084882
0x18008482e  cmp     [rax+18h], r13d
0x180084832  jz      short loc_180084850
0x180084834  mov     ecx, [rax+14h]
0x180084837  shl     rcx, 7
0x18008483b  mov     edx, [rax+18h]
0x18008483e  add     rcx, rax
0x180084841  add     rdx, rcx
0x180084844  mov     [rsp+0B8h+var_48], rdx
0x180084849  mov     edx, 2
0x18008484e  jmp     short loc_180084887
0x180084850  mov     rcx, [rsp+0B8h]; this
0x180084858  mov     r9d, 57h ; 'W'; char *
0x18008485e  lea     r8, aOnecoreuapNetW_10; "onecoreuap\\net\\wlan\\autocfg\\server"...
0x180084865  mov     edx, 191h; void *
0x18008486a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18008486f  mov     ebx, eax
0x180084871  lea     rcx, [rsp+0B8h+var_88]
0x180084876  call    ??1?$unique_ptr@U_DOT11_OFFLOAD_NETWORK_V2@@U?$integral_constant@P6AHPEAX@Z$1?FreeWLMem@@YAH0@Z@std@@@std@@QEAA@XZ; std::unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>::~unique_ptr<_DOT11_OFFLOAD_NETWORK_V2,std::integral_constant<int (*)(void *),&FreeWLMem(void *)>>(void)
0x18008487b  mov     eax, ebx
0x18008487d  jmp     loc_180084C44
0x180084882  mov     [rsp+0B8h+var_48], r13
0x180084887  xorps   xmm0, xmm0
0x18008488a  movdqu  [rsp+0B8h+var_70], xmm0
0x180084890  mov     [rsp+0B8h+var_60], r13
0x180084895  test    r14d, r14d
0x180084898  jnz     loc_180084BC2
0x18008489e  cmp     r13d, [rax+14h]
0x1800848a2  jnb     loc_180084BC2
0x1800848a8  mov     esi, r13d
0x1800848ab  shl     rsi, 7
0x1800848af  movzx   r14d, word ptr [rsi+r15]
0x1800848b4  cmp     r14w, di
0x1800848b8  jnz     loc_180084BB5
0x1800848be  mov     eax, 16h
0x1800848c3  lea     ecx, [rax+2Bh]
0x1800848c6  cmp     r14w, dx
0x1800848ca  cmovnz  eax, ecx
0x1800848cd  mov     [rsp+0B8h+AddressStringLength], eax
0x1800848d1  mov     r8d, eax
0x1800848d4  lea     rcx, [rsp+0B8h+InterfaceLuid]
0x1800848d9  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800848de  or      r12d, 1
0x1800848e2  mov     eax, 2
0x1800848e7  cmp     ax, r14w
0x1800848eb  jnz     loc_180084987
0x1800848f1  xor     edx, edx; Port
0x1800848f3  lea     rcx, [r15+4]
0x1800848f7  add     rcx, rsi; Address
0x1800848fa  lea     r9, [rsp+0B8h+AddressStringLength]; AddressStringLength
0x1800848ff  mov     r8, qword ptr [rsp+0B8h+InterfaceLuid]; AddressString
  ... truncated ...
```
