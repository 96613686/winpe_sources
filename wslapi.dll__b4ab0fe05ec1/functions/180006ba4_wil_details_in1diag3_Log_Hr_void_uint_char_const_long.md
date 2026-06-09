# wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)

- ea: `0x180006ba4`
- end: `0x180006bce`
- name: `?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `42`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800069e4`
- `0x180006aa0`
- `0x180006f80`
- `0x18000710c`
- `0x1800071b0`
- `0x1800079cc`
- `0x180007a80`
- `0x180008ea0`

## callees

- `0x180002d74`

## pseudocode

```c
void __fastcall wil::details::in1diag3::_Log_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details *v4; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v4) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<2>((int)this, (int)a2, a3, 0, 0, retaddr, v4);
}

```

## disassembly

```asm
0x180006ba4  sub     rsp, 48h
0x180006ba8  mov     rax, [rsp+48h]
0x180006bad  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006bb2  mov     [rsp+48h+var_20], rax; __int64
0x180006bb7  mov     [rsp+48h+var_28], 0; __int64
0x180006bc0  xor     r9d, r9d; int
0x180006bc3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006bc8  nop
0x180006bc9  add     rsp, 48h
0x180006bcd  retn
```
