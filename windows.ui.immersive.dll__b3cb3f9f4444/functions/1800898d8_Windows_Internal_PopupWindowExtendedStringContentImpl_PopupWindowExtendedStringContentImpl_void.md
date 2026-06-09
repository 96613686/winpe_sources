# Windows::Internal::PopupWindowExtendedStringContentImpl::~PopupWindowExtendedStringContentImpl(void)

- ea: `0x1800898d8`
- end: `0x18008993e`
- name: `??1PopupWindowExtendedStringContentImpl@Internal@Windows@@UEAA@XZ`
- size: `102`
- prototype: `void __fastcall(Windows::Internal::PopupWindowExtendedStringContentImpl *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180089ed0`

## callees

- `0x18004bb80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800898e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800898f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089925`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800898e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800898f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089905`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089915`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180089925`

## pseudocode

```c
void __fastcall Windows::Internal::PopupWindowExtendedStringContentImpl::~PopupWindowExtendedStringContentImpl(
        LPVOID *this)
{
  CoTaskMemFree(this[9]);
  CoTaskMemFree(this[7]);
  CoTaskMemFree(this[6]);
  CoTaskMemFree(this[5]);
  CoTaskMemFree(this[4]);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>(this);
}

```

## disassembly

```asm
0x1800898d8  push    rbx
0x1800898da  sub     rsp, 20h
0x1800898de  mov     rbx, rcx
0x1800898e1  mov     rcx, [rcx+48h]; pv
0x1800898e5  call    cs:__imp_CoTaskMemFree
0x1800898ec  nop     dword ptr [rax+rax+00h]
0x1800898f1  mov     rcx, [rbx+38h]; pv
0x1800898f5  call    cs:__imp_CoTaskMemFree
0x1800898fc  nop     dword ptr [rax+rax+00h]
0x180089901  mov     rcx, [rbx+30h]; pv
0x180089905  call    cs:__imp_CoTaskMemFree
0x18008990c  nop     dword ptr [rax+rax+00h]
0x180089911  mov     rcx, [rbx+28h]; pv
0x180089915  call    cs:__imp_CoTaskMemFree
0x18008991c  nop     dword ptr [rax+rax+00h]
0x180089921  mov     rcx, [rbx+20h]; pv
0x180089925  call    cs:__imp_CoTaskMemFree
0x18008992c  nop     dword ptr [rax+rax+00h]
0x180089931  mov     rcx, rbx
0x180089934  add     rsp, 20h
0x180089938  pop     rbx
0x180089939  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICoreWindowPopupShowingEventArgs@Core@UI@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::UI::Core::ICoreWindowPopupShowingEventArgs>(void)
```
