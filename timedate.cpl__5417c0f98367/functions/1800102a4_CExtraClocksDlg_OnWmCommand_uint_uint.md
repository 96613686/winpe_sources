# CExtraClocksDlg::_OnWmCommand(uint,uint)

- ea: `0x1800102a4`
- end: `0x180010391`
- name: `?_OnWmCommand@CExtraClocksDlg@@AEAA_JII@Z`
- size: `237`
- prototype: `__int64 __fastcall(CExtraClocksDlg *__hidden this, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800103a0`

## callees

- `0x18000fbfc`
- `0x1800101f4`
- `0x1800102a4`

## import_xrefs

- `SHLWAPI!PathRemoveBlanksW` at `0x180010314`
- `SHLWAPI!PathRemoveBlanksW` at `0x180010314`
- `USER32!GetDlgItemTextW` at `0x18001030a`
- `USER32!GetDlgItemTextW` at `0x18001030a`
- `USER32!IsDlgButtonChecked` at `0x180010341`
- `USER32!IsDlgButtonChecked` at `0x180010341`
- `USER32!SendMessageW` at `0x18001037c`
- `USER32!SendMessageW` at `0x18001037c`

## pseudocode

```c
__int64 __fastcall CExtraClocksDlg::_OnWmCommand(HWND *this, int a2, unsigned int a3)
{
  __int64 v4; // rsi
  WCHAR *v5; // rbx
  unsigned int v6; // ebx
  BOOL v7; // r8d
  __int64 v8; // rcx

  v4 = 1;
  if ( a3 == 351 || a3 == 352 )
  {
    if ( !a2 )
    {
      v6 = a3 - 351;
      v7 = IsDlgButtonChecked(this[1], a3) == 1;
      v8 = 38LL * v6;
      HIDWORD(this[v8 + 8]) = v7;
      LODWORD(this[v8 + 4]) = 1;
      CExtraClocksDlg::_EnableExtraClockControls((CExtraClocksDlg *)this, v6, v7);
      goto LABEL_12;
    }
  }
  else if ( a3 == 353 || a3 == 354 )
  {
    if ( a2 == 1 )
    {
      CExtraClocksDlg::_OnChangeTimeZone((CExtraClocksDlg *)this, a3);
      return 0;
    }
  }
  else if ( a3 - 355 <= 1 && a2 == 768 )
  {
    v5 = (WCHAR *)&this[38 * a3 - 13490];
    GetDlgItemTextW(this[1], a3, v5 + 18, 16);
    PathRemoveBlanksW(v5 + 18);
    *((_DWORD *)v5 + 8) = 1;
LABEL_12:
    SendMessageW(*this, 0x468u, (WPARAM)this[1], 0);
    return 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800102a4  push    rbx
0x1800102a6  push    rsi
0x1800102a7  push    rdi
0x1800102a8  push    r14
0x1800102aa  sub     rsp, 28h
0x1800102ae  mov     eax, r8d
0x1800102b1  mov     r10d, r8d
0x1800102b4  mov     r14, rcx
0x1800102b7  mov     esi, 1
0x1800102bc  sub     eax, 15Fh
0x1800102c1  jz      short loc_18001032F
0x1800102c3  sub     eax, esi
0x1800102c5  jz      short loc_18001032F
0x1800102c7  sub     eax, esi
0x1800102c9  jz      short loc_180010321
0x1800102cb  sub     eax, esi
0x1800102cd  jz      short loc_180010321
0x1800102cf  sub     eax, esi
0x1800102d1  jz      short loc_1800102DB
0x1800102d3  cmp     eax, esi
0x1800102d5  jnz     loc_180010384
0x1800102db  cmp     edx, 300h
0x1800102e1  jnz     loc_180010384
0x1800102e7  lea     ecx, [r8-163h]
0x1800102ee  mov     r9d, 10h; cchMax
0x1800102f4  imul    rdi, rcx, 130h
0x1800102fb  mov     rcx, [r14+8]; hDlg
0x1800102ff  mov     edx, r10d; nIDDlgItem
0x180010302  lea     rbx, [rdi+r14]
0x180010306  lea     r8, [rbx+24h]; lpString
0x18001030a  call    cs:__imp_GetDlgItemTextW
0x180010310  lea     rcx, [rbx+24h]; pszPath
0x180010314  call    cs:__imp_PathRemoveBlanksW
0x18001031a  mov     [rdi+r14+20h], esi
0x18001031f  jmp     short loc_18001036D
0x180010321  cmp     edx, esi
0x180010323  jnz     short loc_180010384
0x180010325  mov     edx, r10d; unsigned int
0x180010328  call    ?_OnChangeTimeZone@CExtraClocksDlg@@AEAAXI@Z; CExtraClocksDlg::_OnChangeTimeZone(uint)
0x18001032d  jmp     short loc_180010382
0x18001032f  test    edx, edx
0x180010331  jnz     short loc_180010384
0x180010333  mov     rcx, [rcx+8]; hDlg
0x180010337  lea     ebx, [r8-15Fh]
0x18001033e  mov     edx, r10d; nIDButton
0x180010341  call    cs:__imp_IsDlgButtonChecked
0x180010347  xor     r8d, r8d
0x18001034a  mov     edx, ebx; unsigned int
0x18001034c  cmp     eax, esi
0x18001034e  mov     eax, ebx
0x180010350  setz    r8b; int
0x180010354  imul    rcx, rax, 130h
0x18001035b  mov     [rcx+r14+44h], r8d
0x180010360  mov     [rcx+r14+20h], esi
0x180010365  mov     rcx, r14; this
0x180010368  call    ?_EnableExtraClockControls@CExtraClocksDlg@@AEAAXIH@Z; CExtraClocksDlg::_EnableExtraClockControls(uint,int)
0x18001036d  mov     r8, [r14+8]; wParam
0x180010371  xor     r9d, r9d; lParam
0x180010374  mov     rcx, [r14]; hWnd
0x180010377  mov     edx, 468h; Msg
0x18001037c  call    cs:__imp_SendMessageW
0x180010382  xor     esi, esi
0x180010384  mov     rax, rsi
0x180010387  add     rsp, 28h
0x18001038b  pop     r14
0x18001038d  pop     rdi
0x18001038e  pop     rsi
0x18001038f  pop     rbx
0x180010390  retn
```
