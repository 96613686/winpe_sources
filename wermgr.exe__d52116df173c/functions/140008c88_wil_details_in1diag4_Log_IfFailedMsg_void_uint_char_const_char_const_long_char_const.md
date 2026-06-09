# wil::details::in1diag4::Log_IfFailedMsg(void *,uint,char const *,char const *,long,char const *,...)

- ea: `0x140008c88`
- end: `0x140008cdb`
- name: `?Log_IfFailedMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ`
- size: `83`
- prototype: `__int64(wil::details::in1diag4 *this, void *, int, const char *, wil::details *, __int64, const char *, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400058ec`
- `0x14000659c`
- `0x14000a1ac`
- `0x14000e49c`

## callees

- `0x140003c74`
- `0x140008c88`

## pseudocode

```c
__int64 wil::details::in1diag4::Log_IfFailedMsg(
        wil::details::in1diag4 *this,
        void *a2,
        int a3,
        const char *a4,
        wil::details *a5,
        __int64 a6,
        const char *a7,
        ...)
{
  int v8; // [rsp+20h] [rbp-48h]
  wil::details *v9; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]

  if ( (int)a5 < 0 )
  {
    LODWORD(v9) = (_DWORD)a5;
    wil::details::ReportFailure_HrMsg<2>((int)this, (int)a2, a3, (int)a4, v8, retaddr, v9, a6, (__int64)&a7);
  }
  return (unsigned int)a5;
}

```

## disassembly

```asm
0x140008c88  mov     r11, rsp
0x140008c8b  push    rbx
0x140008c8c  sub     rsp, 60h
0x140008c90  mov     rax, r9
0x140008c93  mov     ebx, dword ptr [rsp+68h+arg_20]
0x140008c9a  test    ebx, ebx
0x140008c9c  jns     short loc_140008CD3
0x140008c9e  mov     qword ptr [r11-18h], 0
0x140008ca6  lea     r11, [r11+38h]
0x140008caa  mov     r10, [rsp+68h+arg_28]
0x140008cb2  mov     r9, [rsp+68h]
0x140008cb7  mov     [rsp+68h+var_28], r11; __int64
0x140008cbc  mov     [rsp+68h+var_30], r10; __int64
0x140008cc1  mov     dword ptr [rsp+68h+var_38], ebx; wil::details *
0x140008cc5  mov     [rsp+68h+var_40], r9; __int64
0x140008cca  mov     r9, rax; int
0x140008ccd  call    ??$ReportFailure_HrMsg@$01@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<2>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x140008cd2  nop
0x140008cd3  mov     eax, ebx
0x140008cd5  add     rsp, 60h
0x140008cd9  pop     rbx
0x140008cda  retn
```
