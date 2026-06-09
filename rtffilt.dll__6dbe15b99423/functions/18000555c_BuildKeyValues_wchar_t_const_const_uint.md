# BuildKeyValues(wchar_t const * const *,uint)

- ea: `0x18000555c`
- end: `0x180005747`
- name: `?BuildKeyValues@@YAJPEBQEB_WI@Z`
- size: `491`
- prototype: `__int64 __fastcall(const wchar_t *const *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cff4`

## callees

- `0x180001e40`
- `0x18000555c`
- `0x18000c614`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000570f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000570f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800056c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800056c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800055f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800056ef`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005681`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005681`

## string_xrefs

- `0x1800055a0`: `CLSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall BuildKeyValues(const wchar_t *const *a1, unsigned int a2)
{
  unsigned int v4; // edi
  HKEY v5; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rbx
  const BYTE *v8; // rdx
  __int64 v9; // rax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  void **v13; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSubKey; // [rsp+68h] [rbp-98h]
  int v15; // [rsp+70h] [rbp-90h]
  unsigned int v16; // [rsp+74h] [rbp-8Ch]
  __int64 v17; // [rsp+78h] [rbp-88h] BYREF
  WCHAR v18; // [rsp+80h] [rbp-80h]
  __int16 v19; // [rsp+82h] [rbp-7Eh]

  lpSubKey = (LPCWSTR)&v17;
  v15 = 1025;
  v17 = *(_QWORD *)L"CLSID";
  v18 = aClsid_1[4];
  v16 = 5;
  v19 = 0;
  v13 = &TLMString<1024,1024,1048576>::`vftable';
  v4 = 0;
  v5 = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = 0;
  if ( a2 )
  {
    while ( 1 )
    {
      if ( v5 != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      {
        RegCloseKey(v5);
        hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
      }
      ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v13[4])(&v13, L"\\", v16, 0xFFFFFFFFLL);
      ((void (__fastcall *)(void ***, const wchar_t *const, _QWORD, __int64))v13[4])(&v13, a1[v6], v16, 0xFFFFFFFFLL);
      dwDisposition = 0;
      v4 = RegCreateKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
      if ( v4 )
        break;
      v7 = v6 + 1;
      if ( (unsigned int)v7 < a2 )
      {
        v8 = (const BYTE *)a1[v7];
        if ( v8 )
        {
          v9 = -1;
          do
            ++v9;
          while ( *(_WORD *)&v8[2 * v9] );
          v4 = RegSetValueExW(hKey, 0, 0, 1u, v8, 2 * v9 + 2);
          if ( v4 )
            break;
        }
      }
      v6 = v7 + 1;
      if ( v6 >= a2 )
        break;
      v5 = hKey;
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
  }
  v13 = &TLMString<1024,1024,1048576>::`vftable';
  if ( lpSubKey && lpSubKey != (LPCWSTR)&v17 )
  {
    free((void *)lpSubKey);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
  }
  return v4;
}

