# IsolationAwareCreateWindowExW

- ea: `0x180050f68`
- end: `0x18005107c`
- name: `IsolationAwareCreateWindowExW`
- size: `276`
- prototype: `__int64 __fastcall(DWORD dwExStyle, LPCWSTR lpClassName, LPCWSTR lpWindowName, DWORD dwStyle, int, int, int, int, HWND, ULONG_PTR ulCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18004e438`
- `0x180060ca4`
- `0x180063138`

## callees

- `0x180022c04`
- `0x180050f68`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005104a`
- `KERNEL32!GetLastError` at `0x180076447`
- `KERNEL32!GetLastError` at `0x18005104a`
- `KERNEL32!GetLastError` at `0x180076447`
- `KERNEL32!DeactivateActCtx` at `0x180051062`
- `KERNEL32!DeactivateActCtx` at `0x18007645e`
- `KERNEL32!DeactivateActCtx` at `0x180051062`
- `KERNEL32!DeactivateActCtx` at `0x18007645e`
- `KERNEL32!SetLastError` at `0x18005106e`
- `KERNEL32!SetLastError` at `0x18007646a`
- `KERNEL32!SetLastError` at `0x18005106e`
- `KERNEL32!SetLastError` at `0x18007646a`
- `USER32!CreateWindowExW` at `0x180051022`
- `USER32!CreateWindowExW` at `0x180051022`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        DWORD dwExStyle,
        LPCWSTR lpClassName,
        LPCWSTR lpWindowName,
        DWORD dwStyle,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent,
        ULONG_PTR ulCookie)
{
  HINSTANCE hInstance; // r15
  HWND Window; // rax
  HWND v17; // rsi
  int v18; // edi
  DWORD LastError; // ebx

  hInstance = g_hInst;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             dwExStyle,
             lpClassName,
             lpWindowName,
             dwStyle,
             X,
             Y,
             nWidth,
             nHeight,
             hWndParent,
             0,
             hInstance,
             0);
  v17 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v18 = 0;
      LastError = 0;
    }
    else
    {
      v18 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v18 )
      SetLastError(LastError);
  }
  return v17;
}

```

## disassembly

```asm
0x180050f68  mov     rax, rsp
0x180050f6b  push    rbx
0x180050f6c  push    rsi
0x180050f6d  push    rdi
0x180050f6e  push    r14
0x180050f70  push    r15
0x180050f72  sub     rsp, 70h
0x180050f76  mov     ebx, r9d
0x180050f79  mov     rdi, r8
0x180050f7c  mov     rsi, rdx
0x180050f7f  mov     r14d, ecx
0x180050f82  mov     r15, cs:g_hInst
0x180050f89  mov     qword ptr [rax-38h], 0
0x180050f91  mov     qword ptr [rax+50h], 0
0x180050f99  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180050fa0  jnz     short loc_180050FC6
0x180050fa2  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180050fa9  jnz     short loc_180050FC6
0x180050fab  lea     rcx, [rax+50h]; lpCookie
0x180050faf  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180050fb4  test    eax, eax
0x180050fb6  jnz     short loc_180050FC6
0x180050fb8  xor     eax, eax
0x180050fba  add     rsp, 70h
0x180050fbe  pop     r15
0x180050fc0  pop     r14
0x180050fc2  pop     rdi
0x180050fc3  pop     rsi
0x180050fc4  pop     rbx
0x180050fc5  retn
0x180050fc6  mov     [rsp+98h+lpParam], 0; lpParam
0x180050fcf  mov     [rsp+98h+hInstance], r15; hInstance
0x180050fd4  mov     [rsp+98h+hMenu], 0; hMenu
0x180050fdd  mov     rax, [rsp+98h+arg_40]
0x180050fe5  mov     [rsp+98h+hWndParent], rax; hWndParent
0x180050fea  mov     eax, [rsp+98h+arg_38]
0x180050ff1  mov     [rsp+98h+nHeight], eax; nHeight
0x180050ff5  mov     eax, [rsp+98h+arg_30]
0x180050ffc  mov     [rsp+98h+nWidth], eax; nWidth
0x180051000  mov     eax, [rsp+98h+arg_28]
0x180051007  mov     [rsp+98h+Y], eax; Y
0x18005100b  mov     eax, [rsp+98h+arg_20]
0x180051012  mov     [rsp+98h+X], eax; X
0x180051016  mov     r9d, ebx; dwStyle
0x180051019  mov     r8, rdi; lpWindowName
0x18005101c  mov     rdx, rsi; lpClassName
0x18005101f  mov     ecx, r14d; dwExStyle
0x180051022  call    cs:__imp_CreateWindowExW
0x180051028  mov     rsi, rax
0x18005102b  mov     [rsp+98h+var_38], rax
0x180051030  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180051037  jz      short loc_180051042
0x180051039  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180051040  jnz     short loc_180051074
0x180051042  test    rsi, rsi
0x180051045  jnz     short loc_180051054
0x180051047  lea     edi, [rsi+1]
0x18005104a  call    cs:__imp_GetLastError
0x180051050  mov     ebx, eax
0x180051052  jmp     short loc_180051058
0x180051054  xor     edi, edi
0x180051056  xor     ebx, ebx
0x180051058  mov     rdx, [rsp+98h+ulCookie]; ulCookie
0x180051060  xor     ecx, ecx; dwFlags
0x180051062  call    cs:__imp_DeactivateActCtx
0x180051068  test    edi, edi
0x18005106a  jz      short loc_180051074
0x18005106c  mov     ecx, ebx; dwErrCode
0x18005106e  call    cs:__imp_SetLastError
0x180051074  mov     rax, rsi
0x180051077  jmp     loc_180050FBA
0x18007641e  push    rbx
0x180076420  push    rbp
0x180076421  push    rdi
0x180076422  sub     rsp, 60h
0x180076426  mov     rbp, rdx
0x180076429  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180076430  jz      short loc_18007643B
0x180076432  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180076439  jnz     short loc_180076471
0x18007643b  cmp     qword ptr [rbp+60h], 0
0x180076440  jnz     short loc_180076451
0x180076442  mov     edi, 1
0x180076447  call    cs:__imp_GetLastError
0x18007644d  mov     ebx, eax
0x18007644f  jmp     short loc_180076455
0x180076451  xor     edi, edi
0x180076453  xor     ebx, ebx
0x180076455  mov     rdx, [rbp+0E8h]; ulCookie
0x18007645c  xor     ecx, ecx; dwFlags
0x18007645e  call    cs:__imp_DeactivateActCtx
0x180076464  test    edi, edi
0x180076466  jz      short loc_180076471
0x180076468  mov     ecx, ebx; dwErrCode
0x18007646a  call    cs:__imp_SetLastError
0x180076470  nop
0x180076471  add     rsp, 60h
0x180076475  pop     rdi
0x180076476  pop     rbp
0x180076477  pop     rbx
0x180076478  retn
```
