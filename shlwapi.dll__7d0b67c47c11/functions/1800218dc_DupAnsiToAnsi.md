# DupAnsiToAnsi

- ea: `0x1800218dc`
- end: `0x180021934`
- name: `DupAnsiToAnsi`
- size: `88`
- prototype: `__int64 __fastcall(STRSAFE_LPCSTR pszSrc)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021bb0`

## callees

- `0x180017344`
- `0x1800218dc`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800218f1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800218f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800218ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800218ff`

## pseudocode

```c
__int64 __fastcall DupAnsiToAnsi(STRSAFE_LPCSTR pszSrc, char **a2)
{
  SIZE_T v4; // rsi
  char *v5; // rax

  v4 = lstrlenA(pszSrc) + 1;
  v5 = (char *)CoTaskMemAlloc(v4);
  *a2 = v5;
  if ( !v5 )
    return 2147942414LL;
  StringCchCopyA(v5, v4, pszSrc);
  return 0;
}

```

## disassembly

```asm
0x1800218dc  mov     [rsp+arg_0], rbx
0x1800218e1  mov     [rsp+arg_8], rsi
0x1800218e6  push    rdi
0x1800218e7  sub     rsp, 20h
0x1800218eb  mov     rbx, rdx
0x1800218ee  mov     rdi, rcx
0x1800218f1  call    cs:__imp_lstrlenA
0x1800218f7  inc     eax
0x1800218f9  movsxd  rsi, eax
0x1800218fc  mov     rcx, rsi; cb
0x1800218ff  call    cs:__imp_CoTaskMemAlloc
0x180021905  mov     [rbx], rax
0x180021908  test    rax, rax
0x18002190b  jz      short loc_18002191F
0x18002190d  mov     r8, rdi; pszSrc
0x180021910  mov     rdx, rsi; cchDest
0x180021913  mov     rcx, rax; pszDest
0x180021916  call    StringCchCopyA
0x18002191b  xor     eax, eax
0x18002191d  jmp     short loc_180021924
0x18002191f  mov     eax, 8007000Eh
0x180021924  mov     rbx, [rsp+28h+arg_0]
0x180021929  mov     rsi, [rsp+28h+arg_8]
0x18002192e  add     rsp, 20h
0x180021932  pop     rdi
0x180021933  retn
```
