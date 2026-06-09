# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180017860`
- end: `0x180017896`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `54`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180016954`

## callees

- `0x180002e24`

## string_xrefs

- `0x18001787f`: `onecore\ds\security\scard\vscr\transports\simulator\cards\tpmvsc\dll\cardops.cpp`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, __int64 a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>(
    (int)this,
    382,
    (int)"onecore\\ds\\security\\scard\\vscr\\transports\\simulator\\cards\\tpmvsc\\dll\\cardops.cpp",
    0,
    0,
    retaddr,
    v4);
}

```

## disassembly

```asm
0x180017860  sub     rsp, 48h
0x180017864  mov     rax, [rsp+48h]
0x180017869  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18001786e  mov     [rsp+48h+var_20], rax; __int64
0x180017873  mov     [rsp+48h+var_28], 0; __int64
0x18001787c  xor     r9d, r9d; int
0x18001787f  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\scard\\vscr\\tra"...
0x180017886  mov     edx, 17Eh; int
0x18001788b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180017890  nop
0x180017891  add     rsp, 48h
0x180017895  retn
```
