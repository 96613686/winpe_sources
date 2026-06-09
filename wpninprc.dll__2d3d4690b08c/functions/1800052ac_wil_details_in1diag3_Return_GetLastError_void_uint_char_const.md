# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800052ac`
- end: `0x1800052c5`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180004be0`
- `0x1800055c0`

## callees

- `0x180003818`

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
0x1800052ac  sub     rsp, 38h
0x1800052b0  mov     rax, [rsp+38h]
0x1800052b5  mov     [rsp+38h+var_10], rax
0x1800052ba  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1800052bf  nop
0x1800052c0  add     rsp, 38h
0x1800052c4  retn
```
