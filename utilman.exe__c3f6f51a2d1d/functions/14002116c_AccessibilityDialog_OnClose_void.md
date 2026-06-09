# AccessibilityDialog::OnClose(void)

- ea: `0x14002116c`
- end: `0x1400212ba`
- name: `?OnClose@AccessibilityDialog@@AEAAXXZ`
- size: `334`
- prototype: `void __fastcall(AccessibilityDialog *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140023370`

## callees

- `0x140002480`
- `0x140002fa0`
- `0x14000f774`
- `0x140020c64`
- `0x14002116c`
- `0x140022d64`
- `0x140029010`

## import_xrefs

- `USER32!SendInput` at `0x140021246`
- `USER32!SendInput` at `0x140021277`
- `USER32!SendInput` at `0x140021246`
- `USER32!SendInput` at `0x140021277`
- `USER32!DestroyWindow` at `0x1400211d1`
- `USER32!DestroyWindow` at `0x1400211d1`
- `USER32!PostQuitMessage` at `0x1400211df`
- `USER32!PostQuitMessage` at `0x1400211df`

## string_xrefs

- `0x1400211b9`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x14002125a`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`
- `0x14002128b`: `enduser\ezap\easeofaccess\accessibilitydialog\accessibilitydialog.cpp`

## pseudocode

```c
void __fastcall AccessibilityDialog::OnClose(AccessibilityDialog *this)
{
  __int64 v2; // rcx
  int v3; // eax
  const char *v4; // r9
  const char *v5; // r9
  struct tagINPUT pInputs; // [rsp+20h] [rbp-59h] BYREF
  int v7; // [rsp+48h] [rbp-31h]
  __int16 v8; // [rsp+50h] [rbp-29h]
  int v9; // [rsp+70h] [rbp-9h]
  __int16 v10; // [rsp+78h] [rbp-1h]
  int v11; // [rsp+7Ch] [rbp+3h]
  int v12; // [rsp+98h] [rbp+1Fh]
  __int16 v13; // [rsp+A0h] [rbp+27h]
  int v14; // [rsp+A4h] [rbp+2Bh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = *((_QWORD *)this + 39);
  if ( v2 )
  {
    if ( *((_DWORD *)this + 76) )
    {
      v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 40LL))(v2);
      if ( v3 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x238,
          (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
          (const char *)(unsigned int)v3,
          pInputs.type);
    }
  }
  DestroyWindow(*((HWND *)this + 5));
  PostQuitMessage(0);
  if ( IsFullscreenCXHRunning() )
  {
    memset_0(&pInputs, 0, 0xA0u);
    pInputs.type = 1;
    v7 = 1;
    v9 = 1;
    v12 = 1;
    v8 = 9;
    v10 = 9;
    pInputs.ki.wVk = 16;
    v13 = 16;
    v11 = 2;
    v14 = 2;
    if ( !SendInput(4u, &pInputs, 40) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x250,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        v4);
    if ( !SendInput(4u, &pInputs, 40) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x251,
        (unsigned int)"enduser\\ezap\\easeofaccess\\accessibilitydialog\\accessibilitydialog.cpp",
        v5);
  }
}

```

## disassembly

```asm
0x14002116c  mov     [rsp-8+arg_8], rbx
0x140021171  push    rbp
0x140021172  lea     rbp, [rsp-57h]
0x140021177  sub     rsp, 0D0h
0x14002117e  mov     rax, cs:__security_cookie
0x140021185  xor     rax, rsp
0x140021188  mov     [rbp+57h+var_10], rax
0x14002118c  mov     rbx, rcx
0x14002118f  mov     rcx, [rcx+138h]
0x140021196  test    rcx, rcx
0x140021199  jz      short loc_1400211CD
0x14002119b  mov     edx, [rbx+130h]
0x1400211a1  test    edx, edx
0x1400211a3  jz      short loc_1400211CD
0x1400211a5  mov     rax, [rcx]
0x1400211a8  mov     rax, [rax+28h]
0x1400211ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400211b1  test    eax, eax
0x1400211b3  jns     short loc_1400211CD
0x1400211b5  mov     rcx, [rbp+5Fh]; this
0x1400211b9  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x1400211c0  mov     r9d, eax; char *
0x1400211c3  mov     edx, 238h; void *
0x1400211c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1400211cd  mov     rcx, [rbx+28h]; hWnd
0x1400211d1  call    cs:__imp_DestroyWindow
0x1400211d8  nop     dword ptr [rax+rax+00h]
0x1400211dd  xor     ecx, ecx; nExitCode
0x1400211df  call    cs:__imp_PostQuitMessage
0x1400211e6  nop     dword ptr [rax+rax+00h]
0x1400211eb  call    ?IsFullscreenCXHRunning@@YA_NXZ; IsFullscreenCXHRunning(void)
0x1400211f0  test    al, al
0x1400211f2  jz      loc_14002129C
0x1400211f8  xor     edx, edx; Val
0x1400211fa  lea     rcx, [rbp+57h+pInputs]; void *
0x1400211fe  mov     r8d, 0A0h; Size
0x140021204  call    memset_0
0x140021209  mov     ecx, 1
0x14002120e  mov     [rbp+57h+pInputs.type], ecx
0x140021211  mov     [rbp+57h+var_88], ecx
0x140021214  mov     [rbp+57h+var_60], ecx
0x140021217  lea     eax, [rcx+8]
0x14002121a  mov     [rbp+57h+var_38], ecx
0x14002121d  lea     edx, [rcx+0Fh]
0x140021220  mov     [rbp+57h+var_80], ax
0x140021224  lea     ebx, [rcx+27h]
0x140021227  mov     [rbp+57h+var_58], ax
0x14002122b  lea     eax, [rcx+1]
0x14002122e  mov     word ptr [rbp+57h+pInputs.8], dx
0x140021232  mov     [rbp+57h+var_30], dx
0x140021236  lea     ecx, [rax+2]; cInputs
0x140021239  mov     r8d, ebx; cbSize
0x14002123c  mov     [rbp+57h+var_54], eax
0x14002123f  lea     rdx, [rbp+57h+pInputs]; pInputs
0x140021243  mov     [rbp+57h+var_2C], eax
0x140021246  call    cs:__imp_SendInput
0x14002124d  nop     dword ptr [rax+rax+00h]
0x140021252  test    eax, eax
0x140021254  jnz     short loc_14002126B
0x140021256  mov     rcx, [rbp+5Fh]; this
0x14002125a  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140021261  mov     edx, 250h; void *
0x140021266  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14002126b  mov     r8d, ebx; cbSize
0x14002126e  lea     rdx, [rbp+57h+pInputs]; pInputs
0x140021272  mov     ecx, 4; cInputs
0x140021277  call    cs:__imp_SendInput
0x14002127e  nop     dword ptr [rax+rax+00h]
0x140021283  test    eax, eax
0x140021285  jnz     short loc_14002129C
0x140021287  mov     rcx, [rbp+5Fh]; this
0x14002128b  lea     r8, aEnduserEzapEas_0; "enduser\\ezap\\easeofaccess\\accessibil"...
0x140021292  mov     edx, 251h; void *
0x140021297  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14002129c  mov     rcx, [rbp+57h+var_10]
0x1400212a0  xor     rcx, rsp; StackCookie
0x1400212a3  call    __security_check_cookie
0x1400212a8  mov     rbx, [rsp+0D0h+arg_8]
0x1400212b0  add     rsp, 0D0h
0x1400212b7  pop     rbp
0x1400212b8  retn
```
