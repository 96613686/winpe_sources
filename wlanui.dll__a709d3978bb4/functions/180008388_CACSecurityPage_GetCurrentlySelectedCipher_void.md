# CACSecurityPage::GetCurrentlySelectedCipher(void)

- ea: `0x180008388`
- end: `0x1800083cc`
- name: `?GetCurrentlySelectedCipher@CACSecurityPage@@QEAAPEAU_AUI_CIPHER_INFO@@XZ`
- size: `68`
- prototype: `struct _AUI_CIPHER_INFO *__fastcall(CACSecurityPage *__hidden this)`
- caller_count: `13`
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
- `0x18000c824`
- `0x18000cf08`
- `0x18000d3c4`
- `0x18000d714`
- `0x18000d834`
- `0x180012660`

## callees

- `0x1800060a0`

## import_xrefs

- `USER32!SendMessageW` at `0x1800083a6`
- `USER32!SendMessageW` at `0x1800083a6`

## pseudocode

```c
struct _AUI_CIPHER_INFO *__fastcall CACSecurityPage::GetCurrentlySelectedCipher(HWND *this)
{
  __int64 v2; // rdi
  int v3; // eax
  void *ItemDataPtr; // rax

  v2 = 0;
  v3 = SendMessageW(this[9], 0x147u, 0, 0);
  ItemDataPtr = ComboBox_GetItemDataPtr(this[9], v3);
  if ( ItemDataPtr )
    return (struct _AUI_CIPHER_INFO *)ItemDataPtr;
  return (struct _AUI_CIPHER_INFO *)v2;
}

```

## disassembly

```asm
0x180008388  mov     [rsp+arg_0], rbx
0x18000838d  push    rdi
0x18000838e  sub     rsp, 20h
0x180008392  mov     rbx, rcx
0x180008395  xor     r9d, r9d; lParam
0x180008398  mov     rcx, [rcx+48h]; hWnd
0x18000839c  xor     r8d, r8d; wParam
0x18000839f  mov     edx, 147h; Msg
0x1800083a4  xor     edi, edi
0x1800083a6  call    cs:__imp_SendMessageW
0x1800083ac  mov     rcx, [rbx+48h]; HWND
0x1800083b0  mov     edx, eax; int
0x1800083b2  call    ?ComboBox_GetItemDataPtr@@YAPEAXPEAUHWND__@@H@Z; ComboBox_GetItemDataPtr(HWND__ *,int)
0x1800083b7  mov     rbx, [rsp+28h+arg_0]
0x1800083bc  test    rax, rax
0x1800083bf  cmovnz  rdi, rax
0x1800083c3  mov     rax, rdi
0x1800083c6  add     rsp, 20h
0x1800083ca  pop     rdi
0x1800083cb  retn
```
