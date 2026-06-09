# CReport::XMLWriteMachineInfo(CXMLWriter *)

- ea: `0x18004e0c4`
- end: `0x18004e42a`
- name: `?XMLWriteMachineInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z`
- size: `870`
- prototype: `__int64 __fastcall(CReport *__hidden this, struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073de8`

## callees

- `0x180004bb4`
- `0x180009298`
- `0x18000bc10`
- `0x18000cc74`
- `0x18000dad0`
- `0x18001fe24`
- `0x18004144c`
- `0x18004e0c4`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18004e316`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x18004e316`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004e138`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x18004e138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e251`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e1d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e251`
- `ntdll!RtlGetVersion` at `0x18004e207`
- `ntdll!RtlGetVersion` at `0x18004e207`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18004e1b3`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18004e235`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18004e1b3`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x18004e235`

## pseudocode

```c
__int64 __fastcall CReport::XMLWriteMachineInfo(CReport *this, struct CXMLWriter *a2)
{
  int v2; // ebx
  unsigned int v3; // ebx
  DWORD LastError; // eax
  DWORD v5; // eax
  DWORD v6; // r8d
  LCID UserDefaultLCID; // eax
  int v8; // r9d
  __int64 v9; // rax
  int v10; // eax
  PDWORD pdwReturnedProductType; // [rsp+20h] [rbp-E0h]
  DWORD dwPlatformId; // [rsp+28h] [rbp-D8h]
  int v14; // [rsp+30h] [rbp-D0h]
  int v15; // [rsp+38h] [rbp-C8h]
  int v16; // [rsp+40h] [rbp-C0h]
  DWORD v17; // [rsp+48h] [rbp-B8h]
  DWORD v18[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v19[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v20[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v21[4]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v22; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v23[4]; // [rsp+B0h] [rbp-50h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int16 v25; // [rsp+1E4h] [rbp+E4h]
  unsigned __int16 v26; // [rsp+1E6h] [rbp+E6h]
  unsigned __int16 v27; // [rsp+1E8h] [rbp+E8h]
  _QWORD v28[12]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR Buffer[512]; // [rsp+250h] [rbp+150h] BYREF

  v18[1] = 512;
  v2 = (int)a2;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v21);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v23);
  memset_0(&VersionInformation, 0, 0x11Cu);
  v18[0] = 0;
  if ( GetComputerNameExW(ComputerNamePhysicalDnsFullyQualified, Buffer, &v18[1]) )
  {
    UtilGetManufacturerInformation((__int64)v21, 0, 0);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v25, v26, v18) )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, LastError);
      }
      v18[0] = 0;
    }
    if ( RtlGetVersion(&VersionInformation) >= 0 )
    {
      if ( GetProductInfo(VersionInformation.dwMajorVersion, VersionInformation.dwMinorVersion, v25, v26, v18) )
      {
        v6 = v18[0];
      }
      else
      {
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        {
          v5 = GetLastError();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_6898268820d636d20e115db2eaa75970_Traceguids, v5);
        }
        v6 = 0;
        v18[0] = 0;
      }
      v17 = v6;
      v16 = v27;
      v15 = v26;
      v14 = v25;
      dwPlatformId = VersionInformation.dwPlatformId;
      LODWORD(pdwReturnedProductType) = VersionInformation.dwBuildNumber;
      tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
        v23,
        L"%u.%u.%u.%u.%u.%u.%u.%u",
        VersionInformation.dwMajorVersion,
        VersionInformation.dwMinorVersion,
        pdwReturnedProductType,
        dwPlatformId,
        v14,
        v15,
        v16,
        v17,
        *(_QWORD *)v18);
    }
    v28[0] = L"machinename";
    v28[1] = Buffer;
    v28[3] = L"os";
    v28[4] = v23[0];
    v28[2] = 0;
    v28[5] = 0;
    UserDefaultLCID = GetUserDefaultLCID();
    v28[7] = 0;
    v28[6] = L"lcid";
    v28[8] = UserDefaultLCID;
    if ( v21[0] == v21[1] )
    {
      v9 = 3;
    }
    else
    {
      v28[10] = v21[0];
      v28[11] = 0;
      v9 = 4;
      v28[9] = L"oem";
    }
    v19[1] = v9;
    v19[0] = v28;
    v20[0] = L"MACHINEINFO";
    v20[1] = 11;
    LOBYTE(v8) = 1;
    v22 = 0;
    v10 = CXMLWriter::BeginElement(v2, (unsigned int)v20, (unsigned int)&v22, v8, (__int64)v19);
    v3 = v10;
    if ( v10 >= 0 )
    {
      v3 = 0;
    }
    else if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        235,
        &WPP_6898268820d636d20e115db2eaa75970_Traceguids,
        (unsigned int)v10);
    }
  }
  else
  {
    v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 232, &WPP_6898268820d636d20e115db2eaa75970_Traceguids);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
  return v3;
}

