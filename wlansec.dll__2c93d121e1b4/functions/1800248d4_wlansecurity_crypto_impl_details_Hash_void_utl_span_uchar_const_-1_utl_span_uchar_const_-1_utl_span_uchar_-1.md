# wlansecurity::crypto::impl::details::Hash(void *,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x1800248d4`
- end: `0x1800249bb`
- name: `?Hash@details@impl@crypto@wlansecurity@@YAJPEAXV?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@6@@Z`
- size: `231`
- prototype: ``
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800246b0`
- `0x180040c0c`
- `0x18006d434`
- `0x180080560`
- `0x1800809c8`
- `0x1800839b0`
- `0x180083e58`

## callees

- `0x1800248d4`
- `0x1800249c4`
- `0x180033650`
- `0x180096010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x180024988`
- `bcrypt!BCryptFinishHash` at `0x18002496d`
- `bcrypt!BCryptFinishHash` at `0x18002496d`
- `bcrypt!BCryptHashData` at `0x18002494d`
- `bcrypt!BCryptHashData` at `0x18002494d`
- `bcrypt!BCryptCreateHash` at `0x180024924`
- `bcrypt!BCryptCreateHash` at `0x180024924`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wlansecurity::crypto::impl::details::Hash(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  NTSTATUS v6; // esi
  NTSTATUS v7; // ebx
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  char v11; // [rsp+50h] [rbp-18h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+A0h] [rbp+38h] BYREF

  hHash = 0;
  p_hHash = &hHash;
  phHash = 0;
  v11 = 1;
  v6 = BCryptCreateHash(a1, &phHash, 0, 0, *(PUCHAR *)a3, *(_DWORD *)(a3 + 8), 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
  if ( v6 < 0 )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
    return (unsigned int)v6;
  }
  else
  {
    v7 = BCryptHashData(hHash, *(PUCHAR *)a2, *(_DWORD *)(a2 + 8), 0);
    if ( v7 < 0 || (v7 = BCryptFinishHash(hHash, *(PUCHAR *)a4, *(_DWORD *)(a4 + 8), 0), v7 < 0) )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
      return (unsigned int)v7;
    }
    else
    {
      if ( hHash )
        ((void (*)(void))BCryptDestroyHash)();
      return 0;
    }
  }
}

```

## disassembly

```asm
0x1800248d4  push    rbp
0x1800248d6  push    rbx
0x1800248d7  push    rsi
0x1800248d8  push    rdi
0x1800248d9  mov     rbp, rsp
0x1800248dc  sub     rsp, 68h
0x1800248e0  mov     rdi, r9
0x1800248e3  mov     rbx, rdx
0x1800248e6  mov     [rbp+hHash], 0
0x1800248ee  lea     rax, [rbp+hHash]
0x1800248f2  mov     [rbp+var_28], rax
0x1800248f6  mov     [rbp+phHash], 0
0x1800248fe  mov     [rbp+var_18], 1
0x180024902  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18002490a  mov     eax, [r8+8]
0x18002490e  mov     [rsp+68h+cbSecret], eax; cbSecret
0x180024912  mov     rax, [r8]
0x180024915  mov     [rsp+68h+pbSecret], rax; pbSecret
0x18002491a  xor     r9d, r9d; cbHashObject
0x18002491d  xor     r8d, r8d; pbHashObject
0x180024920  lea     rdx, [rbp+phHash]; phHash
0x180024924  call    cs:__imp_BCryptCreateHash
0x18002492b  nop     dword ptr [rax+rax+00h]
0x180024930  mov     esi, eax
0x180024932  lea     rcx, [rbp+var_28]
0x180024936  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18002493b  test    esi, esi
0x18002493d  js      short loc_1800249A1
0x18002493f  xor     r9d, r9d; dwFlags
0x180024942  mov     r8d, [rbx+8]; cbInput
0x180024946  mov     rdx, [rbx]; pbInput
0x180024949  mov     rcx, [rbp+hHash]; hHash
0x18002494d  call    cs:__imp_BCryptHashData
0x180024954  nop     dword ptr [rax+rax+00h]
0x180024959  mov     ebx, eax
0x18002495b  test    eax, eax
0x18002495d  js      short loc_1800249AE
0x18002495f  xor     r9d, r9d; dwFlags
0x180024962  mov     r8d, [rdi+8]; cbOutput
0x180024966  mov     rdx, [rdi]; pbOutput
0x180024969  mov     rcx, [rbp+hHash]; hHash
0x18002496d  call    cs:__imp_BCryptFinishHash
0x180024974  nop     dword ptr [rax+rax+00h]
0x180024979  mov     ebx, eax
0x18002497b  test    eax, eax
0x18002497d  js      short loc_1800249AE
0x18002497f  mov     rcx, [rbp+hHash]
0x180024983  test    rcx, rcx
0x180024986  jz      short loc_180024995
0x180024988  mov     rax, cs:__imp_BCryptDestroyHash
0x18002498f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024994  nop
0x180024995  xor     eax, eax
0x180024997  add     rsp, 68h
0x18002499b  pop     rdi
0x18002499c  pop     rsi
0x18002499d  pop     rbx
0x18002499e  pop     rbp
0x18002499f  retn
0x1800249a1  lea     rcx, [rbp+hHash]
0x1800249a5  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800249aa  mov     eax, esi
0x1800249ac  jmp     short loc_180024997
0x1800249ae  lea     rcx, [rbp+hHash]
0x1800249b2  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800249b7  mov     eax, ebx
0x1800249b9  jmp     short loc_180024997
```
