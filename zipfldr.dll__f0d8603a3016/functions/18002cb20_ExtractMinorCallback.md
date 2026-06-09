# ExtractMinorCallback

- ea: `0x18002cb20`
- end: `0x18002cc23`
- name: `ExtractMinorCallback`
- size: `259`
- prototype: `__int64 __fastcall(PCWSTR pszPathIn, __int64, __int64, __int64, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, installer_update`

## callees

- `0x180010d20`
- `0x18002cb20`
- `0x180036f50`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18002cb6f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x18002cb6f`
- `USER32!PeekMessageW` at `0x18002cbae`
- `USER32!PeekMessageW` at `0x18002cbae`
- `USER32!TranslateMessage` at `0x18002cbbd`
- `USER32!TranslateMessage` at `0x18002cbbd`
- `USER32!DispatchMessageW` at `0x18002cbc8`
- `USER32!DispatchMessageW` at `0x18002cbc8`

## pseudocode

```c
__int64 __fastcall ExtractMinorCallback(PCWSTR pszPathIn, __int64 a2, __int64 a3, __int64 a4, unsigned __int16 *a5)
{
  unsigned int v7; // edi
  struct tagMSG Msg; // [rsp+40h] [rbp-68h] BYREF

  v7 = 0;
  if ( !a5[4] && PathCchCanonicalizeEx(a5 + 4, 0x104u, pszPathIn, 0x40u) >= 0 )
    PathFixSeparators(a5 + 4);
  if ( *(_QWORD *)a5 )
  {
    memset(&Msg, 0, sizeof(Msg));
    if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
    }
    if ( (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, _QWORD, _DWORD, _DWORD, _DWORD))(**(_QWORD **)a5
                                                                                                  + 24LL))(
           *(_QWORD *)a5,
           a3,
           a2,
           0,
           0,
           0,
           0) == -2144927744 )
      return 1;
  }
  return v7;
}

```

## disassembly

```asm
0x18002cb20  mov     [rsp+arg_18], rbx
0x18002cb25  push    rbp
0x18002cb26  push    rsi
0x18002cb27  push    rdi
0x18002cb28  push    r14
0x18002cb2a  push    r15
0x18002cb2c  sub     rsp, 80h
0x18002cb33  mov     rax, cs:__security_cookie
0x18002cb3a  xor     rax, rsp
0x18002cb3d  mov     [rsp+0A8h+var_38], rax
0x18002cb42  mov     rsi, [rsp+0A8h+arg_20]
0x18002cb4a  xor     r15d, r15d
0x18002cb4d  mov     r14, r8
0x18002cb50  mov     rbp, rdx
0x18002cb53  mov     edi, r15d
0x18002cb56  lea     rbx, [rsi+8]
0x18002cb5a  cmp     [rbx], r15w
0x18002cb5e  jnz     short loc_18002CB81
0x18002cb60  mov     r8, rcx; pszPathIn
0x18002cb63  lea     r9d, [r15+40h]; dwFlags
0x18002cb67  mov     rcx, rbx; pszPathOut
0x18002cb6a  mov     edx, 104h; cchPathOut
0x18002cb6f  call    cs:__imp_PathCchCanonicalizeEx
0x18002cb75  test    eax, eax
0x18002cb77  js      short loc_18002CB81
0x18002cb79  mov     rcx, rbx; unsigned __int16 *
0x18002cb7c  call    ?PathFixSeparators@@YAXPEAG@Z; PathFixSeparators(ushort *)
0x18002cb81  cmp     [rsi], r15
0x18002cb84  jz      short loc_18002CBFD
0x18002cb86  xorps   xmm0, xmm0
0x18002cb89  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x18002cb8e  mov     ebx, 1
0x18002cb93  xor     r9d, r9d; wMsgFilterMax
0x18002cb96  xor     r8d, r8d; wMsgFilterMin
0x18002cb99  mov     [rsp+0A8h+wRemoveMsg], ebx; wRemoveMsg
0x18002cb9d  xor     edx, edx; hWnd
0x18002cb9f  movups  xmmword ptr [rsp+0A8h+Msg.hwnd], xmm0
0x18002cba4  movups  xmmword ptr [rsp+0A8h+Msg.wParam], xmm0
0x18002cba9  movups  xmmword ptr [rsp+0A8h+Msg.time], xmm0
0x18002cbae  call    cs:__imp_PeekMessageW
0x18002cbb4  test    eax, eax
0x18002cbb6  jz      short loc_18002CBCE
0x18002cbb8  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x18002cbbd  call    cs:__imp_TranslateMessage
0x18002cbc3  lea     rcx, [rsp+0A8h+Msg]; lpMsg
0x18002cbc8  call    cs:__imp_DispatchMessageW
0x18002cbce  mov     rcx, [rsi]
0x18002cbd1  xor     r9d, r9d
0x18002cbd4  mov     [rsp+0A8h+var_78], r15d
0x18002cbd9  mov     r8, rbp
0x18002cbdc  mov     [rsp+0A8h+var_80], r15d
0x18002cbe1  mov     rdx, r14
0x18002cbe4  mov     [rsp+0A8h+wRemoveMsg], r15d
0x18002cbe9  mov     rax, [rcx]
0x18002cbec  mov     rax, [rax+18h]
0x18002cbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbf5  cmp     eax, 80270000h
0x18002cbfa  cmovz   edi, ebx
0x18002cbfd  mov     eax, edi
0x18002cbff  mov     rcx, [rsp+0A8h+var_38]
0x18002cc04  xor     rcx, rsp; StackCookie
0x18002cc07  call    __security_check_cookie
0x18002cc0c  mov     rbx, [rsp+0A8h+arg_18]
0x18002cc14  add     rsp, 80h
0x18002cc1b  pop     r15
0x18002cc1d  pop     r14
0x18002cc1f  pop     rdi
0x18002cc20  pop     rsi
0x18002cc21  pop     rbp
0x18002cc22  retn
```
