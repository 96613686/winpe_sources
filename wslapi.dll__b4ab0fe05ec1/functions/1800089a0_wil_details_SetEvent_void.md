# wil::details::SetEvent(void *)

- ea: `0x1800089a0`
- end: `0x1800089ca`
- name: `?SetEvent@details@wil@@YAXPEAX@Z`
- size: `42`
- prototype: `void __fastcall(wil::details *__hidden this, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800082a0`

## callees

- `0x1800059bc`
- `0x1800089a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800089a4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800089a4`

## string_xrefs

- `0x1800089b3`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details::SetEvent(wil::details *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !SetEvent(this) )
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0xA01,
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v2);
}

```

## disassembly

```asm
0x1800089a0  sub     rsp, 28h
0x1800089a4  call    cs:__imp_SetEvent
0x1800089aa  test    eax, eax
0x1800089ac  jnz     short loc_1800089C5
0x1800089ae  mov     rcx, [rsp+28h]; this
0x1800089b3  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800089ba  mov     edx, 0A01h; void *
0x1800089bf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800089c5  add     rsp, 28h
0x1800089c9  retn
```
