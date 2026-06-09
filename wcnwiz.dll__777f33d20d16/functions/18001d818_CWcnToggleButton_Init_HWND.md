# CWcnToggleButton::Init(HWND__ *)

- ea: `0x18001d818`
- end: `0x18001da37`
- name: `?Init@CWcnToggleButton@@QEAAJPEAUHWND__@@@Z`
- size: `543`
- prototype: `__int64 __fastcall(CWcnToggleButton *__hidden this, HWND)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014880`

## callees

- `0x18000d630`
- `0x18000e1dc`
- `0x18001aad8`
- `0x18001d818`
- `0x18001da40`
- `0x18002de1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d88e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d997`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d87a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d88e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d983`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d98d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d997`
- `USER32!SendMessageW` at `0x18001d9df`
- `USER32!SendMessageW` at `0x18001d9df`
- `USER32!GetSystemMetrics` at `0x18001d903`
- `USER32!GetSystemMetrics` at `0x18001d910`
- `USER32!GetSystemMetrics` at `0x18001d903`
- `USER32!GetSystemMetrics` at `0x18001d910`
- `USER32!GetClientRect` at `0x18001d8e9`
- `USER32!GetClientRect` at `0x18001d8e9`
- `GDI32!DeleteObject` at `0x18001d8f8`
- `GDI32!DeleteObject` at `0x18001d8f8`
- `GDI32!CreateFontW` at `0x18001d974`
- `GDI32!CreateFontW` at `0x18001d974`

## pseudocode

