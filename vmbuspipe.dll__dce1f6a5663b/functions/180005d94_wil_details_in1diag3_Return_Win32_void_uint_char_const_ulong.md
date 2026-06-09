# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x180005d94`
- end: `0x180005db2`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `30`
- prototype: `int(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001b84`
- `0x180001d30`
- `0x1800048b0`
- `0x1800049fc`
- `0x180006718`
- `0x180006a10`
- `0x1800076d0`

## callees

- `0x1800039a8`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_Win32(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x180005d94  sub     rsp, 48h
0x180005d98  mov     rax, [rsp+48h]
0x180005d9d  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180005da2  mov     [rsp+48h+var_20], rax; __int64
0x180005da7  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x180005dac  nop
0x180005dad  add     rsp, 48h
0x180005db1  retn
```
