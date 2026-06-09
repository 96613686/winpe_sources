# CSWbemLocator::GetDefaultNamespace(void)

- ea: `0x180015078`
- end: `0x18001523a`
- name: `?GetDefaultNamespace@CSWbemLocator@@CAPEBGXZ`
- size: `450`
- prototype: `const unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800045c0`

## callees

- `0x180015078`
- `0x180015240`
- `0x180018460`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001510d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015176`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001510d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180015176`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800150d8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150c6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800150c6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015136`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800151ab`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001520f`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x180015136`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800151ab`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x18001520f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
unsigned __int16 *CSWbemLocator::GetDefaultNamespace(void)
{
  unsigned __int16 *v0; // r11
  HKEY v1; // rdi
  unsigned __int16 *v2; // rbx
  __int64 v3; // rax
  unsigned __int64 v4; // r14
  unsigned __int16 *v5; // rax
  unsigned __int16 *v7; // rax
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+38h] BYREF

  v0 = CSWbemLocator::s_pDefaultNamespace;
  if ( !CSWbemLocator::s_pDefaultNamespace )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wbem\\Scripting", 0, 1u, &hKey) )
    {
      v1 = hKey;
      cbData = 0;
      if ( !RegQueryValueExW(hKey, L"Default Namespace", 0, 0, 0, &cbData) )
      {
        v2 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(((unsigned __int64)cbData >> 1) + 1, 2u));
        if ( v2 )
        {
          if ( !RegQueryValueExW(hKey, L"Default Namespace", 0, 0, (LPBYTE)v2, &cbData) )
          {
            v2[(unsigned __int64)cbData >> 1] = 0;
            v3 = -1;
            do
              ++v3;
            while ( v2[v3] );
            v4 = (unsigned int)(v3 + 1);
            v5 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(v4, 2u));
            CSWbemLocator::s_pDefaultNamespace = v5;
            if ( v5 )
              StringCchCopyW(v5, v4, v2);
          }
        }
        deleteArray<unsigned short>(v2);
      }
      ((void (__fastcall *)(HKEY))RegCloseKey)(v1);
    }
    v0 = CSWbemLocator::s_pDefaultNamespace;
    if ( !CSWbemLocator::s_pDefaultNamespace )
    {
      v7 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(0x16u);
      v0 = v7;
      CSWbemLocator::s_pDefaultNamespace = v7;
      if ( v7 )
        StringCchCopyW(v7, 0xBu, L"root\\cimv2");
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180015078  mov     [rsp-28h+arg_10], rbx
0x18001507d  mov     [rsp-28h+arg_18], rsi
0x180015082  push    rbp
0x180015083  push    rdi
0x180015084  push    r12
0x180015086  push    r14
0x180015088  push    r15
0x18001508a  mov     rbp, rsp
0x18001508d  sub     rsp, 60h
0x180015091  mov     r11, cs:?s_pDefaultNamespace@CSWbemLocator@@0PEAGEA; ushort * CSWbemLocator::s_pDefaultNamespace
0x180015098  xor     r15d, r15d
0x18001509b  test    r11, r11
0x18001509e  jnz     loc_1800151DE
0x1800150a4  mov     [rbp+hKey], r15
0x1800150a8  lea     rax, [rbp+hKey]
0x1800150ac  mov     [rsp+60h+phkResult], rax; phkResult
0x1800150b1  lea     r9d, [r11+1]; samDesired
0x1800150b5  xor     r8d, r8d; ulOptions
0x1800150b8  lea     rdx, SubKey; "Software\\Microsoft\\Wbem\\Scripting"
0x1800150bf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800150c6  call    cs:__imp_RegOpenKeyExW
0x1800150cc  test    eax, eax
0x1800150ce  jnz     loc_1800151D2
0x1800150d4  mov     rdi, [rbp+hKey]
0x1800150d8  mov     rsi, cs:__imp_RegCloseKey
0x1800150df  mov     [rbp+var_30], r15b
0x1800150e3  mov     [rbp+var_28], rsi
0x1800150e7  mov     [rbp+var_20], rdi
0x1800150eb  mov     [rbp+cbData], r15d
0x1800150ef  lea     rax, [rbp+cbData]
0x1800150f3  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1800150f8  mov     [rsp+60h+phkResult], r15; lpData
0x1800150fd  xor     r9d, r9d; lpType
0x180015100  xor     r8d, r8d; lpReserved
0x180015103  lea     rdx, aDefaultNamespa; "Default Namespace"
0x18001510a  mov     rcx, rdi; hKey
0x18001510d  call    cs:__imp_RegQueryValueExW
0x180015113  test    eax, eax
0x180015115  jnz     loc_1800151C6
0x18001511b  mov     ecx, [rbp+cbData]
0x18001511e  shr     rcx, 1
0x180015121  inc     rcx
0x180015124  lea     eax, [r15+2]
0x180015128  mul     rcx
0x18001512b  lea     r12, [r15-1]
0x18001512f  cmovb   rax, r12
0x180015133  mov     rcx, rax
0x180015136  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x18001513c  mov     rbx, rax
0x18001513f  mov     [rbp+var_18], r15b
0x180015143  lea     rax, ??$deleteArray@G@@YAXPEAG@Z; deleteArray<ushort>(ushort *)
0x18001514a  mov     [rbp+var_10], rax
0x18001514e  mov     [rbp+var_8], rbx
0x180015152  test    rbx, rbx
0x180015155  jz      short loc_1800151BD
0x180015157  lea     rax, [rbp+cbData]
0x18001515b  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180015160  mov     [rsp+60h+phkResult], rbx; lpData
0x180015165  xor     r9d, r9d; lpType
0x180015168  xor     r8d, r8d; lpReserved
0x18001516b  lea     rdx, aDefaultNamespa; "Default Namespace"
0x180015172  mov     rcx, [rbp+hKey]; hKey
0x180015176  call    cs:__imp_RegQueryValueExW
0x18001517c  test    eax, eax
0x18001517e  jnz     short loc_1800151BD
0x180015180  mov     ecx, [rbp+cbData]
0x180015183  shr     rcx, 1
0x180015186  mov     [rbx+rcx*2], r15w
0x18001518b  mov     rax, r12
0x18001518e  inc     rax
0x180015191  cmp     [rbx+rax*2], r15w
0x180015196  jnz     short loc_18001518E
0x180015198  lea     r14d, [rax+1]
0x18001519c  mov     eax, 2
0x1800151a1  mul     r14
0x1800151a4  cmovb   rax, r12
0x1800151a8  mov     rcx, rax
0x1800151ab  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800151b1  mov     cs:?s_pDefaultNamespace@CSWbemLocator@@0PEAGEA, rax; ushort * CSWbemLocator::s_pDefaultNamespace
0x1800151b8  test    rax, rax
0x1800151bb  jnz     short loc_1800151FA
0x1800151bd  mov     rcx, rbx
0x1800151c0  call    ??$deleteArray@G@@YAXPEAG@Z; deleteArray<ushort>(ushort *)
0x1800151c5  nop
0x1800151c6  mov     rcx, rdi
0x1800151c9  mov     rax, rsi
0x1800151cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151d1  nop
0x1800151d2  mov     r11, cs:?s_pDefaultNamespace@CSWbemLocator@@0PEAGEA; ushort * CSWbemLocator::s_pDefaultNamespace
0x1800151d9  test    r11, r11
0x1800151dc  jz      short loc_18001520A
0x1800151de  mov     rax, r11
0x1800151e1  lea     r11, [rsp+60h+var_s0]
0x1800151e6  mov     rbx, [r11+40h]
0x1800151ea  mov     rsi, [r11+48h]
0x1800151ee  mov     rsp, r11
0x1800151f1  pop     r15
0x1800151f3  pop     r14
0x1800151f5  pop     r12
0x1800151f7  pop     rdi
0x1800151f8  pop     rbp
0x1800151f9  retn
0x1800151fa  mov     r8, rbx; unsigned __int16 *
0x1800151fd  mov     rdx, r14; unsigned __int64
0x180015200  mov     rcx, rax; unsigned __int16 *
0x180015203  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015208  jmp     short loc_1800151BD
0x18001520a  mov     ecx, 16h
0x18001520f  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x180015215  mov     r11, rax
0x180015218  mov     cs:?s_pDefaultNamespace@CSWbemLocator@@0PEAGEA, rax; ushort * CSWbemLocator::s_pDefaultNamespace
0x18001521f  test    rax, rax
0x180015222  jz      short loc_1800151DE
0x180015224  lea     r8, aRootCimv2; "root\\cimv2"
0x18001522b  mov     edx, 0Bh; unsigned __int64
0x180015230  mov     rcx, rax; unsigned __int16 *
0x180015233  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015238  jmp     short loc_1800151DE
```
