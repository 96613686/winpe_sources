# TraceProcessConsoleInput

- ea: `0x180009838`
- end: `0x180009a2a`
- name: `TraceProcessConsoleInput`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009a30`

## callees

- `0x180001fa0`
- `0x1800026d0`
- `0x180003530`
- `0x180003bb0`
- `0x180009838`
- `0x180009cb4`

## import_xrefs

- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x180009990`
- `api-ms-win-core-console-l2-1-0!GetConsoleScreenBufferInfo` at `0x180009990`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x1800098aa`
- `api-ms-win-core-console-l1-1-0!ReadConsoleInputA` at `0x1800098aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a1f`

## pseudocode

```c
DWORD __fastcall TraceProcessConsoleInput(__int64 a1)
{
  bool v1; // zf
  char *v3; // rcx
  __int64 v4; // rbx
  int wRepeatCount; // edi
  __int64 v6; // r8
  __int64 v7; // rdx
  _CONSOLE_SCREEN_BUFFER_INFO *p_ConsoleScreenBufferInfo; // r9
  int v10; // eax
  __int64 v11; // rcx
  DWORD NumberOfEventsRead; // [rsp+20h] [rbp-40h] BYREF
  _INPUT_RECORD Buffer; // [rsp+28h] [rbp-38h] BYREF
  _CONSOLE_SCREEN_BUFFER_INFO ConsoleScreenBufferInfo; // [rsp+40h] [rbp-20h] BYREF

  NumberOfEventsRead = 0;
  v1 = *(_DWORD *)(a1 + 64) == 60;
  memset(&Buffer, 0, 18);
  if ( v1 )
    return 0;
  v3 = *(char **)(a1 + 72);
  if ( (unsigned __int64)(v3 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    return 0;
  v4 = *(_QWORD *)(a1 + 8LL * *(unsigned int *)(a1 + 64) + 352);
  if ( ReadConsoleInputA(v3, &Buffer, 1u, &NumberOfEventsRead) && NumberOfEventsRead )
  {
    if ( Buffer.EventType != 1 || !Buffer.Event.KeyEvent.bKeyDown )
      return 0;
    wRepeatCount = Buffer.Event.KeyEvent.wRepeatCount;
    switch ( Buffer.Event.KeyEvent.wVirtualKeyCode )
    {
      case 9u:
        if ( (*(_BYTE *)(&Buffer.Event.FocusEvent + 3) & 0xC) != 0 )
          TraceUpdateConsoleOwner(a1, (*(_BYTE *)(&Buffer.Event.FocusEvent + 3) & 0x10) != 0 ? -1 : 1);
        return 0;
      case 0x13u:
      case 0x20u:
        if ( v4 && (*(_BYTE *)(&Buffer.Event.MenuEvent + 1) & 1) != 0 )
        {
          v10 = *(_DWORD *)(v4 + 56);
          if ( (v10 & 1) != 0 )
          {
            TraceEnableClientA(a1, v4, 0);
          }
          else
          {
            v11 = *(unsigned int *)(v4 + 60);
            *(_DWORD *)(v4 + 56) = v10 | 1;
            _InterlockedExchange((volatile __int32 *)(a1 + 4 * v11 + 112), 0);
          }
          TraceUpdateConsoleTitleA(v4);
        }
        return 0;
      case 0x21u:
      case 0x22u:
        memset(&ConsoleScreenBufferInfo, 0, sizeof(ConsoleScreenBufferInfo));
        if ( !v4 || !GetConsoleScreenBufferInfo(*(HANDLE *)(v4 + 264), &ConsoleScreenBufferInfo) )
          return 0;
        v6 = (unsigned int)(wRepeatCount
                          * (ConsoleScreenBufferInfo.srWindow.Bottom - ConsoleScreenBufferInfo.srWindow.Top));
        if ( Buffer.Event.KeyEvent.wVirtualKeyCode == 33 )
          v6 = (unsigned int)-(int)v6;
        p_ConsoleScreenBufferInfo = &ConsoleScreenBufferInfo;
        goto LABEL_23;
      case 0x25u:
        if ( v4 )
        {
          v7 = (unsigned int)-Buffer.Event.KeyEvent.wRepeatCount;
          goto LABEL_26;
        }
        break;
      case 0x26u:
        if ( v4 )
        {
          v6 = (unsigned int)-Buffer.Event.KeyEvent.wRepeatCount;
LABEL_22:
          p_ConsoleScreenBufferInfo = 0;
LABEL_23:
          v7 = 0;
LABEL_27:
          TraceShiftConsoleWindow(v4, v7, v6, p_ConsoleScreenBufferInfo);
        }
        break;
      case 0x27u:
        if ( v4 )
        {
          v7 = Buffer.Event.KeyEvent.wRepeatCount;
LABEL_26:
          p_ConsoleScreenBufferInfo = 0;
          v6 = 0;
          goto LABEL_27;
        }
        break;
      default:
        if ( Buffer.Event.KeyEvent.wVirtualKeyCode != 40 || !v4 )
          return 0;
        v6 = Buffer.Event.KeyEvent.wRepeatCount;
        goto LABEL_22;
    }
    return 0;
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180009838  mov     [rsp-18h+arg_8], rbx
0x18000983d  mov     [rsp-18h+arg_10], rsi
0x180009842  push    rbp
0x180009843  push    rdi
0x180009844  push    r15
0x180009846  mov     rbp, rsp
0x180009849  sub     rsp, 60h
0x18000984d  mov     rax, cs:__security_cookie
0x180009854  xor     rax, rsp
0x180009857  mov     [rbp+var_8], rax
0x18000985b  xor     eax, eax
0x18000985d  mov     [rbp+NumberOfEventsRead], 0
0x180009864  cmp     dword ptr [rcx+40h], 3Ch ; '<'
0x180009868  xorps   xmm0, xmm0
0x18000986b  mov     rsi, rcx
0x18000986e  mov     word ptr [rbp+Buffer.Event+0Ch], ax
0x180009872  movups  xmmword ptr [rbp+Buffer.EventType], xmm0
0x180009876  jz      loc_180009950
0x18000987c  mov     rcx, [rcx+48h]; hConsoleInput
0x180009880  lea     rax, [rcx-1]
0x180009884  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180009888  ja      loc_180009950
0x18000988e  mov     eax, [rsi+40h]
0x180009891  lea     r9, [rbp+NumberOfEventsRead]; lpNumberOfEventsRead
0x180009895  mov     r15d, 1
0x18000989b  lea     rdx, [rbp+Buffer]; lpBuffer
0x18000989f  mov     r8d, r15d; nLength
0x1800098a2  mov     rbx, [rsi+rax*8+160h]
0x1800098aa  call    cs:__imp_ReadConsoleInputA
0x1800098b0  test    eax, eax
0x1800098b2  jz      loc_180009A1F
0x1800098b8  cmp     [rbp+NumberOfEventsRead], 0
0x1800098bc  jz      loc_180009A1F
0x1800098c2  cmp     [rbp+Buffer.EventType], r15w
0x1800098c7  jnz     loc_180009950
0x1800098cd  cmp     dword ptr [rbp+Buffer.Event], 0
0x1800098d1  jz      short loc_180009950
0x1800098d3  movzx   ecx, word ptr [rbp+Buffer.Event+6]
0x1800098d7  movzx   edi, word ptr [rbp+Buffer.Event+4]
0x1800098db  sub     ecx, 9
0x1800098de  jz      loc_1800099FB
0x1800098e4  sub     ecx, 0Ah
0x1800098e7  jz      loc_1800099BD
0x1800098ed  sub     ecx, 0Dh
0x1800098f0  jz      loc_1800099BD
0x1800098f6  sub     ecx, r15d
0x1800098f9  jz      short loc_180009973
0x1800098fb  sub     ecx, r15d
0x1800098fe  jz      short loc_180009973
0x180009900  sub     ecx, 3
0x180009903  jz      short loc_180009939
0x180009905  sub     ecx, r15d
0x180009908  jz      short loc_180009927
0x18000990a  sub     ecx, r15d
0x18000990d  jz      short loc_18000991E
0x18000990f  cmp     ecx, r15d
0x180009912  jnz     short loc_180009950
0x180009914  test    rbx, rbx
0x180009917  jz      short loc_180009950
0x180009919  mov     r8d, edi
0x18000991c  jmp     short loc_180009932
0x18000991e  test    rbx, rbx
0x180009921  jz      short loc_180009950
0x180009923  mov     edx, edi
0x180009925  jmp     short loc_180009942
0x180009927  test    rbx, rbx
0x18000992a  jz      short loc_180009950
0x18000992c  mov     r8d, edi
0x18000992f  neg     r8d
0x180009932  xor     r9d, r9d
0x180009935  xor     edx, edx
0x180009937  jmp     short loc_180009948
0x180009939  test    rbx, rbx
0x18000993c  jz      short loc_180009950
0x18000993e  mov     edx, edi
0x180009940  neg     edx
0x180009942  xor     r9d, r9d
0x180009945  xor     r8d, r8d
0x180009948  mov     rcx, rbx
0x18000994b  call    TraceShiftConsoleWindow
0x180009950  xor     eax, eax
0x180009952  mov     rcx, [rbp+var_8]
0x180009956  xor     rcx, rsp; StackCookie
0x180009959  call    __security_check_cookie
0x18000995e  lea     r11, [rsp+60h+var_s0]
0x180009963  mov     rbx, [r11+28h]
0x180009967  mov     rsi, [r11+30h]
0x18000996b  mov     rsp, r11
0x18000996e  pop     r15
0x180009970  pop     rdi
0x180009971  pop     rbp
0x180009972  retn
0x180009973  xor     eax, eax
0x180009975  xorps   xmm0, xmm0
0x180009978  movups  xmmword ptr [rbp+ConsoleScreenBufferInfo.dwSize.X], xmm0
0x18000997c  mov     qword ptr [rbp+ConsoleScreenBufferInfo.srWindow.Right], rax
0x180009980  test    rbx, rbx
0x180009983  jz      short loc_180009950
0x180009985  mov     rcx, [rbx+108h]; hConsoleOutput
0x18000998c  lea     rdx, [rbp+ConsoleScreenBufferInfo]; lpConsoleScreenBufferInfo
0x180009990  call    cs:__imp_GetConsoleScreenBufferInfo
0x180009996  test    eax, eax
0x180009998  jz      short loc_180009950
0x18000999a  movsx   eax, [rbp+ConsoleScreenBufferInfo.srWindow.Top]
0x18000999e  movsx   r8d, [rbp+ConsoleScreenBufferInfo.srWindow.Bottom]
0x1800099a3  sub     r8d, eax
0x1800099a6  imul    r8d, edi
0x1800099aa  cmp     word ptr [rbp+Buffer.Event+6], 21h ; '!'
0x1800099af  jnz     short loc_1800099B4
0x1800099b1  neg     r8d
0x1800099b4  lea     r9, [rbp+ConsoleScreenBufferInfo]
0x1800099b8  jmp     loc_180009935
0x1800099bd  test    rbx, rbx
0x1800099c0  jz      short loc_180009950
0x1800099c2  test    r15b, dil
0x1800099c5  jz      short loc_180009950
0x1800099c7  mov     eax, [rbx+38h]
0x1800099ca  test    r15b, al
0x1800099cd  jz      short loc_1800099DF
0x1800099cf  xor     r8d, r8d
0x1800099d2  mov     rdx, rbx
0x1800099d5  mov     rcx, rsi
0x1800099d8  call    TraceEnableClientA
0x1800099dd  jmp     short loc_1800099EE
0x1800099df  mov     ecx, [rbx+3Ch]
0x1800099e2  or      eax, r15d
0x1800099e5  mov     [rbx+38h], eax
0x1800099e8  xor     eax, eax
0x1800099ea  xchg    eax, [rsi+rcx*4+70h]
0x1800099ee  mov     rcx, rbx
0x1800099f1  call    TraceUpdateConsoleTitleA
0x1800099f6  jmp     loc_180009950
0x1800099fb  mov     eax, dword ptr [rbp+Buffer.Event+0Ch]
0x1800099fe  test    al, 0Ch
0x180009a00  jz      loc_180009950
0x180009a06  and     al, 10h
0x180009a08  mov     rcx, rsi
0x180009a0b  neg     al
0x180009a0d  sbb     edx, edx
0x180009a0f  and     edx, 0FFFFFFFEh
0x180009a12  add     edx, r15d
0x180009a15  call    TraceUpdateConsoleOwner
0x180009a1a  jmp     loc_180009950
0x180009a1f  call    cs:__imp_GetLastError
0x180009a25  jmp     loc_180009952
```
