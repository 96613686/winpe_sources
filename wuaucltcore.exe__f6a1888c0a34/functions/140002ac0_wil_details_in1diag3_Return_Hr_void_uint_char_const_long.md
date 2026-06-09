# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x140002ac0`
- end: `0x140002ae6`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `38`
- prototype: `void(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, int)`
- caller_count: `98`
- callee_count: `1`
- tags: ``

## callers

- `0x140002aec`
- `0x140003f00`
- `0x140004074`
- `0x140005738`
- `0x140005b58`
- `0x140005e60`
- `0x140005f84`
- `0x14000631c`
- `0x1400066b0`
- `0x1400074c8`
- `0x1400080bc`
- `0x140008afc`
- `0x140008bbc`
- `0x140008c78`
- `0x14000997c`
- `0x14000ae78`
- `0x14000bb94`
- `0x14000bf4c`
- `0x14000c0d0`
- `0x14000c160`
- `0x14000c21c`
- `0x14000c270`
- `0x14000c340`
- `0x14000c430`
- `0x14000c52c`
- `0x14000c80c`
- `0x14000c8cc`
- `0x14000c980`
- `0x14000ca6c`
- `0x14000cae4`
- `0x14000cb5c`
- `0x14000cc58`
- `0x14000cd5c`
- `0x14000ce5c`
- `0x14000ce98`
- `0x14000d308`
- `0x14000ffcc`
- `0x140010128`
- `0x1400105d8`
- `0x140010c44`
- `0x140010e78`
- `0x140010f3c`
- `0x1400110ac`
- `0x1400111a4`
- `0x140011530`
- `0x140011d2c`
- `0x140011f2c`
- `0x140012128`
- `0x1400126b8`
- `0x140012990`

## callees

- `0x140002a5c`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5, 0);
}

```

## disassembly

```asm
0x140002ac0  sub     rsp, 48h
0x140002ac4  mov     rax, [rsp+48h]
0x140002ac9  mov     [rsp+48h+var_10], 0; int
0x140002ad1  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x140002ad6  mov     [rsp+48h+var_20], rax; __int64
0x140002adb  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140002ae0  nop
0x140002ae1  add     rsp, 48h
0x140002ae5  retn
```
