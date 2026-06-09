# RemoveEUDCRegEntry

- ea: `0x180022770`
- end: `0x180022822`
- name: `RemoveEUDCRegEntry`
- size: `178`
- prototype: `__int64 __fastcall(LPCSTR lpValueName)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001f620`

## callees

- `0x18001f470`
- `0x180022770`
- `0x18002a590`

## import_xrefs

- `KERNEL32!RegOpenKeyExA` at `0x1800227d3`
- `KERNEL32!RegOpenKeyExA` at `0x1800227d3`
- `KERNEL32!RegCloseKey` at `0x1800227fd`
- `KERNEL32!RegCloseKey` at `0x1800227fd`
- `KERNEL32!RegDeleteValueA` at `0x1800227e5`
- `KERNEL32!RegDeleteValueA` at `0x1800227e5`

## pseudocode

```c
_BOOL8 __fastcall RemoveEUDCRegEntry(LPCSTR lpValueName, int a2)
{
  BOOL v3; // ebx
  HKEY hKey; // [rsp+30h] [rbp-128h] BYREF
  char pszDest[256]; // [rsp+40h] [rbp-118h] BYREF

  hKey = 0;
  if ( StringCchPrintfA(pszDest, 0x100u, "EUDC\\%lu", a2) < 0
    || RegOpenKeyExA(HKEY_CURRENT_USER, pszDest, 0, 0x2001Fu, &hKey) )
  {
    return 0;
  }
  v3 = RegDeleteValueA(hKey, lpValueName) == 0;
  RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180022770  push    rbx
0x180022772  sub     rsp, 150h
0x180022779  mov     rax, cs:__security_cookie
0x180022780  xor     rax, rsp
0x180022783  mov     [rsp+158h+var_18], rax
0x18002278b  mov     rbx, rcx
0x18002278e  mov     [rsp+158h+hKey], 0
0x180022797  mov     r9d, edx
0x18002279a  lea     rcx, [rsp+158h+pszDest]; pszDest
0x18002279f  mov     edx, 100h; cchDest
0x1800227a4  lea     r8, pszFormat; "EUDC\\%lu"
0x1800227ab  call    StringCchPrintfA
0x1800227b0  test    eax, eax
0x1800227b2  js      short loc_180022807
0x1800227b4  lea     rax, [rsp+158h+hKey]
0x1800227b9  mov     r9d, 2001Fh; samDesired
0x1800227bf  xor     r8d, r8d; ulOptions
0x1800227c2  mov     [rsp+158h+phkResult], rax; phkResult
0x1800227c7  lea     rdx, [rsp+158h+pszDest]; lpSubKey
0x1800227cc  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800227d3  call    cs:__imp_RegOpenKeyExA
0x1800227d9  test    eax, eax
0x1800227db  jnz     short loc_180022807
0x1800227dd  mov     rcx, [rsp+158h+hKey]; hKey
0x1800227e2  mov     rdx, rbx; lpValueName
0x1800227e5  call    cs:__imp_RegDeleteValueA
0x1800227eb  test    eax, eax
0x1800227ed  jz      short loc_1800227F3
0x1800227ef  xor     ebx, ebx
0x1800227f1  jmp     short loc_1800227F8
0x1800227f3  mov     ebx, 1
0x1800227f8  mov     rcx, [rsp+158h+hKey]; hKey
0x1800227fd  call    cs:__imp_RegCloseKey
0x180022803  mov     eax, ebx
0x180022805  jmp     short loc_180022809
0x180022807  xor     eax, eax
0x180022809  mov     rcx, [rsp+158h+var_18]
0x180022811  xor     rcx, rsp; StackCookie
0x180022814  call    __security_check_cookie
0x180022819  add     rsp, 150h
0x180022820  pop     rbx
0x180022821  retn
```
