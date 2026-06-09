# wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(void)

- ea: `0x14000ccf8`
- end: `0x14000cd0f`
- name: `??1?$com_ptr_t@V?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000cf60`
- `0x14000cf88`
- `0x14000e72c`
- `0x14000ffc0`
- `0x1400206e8`

## callees

- `0x14000ccf8`
- `0x14000ee10`

## pseudocode

```c
__int64 __fastcall wil::com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>,wil::err_returncode_policy>(
        volatile signed __int32 **a1)
{
  volatile signed __int32 *v1; // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::Release(v1);
  return result;
}

```

## disassembly

```asm
0x14000ccf8  sub     rsp, 28h
0x14000ccfc  mov     rcx, [rcx]; pv
0x14000ccff  test    rcx, rcx
0x14000cd02  jz      short loc_14000CD09
0x14000cd04  call    ?Release@?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::Release(void)
0x14000cd09  add     rsp, 28h
0x14000cd0d  retn
```
