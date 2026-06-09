# SebHelper::PublishDeviceServiceNotification(_GUID const &,_GUID &,ulong,ulong,uchar *)

- ea: `0x1800907c0`
- end: `0x180090b78`
- name: `?PublishDeviceServiceNotification@SebHelper@@QEAAXAEBU_GUID@@AEAU2@KKPEAE@Z`
- size: `952`
- prototype: `void(SebHelper *__hidden this, const struct _GUID *, struct _GUID *, unsigned int, unsigned int, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018eac`

## callees

- `0x1800085d0`
- `0x1800094dc`
- `0x1800094f4`
- `0x180011a58`
- `0x180012300`
- `0x180013288`
- `0x180013588`
- `0x18001375c`
- `0x180014f1c`
- `0x180015d6c`
- `0x18001a63c`
- `0x1800907c0`
- `0x1800c18c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009086e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009086e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090b48`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180090b48`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180090919`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800909f6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180090919`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800909f6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180090aac`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180090aac`
- `MobileNetworking!PersistentRegPathCreateKey` at `0x18009097c`
- `MobileNetworking!PersistentRegPathCreateKey` at `0x180090a59`
- `MobileNetworking!PersistentRegPathCreateKey` at `0x18009097c`
- `MobileNetworking!PersistentRegPathCreateKey` at `0x180090a59`

## string_xrefs

- `0x180090838`: `SebHelper::PublishDeviceServiceNotification`
- `0x18009089e`: `SebHelper::PublishDeviceServiceNotification`
- `0x1800908bb`: `Datasize greater than %d. Serializing data to registry`
- `0x180090854`: `Device Service GUID is NULL`
- `0x18009098c`: `pre-existed, so is just opened`
- `0x180090a6e`: `pre-existed, so is just opened`
- `0x180090985`: `is created`
- `0x1800909d4`: `Failed (%d) to create non-volatile regkey %s`
- `0x1800909fc`: `\DeviceServices\`
- `0x180090ab6`: `Failed to serialize DS notification data into registry, err %d`
- `0x180090a7c`: `Serializing DS notification data to registry. Key %s`
- `0x180090b33`: `Failed to publish SEB event for device service, hr = %d`
- `0x180090ac5`: `Failed to create volatile regkey for holding DS notification data, err %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall SebHelper::PublishDeviceServiceNotification(
        SebHelper *this,
        const struct _GUID *a2,
        struct _GUID *a3,
        int a4,
        DWORD cbData,
        unsigned __int8 *Src)
{
  LPCRITICAL_SECTION v9; // rbx
  struct _RTL_CRITICAL_SECTION *v10; // r13
  __int64 v11; // rdx
  __int64 v12; // rax
  const wchar_t *v13; // r12
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  int v19; // eax
  int v20; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-A8h]
  LPCRITICAL_SECTION v24; // [rsp+60h] [rbp-A0h]
  char v25; // [rsp+68h] [rbp-98h]
  _OWORD v26[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v27; // [rsp+90h] [rbp-70h] BYREF
  __m128i si128; // [rsp+A0h] [rbp-60h]
  _OWORD v29[3]; // [rsp+B0h] [rbp-50h] BYREF
  int v30; // [rsp+E0h] [rbp-20h]
  unsigned int v31; // [rsp+E4h] [rbp-1Ch]
  _BYTE v32[2056]; // [rsp+E8h] [rbp-18h] BYREF
  OLECHAR sz[40]; // [rsp+8F0h] [rbp+7F0h] BYREF
  OLECHAR v34[40]; // [rsp+940h] [rbp+840h] BYREF

  lpData = Src;
  memset_0(v29, 0, 0x838u);
  if ( *(_OWORD *)a2 == *(_OWORD *)&GUID_NULL )
  {
    WwanLog::Warning("SebHelper::PublishDeviceServiceNotification", 0, L"interface GUID is NULL");
  }
  else if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_NULL.Data4 )
  {
    WwanLog::Warning("SebHelper::PublishDeviceServiceNotification", a2, L"Device Service GUID is NULL");
  }
  else
  {
    v9 = lpCriticalSection;
    v10 = lpCriticalSection + 3;
    EnterCriticalSection(lpCriticalSection + 3);
    v24 = v9;
    v25 = 1;
    v29[0] = xmmword_1801214E8;
    v29[1] = *a2;
    v29[2] = *a3;
    v30 = a4;
    if ( cbData <= 0x800 )
    {
      v31 = cbData;
      if ( cbData )
        memcpy_0(v32, Src, cbData);
    }
    else
    {
      WwanLog::Info(
        "SebHelper::PublishDeviceServiceNotification",
        a2,
        L"Datasize greater than %d. Serializing data to registry");
      v31 = cbData;
      v27 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v27) = 0;
      v26[0] = 0;
      v26[1] = si128;
      LOWORD(v26[0]) = 0;
      std::wstring::assign(v26, L"Interfaces");
      StringFromGUID2(a2, sz, 39);
      std::wstring::append(v26, L"\\");
      std::wstring::append(v26, sz);
      v20 = 0;
      v22 = 0;
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      v13 = L"is created";
      if ( (unsigned int)PersistentRegPathCreateKey(0, v12, 0, 983103, 0, &v22, &v20) )
      {
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        WwanLog::Error(
          "SebHelper::PublishDeviceServiceNotification",
          a2,
          L"Failed (%d) to create non-volatile regkey %s");
      }
      else
      {
        v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
        WwanLog::Info("SebHelper::PublishDeviceServiceNotification", a2, L"Non-volatile regkey %s %s", v14, v15);
      }
      StringFromGUID2(a3, v34, 39);
      std::wstring::append(v26, L"\\DeviceServices\\");
      std::wstring::append(v26, v34);
      v20 = 0;
      hKey = 0;
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      v17 = PersistentRegPathCreateKey(0, v16, 1, 983103, 0, &hKey, &v20);
      if ( v17 )
      {
        WwanLog::Error(
          "SebHelper::PublishDeviceServiceNotification",
          a2,
          L"Failed to create volatile regkey for holding DS notification data, err %d",
          v17);
      }
      else
      {
        if ( v20 != 1 )
          v13 = L"pre-existed, so is just opened";
        WwanLog::Info(
          "SebHelper::PublishDeviceServiceNotification",
          a2,
          L"Serializing DS notification data to registry. Key %s",
          v13);
        v18 = RegSetValueExW(hKey, L"Notification", 0, 3u, lpData, cbData);
        if ( v18 )
          WwanLog::Error(
            "SebHelper::PublishDeviceServiceNotification",
            a2,
            L"Failed to serialize DS notification data into registry, err %d",
            v18);
      }
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v22);
      std::wstring::_Tidy_deallocate(v26);
      std::wstring::_Tidy_deallocate(&v27);
    }
    v19 = PubSebEdgeEventSyncInternal(WNF_SEB_MOBILE_BROADBAND_DEVICE_SERVICE_NOTIFICATION, v11, v29);
    if ( v19 < 0 )
      WwanLog::Warning(
        "SebHelper::PublishDeviceServiceNotification",
        0,
        L"Failed to publish SEB event for device service, hr = %d",
        v19 | 0x10000000u);
    LeaveCriticalSection(v10);
  }
}

