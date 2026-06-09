# CertHelper::CreateKey(unsigned __int64,ushort const *,unsigned __int64 *)

- ea: `0x14015c884`
- end: `0x14015ce2d`
- name: `?CreateKey@CertHelper@@CAJ_KPEBGPEA_K@Z`
- size: `1449`
- prototype: `__int64 __fastcall(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszKeyName, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1407df298`

## callees

- `0x14007bb80`
- `0x140091cd0`
- `0x140092260`
- `0x1400923e8`
- `0x1400938f0`
- `0x140093948`
- `0x1400e5644`
- `0x1400eaaac`
- `0x1400ee880`
- `0x140116354`
- `0x140116380`
- `0x14015ac08`
- `0x14015c884`
- `0x14015d018`
- `0x140209758`
- `0x14022adfc`
- `0x140237a2c`
- `0x1404828e0`
- `0x1404835a0`
- `0x14052a79c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cb8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cc45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cc5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cdc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cdd6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cb8a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cba4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cc45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cc5a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cdc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14015cdd6`
- `ncrypt!NCryptCreatePersistedKey` at `0x14015c9db`
- `ncrypt!NCryptCreatePersistedKey` at `0x14015c9db`
- `ncrypt!NCryptFinalizeKey` at `0x14015cd9a`
- `ncrypt!NCryptFinalizeKey` at `0x14015cd9a`
- `ncrypt!NCryptSetProperty` at `0x14015cc0d`
- `ncrypt!NCryptSetProperty` at `0x14015cce0`
- `ncrypt!NCryptSetProperty` at `0x14015cd23`
- `ncrypt!NCryptSetProperty` at `0x14015cd70`
- `ncrypt!NCryptSetProperty` at `0x14015cc0d`
- `ncrypt!NCryptSetProperty` at `0x14015cce0`
- `ncrypt!NCryptSetProperty` at `0x14015cd23`
- `ncrypt!NCryptSetProperty` at `0x14015cd70`
- `ncrypt!NCryptDeleteKey` at `0x14015c9a3`
- `ncrypt!NCryptDeleteKey` at `0x14015cca4`
- `ncrypt!NCryptDeleteKey` at `0x14015c9a3`
- `ncrypt!NCryptDeleteKey` at `0x14015cca4`

## string_xrefs

- `0x14015c913`: `onecore\vm\common\vdev\certhelper\certhelper.cpp`
- `0x14015cb6b`: `onecore\vm\common\vdev\certhelper\certhelper.cpp`
- `0x14015cbce`: `onecore\vm\common\vdev\certhelper\certhelper.cpp`
- `0x14015cbf8`: `Security Descr`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CertHelper::CreateKey(NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszKeyName, unsigned __int64 *a3)
{
  __int64 v5; // rdx
  int v6; // eax
  unsigned int LastError; // edi
  const char *v9; // r9
  const struct _ACL *Dacl; // rax
  const char *v11; // r9
  DWORD v12; // eax
  HLOCAL v13; // rdi
  const char *v14; // r9
  __int64 v15; // rdx
  unsigned int v16; // esi
  DWORD v17; // eax
  DWORD v18; // eax
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-1A8h]
  DWORD dwLegacyKeySpeca; // [rsp+20h] [rbp-1A8h]
  char *v21; // [rsp+30h] [rbp-198h] BYREF
  _QWORD v22[3]; // [rsp+38h] [rbp-190h] BYREF
  __int16 v23; // [rsp+50h] [rbp-178h]
  void *v24[11]; // [rsp+60h] [rbp-168h] BYREF
  char v25; // [rsp+B8h] [rbp-110h]
  NCRYPT_KEY_HANDLE *phKey; // [rsp+C0h] [rbp-108h] BYREF
  HLOCAL v27[2]; // [rsp+C8h] [rbp-100h] BYREF
  HLOCAL hMem[2]; // [rsp+D8h] [rbp-F0h] BYREF
  BYTE pbInput[8]; // [rsp+E8h] [rbp-E0h] BYREF
  void *v30[10]; // [rsp+F0h] [rbp-D8h] BYREF
  void *v31[10]; // [rsp+140h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  phKey = a3;
  *a3 = 0;
  v24[10] = &phKey;
  v25 = 1;
  memset_0(v30, 0, sizeof(v30));
  Vml::VmSid::VmSid((Vml::VmSid *)v30, 0);
  v21 = (char *)v30;
  v22[0] = retaddr;
  v22[1] = "onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp";
  v22[2] = 0;
  v23 = 1817;
  v27[0] = &off_1408F6CB8;
  v27[1] = &v21;
  v6 = wil::details::ResultFromException(v22, v5, v27);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x719,
      (unsigned int)"onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp",
      (const char *)(unsigned int)v6,
      dwLegacyKeySpec);
