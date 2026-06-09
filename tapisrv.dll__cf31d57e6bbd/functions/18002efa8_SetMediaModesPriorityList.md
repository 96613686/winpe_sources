# SetMediaModesPriorityList

- ea: `0x18002efa8`
- end: `0x18002f066`
- name: `SetMediaModesPriorityList`
- size: `190`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027ec0`

## callees

- `0x180001600`
- `0x18001c8a4`
- `0x18002efa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f035`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002f035`
- `KERNEL32!lstrlenW` at `0x18002f00a`
- `KERNEL32!lstrlenW` at `0x18002f00a`

## pseudocode

```c
void __fastcall SetMediaModesPriorityList(HKEY hKey, __int64 a2)
{
  unsigned int v2; // r8d
  unsigned int i; // ebx
  _WORD *v6; // rcx
  int v7; // eax
  wchar_t pszDest[20]; // [rsp+30h] [rbp-48h] BYREF

  v2 = qword_180051960;
  for ( i = 0; i < v2; ++i )
  {
    v6 = *(_WORD **)(a2 + 16LL * i + 8);
    if ( v6 )
    {
      if ( *v6 )
      {
        StringCbPrintfW(pszDest, 0x28u, L"%d", *(unsigned int *)(a2 + 16LL * i));
        v7 = lstrlenW(*(LPCWSTR *)(a2 + 16LL * i + 8));
        RegSetValueExW(hKey, pszDest, 0, 1u, (const BYTE *)(*(_QWORD *)(a2 + 16LL * i + 8) + 2LL), 2 * v7);
        v2 = qword_180051960;
      }
    }
  }
}

```

## disassembly

```asm
0x18002efa8  mov     [rsp+arg_10], rbx
0x18002efad  push    rbp
0x18002efae  push    rsi
0x18002efaf  push    rdi
0x18002efb0  sub     rsp, 60h
0x18002efb4  mov     rax, cs:__security_cookie
0x18002efbb  xor     rax, rsp
0x18002efbe  mov     [rsp+78h+var_20], rax
0x18002efc3  mov     r8d, dword ptr cs:qword_180051960
0x18002efca  xor     ebx, ebx
0x18002efcc  mov     rsi, rdx
0x18002efcf  mov     rbp, rcx
0x18002efd2  test    r8d, r8d
0x18002efd5  jz      short loc_18002F049
0x18002efd7  mov     edi, ebx
0x18002efd9  add     rdi, rdi
0x18002efdc  mov     rcx, [rsi+rdi*8+8]
0x18002efe1  test    rcx, rcx
0x18002efe4  jz      short loc_18002F042
0x18002efe6  xor     eax, eax
0x18002efe8  cmp     ax, [rcx]
0x18002efeb  jz      short loc_18002F042
0x18002efed  mov     r9d, [rsi+rdi*8]
0x18002eff1  lea     r8, aD; "%d"
0x18002eff8  lea     edx, [rax+28h]; cbDest
0x18002effb  lea     rcx, [rsp+78h+pszDest]; pszDest
0x18002f000  call    StringCbPrintfW
0x18002f005  mov     rcx, [rsi+rdi*8+8]; lpString
0x18002f00a  call    cs:__imp_lstrlenW
0x18002f010  mov     rcx, [rsi+rdi*8+8]
0x18002f015  lea     rdx, [rsp+78h+pszDest]; lpValueName
0x18002f01a  add     rcx, 2
0x18002f01e  add     eax, eax
0x18002f020  mov     [rsp+78h+cbData], eax; cbData
0x18002f024  mov     r9d, 1; dwType
0x18002f02a  mov     [rsp+78h+lpData], rcx; lpData
0x18002f02f  xor     r8d, r8d; Reserved
0x18002f032  mov     rcx, rbp; hKey
0x18002f035  call    cs:__imp_RegSetValueExW
0x18002f03b  mov     r8d, dword ptr cs:qword_180051960
0x18002f042  inc     ebx
0x18002f044  cmp     ebx, r8d
0x18002f047  jb      short loc_18002EFD7
0x18002f049  mov     rcx, [rsp+78h+var_20]
0x18002f04e  xor     rcx, rsp; StackCookie
0x18002f051  call    __security_check_cookie
0x18002f056  mov     rbx, [rsp+78h+arg_10]
0x18002f05e  add     rsp, 60h
0x18002f062  pop     rdi
0x18002f063  pop     rsi
0x18002f064  pop     rbp
0x18002f065  retn
```
