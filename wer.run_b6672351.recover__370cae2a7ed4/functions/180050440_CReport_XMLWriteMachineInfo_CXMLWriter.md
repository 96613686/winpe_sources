# CReport::XMLWriteMachineInfo(CXMLWriter *)

- ea: `0x180050440`
- end: `0x1800507d1`
- name: `?XMLWriteMachineInfo@CReport@@IEAAJPEAVCXMLWriter@@@Z`
- size: `913`
- prototype: `__int64 __fastcall(CReport *__hidden this, struct CXMLWriter *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077234`

## callees

- `0x180004c64`
- `0x18000a3ac`
- `0x18000cf50`
- `0x18000db80`
- `0x18000e31c`
- `0x180020680`
- `0x180043324`
- `0x180050440`
- `0x180053300`
- `0x180053d3c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800506b6`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x1800506b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800504b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800504b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005055e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005055e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505eb`
- `ntdll!RtlGetVersion` at `0x180050595`
- `ntdll!RtlGetVersion` at `0x180050595`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180050535`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800505c9`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180050535`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x1800505c9`

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
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, LastError);
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
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v5);
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
        236,
        WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids,
        (unsigned int)v10);
    }
  }
  else
  {
    v3 = -2147467259;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v23);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v21);
  return v3;
}

```

## disassembly

