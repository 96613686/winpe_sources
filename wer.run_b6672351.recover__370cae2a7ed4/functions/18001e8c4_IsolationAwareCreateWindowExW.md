# IsolationAwareCreateWindowExW

- ea: `0x18001e8c4`
- end: `0x18001e9b9`
- name: `IsolationAwareCreateWindowExW`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180050f58`

## callees

- `0x18001e8c4`
- `0x18001ea84`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e9a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af5e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e9a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800af5e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e973`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800af5b4`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e993`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af5d1`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e993`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800af5d1`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001e945`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExW` at `0x18001e945`

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
0x18001e8c4  mov     rax, rsp
0x18001e8c7  mov     [rax+18h], r8
0x18001e8cb  push    rbx
0x18001e8cc  push    rsi
0x18001e8cd  push    rdi
0x18001e8ce  push    r14
0x18001e8d0  sub     rsp, 78h
0x18001e8d4  mov     rbx, rdx
0x18001e8d7  xor     r14d, r14d
0x18001e8da  mov     [rax-38h], r14
0x18001e8de  mov     [rax+18h], r14
0x18001e8e2  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001e8e9  jnz     short loc_18001E90E
0x18001e8eb  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001e8f2  jnz     short loc_18001E90E
0x18001e8f4  lea     rcx, [rax+18h]; lpCookie
0x18001e8f8  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x18001e8fd  test    eax, eax
0x18001e8ff  jnz     short loc_18001E90E
0x18001e901  xor     eax, eax
0x18001e903  add     rsp, 78h
0x18001e907  pop     r14
0x18001e909  pop     rdi
0x18001e90a  pop     rsi
0x18001e90b  pop     rbx
0x18001e90c  retn
0x18001e90e  mov     [rsp+98h+lpParam], r14; lpParam
0x18001e913  mov     [rsp+98h+hInstance], r14; hInstance
0x18001e918  mov     [rsp+98h+hMenu], r14; hMenu
0x18001e91d  mov     [rsp+98h+hWndParent], r14; hWndParent
0x18001e922  mov     [rsp+98h+nHeight], r14d; nHeight
0x18001e927  mov     [rsp+98h+nWidth], r14d; nWidth
0x18001e92c  mov     [rsp+98h+Y], r14d; Y
0x18001e931  mov     [rsp+98h+X], r14d; X
0x18001e936  xor     r9d, r9d; dwStyle
0x18001e939  lea     r8, WindowName; "WER Fault"
0x18001e940  mov     rdx, rbx; lpClassName
0x18001e943  xor     ecx, ecx; dwExStyle
0x18001e945  call    cs:__imp_CreateWindowExW
0x18001e94c  nop     dword ptr [rax+rax+00h]
0x18001e951  mov     rbx, rax
0x18001e954  mov     [rsp+98h+var_38], rax
0x18001e959  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, r14d
0x18001e960  jz      short loc_18001E96B
0x18001e962  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, r14d
0x18001e969  jnz     short loc_18001E9B1
0x18001e96b  test    rbx, rbx
0x18001e96e  jnz     short loc_18001E983
0x18001e970  lea     esi, [rbx+1]
0x18001e973  call    cs:__imp_GetLastError
0x18001e97a  nop     dword ptr [rax+rax+00h]
0x18001e97f  mov     edi, eax
0x18001e981  jmp     short loc_18001E989
0x18001e983  mov     esi, r14d
0x18001e986  mov     edi, r14d
0x18001e989  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x18001e991  xor     ecx, ecx; dwFlags
0x18001e993  call    cs:__imp_DeactivateActCtx
0x18001e99a  nop     dword ptr [rax+rax+00h]
0x18001e99f  test    esi, esi
0x18001e9a1  jz      short loc_18001E9B1
0x18001e9a3  mov     ecx, edi; dwErrCode
0x18001e9a5  call    cs:__imp_SetLastError
0x18001e9ac  nop     dword ptr [rax+rax+00h]
0x18001e9b1  mov     rax, rbx
0x18001e9b4  jmp     loc_18001E903
0x1800af58b  push    rbx
0x1800af58d  push    rbp
0x1800af58e  push    rdi
0x1800af58f  sub     rsp, 60h
0x1800af593  mov     rbp, rdx
0x1800af596  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x1800af59d  jz      short loc_1800AF5A8
0x1800af59f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800af5a6  jnz     short loc_1800AF5F0
0x1800af5a8  cmp     qword ptr [rbp+60h], 0
0x1800af5ad  jnz     short loc_1800AF5C4
0x1800af5af  mov     edi, 1
0x1800af5b4  call    cs:__imp_GetLastError
0x1800af5bb  nop     dword ptr [rax+rax+00h]
0x1800af5c0  mov     ebx, eax
0x1800af5c2  jmp     short loc_1800AF5C8
0x1800af5c4  xor     edi, edi
0x1800af5c6  xor     ebx, ebx
0x1800af5c8  mov     rdx, [rbp+0B0h]; ulCookie
0x1800af5cf  xor     ecx, ecx; dwFlags
0x1800af5d1  call    cs:__imp_DeactivateActCtx
0x1800af5d8  nop     dword ptr [rax+rax+00h]
0x1800af5dd  test    edi, edi
0x1800af5df  jz      short loc_1800AF5F0
0x1800af5e1  mov     ecx, ebx; dwErrCode
0x1800af5e3  call    cs:__imp_SetLastError
0x1800af5ea  nop     dword ptr [rax+rax+00h]
0x1800af5ef  nop
0x1800af5f0  add     rsp, 60h
0x1800af5f4  pop     rdi
0x1800af5f5  pop     rbp
0x1800af5f6  pop     rbx
0x1800af5f7  retn
```