LABEL_3:
    Vml::VmSid::~VmSid((Vml::VmSid *)v30);
    if ( *phKey )
      NCryptDeleteKey(*phKey, 0x40u);
    return LastError;
  }
  if ( NCryptCreatePersistedKey(hProvider, phKey, L"RSA", pszKeyName, 0, 0x20u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x720,
                  (unsigned int)"onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp",
                  v9);
    goto LABEL_3;
  }
  memset_0(v31, 0, sizeof(v31));
  Vml::VmSid::VmSid(
    (Vml::VmSid *)v31,
    L"S-1-15-3-1024-2268835264-3721307629-241982045-173645152-1490879176-104643441-2915960892-1612460704");
  memset_0(v24, 0, 0x50u);
  Vml::Sids::LocalSystem(v24);
  *(_OWORD *)v27 = 0;
  *(_OWORD *)hMem = 0;
  Vml::VmDacl::VmDacl((Vml::VmDacl *)hMem, 0);
  try
  {
    Vml::VmSecurityDescriptor::Initialize((Vml::VmSecurityDescriptor *)v27);
    Vml::VmSecurityDescriptor::SetOwner((Vml::VmSecurityDescriptor *)v27, v24[0]);
    Vml::VmSecurityDescriptor::SetGroup((Vml::VmSecurityDescriptor *)v27, v30[0]);
    Dacl = Vml::VmSecurityDescriptor::GetDacl((Vml::VmSecurityDescriptor *)v27);
    Vml::VmAcl::Assign((Vml::VmAcl *)hMem, Dacl);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v30[0], 0x90000000, 0, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v31[0], 0x90000000, 0, GRANT_ACCESS);
    Vml::VmAcl::UpdateAccess((Vml::VmAcl *)hMem, v24[0], 0x90000000, 0, GRANT_ACCESS);
    Vml::VmSecurityDescriptor::SetDacl((Vml::VmSecurityDescriptor *)v27, (const struct _ACL *)hMem[0]);
    Vml::VmSecurityDescriptor::MakeSelfRelative((Vml::VmSecurityDescriptor *)v27);
  }
  catch ( ... )
  {
    LODWORD(v21) = wil::details::in1diag3::Log_CaughtException(
                     retaddr,
                     (void *)0x739,
                     (unsigned int)"onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp",
                     v11);
    LastError = (unsigned int)v21;
    if ( (int)v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73B,
        (unsigned int)"onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp",
        (const char *)(unsigned int)v21,
        dwLegacyKeySpeca);
      if ( hMem[0] )
        LocalFree(hMem[0]);
      if ( v27[0] )
        LocalFree(v27[0]);
      Vml::VmSid::~VmSid((Vml::VmSid *)v24);
      Vml::VmSid::~VmSid((Vml::VmSid *)v31);
      goto LABEL_3;
    }
  }
  v12 = Vml::VmSecurityDescriptor::Length((Vml::VmSecurityDescriptor *)v27);
  v13 = v27[0];
  if ( NCryptSetProperty(*phKey, L"Security Descr", (PBYTE)v27[0], v12, 0x80000041) )
  {
    v15 = 1857;
LABEL_17:
    v16 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\vm\\common\\vdev\\certhelper\\certhelper.cpp",
            v14);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( v13 )
      LocalFree(v13);
    Vml::VmSid::~VmSid((Vml::VmSid *)v24);
    Vml::VmSid::~VmSid((Vml::VmSid *)v31);
    Vml::VmSid::~VmSid((Vml::VmSid *)v30);
    if ( *phKey )
      NCryptDeleteKey(*phKey, 0x40u);
    return v16;
  }
  v17 = Vml::VmSecurityDescriptor::Length((Vml::VmSecurityDescriptor *)v27);
  if ( NCryptSetProperty(*phKey, L"Security Descr", (PBYTE)v13, v17, 0x80000042) )
  {
    v15 = 1863;
    goto LABEL_17;
  }
  v18 = Vml::VmSecurityDescriptor::Length((Vml::VmSecurityDescriptor *)v27);
  if ( NCryptSetProperty(*phKey, L"Security Descr", (PBYTE)v13, v18, 0x80000044) )
  {
    v15 = 1869;
    goto LABEL_17;
  }
  *(_DWORD *)pbInput = 2048;
  if ( NCryptSetProperty(*phKey, L"Length", pbInput, 4u, 0) )
  {
    v15 = 1876;
    goto LABEL_17;
  }
  if ( NCryptFinalizeKey(*phKey, 0x240u) )
  {
    v15 = 1883;
    goto LABEL_17;
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v13 )
    LocalFree(v13);
  Vml::VmSid::~VmSid((Vml::VmSid *)v24);
  Vml::VmSid::~VmSid((Vml::VmSid *)v31);
  Vml::VmSid::~VmSid((Vml::VmSid *)v30);
  return 0;
}