```asm
0x180050440  mov     [rsp-8+arg_0], rbx
0x180050445  mov     [rsp-8+arg_10], rdi
0x18005044a  push    rbp
0x18005044b  lea     rbp, [rsp-560h]
0x180050453  sub     rsp, 660h
0x18005045a  mov     rax, cs:__security_cookie
0x180050461  xor     rax, rsp
0x180050464  mov     [rbp+560h+var_10], rax
0x18005046b  lea     rcx, [rbp+560h+var_5E0]; void *
0x18005046f  mov     [rsp+660h+nSize], 200h
0x180050477  mov     rbx, rdx
0x18005047a  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18005047f  lea     rcx, [rbp+560h+var_5B0]; void *
0x180050483  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180050488  mov     edi, 11Ch
0x18005048d  lea     rcx, [rbp+560h+VersionInformation]; void *
0x180050491  mov     r8d, edi; Size
0x180050494  xor     edx, edx; Val
0x180050496  call    memset_0
0x18005049b  lea     r8, [rsp+660h+nSize]; nSize
0x1800504a0  mov     [rsp+660h+var_610], 0
0x1800504a8  lea     rdx, [rbp+560h+Buffer]; lpBuffer
0x1800504af  mov     ecx, 7; NameType
0x1800504b4  call    cs:__imp_GetComputerNameExW
0x1800504bb  nop     dword ptr [rax+rax+00h]
0x1800504c0  test    eax, eax
0x1800504c2  jnz     short loc_180050504
0x1800504c4  mov     ebx, 80004005h
0x1800504c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800504d0  lea     rdi, WPP_GLOBAL_Control
0x1800504d7  cmp     rcx, rdi
0x1800504da  jz      loc_180050798
0x1800504e0  test    byte ptr [rcx+1Ch], 1
0x1800504e4  jz      loc_180050798
0x1800504ea  mov     rcx, [rcx+10h]
0x1800504ee  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x1800504f5  mov     edx, 0E9h
0x1800504fa  call    WPP_SF_
0x1800504ff  jmp     loc_180050798
0x180050504  xor     r8d, r8d; __int64
0x180050507  lea     rcx, [rbp+560h+var_5E0]; __int64
0x18005050b  xor     edx, edx; __int64
0x18005050d  call    ?UtilGetManufacturerInformation@@YAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@00@Z; UtilGetManufacturerInformation(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180050512  movzx   r9d, [rbp+560h+var_47A]; dwSpMinorVersion
0x18005051a  lea     rax, [rsp+660h+var_610]
0x18005051f  movzx   r8d, [rbp+560h+var_47C]; dwSpMajorVersion
0x180050527  mov     edx, [rbp+560h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18005052a  mov     ecx, [rbp+560h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x18005052d  mov     [rsp+660h+pdwReturnedProductType], rax; pdwReturnedProductType
0x180050532  mov     [rbp+560h+VersionInformation.dwOSVersionInfoSize], edi
0x180050535  call    cs:__imp_GetProductInfo
0x18005053c  nop     dword ptr [rax+rax+00h]
0x180050541  lea     rdi, WPP_GLOBAL_Control
0x180050548  test    eax, eax
0x18005054a  jnz     short loc_180050591
0x18005054c  mov     rax, cs:WPP_GLOBAL_Control
0x180050553  cmp     rax, rdi
0x180050556  jz      short loc_180050589
0x180050558  test    byte ptr [rax+1Ch], 1
0x18005055c  jz      short loc_180050589
0x18005055e  call    cs:__imp_GetLastError
0x180050565  nop     dword ptr [rax+rax+00h]
0x18005056a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050571  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180050578  mov     edx, 0EAh
0x18005057d  mov     r9d, eax
0x180050580  mov     rcx, [rcx+10h]
0x180050584  call    WPP_SF_d
0x180050589  mov     [rsp+660h+var_610], 0
0x180050591  lea     rcx, [rbp+560h+VersionInformation]; lpVersionInformation
0x180050595  call    cs:__imp_RtlGetVersion
0x18005059c  nop     dword ptr [rax+rax+00h]
0x1800505a1  test    eax, eax
0x1800505a3  js      loc_180050671
0x1800505a9  movzx   r9d, [rbp+560h+var_47A]; dwSpMinorVersion
0x1800505b1  lea     rax, [rsp+660h+var_610]
0x1800505b6  movzx   r8d, [rbp+560h+var_47C]; dwSpMajorVersion
0x1800505be  mov     edx, [rbp+560h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x1800505c1  mov     ecx, [rbp+560h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x1800505c4  mov     [rsp+660h+pdwReturnedProductType], rax; pdwReturnedProductType
0x1800505c9  call    cs:__imp_GetProductInfo
0x1800505d0  nop     dword ptr [rax+rax+00h]
0x1800505d5  test    eax, eax
0x1800505d7  jnz     short loc_180050620
0x1800505d9  mov     rax, cs:WPP_GLOBAL_Control
0x1800505e0  cmp     rax, rdi
0x1800505e3  jz      short loc_180050616
0x1800505e5  test    byte ptr [rax+1Ch], 1
0x1800505e9  jz      short loc_180050616
0x1800505eb  call    cs:__imp_GetLastError
0x1800505f2  nop     dword ptr [rax+rax+00h]
0x1800505f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800505fe  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180050605  mov     edx, 0EBh
0x18005060a  mov     r9d, eax
0x18005060d  mov     rcx, [rcx+10h]
0x180050611  call    WPP_SF_d
0x180050616  xor     r8d, r8d
0x180050619  mov     [rsp+660h+var_610], r8d
0x18005061e  jmp     short loc_180050625
0x180050620  mov     r8d, [rsp+660h+var_610]
0x180050625  movzx   eax, [rbp+560h+var_478]
0x18005062c  movzx   ecx, [rbp+560h+var_47A]
0x180050633  movzx   edx, [rbp+560h+var_47C]
0x18005063a  mov     r9d, [rbp+560h+VersionInformation.dwMinorVersion]
0x18005063e  mov     [rsp+660h+var_618], r8d
0x180050643  mov     r8d, [rbp+560h+VersionInformation.dwMajorVersion]
0x180050647  mov     [rsp+660h+var_620], eax
0x18005064b  mov     eax, [rbp+560h+VersionInformation.dwPlatformId]
0x18005064e  mov     [rsp+660h+var_628], ecx
0x180050652  lea     rcx, [rbp+560h+var_5B0]
0x180050656  mov     [rsp+660h+var_630], edx
0x18005065a  lea     rdx, aUUUUUUUU; "%u.%u.%u.%u.%u.%u.%u.%u"
0x180050661  mov     [rsp+660h+var_638], eax
0x180050665  mov     eax, [rbp+560h+VersionInformation.dwBuildNumber]
0x180050668  mov     dword ptr [rsp+660h+pdwReturnedProductType], eax
0x18005066c  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180050671  xor     eax, eax
0x180050673  lea     rcx, aMachinename; "machinename"
0x18005067a  lea     rdx, [rbp+560h+Buffer]
0x180050681  mov     [rbp+560h+var_470], rcx
0x180050688  mov     rcx, [rbp+560h+var_5B0]
0x18005068c  mov     [rbp+560h+var_468], rdx
0x180050693  lea     rdx, aOs; "os"
0x18005069a  mov     [rbp+560h+var_458], rdx
0x1800506a1  mov     [rbp+560h+var_450], rcx
0x1800506a8  mov     [rbp+560h+var_460], rax
0x1800506af  mov     [rbp+560h+var_448], rax
0x1800506b6  call    cs:__imp_GetUserDefaultLCID
0x1800506bd  nop     dword ptr [rax+rax+00h]
0x1800506c2  lea     rcx, aLcid_0; "lcid"
0x1800506c9  mov     [rbp+560h+var_438], 0
0x1800506d4  mov     [rbp+560h+var_440], rcx
0x1800506db  mov     rcx, [rbp+560h+var_5E0]
0x1800506df  mov     eax, eax
0x1800506e1  mov     [rbp+560h+var_430], rax
0x1800506e8  cmp     rcx, [rbp+560h+var_5D8]
0x1800506ec  jnz     short loc_1800506F5
0x1800506ee  mov     eax, 3
0x1800506f3  jmp     short loc_180050718
0x1800506f5  xor     eax, eax
0x1800506f7  mov     [rbp+560h+var_420], rcx
0x1800506fe  lea     rdx, aOem; "oem"
0x180050705  mov     [rbp+560h+var_418], rax
0x18005070c  mov     eax, 4
0x180050711  mov     [rbp+560h+var_428], rdx
0x180050718  mov     [rsp+660h+var_5F8], rax
0x18005071d  lea     rcx, [rbp+560h+var_470]
0x180050724  lea     rax, aMachineinfo; "MACHINEINFO"
0x18005072b  mov     [rsp+660h+var_600], rcx
0x180050730  mov     [rsp+660h+var_5F0], rax
0x180050735  lea     r8, [rbp+560h+var_5C0]
0x180050739  lea     rax, [rsp+660h+var_600]
0x18005073e  mov     [rsp+660h+var_5E8], 0Bh
0x180050747  xorps   xmm0, xmm0
0x18005074a  mov     [rsp+660h+pdwReturnedProductType], rax
0x18005074f  mov     r9b, 1
0x180050752  movdqa  [rbp+560h+var_5C0], xmm0
0x180050757  lea     rdx, [rsp+660h+var_5F0]
0x18005075c  mov     rcx, rbx
0x18005075f  call    ?BeginElement@CXMLWriter@@QEAAJV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@0_NV?$span@$$CBUCXMLAttribute@@$0?0@3@@Z; CXMLWriter::BeginElement(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool,utl::span<CXMLAttribute const,-1>)
0x180050764  mov     ebx, eax
0x180050766  test    eax, eax
0x180050768  jns     short loc_180050796
0x18005076a  mov     rcx, cs:WPP_GLOBAL_Control
0x180050771  cmp     rcx, rdi
0x180050774  jz      short loc_180050798
0x180050776  test    byte ptr [rcx+1Ch], 1
0x18005077a  jz      short loc_180050798
0x18005077c  mov     rcx, [rcx+10h]
0x180050780  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180050787  mov     edx, 0ECh
0x18005078c  mov     r9d, eax
0x18005078f  call    WPP_SF_d
0x180050794  jmp     short loc_180050798
0x180050796  xor     ebx, ebx
0x180050798  lea     rcx, [rbp+560h+var_5B0]; void *
0x18005079c  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800507a1  lea     rcx, [rbp+560h+var_5E0]; void *
0x1800507a5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800507aa  mov     eax, ebx
0x1800507ac  mov     rcx, [rbp+560h+var_10]
0x1800507b3  xor     rcx, rsp; StackCookie
0x1800507b6  call    __security_check_cookie
0x1800507bb  lea     r11, [rsp+660h+var_s0]
0x1800507c3  mov     rbx, [r11+10h]
0x1800507c7  mov     rdi, [r11+20h]
0x1800507cb  mov     rsp, r11
0x1800507ce  pop     rbp
0x1800507cf  retn
```
