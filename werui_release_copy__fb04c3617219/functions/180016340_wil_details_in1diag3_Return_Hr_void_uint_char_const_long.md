# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180016340`
- end: `0x18001635d`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180015490`
- `0x180015658`
- `0x180015b8c`
- `0x180015fd8`
- `0x18001664c`

## callees

- `0x180014cbc`

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
0x180016340  sub     rsp, 48h
0x180016344  mov     rax, [rsp+48h]
0x180016349  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18001634e  mov     [rsp+48h+var_20], rax; __int64
0x180016353  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016358  add     rsp, 48h
0x18001635c  retn
```
