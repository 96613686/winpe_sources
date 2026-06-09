# TraceProcessConsoleInput(x)

- ea: `0x10009977`
- end: `0x10009b0e`
- name: `_TraceProcessConsoleInput@4`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x10009b20`

## callees

- `0x100027e0`
- `0x10003c20`
- `0x100086c3`
- `0x10009977`
- `0x10009dd0`
- `0x10009eb2`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x10009a79`
- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x10009a79`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x100099b6`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x100099b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10009b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10009b03`

## pseudocode

```c
DWORD __thiscall TraceProcessConsoleInput(_DWORD *this)
{
  int v2; // esi
  void *v3; // eax
  int v4; // esi
  int wRepeatCount; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // ecx
  int v10; // [esp-8h] [ebp-48h]
  _CONSOLE_SCREEN_BUFFER_INFO *p_ConsoleScreenBufferInfo; // [esp-4h] [ebp-44h]
  DWORD NumberOfEventsRead; // [esp+Ch] [ebp-34h] BYREF
  _CONSOLE_SCREEN_BUFFER_INFO ConsoleScreenBufferInfo; // [esp+10h] [ebp-30h] BYREF
  _INPUT_RECORD Buffer; // [esp+28h] [ebp-18h] BYREF

  v2 = this[10];
  if ( v2 == 60 )
    return 0;
  v3 = (void *)this[12];
  v4 = this[v2 + 77];
  if ( !v3 || v3 == (void *)-1 )
    return 0;
  if ( ReadConsoleInputA(v3, &Buffer, 1u, &NumberOfEventsRead) && NumberOfEventsRead )
  {
    if ( Buffer.EventType != 1 || !Buffer.Event.KeyEvent.bKeyDown )
      return 0;
    wRepeatCount = Buffer.Event.KeyEvent.wRepeatCount;
    if ( Buffer.Event.KeyEvent.wVirtualKeyCode <= 0x22u )
    {
      switch ( Buffer.Event.KeyEvent.wVirtualKeyCode )
      {
        case 0x22u:
          goto LABEL_47;
        case 9u:
          if ( (*(_BYTE *)(&Buffer.Event.FocusEvent + 3) & 0xC) != 0 )
          {
            v8 = -1;
            if ( (*(_BYTE *)(&Buffer.Event.FocusEvent + 3) & 0x10) == 0 )
              v8 = 1;
            TraceUpdateConsoleOwner(this, v8);
          }
          return 0;
        case 0x13u:
        case 0x20u:
          if ( v4 && (*(_BYTE *)(&Buffer.Event.MenuEvent + 1) & 1) != 0 )
          {
            v7 = *(_DWORD *)(v4 + 32);
            if ( (v7 & 1) != 0 )
            {
              TraceEnableClientA(0);
            }
            else
            {
              *(_DWORD *)(v4 + 32) = v7 | 1;
              _InterlockedExchange(&this[*(_DWORD *)(v4 + 36) + 17], 0);
            }
            TraceUpdateConsoleTitleA(v4);
          }
          return 0;
        case 0x21u:
LABEL_47:
          if ( v4 && GetConsoleScreenBufferInfo(*(HANDLE *)(v4 + 236), &ConsoleScreenBufferInfo) )
          {
            v9 = wRepeatCount * (ConsoleScreenBufferInfo.srWindow.Bottom - ConsoleScreenBufferInfo.srWindow.Top);
            if ( Buffer.Event.KeyEvent.wVirtualKeyCode == 33 )
              v9 = -v9;
            p_ConsoleScreenBufferInfo = &ConsoleScreenBufferInfo;
            LOWORD(v10) = v9;
            goto LABEL_43;
          }
          break;
      }
      return 0;
    }
    switch ( Buffer.Event.KeyEvent.wVirtualKeyCode )
    {
      case '%':
        if ( !v4 )
          return 0;
        break;
      case '&':
        if ( !v4 )
          return 0;
        p_ConsoleScreenBufferInfo = 0;
        v10 = -Buffer.Event.KeyEvent.wRepeatCount;
LABEL_43:
        TraceShiftConsoleWindow(v10, p_ConsoleScreenBufferInfo);
        return 0;
      case '\'':
        if ( !v4 )
          return 0;
        break;
      default:
        if ( Buffer.Event.KeyEvent.wVirtualKeyCode != 40 || !v4 )
          return 0;
        p_ConsoleScreenBufferInfo = 0;
        LOWORD(v10) = Buffer.Event.KeyEvent.wRepeatCount;
        goto LABEL_43;
    }
    p_ConsoleScreenBufferInfo = 0;
    LOWORD(v10) = 0;
    goto LABEL_43;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x10009977  mov     edi, edi
0x10009979  push    ebp
0x1000997a  mov     ebp, esp
0x1000997c  sub     esp, 34h
0x1000997f  mov     eax, ___security_cookie
0x10009984  xor     eax, ebp
0x10009986  mov     [ebp+var_4], eax
0x10009989  push    ebx
0x1000998a  push    esi
0x1000998b  push    edi
0x1000998c  mov     edi, ecx
0x1000998e  mov     esi, [edi+28h]
0x10009991  cmp     esi, 3Ch ; '<'
0x10009994  jz      short loc_10009A01
0x10009996  mov     eax, [edi+30h]
0x10009999  mov     esi, [edi+esi*4+134h]
0x100099a0  test    eax, eax
0x100099a2  jz      short loc_10009A01
0x100099a4  cmp     eax, 0FFFFFFFFh
0x100099a7  jz      short loc_10009A01
0x100099a9  lea     ecx, [ebp+NumberOfEventsRead]
0x100099ac  xor     ebx, ebx
0x100099ae  push    ecx; lpNumberOfEventsRead
0x100099af  inc     ebx
0x100099b0  lea     ecx, [ebp+Buffer]
0x100099b3  push    ebx; nLength
0x100099b4  push    ecx; lpBuffer
0x100099b5  push    eax; hConsoleInput
0x100099b6  call    ds:__imp__ReadConsoleInputA@16; ReadConsoleInputA(x,x,x,x)
0x100099bc  test    eax, eax
0x100099be  jz      loc_10009B03
0x100099c4  cmp     [ebp+NumberOfEventsRead], 0
0x100099c8  jz      loc_10009B03
0x100099ce  cmp     [ebp+Buffer.EventType], bx
0x100099d2  jnz     short loc_10009A01
0x100099d4  cmp     dword ptr [ebp+Buffer.Event], 0
0x100099d8  jz      short loc_10009A01
0x100099da  movzx   eax, word ptr [ebp+Buffer.Event+6]
0x100099de  movzx   ebx, word ptr [ebp+Buffer.Event+4]
0x100099e2  cmp     eax, 22h ; '"'
0x100099e5  ja      loc_10009AA4
0x100099eb  jz      short loc_10009A6B
0x100099ed  sub     eax, 9
0x100099f0  jz      short loc_10009A4D
0x100099f2  sub     eax, 0Ah
0x100099f5  jz      short loc_10009A12
0x100099f7  sub     eax, 0Dh
0x100099fa  jz      short loc_10009A12
0x100099fc  sub     eax, 1
0x100099ff  jz      short loc_10009A6B
0x10009a01  xor     eax, eax
0x10009a03  mov     ecx, [ebp+var_4]
0x10009a06  pop     edi
0x10009a07  pop     esi
0x10009a08  xor     ecx, ebp; StackCookie
0x10009a0a  pop     ebx
0x10009a0b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10009a10  leave
0x10009a11  retn
0x10009a12  test    esi, esi
0x10009a14  jz      short loc_10009A01
0x10009a16  test    bl, 1
0x10009a19  jz      short loc_10009A01
0x10009a1b  mov     eax, [esi+20h]
0x10009a1e  test    al, 1
0x10009a20  jz      short loc_10009A2F
0x10009a22  push    0
0x10009a24  mov     edx, esi
0x10009a26  mov     ecx, edi
0x10009a28  call    _TraceEnableClientA@12; TraceEnableClientA(x,x,x)
0x10009a2d  jmp     short loc_10009A44
0x10009a2f  xor     ecx, ecx
0x10009a31  xor     edx, edx
0x10009a33  inc     ecx
0x10009a34  or      eax, ecx
0x10009a36  mov     [esi+20h], eax
0x10009a39  mov     eax, [esi+24h]
0x10009a3c  add     eax, 11h
0x10009a3f  lea     eax, [edi+eax*4]
0x10009a42  xchg    edx, [eax]
0x10009a44  mov     ecx, esi
0x10009a46  call    _TraceUpdateConsoleTitleA@4; TraceUpdateConsoleTitleA(x)
0x10009a4b  jmp     short loc_10009A01
0x10009a4d  test    byte ptr [ebp+Buffer.Event+0Ch], 0Ch
0x10009a51  jz      short loc_10009A01
0x10009a53  test    byte ptr [ebp+Buffer.Event+0Ch], 10h
0x10009a57  push    0FFFFFFFFh
0x10009a59  pop     eax
0x10009a5a  push    1
0x10009a5c  pop     ecx
0x10009a5d  cmovz   eax, ecx
0x10009a60  mov     ecx, edi
0x10009a62  mov     edx, eax
0x10009a64  call    _TraceUpdateConsoleOwner@8; TraceUpdateConsoleOwner(x,x)
0x10009a69  jmp     short loc_10009A01
0x10009a6b  test    esi, esi
0x10009a6d  jz      short loc_10009A01
0x10009a6f  lea     eax, [ebp+ConsoleScreenBufferInfo]
0x10009a72  push    eax; lpConsoleScreenBufferInfo
0x10009a73  push    dword ptr [esi+0ECh]; hConsoleOutput
0x10009a79  call    ds:__imp__GetConsoleScreenBufferInfo@8; GetConsoleScreenBufferInfo(x,x)
0x10009a7f  test    eax, eax
0x10009a81  jz      loc_10009A01
0x10009a87  movsx   eax, [ebp+ConsoleScreenBufferInfo.srWindow.Top]
0x10009a8b  movsx   ecx, [ebp+ConsoleScreenBufferInfo.srWindow.Bottom]
0x10009a8f  sub     ecx, eax
0x10009a91  imul    ecx, ebx
0x10009a94  cmp     word ptr [ebp+Buffer.Event+6], 21h ; '!'
0x10009a99  jnz     short loc_10009A9D
0x10009a9b  neg     ecx
0x10009a9d  lea     eax, [ebp+ConsoleScreenBufferInfo]
0x10009aa0  push    eax
0x10009aa1  push    ecx
0x10009aa2  jmp     short loc_10009AE3
0x10009aa4  sub     eax, 25h ; '%'
0x10009aa7  jz      short loc_10009AE7
0x10009aa9  sub     eax, 1
0x10009aac  jz      short loc_10009AD4
0x10009aae  sub     eax, 1
0x10009ab1  jz      short loc_10009AC8
0x10009ab3  sub     eax, 1
0x10009ab6  jnz     loc_10009A01
0x10009abc  test    esi, esi
0x10009abe  jz      loc_10009A01
0x10009ac4  push    eax
0x10009ac5  push    ebx
0x10009ac6  jmp     short loc_10009AE3
0x10009ac8  test    esi, esi
0x10009aca  jz      loc_10009A01
0x10009ad0  mov     edx, ebx
0x10009ad2  jmp     short loc_10009AF3
0x10009ad4  test    esi, esi
0x10009ad6  jz      loc_10009A01
0x10009adc  mov     eax, ebx
0x10009ade  push    0
0x10009ae0  neg     eax
0x10009ae2  push    eax
0x10009ae3  xor     edx, edx
0x10009ae5  jmp     short loc_10009AF7
0x10009ae7  test    esi, esi
0x10009ae9  jz      loc_10009A01
0x10009aef  mov     edx, ebx
0x10009af1  neg     edx
0x10009af3  push    0
0x10009af5  push    0
0x10009af7  mov     ecx, esi
0x10009af9  call    _TraceShiftConsoleWindow@16; TraceShiftConsoleWindow(x,x,x,x)
0x10009afe  jmp     loc_10009A01
0x10009b03  call    ds:__imp__GetLastError@0; GetLastError()
0x10009b09  jmp     loc_10009A03
```
