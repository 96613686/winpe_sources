# Windows::UI::Core::CCoreWindowResizeManager::put_ShouldWaitForLayoutCompletion(uchar)

- ea: `0x18007ef50`
- end: `0x18007ef7e`
- name: `?put_ShouldWaitForLayoutCompletion@CCoreWindowResizeManager@Core@UI@Windows@@UEAAJE@Z`
- size: `46`
- prototype: `__int64 __fastcall(Windows::UI::Core::CCoreWindowResizeManager *__hidden this, unsigned __int8)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18007ef50`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18007ef71`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RemovePropW` at `0x18007ef71`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18007ef69`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetPropW` at `0x18007ef69`

## string_xrefs

- `0x18007ef5a`: `CoreWindowResizeManager_ShouldWaitForLayoutCompletion`

## pseudocode

```c
__int64 __fastcall Windows::UI::Core::CCoreWindowResizeManager::put_ShouldWaitForLayoutCompletion(
        Windows::UI::Core::CCoreWindowResizeManager *this,
        char a2)
{
  HWND v2; // rcx

  v2 = (HWND)*((_QWORD *)this + 6);
  if ( a2 )
    SetPropW(v2, L"CoreWindowResizeManager_ShouldWaitForLayoutCompletion", HANDLE_FLAG_INHERIT);
  else
    RemovePropW(v2, L"CoreWindowResizeManager_ShouldWaitForLayoutCompletion");
  return 0;
}

```

## disassembly

```asm
0x18007ef50  sub     rsp, 28h
0x18007ef54  mov     rcx, [rcx+30h]; hWnd
0x18007ef58  test    dl, dl
0x18007ef5a  lea     rdx, aCorewindowresi; "CoreWindowResizeManager_ShouldWaitForLa"...
0x18007ef61  jz      short loc_18007EF71
0x18007ef63  mov     r8d, 1; hData
0x18007ef69  call    cs:__imp_SetPropW
0x18007ef6f  jmp     short loc_18007EF77
0x18007ef71  call    cs:__imp_RemovePropW
0x18007ef77  xor     eax, eax
0x18007ef79  add     rsp, 28h
0x18007ef7d  retn
```
