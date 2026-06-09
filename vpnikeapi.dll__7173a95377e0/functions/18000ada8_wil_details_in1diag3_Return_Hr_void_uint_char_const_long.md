# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x18000ada8`
- end: `0x18000adc5`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `29`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180007f30`
- `0x180008098`
- `0x180008260`
- `0x180009124`
- `0x180009a80`
- `0x180009ba8`
- `0x18000b528`
- `0x18000b59c`

## callees

- `0x180006f0c`

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
0x18000ada8  sub     rsp, 48h
0x18000adac  mov     rax, [rsp+48h]
0x18000adb1  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000adb6  mov     [rsp+48h+var_20], rax; __int64
0x18000adbb  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000adc0  add     rsp, 48h
0x18000adc4  retn
```
