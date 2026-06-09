# IsolationAwareCreateWindowExW

- ea: `0x18001263c`
- end: `0x180012755`
- name: `IsolationAwareCreateWindowExW`
- size: `281`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180011d40`
- `0x180011dc0`
- `0x180011e38`
- `0x18001fd0c`

## callees

- `0x180009a60`
- `0x18001263c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800295a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800295c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800295c6`
- `KERNEL32!DeactivateActCtx` at `0x18001273b`
- `KERNEL32!DeactivateActCtx` at `0x1800295ba`
- `KERNEL32!DeactivateActCtx` at `0x18001273b`
- `KERNEL32!DeactivateActCtx` at `0x1800295ba`
- `USER32!CreateWindowExW` at `0x1800126fb`
- `USER32!CreateWindowExW` at `0x1800126fb`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        DWORD a4,
        int X,
        int Y,
        int nWidth,
        int nHeight,
        HWND hWndParent)
{
  HINSTANCE hInstance; // rsi
  HWND Window; // rax
  HWND v14; // rsi
  int v15; // edi
  DWORD LastError; // ebx
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  hInstance = g_hInst;
  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(0, a2, 0, a4, X, Y, nWidth, nHeight, hWndParent, 0, hInstance, 0);
  v14 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v15 = 0;
      LastError = 0;
    }
    else
    {
      v15 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v15 )
      SetLastError(LastError);
  }
  return v14;
}

```

## disassembly

```asm
0x18001263c  mov     rax, rsp
0x18001263f  mov     [rax+8], rbx
0x180012643  mov     [rax+10h], rsi
0x180012647  mov     [rax+18h], r8
0x18001264b  push    rdi
0x18001264c  sub     rsp, 70h
0x180012650  mov     ebx, r9d
0x180012653  mov     rdi, rdx
0x180012656  mov     rsi, cs:g_hInst
0x18001265d  mov     qword ptr [rax-18h], 0
0x180012665  mov     qword ptr [rax+18h], 0
0x18001266d  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180012674  jnz     short loc_1800126A0
0x180012676  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001267d  jnz     short loc_1800126A0
0x18001267f  lea     rcx, [rax+18h]; lpCookie
0x180012683  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180012688  test    eax, eax
0x18001268a  jnz     short loc_1800126A0
0x18001268c  xor     eax, eax
0x18001268e  lea     r11, [rsp+78h+var_8]
0x180012693  mov     rbx, [r11+10h]
0x180012697  mov     rsi, [r11+18h]
0x18001269b  mov     rsp, r11
0x18001269e  pop     rdi
0x18001269f  retn
0x1800126a0  mov     [rsp+78h+lpParam], 0; lpParam
0x1800126a9  mov     [rsp+78h+hInstance], rsi; hInstance
0x1800126ae  mov     [rsp+78h+hMenu], 0; hMenu
0x1800126b7  mov     rax, [rsp+78h+arg_40]
0x1800126bf  mov     [rsp+78h+hWndParent], rax; hWndParent
0x1800126c4  mov     eax, [rsp+78h+arg_38]
0x1800126cb  mov     [rsp+78h+nHeight], eax; nHeight
0x1800126cf  mov     eax, [rsp+78h+arg_30]
0x1800126d6  mov     [rsp+78h+nWidth], eax; nWidth
0x1800126da  mov     eax, [rsp+78h+arg_28]
0x1800126e1  mov     [rsp+78h+Y], eax; Y
0x1800126e5  mov     eax, [rsp+78h+arg_20]
0x1800126ec  mov     [rsp+78h+X], eax; X
0x1800126f0  mov     r9d, ebx; dwStyle
0x1800126f3  xor     r8d, r8d; lpWindowName
0x1800126f6  mov     rdx, rdi; lpClassName
0x1800126f9  xor     ecx, ecx; dwExStyle
0x1800126fb  call    cs:__imp_CreateWindowExW
0x180012701  mov     rsi, rax
0x180012704  mov     [rsp+78h+var_18], rax
0x180012709  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180012710  jz      short loc_18001271B
0x180012712  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180012719  jnz     short loc_18001274D
0x18001271b  test    rsi, rsi
0x18001271e  jnz     short loc_18001272D
0x180012720  lea     edi, [rsi+1]
0x180012723  call    cs:__imp_GetLastError
0x180012729  mov     ebx, eax
0x18001272b  jmp     short loc_180012731
0x18001272d  xor     edi, edi
0x18001272f  xor     ebx, ebx
0x180012731  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x180012739  xor     ecx, ecx; dwFlags
0x18001273b  call    cs:__imp_DeactivateActCtx
0x180012741  test    edi, edi
0x180012743  jz      short loc_18001274D
0x180012745  mov     ecx, ebx; dwErrCode
0x180012747  call    cs:__imp_SetLastError
0x18001274d  mov     rax, rsi
0x180012750  jmp     loc_18001268E
0x18002957a  push    rbx
0x18002957c  push    rbp
0x18002957d  push    rdi
0x18002957e  sub     rsp, 60h
0x180029582  mov     rbp, rdx
0x180029585  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002958c  jz      short loc_180029597
0x18002958e  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180029595  jnz     short loc_1800295CD
0x180029597  cmp     qword ptr [rbp+60h], 0
0x18002959c  jnz     short loc_1800295AD
0x18002959e  mov     edi, 1
0x1800295a3  call    cs:__imp_GetLastError
0x1800295a9  mov     ebx, eax
0x1800295ab  jmp     short loc_1800295B1
0x1800295ad  xor     edi, edi
0x1800295af  xor     ebx, ebx
0x1800295b1  mov     rdx, [rbp+90h]; ulCookie
0x1800295b8  xor     ecx, ecx; dwFlags
0x1800295ba  call    cs:__imp_DeactivateActCtx
0x1800295c0  test    edi, edi
0x1800295c2  jz      short loc_1800295CD
0x1800295c4  mov     ecx, ebx; dwErrCode
0x1800295c6  call    cs:__imp_SetLastError
0x1800295cc  nop
0x1800295cd  add     rsp, 60h
0x1800295d1  pop     rdi
0x1800295d2  pop     rbp
0x1800295d3  pop     rbx
0x1800295d4  retn
```
