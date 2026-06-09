# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x140005514`
- end: `0x140005536`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `34`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, __int64, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a94`
- `0x14000697c`

## callees

- `0x140002f38`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        __int64 a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2);
}

```

## disassembly

```asm
0x140005514  sub     rsp, 48h
0x140005518  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x140005521  mov     rax, [rsp+48h]
0x140005526  mov     [rsp+48h+var_20], rax
0x14000552b  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x140005530  nop
0x140005531  add     rsp, 48h
0x140005535  retn
```
