# winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(void)

- ea: `0x18001c0e4`
- end: `0x18001c1d6`
- name: `??D?$fast_iterator@UJsonArray@Json@Data@Windows@winrt@@@impl@winrt@@QEBA?AUIJsonValue@Json@Data@Windows@2@XZ`
- size: `242`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x1800066dc`
- `0x180017b60`
- `0x18001c0e4`
- `0x180029010`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::fast_iterator<winrt::Windows::Data::Json::JsonArray>::operator*(__int64 a1, _QWORD *a2)
{
  __int64 (__fastcall ****v3)(_QWORD, __int64 *, __int64 *); // rax
  unsigned int v4; // r14d
  __int64 (__fastcall ***v5)(_QWORD, __int64 *, __int64 *); // rcx
  int v6; // eax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, _QWORD *); // rsi
  int v9; // eax
  int v11; // [rsp+28h] [rbp-18h] BYREF
  __int128 v12; // [rsp+30h] [rbp-10h]
  __int64 v13; // [rsp+60h] [rbp+20h] BYREF
  _QWORD *v14; // [rsp+68h] [rbp+28h]

  v14 = a2;
  v3 = *(__int64 (__fastcall *****)(_QWORD, __int64 *, __int64 *))a1;
  v4 = *(_DWORD *)(a1 + 8);
  *a2 = 0;
  v5 = *v3;
  if ( *v3 )
  {
    v13 = 0;
    v6 = (**v5)(
           v5,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
           &v13);
    v7 = v13;
  }
  else
  {
    v6 = 0;
    v13 = 0;
    v7 = 0;
  }
  v11 = 0;
  v12 = 0;
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v11);
  v11 = 0;
  v12 = 0;
  v8 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v7 + 48LL);
  if ( *a2 )
    winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(a2);
  v9 = v8(v7, v4, a2);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v11);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v13);
  return a2;
}

```

## disassembly

```asm
0x18001c0e4  mov     [rsp-18h+arg_10], rbx
0x18001c0e9  mov     [rsp-18h+arg_18], rsi
0x18001c0ee  mov     [rsp-18h+arg_8], rdx
0x18001c0f3  push    rbp
0x18001c0f4  push    rdi
0x18001c0f5  push    r14
0x18001c0f7  mov     rbp, rsp
0x18001c0fa  sub     rsp, 40h
0x18001c0fe  mov     rbx, rdx
0x18001c101  mov     [rbp+var_20], 0
0x18001c108  mov     rax, [rcx]
0x18001c10b  mov     r14d, [rcx+8]
0x18001c10f  mov     qword ptr [rdx], 0
0x18001c116  mov     [rbp+var_20], 2
0x18001c11d  mov     rcx, [rax]
0x18001c120  test    rcx, rcx
0x18001c123  jnz     short loc_18001C12F
0x18001c125  xor     eax, eax
0x18001c127  mov     [rbp+arg_0], rax
0x18001c12b  xor     edi, edi
0x18001c12d  jmp     short loc_18001C155
0x18001c12f  mov     [rbp+arg_0], 0
0x18001c137  mov     rax, [rcx]
0x18001c13a  lea     r8, [rbp+arg_0]
0x18001c13e  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x18001c145  mov     rax, [rax]
0x18001c148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c14d  mov     rdi, [rbp+arg_0]
0x18001c151  mov     [rbp+arg_0], rdi
0x18001c155  mov     [rbp+var_18], 0
0x18001c15c  xorps   xmm0, xmm0
0x18001c15f  movdqu  [rbp+var_10], xmm0
0x18001c164  test    eax, eax
0x18001c166  js      short loc_18001C1CA
0x18001c168  mov     [rbp+var_18], 0
0x18001c16f  movdqu  [rbp+var_10], xmm0
0x18001c174  mov     rax, [rdi]
0x18001c177  mov     rsi, [rax+30h]
0x18001c17b  cmp     qword ptr [rbx], 0
0x18001c17f  jz      short loc_18001C189
0x18001c181  mov     rcx, rbx
0x18001c184  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001c189  mov     r8, rbx
0x18001c18c  mov     edx, r14d
0x18001c18f  mov     rcx, rdi
0x18001c192  mov     rax, rsi
0x18001c195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c19a  test    eax, eax
0x18001c19c  js      short loc_18001C1BE
0x18001c19e  lea     rcx, [rbp+arg_0]
0x18001c1a2  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18001c1a7  nop
0x18001c1a8  mov     rax, rbx
0x18001c1ab  mov     rbx, [rsp+40h+arg_10]
0x18001c1b0  mov     rsi, [rsp+40h+arg_18]
0x18001c1b5  add     rsp, 40h
0x18001c1b9  pop     r14
0x18001c1bb  pop     rdi
0x18001c1bc  pop     rbp
0x18001c1bd  retn
0x18001c1be  lea     rdx, [rbp+var_18]
0x18001c1c2  mov     ecx, eax
0x18001c1c4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001c1ca  lea     rdx, [rbp+var_18]
0x18001c1ce  mov     ecx, eax
0x18001c1d0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
