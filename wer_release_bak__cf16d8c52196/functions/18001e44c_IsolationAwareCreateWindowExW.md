# IsolationAwareCreateWindowExW

- ea: `0x18001e44c`
- end: `0x18001e528`
- name: `IsolationAwareCreateWindowExW`
- size: `220`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18004eb44`

## callees

- `0x18001e44c`
- `0x18001e5dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e51a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aa5cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e51a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800aa5cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e4f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aa5a8`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e50e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa5bf`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e50e`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa5bf`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001e4cc`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001e4cc`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(__int64 a1, const WCHAR *a2)
{
  HWND Window; // rax
  HWND v5; // rbx
  int v6; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+B0h] [rbp+18h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(0, a2, L"WER Fault", 0, 0, 0, 0, 0, 0, 0, 0, 0);
  v5 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v6 = 0;
      LastError = 0;
    }
    else
    {
      v6 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v6 )
      SetLastError(LastError);
  }
  return v5;
}

```

## disassembly

```asm
0x18001e44c  mov     rax, rsp
0x18001e44f  mov     [rax+18h], r8
0x18001e453  push    rbx
0x18001e454  push    rsi
0x18001e455  push    rdi
0x18001e456  push    r14
0x18001e458  sub     rsp, 78h
0x18001e45c  mov     rbx, rdx
0x18001e45f  xor     r14d, r14d
0x18001e462  mov     [rax-38h], r14
0x18001e466  mov     [rax+18h], r14
0x18001e46a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001e471  jnz     short loc_18001E495
0x18001e473  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001e47a  jnz     short loc_18001E495
0x18001e47c  lea     rcx, [rax+18h]; lpCookie
0x18001e480  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001e485  test    eax, eax
0x18001e487  jnz     short loc_18001E495
0x18001e489  xor     eax, eax
0x18001e48b  add     rsp, 78h
0x18001e48f  pop     r14
0x18001e491  pop     rdi
0x18001e492  pop     rsi
0x18001e493  pop     rbx
0x18001e494  retn
0x18001e495  mov     [rsp+98h+lpParam], r14; lpParam
0x18001e49a  mov     [rsp+98h+hInstance], r14; hInstance
0x18001e49f  mov     [rsp+98h+hMenu], r14; hMenu
0x18001e4a4  mov     [rsp+98h+hWndParent], r14; hWndParent
0x18001e4a9  mov     [rsp+98h+nHeight], r14d; nHeight
0x18001e4ae  mov     [rsp+98h+nWidth], r14d; nWidth
0x18001e4b3  mov     [rsp+98h+Y], r14d; Y
0x18001e4b8  mov     [rsp+98h+X], r14d; X
0x18001e4bd  xor     r9d, r9d; dwStyle
0x18001e4c0  lea     r8, WindowName; "WER Fault"
0x18001e4c7  mov     rdx, rbx; lpClassName
0x18001e4ca  xor     ecx, ecx; dwExStyle
0x18001e4cc  call    cs:__imp_CreateWindowExW
0x18001e4d2  mov     rbx, rax
0x18001e4d5  mov     [rsp+98h+var_38], rax
0x18001e4da  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001e4e1  jz      short loc_18001E4EC
0x18001e4e3  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001e4ea  jnz     short loc_18001E520
0x18001e4ec  test    rbx, rbx
0x18001e4ef  jnz     short loc_18001E4FE
0x18001e4f1  lea     esi, [rbx+1]
0x18001e4f4  call    cs:__imp_GetLastError
0x18001e4fa  mov     edi, eax
0x18001e4fc  jmp     short loc_18001E504
0x18001e4fe  mov     esi, r14d
0x18001e501  mov     edi, r14d
0x18001e504  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x18001e50c  xor     ecx, ecx; dwFlags
0x18001e50e  call    cs:__imp_DeactivateActCtx
0x18001e514  test    esi, esi
0x18001e516  jz      short loc_18001E520
0x18001e518  mov     ecx, edi; dwErrCode
0x18001e51a  call    cs:__imp_SetLastError
0x18001e520  mov     rax, rbx
0x18001e523  jmp     loc_18001E48B
0x1800aa57f  push    rbx
0x1800aa581  push    rbp
0x1800aa582  push    rdi
0x1800aa583  sub     rsp, 60h
0x1800aa587  mov     rbp, rdx
0x1800aa58a  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800aa591  jz      short loc_1800AA59C
0x1800aa593  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800aa59a  jnz     short loc_1800AA5D2
0x1800aa59c  cmp     qword ptr [rbp+60h], 0
0x1800aa5a1  jnz     short loc_1800AA5B2
0x1800aa5a3  mov     edi, 1
0x1800aa5a8  call    cs:__imp_GetLastError
0x1800aa5ae  mov     ebx, eax
0x1800aa5b0  jmp     short loc_1800AA5B6
0x1800aa5b2  xor     edi, edi
0x1800aa5b4  xor     ebx, ebx
0x1800aa5b6  mov     rdx, [rbp+0B0h]; ulCookie
0x1800aa5bd  xor     ecx, ecx; dwFlags
0x1800aa5bf  call    cs:__imp_DeactivateActCtx
0x1800aa5c5  test    edi, edi
0x1800aa5c7  jz      short loc_1800AA5D2
0x1800aa5c9  mov     ecx, ebx; dwErrCode
0x1800aa5cb  call    cs:__imp_SetLastError
0x1800aa5d1  nop
0x1800aa5d2  add     rsp, 60h
0x1800aa5d6  pop     rdi
0x1800aa5d7  pop     rbp
0x1800aa5d8  pop     rbx
0x1800aa5d9  retn
```
