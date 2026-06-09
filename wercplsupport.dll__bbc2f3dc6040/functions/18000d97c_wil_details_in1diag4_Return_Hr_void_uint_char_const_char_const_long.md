# wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)

- ea: `0x18000d97c`
- end: `0x18000d99c`
- name: `?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z`
- size: `32`
- prototype: `void __fastcall(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, wil::details *, int)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180009b78`
- `0x180009f58`
- `0x18000a410`
- `0x18000b92c`
- `0x18000e098`

## callees

- `0x1800087ec`

## pseudocode

```c
void __fastcall wil::details::in1diag4::Return_Hr(
        wil::details::in1diag4 *this,
        void *a2,
        __int64 a3,
        const char *a4,
        wil::details *a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a5;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, retaddr, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x18000d97c  sub     rsp, 48h
0x18000d980  mov     r8, [rsp+48h]; int
0x18000d985  mov     eax, dword ptr [rsp+48h+arg_20]
0x18000d989  mov     dword ptr [rsp+48h+var_18], eax; wil::details *
0x18000d98d  mov     [rsp+48h+var_20], r8; __int64
0x18000d992  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d997  add     rsp, 48h
0x18000d99b  retn
```
