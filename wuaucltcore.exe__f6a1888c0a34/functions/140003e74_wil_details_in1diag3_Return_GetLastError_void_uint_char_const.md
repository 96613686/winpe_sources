# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140003e74`
- end: `0x140003e8d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f00`
- `0x140004074`
- `0x140005f84`
- `0x1400066b0`
- `0x1400080bc`
- `0x140009be0`
- `0x14000b110`
- `0x14000c80c`
- `0x140010c44`
- `0x1400114f0`
- `0x140014cac`
- `0x1400189f4`
- `0x140018b14`

## callees

- `0x140005554`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  int v5; // [rsp+20h] [rbp-18h]
  __int64 retaddr; // [rsp+38h] [rbp+0h]

  return wil::details::ReportFailure_GetLastErrorHr<1>((int)this, (int)a2, a3, v5, retaddr);
}

```

## disassembly

```asm
0x140003e74  sub     rsp, 38h
0x140003e78  mov     rax, [rsp+38h]
0x140003e7d  mov     [rsp+38h+var_10], rax; __int64
0x140003e82  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140003e87  nop
0x140003e88  add     rsp, 38h
0x140003e8c  retn
```
