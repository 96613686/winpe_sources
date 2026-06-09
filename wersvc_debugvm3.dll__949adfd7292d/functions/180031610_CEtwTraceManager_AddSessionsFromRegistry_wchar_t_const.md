# CEtwTraceManager::AddSessionsFromRegistry(wchar_t const *)

- ea: `0x180031610`
- end: `0x180031a3f`
- name: `?AddSessionsFromRegistry@CEtwTraceManager@@QEAAJPEB_W@Z`
- size: `1071`
- prototype: `__int64 __fastcall(CEtwTraceManager *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180018c5c`

## callees

- `0x1800029d0`
- `0x1800029f4`
- `0x180002a00`
- `0x1800035e8`
- `0x180007cc8`
- `0x180011648`
- `0x180031498`
- `0x180031610`
- `0x180032664`
- `0x180032914`
- `0x180032b4c`
- `0x1800335f0`
- `0x1800344f0`
- `0x180034550`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031685`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180031685`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031a0d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800317e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003186a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800317e5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18003186a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800316d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003195f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800316d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003195f`

## pseudocode

```c
__int64 __fastcall CEtwTraceManager::AddSessionsFromRegistry(const wchar_t **this, const wchar_t *a2)
{
  HKEY *phkResult; // rax
  signed int v5; // edi
  LSTATUS v6; // eax
  DWORD v7; // r15d
  int *v8; // rax
  int *v9; // rsi
  __int64 v10; // r8
  LSTATUS ValueW; // eax
  int SessionInfo; // eax
  CEtwSession *v13; // rcx
  int v14; // ecx
  bool v15; // cc
  wchar_t *v16; // rax
  CEtwSession *v17; // rbx
  const wchar_t *v18; // rbx
  __int64 v19; // rcx
  char *v20; // r9
  CEtwSession **v21; // rdx
  CEtwSession *v22; // rax
  const wchar_t *v23; // rdx
  __int64 v24; // r8
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+44h] [rbp-BCh] BYREF
  int pvData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  CEtwSession *v30; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE Src[64]; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+A0h] [rbp-60h]
  WCHAR Name[1032]; // [rsp+10E0h] [rbp+FE0h] BYREF

  hKey = 0;
  cchName = 0;
  v27 = 0;
  pvData = 0;
  phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, phkResult) )
  {
    v5 = 1;
    goto LABEL_49;
  }
  v27 = 0;
  pvData = 0;
  cchName = 1025;
  v6 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
  v7 = 1;
  if ( v6 == 259 )
  {
LABEL_48:
    v5 = 0;
    goto LABEL_49;
  }
  while ( 1 )
  {
    if ( v6 == 234 )
      goto LABEL_32;
    if ( v6 )
    {
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      else
        v5 = v6;
      goto LABEL_49;
    }
    v8 = (int *)operator new(0x10A8u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
      goto LABEL_44;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 529) = v8 + 1062;
    *((_QWORD *)v8 + 530) = v8 + 1062;
    *((_WORD *)v8 + 2124) = 0;
    memset_0(Src, 0, 0x1080u);
    memcpy_0(v9 + 2, Src, 0x1080u);
    v9[2] = 4224;
    v9[31] = 120;
    v10 = -1;
    v9[30] = 2170;
    v30 = (CEtwSession *)v9;
    do
      ++v10;
    while ( Name[v10] );
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             v9 + 1058,
                             Name) )
      break;
    cchName = 4;
    ValueW = RegGetValueW(hKey, Name, L"Rundown", 0x18u, 0, &pvData, &cchName);
    if ( ValueW )
    {
      if ( ValueW != 2 )
      {
        v15 = ValueW <= 0;
LABEL_37:
        if ( v15 )
          v5 = ValueW;
        else
          v5 = (unsigned __int16)ValueW | 0x80070000;
        if ( v5 >= 0 )
          v5 = -2147467259;
LABEL_42:
        CEtwSession::~CEtwSession((CEtwSession *)v9);
        operator delete(v9, (const struct std::nothrow_t *)0x10A8);
        goto LABEL_49;
      }
      v9[1] = 0;
    }
    else
    {
      v9[1] = pvData;
    }
    SessionInfo = CEtwSession::QuerySessionInfo((CEtwSession *)v9);
    if ( SessionInfo < 0 )
    {
      LogEtwSessionQuery(this[6], (struct CEtwSession *)v9, SessionInfo);
      CEtwSession::~CEtwSession((CEtwSession *)v9);
      v13 = (CEtwSession *)v9;
LABEL_31:
      operator delete(v13, (const struct std::nothrow_t *)0x10A8);
      goto LABEL_32;
    }
    cchName = 4;
    ValueW = RegGetValueW(hKey, Name, L"PassNumber", 0x18u, 0, &v27, &cchName);
    if ( !ValueW )
      *v9 = v27;
    if ( ValueW == 2 )
    {
      memcpy_0(Src, v9 + 2, 0x1080u);
      v14 = 1;
      if ( (v32 & 0x400) == 0 )
        v14 = 2;
      *v9 = v14;
    }
    else
    {
      v15 = ValueW <= 0;
      if ( ValueW )
        goto LABEL_37;
    }
    v16 = (wchar_t *)this[1];
    if ( v16 == this[2] )
    {
      v18 = *this;
      if ( !(unsigned __int8)utl::vector<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>,utl::allocator<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>>>::_Grow(this) )
      {
        v23 = *this;
        v5 = -2147024882;
        v24 = (char *)this[1] - (char *)*this;
        this[1] = *this;
        utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>>>(
          v19,
          v23,
          v24 >> 3);
        if ( !v9 )
          goto LABEL_49;
        goto LABEL_42;
      }
      v20 = (char *)this[1];
      v21 = &v30;
      if ( (char *)&v30 - (char *)v18 < (unsigned __int64)(v20 - (char *)*this) )
        v21 = (CEtwSession **)((char *)*this + (char *)&v30 - (char *)v18);
      v22 = *v21;
      *v21 = 0;
      v17 = v30;
      *(_QWORD *)v20 = v22;
    }
    else
    {
      v17 = 0;
      *(_QWORD *)v16 = v9;
    }
    this[1] += 4;
    if ( v17 )
    {
      CEtwSession::~CEtwSession(v17);
      v13 = v17;
      goto LABEL_31;
    }
