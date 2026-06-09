# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000cb0c`
- end: `0x18000cb2a`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000794c`
- `0x180007d44`
- `0x180008288`
- `0x180009994`
- `0x18000dec0`

## callees

- `0x1800067c0`

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
0x18000cb0c  sub     rsp, 48h
0x18000cb10  mov     rax, [rsp+48h]
0x18000cb15  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000cb1a  mov     [rsp+48h+var_20], rax; __int64
0x18000cb1f  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000cb24  add     rsp, 48h
0x18000cb28  retn
```
