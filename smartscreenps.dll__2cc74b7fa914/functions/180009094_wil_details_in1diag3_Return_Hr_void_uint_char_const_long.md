# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180009094`
- end: `0x1800090b2`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180007848`
- `0x180007a24`
- `0x1800083ec`
- `0x180008acc`
- `0x180009798`
- `0x18000afb0`
- `0x18000b000`
- `0x18000b5d0`
- `0x18000b620`

## callees

- `0x180006dac`

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
0x180009094  sub     rsp, 48h
0x180009098  mov     rax, [rsp+48h]
0x18000909d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x1800090a2  mov     [rsp+48h+var_20], rax; __int64
0x1800090a7  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800090ac  nop
0x1800090ad  add     rsp, 48h
0x1800090b1  retn
```
