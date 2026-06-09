# CEventUI::UpdateUIForStateCommon(ushort const *,ushort const *)

- ea: `0x18000845c`
- end: `0x1800084b0`
- name: `?UpdateUIForStateCommon@CEventUI@@AEAAJPEBG0@Z`
- size: `84`
- prototype: `int(CEventUI *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007e50`
- `0x1800083c0`
- `0x1800084b8`
- `0x180008528`
- `0x180008668`

## callees

- `0x18000845c`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008488`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000849d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x180008488`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x18000849d`

## pseudocode

```c
__int64 __fastcall CEventUI::UpdateUIForStateCommon(HWND *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  if ( a2 && *a2 )
    SendMessageW(this[13], 0x46Cu, 3u, (LPARAM)a2);
  SendMessageW(this[13], 0x46Cu, 0, (LPARAM)a3);
  return 0;
}

```

## disassembly

```asm
0x18000845c  mov     [rsp+arg_0], rbx
0x180008461  push    rdi
0x180008462  sub     rsp, 20h
0x180008466  xor     eax, eax
0x180008468  mov     rdi, r8
0x18000846b  mov     rbx, rcx
0x18000846e  test    rdx, rdx
0x180008471  jz      short loc_18000848E
0x180008473  cmp     [rdx], ax
0x180008476  jz      short loc_18000848E
0x180008478  mov     rcx, [rcx+68h]; hWnd
0x18000847c  lea     r8d, [rax+3]; wParam
0x180008480  mov     r9, rdx; lParam
0x180008483  mov     edx, 46Ch; Msg
0x180008488  call    cs:__imp_SendMessageW
0x18000848e  mov     rcx, [rbx+68h]; hWnd
0x180008492  mov     r9, rdi; lParam
0x180008495  xor     r8d, r8d; wParam
0x180008498  mov     edx, 46Ch; Msg
0x18000849d  call    cs:__imp_SendMessageW
0x1800084a3  mov     rbx, [rsp+28h+arg_0]
0x1800084a8  xor     eax, eax
0x1800084aa  add     rsp, 20h
0x1800084ae  pop     rdi
0x1800084af  retn
```