```

## disassembly

```asm
0x14015c884  mov     r11, rsp
0x14015c887  push    rsi
0x14015c888  push    rdi
0x14015c889  push    r13
0x14015c88b  push    r14
0x14015c88d  push    r15
0x14015c88f  sub     rsp, 1A0h
0x14015c896  mov     rax, cs:__security_cookie
0x14015c89d  xor     rax, rsp
0x14015c8a0  mov     [rsp+1C8h+var_38], rax
0x14015c8a8  mov     r15, rdx
0x14015c8ab  mov     r14, rcx
0x14015c8ae  mov     [r11-108h], r8
0x14015c8b5  mov     qword ptr [r8], 0
0x14015c8bc  lea     rax, [r11-108h]
0x14015c8c3  mov     [r11-118h], rax
0x14015c8ca  mov     [rsp+1C8h+var_110], 1
0x14015c8d2  mov     r13d, 50h ; 'P'
0x14015c8d8  mov     r8d, r13d; Size
0x14015c8db  xor     edx, edx; Val
0x14015c8dd  lea     rcx, [r11-0D8h]; void *
0x14015c8e4  call    memset_0
0x14015c8e9  xor     edx, edx; void *
0x14015c8eb  lea     rcx, [rsp+1C8h+var_D8]; this
0x14015c8f3  call    ??0VmSid@Vml@@QEAA@PEAX@Z; Vml::VmSid::VmSid(void *)
0x14015c8f8  nop
0x14015c8f9  lea     rax, [rsp+1C8h+var_D8]
0x14015c901  mov     [rsp+1C8h+var_198], rax
0x14015c906  mov     rax, [rsp+1C8h]
0x14015c90e  mov     [rsp+1C8h+var_190], rax
0x14015c913  lea     rsi, aOnecoreVmCommo_40; "onecore\\vm\\common\\vdev\\certhelper\\"...
0x14015c91a  mov     [rsp+1C8h+var_188], rsi
0x14015c91f  mov     [rsp+1C8h+var_180], 0
0x14015c928  mov     eax, 719h
0x14015c92d  mov     [rsp+1C8h+var_178], ax
0x14015c932  lea     rax, off_1408F6CB8
0x14015c939  mov     [rsp+1C8h+var_100], rax
0x14015c941  lea     rax, [rsp+1C8h+var_198]
0x14015c946  mov     [rsp+1C8h+var_100+8], rax
0x14015c94e  lea     r8, [rsp+1C8h+var_100]
0x14015c956  lea     rcx, [rsp+1C8h+var_190]
0x14015c95b  call    ?ResultFromException@details@wil@@YAJAEBUDiagnosticsInfo@2@W4SupportedExceptions@2@AEAUIFunctor@12@@Z; wil::details::ResultFromException(wil::DiagnosticsInfo const &,wil::SupportedExceptions,wil::details::IFunctor &)
0x14015c960  mov     edi, eax
0x14015c962  test    eax, eax
0x14015c964  jns     short loc_14015C9B6
0x14015c966  mov     rcx, [rsp+1C8h]; this
0x14015c96e  mov     r9d, eax; char *
0x14015c971  mov     r8, rsi; unsigned int
0x14015c974  mov     edx, 719h; void *
0x14015c979  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14015c97e  nop
0x14015c97f  lea     rcx, [rsp+1C8h+var_D8]; this
0x14015c987  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015c98c  nop
0x14015c98d  mov     rcx, [rsp+1C8h+phKey]
0x14015c995  cmp     qword ptr [rcx], 0
0x14015c999  jz      short loc_14015C9AF
0x14015c99b  mov     edx, 40h ; '@'; dwFlags
0x14015c9a0  mov     rcx, [rcx]; hKey
0x14015c9a3  call    cs:__imp_NCryptDeleteKey
0x14015c9aa  nop     dword ptr [rax+rax+00h]
0x14015c9af  mov     eax, edi
0x14015c9b1  jmp     loc_14015CE0C
0x14015c9b6  mov     [rsp+1C8h+dwFlags], 20h ; ' '; dwFlags
0x14015c9be  mov     [rsp+1C8h+dwLegacyKeySpec], 0; dwLegacyKeySpec
0x14015c9c6  mov     r9, r15; pszKeyName
0x14015c9c9  lea     r8, pszAlgId; "RSA"
0x14015c9d0  mov     rdx, [rsp+1C8h+phKey]; phKey
0x14015c9d8  mov     rcx, r14; hProvider
0x14015c9db  call    cs:__imp_NCryptCreatePersistedKey
0x14015c9e2  nop     dword ptr [rax+rax+00h]
0x14015c9e7  test    eax, eax
0x14015c9e9  jz      short loc_14015CA07
0x14015c9eb  mov     rcx, [rsp+1C8h]; this
0x14015c9f3  mov     r8, rsi; unsigned int
0x14015c9f6  mov     edx, 720h; void *
0x14015c9fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14015ca00  mov     edi, eax
0x14015ca02  jmp     loc_14015C97F
0x14015ca07  mov     r8, r13; Size
0x14015ca0a  xor     edx, edx; Val
0x14015ca0c  lea     rcx, [rsp+1C8h+var_88]; void *
0x14015ca14  call    memset_0
0x14015ca19  lea     rdx, StringSid; "S-1-15-3-1024-2268835264-3721307629-241"...
0x14015ca20  lea     rcx, [rsp+1C8h+var_88]; this
0x14015ca28  call    ??0VmSid@Vml@@QEAA@PEBG@Z; Vml::VmSid::VmSid(ushort const *)
0x14015ca2d  nop
0x14015ca2e  mov     r8, r13; Size
0x14015ca31  xor     edx, edx; Val
0x14015ca33  lea     rcx, [rsp+1C8h+var_168]; void *
0x14015ca38  call    memset_0
0x14015ca3d  lea     rcx, [rsp+1C8h+var_168]
0x14015ca42  call    ?LocalSystem@Sids@Vml@@YA?AVVmSid@2@XZ; Vml::Sids::LocalSystem(void)
0x14015ca47  nop
0x14015ca48  xorps   xmm0, xmm0
0x14015ca4b  movups  xmmword ptr [rsp+1C8h+var_100], xmm0
0x14015ca53  mov     [rsp+1C8h+var_100], 0
0x14015ca5f  movups  xmmword ptr [rsp+1C8h+hMem], xmm0
0x14015ca67  xor     edx, edx; struct _ACL *
0x14015ca69  lea     rcx, [rsp+1C8h+hMem]; this
0x14015ca71  call    ??0VmDacl@Vml@@QEAA@PEBU_ACL@@@Z; Vml::VmDacl::VmDacl(_ACL const *)
0x14015ca76  nop
0x14015ca77  lea     rcx, [rsp+1C8h+var_100]; this
0x14015ca7f  call    ?Initialize@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::Initialize(void)
0x14015ca84  mov     rdx, [rsp+1C8h+var_168]; void *
0x14015ca89  lea     rcx, [rsp+1C8h+var_100]; this
0x14015ca91  call    ?SetOwner@VmSecurityDescriptor@Vml@@QEAAXPEAX@Z; Vml::VmSecurityDescriptor::SetOwner(void *)
0x14015ca96  mov     rdx, [rsp+1C8h+var_D8]; void *
0x14015ca9e  lea     rcx, [rsp+1C8h+var_100]; this
0x14015caa6  call    ?SetGroup@VmSecurityDescriptor@Vml@@QEAAXPEAX@Z; Vml::VmSecurityDescriptor::SetGroup(void *)
0x14015caab  lea     rcx, [rsp+1C8h+var_100]; this
0x14015cab3  call    ?GetDacl@VmSecurityDescriptor@Vml@@QEBAPEBU_ACL@@XZ; Vml::VmSecurityDescriptor::GetDacl(void)
0x14015cab8  mov     rdx, rax; struct _ACL *
0x14015cabb  lea     rcx, [rsp+1C8h+hMem]; this
0x14015cac3  call    ?Assign@VmAcl@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmAcl::Assign(_ACL const *)
0x14015cac8  mov     [rsp+1C8h+dwLegacyKeySpec], 1; enum _ACCESS_MODE
0x14015cad0  xor     r9d, r9d; unsigned int
0x14015cad3  mov     edi, 90000000h
0x14015cad8  mov     r8d, edi; unsigned int
0x14015cadb  mov     rdx, [rsp+1C8h+var_D8]; void *
0x14015cae3  lea     rcx, [rsp+1C8h+hMem]; this
0x14015caeb  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14015caf0  mov     [rsp+1C8h+dwLegacyKeySpec], 1; enum _ACCESS_MODE
0x14015caf8  xor     r9d, r9d; unsigned int
0x14015cafb  mov     r8d, edi; unsigned int
0x14015cafe  mov     rdx, [rsp+1C8h+var_88]; void *
0x14015cb06  lea     rcx, [rsp+1C8h+hMem]; this
0x14015cb0e  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14015cb13  mov     [rsp+1C8h+dwLegacyKeySpec], 1; enum _ACCESS_MODE
0x14015cb1b  xor     r9d, r9d; unsigned int
0x14015cb1e  mov     r8d, edi; unsigned int
0x14015cb21  mov     rdx, [rsp+1C8h+var_168]; void *
0x14015cb26  lea     rcx, [rsp+1C8h+hMem]; this
0x14015cb2e  call    ?UpdateAccess@VmAcl@Vml@@IEAAXPEAXKKW4_ACCESS_MODE@@@Z; Vml::VmAcl::UpdateAccess(void *,ulong,ulong,_ACCESS_MODE)
0x14015cb33  mov     rdx, [rsp+1C8h+hMem]; struct _ACL *
0x14015cb3b  lea     rcx, [rsp+1C8h+var_100]; this
0x14015cb43  call    ?SetDacl@VmSecurityDescriptor@Vml@@QEAAXPEBU_ACL@@@Z; Vml::VmSecurityDescriptor::SetDacl(_ACL const *)
0x14015cb48  lea     rcx, [rsp+1C8h+var_100]; this
0x14015cb50  call    ?MakeSelfRelative@VmSecurityDescriptor@Vml@@QEAAXXZ; Vml::VmSecurityDescriptor::MakeSelfRelative(void)
0x14015cb55  nop
0x14015cb56  jmp     short loc_14015CBD5
0x14015cb58  mov     edi, dword ptr [rsp+1C8h+var_198]
0x14015cb5c  test    edi, edi
0x14015cb5e  jns     short loc_14015CBCE
0x14015cb60  mov     rcx, [rsp+1C8h]; this
0x14015cb68  mov     r9d, edi; char *
0x14015cb6b  lea     r8, aOnecoreVmCommo_40; "onecore\\vm\\common\\vdev\\certhelper\\"...
0x14015cb72  mov     edx, 73Bh; void *
0x14015cb77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14015cb7c  nop
0x14015cb7d  mov     rcx, [rsp+1C8h+hMem]; hMem
0x14015cb85  test    rcx, rcx
0x14015cb88  jz      short loc_14015CB97
0x14015cb8a  call    cs:__imp_LocalFree
0x14015cb91  nop     dword ptr [rax+rax+00h]
0x14015cb96  nop
0x14015cb97  mov     rcx, [rsp+1C8h+var_100]; hMem
0x14015cb9f  test    rcx, rcx
0x14015cba2  jz      short loc_14015CBB1
0x14015cba4  call    cs:__imp_LocalFree
0x14015cbab  nop     dword ptr [rax+rax+00h]
0x14015cbb0  nop
0x14015cbb1  lea     rcx, [rsp+1C8h+var_168]; this
0x14015cbb6  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cbbb  nop
0x14015cbbc  lea     rcx, [rsp+1C8h+var_88]; this
0x14015cbc4  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cbc9  jmp     loc_14015C97F
0x14015cbce  lea     rsi, aOnecoreVmCommo_40; "onecore\\vm\\common\\vdev\\certhelper\\"...
0x14015cbd5  lea     rcx, [rsp+1C8h+var_100]; this
0x14015cbdd  call    ?Length@VmSecurityDescriptor@Vml@@QEBAKXZ; Vml::VmSecurityDescriptor::Length(void)
0x14015cbe2  mov     [rsp+1C8h+dwLegacyKeySpec], 80000041h; dwFlags
0x14015cbea  mov     r9d, eax; cbInput
0x14015cbed  mov     rdi, [rsp+1C8h+var_100]
0x14015cbf5  mov     r8, rdi; pbInput
0x14015cbf8  lea     r14, pszProperty; "Security Descr"
0x14015cbff  mov     rdx, r14; pszProperty
0x14015cc02  mov     rcx, [rsp+1C8h+phKey]
0x14015cc0a  mov     rcx, [rcx]; hObject
0x14015cc0d  call    cs:__imp_NCryptSetProperty
0x14015cc14  nop     dword ptr [rax+rax+00h]
0x14015cc19  test    eax, eax
0x14015cc1b  jz      loc_14015CCB7
0x14015cc21  mov     edx, 741h; void *
0x14015cc26  mov     rcx, [rsp+1C8h]; this
0x14015cc2e  mov     r8, rsi; unsigned int
0x14015cc31  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14015cc36  mov     esi, eax
0x14015cc38  mov     rcx, [rsp+1C8h+hMem]; hMem
0x14015cc40  test    rcx, rcx
0x14015cc43  jz      short loc_14015CC52
0x14015cc45  call    cs:__imp_LocalFree
0x14015cc4c  nop     dword ptr [rax+rax+00h]
0x14015cc51  nop
0x14015cc52  test    rdi, rdi
0x14015cc55  jz      short loc_14015CC67
0x14015cc57  mov     rcx, rdi; hMem
0x14015cc5a  call    cs:__imp_LocalFree
0x14015cc61  nop     dword ptr [rax+rax+00h]
0x14015cc66  nop
0x14015cc67  lea     rcx, [rsp+1C8h+var_168]; this
0x14015cc6c  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cc71  nop
0x14015cc72  lea     rcx, [rsp+1C8h+var_88]; this
0x14015cc7a  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cc7f  nop
0x14015cc80  lea     rcx, [rsp+1C8h+var_D8]; this
0x14015cc88  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cc8d  nop
0x14015cc8e  mov     rax, [rsp+1C8h+phKey]
0x14015cc96  cmp     qword ptr [rax], 0
0x14015cc9a  jz      short loc_14015CCB0
0x14015cc9c  mov     edx, 40h ; '@'; dwFlags
0x14015cca1  mov     rcx, [rax]; hKey
0x14015cca4  call    cs:__imp_NCryptDeleteKey
0x14015ccab  nop     dword ptr [rax+rax+00h]
0x14015ccb0  mov     eax, esi
0x14015ccb2  jmp     loc_14015CE0C
0x14015ccb7  lea     rcx, [rsp+1C8h+var_100]; this
0x14015ccbf  call    ?Length@VmSecurityDescriptor@Vml@@QEBAKXZ; Vml::VmSecurityDescriptor::Length(void)
0x14015ccc4  mov     [rsp+1C8h+dwLegacyKeySpec], 80000042h; dwFlags
0x14015cccc  mov     r9d, eax; cbInput
0x14015cccf  mov     r8, rdi; pbInput
0x14015ccd2  mov     rdx, r14; pszProperty
0x14015ccd5  mov     rcx, [rsp+1C8h+phKey]
0x14015ccdd  mov     rcx, [rcx]; hObject
0x14015cce0  call    cs:__imp_NCryptSetProperty
0x14015cce7  nop     dword ptr [rax+rax+00h]
0x14015ccec  test    eax, eax
0x14015ccee  jz      short loc_14015CCFA
0x14015ccf0  mov     edx, 747h
0x14015ccf5  jmp     loc_14015CC26
0x14015ccfa  lea     rcx, [rsp+1C8h+var_100]; this
0x14015cd02  call    ?Length@VmSecurityDescriptor@Vml@@QEBAKXZ; Vml::VmSecurityDescriptor::Length(void)
0x14015cd07  mov     [rsp+1C8h+dwLegacyKeySpec], 80000044h; dwFlags
0x14015cd0f  mov     r9d, eax; cbInput
0x14015cd12  mov     r8, rdi; pbInput
0x14015cd15  mov     rdx, r14; pszProperty
0x14015cd18  mov     rcx, [rsp+1C8h+phKey]
0x14015cd20  mov     rcx, [rcx]; hObject
0x14015cd23  call    cs:__imp_NCryptSetProperty
0x14015cd2a  nop     dword ptr [rax+rax+00h]
0x14015cd2f  test    eax, eax
0x14015cd31  jz      short loc_14015CD3D
0x14015cd33  mov     edx, 74Dh
0x14015cd38  jmp     loc_14015CC26
0x14015cd3d  mov     dword ptr [rsp+1C8h+pbInput], 800h
0x14015cd48  mov     [rsp+1C8h+dwLegacyKeySpec], 0; dwFlags
0x14015cd50  mov     r9d, 4; cbInput
0x14015cd56  lea     r8, [rsp+1C8h+pbInput]; pbInput
0x14015cd5e  lea     rdx, aLength; "Length"
0x14015cd65  mov     rcx, [rsp+1C8h+phKey]
0x14015cd6d  mov     rcx, [rcx]; hObject
0x14015cd70  call    cs:__imp_NCryptSetProperty
0x14015cd77  nop     dword ptr [rax+rax+00h]
0x14015cd7c  test    eax, eax
0x14015cd7e  jz      short loc_14015CD8A
0x14015cd80  mov     edx, 754h
0x14015cd85  jmp     loc_14015CC26
0x14015cd8a  mov     edx, 240h; dwFlags
0x14015cd8f  mov     rcx, [rsp+1C8h+phKey]
0x14015cd97  mov     rcx, [rcx]; hKey
0x14015cd9a  call    cs:__imp_NCryptFinalizeKey
0x14015cda1  nop     dword ptr [rax+rax+00h]
0x14015cda6  test    eax, eax
0x14015cda8  jz      short loc_14015CDB4
0x14015cdaa  mov     edx, 75Bh
0x14015cdaf  jmp     loc_14015CC26
0x14015cdb4  mov     rcx, [rsp+1C8h+hMem]; hMem
0x14015cdbc  test    rcx, rcx
0x14015cdbf  jz      short loc_14015CDCE
0x14015cdc1  call    cs:__imp_LocalFree
0x14015cdc8  nop     dword ptr [rax+rax+00h]
0x14015cdcd  nop
0x14015cdce  test    rdi, rdi
0x14015cdd1  jz      short loc_14015CDE3
0x14015cdd3  mov     rcx, rdi; hMem
0x14015cdd6  call    cs:__imp_LocalFree
0x14015cddd  nop     dword ptr [rax+rax+00h]
0x14015cde2  nop
0x14015cde3  lea     rcx, [rsp+1C8h+var_168]; this
0x14015cde8  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cded  nop
0x14015cdee  lea     rcx, [rsp+1C8h+var_88]; this
0x14015cdf6  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015cdfb  nop
0x14015cdfc  lea     rcx, [rsp+1C8h+var_D8]; this
0x14015ce04  call    ??1VmSid@Vml@@QEAA@XZ; Vml::VmSid::~VmSid(void)
0x14015ce09  nop
0x14015ce0a  xor     eax, eax
0x14015ce0c  mov     rcx, [rsp+1C8h+var_38]
0x14015ce14  xor     rcx, rsp; StackCookie
0x14015ce17  call    __security_check_cookie
0x14015ce1c  add     rsp, 1A0h
0x14015ce23  pop     r15
0x14015ce25  pop     r14
0x14015ce27  pop     r13
0x14015ce29  pop     rdi
0x14015ce2a  pop     rsi
0x14015ce2b  retn
  ... truncated ...
```
