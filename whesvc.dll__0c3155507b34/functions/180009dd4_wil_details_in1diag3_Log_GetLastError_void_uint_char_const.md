# wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)

- ea: `0x180009dd4`
- end: `0x180009df9`
- name: `?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z`
- size: `37`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a370`

## callees

- `0x180007138`

## string_xrefs

- `0x180009de2`: `onecore\internal\sdk\inc\wil\wrlservicecomponent.h`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  int v4; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  wil::details::ReportFailure_GetLastError<2>(
    (int)this,
    233,
    (int)"onecore\\internal\\sdk\\inc\\wil\\wrlservicecomponent.h",
    v4,
    retaddr);
}

```

## disassembly

```asm
0x180009dd4  sub     rsp, 38h
0x180009dd8  mov     rax, [rsp+38h]
0x180009ddd  mov     [rsp+38h+var_10], rax; __int64
0x180009de2  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\wrlse"...
0x180009de9  mov     edx, 0E9h; int
0x180009dee  call    ??$ReportFailure_GetLastError@$01@details@wil@@YAKPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastError<2>(void *,uint,char const *,char const *,char const *,void *)
0x180009df3  nop
0x180009df4  add     rsp, 38h
0x180009df8  retn
```
