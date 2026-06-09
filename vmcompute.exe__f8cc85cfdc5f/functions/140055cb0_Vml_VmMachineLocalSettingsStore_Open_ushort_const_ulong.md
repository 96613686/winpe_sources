# Vml::VmMachineLocalSettingsStore::Open(ushort const *,ulong)

- ea: `0x140055cb0`
- end: `0x140055dfc`
- name: `?Open@VmMachineLocalSettingsStore@Vml@@UEAA_NPEBGK@Z`
- size: `332`
- prototype: `bool(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140055cb0`
- `0x1400bc830`
- `0x1400c4154`
- `0x1401332f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055cf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055d60`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055cf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140055d60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055d19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055d82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055dec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055d19`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055d82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140055dec`

## string_xrefs

- `0x140055db6`: `onecore\vm\common\vml\VmRegistry.h`
- `0x140055dd0`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Vml::VmMachineLocalSettingsStore::Open(
        Vml::VmMachineLocalSettingsStore *this,
        const unsigned __int16 *a2,
        REGSAM a3)
{
  unsigned int v6; // eax
  HKEY v7; // rcx
  const WCHAR *v8; // rdx
  __int64 v9; // r8
  unsigned int v10; // eax
  bool v11; // bl
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
         0,
         a3,
         &hKey);
  if ( v6 )
  {
    if ( v6 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v6,
        phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v7 = (HKEY)*((_QWORD *)this + 1);
    if ( v7 )
    {
      RegCloseKey(v7);
      *((_QWORD *)this + 1) = 0;
    }
    v8 = &szPassword;
    if ( a2 )
      v8 = a2;
    v9 = -1;
    do
      ++v9;
    while ( v8[v9] );
    std::wstring::_Assign<unsigned short>((char *)this + 16);
    v10 = RegOpenKeyExW(hKey, a2, 0, a3, (PHKEY)this + 1);
    if ( (v10 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v10,
        phkResulta);
    v11 = v10 == 0;
    if ( hKey )
      RegCloseKey(hKey);
    return v11;
  }
}

```

## disassembly

```asm
0x140055cb0  push    rbx
0x140055cb2  push    rbp
0x140055cb3  push    rsi
0x140055cb4  push    rdi
0x140055cb5  push    r14
0x140055cb7  sub     rsp, 40h
0x140055cbb  mov     rax, cs:__security_cookie
0x140055cc2  xor     rax, rsp
0x140055cc5  mov     [rsp+68h+var_30], rax
0x140055cca  mov     ebp, r8d
0x140055ccd  mov     rdi, rdx
0x140055cd0  mov     rsi, rcx
0x140055cd3  xor     r14d, r14d
0x140055cd6  mov     [rsp+68h+hKey], r14
0x140055cdb  lea     rax, [rsp+68h+hKey]
0x140055ce0  mov     qword ptr [rsp+68h+phkResult], rax; unsigned int
0x140055ce5  mov     r9d, r8d; samDesired
0x140055ce8  xor     r8d, r8d; ulOptions
0x140055ceb  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x140055cf2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140055cf9  call    cs:__imp_RegOpenKeyExW
0x140055d00  nop     dword ptr [rax+rax+00h]
0x140055d05  test    eax, eax
0x140055d07  jnz     loc_140055DA9
0x140055d0d  lea     rbx, [rsi+8]
0x140055d11  mov     rcx, [rbx]; hKey
0x140055d14  test    rcx, rcx
0x140055d17  jz      short loc_140055D28
0x140055d19  call    cs:__imp_RegCloseKey
0x140055d20  nop     dword ptr [rax+rax+00h]
0x140055d25  mov     [rbx], r14
0x140055d28  lea     rdx, szPassword
0x140055d2f  test    rdi, rdi
0x140055d32  cmovnz  rdx, rdi
0x140055d36  or      r8, 0FFFFFFFFFFFFFFFFh
0x140055d3a  inc     r8
0x140055d3d  cmp     [rdx+r8*2], r14w
0x140055d42  jnz     short loc_140055D3A
0x140055d44  lea     rcx, [rsi+10h]
0x140055d48  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x140055d4d  mov     qword ptr [rsp+68h+phkResult], rbx; unsigned int
0x140055d52  mov     r9d, ebp; samDesired
0x140055d55  xor     r8d, r8d; ulOptions
0x140055d58  mov     rdx, rdi; lpSubKey
0x140055d5b  mov     rcx, [rsp+68h+hKey]; hKey
0x140055d60  call    cs:__imp_RegOpenKeyExW
0x140055d67  nop     dword ptr [rax+rax+00h]
0x140055d6c  test    eax, 0FFFFFFFDh
0x140055d71  jnz     short loc_140055DC8
0x140055d73  test    eax, eax
0x140055d75  setz    bl
0x140055d78  mov     rcx, [rsp+68h+hKey]; hKey
0x140055d7d  test    rcx, rcx
0x140055d80  jz      short loc_140055D8E
0x140055d82  call    cs:__imp_RegCloseKey
0x140055d89  nop     dword ptr [rax+rax+00h]
0x140055d8e  mov     al, bl
0x140055d90  mov     rcx, [rsp+68h+var_30]
0x140055d95  xor     rcx, rsp; StackCookie
0x140055d98  call    __security_check_cookie
0x140055d9d  add     rsp, 40h
0x140055da1  pop     r14
0x140055da3  pop     rdi
0x140055da4  pop     rsi
0x140055da5  pop     rbp
0x140055da6  pop     rbx
0x140055da7  retn
0x140055da9  cmp     eax, 2
0x140055dac  jz      short loc_140055DE2
0x140055dae  mov     rcx, [rsp+68h]; this
0x140055db3  mov     r9d, eax; char *
0x140055db6  lea     r8, aOnecoreVmCommo_65; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140055dbd  mov     edx, 1F9h; void *
0x140055dc2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140055dc8  mov     rcx, [rsp+68h]; this
0x140055dcd  mov     r9d, eax; char *
0x140055dd0  lea     r8, aOnecoreVmCommo_65; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x140055dd7  mov     edx, 1F9h; void *
0x140055ddc  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140055de2  mov     rcx, [rsp+68h+hKey]; hKey
0x140055de7  test    rcx, rcx
0x140055dea  jz      short loc_140055DF8
0x140055dec  call    cs:__imp_RegCloseKey
0x140055df3  nop     dword ptr [rax+rax+00h]
0x140055df8  xor     al, al
0x140055dfa  jmp     short loc_140055D90
```
