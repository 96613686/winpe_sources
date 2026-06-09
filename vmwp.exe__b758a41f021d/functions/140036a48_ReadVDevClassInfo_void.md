# ReadVDevClassInfo(void)

- ea: `0x140036a48`
- end: `0x140036cec`
- name: `?ReadVDevClassInfo@@YA?AV?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@XZ`
- size: `676`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400cc3b0`

## callees

- `0x140024504`
- `0x140036a48`
- `0x140036cf4`
- `0x140036e3c`
- `0x140037298`
- `0x140037420`
- `0x1400ba144`
- `0x1400c2998`
- `0x14011ea40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036ac0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036b1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036bd3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036ac0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036b1b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140036bd3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036c33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036cb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036c33`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036c94`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140036cb6`

## string_xrefs

- `0x140036ade`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140036b39`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140036bf1`: `onecore\vm\common\vml\VmRegistry.h`

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
0x140036a48  mov     rax, rsp
0x140036a4b  mov     [rax+10h], rbx
0x140036a4f  push    rdi
0x140036a50  sub     rsp, 0B0h
0x140036a57  movaps  xmmword ptr [rax-18h], xmm6
0x140036a5b  mov     rax, cs:__security_cookie
0x140036a62  xor     rax, rsp
0x140036a65  mov     [rsp+0B8h+var_20], rax
0x140036a6d  mov     rbx, rcx
0x140036a70  mov     [rsp+0B8h+var_80], rcx
0x140036a75  mov     [rsp+0B8h+var_88], 0
0x140036a7d  xorps   xmm0, xmm0
0x140036a80  movups  xmmword ptr [rcx], xmm0
0x140036a83  call    ??0?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@QEAA@XZ; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>(void)
0x140036a88  mov     [rsp+0B8h+var_88], 1
0x140036a90  mov     [rsp+0B8h+hKey], 0
0x140036a9c  lea     rax, [rsp+0B8h+hKey]
0x140036aa4  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x140036aa9  mov     r9d, 20019h; samDesired
0x140036aaf  xor     r8d, r8d; ulOptions
0x140036ab2  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140036ab9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140036ac0  call    cs:__imp_RegOpenKeyExW
0x140036ac7  nop     dword ptr [rax+rax+00h]
0x140036acc  test    eax, 0FFFFFFFDh
0x140036ad1  jz      short loc_140036AF0
0x140036ad3  mov     rcx, [rsp+0B8h]; this
0x140036adb  mov     r9d, eax; char *
0x140036ade  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140036ae5  mov     edx, 1F9h; void *
0x140036aea  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140036af0  mov     [rsp+0B8h+var_68], 0
0x140036af9  lea     rax, [rsp+0B8h+var_68]
0x140036afe  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x140036b03  mov     r9d, 20019h; samDesired
0x140036b09  xor     r8d, r8d; ulOptions
0x140036b0c  lea     rdx, SubKey; "VirtualDevices"
0x140036b13  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140036b1b  call    cs:__imp_RegOpenKeyExW
0x140036b22  nop     dword ptr [rax+rax+00h]
0x140036b27  test    eax, 0FFFFFFFDh
0x140036b2c  jz      short loc_140036B4B
0x140036b2e  mov     rcx, [rsp+0B8h]; this
0x140036b36  mov     r9d, eax; char *
0x140036b39  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140036b40  mov     edx, 1F9h; void *
0x140036b45  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140036b4b  xor     edi, edi
0x140036b4d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x140036b55  xorps   xmm0, xmm0
0x140036b58  movups  xmmword ptr [rsp+0B8h+lpSubKey], xmm0
0x140036b5d  movdqu  [rsp+0B8h+var_48], xmm6
0x140036b63  xor     eax, eax
0x140036b65  mov     word ptr [rsp+0B8h+lpSubKey], ax
0x140036b6a  lea     r8, [rsp+0B8h+lpSubKey]
0x140036b6f  mov     edx, edi
0x140036b71  lea     rcx, [rsp+0B8h+var_68]
0x140036b76  call    ?EnumKey@VmRegistryKey@Vml@@QEBAHKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Vml::VmRegistryKey::EnumKey(ulong,std::wstring &)
0x140036b7b  test    eax, eax
0x140036b7d  jz      loc_140036C6C
0x140036b83  lea     rdx, [rsp+0B8h+lpSubKey]
0x140036b88  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x140036b8e  cmova   rdx, [rsp+0B8h+lpSubKey]; unsigned __int16 *
0x140036b94  lea     rcx, [rsp+0B8h+var_30]; this
0x140036b9c  call    ?Assign@VmGuid@Vml@@QEAAXQEBG@Z; Vml::VmGuid::Assign(ushort const * const)
0x140036ba1  mov     [rsp+0B8h+var_60], 0
0x140036baa  lea     rdx, [rsp+0B8h+lpSubKey]
0x140036baf  cmp     qword ptr [rsp+0B8h+var_48+8], 7
0x140036bb5  cmova   rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x140036bbb  lea     rax, [rsp+0B8h+var_60]
0x140036bc0  mov     qword ptr [rsp+0B8h+phkResult], rax; unsigned int
0x140036bc5  mov     r9d, 20019h; samDesired
0x140036bcb  xor     r8d, r8d; ulOptions
0x140036bce  mov     rcx, [rsp+0B8h+var_68]; hKey
0x140036bd3  call    cs:__imp_RegOpenKeyExW
0x140036bda  nop     dword ptr [rax+rax+00h]
0x140036bdf  test    eax, 0FFFFFFFDh
0x140036be4  jz      short loc_140036C02
0x140036be6  mov     rcx, [rsp+0B8h]; this
0x140036bee  mov     r9d, eax; char *
0x140036bf1  lea     r8, aOnecoreVmCommo_108; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140036bf8  mov     edx, 1F9h; void *
0x140036bfd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140036c02  lea     r8, [rsp+0B8h+var_30]
0x140036c0a  lea     rdx, [rsp+0B8h+var_78]
0x140036c0f  mov     rcx, rbx
0x140036c12  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UVDevClassInfo@@UGuidLess@Vml@@V?$allocator@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UVDevClassInfo@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,VDevClassInfo,Vml::GuidLess,std::allocator<std::pair<_GUID const,VDevClassInfo>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x140036c17  mov     rdx, [rax]
0x140036c1a  add     rdx, 30h ; '0'; struct VDevClassInfo *
0x140036c1e  lea     rcx, [rsp+0B8h+var_60]; struct Vml::VmRegistryKey *
0x140036c23  call    ?ReadSingleVDevClassInfo@@YAXAEAVVmRegistryKey@Vml@@PEAUVDevClassInfo@@@Z; ReadSingleVDevClassInfo(Vml::VmRegistryKey &,VDevClassInfo *)
0x140036c28  nop
0x140036c29  mov     rcx, [rsp+0B8h+var_60]; hKey
0x140036c2e  test    rcx, rcx
0x140036c31  jz      short loc_140036C48
0x140036c33  call    cs:__imp_RegCloseKey
0x140036c3a  nop     dword ptr [rax+rax+00h]
0x140036c3f  mov     [rsp+0B8h+var_60], 0
0x140036c48  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140036c4d  cmp     rdx, 7
0x140036c51  jbe     short loc_140036C65
0x140036c53  lea     rdx, ds:2[rdx*2]
0x140036c5b  mov     rcx, [rsp+0B8h+lpSubKey]
0x140036c60  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140036c65  inc     edi
0x140036c67  jmp     loc_140036B55
0x140036c6c  mov     rdx, qword ptr [rsp+0B8h+var_48+8]
0x140036c71  cmp     rdx, 7
0x140036c75  jbe     short loc_140036C8A
0x140036c77  lea     rdx, ds:2[rdx*2]
0x140036c7f  mov     rcx, [rsp+0B8h+lpSubKey]
0x140036c84  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140036c89  nop
0x140036c8a  mov     rcx, [rsp+0B8h+var_68]; hKey
0x140036c8f  test    rcx, rcx
0x140036c92  jz      short loc_140036CA9
0x140036c94  call    cs:__imp_RegCloseKey
0x140036c9b  nop     dword ptr [rax+rax+00h]
0x140036ca0  mov     [rsp+0B8h+var_68], 0
0x140036ca9  mov     rcx, [rsp+0B8h+hKey]; hKey
0x140036cb1  test    rcx, rcx
0x140036cb4  jz      short loc_140036CC2
0x140036cb6  call    cs:__imp_RegCloseKey
0x140036cbd  nop     dword ptr [rax+rax+00h]
0x140036cc2  mov     rax, rbx
0x140036cc5  mov     rcx, [rsp+0B8h+var_20]
0x140036ccd  xor     rcx, rsp; StackCookie
0x140036cd0  call    __security_check_cookie
0x140036cd5  lea     r11, [rsp+0B8h+var_8]
0x140036cdd  mov     rbx, [r11+18h]
0x140036ce1  movaps  xmm6, xmmword ptr [r11-10h]
0x140036ce6  mov     rsp, r11
0x140036ce9  pop     rdi
0x140036cea  retn
```
