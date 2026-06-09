# winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateColorBrush(winrt::Windows::UI::Color const &)

- ea: `0x1800101b4`
- end: `0x18001021d`
- name: `?CreateColorBrush@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@AEBUColor@UI@Windows@3@@Z`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010c58`

## callees

- `0x1800101b4`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x1800101bf`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateColorBrush(
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
  v12 = 0;
  v9 = 7559;
  v10 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v5 = *v3;
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 *))(v5 + 64))(v3, v6, &v12);
  if ( v7 < 0 )
    winrt::throw_hresult((unsigned int)v7, &v9);
  *a2 = v12;
  return a2;
}

```

## disassembly

```asm
0x1800101b4  mov     r11, rsp
0x1800101b7  push    rbx
0x1800101b8  sub     rsp, 40h
0x1800101bc  mov     rcx, [rcx]
0x1800101bf  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x1800101c6  mov     qword ptr [r11+8], 0
0x1800101ce  mov     r9, r8
0x1800101d1  mov     [rsp+48h+var_20], 1D87h
0x1800101d9  lea     r8, [r11+8]
0x1800101dd  mov     [r11-18h], rax
0x1800101e1  mov     rbx, rdx
0x1800101e4  mov     rax, [rcx]
0x1800101e7  mov     edx, [r9]
0x1800101ea  mov     qword ptr [r11-10h], 0
0x1800101f2  mov     rax, [rax+40h]
0x1800101f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101fb  test    eax, eax
0x1800101fd  jns     short loc_18001020C
0x1800101ff  lea     rdx, [rsp+48h+var_20]
0x180010204  mov     ecx, eax
0x180010206  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001020c  mov     rax, [rsp+48h+arg_0]
0x180010211  mov     [rbx], rax
0x180010214  mov     rax, rbx
0x180010217  add     rsp, 40h
0x18001021b  pop     rbx
0x18001021c  retn
```
