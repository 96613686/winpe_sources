# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180001f64`
- end: `0x180001f7d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001d30`
- `0x1800048b0`
- `0x180004ea8`
- `0x180006558`
- `0x180006718`
- `0x180006a10`

## callees

- `0x180003254`

## pseudocode

```c
__int64 __fastcall wil::details::in1diag3::Return_GetLastError(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4)
{
  return wil::details::ReportFailure_GetLastErrorHr<1>((_DWORD)this, (_DWORD)a2, a3, (_DWORD)a4);
}

```

## disassembly

```asm
0x180001f64  sub     rsp, 38h
0x180001f68  mov     rax, [rsp+38h]
0x180001f6d  mov     [rsp+38h+var_10], rax
0x180001f72  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180001f77  nop
0x180001f78  add     rsp, 38h
0x180001f7c  retn
```
