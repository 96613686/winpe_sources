# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000dfb8`
- end: `0x18000dfd5`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c010`
- `0x18000c0c0`
- `0x18000c270`
- `0x18000c450`
- `0x18000c584`
- `0x18000c760`
- `0x18000d19c`
- `0x18000d4b0`
- `0x18000d8f4`
- `0x18000d9d4`
- `0x18000de44`
- `0x18000e43c`
- `0x18000e9c0`
- `0x18000ed20`

## callees

- `0x18000b6c0`

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
0x18000dfb8  sub     rsp, 48h
0x18000dfbc  mov     rax, [rsp+48h]
0x18000dfc1  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000dfc6  mov     [rsp+48h+var_20], rax; __int64
0x18000dfcb  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000dfd0  add     rsp, 48h
0x18000dfd4  retn
```
