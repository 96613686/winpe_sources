# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180002590`
- end: `0x1800025b3`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `35`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025c0`
- `0x180002780`
- `0x180002920`
- `0x1800029c0`
- `0x180002aa0`
- `0x180002b20`
- `0x180002bb0`
- `0x180002c30`
- `0x180002cc0`
- `0x180002d30`
- `0x180002db0`
- `0x180002e40`

## callees

- `0x180001d50`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details::ReportFailure_Hr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180002590  sub     rsp, 58h
0x180002594  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000259d  mov     rax, [rsp+58h]
0x1800025a2  mov     [rsp+58h+var_30], rax
0x1800025a7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800025ac  nop
0x1800025ad  add     rsp, 58h
0x1800025b1  retn
```
