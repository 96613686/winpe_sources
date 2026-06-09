# wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)

- ea: `0x18000ed98`
- end: `0x18000edb5`
- name: `?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z`
- size: `29`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e10`
- `0x180012e78`
- `0x1800130b8`
- `0x180013b2c`
- `0x180014470`
- `0x1800147b0`
- `0x180014ce0`

## callees

- `0x18000b058`

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
0x18000ed98  sub     rsp, 48h
0x18000ed9c  mov     rax, [rsp+48h]
0x18000eda1  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x18000eda6  mov     [rsp+48h+var_20], rax; __int64
0x18000edab  call    ??$ReportFailure_Win32@$00@details@wil@@YAJPEAXIPEBD110K@Z; wil::details::ReportFailure_Win32<1>(void *,uint,char const *,char const *,char const *,void *,ulong)
0x18000edb0  add     rsp, 48h
0x18000edb4  retn
```
