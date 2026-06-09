# wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)

- ea: `0x180003784`
- end: `0x18000379d`
- name: `?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z`
- size: `25`
- prototype: `__int64 __fastcall(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x180003974`
- `0x180009790`
- `0x18000e630`
- `0x18000ecfc`
- `0x18000f69c`

## callees

- `0x180004864`

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
0x180003784  sub     rsp, 38h
0x180003788  mov     rax, [rsp+38h]
0x18000378d  mov     [rsp+38h+var_10], rax; __int64
0x180003792  call    ??$ReportFailure_GetLastErrorHr@$00@details@wil@@YAJPEAXIPEBD110@Z; wil::details::ReportFailure_GetLastErrorHr<1>(void *,uint,char const *,char const *,char const *,void *)
0x180003797  nop
0x180003798  add     rsp, 38h
0x18000379c  retn
```
