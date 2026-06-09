# IsolationAwareCreateWindowExW

- ea: `0x180022f4c`
- end: `0x18002304c`
- name: `IsolationAwareCreateWindowExW`
- size: `256`
- prototype: `__int64 __fastcall(int, int, int, int, int, int, int, int, HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180020c0c`

## callees

- `0x18000c6ec`
- `0x180022f4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002301a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002301a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e844`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002303e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e867`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002303e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002e867`
- `KERNEL32!DeactivateActCtx` at `0x180023032`
- `KERNEL32!DeactivateActCtx` at `0x18002e85b`
- `KERNEL32!DeactivateActCtx` at `0x180023032`
- `KERNEL32!DeactivateActCtx` at `0x18002e85b`
- `USER32!CreateWindowExW` at `0x180022ff2`
- `USER32!CreateWindowExW` at `0x180022ff2`

## pseudocode

```c
HWND __fastcall IsolationAwareCreateWindowExW(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        HWND hWndParent)
{
  HWND Window; // rax
  HWND v11; // rbx
  int v12; // esi
  DWORD LastError; // edi
  ULONG_PTR ulCookie; // [rsp+90h] [rbp+18h] BYREF

  ulCookie = 0;
  if ( !IsolationAwarePrivateT_SAbnPgpgk
    && !IsolationAwarePrivateT_SqbjaYRiRY
    && !(unsigned int)IsolationAwarePrivatenPgViNgRzlnPgpgk(&ulCookie) )
  {
    return 0;
  }
  Window = CreateWindowExW(
             0,
             L"tooltips_class32",
             0,
             0x80000042,
             0x80000000,
             0x80000000,
             0x80000000,
             0x80000000,
             hWndParent,
             0,
             0,
             0);
  v11 = Window;
  if ( !IsolationAwarePrivateT_SAbnPgpgk || !IsolationAwarePrivateT_SqbjaYRiRY )
  {
    if ( Window )
    {
      v12 = 0;
      LastError = 0;
    }
    else
    {
      v12 = 1;
      LastError = GetLastError();
    }
    DeactivateActCtx(0, ulCookie);
    if ( v12 )
      SetLastError(LastError);
  }
  return v11;
}

```

## disassembly

```asm
0x180022f4c  mov     rax, rsp
0x180022f4f  mov     [rax+8], rbx
0x180022f53  mov     [rax+10h], rsi
0x180022f57  mov     [rax+18h], r8
0x180022f5b  push    rdi
0x180022f5c  sub     rsp, 70h
0x180022f60  mov     qword ptr [rax-18h], 0
0x180022f68  mov     qword ptr [rax+18h], 0
0x180022f70  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180022f77  jnz     short loc_180022FA3
0x180022f79  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180022f80  jnz     short loc_180022FA3
0x180022f82  lea     rcx, [rax+18h]; lpCookie
0x180022f86  call    IsolationAwarePrivatenPgViNgRzlnPgpgk
0x180022f8b  test    eax, eax
0x180022f8d  jnz     short loc_180022FA3
0x180022f8f  xor     eax, eax
0x180022f91  lea     r11, [rsp+78h+var_8]
0x180022f96  mov     rbx, [r11+10h]
0x180022f9a  mov     rsi, [r11+18h]
0x180022f9e  mov     rsp, r11
0x180022fa1  pop     rdi
0x180022fa2  retn
0x180022fa3  mov     [rsp+78h+lpParam], 0; lpParam
0x180022fac  mov     [rsp+78h+hInstance], 0; hInstance
0x180022fb5  mov     [rsp+78h+hMenu], 0; hMenu
0x180022fbe  mov     rax, [rsp+78h+arg_40]
0x180022fc6  mov     [rsp+78h+hWndParent], rax; hWndParent
0x180022fcb  mov     eax, 80000000h
0x180022fd0  mov     [rsp+78h+nHeight], eax; nHeight
0x180022fd4  mov     [rsp+78h+nWidth], eax; nWidth
0x180022fd8  mov     [rsp+78h+Y], eax; Y
0x180022fdc  mov     [rsp+78h+X], eax; X
0x180022fe0  mov     r9d, 80000042h; dwStyle
0x180022fe6  xor     r8d, r8d; lpWindowName
0x180022fe9  lea     rdx, ClassName; "tooltips_class32"
0x180022ff0  xor     ecx, ecx; dwExStyle
0x180022ff2  call    cs:__imp_CreateWindowExW
0x180022ff8  mov     rbx, rax
0x180022ffb  mov     [rsp+78h+var_18], rax
0x180023000  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x180023007  jz      short loc_180023012
0x180023009  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180023010  jnz     short loc_180023044
0x180023012  test    rbx, rbx
0x180023015  jnz     short loc_180023024
0x180023017  lea     esi, [rbx+1]
0x18002301a  call    cs:__imp_GetLastError
0x180023020  mov     edi, eax
0x180023022  jmp     short loc_180023028
0x180023024  xor     esi, esi
0x180023026  xor     edi, edi
0x180023028  mov     rdx, [rsp+78h+ulCookie]; ulCookie
0x180023030  xor     ecx, ecx; dwFlags
0x180023032  call    cs:__imp_DeactivateActCtx
0x180023038  test    esi, esi
0x18002303a  jz      short loc_180023044
0x18002303c  mov     ecx, edi; dwErrCode
0x18002303e  call    cs:__imp_SetLastError
0x180023044  mov     rax, rbx
0x180023047  jmp     loc_180022F91
0x18002e81b  push    rbx
0x18002e81d  push    rbp
0x18002e81e  push    rdi
0x18002e81f  sub     rsp, 60h
0x18002e823  mov     rbp, rdx
0x18002e826  cmp     cs:IsolationAwarePrivateT_SAbnPgpgk, 0
0x18002e82d  jz      short loc_18002E838
0x18002e82f  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18002e836  jnz     short loc_18002E86E
0x18002e838  cmp     qword ptr [rbp+60h], 0
0x18002e83d  jnz     short loc_18002E84E
0x18002e83f  mov     edi, 1
0x18002e844  call    cs:__imp_GetLastError
0x18002e84a  mov     ebx, eax
0x18002e84c  jmp     short loc_18002E852
0x18002e84e  xor     edi, edi
0x18002e850  xor     ebx, ebx
0x18002e852  mov     rdx, [rbp+90h]; ulCookie
0x18002e859  xor     ecx, ecx; dwFlags
0x18002e85b  call    cs:__imp_DeactivateActCtx
0x18002e861  test    edi, edi
0x18002e863  jz      short loc_18002E86E
0x18002e865  mov     ecx, ebx; dwErrCode
0x18002e867  call    cs:__imp_SetLastError
0x18002e86d  nop
0x18002e86e  add     rsp, 60h
0x18002e872  pop     rdi
0x18002e873  pop     rbp
0x18002e874  pop     rbx
0x18002e875  retn
```