LABEL_32:
    v27 = 0;
    pvData = 0;
    cchName = 1025;
    v6 = RegEnumKeyExW(hKey, v7, Name, &cchName, 0, 0, 0, 0);
    if ( v6 == 259 )
      goto LABEL_48;
    ++v7;
  }
  CEtwSession::~CEtwSession((CEtwSession *)v9);
  operator delete(v9, (const struct std::nothrow_t *)0x10A8);
LABEL_44:
  v5 = -2147024882;
LABEL_49:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180031610  mov     [rsp-8+arg_10], rbx
0x180031615  push    rbp
0x180031616  push    rsi
0x180031617  push    rdi
0x180031618  push    r12
0x18003161a  push    r13
0x18003161c  push    r14
0x18003161e  push    r15
0x180031620  lea     rbp, [rsp-1800h]
0x180031628  mov     eax, 1900h
0x18003162d  call    _alloca_probe
0x180031632  sub     rsp, rax
0x180031635  mov     rax, cs:__security_cookie
0x18003163c  xor     rax, rsp
0x18003163f  mov     [rbp+1830h+var_40], rax
0x180031646  xor     r12d, r12d
0x180031649  mov     r14, rcx
0x18003164c  lea     rcx, [rsp+1930h+hKey]
0x180031651  mov     [rsp+1930h+hKey], r12
0x180031656  mov     [rsp+1930h+cchName], r12d
0x18003165b  mov     rbx, rdx
0x18003165e  mov     [rsp+1930h+var_18EC], r12d
0x180031663  mov     [rsp+1930h+pvData], r12d
0x180031668  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x18003166d  mov     r9d, 20019h; samDesired
0x180031673  mov     [rsp+1930h+phkResult], rax; phkResult
0x180031678  xor     r8d, r8d; ulOptions
0x18003167b  mov     rdx, rbx; lpSubKey
0x18003167e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031685  call    cs:__imp_RegOpenKeyExW
0x18003168b  test    eax, eax
0x18003168d  jz      short loc_180031699
0x18003168f  lea     edi, [r12+1]
0x180031694  jmp     loc_180031A03
0x180031699  mov     rcx, [rsp+1930h+hKey]; hKey
0x18003169e  lea     r9, [rsp+1930h+cchName]; lpcchName
0x1800316a3  mov     [rsp+1930h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800316a8  lea     r8, [rbp+1830h+Name]; lpName
0x1800316af  mov     [rsp+1930h+lpcchClass], r12; lpcchClass
0x1800316b4  xor     edx, edx; dwIndex
0x1800316b6  mov     [rsp+1930h+lpClass], r12; lpClass
0x1800316bb  mov     [rsp+1930h+phkResult], r12; lpReserved
0x1800316c0  mov     [rsp+1930h+var_18EC], r12d
0x1800316c5  mov     [rsp+1930h+pvData], r12d
0x1800316ca  mov     [rsp+1930h+cchName], 401h
0x1800316d2  call    cs:__imp_RegEnumKeyExW
0x1800316d8  mov     edi, 1
0x1800316dd  mov     r15d, edi
0x1800316e0  cmp     eax, 103h
0x1800316e5  jz      loc_180031A00
0x1800316eb  mov     r13d, 10A8h
0x1800316f1  cmp     eax, 0EAh
0x1800316f6  jz      loc_180031925
0x1800316fc  test    eax, eax
0x1800316fe  jnz     loc_1800319E5
0x180031704  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18003170b  mov     rcx, r13; unsigned __int64
0x18003170e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180031713  mov     rsi, rax
0x180031716  test    rax, rax
0x180031719  jz      loc_1800319DE
0x18003171f  lea     rcx, [rax+1098h]
0x180031726  mov     [rax], r12
0x180031729  mov     [rax+1088h], rcx
0x180031730  xor     edx, edx; Val
0x180031732  mov     [rax+1090h], rcx
0x180031739  mov     r8d, 1080h; Size
0x18003173f  mov     [rcx], r12w
0x180031743  lea     rcx, [rsp+1930h+Src]; void *
0x180031748  call    memset_0
0x18003174d  mov     r8d, 1080h; Size
0x180031753  lea     rdx, [rsp+1930h+Src]; Src
0x180031758  lea     rcx, [rsi+8]; void *
0x18003175c  call    memcpy_0
0x180031761  lea     rcx, [rsi+1088h]
0x180031768  mov     dword ptr [rsi+8], 1080h
0x18003176f  lea     rax, [rbp+1830h+Name]
0x180031776  mov     dword ptr [rsi+7Ch], 78h ; 'x'
0x18003177d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180031781  mov     dword ptr [rsi+78h], 87Ah
0x180031788  mov     [rsp+1930h+var_18D8], rsi
0x18003178d  inc     r8
0x180031790  cmp     [rax+r8*2], r12w
0x180031795  jnz     short loc_18003178D
0x180031797  lea     rdx, [rbp+1830h+Name]
0x18003179e  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1800317a3  test    al, al
0x1800317a5  jz      loc_1800319CB
0x1800317ab  mov     rcx, [rsp+1930h+hKey]; hkey
0x1800317b0  lea     rax, [rsp+1930h+cchName]
0x1800317b5  mov     [rsp+1930h+lpcchClass], rax; pcbData
0x1800317ba  lea     r8, aRundown; "Rundown"
0x1800317c1  lea     rax, [rsp+1930h+pvData]
0x1800317c6  mov     [rsp+1930h+cchName], 4
0x1800317ce  mov     [rsp+1930h+lpClass], rax; pvData
0x1800317d3  lea     rdx, [rbp+1830h+Name]; lpSubKey
0x1800317da  mov     r9d, 18h; dwFlags
0x1800317e0  mov     [rsp+1930h+phkResult], r12; pdwType
0x1800317e5  call    cs:__imp_RegGetValueW
0x1800317eb  test    eax, eax
0x1800317ed  jnz     short loc_1800317F8
0x1800317ef  mov     eax, [rsp+1930h+pvData]
0x1800317f3  mov     [rsi+4], eax
0x1800317f6  jmp     short loc_180031805
0x1800317f8  cmp     eax, 2
0x1800317fb  jnz     loc_18003199B
0x180031801  mov     [rsi+4], r12d
0x180031805  mov     rcx, rsi; this
0x180031808  call    ?QuerySessionInfo@CEtwSession@@QEAAJXZ; CEtwSession::QuerySessionInfo(void)
0x18003180d  test    eax, eax
0x18003180f  jns     short loc_180031830
0x180031811  mov     rcx, [r14+30h]; wchar_t *
0x180031815  mov     r8d, eax; int
0x180031818  mov     rdx, rsi; struct CEtwSession *
0x18003181b  call    ?LogEtwSessionQuery@@YAXPEB_WPEAVCEtwSession@@J@Z; LogEtwSessionQuery(wchar_t const *,CEtwSession *,long)
0x180031820  mov     rcx, rsi; this
0x180031823  call    ??1CEtwSession@@QEAA@XZ; CEtwSession::~CEtwSession(void)
0x180031828  mov     rcx, rsi
0x18003182b  jmp     loc_18003191D
0x180031830  mov     rcx, [rsp+1930h+hKey]; hkey
0x180031835  lea     rax, [rsp+1930h+cchName]
0x18003183a  mov     [rsp+1930h+lpcchClass], rax; pcbData
0x18003183f  lea     r8, aPassnumber; "PassNumber"
0x180031846  lea     rax, [rsp+1930h+var_18EC]
0x18003184b  mov     [rsp+1930h+cchName], 4
0x180031853  mov     [rsp+1930h+lpClass], rax; pvData
0x180031858  lea     rdx, [rbp+1830h+Name]; lpSubKey
0x18003185f  mov     r9d, 18h; dwFlags
0x180031865  mov     [rsp+1930h+phkResult], r12; pdwType
0x18003186a  call    cs:__imp_RegGetValueW
0x180031870  test    eax, eax
0x180031872  jnz     short loc_18003187A
0x180031874  mov     ecx, [rsp+1930h+var_18EC]
0x180031878  mov     [rsi], ecx
0x18003187a  cmp     eax, 2
0x18003187d  jnz     short loc_1800318AA
0x18003187f  lea     rdx, [rsi+8]; Src
0x180031883  mov     r8d, 1080h; Size
0x180031889  lea     rcx, [rsp+1930h+Src]; void *
0x18003188e  call    memcpy_0
0x180031893  test    [rbp+1830h+var_1890], 400h
0x18003189a  mov     rax, rsi
0x18003189d  mov     ecx, edi
0x18003189f  jnz     short loc_1800318A6
0x1800318a1  mov     ecx, 2
0x1800318a6  mov     [rax], ecx
0x1800318a8  jmp     short loc_1800318B2
0x1800318aa  test    eax, eax
0x1800318ac  jnz     loc_18003199D
0x1800318b2  mov     rax, [r14+8]
0x1800318b6  cmp     rax, [r14+10h]
0x1800318ba  jz      short loc_1800318C4
0x1800318bc  mov     rbx, r12
0x1800318bf  mov     [rax], rsi
0x1800318c2  jmp     short loc_180031908
0x1800318c4  mov     rbx, [r14]
0x1800318c7  mov     rcx, r14
0x1800318ca  call    ?_Grow@?$vector@V?$unique_ptr@VCEtwSession@@U?$default_delete@VCEtwSession@@@utl@@@utl@@V?$allocator@V?$unique_ptr@VCEtwSession@@U?$default_delete@VCEtwSession@@@utl@@@utl@@@2@@utl@@AEAA_NXZ; utl::vector<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>,utl::allocator<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>>>::_Grow(void)
0x1800318cf  test    al, al
0x1800318d1  jz      loc_180031978
0x1800318d7  mov     r9, [r14+8]
0x1800318db  lea     rcx, [rsp+1930h+var_18D8]
0x1800318e0  mov     r8, [r14]
0x1800318e3  lea     rdx, [rsp+1930h+var_18D8]
0x1800318e8  mov     rax, r9
0x1800318eb  sub     rcx, rbx
0x1800318ee  sub     rax, r8
0x1800318f1  cmp     rcx, rax
0x1800318f4  jnb     short loc_1800318FA
0x1800318f6  lea     rdx, [rcx+r8]
0x1800318fa  mov     rax, [rdx]
0x1800318fd  mov     [rdx], r12
0x180031900  mov     rbx, [rsp+1930h+var_18D8]
0x180031905  mov     [r9], rax
0x180031908  add     qword ptr [r14+8], 8
0x18003190d  test    rbx, rbx
0x180031910  jz      short loc_180031925
0x180031912  mov     rcx, rbx; this
0x180031915  call    ??1CEtwSession@@QEAA@XZ; CEtwSession::~CEtwSession(void)
0x18003191a  mov     rcx, rbx; void *
0x18003191d  mov     rdx, r13; struct std::nothrow_t *
0x180031920  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180031925  mov     rcx, [rsp+1930h+hKey]; hKey
0x18003192a  lea     r9, [rsp+1930h+cchName]; lpcchName
0x18003192f  mov     [rsp+1930h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180031934  lea     r8, [rbp+1830h+Name]; lpName
0x18003193b  mov     [rsp+1930h+lpcchClass], r12; lpcchClass
0x180031940  mov     edx, r15d; dwIndex
0x180031943  mov     [rsp+1930h+lpClass], r12; lpClass
0x180031948  mov     [rsp+1930h+phkResult], r12; lpReserved
0x18003194d  mov     [rsp+1930h+var_18EC], r12d
0x180031952  mov     [rsp+1930h+pvData], r12d
0x180031957  mov     [rsp+1930h+cchName], 401h
0x18003195f  call    cs:__imp_RegEnumKeyExW
0x180031965  cmp     eax, 103h
0x18003196a  jz      loc_180031A00
0x180031970  add     r15d, edi
0x180031973  jmp     loc_1800316F1
0x180031978  mov     rdx, [r14]
0x18003197b  mov     edi, 8007000Eh
0x180031980  mov     r8, [r14+8]
0x180031984  sub     r8, rdx
0x180031987  mov     [r14+8], rdx
0x18003198b  sar     r8, 3
0x18003198f  call    ??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCEtwSession@@U?$default_delete@VCEtwSession@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCEtwSession@@U?$default_delete@VCEtwSession@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCEtwSession@@U?$default_delete@VCEtwSession@@@utl@@@0@_K@Z; utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>>>(utl::allocator<utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>>> &,utl::unique_ptr<CEtwSession,utl::default_delete<CEtwSession>> *,unsigned __int64)
0x180031994  test    rsi, rsi
0x180031997  jz      short loc_180031A03
0x180031999  jmp     short loc_1800319B6
0x18003199b  test    eax, eax
0x18003199d  jg      short loc_1800319A3
0x18003199f  mov     edi, eax
0x1800319a1  jmp     short loc_1800319AC
0x1800319a3  movzx   edi, ax
0x1800319a6  or      edi, 80070000h
0x1800319ac  test    edi, edi
0x1800319ae  mov     eax, 80004005h
0x1800319b3  cmovns  edi, eax
0x1800319b6  mov     rcx, rsi; this
0x1800319b9  call    ??1CEtwSession@@QEAA@XZ; CEtwSession::~CEtwSession(void)
0x1800319be  mov     rdx, r13; struct std::nothrow_t *
0x1800319c1  mov     rcx, rsi; void *
0x1800319c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800319c9  jmp     short loc_180031A03
0x1800319cb  mov     rcx, rsi; this
0x1800319ce  call    ??1CEtwSession@@QEAA@XZ; CEtwSession::~CEtwSession(void)
0x1800319d3  mov     rdx, r13; struct std::nothrow_t *
0x1800319d6  mov     rcx, rsi; void *
0x1800319d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800319de  mov     edi, 8007000Eh
0x1800319e3  jmp     short loc_180031A03
0x1800319e5  jg      short loc_1800319EB
0x1800319e7  mov     edi, eax
0x1800319e9  jmp     short loc_1800319F4
0x1800319eb  movzx   edi, ax
0x1800319ee  or      edi, 80070000h
0x1800319f4  test    edi, edi
0x1800319f6  mov     eax, 80004005h
0x1800319fb  cmovns  edi, eax
0x1800319fe  jmp     short loc_180031A03
0x180031a00  mov     edi, r12d
0x180031a03  mov     rcx, [rsp+1930h+hKey]; hKey
0x180031a08  test    rcx, rcx
0x180031a0b  jz      short loc_180031A13
0x180031a0d  call    cs:__imp_RegCloseKey
0x180031a13  mov     eax, edi
0x180031a15  mov     rcx, [rbp+1830h+var_40]
0x180031a1c  xor     rcx, rsp; StackCookie
0x180031a1f  call    __security_check_cookie
0x180031a24  mov     rbx, [rsp+1930h+arg_10]
0x180031a2c  add     rsp, 1900h
0x180031a33  pop     r15
0x180031a35  pop     r14
0x180031a37  pop     r13
0x180031a39  pop     r12
0x180031a3b  pop     rdi
0x180031a3c  pop     rsi
0x180031a3d  pop     rbp
0x180031a3e  retn
```
