# winrt::impl::consume_Windows_UI_Composition_ICompositor3<winrt::Windows::UI::Composition::Compositor>::CreateHostBackdropBrush(void)

- ea: `0x18001e110`
- end: `0x18001e1d9`
- name: `?CreateHostBackdropBrush@?$consume_Windows_UI_Composition_ICompositor3@UCompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180010aac`

## callees

- `0x180012040`
- `0x18001e110`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001e165`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor3<winrt::Windows::UI::Composition::Compositor>::CreateHostBackdropBrush(
        __int64 *a1,
        _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-18h] BYREF
  const char *v8; // [rsp+30h] [rbp-10h]
  __int64 v9; // [rsp+38h] [rbp-8h]
  __int64 v10; // [rsp+50h] [rbp+10h] BYREF
  __int64 v11; // [rsp+60h] [rbp+20h] BYREF

  v11 = 0;
  v3 = *a1;
  if ( v3 )
  {
    v10 = 0;
    v4 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v3)(
           v3,
           winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositor3>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 8182;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 8184;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v11);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v10);
  *a2 = v11;
  return a2;
}

```

## disassembly

```asm
0x18001e110  mov     [rsp-8+arg_8], rbx
0x18001e115  push    rbp
0x18001e116  mov     rbp, rsp
0x18001e119  sub     rsp, 40h
0x18001e11d  mov     rbx, rdx
0x18001e120  mov     [rbp+arg_10], 0
0x18001e128  mov     rcx, [rcx]
0x18001e12b  test    rcx, rcx
0x18001e12e  jnz     short loc_18001E138
0x18001e130  xor     eax, eax
0x18001e132  mov     [rbp+arg_0], rax
0x18001e136  jmp     short loc_18001E15E
0x18001e138  mov     [rbp+arg_0], 0
0x18001e140  mov     rax, [rcx]
0x18001e143  lea     r8, [rbp+arg_0]
0x18001e147  lea     rdx, ??$guid_v@UICompositor3@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositor3>
0x18001e14e  mov     rax, [rax]
0x18001e151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e156  mov     rcx, [rbp+arg_0]
0x18001e15a  mov     [rbp+arg_0], rcx
0x18001e15e  mov     [rbp+var_18], 1FF6h
0x18001e165  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001e16c  mov     [rbp+var_10], rdx
0x18001e170  mov     [rbp+var_8], 0
0x18001e178  test    eax, eax
0x18001e17a  jns     short loc_18001E188
0x18001e17c  lea     rdx, [rbp+var_18]
0x18001e180  mov     ecx, eax
0x18001e182  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e188  mov     [rbp+var_18], 1FF8h
0x18001e18f  mov     [rbp+var_10], rdx
0x18001e193  mov     [rbp+var_8], 0
0x18001e19b  mov     rax, [rcx]
0x18001e19e  lea     rdx, [rbp+arg_10]
0x18001e1a2  mov     rax, [rax+30h]
0x18001e1a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ab  test    eax, eax
0x18001e1ad  jns     short loc_18001E1BB
0x18001e1af  lea     rdx, [rbp+var_18]
0x18001e1b3  mov     ecx, eax
0x18001e1b5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e1bb  lea     rcx, [rbp+arg_0]
0x18001e1bf  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e1c4  mov     rax, [rbp+arg_10]
0x18001e1c8  mov     [rbx], rax
0x18001e1cb  mov     rax, rbx
0x18001e1ce  mov     rbx, [rsp+40h+arg_8]
0x18001e1d3  add     rsp, 40h
0x18001e1d7  pop     rbp
0x18001e1d8  retn
```
