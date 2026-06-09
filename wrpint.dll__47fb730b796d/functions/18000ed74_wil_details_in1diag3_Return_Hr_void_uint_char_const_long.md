# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000ed74`
- end: `0x18000ed91`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b794`
- `0x18000bb64`
- `0x18000bf5c`
- `0x18000d140`
- `0x18000f648`
- `0x18001029c`
- `0x180010448`
- `0x180010750`
- `0x1800109a0`
- `0x180010af0`
- `0x180010de4`
- `0x180010fe0`
- `0x180011248`
- `0x180011364`
- `0x180011654`
- `0x180011e10`
- `0x1800130b8`
- `0x1800138a0`
- `0x180013b2c`
- `0x180014054`
- `0x180014470`
- `0x1800147b0`
- `0x180014ce0`
- `0x180014f38`

## callees

- `0x18000a924`

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
0x18000ed74  sub     rsp, 48h
0x18000ed78  mov     rax, [rsp+48h]
0x18000ed7d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000ed82  mov     [rsp+48h+var_20], rax; __int64
0x18000ed87  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ed8c  add     rsp, 48h
0x18000ed90  retn
```
