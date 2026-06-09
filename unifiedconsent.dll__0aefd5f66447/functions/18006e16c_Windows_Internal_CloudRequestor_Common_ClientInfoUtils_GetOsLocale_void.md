# Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetOsLocale(void)

- ea: `0x18006e16c`
- end: `0x18006e29f`
- name: `?GetOsLocale@ClientInfoUtils@Common@CloudRequestor@Internal@Windows@@YA?AUhstring@winrt@@XZ`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18006dd44`

## callees

- `0x180002810`
- `0x18000ebfc`
- `0x18000f44c`
- `0x1800139fc`
- `0x18001b0b8`
- `0x18006e16c`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18006e1c2`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18006e20f`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18006e1c2`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x18006e20f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
struct winrt::impl::shared_hstring_header **__fastcall Windows::Internal::CloudRequestor::Common::ClientInfoUtils::GetOsLocale(
        struct winrt::impl::shared_hstring_header **a1)
{
  struct winrt::impl::shared_hstring_header *v2; // rbx
  WCHAR *v3; // r8
  unsigned int v4; // edx
  PZZWSTR *v5; // r14
  unsigned int v6; // esi
  ULONG pcchLanguagesBuffer; // [rsp+20h] [rbp-68h] BYREF
  ULONG pulNumLanguages[3]; // [rsp+24h] [rbp-64h] BYREF
  struct winrt::impl::shared_hstring_header **v10; // [rsp+30h] [rbp-58h]
  PZZWSTR pwszLanguagesBuffer[2]; // [rsp+38h] [rbp-50h] BYREF
  winrt::impl *v12; // [rsp+48h] [rbp-40h]
  unsigned __int64 v13; // [rsp+50h] [rbp-38h]

  v10 = a1;
  v2 = 0;
  *(_OWORD *)pwszLanguagesBuffer = 0;
  v12 = 0;
  v13 = 7;
  LOWORD(pwszLanguagesBuffer[0]) = 0;
  pulNumLanguages[0] = 0;
  pcchLanguagesBuffer = 0;
  if ( GetSystemPreferredUILanguages(8u, pulNumLanguages, 0, &pcchLanguagesBuffer)
    && pulNumLanguages[0]
    && pcchLanguagesBuffer )
  {
    std::wstring::resize(pwszLanguagesBuffer);
    v3 = (WCHAR *)pwszLanguagesBuffer;
    if ( v13 > 7 )
      v3 = pwszLanguagesBuffer[0];
    GetSystemPreferredUILanguages(8u, pulNumLanguages, v3, &pcchLanguagesBuffer);
    std::wstring::resize(pwszLanguagesBuffer);
    v5 = pwszLanguagesBuffer;
    if ( v13 > 7 )
      v5 = (PZZWSTR *)pwszLanguagesBuffer[0];
    v6 = (unsigned int)v12;
    if ( (_DWORD)v12 )
    {
      v2 = winrt::impl::precreate_hstring_on_heap((winrt::impl *)(unsigned int)v12, v4);
      memcpy_s((char *)v2 + 28, 2LL * v6, v5, 2LL * v6);
    }
    *a1 = v2;
    std::wstring::_Tidy_deallocate(pwszLanguagesBuffer);
    return a1;
  }
  else
  {
    std::wstring::_Tidy_deallocate(pwszLanguagesBuffer);
    *a1 = 0;
    return a1;
  }
}

