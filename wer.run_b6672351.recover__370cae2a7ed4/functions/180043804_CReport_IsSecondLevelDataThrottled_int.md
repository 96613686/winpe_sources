# CReport::IsSecondLevelDataThrottled(int)

- ea: `0x180043804`
- end: `0x180043e95`
- name: `?IsSecondLevelDataThrottled@CReport@@QEAAHH@Z`
- size: `1681`
- prototype: `__int64 __fastcall(CReport *__hidden this, int)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800180d8`
- `0x18001f718`

## callees

- `0x180004c64`
- `0x180009b50`
- `0x18000a6c0`
- `0x18000ad98`
- `0x18000cf50`
- `0x18000da00`
- `0x18000db80`
- `0x18000e31c`
- `0x18001fcf4`
- `0x18001fd1c`
- `0x18001fe88`
- `0x180020680`
- `0x18002219c`
- `0x180030de4`
- `0x18003efe0`
- `0x180040d84`
- `0x180043804`
- `0x180043e9c`
- `0x180053300`
- `0x180075254`
- `0x180079eec`
- `0x1800af010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043b1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180043b1a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043c29`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043d59`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043c29`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180043d59`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CReport::IsSecondLevelDataThrottled(CReport *this, int a2)
{
  unsigned int v4; // esi
  wchar_t *v5; // rax
  int v6; // r8d
  wchar_t *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  int v11; // r12d
  int v12; // r13d
  int v13; // r14d
  int SignatureParamsHash; // eax
  unsigned int i; // ecx
  unsigned int v16; // r14d
  __int64 v17; // rax
  __int64 v18; // rdx
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  FILETIME FileTime1; // [rsp+40h] [rbp-C0h] BYREF
  int v23; // [rsp+48h] [rbp-B8h]
  wchar_t *v24[4]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v25[4]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v26[4]; // [rsp+90h] [rbp-70h] BYREF
  wchar_t *v27[4]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t *v28[4]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v29[4]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v30[5200]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v31[650]; // [rsp+1560h] [rbp+1460h] BYREF

  CReportArchive::CReportArchive((CReportArchive *)v31);
  CReportQueue::CReportQueue((CReportQueue *)v30);
  v4 = 0;
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v29);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v28);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v27);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v24);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v26);
  utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(v25);
  FileTime1 = 0;
  SystemTimeAsFileTime = 0;
  v20 = 0;
  if ( !*((_DWORD *)this + 11670) )
  {
    if ( (*((_DWORD *)this + 1654) & 0x800) != 0
      || (v11 = *((_DWORD *)this + 2277),
          v12 = *((_DWORD *)this + 2276),
          v23 = *((_DWORD *)this + 2275),
          v13 = *((_DWORD *)this + 2274),
          CRegSetting::GetDwordData((CReport *)((char *)this + 48768)) == 1)
      || CRegSetting::GetDwordData((CReport *)((char *)this + 48872)) == 1 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_84;
      v10 = 309;
      goto LABEL_82;
    }
    SignatureParamsHash = CReport::GetSignatureParamsHash(this, v29);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 310;
LABEL_20:
      v9 = (unsigned int)SignatureParamsHash;
      goto LABEL_7;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v25,
                             L"Report") )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 311;
      goto LABEL_6;
    }
    for ( i = 0; i < 6; ++i )
    {
      if ( LODWORD(qword_1800B50D0[2 * i]) == *((_DWORD *)this + 1468) )
      {
        utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
          v25,
          (void *)qword_1800B50D0[2 * i + 1]);
        break;
      }
    }
    SignatureParamsHash = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v28,
                            L"%s_*_%s_*_cab_*",
                            v25[0],
                            v29[0]);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 312;
      goto LABEL_20;
    }
    v16 = v11 ^ v12 ^ v23 ^ v13;
    SignatureParamsHash = tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(
                            v27,
                            L"*_*_*_%08x_cab_*",
                            v16);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 313;
      goto LABEL_20;
    }
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v17 = *(_QWORD *)&SystemTimeAsFileTime - 864000000000LL;
    SystemTimeAsFileTime.dwLowDateTime -= 711573504;
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v17);
    UtilIsCurrentProcessInteractive();
    SignatureParamsHash = CReportArchive::InitMachineStore((CReportArchive *)v31);
    if ( SignatureParamsHash < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
        goto LABEL_87;
      if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
        goto LABEL_84;
      v8 = 314;
      goto LABEL_20;
    }
    if ( (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v31, v28[0]) < 0 )
    {
      if ( a2
        && v16
        && (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v31, v27[0]) >= 0
        && CReportStore::GetReportCreationDate((CReportStore *)v31, v24[0], &FileTime1) >= 0
        && CompareFileTime(&FileTime1, &SystemTimeAsFileTime) > 0 )
      {
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          goto LABEL_47;
        v18 = 316;
      }
      else
      {
        SignatureParamsHash = CReportQueue::InitMachineStore((CReportQueue *)v30);
        if ( SignatureParamsHash < 0 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
            goto LABEL_87;
          if ( (WPP_GLOBAL_Control[14] & 1) == 0 )
            goto LABEL_84;
          v8 = 317;
          goto LABEL_20;
        }
        if ( (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v30, v28[0]) >= 0
          && (int)CReportStore::HasReportFile((CReportStore *)v30, v24[0], &v20) >= 0
          && v20 )
        {
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
            goto LABEL_47;
          v18 = 318;
        }
        else
        {
          if ( !a2
            || !v16
            || (int)CReportStore::EnumerateStoreNextKeyWithPattern((CReportStore *)v30, v27[0]) < 0
            || (int)CReportStore::HasReportFile((CReportStore *)v30, v24[0], &v20) < 0
            || !v20
            || CReportStore::GetReportCreationDate((CReportStore *)v30, v24[0], &FileTime1) < 0
            || CompareFileTime(&FileTime1, &SystemTimeAsFileTime) <= 0 )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
              goto LABEL_87;
            if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
              goto LABEL_84;
            v10 = 320;
            goto LABEL_82;
          }
          v7 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
          {
LABEL_47:
            v4 = 1;
            goto LABEL_84;
          }
          v18 = 319;
        }
      }
    }
    else
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 4) == 0 )
        goto LABEL_47;
      v18 = 315;
    }
    WPP_SF_(*((_QWORD *)v7 + 2), v18, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    v7 = WPP_GLOBAL_Control;
    goto LABEL_47;
  }
  v5 = (wchar_t *)UtilPathTail(*((const wchar_t **)this + 5802));
  if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v26, v5) )
  {
    if ( utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(
           v26[0],
           (__int64)(v26[1] - v26[0]) >> 1,
           v6,
           (unsigned int)L"_cab_",
           5) != -1 )
    {
      v4 = 0;
      goto LABEL_83;
    }
    v4 = 1;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
      goto LABEL_87;
    if ( (WPP_GLOBAL_Control[14] & 4) == 0 )
      goto LABEL_84;
    v10 = 308;
LABEL_82:
    WPP_SF_(*((_QWORD *)v7 + 2), v10, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids);
    goto LABEL_83;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control )
    goto LABEL_87;
  if ( (WPP_GLOBAL_Control[14] & 1) != 0 )
  {
    v8 = 307;
LABEL_6:
    v9 = 2147942414LL;
LABEL_7:
    WPP_SF_d(*((_QWORD *)v7 + 2), v8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v9);
LABEL_83:
    v7 = WPP_GLOBAL_Control;
  }
LABEL_84:
  if ( v7 != (wchar_t *)&WPP_GLOBAL_Control && (v7[14] & 4) != 0 )
    WPP_SF_d(*((_QWORD *)v7 + 2), 321, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids, v4);
LABEL_87:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v25);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v26);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v24);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v27);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v28);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v29);
  CReportStore::~CReportStore((CReportStore *)v30);
  v31[0] = &CReportArchive::`vftable';
  CReportStore::~CReportStore((CReportStore *)v31);
  return v4;
}

