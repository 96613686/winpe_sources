# PublisherManifestTdhConfig::ReadConfig(_GUID const &)

- ea: `0x180009570`
- end: `0x180009618`
- name: `?ReadConfig@PublisherManifestTdhConfig@@UEAAKAEBU_GUID@@@Z`
- size: `168`
- prototype: `unsigned int __fastcall(wchar_t **this, const struct _GUID *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800087c8`
- `0x180008970`
- `0x180009620`
- `0x180018484`
- `0x180026ba8`

## callees

- `0x180009570`
- `0x180009710`
- `0x18001ee20`
- `0x18002bc2c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x1800095cb`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800095cb`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800095ac`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800095ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int __fastcall PublisherManifestTdhConfig::ReadConfig(wchar_t **this, const struct _GUID *a2)
{
  unsigned int Config; // edi
  struct TDH_CACHE *v5; // rcx
  struct TDH_PROVIDER_BINARY_ENTRY *v6; // rsi
  PublisherManifestConfig *v7; // rcx
  unsigned int result; // eax

  Config = PublisherManifestConfig::ReadConfig((PublisherManifestConfig *)this, a2);
  if ( !Config && this[4] && this[2] )
    return Config;
  RtlAcquireSRWLockShared((char *)g_TdhCache + 0x4000);
  v6 = TdhpCacheLookupBinaryByGuid(v5, a2);
  RtlReleaseSRWLockShared((char *)g_TdhCache + 0x4000);
  if ( !v6 )
    return Config;
  if ( this[2] || (result = PublisherManifestConfig::SetStringMember(v7, (const wchar_t *)v6 + 16, this + 2)) == 0 )
  {
    if ( this[4] )
      return 0;
    else
      return PublisherManifestConfig::SetStringMember(v7, (const wchar_t *)v6 + 16, this + 4);
  }
  return result;
}

```

## disassembly

```asm
0x180009570  mov     [rsp+arg_0], rbx
0x180009575  mov     [rsp+arg_8], rsi
0x18000957a  push    rdi
0x18000957b  sub     rsp, 20h
0x18000957f  mov     rsi, rdx
0x180009582  mov     rbx, rcx
0x180009585  call    ?ReadConfig@PublisherManifestConfig@@UEAAKAEBU_GUID@@@Z; PublisherManifestConfig::ReadConfig(_GUID const &)
0x18000958a  mov     edi, eax
0x18000958c  test    eax, eax
0x18000958e  jnz     short loc_18000959E
0x180009590  cmp     qword ptr [rbx+20h], 0
0x180009595  jz      short loc_18000959E
0x180009597  cmp     qword ptr [rbx+10h], 0
0x18000959c  jnz     short loc_180009606
0x18000959e  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800095a5  add     rcx, 4000h
0x1800095ac  call    cs:__imp_RtlAcquireSRWLockShared
0x1800095b2  mov     rdx, rsi; struct _GUID *
0x1800095b5  call    ?TdhpCacheLookupBinaryByGuid@@YAPEAUTDH_PROVIDER_BINARY_ENTRY@@PEAUTDH_CACHE@@PEBU_GUID@@@Z; TdhpCacheLookupBinaryByGuid(TDH_CACHE *,_GUID const *)
0x1800095ba  mov     rcx, cs:?g_TdhCache@@3PEAUTDH_CACHE@@EA; TDH_CACHE * g_TdhCache
0x1800095c1  mov     rsi, rax
0x1800095c4  add     rcx, 4000h
0x1800095cb  call    cs:__imp_RtlReleaseSRWLockShared
0x1800095d1  test    rsi, rsi
0x1800095d4  jz      short loc_180009606
0x1800095d6  lea     r8, [rbx+10h]; wchar_t **
0x1800095da  cmp     qword ptr [r8], 0
0x1800095de  jnz     short loc_1800095ED
0x1800095e0  lea     rdx, [rsi+20h]; wchar_t *
0x1800095e4  call    ?SetStringMember@PublisherManifestConfig@@AEAAKPEB_WPEAPEA_W@Z; PublisherManifestConfig::SetStringMember(wchar_t const *,wchar_t * *)
0x1800095e9  test    eax, eax
0x1800095eb  jnz     short loc_180009608
0x1800095ed  lea     r8, [rbx+20h]; wchar_t **
0x1800095f1  cmp     qword ptr [r8], 0
0x1800095f5  jnz     short loc_180009602
0x1800095f7  lea     rdx, [rsi+20h]; wchar_t *
0x1800095fb  call    ?SetStringMember@PublisherManifestConfig@@AEAAKPEB_WPEAPEA_W@Z; PublisherManifestConfig::SetStringMember(wchar_t const *,wchar_t * *)
0x180009600  jmp     short loc_180009608
0x180009602  xor     eax, eax
0x180009604  jmp     short loc_180009608
0x180009606  mov     eax, edi
0x180009608  mov     rbx, [rsp+28h+arg_0]
0x18000960d  mov     rsi, [rsp+28h+arg_8]
0x180009612  add     rsp, 20h
0x180009616  pop     rdi
0x180009617  retn
```
