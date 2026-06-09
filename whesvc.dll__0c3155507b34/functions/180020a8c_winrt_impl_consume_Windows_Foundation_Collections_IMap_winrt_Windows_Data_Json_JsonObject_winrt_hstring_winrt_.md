# winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(winrt::param::hstring const &)

- ea: `0x180020a8c`
- end: `0x180020b3b`
- name: `?HasKey@?$consume_Windows_Foundation_Collections_IMap@UJsonObject@Json@Data@Windows@winrt@@Uhstring@5@UIJsonValue@2345@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z`
- size: `175`
- prototype: `char __fastcall(__int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x1800066dc`
- `0x180017b60`
- `0x180020a8c`
- `0x180029010`

## pseudocode

```c
char __fastcall winrt::impl::consume_Windows_Foundation_Collections_IMap<winrt::Windows::Data::Json::JsonObject,winrt::hstring,winrt::Windows::Data::Json::IJsonValue>::HasKey(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+20h] [rbp-20h] BYREF
  __int128 v8; // [rsp+28h] [rbp-18h]
  char v9; // [rsp+50h] [rbp+10h] BYREF
  __int64 v10; // [rsp+60h] [rbp+20h] BYREF

  v9 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 0;
  v8 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 0;
  v8 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, char *))(*(_QWORD *)v3 + 64LL))(v3, *a2, &v9);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v10);
  return v9;
}

```

## disassembly

```asm
0x180020a8c  mov     [rsp-8+arg_8], rbx
0x180020a91  push    rbp
0x180020a92  mov     rbp, rsp
0x180020a95  sub     rsp, 40h
0x180020a99  mov     rbx, rdx
0x180020a9c  mov     [rbp+arg_0], 0
0x180020aa0  mov     rcx, [rcx]
0x180020aa3  test    rcx, rcx
0x180020aa6  jnz     short loc_180020AB0
0x180020aa8  xor     eax, eax
0x180020aaa  mov     [rbp+arg_10], rax
0x180020aae  jmp     short loc_180020AD6
0x180020ab0  mov     [rbp+arg_10], 0
0x180020ab8  mov     rax, [rcx]
0x180020abb  lea     r8, [rbp+arg_10]
0x180020abf  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIJsonValue@Json@Data@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Data::Json::IJsonValue>>
0x180020ac6  mov     rax, [rax]
0x180020ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ace  mov     rcx, [rbp+arg_10]
0x180020ad2  mov     [rbp+arg_10], rcx
0x180020ad6  mov     [rbp+var_20], 0
0x180020add  xorps   xmm0, xmm0
0x180020ae0  movdqu  [rbp+var_18], xmm0
0x180020ae5  test    eax, eax
0x180020ae7  js      short loc_180020B2F
0x180020ae9  mov     [rbp+var_20], 0
0x180020af0  movdqu  [rbp+var_18], xmm0
0x180020af5  mov     rax, [rcx]
0x180020af8  lea     r8, [rbp+arg_0]
0x180020afc  mov     rdx, [rbx]
0x180020aff  mov     rax, [rax+40h]
0x180020b03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b08  test    eax, eax
0x180020b0a  js      short loc_180020B23
0x180020b0c  lea     rcx, [rbp+arg_10]
0x180020b10  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180020b15  mov     al, [rbp+arg_0]
0x180020b18  mov     rbx, [rsp+40h+arg_8]
0x180020b1d  add     rsp, 40h
0x180020b21  pop     rbp
0x180020b22  retn
0x180020b23  lea     rdx, [rbp+var_20]
0x180020b27  mov     ecx, eax
0x180020b29  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180020b2f  lea     rdx, [rbp+var_20]
0x180020b33  mov     ecx, eax
0x180020b35  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
