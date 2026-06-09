# AddThreadingModel(wchar_t const *,wchar_t const *)

- ea: `0x180005340`
- end: `0x180005555`
- name: `?AddThreadingModel@@YAJPEB_W0@Z`
- size: `533`
- prototype: `int(const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000cff4`

## callees

- `0x180001e40`
- `0x180005340`
- `0x18000c614`
- `0x18000d940`
- `0x18001b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005485`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000551a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180005485`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000551a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800054d4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800054d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054fa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800054fa`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800054ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800054ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005460`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005460`

## string_xrefs

- `0x180005384`: `CLSID`
- `0x1800054c8`: `ThreadingModel`
- `0x1800054de`: `ThreadingModel`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall AddThreadingModel(const wchar_t *a1, const BYTE *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  void **v8; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h]
  int v10; // [rsp+50h] [rbp-B0h]
  unsigned int v11; // [rsp+54h] [rbp-ACh]
  __int64 v12; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR v13; // [rsp+60h] [rbp-A0h]
  __int16 v14; // [rsp+62h] [rbp-9Eh]

  lpSubKey = (LPCWSTR)&v12;
  v10 = 1025;
  v12 = *(_QWORD *)L"CLSID";
  v13 = aClsid_1[4];
  v11 = 5;
  v14 = 0;
  v8 = &TLMString<1024,1024,1048576>::`vftable';
  CLMString::Assign((CLMString *)&v8, L"\\", 5u, 0xFFFFFFFF);
  ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v8[4])(&v8, a1, v11, 0xFFFFFFFFLL);
  ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v8[4])(&v8, L"\\", v11, 0xFFFFFFFFLL);
  ((void (__fastcall *)(void ***, const wchar_t *, _QWORD, __int64))v8[4])(&v8, L"InprocServer32", v11, 0xFFFFFFFFLL);
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = RegOpenKeyExW(HKEY_CLASSES_ROOT, lpSubKey, 0, 0x2001Fu, &hKey);
  if ( v4 )
  {
    v8 = &TLMString<1024,1024,1048576>::`vftable';
    if ( lpSubKey && lpSubKey != (LPCWSTR)&v12 )
    {
      free((void *)lpSubKey);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
    }
  }
  else
  {
    if ( a2 )
    {
      v5 = -1;
      do
        ++v5;
      while ( *(_WORD *)&a2[2 * v5] );
      v4 = RegSetValueExW(hKey, L"ThreadingModel", 0, 1u, a2, 2 * v5 + 2);
    }
    else
    {
      RegDeleteValueW(hKey, L"ThreadingModel");
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    v8 = &TLMString<1024,1024,1048576>::`vftable';
    if ( lpSubKey && lpSubKey != (LPCWSTR)&v12 )
    {
      free((void *)lpSubKey);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl'::`2'::impl);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x180005340  mov     [rsp-8+arg_10], rbx
0x180005345  push    rbp
0x180005346  push    rsi
0x180005347  push    rdi
0x180005348  push    r14
0x18000534a  push    r15
0x18000534c  lea     rbp, [rsp-770h]
0x180005354  sub     rsp, 870h
0x18000535b  mov     rax, cs:__security_cookie
0x180005362  xor     rax, rsp
0x180005365  mov     [rbp+790h+var_30], rax
0x18000536c  mov     rdi, rdx
0x18000536f  mov     rbx, rcx
0x180005372  lea     rcx, [rsp+890h+var_838]
0x180005377  mov     [rsp+890h+lpSubKey], rcx
0x18000537c  mov     [rsp+890h+var_840], 401h
0x180005384  movsd   xmm0, qword ptr cs:aClsid_1; "CLSID"
0x18000538c  movsd   [rsp+890h+var_838], xmm0
0x180005392  movzx   eax, word ptr cs:aClsid_1+8; "D"
0x180005399  mov     [rsp+890h+var_830], ax
0x18000539e  mov     [rsp+890h+var_83C], 5
0x1800053a6  xor     r14d, r14d
0x1800053a9  mov     [rcx+0Ah], r14w
0x1800053ae  lea     r15, ??_7?$TLMString@$0EAA@$0EAA@$0BAAAAA@@@6B@; const TLMString<1024,1024,1048576>::`vftable'
0x1800053b5  mov     [rsp+890h+var_850], r15
0x1800053ba  or      esi, 0FFFFFFFFh
0x1800053bd  mov     r9d, esi; unsigned int
0x1800053c0  mov     r8d, [rsp+890h+var_83C]; unsigned int
0x1800053c5  lea     rdx, asc_18001D50C; "\\"
0x1800053cc  lea     rcx, [rsp+890h+var_850]; this
0x1800053d1  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x1800053d6  mov     rax, [rsp+890h+var_850]
0x1800053db  mov     r9d, esi
0x1800053de  mov     r8d, [rsp+890h+var_83C]
0x1800053e3  mov     rdx, rbx
0x1800053e6  lea     rcx, [rsp+890h+var_850]
0x1800053eb  mov     rax, [rax+20h]
0x1800053ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f4  mov     rax, [rsp+890h+var_850]
0x1800053f9  mov     r9d, esi
0x1800053fc  mov     r8d, [rsp+890h+var_83C]
0x180005401  lea     rdx, asc_18001D50C; "\\"
0x180005408  lea     rcx, [rsp+890h+var_850]
0x18000540d  mov     rax, [rax+20h]
0x180005411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005416  mov     rax, [rsp+890h+var_850]
0x18000541b  mov     r9d, esi
0x18000541e  mov     r8d, [rsp+890h+var_83C]
0x180005423  lea     rdx, aInprocserver32; "InprocServer32"
0x18000542a  lea     rcx, [rsp+890h+var_850]
0x18000542f  mov     rax, [rax+20h]
0x180005433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005438  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000543c  mov     [rsp+890h+hKey], rsi
0x180005441  lea     rax, [rsp+890h+hKey]
0x180005446  mov     [rsp+890h+phkResult], rax; phkResult
0x18000544b  mov     r9d, 2001Fh; samDesired
0x180005451  xor     r8d, r8d; ulOptions
0x180005454  mov     rdx, [rsp+890h+lpSubKey]; lpSubKey
0x180005459  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180005460  call    cs:__imp_RegOpenKeyExW
0x180005466  mov     ebx, eax
0x180005468  test    eax, eax
0x18000546a  jz      short loc_18000549D
0x18000546c  mov     [rsp+890h+var_850], r15
0x180005471  mov     rcx, [rsp+890h+lpSubKey]; Block
0x180005476  test    rcx, rcx
0x180005479  jz      short loc_180005498
0x18000547b  lea     rax, [rsp+890h+var_838]
0x180005480  cmp     rcx, rax
0x180005483  jz      short loc_180005498
0x180005485  call    cs:__imp_free
0x18000548b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x180005492  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x180005497  nop
0x180005498  jmp     loc_18000552D
0x18000549d  test    rdi, rdi
0x1800054a0  jz      short loc_1800054DE
0x1800054a2  mov     rax, rsi
0x1800054a5  inc     rax
0x1800054a8  cmp     [rdi+rax*2], r14w
0x1800054ad  jnz     short loc_1800054A5
0x1800054af  lea     eax, ds:2[rax*2]
0x1800054b6  mov     [rsp+890h+cbData], eax; cbData
0x1800054ba  mov     [rsp+890h+phkResult], rdi; lpData
0x1800054bf  mov     r9d, 1; dwType
0x1800054c5  xor     r8d, r8d; Reserved
0x1800054c8  lea     rdx, ValueName; "ThreadingModel"
0x1800054cf  mov     rcx, [rsp+890h+hKey]; hKey
0x1800054d4  call    cs:__imp_RegSetValueExW
0x1800054da  mov     ebx, eax
0x1800054dc  jmp     short loc_1800054F0
0x1800054de  lea     rdx, ValueName; "ThreadingModel"
0x1800054e5  mov     rcx, [rsp+890h+hKey]; hKey
0x1800054ea  call    cs:__imp_RegDeleteValueW
0x1800054f0  mov     rcx, [rsp+890h+hKey]; hKey
0x1800054f5  cmp     rcx, rsi
0x1800054f8  jz      short loc_180005501
0x1800054fa  call    cs:__imp_RegCloseKey
0x180005500  nop
0x180005501  mov     [rsp+890h+var_850], r15
0x180005506  mov     rcx, [rsp+890h+lpSubKey]; Block
0x18000550b  test    rcx, rcx
0x18000550e  jz      short loc_18000552D
0x180005510  lea     rax, [rsp+890h+var_838]
0x180005515  cmp     rcx, rax
0x180005518  jz      short loc_18000552D
0x18000551a  call    cs:__imp_free
0x180005520  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56494824@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824> `wil::Feature<__WilFeatureTraits_Feature_56494824>::GetImpl(void)'::`2'::impl
0x180005527  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56494824@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56494824>::__private_IsEnabled(void)
0x18000552c  nop
0x18000552d  mov     eax, ebx
0x18000552f  mov     rcx, [rbp+790h+var_30]
0x180005536  xor     rcx, rsp; StackCookie
0x180005539  call    __security_check_cookie
0x18000553e  mov     rbx, [rsp+890h+arg_10]
0x180005546  add     rsp, 870h
0x18000554d  pop     r15
0x18000554f  pop     r14
0x180005551  pop     rdi
0x180005552  pop     rsi
0x180005553  pop     rbp
0x180005554  retn
```
