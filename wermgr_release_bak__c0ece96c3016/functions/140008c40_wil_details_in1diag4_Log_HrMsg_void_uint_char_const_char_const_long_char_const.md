# wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)

- ea: `0x140008c40`
- end: `0x140008c81`
- name: `?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ`
- size: `65`
- prototype: `__int64(wil::details::in1diag4 *__hidden this, void *, unsigned int, const char *, wil::details *, int, const char *, ...)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140004e18`
- `0x1400058ec`
- `0x140005cec`
- `0x140005e30`
- `0x140005f98`
- `0x14000659c`
- `0x1400071d4`
- `0x140007234`
- `0x140007554`
- `0x140007cf0`
- `0x14000964c`
- `0x14000a1ac`
- `0x14000e49c`

## callees

- `0x140003c74`

## pseudocode

```c
__int64 wil::details::in1diag4::Log_HrMsg(
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

  LODWORD(v9) = (_DWORD)a5;
  wil::details::ReportFailure_HrMsg<2>((int)this, (int)a2, a3, (int)a4, v8, retaddr, v9, a6, (__int64)&a7);
  return (unsigned int)a5;
}

```

## disassembly

```asm
0x140008c40  mov     r11, rsp
0x140008c43  push    rbx
0x140008c44  sub     rsp, 60h
0x140008c48  mov     qword ptr [r11-18h], 0
0x140008c50  lea     rax, [r11+38h]
0x140008c54  mov     r10, [rsp+68h]
0x140008c59  mov     [r11-28h], rax
0x140008c5d  mov     rax, [r11+30h]
0x140008c61  mov     [r11-30h], rax
0x140008c65  mov     ebx, dword ptr [rsp+68h+arg_20]
0x140008c6c  mov     dword ptr [rsp+68h+var_38], ebx; wil::details *
0x140008c70  mov     [r11-40h], r10
0x140008c74  call    ??$ReportFailure_HrMsg@$01@details@wil@@YAXPEAXIPEBD110J1PEAD@Z; wil::details::ReportFailure_HrMsg<2>(void *,uint,char const *,char const *,char const *,void *,long,char const *,char *)
0x140008c79  mov     eax, ebx
0x140008c7b  add     rsp, 60h
0x140008c7f  pop     rbx
0x140008c80  retn
```
