# Windows::UI::Internal::Popups::CMessageDialogParameters::~CMessageDialogParameters(void)

- ea: `0x18009c740`
- end: `0x18009c7bd`
- name: `??1CMessageDialogParameters@Popups@Internal@UI@Windows@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(Windows::UI::Internal::Popups::CMessageDialogParameters *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009c6c8`
- `0x1800a1710`

## callees

- `0x1800038e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c75f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c7a5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c75f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c770`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c7a5`

## pseudocode

```c
void __fastcall Windows::UI::Internal::Popups::CMessageDialogParameters::~CMessageDialogParameters(
        Windows::UI::Internal::Popups::CMessageDialogParameters *this)
{
  *(_QWORD *)((char *)this + 20) = 0;
  *((_DWORD *)this + 4) = 0;
  WindowsDeleteString(*(HSTRING *)this);
  *(_QWORD *)this = 0;
  WindowsDeleteString(*((HSTRING *)this + 1));
  *((_QWORD *)this + 1) = 0;
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 32);
  Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease((char *)this + 32);
  WindowsDeleteString(*((HSTRING *)this + 1));
  *((_QWORD *)this + 1) = 0;
  WindowsDeleteString(*(HSTRING *)this);
  *(_QWORD *)this = 0;
}

```

## disassembly

```asm
0x18009c740  mov     [rsp+arg_0], rbx
0x18009c745  push    rdi
0x18009c746  sub     rsp, 20h
0x18009c74a  mov     rdi, rcx
0x18009c74d  mov     qword ptr [rcx+14h], 0
0x18009c755  mov     dword ptr [rcx+10h], 0
0x18009c75c  mov     rcx, [rcx]; string
0x18009c75f  call    cs:__imp_WindowsDeleteString
0x18009c765  mov     qword ptr [rdi], 0
0x18009c76c  mov     rcx, [rdi+8]; string
0x18009c770  call    cs:__imp_WindowsDeleteString
0x18009c776  lea     rcx, [rdi+20h]
0x18009c77a  mov     qword ptr [rdi+8], 0
0x18009c782  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009c787  lea     rcx, [rdi+20h]
0x18009c78b  call    ?InternalRelease@?$ComPtr@UIDCompositionTarget@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionTarget>::InternalRelease(void)
0x18009c790  mov     rcx, [rdi+8]; string
0x18009c794  call    cs:__imp_WindowsDeleteString
0x18009c79a  mov     qword ptr [rdi+8], 0
0x18009c7a2  mov     rcx, [rdi]; string
0x18009c7a5  call    cs:__imp_WindowsDeleteString
0x18009c7ab  mov     rbx, [rsp+28h+arg_0]
0x18009c7b0  mov     qword ptr [rdi], 0
0x18009c7b7  add     rsp, 20h
0x18009c7bb  pop     rdi
0x18009c7bc  retn
```
