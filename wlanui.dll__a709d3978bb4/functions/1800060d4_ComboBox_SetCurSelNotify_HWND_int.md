# ComboBox_SetCurSelNotify(HWND__ *,int)

- ea: `0x1800060d4`
- end: `0x18000612b`
- name: `?ComboBox_SetCurSelNotify@@YAXPEAUHWND__@@H@Z`
- size: `87`
- prototype: `void __fastcall(HWND hWnd, int)`
- caller_count: `7`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800078f4`
- `0x180007ae4`
- `0x180008944`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`
- `0x180014370`

## import_xrefs

- `USER32!GetDlgCtrlID` at `0x1800060f5`
- `USER32!GetDlgCtrlID` at `0x1800060f5`
- `USER32!SendMessageW` at `0x1800060ec`
- `USER32!SendMessageW` at `0x1800060ec`
- `USER32!SendMessageW` at `0x180006124`
- `USER32!GetParent` at `0x180006106`
- `USER32!GetParent` at `0x180006106`

## pseudocode

```c
void __fastcall ComboBox_SetCurSelNotify(HWND hWnd, int a2)
{
  WPARAM v3; // rbx
  HWND Parent; // rax

  SendMessageW(hWnd, 0x14Eu, a2, 0);
  v3 = (unsigned __int16)GetDlgCtrlID(hWnd) | 0x10000LL;
  Parent = GetParent(hWnd);
  SendMessageW(Parent, 0x111u, v3, (LPARAM)hWnd);
}

```

## disassembly

```asm
0x1800060d4  mov     [rsp+arg_0], rbx
0x1800060d9  push    rdi
0x1800060da  sub     rsp, 20h
0x1800060de  movsxd  r8, edx; wParam
0x1800060e1  xor     r9d, r9d; lParam
0x1800060e4  mov     edx, 14Eh; Msg
0x1800060e9  mov     rdi, rcx
0x1800060ec  call    cs:__imp_SendMessageW
0x1800060f2  mov     rcx, rdi; hWnd
0x1800060f5  call    cs:__imp_GetDlgCtrlID
0x1800060fb  movzx   ebx, ax
0x1800060fe  mov     rcx, rdi; hWnd
0x180006101  bts     rbx, 10h
0x180006106  call    cs:__imp_GetParent
0x18000610c  mov     r9, rdi
0x18000610f  mov     r8, rbx
0x180006112  mov     rcx, rax
0x180006115  mov     edx, 111h
0x18000611a  mov     rbx, [rsp+28h+arg_0]
0x18000611f  add     rsp, 20h
0x180006123  pop     rdi
0x180006124  jmp     cs:__imp_SendMessageW
```
