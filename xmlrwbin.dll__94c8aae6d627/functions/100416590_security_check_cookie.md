# __security_check_cookie

- ea: `0x100416590`
- end: `0x1004165ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1004014e0`
- `0x100401600`
- `0x100402b40`
- `0x100402f10`
- `0x100402fe0`
- `0x100403120`
- `0x100403260`
- `0x100403410`
- `0x100403500`
- `0x100403aa0`
- `0x10040b3c0`
- `0x10040bbb0`
- `0x10040cc80`
- `0x10040ed00`
- `0x100412cc0`
- `0x100418000`
- `0x100418a74`
- `0x10041bd5c`
- `0x10041c990`
- `0x10041ceb4`
- `0x10041d2d4`
- `0x10041d88c`
- `0x10041f990`
- `0x10041fe9c`
- `0x1004203bc`
- `0x100420554`
- `0x100420f38`
- `0x1004213b4`
- `0x1004214bc`
- `0x1004215dc`
- `0x100422ae0`
- `0x100423174`
- `0x100423a28`

## callees

- `0x100416590`
- `0x100416980`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x100416590  cmp     rcx, cs:__security_cookie
0x100416597  jnz     short loc_1004165A9
0x100416599  rol     rcx, 10h
0x10041659d  test    cx, 0FFFFh
0x1004165a2  jnz     short loc_1004165A5
0x1004165a4  retn
0x1004165a5  ror     rcx, 10h
0x1004165a9  jmp     __report_gsfailure
```
