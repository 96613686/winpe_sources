# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180006d50`
- end: `0x180006d81`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005a50`
- `0x180005b10`
- `0x1800071f0`

## callees

- `0x1800033c4`

## string_xrefs

- `0x180006d6f`: `onecore\vm\dv\vmbus\pipes\dll\client.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    (int)a2,
    (int)"onecore\\vm\\dv\\vmbus\\pipes\\dll\\client.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180006d50  sub     rsp, 48h
0x180006d54  mov     rax, [rsp+48h]
0x180006d59  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006d5e  mov     [rsp+48h+var_20], rax; __int64
0x180006d63  mov     [rsp+48h+var_28], 0; __int64
0x180006d6c  xor     r9d, r9d; int
0x180006d6f  lea     r8, aOnecoreVmDvVmb; "onecore\\vm\\dv\\vmbus\\pipes\\dll\\cli"...
0x180006d76  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006d7b  nop
0x180006d7c  add     rsp, 48h
0x180006d80  retn
```
