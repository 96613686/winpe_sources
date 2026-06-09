# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180005230`
- end: `0x18000524d`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000383c`
- `0x180003be0`
- `0x180004840`
- `0x180005710`
- `0x18001a148`

## callees

- `0x180002fa0`

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
0x180005230  sub     rsp, 48h
0x180005234  mov     rax, [rsp+48h]
0x180005239  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000523e  mov     [rsp+48h+var_20], rax; __int64
0x180005243  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005248  add     rsp, 48h
0x18000524c  retn
```
