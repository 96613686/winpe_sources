# CACSecurityPage::GetCurrentlySelectedAuth(void)

- ea: `0x18000833c`
- end: `0x180008380`
- name: `?GetCurrentlySelectedAuth@CACSecurityPage@@QEAAPEAU_AUI_AUTH_INFO@@XZ`
- size: `68`
- prototype: `struct _AUI_AUTH_INFO *__fastcall(CACSecurityPage *__hidden this)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007604`
- `0x180008720`
- `0x1800092d0`
- `0x180009380`
- `0x180009dd0`
- `0x18000a29c`
- `0x18000a4b4`
- `0x18000a690`
- `0x18000b078`
- `0x18000c824`
- `0x18000cf08`
- `0x18000d3c4`
- `0x18000d714`
- `0x18000d834`
- `0x180012660`

## callees

- `0x1800060a0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000835a`
- `USER32!SendMessageW` at `0x18000835a`

## pseudocode

```c
struct _AUI_AUTH_INFO *__fastcall CACSecurityPage::GetCurrentlySelectedAuth(HWND *this)
{
  __int64 v2; // rdi
  int v3; // eax
  void *ItemDataPtr; // rax

  v2 = 0;
  v3 = SendMessageW(this[8], 0x147u, 0, 0);
  ItemDataPtr = ComboBox_GetItemDataPtr(this[8], v3);
  if ( ItemDataPtr )
    return (struct _AUI_AUTH_INFO *)ItemDataPtr;
  return (struct _AUI_AUTH_INFO *)v2;
}

```

## disassembly

```asm
0x18000833c  mov     [rsp+arg_0], rbx
0x180008341  push    rdi
0x180008342  sub     rsp, 20h
0x180008346  mov     rbx, rcx
0x180008349  xor     r9d, r9d; lParam
0x18000834c  mov     rcx, [rcx+40h]; hWnd
0x180008350  xor     r8d, r8d; wParam
0x180008353  mov     edx, 147h; Msg
0x180008358  xor     edi, edi
0x18000835a  call    cs:__imp_SendMessageW
0x180008360  mov     rcx, [rbx+40h]; HWND
0x180008364  mov     edx, eax; int
0x180008366  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x18000836b  mov     rbx, [rsp+28h+arg_0]
0x180008370  test    rax, rax
0x180008373  cmovnz  rdi, rax
0x180008377  mov     rax, rdi
0x18000837a  add     rsp, 20h
0x18000837e  pop     rdi
0x18000837f  retn
```
