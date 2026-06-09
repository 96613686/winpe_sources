# DestroyKeyValues(wchar_t const * const *,int)

- ea: `0x180005ae4`
- end: `0x180005d1c`
- name: `?DestroyKeyValues@@YAJPEBQEB_WH@Z`
- size: `568`
- prototype: `__int64 __fastcall(const wchar_t *const *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000ba74`
- `0x18000cee0`

## callees

- `0x180001e40`
- `0x180005ae4`
- `0x18000b7cc`
- `0x18000c614`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ccb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005ccb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005c28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005be8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005be8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005c8f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005c0a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005ca3`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005c0a`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005ca3`

## string_xrefs

- `0x180005b29`: `CLSID`
- `0x180005d0a`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DestroyKeyValues(LPCWSTR *a1, int a2)
{
  void **v4; // rax
  int v5; // edi
  __int64 v6; // rsi
  unsigned int v7; // ebx
  const char *v8; // r9
  __int64 v9; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey[2]; // [rsp+30h] [rbp-D0h] BYREF
  void **v13; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h]
  int v15; // [rsp+50h] [rbp-B0h]
  unsigned int v16; // [rsp+54h] [rbp-ACh]
  __int64 v17; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v18; // [rsp+60h] [rbp-A0h]
  __int16 v19; // [rsp+62h] [rbp-9Eh]
  wil::details::in1diag3 *retaddr; // [rsp+8B8h] [rbp+7B8h]

  lpSubKey = (LPCWSTR)&v17;
  v15 = 1025;
  v17 = *(_QWORD *)L"CLSID";
  v18 = aClsid_1[4];
  v16 = 5;
  v19 = 0;
  v4 = &TLMString<1024,1024,1048576>::`vftable';
  v13 = &TLMString<1024,1024,1048576>::`vftable';
  v5 = 0;
  if ( a2 > 0 )
  {
    while ( 1 )
    {
      ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v4[4])(&v13, L"\\", v16, 0xFFFFFFFFLL);
      ((void (__fastcall *)(void ***, const wchar_t *const, _QWORD, __int64))v13[4])(&v13, a1[v5], v16, 0xFFFFFFFFLL);
      v5 += 2;
      if ( v5 >= a2 )
        break;
      v4 = v13;
    }
  }
  hKey[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  LODWORD(v6) = v16;
  while ( 1 )
  {
    v5 -= 2;
    if ( v5 < 0 )
      break;
    v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, hKey);
    if ( v7 )
      goto LABEL_17;
    if ( v5 + 2 < a2 )
    {
      v7 = RegDeleteKeyW(hKey[0], a1[(unsigned int)v5 + 2]);
      if ( v7 )
        goto LABEL_17;
    }
    if ( hKey[0] != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    v9 = -1;
    do
      ++v9;
    while ( a1[v5][v9] );
    v6 = (unsigned int)(-1 - v9 + v6);
    if ( (unsigned int)v6 > v15 - 1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\lmstr.hxx",
        v8,
        phkResult);
    v16 = v6;
    lpSubKey[v6] = 0;
  }
  v7 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, hKey);
  if ( !v7 )
    v7 = RegDeleteKeyW(hKey[0], *a1);
LABEL_17:
  v13 = &TLMString<1024,1024,1048576>::`vftable';
  if ( lpSubKey && lpSubKey != (LPCWSTR)&v17 )
  {
    free((void *)lpSubKey);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
  }
  return v7;
}

