# TraceUpdateConsoleTitleA

- ea: `0x180003530`
- end: `0x1800035b6`
- name: `TraceUpdateConsoleTitleA`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800026d0`
- `0x180009838`

## callees

- `0x180003040`
- `0x180003530`
- `0x180003bb0`

## import_xrefs

- `api-ms-win-core-console-l2-2-0!SetConsoleTitleA` at `0x180003596`
- `api-ms-win-core-console-l2-2-0!SetConsoleTitleA` at `0x180003596`

## pseudocode

```c
__int64 __fastcall TraceUpdateConsoleTitleA(__int64 a1)
{
  const char *v1; // r8
  __int64 result; // rax
  char pszDest[272]; // [rsp+20h] [rbp-128h] BYREF

  v1 = "%s [Tracing Inactive]";
  if ( (*(_BYTE *)(a1 + 56) & 1) == 0 )
    v1 = "%s [Tracing Active]";
  LODWORD(result) = StringCbPrintfA(pszDest, 0x104u, v1, a1 + 64);
  if ( (int)result < 0 )
    return (unsigned __int16)result;
  SetConsoleTitleA(pszDest);
  return 0;
}

```

## disassembly

```asm
0x180003530  sub     rsp, 148h
0x180003537  mov     rax, cs:__security_cookie
0x18000353e  xor     rax, rsp
0x180003541  mov     [rsp+148h+var_18], rax
0x180003549  test    byte ptr [rcx+38h], 1
0x18000354d  lea     rax, aSTracingActive; "%s [Tracing Active]"
0x180003554  lea     r9, [rcx+40h]
0x180003558  mov     edx, 104h; cbDest
0x18000355d  lea     r8, aSTracingInacti; "%s [Tracing Inactive]"
0x180003564  cmovz   r8, rax; pszFormat
0x180003568  lea     rcx, [rsp+148h+pszDest]; pszDest
0x18000356d  call    StringCbPrintfA
0x180003572  test    eax, eax
0x180003574  jns     short loc_180003591
0x180003576  movzx   eax, ax
0x180003579  mov     rcx, [rsp+148h+var_18]
0x180003581  xor     rcx, rsp; StackCookie
0x180003584  call    __security_check_cookie
0x180003589  add     rsp, 148h
0x180003590  retn
0x180003591  lea     rcx, [rsp+148h+pszDest]; lpConsoleTitle
0x180003596  call    cs:__imp_SetConsoleTitleA
0x18000359c  xor     eax, eax
0x18000359e  mov     rcx, [rsp+148h+var_18]
0x1800035a6  xor     rcx, rsp; StackCookie
0x1800035a9  call    __security_check_cookie
0x1800035ae  add     rsp, 148h
0x1800035b5  retn
```