```

## disassembly

```asm
0x1800907c0  mov     [rsp-8+arg_0], rbx
0x1800907c5  push    rbp
0x1800907c6  push    rsi
0x1800907c7  push    rdi
0x1800907c8  push    r12
0x1800907ca  push    r13
0x1800907cc  push    r14
0x1800907ce  push    r15
0x1800907d0  lea     rbp, [rsp-8A0h]
0x1800907d8  sub     rsp, 9A0h
0x1800907df  mov     rax, cs:__security_cookie
0x1800907e6  xor     rax, rsp
0x1800907e9  mov     [rbp+8D0h+var_40], rax
0x1800907f0  mov     esi, r9d
0x1800907f3  mov     r15, r8
0x1800907f6  mov     rdi, rdx
0x1800907f9  mov     r12, [rbp+8D0h+Src]
0x180090800  mov     [rsp+9D0h+var_978], r12
0x180090805  xor     edx, edx; Val
0x180090807  mov     r8d, 838h; Size
0x18009080d  lea     rcx, [rbp+8D0h+var_920]; void *
0x180090811  call    memset_0
0x180090816  mov     rax, qword ptr cs:GUID_NULL.Data4
0x18009081d  mov     rcx, qword ptr cs:GUID_NULL.Data1
0x180090824  cmp     [rdi], rcx
0x180090827  jnz     short loc_180090849
0x180090829  cmp     [rdi+8], rax
0x18009082d  jnz     short loc_180090849
0x18009082f  lea     r8, aInterfaceGuidI; "interface GUID is NULL"
0x180090836  xor     edx, edx; struct _GUID *
0x180090838  lea     rcx, aSebhelperPubli_2; "SebHelper::PublishDeviceServiceNotifica"...
0x18009083f  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x180090844  jmp     loc_180090B4E
0x180090849  cmp     [r15], rcx
0x18009084c  jnz     short loc_180090860
0x18009084e  cmp     [r15+8], rax
0x180090852  jnz     short loc_180090860
0x180090854  lea     r8, aDeviceServiceG; "Device Service GUID is NULL"
0x18009085b  mov     rdx, rdi
0x18009085e  jmp     short loc_180090838
0x180090860  mov     rbx, cs:lpCriticalSection
0x180090867  lea     r13, [rbx+78h]
0x18009086b  mov     rcx, r13; lpCriticalSection
0x18009086e  call    cs:__imp_EnterCriticalSection
0x180090874  mov     [rsp+9D0h+var_970], rbx
0x180090879  mov     [rsp+9D0h+var_968], 1
0x18009087e  movups  xmm0, cs:xmmword_1801214E8
0x180090885  movdqu  [rbp+8D0h+var_920], xmm0
0x18009088a  movups  xmm0, xmmword ptr [rdi]
0x18009088d  movdqu  [rbp+8D0h+var_910], xmm0
0x180090892  movups  xmm1, xmmword ptr [r15]
0x180090896  movdqu  [rbp+8D0h+var_900], xmm1
0x18009089b  mov     [rbp+8D0h+var_8F0], esi
0x18009089e  lea     rbx, aSebhelperPubli_2; "SebHelper::PublishDeviceServiceNotifica"...
0x1800908a5  mov     r14d, [rbp+8D0h+arg_20]
0x1800908ac  mov     r9d, 800h
0x1800908b2  cmp     r14d, r9d
0x1800908b5  jbe     loc_180090B00
0x1800908bb  lea     r8, aDatasizeGreate; "Datasize greater than %d. Serializing d"...
0x1800908c2  mov     rdx, rdi; struct _GUID *
0x1800908c5  mov     rcx, rbx; char *
0x1800908c8  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800908cd  mov     [rbp+8D0h+var_8EC], r14d
0x1800908d1  xorps   xmm0, xmm0
0x1800908d4  movups  [rbp+8D0h+var_940], xmm0
0x1800908d8  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800908e0  movdqu  [rbp+8D0h+var_930], xmm1
0x1800908e5  xor     esi, esi
0x1800908e7  mov     word ptr [rbp+8D0h+var_940], si
0x1800908eb  movups  [rsp+9D0h+var_960], xmm0
0x1800908f0  movdqu  [rbp+8D0h+var_950], xmm1
0x1800908f5  mov     word ptr [rsp+9D0h+var_960], si
0x1800908fa  lea     rdx, aInterfaces; "Interfaces"
0x180090901  lea     rcx, [rsp+9D0h+var_960]
0x180090906  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18009090b  lea     r8d, [rsi+27h]; cchMax
0x18009090f  lea     rdx, [rbp+8D0h+sz]; lpsz
0x180090916  mov     rcx, rdi; rguid
0x180090919  call    cs:__imp_StringFromGUID2
0x18009091f  lea     rdx, SubBlock; "\\"
0x180090926  lea     rcx, [rsp+9D0h+var_960]
0x18009092b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180090930  lea     rdx, [rbp+8D0h+sz]
0x180090937  lea     rcx, [rsp+9D0h+var_960]
0x18009093c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180090941  nop
0x180090942  mov     [rsp+9D0h+var_990], esi
0x180090946  mov     [rsp+9D0h+var_980], rsi
0x18009094b  lea     rcx, [rsp+9D0h+var_960]
0x180090950  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180090955  mov     rdx, rax
0x180090958  lea     rax, [rsp+9D0h+var_990]
0x18009095d  mov     [rsp+9D0h+var_9A0], rax
0x180090962  lea     rax, [rsp+9D0h+var_980]
0x180090967  mov     qword ptr [rsp+9D0h+cbData], rax
0x18009096c  mov     [rsp+9D0h+lpData], rsi
0x180090971  mov     r9d, 0F003Fh
0x180090977  xor     r8d, r8d
0x18009097a  xor     ecx, ecx
0x18009097c  call    cs:__imp_PersistentRegPathCreateKey
0x180090982  mov     r9d, eax
0x180090985  lea     r12, aIsCreated; "is created"
0x18009098c  lea     rax, aPreExistedSoIs; "pre-existed, so is just opened"
0x180090993  lea     rcx, [rsp+9D0h+var_960]
0x180090998  test    r9d, r9d
0x18009099b  jnz     short loc_1800909CA
0x18009099d  mov     rdx, r12
0x1800909a0  cmp     [rsp+9D0h+var_990], 1
0x1800909a5  cmovnz  rdx, rax
0x1800909a9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800909ae  mov     r9, rax
0x1800909b1  mov     [rsp+9D0h+lpData], rdx
0x1800909b6  lea     r8, aNonVolatileReg; "Non-volatile regkey %s %s"
0x1800909bd  mov     rdx, rdi; struct _GUID *
0x1800909c0  mov     rcx, rbx; char *
0x1800909c3  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x1800909c8  jmp     short loc_1800909E6
0x1800909ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800909cf  mov     [rsp+9D0h+lpData], rax
0x1800909d4  lea     r8, aFailedDToCreat; "Failed (%d) to create non-volatile regk"...
0x1800909db  mov     rdx, rdi; struct _GUID *
0x1800909de  mov     rcx, rbx; char *
0x1800909e1  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x1800909e6  mov     r8d, 27h ; '''; cchMax
0x1800909ec  lea     rdx, [rbp+8D0h+var_90]; lpsz
0x1800909f3  mov     rcx, r15; rguid
0x1800909f6  call    cs:__imp_StringFromGUID2
0x1800909fc  lea     rdx, aDeviceservices; "\\DeviceServices\\"
0x180090a03  lea     rcx, [rsp+9D0h+var_960]
0x180090a08  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180090a0d  lea     rdx, [rbp+8D0h+var_90]
0x180090a14  lea     rcx, [rsp+9D0h+var_960]
0x180090a19  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180090a1e  mov     [rsp+9D0h+var_990], esi
0x180090a22  mov     [rsp+9D0h+hKey], rsi
0x180090a27  lea     rcx, [rsp+9D0h+var_960]
0x180090a2c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180090a31  mov     rdx, rax
0x180090a34  lea     rax, [rsp+9D0h+var_990]
0x180090a39  mov     [rsp+9D0h+var_9A0], rax
0x180090a3e  lea     rax, [rsp+9D0h+hKey]
0x180090a43  mov     qword ptr [rsp+9D0h+cbData], rax
0x180090a48  mov     [rsp+9D0h+lpData], rsi
0x180090a4d  xor     ecx, ecx
0x180090a4f  mov     r9d, 0F003Fh
0x180090a55  lea     r8d, [rcx+1]
0x180090a59  call    cs:__imp_PersistentRegPathCreateKey
0x180090a5f  mov     rdx, rdi; struct _GUID *
0x180090a62  mov     rcx, rbx; char *
0x180090a65  test    eax, eax
0x180090a67  jnz     short loc_180090AC5
0x180090a69  cmp     [rsp+9D0h+var_990], 1
0x180090a6e  lea     rax, aPreExistedSoIs; "pre-existed, so is just opened"
0x180090a75  cmovnz  r12, rax
0x180090a79  mov     r9, r12
0x180090a7c  lea     r8, aSerializingDsN; "Serializing DS notification data to reg"...
0x180090a83  call    ?Info@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Info(char const *,_GUID const *,ushort const *,...)
0x180090a88  mov     [rsp+9D0h+cbData], r14d; cbData
0x180090a8d  mov     rax, [rsp+9D0h+var_978]
0x180090a92  mov     [rsp+9D0h+lpData], rax; lpData
0x180090a97  mov     r9d, 3; dwType
0x180090a9d  xor     r8d, r8d; Reserved
0x180090aa0  lea     rdx, aNotification; "Notification"
0x180090aa7  mov     rcx, [rsp+9D0h+hKey]; hKey
0x180090aac  call    cs:__imp_RegSetValueExW
0x180090ab2  test    eax, eax
0x180090ab4  jz      short loc_180090AD4
0x180090ab6  lea     r8, aFailedToSerial; "Failed to serialize DS notification dat"...
0x180090abd  mov     rdx, rdi
0x180090ac0  mov     rcx, rbx
0x180090ac3  jmp     short loc_180090ACC
0x180090ac5  lea     r8, aFailedToCreate_0; "Failed to create volatile regkey for ho"...
0x180090acc  mov     r9d, eax
0x180090acf  call    ?Error@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Error(char const *,_GUID const *,ushort const *,...)
0x180090ad4  lea     rcx, [rsp+9D0h+hKey]
0x180090ad9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180090ade  nop
0x180090adf  lea     rcx, [rsp+9D0h+var_980]
0x180090ae4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&RegCloseKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180090ae9  nop
0x180090aea  lea     rcx, [rsp+9D0h+var_960]
0x180090aef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090af4  nop
0x180090af5  lea     rcx, [rbp+8D0h+var_940]
0x180090af9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180090afe  jmp     short loc_180090B18
0x180090b00  mov     [rbp+8D0h+var_8EC], r14d
0x180090b04  test    r14d, r14d
0x180090b07  jz      short loc_180090B18
0x180090b09  mov     r8, r14; Size
0x180090b0c  mov     rdx, r12; Src
0x180090b0f  lea     rcx, [rbp+8D0h+var_8E8]; void *
0x180090b13  call    memcpy_0
0x180090b18  lea     r8, [rbp+8D0h+var_920]
0x180090b1c  mov     rcx, cs:WNF_SEB_MOBILE_BROADBAND_DEVICE_SERVICE_NOTIFICATION
0x180090b23  call    PubSebEdgeEventSyncInternal
0x180090b28  test    eax, eax
0x180090b2a  jns     short loc_180090B45
0x180090b2c  bts     eax, 1Ch
0x180090b30  mov     r9d, eax
0x180090b33  lea     r8, aFailedToPublis_1; "Failed to publish SEB event for device "...
0x180090b3a  xor     edx, edx; struct _GUID *
0x180090b3c  mov     rcx, rbx; char *
0x180090b3f  call    ?Warning@WwanLog@@SAXPEBDPEBU_GUID@@PEBGZZ; WwanLog::Warning(char const *,_GUID const *,ushort const *,...)
0x180090b44  nop
0x180090b45  mov     rcx, r13; lpCriticalSection
0x180090b48  call    cs:__imp_LeaveCriticalSection
0x180090b4e  mov     rcx, [rbp+8D0h+var_40]
0x180090b55  xor     rcx, rsp; StackCookie
0x180090b58  call    __security_check_cookie
0x180090b5d  mov     rbx, [rsp+9D0h+arg_0]
0x180090b65  add     rsp, 9A0h
0x180090b6c  pop     r15
0x180090b6e  pop     r14
0x180090b70  pop     r13
0x180090b72  pop     r12
0x180090b74  pop     rdi
0x180090b75  pop     rsi
0x180090b76  pop     rbp
0x180090b77  retn
```
