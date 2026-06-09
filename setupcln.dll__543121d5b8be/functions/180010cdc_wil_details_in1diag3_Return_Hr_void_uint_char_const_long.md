# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180010cdc`
- end: `0x180010cfa`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x18000de78`
- `0x18000dfe0`
- `0x18000e1a8`
- `0x18000f204`
- `0x18000fa94`
- `0x18000fbbc`
- `0x18001176c`
- `0x1800117e0`

## callees

- `0x18000cb1c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180010cdc  sub     rsp, 48h
0x180010ce0  mov     rax, [rsp+48h]
0x180010ce5  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180010cea  mov     [rsp+48h+var_20], rax; __int64
0x180010cef  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180010cf4  nop
0x180010cf5  add     rsp, 48h
0x180010cf9  retn
```
