# tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,_GUID * &>(_GUID * &)

- ea: `0x14001ecbc`
- end: `0x14001ed05`
- name: `??$tip_make_shared_nothrow@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@AEAPEAU_GUID@@@details@tip2@@YA?AV?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@AEAPEAU_GUID@@@Z`
- size: `73`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1400206e8`

## callees

- `0x140009694`
- `0x14001ecbc`
- `0x14001f1e0`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x14001ecd1`
- `ole32!CoTaskMemAlloc` at `0x14001ecd1`

## pseudocode

```c
_QWORD *__fastcall tip2::details::tip_make_shared_nothrow<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,_GUID * &>(
        _QWORD *a1,
        _QWORD *a2)
{
  LPVOID v4; // rax
  wil::details::in1diag3 *v5; // rcx

  v4 = CoTaskMemAlloc(0x118u);
  if ( !v4 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v5);
  *a1 = tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>(
          v4,
          *a2);
  return a1;
}

```

## disassembly

```asm
0x14001ecbc  mov     [rsp+arg_0], rbx
0x14001ecc1  push    rdi
0x14001ecc2  sub     rsp, 20h
0x14001ecc6  mov     rbx, rcx
0x14001ecc9  mov     rdi, rdx
0x14001eccc  mov     ecx, 118h; cb
0x14001ecd1  call    cs:__imp_CoTaskMemAlloc
0x14001ecd8  nop     dword ptr [rax+rax+00h]
0x14001ecdd  test    rax, rax
0x14001ece0  jz      short loc_14001ECFF
0x14001ece2  mov     rdx, [rdi]
0x14001ece5  mov     rcx, rax
0x14001ece8  call    ??0?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@QEAA@PEAU_GUID@@@Z; tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>(_GUID *)
0x14001eced  mov     [rbx], rax
0x14001ecf0  mov     rax, rbx
0x14001ecf3  mov     rbx, [rsp+28h+arg_0]
0x14001ecf8  add     rsp, 20h
0x14001ecfc  pop     rdi
0x14001ecfd  retn
0x14001ecff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
