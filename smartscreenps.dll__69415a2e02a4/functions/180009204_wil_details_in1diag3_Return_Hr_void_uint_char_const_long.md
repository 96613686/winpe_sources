# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180009204`
- end: `0x180009223`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `31`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x18000781c`
- `0x180007aa8`
- `0x1800084c0`
- `0x180008bf0`
- `0x180009958`
- `0x18000b260`
- `0x18000b2b0`
- `0x18000b880`
- `0x18000b8d0`

## callees

- `0x180006dbc`

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
0x180009204  sub     rsp, 48h
0x180009208  mov     rax, [rsp+48h]
0x18000920d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180009212  mov     [rsp+48h+var_20], rax; __int64
0x180009217  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000921c  nop
0x18000921d  add     rsp, 48h
0x180009221  retn
```
