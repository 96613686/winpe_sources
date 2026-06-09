# winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(void)

- ea: `0x180023ae8`
- end: `0x180023b9f`
- name: `?Stringify@?$consume_Windows_Data_Json_IJsonValue@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020634`

## callees

- `0x1800066dc`
- `0x180017b60`
- `0x180023ae8`
- `0x180029010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_Data_Json_IJsonValue<winrt::Windows::Data::Json::IJsonObject>::Stringify(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rcx
  signed int v5; // eax
  signed int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+28h] [rbp-18h] BYREF
  __int128 v10; // [rsp+30h] [rbp-10h]
  __int64 v11; // [rsp+50h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF

  v12 = 0;
  v4 = *a1;
  if ( v4 )
  {
    v11 = 0;
    v5 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v4)(
           v4,
           winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>,
           &v11);
    v4 = v11;
  }
  else
  {
    v5 = 0;
    v11 = 0;
  }
  v9 = 0;
  v10 = 0;
  if ( v5 < 0 )
    winrt::throw_hresult(v5, &v9, a3);
  v9 = 0;
  v10 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v4 + 56LL))(v4, &v12);
  if ( v6 < 0 )
    winrt::throw_hresult(v6, &v9, v7);
  winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(&v11);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x180023ae8  mov     [rsp-8+arg_8], rbx
0x180023aed  push    rbp
0x180023aee  mov     rbp, rsp
0x180023af1  sub     rsp, 40h
0x180023af5  mov     rbx, rdx
0x180023af8  mov     [rbp+arg_10], 0
0x180023b00  mov     rcx, [rcx]
0x180023b03  test    rcx, rcx
0x180023b06  jnz     short loc_180023B10
0x180023b08  xor     eax, eax
0x180023b0a  mov     [rbp+arg_0], rax
0x180023b0e  jmp     short loc_180023B36
0x180023b10  mov     [rbp+arg_0], 0
0x180023b18  mov     rax, [rcx]
0x180023b1b  lea     r8, [rbp+arg_0]
0x180023b1f  lea     rdx, ??$guid_v@UIJsonValue@Json@Data@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Data::Json::IJsonValue>
0x180023b26  mov     rax, [rax]
0x180023b29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b2e  mov     rcx, [rbp+arg_0]
0x180023b32  mov     [rbp+arg_0], rcx
0x180023b36  mov     [rbp+var_18], 0
0x180023b3d  xorps   xmm0, xmm0
0x180023b40  movdqu  [rbp+var_10], xmm0
0x180023b45  test    eax, eax
0x180023b47  js      short loc_180023B93
0x180023b49  mov     [rbp+var_18], 0
0x180023b50  movdqu  [rbp+var_10], xmm0
0x180023b55  mov     rax, [rcx]
0x180023b58  lea     rdx, [rbp+arg_10]
0x180023b5c  mov     rax, [rax+38h]
0x180023b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023b65  test    eax, eax
0x180023b67  js      short loc_180023B87
0x180023b69  lea     rcx, [rbp+arg_0]
0x180023b6d  call    ?unconditional_release_ref@?$com_ptr@UIAgileObject@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IAgileObject>::unconditional_release_ref(void)
0x180023b72  mov     rax, [rbp+arg_10]
0x180023b76  mov     [rbx], rax
0x180023b79  mov     rax, rbx
0x180023b7c  mov     rbx, [rsp+40h+arg_8]
0x180023b81  add     rsp, 40h
0x180023b85  pop     rbp
0x180023b86  retn
0x180023b87  lea     rdx, [rbp+var_18]
0x180023b8b  mov     ecx, eax
0x180023b8d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180023b93  lea     rdx, [rbp+var_18]
0x180023b97  mov     ecx, eax
0x180023b99  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