```

## disassembly

```asm
0x180043804  push    rbp
0x180043806  push    rbx
0x180043807  push    rsi
0x180043808  push    rdi
0x180043809  push    r12
0x18004380b  push    r13
0x18004380d  push    r14
0x18004380f  push    r15
0x180043811  lea     rbp, [rsp-28C8h]
0x180043819  mov     eax, 29C8h
0x18004381e  call    _alloca_probe
0x180043823  sub     rsp, rax
0x180043826  mov     rax, cs:__security_cookie
0x18004382d  xor     rax, rsp
0x180043830  mov     [rbp+2900h+var_50], rax
0x180043837  mov     r15d, edx
0x18004383a  mov     rdi, rcx
0x18004383d  lea     rcx, [rbp+2900h+var_14A0]; this
0x180043844  call    ??0CReportArchive@@QEAA@XZ; CReportArchive::CReportArchive(void)
0x180043849  nop
0x18004384a  lea     rcx, [rbp+2900h+var_28F0]; this
0x18004384e  call    ??0CReportQueue@@QEAA@XZ; CReportQueue::CReportQueue(void)
0x180043853  nop
0x180043854  xor     ebx, ebx
0x180043856  mov     esi, ebx
0x180043858  lea     rcx, [rbp+2900h+var_2910]; void *
0x18004385c  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180043861  nop
0x180043862  lea     rcx, [rbp+2900h+var_2930]; void *
0x180043866  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18004386b  nop
0x18004386c  lea     rcx, [rbp+2900h+var_2950]; void *
0x180043870  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180043875  nop
0x180043876  lea     rcx, [rsp+2A00h+var_29B0]; void *
0x18004387b  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180043880  nop
0x180043881  lea     rcx, [rbp+2900h+var_2970]; void *
0x180043885  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x18004388a  nop
0x18004388b  lea     rcx, [rsp+2A00h+var_2990]; void *
0x180043890  call    ??0?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA@XZ; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(void)
0x180043895  nop
0x180043896  mov     qword ptr [rsp+2A00h+FileTime1.dwLowDateTime], rbx
0x18004389b  mov     qword ptr [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime], rbx
0x1800438a0  mov     [rsp+2A00h+var_29D0], ebx
0x1800438a4  cmp     [rdi+0B658h], ebx
0x1800438aa  jz      loc_180043978
0x1800438b0  mov     rcx, [rdi+0B550h]; wchar_t *
0x1800438b7  call    ?UtilPathTail@@YAPEB_WPEB_W@Z; UtilPathTail(wchar_t const *)
0x1800438bc  mov     rdx, rax
0x1800438bf  lea     rcx, [rbp+2900h+var_2970]
0x1800438c3  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x1800438c8  test    al, al
0x1800438ca  jnz     short loc_180043911
0x1800438cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800438d3  lea     rdi, WPP_GLOBAL_Control
0x1800438da  cmp     rcx, rdi
0x1800438dd  jz      loc_180043E0D
0x1800438e3  mov     ebx, 1
0x1800438e8  test    [rcx+1Ch], bl
0x1800438eb  jz      loc_180043DE9
0x1800438f1  mov     edx, 133h
0x1800438f6  mov     r9d, 8007000Eh
0x1800438fc  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180043903  mov     rcx, [rcx+10h]
0x180043907  call    WPP_SF_d
0x18004390c  jmp     loc_180043DE2
0x180043911  mov     rcx, [rbp+2900h+var_2970]
0x180043915  mov     rdx, [rbp+2900h+var_2968]
0x180043919  sub     rdx, rcx
0x18004391c  sar     rdx, 1
0x18004391f  mov     [rsp+2A00h+var_29E0], 5
0x180043928  lea     r9, aCab; "_cab_"
0x18004392f  call    ?find@?$_StringTraits@U?$transform_traits@_WUascii_toupper_transform@tlx@@@tlx@@@utl@@SA_KPEB_W_K101@Z; utl::_StringTraits<tlx::transform_traits<wchar_t,tlx::ascii_toupper_transform>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180043934  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180043938  jz      short loc_180043948
0x18004393a  mov     esi, ebx
0x18004393c  lea     rdi, WPP_GLOBAL_Control
0x180043943  jmp     loc_180043DE2
0x180043948  mov     esi, 1
0x18004394d  mov     rcx, cs:WPP_GLOBAL_Control
0x180043954  lea     rdi, WPP_GLOBAL_Control
0x18004395b  cmp     rcx, rdi
0x18004395e  jz      loc_180043E0D
0x180043964  test    byte ptr [rcx+1Ch], 4
0x180043968  jz      loc_180043DE9
0x18004396e  mov     edx, 134h
0x180043973  jmp     loc_180043DD2
0x180043978  test    dword ptr [rdi+19D8h], 800h
0x180043982  jnz     loc_180043DB4
0x180043988  mov     r12d, [rdi+2394h]
0x18004398f  mov     r13d, [rdi+2390h]
0x180043996  mov     eax, [rdi+238Ch]
0x18004399c  mov     [rsp+2A00h+var_29B8], eax
0x1800439a0  mov     r14d, [rdi+2388h]
0x1800439a7  lea     rcx, [rdi+0BE80h]; this
0x1800439ae  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x1800439b3  mov     ebx, 1
0x1800439b8  cmp     eax, ebx
0x1800439ba  jz      loc_180043DB4
0x1800439c0  lea     rcx, [rdi+0BEE8h]; this
0x1800439c7  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x1800439cc  cmp     eax, ebx
0x1800439ce  jz      loc_180043DB4
0x1800439d4  lea     rdx, [rbp+2900h+var_2910]
0x1800439d8  mov     rcx, rdi
0x1800439db  call    ?GetSignatureParamsHash@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetSignatureParamsHash(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800439e0  test    eax, eax
0x1800439e2  jns     short loc_180043A11
0x1800439e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800439eb  lea     rdi, WPP_GLOBAL_Control
0x1800439f2  cmp     rcx, rdi
0x1800439f5  jz      loc_180043E0D
0x1800439fb  test    [rcx+1Ch], bl
0x1800439fe  jz      loc_180043DE9
0x180043a04  mov     edx, 136h
0x180043a09  mov     r9d, eax
0x180043a0c  jmp     loc_1800438FC
0x180043a11  lea     rdx, aReport; "Report"
0x180043a18  lea     rcx, [rsp+2A00h+var_2990]
0x180043a1d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180043a22  test    al, al
0x180043a24  jnz     short loc_180043A50
0x180043a26  mov     rcx, cs:WPP_GLOBAL_Control
0x180043a2d  lea     rdi, WPP_GLOBAL_Control
0x180043a34  cmp     rcx, rdi
0x180043a37  jz      loc_180043E0D
0x180043a3d  test    [rcx+1Ch], bl
0x180043a40  jz      loc_180043DE9
0x180043a46  mov     edx, 137h
0x180043a4b  jmp     loc_1800438F6
0x180043a50  xor     ecx, ecx
0x180043a52  lea     r8, qword_1800B50D0
0x180043a59  cmp     ecx, 6
0x180043a5c  jnb     short loc_180043A82
0x180043a5e  mov     edx, ecx
0x180043a60  add     rdx, rdx
0x180043a63  mov     eax, [rdi+16F0h]
0x180043a69  cmp     [r8+rdx*8], eax
0x180043a6d  jz      short loc_180043A73
0x180043a6f  add     ecx, ebx
0x180043a71  jmp     short loc_180043A59
0x180043a73  mov     rdx, [r8+rdx*8+8]
0x180043a78  lea     rcx, [rsp+2A00h+var_2990]
0x180043a7d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180043a82  mov     r9, [rbp+2900h+var_2910]
0x180043a86  mov     r8, [rsp+2A00h+var_2990]
0x180043a8b  lea     rdx, aSSCab; "%s_*_%s_*_cab_*"
0x180043a92  lea     rcx, [rbp+2900h+var_2930]
0x180043a96  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180043a9b  test    eax, eax
0x180043a9d  jns     short loc_180043AC9
0x180043a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180043aa6  lea     rdi, WPP_GLOBAL_Control
0x180043aad  cmp     rcx, rdi
0x180043ab0  jz      loc_180043E0D
0x180043ab6  test    [rcx+1Ch], bl
0x180043ab9  jz      loc_180043DE9
0x180043abf  mov     edx, 138h
0x180043ac4  jmp     loc_180043A09
0x180043ac9  xor     r14d, [rsp+2A00h+var_29B8]
0x180043ace  xor     r14d, r13d
0x180043ad1  xor     r14d, r12d
0x180043ad4  mov     r8d, r14d
0x180043ad7  lea     rdx, a08xCab; "*_*_*_%08x_cab_*"
0x180043ade  lea     rcx, [rbp+2900h+var_2950]
0x180043ae2  call    ??$assign_sprintf@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@tlx@@YAJAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEB_WZZ; tlx::assign_sprintf<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &,wchar_t const *,...)
0x180043ae7  test    eax, eax
0x180043ae9  jns     short loc_180043B15
0x180043aeb  mov     rcx, cs:WPP_GLOBAL_Control
0x180043af2  lea     rdi, WPP_GLOBAL_Control
0x180043af9  cmp     rcx, rdi
0x180043afc  jz      loc_180043E0D
0x180043b02  test    [rcx+1Ch], bl
0x180043b05  jz      loc_180043DE9
0x180043b0b  mov     edx, 139h
0x180043b10  jmp     loc_180043A09
0x180043b15  lea     rcx, [rsp+2A00h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180043b1a  call    cs:__imp_GetSystemTimeAsFileTime
0x180043b21  nop     dword ptr [rax+rax+00h]
0x180043b26  mov     ecx, [rsp+2A00h+SystemTimeAsFileTime.dwHighDateTime]
0x180043b2a  shl     rcx, 20h
0x180043b2e  mov     eax, [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime]
0x180043b32  or      rcx, rax
0x180043b35  mov     rax, 0FFFFFF36D5964000h
0x180043b3f  add     rax, rcx
0x180043b42  mov     [rsp+2A00h+SystemTimeAsFileTime.dwLowDateTime], eax
0x180043b46  shr     rax, 20h
0x180043b4a  mov     [rsp+2A00h+SystemTimeAsFileTime.dwHighDateTime], eax
0x180043b4e  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x180043b53  lea     rcx, [rbp+2900h+var_14A0]; this
0x180043b5a  call    ?InitMachineStore@CReportArchive@@UEAAJXZ; CReportArchive::InitMachineStore(void)
0x180043b5f  test    eax, eax
0x180043b61  jns     short loc_180043B8D
0x180043b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180043b6a  lea     rdi, WPP_GLOBAL_Control
0x180043b71  cmp     rcx, rdi
0x180043b74  jz      loc_180043E0D
0x180043b7a  test    [rcx+1Ch], bl
0x180043b7d  jz      loc_180043DE9
0x180043b83  mov     edx, 13Ah
0x180043b88  jmp     loc_180043A09
0x180043b8d  lea     r8, [rsp+2A00h+var_29B0]
0x180043b92  mov     rdx, [rbp+2900h+var_2930]; wchar_t *
0x180043b96  lea     rcx, [rbp+2900h+var_14A0]; this
0x180043b9d  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180043ba2  test    eax, eax
0x180043ba4  js      short loc_180043BE2
0x180043ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bad  lea     rdi, WPP_GLOBAL_Control
0x180043bb4  cmp     rcx, rdi
0x180043bb7  jz      short loc_180043BDB
0x180043bb9  test    byte ptr [rcx+1Ch], 4
0x180043bbd  jz      short loc_180043BDB
0x180043bbf  mov     edx, 13Bh
0x180043bc4  lea     r8, WPP_eb079da2851a31dd15f4c4bdfdeb0a1a_Traceguids
0x180043bcb  mov     rcx, [rcx+10h]
0x180043bcf  call    WPP_SF_
0x180043bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180043bdb  mov     esi, ebx
0x180043bdd  jmp     loc_180043DE9
0x180043be2  test    r15d, r15d
0x180043be5  jz      short loc_180043C5C
0x180043be7  test    r14d, r14d
0x180043bea  jz      short loc_180043C5C
0x180043bec  lea     r8, [rsp+2A00h+var_29B0]
0x180043bf1  mov     rdx, [rbp+2900h+var_2950]; wchar_t *
0x180043bf5  lea     rcx, [rbp+2900h+var_14A0]; this
0x180043bfc  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180043c01  test    eax, eax
0x180043c03  js      short loc_180043C5C
0x180043c05  lea     r8, [rsp+2A00h+FileTime1]; struct _FILETIME *
0x180043c0a  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180043c0f  lea     rcx, [rbp+2900h+var_14A0]; this
0x180043c16  call    ?GetReportCreationDate@CReportStore@@QEAAJPEB_WPEAU_FILETIME@@@Z; CReportStore::GetReportCreationDate(wchar_t const *,_FILETIME *)
0x180043c1b  test    eax, eax
0x180043c1d  js      short loc_180043C5C
0x180043c1f  lea     rdx, [rsp+2A00h+SystemTimeAsFileTime]; lpFileTime2
0x180043c24  lea     rcx, [rsp+2A00h+FileTime1]; lpFileTime1
0x180043c29  call    cs:__imp_CompareFileTime
0x180043c30  nop     dword ptr [rax+rax+00h]
0x180043c35  test    eax, eax
0x180043c37  jle     short loc_180043C5C
0x180043c39  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c40  lea     rdi, WPP_GLOBAL_Control
0x180043c47  cmp     rcx, rdi
0x180043c4a  jz      short loc_180043BDB
0x180043c4c  test    byte ptr [rcx+1Ch], 4
0x180043c50  jz      short loc_180043BDB
0x180043c52  mov     edx, 13Ch
0x180043c57  jmp     loc_180043BC4
0x180043c5c  lea     rcx, [rbp+2900h+var_28F0]; this
0x180043c60  call    ?InitMachineStore@CReportQueue@@UEAAJXZ; CReportQueue::InitMachineStore(void)
0x180043c65  test    eax, eax
0x180043c67  jns     short loc_180043C93
0x180043c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180043c70  lea     rdi, WPP_GLOBAL_Control
0x180043c77  cmp     rcx, rdi
0x180043c7a  jz      loc_180043E0D
0x180043c80  test    [rcx+1Ch], bl
0x180043c83  jz      loc_180043DE9
0x180043c89  mov     edx, 13Dh
0x180043c8e  jmp     loc_180043A09
0x180043c93  lea     r8, [rsp+2A00h+var_29B0]
0x180043c98  mov     rdx, [rbp+2900h+var_2930]; wchar_t *
0x180043c9c  lea     rcx, [rbp+2900h+var_28F0]; this
0x180043ca0  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180043ca5  test    eax, eax
0x180043ca7  js      short loc_180043CF2
0x180043ca9  lea     r8, [rsp+2A00h+var_29D0]; int *
0x180043cae  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180043cb3  lea     rcx, [rbp+2900h+var_28F0]; this
0x180043cb7  call    ?HasReportFile@CReportStore@@QEAAJPEB_WPEAH@Z; CReportStore::HasReportFile(wchar_t const *,int *)
0x180043cbc  test    eax, eax
0x180043cbe  js      short loc_180043CF2
0x180043cc0  cmp     [rsp+2A00h+var_29D0], 0
0x180043cc5  jz      short loc_180043CF2
0x180043cc7  mov     rcx, cs:WPP_GLOBAL_Control
0x180043cce  lea     rdi, WPP_GLOBAL_Control
0x180043cd5  cmp     rcx, rdi
0x180043cd8  jz      loc_180043BDB
0x180043cde  test    byte ptr [rcx+1Ch], 4
0x180043ce2  jz      loc_180043BDB
0x180043ce8  mov     edx, 13Eh
0x180043ced  jmp     loc_180043BC4
0x180043cf2  test    r15d, r15d
0x180043cf5  jz      loc_180043D94
0x180043cfb  test    r14d, r14d
0x180043cfe  jz      loc_180043D94
0x180043d04  lea     r8, [rsp+2A00h+var_29B0]
0x180043d09  mov     rdx, [rbp+2900h+var_2950]; wchar_t *
0x180043d0d  lea     rcx, [rbp+2900h+var_28F0]; this
0x180043d11  call    ?EnumerateStoreNextKeyWithPattern@CReportStore@@QEAAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportStore::EnumerateStoreNextKeyWithPattern(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180043d16  test    eax, eax
0x180043d18  js      short loc_180043D94
0x180043d1a  lea     r8, [rsp+2A00h+var_29D0]; int *
0x180043d1f  mov     rdx, [rsp+2A00h+var_29B0]; wchar_t *
0x180043d24  lea     rcx, [rbp+2900h+var_28F0]; this
0x180043d28  call    ?HasReportFile@CReportStore@@QEAAJPEB_WPEAH@Z; CReportStore::HasReportFile(wchar_t const *,int *)
  ... truncated ...
```
