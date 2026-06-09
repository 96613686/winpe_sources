# winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScopedBatch(winrt::Windows::UI::Composition::CompositionBatchTypes const &)

- ea: `0x1800121f4`
- end: `0x180012260`
- name: `?CreateScopedBatch@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBW4CompositionBatchTypes@Composition@UI@Windows@3@@Z`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x1800121f4`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x1800121ff`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScopedBatch(
        __int64 **a1,
        _QWORD *a2,
        unsigned int *a3)
{
  __int64 *v3; // rcx
  __int64 v5; // rax
  __int64 v6; // rdx
  int v7; // eax
  int v9; // [rsp+28h] [rbp-20h] BYREF
  const char *v10; // [rsp+30h] [rbp-18h]
  __int64 v11; // [rsp+38h] [rbp-10h]
  __int64 v12; // [rsp+50h] [rbp+8h] BYREF

  v3 = *a1;
  v9 = 7793;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v12 = 0;
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 168))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x1800121f4  mov     r11, rsp
0x1800121f7  push    rbx
0x1800121f8  sub     rsp, 40h
0x1800121fc  mov     rcx, [rcx]
0x1800121ff  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x180012206  mov     r9, r8
0x180012209  mov     [rsp+48h+var_20], 1E71h
0x180012211  mov     [r11-18h], rax
0x180012215  lea     r8, [r11+8]
0x180012219  mov     qword ptr [r11+8], 0
0x180012221  mov     rbx, rdx
0x180012224  mov     rax, [rcx]
0x180012227  mov     edx, [r9]
0x18001222a  mov     qword ptr [r11-10h], 0
0x180012232  mov     rax, [rax+0A8h]
0x180012239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001223e  test    eax, eax
0x180012240  js      short loc_180012253
0x180012242  mov     rax, [rsp+48h+arg_0]
0x180012247  mov     [rbx], rax
0x18001224a  mov     rax, rbx
0x18001224d  add     rsp, 40h
0x180012251  pop     rbx
0x180012252  retn
0x180012253  lea     rdx, [rsp+48h+var_20]
0x180012258  mov     ecx, eax
0x18001225a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
