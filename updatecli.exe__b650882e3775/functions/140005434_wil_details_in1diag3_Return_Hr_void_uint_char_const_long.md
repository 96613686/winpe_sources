# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140005434`
- end: `0x140005452`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a18`
- `0x140003de8`
- `0x1400049a4`
- `0x140005e9c`
- `0x1400065f4`

## callees

- `0x140002e70`

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
0x140005434  sub     rsp, 48h
0x140005438  mov     rax, [rsp+48h]
0x14000543d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140005442  mov     [rsp+48h+var_20], rax; __int64
0x140005447  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000544c  nop
0x14000544d  add     rsp, 48h
0x140005451  retn
```
