# wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)

- ea: `0x180006858`
- end: `0x180006876`
- name: `?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z`
- size: `30`
- prototype: `void __fastcall(wil::details::in1diag3 *this, void *, int, const char *)`
- caller_count: `21`
- callee_count: `1`
- tags: ``

## callers

- `0x180003128`
- `0x180003984`
- `0x180004ea4`
- `0x180008e70`
- `0x180008fe4`
- `0x180009a28`
- `0x180009e48`
- `0x18000a1e0`
- `0x18000cc78`
- `0x18000cdd4`
- `0x18000d538`
- `0x18000d6f8`
- `0x18000d7f0`
- `0x18000e060`
- `0x18000e0fc`
- `0x18000e174`
- `0x18000e26c`
- `0x18000e370`
- `0x18000e3ac`
- `0x18000e488`
- `0x18000e8a8`

## callees

- `0x180006808`

## pseudocode

```c
void __fastcall wil::details::in1diag3::Return_Hr(wil::details::in1diag3 *this, void *a2, int a3, const char *a4)
{
  int v4; // [rsp+20h] [rbp-28h]
  wil::details *v5; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v5) = (_DWORD)a4;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v4, retaddr, v5);
}

```

## disassembly

```asm
0x180006858  sub     rsp, 48h
0x18000685c  mov     rax, [rsp+48h]
0x180006861  mov     dword ptr [rsp+48h+var_18], r9d; wil::details *
0x180006866  mov     [rsp+48h+var_20], rax; __int64
0x18000686b  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006870  nop
0x180006871  add     rsp, 48h
0x180006875  retn
```
