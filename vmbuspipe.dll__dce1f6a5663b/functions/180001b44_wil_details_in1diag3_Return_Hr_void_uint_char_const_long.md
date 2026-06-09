# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180001b44`
- end: `0x180001b62`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001980`
- `0x180001d30`
- `0x180004254`
- `0x1800048b0`
- `0x180004ea8`
- `0x18000526c`
- `0x1800056bc`
- `0x180006558`
- `0x180006718`

## callees

- `0x18000336c`

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
0x180001b44  sub     rsp, 48h
0x180001b48  mov     rax, [rsp+48h]
0x180001b4d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180001b52  mov     [rsp+48h+var_20], rax; __int64
0x180001b57  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180001b5c  nop
0x180001b5d  add     rsp, 48h
0x180001b61  retn
```
