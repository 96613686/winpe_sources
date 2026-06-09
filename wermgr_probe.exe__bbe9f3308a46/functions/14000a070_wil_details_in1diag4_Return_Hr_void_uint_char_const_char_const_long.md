# wil::details::in1diag4::Return_Hr(void *,uint,char const *,char const *,long)

- ea: `0x14000a070`
- end: `0x14000a091`
- name: `?Return_Hr@in1diag4@details@wil@@YAXPEAXIPEBD1J@Z`
- size: `33`
- prototype: `void __fastcall(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, wil::details *, int)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x140005464`
- `0x140005f98`
- `0x140010778`
- `0x140010b80`
- `0x140010fac`
- `0x140011d60`
- `0x14001410c`

## callees

- `0x140003bc0`

## pseudocode

```c
void __fastcall wil::details::in1diag4::Return_Hr(
        wil::details::in1diag4 *this,
        void *a2,
        int a3,
        const char *a4,
        wil::details *a5)
{
  int v5; // [rsp+20h] [rbp-28h]
  wil::details *v6; // [rsp+30h] [rbp-18h]
  __int64 retaddr; // [rsp+48h] [rbp+0h]

  LODWORD(v6) = (_DWORD)a5;
  wil::details::ReportFailure_Hr<1>((int)this, (int)a2, a3, (int)a4, v5, retaddr, v6);
}

```

## disassembly

```asm
0x14000a070  sub     rsp, 48h
0x14000a074  mov     r10, [rsp+48h]
0x14000a079  mov     eax, dword ptr [rsp+48h+arg_20]
0x14000a07d  mov     dword ptr [rsp+48h+var_18], eax; wil::details *
0x14000a081  mov     [rsp+48h+var_20], r10; __int64
0x14000a086  call    ??$ReportFailure_Hr@$00@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<1>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a08b  nop
0x14000a08c  add     rsp, 48h
0x14000a090  retn
```
