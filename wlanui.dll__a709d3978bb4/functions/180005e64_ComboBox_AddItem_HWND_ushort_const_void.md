# ComboBox_AddItem(HWND__ *,ushort const *,void *)

- ea: `0x180005e64`
- end: `0x180005eb7`
- name: `?ComboBox_AddItem@@YAHPEAUHWND__@@PEBGPEAX@Z`
- size: `83`
- prototype: `__int64 __fastcall(HWND hWnd, LPARAM lParam, LPARAM)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800078f4`
- `0x180007ae4`
- `0x180008944`
- `0x18000ac1c`
- `0x18000b6f8`
- `0x18000bb54`
- `0x18000bd88`
- `0x180014370`

## callees

- `0x180005e64`

## import_xrefs

- `USER32!SendMessageW` at `0x180005e84`
- `USER32!SendMessageW` at `0x180005e9f`
- `USER32!SendMessageW` at `0x180005e84`
- `USER32!SendMessageW` at `0x180005e9f`

## pseudocode

```c
__int64 __fastcall ComboBox_AddItem(HWND hWnd, LPARAM lParam, LPARAM a3)
{
  int v5; // eax
  unsigned int v6; // ebx

  v5 = SendMessageW(hWnd, 0x143u, 0, lParam);
  v6 = v5;
  if ( v5 >= 0 )
    SendMessageW(hWnd, 0x151u, v5, a3);
  return v6;
}

```

## disassembly

```asm
0x180005e64  mov     [rsp+arg_0], rbx
0x180005e69  mov     [rsp+arg_8], rsi
0x180005e6e  push    rdi
0x180005e6f  sub     rsp, 20h
0x180005e73  mov     rsi, r8
0x180005e76  mov     r9, rdx; lParam
0x180005e79  xor     r8d, r8d; wParam
0x180005e7c  mov     edx, 143h; Msg
0x180005e81  mov     rdi, rcx
0x180005e84  call    cs:__imp_SendMessageW
0x180005e8a  mov     rbx, rax
0x180005e8d  test    eax, eax
0x180005e8f  js      short loc_180005EA5
0x180005e91  movsxd  r8, ebx; wParam
0x180005e94  mov     r9, rsi; lParam
0x180005e97  mov     edx, 151h; Msg
0x180005e9c  mov     rcx, rdi; hWnd
0x180005e9f  call    cs:__imp_SendMessageW
0x180005ea5  mov     rsi, [rsp+28h+arg_8]
0x180005eaa  mov     eax, ebx
0x180005eac  mov     rbx, [rsp+28h+arg_0]
0x180005eb1  add     rsp, 20h
0x180005eb5  pop     rdi
0x180005eb6  retn
```
