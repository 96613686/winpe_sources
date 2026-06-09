# winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(void)

- ea: `0x1800256ac`
- end: `0x180025771`
- name: `?end@?$consume_Windows_Foundation_Collections_IIterable@UJsonArray@Json@Data@Windows@winrt@@UIJsonValue@2345@@impl@winrt@@QEBA@XZ`
- size: `197`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800227bc`

## callees

- `0x1800066dc`
- `0x180017b60`
- `0x1800256ac`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Data::Json::JsonArray,winrt::Windows::Data::Json::IJsonValue>::end(
        __int64 *a1,
        __int64 a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // eax
  int v8; // [rsp+20h] [rbp-20h] BYREF
  __int128 v9; // [rsp+28h] [rbp-18h]
  int v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v10 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v11 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>,
           &v11);
    v4 = v11;
  }
  else
  {
    v5 = 0;
    v11 = 0;
  }
  v8 = 0;
  v9 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v8);
  v8 = 0;
  v9 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v4 + 56LL))(v4, &v10);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6, &v8);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v11);
  *(_QWORD *)a2 = a1;
  *(_DWORD *)(a2 + 8) = v10;
  return a2;
}

```

## disassembly

```asm
0x1800256ac  mov     [rsp-8+arg_8], rbx
0x1800256b1  mov     [rsp-8+arg_18], rdi
0x1800256b6  push    rbp
0x1800256b7  mov     rbp, rsp
0x1800256ba  sub     rsp, 40h
0x1800256be  mov     rbx, rdx
0x1800256c1  mov     rdi, rcx
0x1800256c4  mov     [rbp+arg_0], 0
0x1800256cb  mov     rcx, [rcx]
0x1800256ce  test    rcx, rcx
0x1800256d1  jnz     short loc_1800256DB
0x1800256d3  xor     eax, eax
0x1800256d5  mov     [rbp+arg_10], rax
0x1800256d9  jmp     short loc_180025701
0x1800256db  mov     [rbp+arg_10], 0
0x1800256e3  mov     rax, [rcx]
0x1800256e6  lea     r8, [rbp+arg_10]
0x1800256ea  lea     rdx, ??$guid_v@U?$IVector@UIJsonValue@Json@Data@Windows@winrt@@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Data::Json::IJsonValue>>
0x1800256f1  mov     rax, [rax]
0x1800256f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256f9  mov     rcx, [rbp+arg_10]
0x1800256fd  mov     [rbp+arg_10], rcx
0x180025701  mov     [rbp+var_20], 0
0x180025708  xorps   xmm0, xmm0
0x18002570b  movdqu  [rbp+var_18], xmm0
0x180025710  test    eax, eax
0x180025712  js      short loc_180025765
0x180025714  mov     [rbp+var_20], 0
0x18002571b  movdqu  [rbp+var_18], xmm0
0x180025720  mov     rax, [rcx]
0x180025723  lea     rdx, [rbp+arg_0]
0x180025727  mov     rax, [rax+38h]
0x18002572b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025730  test    eax, eax
0x180025732  js      short loc_180025759
0x180025734  lea     rcx, [rbp+arg_10]
0x180025738  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x18002573d  mov     [rbx], rdi
0x180025740  mov     eax, [rbp+arg_0]
0x180025743  mov     [rbx+8], eax
0x180025746  mov     rax, rbx
0x180025749  mov     rbx, [rsp+40h+arg_8]
0x18002574e  mov     rdi, [rsp+40h+arg_18]
0x180025753  add     rsp, 40h
0x180025757  pop     rbp
0x180025758  retn
0x180025759  lea     rdx, [rbp+var_20]
0x18002575d  mov     ecx, eax
0x18002575f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180025765  lea     rdx, [rbp+var_20]
0x180025769  mov     ecx, eax
0x18002576b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
