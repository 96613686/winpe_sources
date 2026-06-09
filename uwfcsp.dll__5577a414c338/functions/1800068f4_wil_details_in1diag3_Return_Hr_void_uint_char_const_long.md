# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x1800068f4`
- end: `0x180006911`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180004f1c`
- `0x1800052ec`
- `0x180005e84`
- `0x180006dbc`
- `0x1800092a0`
- `0x18000d7f0`
- `0x18000eed0`

## callees

- `0x18000461c`

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
0x1800068f4  sub     rsp, 48h
0x1800068f8  mov     rax, [rsp+48h]
0x1800068fd  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006902  mov     [rsp+48h+var_20], rax; __int64
0x180006907  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000690c  add     rsp, 48h
0x180006910  retn
```
