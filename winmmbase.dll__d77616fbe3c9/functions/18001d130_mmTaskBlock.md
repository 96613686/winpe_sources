# mmTaskBlock

- ea: `0x18001d130`
- end: `0x18001d186`
- name: `mmTaskBlock`
- size: `86`
- prototype: `void __stdcall(DWORD h)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update`

## callees

- `0x180011690`
- `0x18001d130`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x18001d15c`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x18001d15c`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001d16f`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001d16f`

## pseudocode

```c
void __stdcall mmTaskBlock(DWORD h)
{
  tagMSG Msg; // [rsp+20h] [rbp-38h] BYREF

  memset(&Msg, 0, sizeof(Msg));
  if ( IsPostThreadMessageWPresent() )
  {
    do
    {
      while ( 1 )
      {
        GetMessageA(&Msg, 0, 0, 0);
        if ( !Msg.hwnd )
          break;
        DispatchMessageA(&Msg);
      }
    }
    while ( Msg.message != 1024 );
  }
}

```

## disassembly

```asm
0x18001d130  sub     rsp, 58h
0x18001d134  xorps   xmm0, xmm0
0x18001d137  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x18001d13c  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x18001d141  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x18001d146  call    IsPostThreadMessageWPresent
0x18001d14b  test    al, al
0x18001d14d  jz      short loc_18001D181
0x18001d14f  xor     r9d, r9d; wMsgFilterMax
0x18001d152  lea     rcx, [rsp+58h+Msg]; lpMsg
0x18001d157  xor     r8d, r8d; wMsgFilterMin
0x18001d15a  xor     edx, edx; hWnd
0x18001d15c  call    cs:__imp_GetMessageA
0x18001d162  cmp     [rsp+58h+Msg.hwnd], 0
0x18001d168  jz      short loc_18001D177
0x18001d16a  lea     rcx, [rsp+58h+Msg]; lpMsg
0x18001d16f  call    cs:__imp_DispatchMessageA
0x18001d175  jmp     short loc_18001D14F
0x18001d177  cmp     [rsp+58h+Msg.message], 400h
0x18001d17f  jnz     short loc_18001D14F
0x18001d181  add     rsp, 58h
0x18001d185  retn
```