```c
__int64 __fastcall CWcnToggleButton::Init(struct tagRECT *this, HWND a2, __int64 a3)
{
  const char *Indent; // rax
  __int64 v6; // r10
  unsigned int v7; // ebx
  signed int v8; // ebx
  _BYTE *v9; // r10
  const char *v10; // rax
  __int64 v11; // r10
  __int64 v12; // rdx
  void *v13; // rcx
  int SystemMetrics; // ebx
  int v15; // eax
  HFONT FontW; // rax
  unsigned int LastError; // ebx
  unsigned int v18; // eax
  __int64 v19; // r10

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 10, WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids, Indent);
  }
  if ( (unsigned int)IsolationAwareSetWindowSubclass(a2, CWcnToggleButton::WindowProcThunk, a3, this) )
  {
    GetClientRect(a2, this + 1);
    v13 = *(void **)&this[2].right;
    if ( v13 )
      DeleteObject(v13);
    SystemMetrics = GetSystemMetrics(49);
    v15 = GetSystemMetrics(50);
    FontW = CreateFontW(SystemMetrics, v15, 0, 0, 400, 0, 0, 0, 2u, 0, 0, 0, 0, L"Marlett");
    *(_QWORD *)&this[2].right = FontW;
    if ( FontW )
    {
      v8 = 0;
      SendMessageW(a2, 0x30u, (WPARAM)FontW, 1);
      CWcnToggleButton::InitializeTheme((CWcnToggleButton *)this, a2);
      goto LABEL_22;
    }
    if ( (int)GetLastError() > 0 )
      LastError = (unsigned __int16)GetLastError() | 0x80070000;
    else
      LastError = GetLastError();
    v8 = LastError | 0x80000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = GetIndent(0);
        v12 = 12;
        goto LABEL_11;
      }
LABEL_23:
      if ( v9 != (_BYTE *)&WPP_GLOBAL_Control && (v8 < 0 || v9[25] >= 6u) )
      {
        v18 = (unsigned int)GetIndent(-1);
        WPP_SF_sd(*(_QWORD *)(v19 + 16), 13, (unsigned int)WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids, v18, v8);
      }
    }
  }
  else
  {
    if ( (int)GetLastError() > 0 )
      v7 = (unsigned __int16)GetLastError() | 0x80070000;
    else
      v7 = GetLastError();
    v8 = v7 | 0x80000000;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v10 = GetIndent(0);
        v12 = 11;
LABEL_11:
        WPP_SF_s(*(_QWORD *)(v11 + 16), v12, WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids, v10);
LABEL_22:
        v9 = WPP_GLOBAL_Control;
        goto LABEL_23;
      }
      goto LABEL_23;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001d818  push    rbx
0x18001d81a  push    rsi
0x18001d81b  push    rdi
0x18001d81c  push    r14
0x18001d81e  sub     rsp, 78h
0x18001d822  mov     rsi, rdx
0x18001d825  mov     rdi, rcx
0x18001d828  mov     r10, cs:WPP_GLOBAL_Control
0x18001d82f  lea     r14, WPP_GLOBAL_Control
0x18001d836  cmp     r10, r14
0x18001d839  jz      short loc_18001D864
0x18001d83b  cmp     byte ptr [r10+19h], 6
0x18001d840  jb      short loc_18001D864
0x18001d842  mov     ecx, 1; int
0x18001d847  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001d84c  mov     rcx, [r10+10h]
0x18001d850  lea     r8, WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids
0x18001d857  mov     edx, 0Ah
0x18001d85c  mov     r9, rax
0x18001d85f  call    WPP_SF_s
0x18001d864  mov     r9, rdi
0x18001d867  lea     rdx, ?WindowProcThunk@CWcnToggleButton@@CA_JPEAUHWND__@@I_K_J11@Z; CWcnToggleButton::WindowProcThunk(HWND__ *,uint,unsigned __int64,__int64,unsigned __int64,unsigned __int64)
0x18001d86e  mov     rcx, rsi
0x18001d871  call    IsolationAwareSetWindowSubclass
0x18001d876  test    eax, eax
0x18001d878  jnz     short loc_18001D8E2
0x18001d87a  call    cs:__imp_GetLastError
0x18001d880  test    eax, eax
0x18001d882  jg      short loc_18001D88E
0x18001d884  call    cs:__imp_GetLastError
0x18001d88a  mov     ebx, eax
0x18001d88c  jmp     short loc_18001D89D
0x18001d88e  call    cs:__imp_GetLastError
0x18001d894  movzx   ebx, ax
0x18001d897  or      ebx, 80070000h
0x18001d89d  or      ebx, 80000000h
0x18001d8a3  mov     r10, cs:WPP_GLOBAL_Control
0x18001d8aa  cmp     r10, r14
0x18001d8ad  jz      loc_18001DA2B
0x18001d8b3  cmp     byte ptr [r10+19h], 2
0x18001d8b8  jb      loc_18001D9F7
0x18001d8be  xor     ecx, ecx; int
0x18001d8c0  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001d8c5  mov     edx, 0Bh
0x18001d8ca  mov     rcx, [r10+10h]
0x18001d8ce  lea     r8, WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids
0x18001d8d5  mov     r9, rax
0x18001d8d8  call    WPP_SF_s
0x18001d8dd  jmp     loc_18001D9F0
0x18001d8e2  lea     rdx, [rdi+10h]; lpRect
0x18001d8e6  mov     rcx, rsi; hWnd
0x18001d8e9  call    cs:__imp_GetClientRect
0x18001d8ef  mov     rcx, [rdi+28h]; ho
0x18001d8f3  test    rcx, rcx
0x18001d8f6  jz      short loc_18001D8FE
0x18001d8f8  call    cs:__imp_DeleteObject
0x18001d8fe  mov     ecx, 31h ; '1'; nIndex
0x18001d903  call    cs:__imp_GetSystemMetrics
0x18001d909  mov     ecx, 32h ; '2'; nIndex
0x18001d90e  mov     ebx, eax
0x18001d910  call    cs:__imp_GetSystemMetrics
0x18001d916  lea     rcx, pszFaceName; "Marlett"
0x18001d91d  xor     r9d, r9d; cOrientation
0x18001d920  mov     [rsp+98h+pszFaceName], rcx; pszFaceName
0x18001d925  xor     r8d, r8d; cEscapement
0x18001d928  mov     [rsp+98h+iPitchAndFamily], 0; iPitchAndFamily
0x18001d930  mov     edx, eax; cWidth
0x18001d932  mov     [rsp+98h+iQuality], 0; iQuality
0x18001d93a  mov     ecx, ebx; cHeight
0x18001d93c  mov     [rsp+98h+iClipPrecision], 0; iClipPrecision
0x18001d944  mov     [rsp+98h+iOutPrecision], 0; iOutPrecision
0x18001d94c  mov     [rsp+98h+iCharSet], 2; iCharSet
0x18001d954  mov     [rsp+98h+bStrikeOut], 0; bStrikeOut
0x18001d95c  mov     [rsp+98h+bUnderline], 0; bUnderline
0x18001d964  mov     [rsp+98h+bItalic], 0; bItalic
0x18001d96c  mov     [rsp+98h+cWeight], 190h; cWeight
0x18001d974  call    cs:__imp_CreateFontW
0x18001d97a  mov     [rdi+28h], rax
0x18001d97e  test    rax, rax
0x18001d981  jnz     short loc_18001D9D0
0x18001d983  call    cs:__imp_GetLastError
0x18001d989  test    eax, eax
0x18001d98b  jg      short loc_18001D997
0x18001d98d  call    cs:__imp_GetLastError
0x18001d993  mov     ebx, eax
0x18001d995  jmp     short loc_18001D9A6
0x18001d997  call    cs:__imp_GetLastError
0x18001d99d  movzx   ebx, ax
0x18001d9a0  or      ebx, 80070000h
0x18001d9a6  or      ebx, 80000000h
0x18001d9ac  mov     r10, cs:WPP_GLOBAL_Control
0x18001d9b3  cmp     r10, r14
0x18001d9b6  jz      short loc_18001DA2B
0x18001d9b8  cmp     byte ptr [r10+19h], 2
0x18001d9bd  jb      short loc_18001D9F7
0x18001d9bf  xor     ecx, ecx; int
0x18001d9c1  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001d9c6  mov     edx, 0Ch
0x18001d9cb  jmp     loc_18001D8CA
0x18001d9d0  xor     ebx, ebx
0x18001d9d2  mov     r8, rax; wParam
0x18001d9d5  mov     rcx, rsi; hWnd
0x18001d9d8  lea     r9d, [rbx+1]; lParam
0x18001d9dc  lea     edx, [rbx+30h]; Msg
0x18001d9df  call    cs:__imp_SendMessageW
0x18001d9e5  mov     rdx, rsi; HWND
0x18001d9e8  mov     rcx, rdi; this
0x18001d9eb  call    ?InitializeTheme@CWcnToggleButton@@AEAAXPEAUHWND__@@@Z; CWcnToggleButton::InitializeTheme(HWND__ *)
0x18001d9f0  mov     r10, cs:WPP_GLOBAL_Control
0x18001d9f7  cmp     r10, r14
0x18001d9fa  jz      short loc_18001DA2B
0x18001d9fc  test    ebx, ebx
0x18001d9fe  js      short loc_18001DA07
0x18001da00  cmp     byte ptr [r10+19h], 6
0x18001da05  jb      short loc_18001DA2B
0x18001da07  or      ecx, 0FFFFFFFFh; int
0x18001da0a  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18001da0f  mov     rcx, [r10+10h]
0x18001da13  lea     r8, WPP_8f54eb7bbcb33e0088ad6f9b6197513b_Traceguids
0x18001da1a  mov     edx, 0Dh
0x18001da1f  mov     [rsp+98h+cWeight], ebx
0x18001da23  mov     r9, rax
0x18001da26  call    WPP_SF_sd
0x18001da2b  mov     eax, ebx
0x18001da2d  add     rsp, 78h
0x18001da31  pop     r14
0x18001da33  pop     rdi
0x18001da34  pop     rsi
0x18001da35  pop     rbx
0x18001da36  retn
```