```

## disassembly

```asm
0x18006e16c  mov     r11, rsp
0x18006e16f  push    rbx
0x18006e170  push    rsi
0x18006e171  push    rdi
0x18006e172  push    r14
0x18006e174  sub     rsp, 68h
0x18006e178  mov     rax, cs:__security_cookie
0x18006e17f  xor     rax, rsp
0x18006e182  mov     [rsp+88h+var_30], rax
0x18006e187  mov     rdi, rcx
0x18006e18a  mov     [rsp+88h+var_58], rcx
0x18006e18f  xor     ebx, ebx
0x18006e191  xorps   xmm0, xmm0
0x18006e194  movups  xmmword ptr [rsp+88h+pwszLanguagesBuffer], xmm0
0x18006e199  mov     [r11-40h], rbx
0x18006e19d  mov     qword ptr [r11-38h], 7
0x18006e1a5  mov     word ptr [rsp+88h+pwszLanguagesBuffer], bx
0x18006e1aa  mov     [rsp+88h+pulNumLanguages], ebx
0x18006e1ae  mov     [rsp+88h+pcchLanguagesBuffer], ebx
0x18006e1b2  lea     r9, [r11-68h]; pcchLanguagesBuffer
0x18006e1b6  xor     r8d, r8d; pwszLanguagesBuffer
0x18006e1b9  lea     rdx, [r11-64h]; pulNumLanguages
0x18006e1bd  lea     esi, [rbx+8]
0x18006e1c0  mov     ecx, esi; dwFlags
0x18006e1c2  call    cs:__imp_GetSystemPreferredUILanguages
0x18006e1c8  test    eax, eax
0x18006e1ca  jz      loc_18006E26D
0x18006e1d0  cmp     [rsp+88h+pulNumLanguages], ebx
0x18006e1d4  jbe     loc_18006E26D
0x18006e1da  cmp     [rsp+88h+pcchLanguagesBuffer], ebx
0x18006e1de  jbe     loc_18006E26D
0x18006e1e4  mov     edx, [rsp+88h+pcchLanguagesBuffer]
0x18006e1e8  lea     rcx, [rsp+88h+pwszLanguagesBuffer]; Src
0x18006e1ed  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18006e1f2  lea     r8, [rsp+88h+pwszLanguagesBuffer]
0x18006e1f7  cmp     [rsp+88h+var_38], 7
0x18006e1fd  cmova   r8, [rsp+88h+pwszLanguagesBuffer]; pwszLanguagesBuffer
0x18006e203  lea     r9, [rsp+88h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x18006e208  lea     rdx, [rsp+88h+pulNumLanguages]; pulNumLanguages
0x18006e20d  mov     ecx, esi; dwFlags
0x18006e20f  call    cs:__imp_GetSystemPreferredUILanguages
0x18006e215  mov     rdx, [rsp+88h+var_40]
0x18006e21a  lea     rcx, [rsp+88h+pwszLanguagesBuffer]; Src
0x18006e21f  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18006e224  lea     r14, [rsp+88h+pwszLanguagesBuffer]
0x18006e229  cmp     [rsp+88h+var_38], 7
0x18006e22f  cmova   r14, [rsp+88h+pwszLanguagesBuffer]
0x18006e235  mov     esi, dword ptr [rsp+88h+var_40]
0x18006e239  test    esi, esi
0x18006e23b  jz      short loc_18006E25B
0x18006e23d  mov     ecx, esi; this
0x18006e23f  call    ?precreate_hstring_on_heap@impl@winrt@@YAPEAUshared_hstring_header@12@I@Z; winrt::impl::precreate_hstring_on_heap(uint)
0x18006e244  mov     rbx, rax
0x18006e247  mov     edx, esi
0x18006e249  add     rdx, rdx; DestinationSize
0x18006e24c  lea     rcx, [rax+1Ch]; Destination
0x18006e250  mov     r9, rdx; SourceSize
0x18006e253  mov     r8, r14; Source
0x18006e256  call    memcpy_s
0x18006e25b  mov     [rdi], rbx
0x18006e25e  lea     rcx, [rsp+88h+pwszLanguagesBuffer]
0x18006e263  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e268  mov     rax, rdi
0x18006e26b  jmp     short loc_18006E287
0x18006e26d  lea     rcx, [rsp+88h+pwszLanguagesBuffer]
0x18006e272  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006e277  nop
0x18006e278  jmp     short loc_18006E281
0x18006e27a  xor     ebx, ebx
0x18006e27c  mov     rdi, [rsp+88h+var_58]
0x18006e281  mov     [rdi], rbx
0x18006e284  mov     rax, rdi
0x18006e287  mov     rcx, [rsp+88h+var_30]
0x18006e28c  xor     rcx, rsp; StackCookie
0x18006e28f  call    __security_check_cookie
0x18006e294  add     rsp, 68h
0x18006e298  pop     r14
0x18006e29a  pop     rdi
0x18006e29b  pop     rsi
0x18006e29c  pop     rbx
0x18006e29d  retn
```