```

## disassembly

```asm
0x18004e0c4  mov     [rsp-8+arg_0], rbx
0x18004e0c9  mov     [rsp-8+arg_10], rdi
0x18004e0ce  push    rbp
0x18004e0cf  lea     rbp, [rsp-560h]
0x18004e0d7  sub     rsp, 660h
0x18004e0de  mov     rax, cs:__security_cookie
0x18004e0e5  xor     rax, rsp
0x18004e0e8  mov     [rbp+560h+var_10], rax
0x18004e0ef  lea     rcx, [rbp+560h+var_5E0]; void *
0x18004e0f3  mov     [rsp+660h+nSize], 200h
0x18004e0fb  mov     rbx, rdx
0x18004e0fe  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18004e103  lea     rcx, [rbp+560h+var_5B0]; void *
0x18004e107  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18004e10c  mov     edi, 11Ch
0x18004e111  lea     rcx, [rbp+560h+VersionInformation]; void *
0x18004e115  mov     r8d, edi; Size
0x18004e118  xor     edx, edx; Val
0x18004e11a  call    memset_0
0x18004e11f  lea     r8, [rsp+660h+nSize]; nSize
0x18004e124  mov     [rsp+660h+var_610], 0
0x18004e12c  lea     rdx, [rbp+560h+Buffer]; lpBuffer
0x18004e133  mov     ecx, 7; NameType
0x18004e138  call    cs:__imp_GetComputerNameExW
0x18004e13e  test    eax, eax
0x18004e140  jnz     short loc_18004E182
0x18004e142  mov     ebx, 80004005h
0x18004e147  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e14e  lea     rdi, WPP_GLOBAL_Control
0x18004e155  cmp     rcx, rdi
0x18004e158  jz      loc_18004E3F2
0x18004e15e  test    byte ptr [rcx+1Ch], 1
0x18004e162  jz      loc_18004E3F2
0x18004e168  mov     rcx, [rcx+10h]
0x18004e16c  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004e173  mov     edx, 0E8h
0x18004e178  call    WPP_SF_
0x18004e17d  jmp     loc_18004E3F2
0x18004e182  xor     r8d, r8d; __int64
0x18004e185  lea     rcx, [rbp+560h+var_5E0]; __int64
0x18004e189  xor     edx, edx; __int64
0x18004e18b  call    ?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z; UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18004e190  movzx   r9d, [rbp+560h+var_47A]; dwSpMinorVersion
0x18004e198  lea     rax, [rsp+660h+var_610]
0x18004e19d  movzx   r8d, [rbp+560h+var_47C]; dwSpMajorVersion
0x18004e1a5  mov     edx, [rbp+560h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18004e1a8  mov     ecx, [rbp+560h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18004e1ab  mov     [rsp+660h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18004e1b0  mov     [rbp+560h+VersionInformation.dwOSVersionInfoSize], edi
0x18004e1b3  call    cs:__imp_GetProductInfo
0x18004e1b9  lea     rdi, WPP_GLOBAL_Control
0x18004e1c0  test    eax, eax
0x18004e1c2  jnz     short loc_18004E203
0x18004e1c4  mov     rax, cs:WPP_GLOBAL_Control
0x18004e1cb  cmp     rax, rdi
0x18004e1ce  jz      short loc_18004E1FB
0x18004e1d0  test    byte ptr [rax+1Ch], 1
0x18004e1d4  jz      short loc_18004E1FB
0x18004e1d6  call    cs:__imp_GetLastError
0x18004e1dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e1e3  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004e1ea  mov     edx, 0E9h
0x18004e1ef  mov     r9d, eax
0x18004e1f2  mov     rcx, [rcx+10h]
0x18004e1f6  call    WPP_SF_d
0x18004e1fb  mov     [rsp+660h+var_610], 0
0x18004e203  lea     rcx, [rbp+560h+VersionInformation]; lpVersionInformation
0x18004e207  call    cs:__imp_RtlGetVersion
0x18004e20d  test    eax, eax
0x18004e20f  js      loc_18004E2D1
0x18004e215  movzx   r9d, [rbp+560h+var_47A]; dwSpMinorVersion
0x18004e21d  lea     rax, [rsp+660h+var_610]
0x18004e222  movzx   r8d, [rbp+560h+var_47C]; dwSpMajorVersion
0x18004e22a  mov     edx, [rbp+560h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18004e22d  mov     ecx, [rbp+560h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18004e230  mov     [rsp+660h+pdwReturnedProductType], rax; pdwReturnedProductType
0x18004e235  call    cs:__imp_GetProductInfo
0x18004e23b  test    eax, eax
0x18004e23d  jnz     short loc_18004E280
0x18004e23f  mov     rax, cs:WPP_GLOBAL_Control
0x18004e246  cmp     rax, rdi
0x18004e249  jz      short loc_18004E276
0x18004e24b  test    byte ptr [rax+1Ch], 1
0x18004e24f  jz      short loc_18004E276
0x18004e251  call    cs:__imp_GetLastError
0x18004e257  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e25e  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004e265  mov     edx, 0EAh
0x18004e26a  mov     r9d, eax
0x18004e26d  mov     rcx, [rcx+10h]
0x18004e271  call    WPP_SF_d
0x18004e276  xor     r8d, r8d
0x18004e279  mov     [rsp+660h+var_610], r8d
0x18004e27e  jmp     short loc_18004E285
0x18004e280  mov     r8d, [rsp+660h+var_610]
0x18004e285  movzx   eax, [rbp+560h+var_478]
0x18004e28c  movzx   ecx, [rbp+560h+var_47A]
0x18004e293  movzx   edx, [rbp+560h+var_47C]
0x18004e29a  mov     r9d, [rbp+560h+VersionInformation.dwMinorVersion]
0x18004e29e  mov     [rsp+660h+var_618], r8d
0x18004e2a3  mov     r8d, [rbp+560h+VersionInformation.dwMajorVersion]
0x18004e2a7  mov     [rsp+660h+var_620], eax
0x18004e2ab  mov     eax, [rbp+560h+VersionInformation.dwPlatformId]
0x18004e2ae  mov     [rsp+660h+var_628], ecx
0x18004e2b2  lea     rcx, [rbp+560h+var_5B0]
0x18004e2b6  mov     [rsp+660h+var_630], edx
0x18004e2ba  lea     rdx, aUUUUUUUU; "%u.%u.%u.%u.%u.%u.%u.%u"
0x18004e2c1  mov     [rsp+660h+var_638], eax
0x18004e2c5  mov     eax, [rbp+560h+VersionInformation.dwBuildNumber]
0x18004e2c8  mov     dword ptr [rsp+660h+pdwReturnedProductType], eax
0x18004e2cc  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x18004e2d1  xor     eax, eax
0x18004e2d3  lea     rcx, aMachinename; "machinename"
0x18004e2da  lea     rdx, [rbp+560h+Buffer]
0x18004e2e1  mov     [rbp+560h+var_470], rcx
0x18004e2e8  mov     rcx, [rbp+560h+var_5B0]
0x18004e2ec  mov     [rbp+560h+var_468], rdx
0x18004e2f3  lea     rdx, aOs; "os"
0x18004e2fa  mov     [rbp+560h+var_458], rdx
0x18004e301  mov     [rbp+560h+var_450], rcx
0x18004e308  mov     [rbp+560h+var_460], rax
0x18004e30f  mov     [rbp+560h+var_448], rax
0x18004e316  call    cs:__imp_GetUserDefaultLCID
0x18004e31c  lea     rcx, aLcid_0; "lcid"
0x18004e323  mov     [rbp+560h+var_438], 0
0x18004e32e  mov     [rbp+560h+var_440], rcx
0x18004e335  mov     rcx, [rbp+560h+var_5E0]
0x18004e339  mov     eax, eax
0x18004e33b  mov     [rbp+560h+var_430], rax
0x18004e342  cmp     rcx, [rbp+560h+var_5D8]
0x18004e346  jnz     short loc_18004E34F
0x18004e348  mov     eax, 3
0x18004e34d  jmp     short loc_18004E372
0x18004e34f  xor     eax, eax
0x18004e351  mov     [rbp+560h+var_420], rcx
0x18004e358  lea     rdx, aOem; "oem"
0x18004e35f  mov     [rbp+560h+var_418], rax
0x18004e366  mov     eax, 4
0x18004e36b  mov     [rbp+560h+var_428], rdx
0x18004e372  mov     [rsp+660h+var_5F8], rax
0x18004e377  lea     rcx, [rbp+560h+var_470]
0x18004e37e  lea     rax, aMachineinfo; "MACHINEINFO"
0x18004e385  mov     [rsp+660h+var_600], rcx
0x18004e38a  mov     [rsp+660h+var_5F0], rax
0x18004e38f  lea     r8, [rbp+560h+var_5C0]
0x18004e393  lea     rax, [rsp+660h+var_600]
0x18004e398  mov     [rsp+660h+var_5E8], 0Bh
0x18004e3a1  xorps   xmm0, xmm0
0x18004e3a4  mov     [rsp+660h+pdwReturnedProductType], rax
0x18004e3a9  mov     r9b, 1
0x18004e3ac  movdqa  [rbp+560h+var_5C0], xmm0
0x18004e3b1  lea     rdx, [rsp+660h+var_5F0]
0x18004e3b6  mov     rcx, rbx
0x18004e3b9  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x18004e3be  mov     ebx, eax
0x18004e3c0  test    eax, eax
0x18004e3c2  jns     short loc_18004E3F0
0x18004e3c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18004e3cb  cmp     rcx, rdi
0x18004e3ce  jz      short loc_18004E3F2
0x18004e3d0  test    byte ptr [rcx+1Ch], 1
0x18004e3d4  jz      short loc_18004E3F2
0x18004e3d6  mov     rcx, [rcx+10h]
0x18004e3da  lea     r8, WPP_6898268820d636d20e115db2eaa75970_Traceguids
0x18004e3e1  mov     edx, 0EBh
0x18004e3e6  mov     r9d, eax
0x18004e3e9  call    WPP_SF_d
0x18004e3ee  jmp     short loc_18004E3F2
0x18004e3f0  xor     ebx, ebx
0x18004e3f2  lea     rcx, [rbp+560h+var_5B0]; void *
0x18004e3f6  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18004e3fb  lea     rcx, [rbp+560h+var_5E0]; void *
0x18004e3ff  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18004e404  mov     eax, ebx
0x18004e406  mov     rcx, [rbp+560h+var_10]
0x18004e40d  xor     rcx, rsp; StackCookie
0x18004e410  call    __security_check_cookie
0x18004e415  lea     r11, [rsp+660h+var_s0]
0x18004e41d  mov     rbx, [r11+10h]
0x18004e421  mov     rdi, [r11+20h]
0x18004e425  mov     rsp, r11
0x18004e428  pop     rbp
0x18004e429  retn
```
