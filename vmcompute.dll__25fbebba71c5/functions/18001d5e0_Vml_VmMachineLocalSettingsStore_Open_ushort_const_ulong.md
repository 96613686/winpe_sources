# Vml::VmMachineLocalSettingsStore::Open(ushort const *,ulong)

- ea: `0x18001d5e0`
- end: `0x18001d72f`
- name: `?Open@VmMachineLocalSettingsStore@Vml@@UEAA_NPEBGK@Z`
- size: `335`
- prototype: `bool(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002f50`
- `0x180014754`
- `0x18001d5e0`
- `0x180022d10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d6b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d629`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d6b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d64c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d66b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d64c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d66b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d6d4`

## string_xrefs

- `0x18001d703`: `onecore\vm\common\vml\VmRegistry.h`
- `0x18001d71d`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Vml::VmMachineLocalSettingsStore::Open(
        Vml::VmMachineLocalSettingsStore *this,
        unsigned __int16 *a2,
        REGSAM a3)
{
  unsigned int v6; // eax
  HKEY v8; // rcx
  __int64 *v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // eax
  bool v12; // bl
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
    v8 = (HKEY)*((_QWORD *)this + 1);
    if ( v8 )
    {
      RegCloseKey(v8);
      *((_QWORD *)this + 1) = 0;
    }
    v9 = &qword_18008E1B0;
    if ( a2 )
      v9 = (__int64 *)a2;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    std::wstring::_Assign<unsigned short>((char *)this + 16, v9, v10);
    v11 = RegOpenKeyExW(hKey, a2, 0, a3, (PHKEY)this + 1);
    if ( (v11 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v11,
        phkResulta);
    v12 = v11 == 0;
    if ( hKey )
      RegCloseKey(hKey);
    return v12;
  }
}

```

## disassembly

```asm
0x18001d5e0  push    rbx
0x18001d5e2  push    rbp
0x18001d5e3  push    rsi
0x18001d5e4  push    rdi
0x18001d5e5  push    r14
0x18001d5e7  sub     rsp, 40h
0x18001d5eb  mov     rax, cs:__security_cookie
0x18001d5f2  xor     rax, rsp
0x18001d5f5  mov     [rsp+68h+var_30], rax
0x18001d5fa  mov     ebp, r8d
0x18001d5fd  mov     rdi, rdx
0x18001d600  mov     rsi, rcx
0x18001d603  xor     r14d, r14d
0x18001d606  mov     [rsp+68h+hKey], r14
0x18001d60b  lea     rax, [rsp+68h+hKey]
0x18001d610  mov     qword ptr [rsp+68h+phkResult], rax; unsigned int
0x18001d615  mov     r9d, r8d; samDesired
0x18001d618  xor     r8d, r8d; ulOptions
0x18001d61b  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001d622  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d629  call    cs:__imp_RegOpenKeyExW
0x18001d630  nop     dword ptr [rax+rax+00h]
0x18001d635  test    eax, eax
0x18001d637  jz      short loc_18001D65F
0x18001d639  cmp     eax, 2
0x18001d63c  jnz     loc_18001D715
0x18001d642  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d647  test    rcx, rcx
0x18001d64a  jz      short loc_18001D658
0x18001d64c  call    cs:__imp_RegCloseKey
0x18001d653  nop     dword ptr [rax+rax+00h]
0x18001d658  xor     al, al
0x18001d65a  jmp     loc_18001D6E2
0x18001d65f  lea     rbx, [rsi+8]
0x18001d663  mov     rcx, [rbx]; hKey
0x18001d666  test    rcx, rcx
0x18001d669  jz      short loc_18001D67A
0x18001d66b  call    cs:__imp_RegCloseKey
0x18001d672  nop     dword ptr [rax+rax+00h]
0x18001d677  mov     [rbx], r14
0x18001d67a  lea     rdx, qword_18008E1B0
0x18001d681  test    rdi, rdi
0x18001d684  cmovnz  rdx, rdi
0x18001d688  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001d68c  inc     r8
0x18001d68f  cmp     [rdx+r8*2], r14w
0x18001d694  jnz     short loc_18001D68C
0x18001d696  lea     rcx, [rsi+10h]
0x18001d69a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001d69f  mov     qword ptr [rsp+68h+phkResult], rbx; unsigned int
0x18001d6a4  mov     r9d, ebp; samDesired
0x18001d6a7  xor     r8d, r8d; ulOptions
0x18001d6aa  mov     rdx, rdi; lpSubKey
0x18001d6ad  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d6b2  call    cs:__imp_RegOpenKeyExW
0x18001d6b9  nop     dword ptr [rax+rax+00h]
0x18001d6be  test    eax, 0FFFFFFFDh
0x18001d6c3  jnz     short loc_18001D6FB
0x18001d6c5  test    eax, eax
0x18001d6c7  setz    bl
0x18001d6ca  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d6cf  test    rcx, rcx
0x18001d6d2  jz      short loc_18001D6E0
0x18001d6d4  call    cs:__imp_RegCloseKey
0x18001d6db  nop     dword ptr [rax+rax+00h]
0x18001d6e0  mov     al, bl
0x18001d6e2  mov     rcx, [rsp+68h+var_30]
0x18001d6e7  xor     rcx, rsp; StackCookie
0x18001d6ea  call    __security_check_cookie
0x18001d6ef  add     rsp, 40h
0x18001d6f3  pop     r14
0x18001d6f5  pop     rdi
0x18001d6f6  pop     rsi
0x18001d6f7  pop     rbp
0x18001d6f8  pop     rbx
0x18001d6f9  retn
0x18001d6fb  mov     rcx, [rsp+68h]; this
0x18001d700  mov     r9d, eax; char *
0x18001d703  lea     r8, aOnecoreVmCommo_14; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001d70a  mov     edx, 1F9h; void *
0x18001d70f  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001d715  mov     rcx, [rsp+68h]; this
0x18001d71a  mov     r9d, eax; char *
0x18001d71d  lea     r8, aOnecoreVmCommo_14; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001d724  mov     edx, 1F9h; void *
0x18001d729  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
