# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180003760`
- end: `0x18000377e`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `25`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180003974`
- `0x180004dfc`
- `0x18000521c`
- `0x180007308`
- `0x180007b64`
- `0x180009064`
- `0x18000aad0`
- `0x18000ab98`
- `0x18000ac10`
- `0x18000ad08`
- `0x18000ae0c`
- `0x18000dc70`
- `0x18000ddcc`
- `0x18000e1c8`
- `0x18000e630`
- `0x18000e6f8`
- `0x18000e8b8`
- `0x18000e9b0`
- `0x18000ecfc`
- `0x18000ef30`
- `0x18000f53c`
- `0x18000f5c0`
- `0x18000f69c`
- `0x18000fabc`

## callees

- `0x180004814`

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
0x180003760  sub     rsp, 48h
0x180003764  mov     rax, [rsp+48h]
0x180003769  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000376e  mov     [rsp+48h+var_20], rax; __int64
0x180003773  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003778  nop
0x180003779  add     rsp, 48h
0x18000377d  retn
```
