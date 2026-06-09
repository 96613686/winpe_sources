# ComputeService::ContainerCredentials::Details::CheckExtraCredentialSpecs(ushort const *)

- ea: `0x1400df380`
- end: `0x1400df4dd`
- name: `?CheckExtraCredentialSpecs@Details@ContainerCredentials@ComputeService@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z`
- size: `349`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400df4e4`

## callees

- `0x140005360`
- `0x1400341ac`
- `0x1400d106c`
- `0x1400df380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400df46d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400df484`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400df46d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400df484`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400df3fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400df42d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400df3fb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400df42d`

## string_xrefs

- `0x1400df4b2`: `onecore\vm\common\vml\VmRegistry.h`
- `0x1400df4cb`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall ComputeService::ContainerCredentials::Details::CheckExtraCredentialSpecs(
        _QWORD *a1,
        unsigned __int16 *a2)
{
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-40h]
  unsigned int phkResulta; // [rsp+20h] [rbp-40h]
  HKEY v9; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+8h]

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 7;
  *(_WORD *)a1 = 0;
  hKey = 0;
  v9 = 0;
  v4 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
         0,
         0xF003Fu,
         &hKey);
  if ( v4 )
  {
    if ( v4 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v4,
        phkResult);
  }
  else
  {
    v5 = RegOpenKeyExW(hKey, L"Containers\\Credentials", 0, 0x20019u, &v9);
    if ( v5 )
    {
      if ( v5 != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F9,
          (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
          (const char *)v5,
          phkResulta);
    }
    else if ( !(unsigned int)Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&v9, a2, a1) )
    {
      Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&v9, 0, a1);
    }
  }
  if ( v9 )
  {
    RegCloseKey(v9);
    v9 = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x1400df380  mov     [rsp-8+arg_10], rbx
0x1400df385  mov     [rsp-8+arg_18], rdi
0x1400df38a  push    rbp
0x1400df38b  mov     rbp, rsp
0x1400df38e  sub     rsp, 60h
0x1400df392  mov     rax, cs:__security_cookie
0x1400df399  xor     rax, rsp
0x1400df39c  mov     [rbp+var_10], rax
0x1400df3a0  mov     rdi, rdx
0x1400df3a3  mov     rbx, rcx
0x1400df3a6  mov     [rbp+var_28], rcx
0x1400df3aa  mov     [rbp+var_30], 0
0x1400df3b1  xorps   xmm0, xmm0
0x1400df3b4  movups  xmmword ptr [rcx], xmm0
0x1400df3b7  mov     qword ptr [rcx+10h], 0
0x1400df3bf  mov     qword ptr [rcx+18h], 7
0x1400df3c7  xor     eax, eax
0x1400df3c9  mov     [rcx], ax
0x1400df3cc  mov     [rbp+var_30], 1
0x1400df3d3  mov     [rbp+hKey], rax
0x1400df3d7  mov     [rbp+var_20], rax
0x1400df3db  lea     rax, [rbp+hKey]
0x1400df3df  mov     qword ptr [rsp+60h+phkResult], rax; unsigned int
0x1400df3e4  mov     r9d, 0F003Fh; samDesired
0x1400df3ea  xor     r8d, r8d; ulOptions
0x1400df3ed  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1400df3f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400df3fb  call    cs:__imp_RegOpenKeyExW
0x1400df401  test    eax, eax
0x1400df403  jz      short loc_1400DF410
0x1400df405  cmp     eax, 2
0x1400df408  jnz     loc_1400DF4AB
0x1400df40e  jmp     short loc_1400DF464
0x1400df410  lea     rax, [rbp+var_20]
0x1400df414  mov     qword ptr [rsp+60h+phkResult], rax; unsigned int
0x1400df419  mov     r9d, 20019h; samDesired
0x1400df41f  xor     r8d, r8d; ulOptions
0x1400df422  lea     rdx, aContainersCred; "Containers\\Credentials"
0x1400df429  mov     rcx, [rbp+hKey]; hKey
0x1400df42d  call    cs:__imp_RegOpenKeyExW
0x1400df433  test    eax, eax
0x1400df435  jz      short loc_1400DF442
0x1400df437  cmp     eax, 2
0x1400df43a  jnz     loc_1400DF4C4
0x1400df440  jmp     short loc_1400DF464
0x1400df442  mov     r8, rbx; void *
0x1400df445  mov     rdx, rdi; unsigned __int16 *
0x1400df448  lea     rcx, [rbp+var_20]; this
0x1400df44c  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x1400df451  test    eax, eax
0x1400df453  jnz     short loc_1400DF464
0x1400df455  mov     r8, rbx; void *
0x1400df458  xor     edx, edx; unsigned __int16 *
0x1400df45a  lea     rcx, [rbp+var_20]; this
0x1400df45e  call    ?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; Vml::VmRegistryKey::QueryValue(ushort const *,std::wstring &,bool)
0x1400df463  nop
0x1400df464  mov     rcx, [rbp+var_20]; hKey
0x1400df468  test    rcx, rcx
0x1400df46b  jz      short loc_1400DF47B
0x1400df46d  call    cs:__imp_RegCloseKey
0x1400df473  mov     [rbp+var_20], 0
0x1400df47b  mov     rcx, [rbp+hKey]; hKey
0x1400df47f  test    rcx, rcx
0x1400df482  jz      short loc_1400DF48A
0x1400df484  call    cs:__imp_RegCloseKey
0x1400df48a  mov     rax, rbx
0x1400df48d  mov     rcx, [rbp+var_10]
0x1400df491  xor     rcx, rsp; StackCookie
0x1400df494  call    __security_check_cookie
0x1400df499  lea     r11, [rsp+60h+var_s0]
0x1400df49e  mov     rbx, [r11+20h]
0x1400df4a2  mov     rdi, [r11+28h]
0x1400df4a6  mov     rsp, r11
0x1400df4a9  pop     rbp
0x1400df4aa  retn
0x1400df4ab  mov     rcx, [rbp+8]; this
0x1400df4af  mov     r9d, eax; char *
0x1400df4b2  lea     r8, aOnecoreVmCommo_14; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400df4b9  mov     edx, 1F9h; void *
0x1400df4be  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400df4c4  mov     rcx, [rbp+8]; this
0x1400df4c8  mov     r9d, eax; char *
0x1400df4cb  lea     r8, aOnecoreVmCommo_14; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x1400df4d2  mov     edx, 1F9h; void *
0x1400df4d7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
