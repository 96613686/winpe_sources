# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140005414`
- end: `0x14000542d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049a4`
- `0x140005e9c`
- `0x140008be0`

## callees

- `0x140002dc8`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3);
}

```

## disassembly

```asm
0x140005414  sub     rsp, 38h
0x140005418  mov     rax, [rsp+38h]
0x14000541d  mov     [rsp+38h+var_10], rax
0x140005422  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140005427  nop
0x140005428  add     rsp, 38h
0x14000542c  retn
```
