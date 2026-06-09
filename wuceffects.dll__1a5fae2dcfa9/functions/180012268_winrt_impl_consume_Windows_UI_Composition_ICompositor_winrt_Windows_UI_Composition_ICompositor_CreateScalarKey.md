# winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScalarKeyFrameAnimation(void)

- ea: `0x180012268`
- end: `0x1800122ce`
- name: `?CreateScalarKeyFrameAnimation@?$consume_Windows_UI_Composition_ICompositor@UICompositor@Composition@UI@Windows@winrt@@@impl@winrt@@QEBA@XZ`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011590`

## callees

- `0x180012268`
- `0x18002ad8c`
- `0x18002e010`

## string_xrefs

- `0x180012273`: `onecoreuap\Internal\BuildMetadata\internal\cppwinrt\winrt\windows.ui.composition.h`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::consume_Windows_UI_Composition_ICompositor<winrt::Windows::UI::Composition::ICompositor>::CreateScalarKeyFrameAnimation(
        __int64 **a1,
        _QWORD *a2)
{
  __int64 *v2; // rcx
  __int64 v4; // rax
  int v5; // eax
  int v7; // [rsp+28h] [rbp-20h] BYREF
  const char *v8; // [rsp+30h] [rbp-18h]
  __int64 v9; // [rsp+38h] [rbp-10h]
  __int64 v10; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a1;
  v7 = 7775;
  v8 = "onecoreuap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.ui.composition.h";
  v10 = 0;
  v4 = *v2;
  v9 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v4 + 160))(v2, &v10);
  if ( v5 < 0 )
    winrt::throw_hresult((unsigned int)v5, &v7);
  *a2 = v10;
  return a2;
}

```

## disassembly

```asm
0x180012268  mov     r11, rsp
0x18001226b  push    rbx
0x18001226c  sub     rsp, 40h
0x180012270  mov     rcx, [rcx]
0x180012273  lea     rax, aOnecoreuapInte; "onecoreuap\\Internal\\BuildMetadata\\in"...
0x18001227a  mov     [rsp+48h+var_20], 1E5Fh
0x180012282  mov     rbx, rdx
0x180012285  mov     [r11-18h], rax
0x180012289  lea     rdx, [r11+8]
0x18001228d  mov     qword ptr [r11+8], 0
0x180012295  mov     rax, [rcx]
0x180012298  mov     qword ptr [r11-10h], 0
0x1800122a0  mov     rax, [rax+0A0h]
0x1800122a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ac  test    eax, eax
0x1800122ae  js      short loc_1800122C1
0x1800122b0  mov     rax, [rsp+48h+arg_0]
0x1800122b5  mov     [rbx], rax
0x1800122b8  mov     rax, rbx
0x1800122bb  add     rsp, 40h
0x1800122bf  pop     rbx
0x1800122c0  retn
0x1800122c1  lea     rdx, [rsp+48h+var_20]
0x1800122c6  mov     ecx, eax
0x1800122c8  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
