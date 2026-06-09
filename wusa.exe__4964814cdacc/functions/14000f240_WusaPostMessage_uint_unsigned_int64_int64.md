# WusaPostMessage(uint,unsigned __int64,__int64)

- ea: `0x14000f240`
- end: `0x14000f28c`
- name: `?WusaPostMessage@@YAXI_K_J@Z`
- size: `76`
- prototype: `void __fastcall(UINT Msg, WPARAM wParam, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140005c70`
- `0x1400075b0`
- `0x14000afc0`
- `0x140011440`

## callees

- `0x14000f240`
- `0x140013490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000f266`
- `KERNEL32!GetLastError` at `0x14000f266`
- `USER32!PostMessageW` at `0x14000f25c`
- `USER32!PostMessageW` at `0x14000f25c`

## pseudocode

```c
void __fastcall WusaPostMessage(UINT Msg, WPARAM wParam)
{
  DWORD LastError; // eax

  if ( !dword_140020188 && !PostMessageW(hWndParent, Msg, wParam, 0) )
  {
    LastError = GetLastError();
    WusaLogDebugEventA(
      (__int64)L"WusaPostMessage",
      679,
      "Failed to PostMessage to progress window, error code %u",
      LastError);
  }
}

```

## disassembly

```asm
0x14000f240  sub     rsp, 28h
0x14000f244  cmp     cs:dword_140020188, 0
0x14000f24b  jnz     short loc_14000F287
0x14000f24d  mov     r8, rdx; wParam
0x14000f250  xor     r9d, r9d; lParam
0x14000f253  mov     edx, ecx; Msg
0x14000f255  mov     rcx, cs:hWndParent; hWnd
0x14000f25c  call    cs:__imp_PostMessageW
0x14000f262  test    eax, eax
0x14000f264  jnz     short loc_14000F287
0x14000f266  call    cs:__imp_GetLastError
0x14000f26c  lea     r8, aFailedToPostme; "Failed to PostMessage to progress windo"...
0x14000f273  mov     edx, 2A7h
0x14000f278  mov     r9d, eax
0x14000f27b  lea     rcx, aWusapostmessag; "WusaPostMessage"
0x14000f282  call    WusaLogDebugEventA
0x14000f287  add     rsp, 28h
0x14000f28b  retn
```
