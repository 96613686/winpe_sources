# wil::details::CloseHandle(void *)

- ea: `0x1800037f4`
- end: `0x18000381e`
- name: `?CloseHandle@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034e4`
- `0x180005acc`
- `0x180009e88`

## callees

- `0x1800037f4`
- `0x1800059bc`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800037f8`

## string_xrefs

- `0x180003807`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::CloseHandle(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !CloseHandle(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x1800037f4  sub     rsp, 28h
0x1800037f8  call    cs:__imp_CloseHandle
0x1800037fe  test    eax, eax
0x180003800  jnz     short loc_180003819
0x180003802  mov     rcx, [rsp+28h]; this
0x180003807  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000380e  mov     edx, 0A0Bh; void *
0x180003813  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003819  add     rsp, 28h
0x18000381d  retn
```
