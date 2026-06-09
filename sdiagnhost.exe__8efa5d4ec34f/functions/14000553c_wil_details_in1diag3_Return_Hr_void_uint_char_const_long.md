# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x14000553c`
- end: `0x140005563`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `39`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140003bd0`
- `0x140003f74`
- `0x140004a94`
- `0x14000697c`

## callees

- `0x140002fe0`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-38h]
  wil::details *v5; // [rsp+30h] [rbp-28h]
  __int64 retaddr; // [rsp+58h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x14000553c  sub     rsp, 58h
0x140005540  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x140005549  mov     rax, [rsp+58h]
0x14000554e  mov     dword ptr [rsp+58h+var_28], r9d; wil::details *
0x140005553  mov     [rsp+58h+var_30], rax; __int64
0x140005558  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000555d  nop
0x14000555e  add     rsp, 58h
0x140005562  retn
```
