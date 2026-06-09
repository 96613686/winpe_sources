# wil::details::ReleaseMutex(void *)

- ea: `0x180004dd8`
- end: `0x180004e02`
- name: `?ReleaseMutex@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003500`
- `0x180004cfc`

## callees

- `0x180004dd8`
- `0x1800059bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ddc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180004ddc`

## string_xrefs

- `0x180004deb`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::ReleaseMutex(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ReleaseMutex(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA15,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x180004dd8  sub     rsp, 28h
0x180004ddc  call    cs:__imp_ReleaseMutex
0x180004de2  test    eax, eax
0x180004de4  jnz     short loc_180004DFD
0x180004de6  mov     rcx, [rsp+28h]; this
0x180004deb  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004df2  mov     edx, 0A15h; void *
0x180004df7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180004dfd  add     rsp, 28h
0x180004e01  retn
```
