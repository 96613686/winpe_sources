# wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)

- ea: `0x180021d50`
- end: `0x180021d6b`
- name: `?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `27`
- prototype: `void __fastcall __noreturn(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ff4c`
- `0x1800283c8`

## callees

- `0x18001cc40`

## string_xrefs

- `0x180021d59`: `onecore\internal\vm\inc\private\common\vml\VmString.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::in1diag3::Throw_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  char *retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<0>(
    (int)this,
    (int)a2,
    (int)"onecore\\internal\\vm\\inc\\private\\common\\vml\\VmString.h",
    (int)a4,
    v4,
    retaddr);
}

```

## disassembly

```asm
0x180021d50  sub     rsp, 38h
0x180021d54  mov     rax, [rsp+38h]
0x180021d59  lea     r8, aOnecoreInterna_4; "onecore\\internal\\vm\\inc\\private\\co"...
0x180021d60  mov     [rsp+38h+var_10], rax; char *
0x180021d65  call    ??$ReportFailure_GetLastError@$0A@@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<0>(void *,uint,char const *,char const *,char const *,void *)
```
