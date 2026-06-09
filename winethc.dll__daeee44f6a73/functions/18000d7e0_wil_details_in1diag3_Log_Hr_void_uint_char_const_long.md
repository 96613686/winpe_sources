# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x18000d7e0`
- end: `0x18000d811`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `49`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004fcc`

## callees

- `0x180002230`

## string_xrefs

- `0x18000d7e9`: `net\diagnostics\common\inc\nlautil.h`

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
    (int)"net\\diagnostics\\common\\inc\\nlautil.h",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x18000d7e0  sub     rsp, 48h
0x18000d7e4  mov     rax, [rsp+48h]
0x18000d7e9  lea     r8, aNetDiagnostics; "net\\diagnostics\\common\\inc\\nlautil."...
0x18000d7f0  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000d7f5  xor     r9d, r9d; int
0x18000d7f8  mov     [rsp+48h+var_20], rax; __int64
0x18000d7fd  mov     [rsp+48h+var_28], 0; __int64
0x18000d806  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d80b  add     rsp, 48h
0x18000d80f  retn
```