```

## disassembly

```asm
0x18000555c  push    rbp
0x18000555e  push    rbx
0x18000555f  push    rsi
0x180005560  push    rdi
0x180005561  push    r12
0x180005563  push    r13
0x180005565  push    r14
0x180005567  push    r15
0x180005569  lea     rbp, [rsp-798h]
0x180005571  sub     rsp, 898h
0x180005578  mov     rax, cs:__security_cookie
0x18000557f  xor     rax, rsp
0x180005582  mov     [rbp+7D0h+var_50], rax
0x180005589  mov     esi, edx
0x18000558b  mov     r14, rcx
0x18000558e  lea     rcx, [rsp+8D0h+var_858]
0x180005593  mov     [rsp+8D0h+lpSubKey], rcx
0x180005598  mov     [rsp+8D0h+var_860], 401h
0x1800055a0  movsd   xmm0, qword ptr cs:aClsid_1; "CLSID"
0x1800055a8  movsd   [rsp+8D0h+var_858], xmm0
0x1800055ae  movzx   eax, word ptr cs:aClsid_1+8; "D"
0x1800055b5  mov     [rbp+7D0h+var_850], ax
0x1800055b9  mov     [rsp+8D0h+var_85C], 5
0x1800055c1  xor     r15d, r15d
0x1800055c4  mov     [rcx+0Ah], r15w
0x1800055c9  lea     r13, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800055d0  mov     [rsp+8D0h+var_870], r13
0x1800055d5  mov     edi, r15d
0x1800055d8  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800055dc  mov     rcx, r12; hKey
0x1800055df  mov     [rsp+8D0h+hKey], rcx
0x1800055e4  mov     ebx, r15d
0x1800055e7  test    edx, edx
0x1800055e9  jz      loc_1800056F6
0x1800055ef  cmp     rcx, r12
0x1800055f2  jz      short loc_1800055FF
0x1800055f4  call    cs:__imp_RegCloseKey
0x1800055fa  mov     [rsp+8D0h+hKey], r12
0x1800055ff  mov     rax, [rsp+8D0h+var_870]
0x180005604  or      r9d, 0FFFFFFFFh
0x180005608  mov     r8d, [rsp+8D0h+var_85C]
0x18000560d  lea     rdx, asc_18001D50C; "\\"
0x180005614  lea     rcx, [rsp+8D0h+var_870]
0x180005619  mov     rax, [rax+20h]
0x18000561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005622  mov     edx, ebx
0x180005624  mov     rax, [rsp+8D0h+var_870]
0x180005629  or      r9d, 0FFFFFFFFh
0x18000562d  mov     r8d, [rsp+8D0h+var_85C]
0x180005632  mov     rdx, [r14+rdx*8]
0x180005636  lea     rcx, [rsp+8D0h+var_870]
0x18000563b  mov     rax, [rax+20h]
0x18000563f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005644  mov     [rsp+8D0h+dwDisposition], r15d
0x180005649  lea     rax, [rsp+8D0h+dwDisposition]
0x18000564e  mov     [rsp+8D0h+lpdwDisposition], rax; lpdwDisposition
0x180005653  lea     rax, [rsp+8D0h+hKey]
0x180005658  mov     [rsp+8D0h+phkResult], rax; phkResult
0x18000565d  mov     [rsp+8D0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180005662  mov     [rsp+8D0h+samDesired], 20006h; samDesired
0x18000566a  mov     [rsp+8D0h+dwOptions], r15d; dwOptions
0x18000566f  xor     r9d, r9d; lpClass
0x180005672  xor     r8d, r8d; Reserved
0x180005675  mov     rdx, [rsp+8D0h+lpSubKey]; lpSubKey
0x18000567a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005681  call    cs:__imp_RegCreateKeyExW
0x180005687  mov     edi, eax
0x180005689  test    eax, eax
0x18000568b  jnz     short loc_1800056E5
0x18000568d  inc     ebx
0x18000568f  cmp     ebx, esi
0x180005691  jnb     short loc_1800056D5
0x180005693  mov     rdx, [r14+rbx*8]
0x180005697  test    rdx, rdx
0x18000569a  jz      short loc_1800056D5
0x18000569c  mov     rax, r12
0x18000569f  inc     rax
0x1800056a2  cmp     [rdx+rax*2], r15w
0x1800056a7  jnz     short loc_18000569F
0x1800056a9  lea     eax, ds:2[rax*2]
0x1800056b0  mov     [rsp+8D0h+samDesired], eax; cbData
0x1800056b4  mov     qword ptr [rsp+8D0h+dwOptions], rdx; lpData
0x1800056b9  mov     r9d, 1; dwType
0x1800056bf  xor     r8d, r8d; Reserved
0x1800056c2  xor     edx, edx; lpValueName
0x1800056c4  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800056c9  call    cs:__imp_RegSetValueExW
0x1800056cf  mov     edi, eax
0x1800056d1  test    eax, eax
0x1800056d3  jnz     short loc_1800056E5
0x1800056d5  inc     ebx
0x1800056d7  cmp     ebx, esi
0x1800056d9  jnb     short loc_1800056E5
0x1800056db  mov     rcx, [rsp+8D0h+hKey]
0x1800056e0  jmp     loc_1800055EF
0x1800056e5  mov     rcx, [rsp+8D0h+hKey]; hKey
0x1800056ea  cmp     rcx, r12
0x1800056ed  jz      short loc_1800056F6
0x1800056ef  call    cs:__imp_RegCloseKey
0x1800056f5  nop
0x1800056f6  mov     [rsp+8D0h+var_870], r13
0x1800056fb  mov     rcx, [rsp+8D0h+lpSubKey]; Block
0x180005700  test    rcx, rcx
0x180005703  jz      short loc_180005722
0x180005705  lea     rax, [rsp+8D0h+var_858]
0x18000570a  cmp     rcx, rax
0x18000570d  jz      short loc_180005722
0x18000570f  call    cs:__imp_free
0x180005715  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x18000571c  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180005721  nop
0x180005722  mov     eax, edi
0x180005724  mov     rcx, [rbp+7D0h+var_50]
0x18000572b  xor     rcx, rsp; StackCookie
0x18000572e  call    __security_check_cookie
0x180005733  add     rsp, 898h
0x18000573a  pop     r15
0x18000573c  pop     r14
0x18000573e  pop     r13
0x180005740  pop     r12
0x180005742  pop     rdi
0x180005743  pop     rsi
0x180005744  pop     rbx
0x180005745  pop     rbp
0x180005746  retn
```
