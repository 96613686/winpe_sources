# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x1800061b0`
- end: `0x1800061c9`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180005550`
- `0x180008e70`
- `0x180008fe4`
- `0x18000a1e0`
- `0x18000e488`

## callees

- `0x1800060ec`

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
0x1800061b0  sub     rsp, 38h
0x1800061b4  mov     rax, [rsp+38h]
0x1800061b9  mov     [rsp+38h+var_10], rax
0x1800061be  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x1800061c3  nop
0x1800061c4  add     rsp, 38h
0x1800061c8  retn
```
