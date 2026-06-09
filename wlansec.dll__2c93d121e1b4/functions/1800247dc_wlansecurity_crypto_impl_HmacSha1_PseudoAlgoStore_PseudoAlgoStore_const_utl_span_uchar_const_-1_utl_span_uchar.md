# wlansecurity::crypto::impl::HmacSha1<PseudoAlgoStore>(PseudoAlgoStore const &,utl::span<uchar const,-1>,utl::span<uchar const,-1>,utl::span<uchar,-1>)

- ea: `0x1800247dc`
- end: `0x1800248cd`
- name: `??$HmacSha1@VPseudoAlgoStore@@@impl@crypto@wlansecurity@@YAJAEBVPseudoAlgoStore@@V?$span@$$CBE$0?0@utl@@1V?$span@E$0?0@5@@Z`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800246b0`

## callees

- `0x1800247dc`
- `0x1800249c4`
- `0x180033650`
- `0x180096010`

## import_xrefs

- `bcrypt!BCryptDestroyHash` at `0x1800248a3`
- `bcrypt!BCryptFinishHash` at `0x180024888`
- `bcrypt!BCryptFinishHash` at `0x180024888`
- `bcrypt!BCryptHashData` at `0x180024869`
- `bcrypt!BCryptHashData` at `0x180024869`
- `bcrypt!BCryptCreateHash` at `0x180024841`
- `bcrypt!BCryptCreateHash` at `0x180024841`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wlansecurity::crypto::impl::HmacSha1<PseudoAlgoStore>(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  UCHAR *v4; // rdi
  ULONG v5; // esi
  UCHAR *v6; // r14
  ULONG v7; // r15d
  NTSTATUS v8; // ebx
  BCRYPT_HASH_HANDLE *p_hHash; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  char v12; // [rsp+50h] [rbp-18h]
  BCRYPT_HASH_HANDLE hHash; // [rsp+A0h] [rbp+38h] BYREF

  hHash = a1;
  v4 = *(UCHAR **)a4;
  v5 = *(_DWORD *)(a4 + 8);
  v6 = *(UCHAR **)a2;
  v7 = *(_DWORD *)(a2 + 8);
  hHash = 0;
  p_hHash = &hHash;
  phHash = 0;
  v12 = 1;
  v8 = BCryptCreateHash((BCRYPT_ALG_HANDLE)0xA1, &phHash, 0, 0, *(PUCHAR *)a3, *(_DWORD *)(a3 + 8), 0);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hHash);
  if ( v8 < 0 || (v8 = BCryptHashData(hHash, v6, v7, 0), v8 < 0) || (v8 = BCryptFinishHash(hHash, v4, v5, 0), v8 < 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&long BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hHash);
  }
  else
  {
    if ( hHash )
      ((void (*)(void))BCryptDestroyHash)();
    return 0;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800247dc  mov     [rsp-30h+hHash], rcx
0x1800247e1  push    rbp
0x1800247e2  push    rbx
0x1800247e3  push    rsi
0x1800247e4  push    rdi
0x1800247e5  push    r14
0x1800247e7  push    r15
0x1800247e9  mov     rbp, rsp
0x1800247ec  sub     rsp, 68h
0x1800247f0  mov     rdi, [r9]
0x1800247f3  mov     esi, [r9+8]
0x1800247f7  mov     r14, [rdx]
0x1800247fa  mov     r15d, [rdx+8]
0x1800247fe  mov     [rbp+hHash], 0
0x180024806  lea     rax, [rbp+hHash]
0x18002480a  mov     [rbp+var_28], rax
0x18002480e  mov     [rbp+phHash], 0
0x180024816  mov     [rbp+var_18], 1
0x18002481a  mov     [rsp+68h+dwFlags], 0; dwFlags
0x180024822  mov     eax, [r8+8]
0x180024826  mov     [rsp+68h+cbSecret], eax; cbSecret
0x18002482a  mov     rax, [r8]
0x18002482d  mov     [rsp+68h+pbSecret], rax; pbSecret
0x180024832  xor     r9d, r9d; cbHashObject
0x180024835  xor     r8d, r8d; pbHashObject
0x180024838  lea     rdx, [rbp+phHash]; phHash
0x18002483c  mov     ecx, 0A1h; hAlgorithm
0x180024841  call    cs:__imp_BCryptCreateHash
0x180024848  nop     dword ptr [rax+rax+00h]
0x18002484d  mov     ebx, eax
0x18002484f  lea     rcx, [rbp+var_28]
0x180024853  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180024858  test    ebx, ebx
0x18002485a  js      short loc_1800248C2
0x18002485c  xor     r9d, r9d; dwFlags
0x18002485f  mov     r8d, r15d; cbInput
0x180024862  mov     rdx, r14; pbInput
0x180024865  mov     rcx, [rbp+hHash]; hHash
0x180024869  call    cs:__imp_BCryptHashData
0x180024870  nop     dword ptr [rax+rax+00h]
0x180024875  mov     ebx, eax
0x180024877  test    eax, eax
0x180024879  js      short loc_1800248C2
0x18002487b  xor     r9d, r9d; dwFlags
0x18002487e  mov     r8d, esi; cbOutput
0x180024881  mov     rdx, rdi; pbOutput
0x180024884  mov     rcx, [rbp+hHash]; hHash
0x180024888  call    cs:__imp_BCryptFinishHash
0x18002488f  nop     dword ptr [rax+rax+00h]
0x180024894  mov     ebx, eax
0x180024896  test    eax, eax
0x180024898  js      short loc_1800248C2
0x18002489a  mov     rcx, [rbp+hHash]
0x18002489e  test    rcx, rcx
0x1800248a1  jz      short loc_1800248B0
0x1800248a3  mov     rax, cs:__imp_BCryptDestroyHash
0x1800248aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248af  nop
0x1800248b0  xor     ebx, ebx
0x1800248b2  mov     eax, ebx
0x1800248b4  add     rsp, 68h
0x1800248b8  pop     r15
0x1800248ba  pop     r14
0x1800248bc  pop     rdi
0x1800248bd  pop     rsi
0x1800248be  pop     rbx
0x1800248bf  pop     rbp
0x1800248c0  retn
0x1800248c2  lea     rcx, [rbp+hHash]
0x1800248c6  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AJPEAX@Z$1?BCryptDestroyHash@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (void *),&BCryptDestroyHash(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800248cb  jmp     short loc_1800248B2
```