```

## disassembly

```asm
0x180005ae4  push    rbp
0x180005ae6  push    rbx
0x180005ae7  push    rsi
0x180005ae8  push    rdi
0x180005ae9  push    r12
0x180005aeb  push    r13
0x180005aed  push    r14
0x180005aef  push    r15
0x180005af1  lea     rbp, [rsp-778h]
0x180005af9  sub     rsp, 878h
0x180005b00  mov     rax, cs:__security_cookie
0x180005b07  xor     rax, rsp
0x180005b0a  mov     [rbp+7B0h+var_50], rax
0x180005b11  mov     r15d, edx
0x180005b14  mov     r14, rcx
0x180005b17  lea     rcx, [rsp+8B0h+var_858]
0x180005b1c  mov     [rsp+8B0h+lpSubKey], rcx
0x180005b21  mov     [rsp+8B0h+var_860], 401h
0x180005b29  movsd   xmm0, qword ptr cs:aClsid_1; "CLSID"
0x180005b31  movsd   [rsp+8B0h+var_858], xmm0
0x180005b37  movzx   eax, word ptr cs:aClsid_1+8; "D"
0x180005b3e  mov     [rsp+8B0h+var_850], ax
0x180005b43  mov     [rsp+8B0h+var_85C], 5
0x180005b4b  xor     r12d, r12d
0x180005b4e  mov     [rcx+0Ah], r12w
0x180005b53  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180005b5a  mov     [rsp+8B0h+var_870], rax
0x180005b5f  mov     edi, r12d
0x180005b62  or      ebx, 0FFFFFFFFh
0x180005b65  test    edx, edx
0x180005b67  jle     short loc_180005BB7
0x180005b69  mov     r9d, ebx
0x180005b6c  mov     r8d, [rsp+8B0h+var_85C]
0x180005b71  lea     rdx, asc_18001D50C; "\\"
0x180005b78  lea     rcx, [rsp+8B0h+var_870]
0x180005b7d  mov     rax, [rax+20h]
0x180005b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b86  movsxd  rdx, edi
0x180005b89  mov     rax, [rsp+8B0h+var_870]
0x180005b8e  mov     r9d, ebx
0x180005b91  mov     r8d, [rsp+8B0h+var_85C]
0x180005b96  mov     rdx, [r14+rdx*8]
0x180005b9a  lea     rcx, [rsp+8B0h+var_870]
0x180005b9f  mov     rax, [rax+20h]
0x180005ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ba8  add     edi, 2
0x180005bab  cmp     edi, r15d
0x180005bae  jge     short loc_180005BB7
0x180005bb0  mov     rax, [rsp+8B0h+var_870]
0x180005bb5  jmp     short loc_180005B69
0x180005bb7  or      r13, 0FFFFFFFFFFFFFFFFh
0x180005bbb  mov     [rsp+8B0h+hKey], r13
0x180005bc0  mov     esi, [rsp+8B0h+var_85C]
0x180005bc4  jmp     loc_180005C67
0x180005bc9  lea     rax, [rsp+8B0h+hKey]
0x180005bce  mov     qword ptr [rsp+8B0h+phkResult], rax; unsigned int
0x180005bd3  mov     r9d, 2001Fh; samDesired
0x180005bd9  xor     r8d, r8d; ulOptions
0x180005bdc  mov     rdx, [rsp+8B0h+lpSubKey]; lpSubKey
0x180005be1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005be8  call    cs:__imp_RegOpenKeyExW
0x180005bee  mov     ebx, eax
0x180005bf0  test    eax, eax
0x180005bf2  jnz     loc_180005CAB
0x180005bf8  lea     eax, [rdi+2]
0x180005bfb  cmp     eax, r15d
0x180005bfe  jge     short loc_180005C1A
0x180005c00  mov     rdx, [r14+rdi*8+10h]; lpSubKey
0x180005c05  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180005c0a  call    cs:__imp_RegDeleteKeyW
0x180005c10  mov     ebx, eax
0x180005c12  test    eax, eax
0x180005c14  jnz     loc_180005CAB
0x180005c1a  mov     eax, edi
0x180005c1c  mov     ebx, eax
0x180005c1e  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180005c23  cmp     rcx, r13
0x180005c26  jz      short loc_180005C33
0x180005c28  call    cs:__imp_RegCloseKey
0x180005c2e  mov     [rsp+8B0h+hKey], r13
0x180005c33  mov     rax, [r14+rbx*8]
0x180005c37  mov     rcx, r13
0x180005c3a  inc     rcx
0x180005c3d  cmp     [rax+rcx*2], r12w
0x180005c42  jnz     short loc_180005C3A
0x180005c44  or      eax, 0FFFFFFFFh
0x180005c47  sub     eax, ecx
0x180005c49  add     esi, eax
0x180005c4b  mov     eax, [rsp+8B0h+var_860]
0x180005c4f  dec     eax
0x180005c51  cmp     esi, eax
0x180005c53  ja      loc_180005D03
0x180005c59  mov     [rsp+8B0h+var_85C], esi
0x180005c5d  mov     rax, [rsp+8B0h+lpSubKey]
0x180005c62  mov     [rax+rsi*2], r12w
0x180005c67  sub     edi, 2
0x180005c6a  jns     loc_180005BC9
0x180005c70  lea     rax, [rsp+8B0h+hKey]
0x180005c75  mov     qword ptr [rsp+8B0h+phkResult], rax; phkResult
0x180005c7a  mov     r9d, 2001Fh; samDesired
0x180005c80  xor     r8d, r8d; ulOptions
0x180005c83  mov     rdx, [rsp+8B0h+lpSubKey]; lpSubKey
0x180005c88  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005c8f  call    cs:__imp_RegOpenKeyExW
0x180005c95  mov     ebx, eax
0x180005c97  test    eax, eax
0x180005c99  jnz     short loc_180005CAB
0x180005c9b  mov     rdx, [r14]; lpSubKey
0x180005c9e  mov     rcx, [rsp+8B0h+hKey]; hKey
0x180005ca3  call    cs:__imp_RegDeleteKeyW
0x180005ca9  mov     ebx, eax
0x180005cab  lea     rax, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x180005cb2  mov     [rsp+8B0h+var_870], rax
0x180005cb7  mov     rcx, [rsp+8B0h+lpSubKey]; Block
0x180005cbc  test    rcx, rcx
0x180005cbf  jz      short loc_180005CDE
0x180005cc1  lea     rax, [rsp+8B0h+var_858]
0x180005cc6  cmp     rcx, rax
0x180005cc9  jz      short loc_180005CDE
0x180005ccb  call    cs:__imp_free
0x180005cd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x180005cd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180005cdd  nop
0x180005cde  mov     eax, ebx
0x180005ce0  mov     rcx, [rbp+7B0h+var_50]
0x180005ce7  xor     rcx, rsp; StackCookie
0x180005cea  call    __security_check_cookie
0x180005cef  add     rsp, 878h
0x180005cf6  pop     r15
0x180005cf8  pop     r14
0x180005cfa  pop     r13
0x180005cfc  pop     r12
0x180005cfe  pop     rdi
0x180005cff  pop     rsi
0x180005d00  pop     rbx
0x180005d01  pop     rbp
0x180005d02  retn
0x180005d03  mov     rcx, [rbp+7B8h]; this
0x180005d0a  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180005d11  mov     edx, 13Bh; void *
0x180005d16  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
