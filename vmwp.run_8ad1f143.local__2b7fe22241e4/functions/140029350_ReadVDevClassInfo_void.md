# ReadVDevClassInfo(void)

- ea: `0x140029350`
- end: `0x1400295f4`
- name: `?ReadVDevClassInfo@@YA?AV?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@XZ`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400dbf80`

## callees

- `0x140023f94`
- `0x140029350`
- `0x1400295fc`
- `0x140029744`
- `0x140029ba0`
- `0x140029d28`
- `0x14009d7cc`
- `0x1400d5d50`
- `0x140132960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400293c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400294db`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400293c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140029423`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400294db`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002953b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002959c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400295be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002953b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002959c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400295be`

## string_xrefs

- `0x1400293e6`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140029441`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400294f9`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_OWORD *__fastcall ReadVDevClassInfo(_OWORD *a1)
{
  unsigned int v2; // eax
  unsigned int v3; // eax
  unsigned int v4; // edi
  __m128i si128; // xmm6
  const unsigned __int16 *v6; // rdx
  const WCHAR *v7; // rdx
  unsigned int v8; // eax
  __int64 v9; // rax
  wil *v11; // rcx
  unsigned int v12; // eax
  LPCWSTR *v13; // r8
  unsigned int phkResult; // [rsp+20h] [rbp-98h]
  unsigned int phkResulta; // [rsp+20h] [rbp-98h]
  unsigned int phkResultb; // [rsp+20h] [rbp-98h]
  _BYTE v17[16]; // [rsp+40h] [rbp-78h] BYREF
  HKEY v18; // [rsp+50h] [rbp-68h] BYREF
  HKEY v19; // [rsp+58h] [rbp-60h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+60h] [rbp-58h] BYREF
  __m128i v21; // [rsp+70h] [rbp-48h]
  HKEY hKey; // [rsp+80h] [rbp-38h] BYREF
  _BYTE v23[16]; // [rsp+88h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  *a1 = 0;
  std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>();
  hKey = 0;
  v2 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
         0,
         0x20019u,
         &hKey);
  if ( (v2 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v2,
      phkResult);
  v18 = 0;
  v3 = RegOpenKeyExW(hKey, L"VirtualDevices", 0, 0x20019u, &v18);
  if ( (v3 & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v3,
      phkResulta);
  v4 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)lpSubKey = 0;
    v21 = si128;
    LOWORD(lpSubKey[0]) = 0;
    if ( !(unsigned int)Vml::VmRegistryKey::EnumKey(&v18, v4, lpSubKey) )
      break;
    v6 = (const unsigned __int16 *)lpSubKey;
    if ( v21.m128i_i64[1] > 7uLL )
      v6 = lpSubKey[0];
    try
    {
      Vml::VmGuid::Assign((Vml::VmGuid *)v23, v6);
      v19 = 0;
      v7 = (const WCHAR *)lpSubKey;
      if ( v21.m128i_i64[1] > 7uLL )
        v7 = lpSubKey[0];
      v8 = RegOpenKeyExW(v18, v7, 0, 0x20019u, &v19);
      if ( (v8 & 0xFFFFFFFD) != 0 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
          (const char *)v8,
          phkResultb);
      v9 = std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::_Try_emplace<_GUID const &,>(
             a1,
             v17,
             v23);
      ReadSingleVDevClassInfo((struct Vml::VmRegistryKey *)&v19, (struct VDevClassInfo *)(*(_QWORD *)v9 + 48LL));
      if ( v19 )
      {
        RegCloseKey(v19);
        v19 = 0;
      }
      if ( v21.m128i_i64[1] > 7uLL )
        std::_Deallocate<16>(lpSubKey[0], 2 * v21.m128i_i64[1] + 2);
      ++v4;
    }
    catch ( ... )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(0x4000) )
      {
        v12 = wil::ResultFromCaughtException(v11);
        v13 = lpSubKey;
        if ( v21.m128i_i64[1] > 7uLL )
          v13 = (LPCWSTR *)lpSubKey[0];
        VmlDebugTrace(0x4000, L"VDevRegistrar: Invalid registration data for device %s (error: 0x%08x)", v13, v12);
      }
      throw;
    }
  }
  if ( v21.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(lpSubKey[0], 2 * v21.m128i_i64[1] + 2);
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x140029350  mov     rax, rsp
0x140029353  mov     [rax+10h], rbx
0x140029357  push    rdi
0x140029358  sub     rsp, 0B0h
0x14002935f  movaps  xmmword ptr [rax-18h], xmm6
0x140029363  mov     rax, cs:__security_cookie
0x14002936a  xor     rax, rsp
0x14002936d  mov     [rsp+0B8h+var_20], rax
0x140029375  mov     rbx, rcx
0x140029378  mov     [rsp+0B8h+var_80], rcx
0x14002937d  mov     [rsp+0B8h+var_88], 0
0x140029385  xorps   xmm0, xmm0
0x140029388  movups  xmmword ptr [rcx], xmm0
0x14002938b  call    ??0?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@QEAA@XZ; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>(void)
0x140029390  mov     [rsp+0B8h+var_88], 1
0x140029398  mov     [rsp+0B8h+hKey], 0
0x1400293a4  lea     rax, [rsp+0B8h+hKey]
0x1400293ac  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x1400293b1  mov     r9d, 20019h; samDesired
0x1400293b7  xor     r8d, r8d; ulOptions
0x1400293ba  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400293c1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400293c8  call    cs:__imp_RegOpenKeyExW
0x1400293cf  nop     dword ptr [rax+rax+00h]
0x1400293d4  test    eax, 0FFFFFFFDh
0x1400293d9  jz      short loc_1400293F8
0x1400293db  mov     rcx, [rsp+0B8h]; this
0x1400293e3  mov     r9d, eax; char *
0x1400293e6  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400293ed  mov     edx, 1F9h; void *
0x1400293f2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400293f8  mov     [rsp+0B8h+var_68], 0
0x140029401  lea     rax, [rsp+0B8h+var_68]
0x140029406  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x14002940b  mov     r9d, 20019h; samDesired
0x140029411  xor     r8d, r8d; ulOptions
0x140029414  lea     rdx, SubKey; "VirtualDevices"
0x14002941b  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140029423  call    cs:__imp_RegOpenKeyExW
0x14002942a  nop     dword ptr [rax+rax+00h]
0x14002942f  test    eax, 0FFFFFFFDh
0x140029434  jz      short loc_140029453
0x140029436  mov     rcx, [rsp+0B8h]; this
0x14002943e  mov     r9d, eax; char *
0x140029441  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140029448  mov     edx, 1F9h; void *
0x14002944d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140029453  xor     edi, edi
0x140029455  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x14002945d  xorps   xmm0, xmm0
0x140029460  movups  xmmword ptr [rsp+0B8h+lpSubKey], xmm0
0x140029465  movdqu  [rsp+0B8h+var_48], xmm6
0x14002946b  xor     eax, eax
0x14002946d  mov     word ptr [rsp+0B8h+lpSubKey], ax
0x140029472  lea     r8, [rsp+0B8h+lpSubKey]
0x140029477  mov     edx, edi
0x140029479  lea     rcx, [rsp+0B8h+var_68]
0x14002947e  call    ?EnumKey@VmRegistryKey@Vml@@QEBAHKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Vml::VmRegistryKey::EnumKey(ulong,std::wstring &)
0x140029483  test    eax, eax
0x140029485  jz      loc_140029574
0x14002948b  lea     rdx, [rsp+0B8h+lpSubKey]
0x140029490  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x140029496  cmova   rdx, [rsp+0B8h+lpSubKey]; unsigned __int16 *
0x14002949c  lea     rcx, [rsp+0B8h+var_30]; this
0x1400294a4  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x1400294a9  mov     [rsp+0B8h+var_60], 0
0x1400294b2  lea     rdx, [rsp+0B8h+lpSubKey]
0x1400294b7  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x1400294bd  cmova   rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x1400294c3  lea     rax, [rsp+0B8h+var_60]
0x1400294c8  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x1400294cd  mov     r9d, 20019h; samDesired
0x1400294d3  xor     r8d, r8d; ulOptions
0x1400294d6  mov     rcx, [rsp+0B8h+var_68]; hKey
0x1400294db  call    cs:__imp_RegOpenKeyExW
0x1400294e2  nop     dword ptr [rax+rax+00h]
0x1400294e7  test    eax, 0FFFFFFFDh
0x1400294ec  jz      short loc_14002950A
0x1400294ee  mov     rcx, [rsp+0B8h]; this
0x1400294f6  mov     r9d, eax; char *
0x1400294f9  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140029500  mov     edx, 1F9h; void *
0x140029505  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x14002950a  lea     r8, [rsp+0B8h+var_30]
0x140029512  lea     rdx, [rsp+0B8h+var_78]
0x140029517  mov     rcx, rbx
0x14002951a  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x14002951f  mov     rdx, [rax]
0x140029522  add     rdx, 30h ; '0'; struct VDevClassInfo *
0x140029526  lea     rcx, [rsp+0B8h+var_60]; struct Vml::VmRegistryKey *
0x14002952b  call    ?ReadSingleVDevClassInfo@@YAXAEAVVmRegistryKey@Vml@@PEAUVDevClassInfo@@@Z; ReadSingleVDevClassInfo(Vml::VmRegistryKey &,VDevClassInfo *)
0x140029530  nop
0x140029531  mov     rcx, [rsp+0B8h+var_60]; hKey
0x140029536  test    rcx, rcx
0x140029539  jz      short loc_140029550
0x14002953b  call    cs:__imp_RegCloseKey
0x140029542  nop     dword ptr [rax+rax+00h]
0x140029547  mov     [rsp+0B8h+var_60], 0
0x140029550  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140029555  cmp     rdx, 7
0x140029559  jbe     short loc_14002956D
0x14002955b  lea     rdx, ds:2[rdx*2]
0x140029563  mov     rcx, [rsp+0B8h+lpSubKey]
0x140029568  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14002956d  inc     edi
0x14002956f  jmp     loc_14002945D
0x140029574  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140029579  cmp     rdx, 7
0x14002957d  jbe     short loc_140029592
0x14002957f  lea     rdx, ds:2[rdx*2]
0x140029587  mov     rcx, [rsp+0B8h+lpSubKey]
0x14002958c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140029591  nop
0x140029592  mov     rcx, [rsp+0B8h+var_68]; hKey
0x140029597  test    rcx, rcx
0x14002959a  jz      short loc_1400295B1
0x14002959c  call    cs:__imp_RegCloseKey
0x1400295a3  nop     dword ptr [rax+rax+00h]
0x1400295a8  mov     [rsp+0B8h+var_68], 0
0x1400295b1  mov     rcx, [rsp+0B8h+hKey]; hKey
0x1400295b9  test    rcx, rcx
0x1400295bc  jz      short loc_1400295CA
0x1400295be  call    cs:__imp_RegCloseKey
0x1400295c5  nop     dword ptr [rax+rax+00h]
0x1400295ca  mov     rax, rbx
0x1400295cd  mov     rcx, [rsp+0B8h+var_20]
0x1400295d5  xor     rcx, rsp; StackCookie
0x1400295d8  call    __security_check_cookie
0x1400295dd  lea     r11, [rsp+0B8h+var_8]
0x1400295e5  mov     rbx, [r11+18h]
0x1400295e9  movaps  xmm6, xmmword ptr [r11-10h]
0x1400295ee  mov     rsp, r11
0x1400295f1  pop     rdi
0x1400295f2  retn
```
