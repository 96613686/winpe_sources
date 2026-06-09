# winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::CompositionBrush>::Comment(void)

- ea: `0x18001e040`
- end: `0x18001e109`
- name: `?Comment@?$consume_Windows_UI_Composition_ICompositionObject2@UCompositionBrush@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x180012040`
- `0x18001e040`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x18001e095`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositionObject2<winrt::Windows::UI::Composition::CompositionBrush>::Comment(
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
           winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>,
           &v10);
    v3 = v10;
  }
  else
  {
    v4 = 0;
    v10 = 0;
  }
  v7 = 4458;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v9 = 0;
  if ( v4 < 0 )
    winrt::throw_hresult((unsigned int)v4, &v7);
  v7 = 4460;
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
0x18001e040  mov     [rsp-8+arg_8], rbx
0x18001e045  push    rbp
0x18001e046  mov     rbp, rsp
0x18001e049  sub     rsp, 40h
0x18001e04d  mov     rbx, rdx
0x18001e050  mov     [rbp+arg_10], 0
0x18001e058  mov     rcx, [rcx]
0x18001e05b  test    rcx, rcx
0x18001e05e  jnz     short loc_18001E068
0x18001e060  xor     eax, eax
0x18001e062  mov     [rbp+arg_0], rax
0x18001e066  jmp     short loc_18001E08E
0x18001e068  mov     [rbp+arg_0], 0
0x18001e070  mov     rax, [rcx]
0x18001e073  lea     r8, [rbp+arg_0]
0x18001e077  lea     rdx, ??$guid_v@UICompositionObject2@Composition@UI@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::UI::Composition::ICompositionObject2>
0x18001e07e  mov     rax, [rax]
0x18001e081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e086  mov     rcx, [rbp+arg_0]
0x18001e08a  mov     [rbp+arg_0], rcx
0x18001e08e  mov     [rbp+var_18], 116Ah
0x18001e095  lea     rdx, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001e09c  mov     [rbp+var_10], rdx
0x18001e0a0  mov     [rbp+var_8], 0
0x18001e0a8  test    eax, eax
0x18001e0aa  jns     short loc_18001E0B8
0x18001e0ac  lea     rdx, [rbp+var_18]
0x18001e0b0  mov     ecx, eax
0x18001e0b2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e0b8  mov     [rbp+var_18], 116Ch
0x18001e0bf  mov     [rbp+var_10], rdx
0x18001e0c3  mov     [rbp+var_8], 0
0x18001e0cb  mov     rax, [rcx]
0x18001e0ce  lea     rdx, [rbp+arg_10]
0x18001e0d2  mov     rax, [rax+30h]
0x18001e0d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0db  test    eax, eax
0x18001e0dd  jns     short loc_18001E0EB
0x18001e0df  lea     rdx, [rbp+var_18]
0x18001e0e3  mov     ecx, eax
0x18001e0e5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001e0eb  lea     rcx, [rbp+arg_0]
0x18001e0ef  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001e0f4  mov     rax, [rbp+arg_10]
0x18001e0f8  mov     [rbx], rax
0x18001e0fb  mov     rax, rbx
0x18001e0fe  mov     rbx, [rsp+40h+arg_8]
0x18001e103  add     rsp, 40h
0x18001e107  pop     rbp
0x18001e108  retn
```
