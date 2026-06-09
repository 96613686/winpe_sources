# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180004fb4`
- end: `0x180004fcd`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x180004200`
- `0x1800056a8`
- `0x180007344`
- `0x180007b58`
- `0x180007ca0`
- `0x180008800`
- `0x180008a48`
- `0x180009270`

## callees

- `0x180002c98`

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
0x180004fb4  sub     rsp, 38h
0x180004fb8  mov     rax, [rsp+38h]
0x180004fbd  mov     [rsp+38h+var_10], rax
0x180004fc2  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180004fc7  nop
0x180004fc8  add     rsp, 38h
0x180004fcc  retn
```
