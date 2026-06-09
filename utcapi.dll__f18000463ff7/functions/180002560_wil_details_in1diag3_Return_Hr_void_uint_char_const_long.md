# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180002560`
- end: `0x180002582`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `34`
- prototype: `void __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002590`
- `0x180002730`
- `0x180002890`
- `0x180002930`
- `0x180002a10`
- `0x180002a90`
- `0x180002b20`
- `0x180002ba0`
- `0x180002c20`
- `0x180002c90`
- `0x180002d00`
- `0x180002d80`

## callees

- `0x180001d48`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  wil::details::ReportFailure_Hr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180002560  sub     rsp, 58h
0x180002564  mov     [rsp+58h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000256d  mov     rax, [rsp+58h]
0x180002572  mov     [rsp+58h+var_30], rax
0x180002577  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000257c  nop
0x18000257d  add     rsp, 58h
0x180002581  retn
```
