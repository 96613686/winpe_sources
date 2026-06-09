# tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::Release(void)

- ea: `0x14000ee10`
- end: `0x14000ee4f`
- name: `?Release@?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@AEAAKXZ`
- size: `63`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14000ccf8`
- `0x14000d32c`

## callees

- `0x14000cec0`
- `0x14000ee10`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x14000ee35`
- `ole32!CoTaskMemFree` at `0x14000ee35`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 68);
  if ( !v2 )
  {
    tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::~merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x14000ee10  mov     [rsp+arg_0], rbx
0x14000ee15  push    rdi
0x14000ee16  sub     rsp, 20h
0x14000ee1a  mov     rdi, rcx
0x14000ee1d  or      ebx, 0FFFFFFFFh
0x14000ee20  lock xadd [rcx+110h], ebx
0x14000ee28  sub     ebx, 1
0x14000ee2b  jnz     short loc_14000EE41
0x14000ee2d  call    ??1?$merged_data@U_tip_AccessibilityDialogFlyoutLaunchTest@@U1@@details@tip2@@QEAA@XZ; tip2::details::merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>::~merged_data<_tip_AccessibilityDialogFlyoutLaunchTest,_tip_AccessibilityDialogFlyoutLaunchTest>(void)
0x14000ee32  mov     rcx, rdi; pv
0x14000ee35  call    cs:__imp_CoTaskMemFree
0x14000ee3c  nop     dword ptr [rax+rax+00h]
0x14000ee41  mov     eax, ebx
0x14000ee43  mov     rbx, [rsp+28h+arg_0]
0x14000ee48  add     rsp, 20h
0x14000ee4c  pop     rdi
0x14000ee4d  retn
```
