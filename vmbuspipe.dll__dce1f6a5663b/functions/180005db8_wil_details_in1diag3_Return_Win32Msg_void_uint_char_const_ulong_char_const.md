# wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)

- ea: `0x180005db8`
- end: `0x180005e0b`
- name: `?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ`
- size: `83`
- prototype: `__int64(wil::details::in1diag3 *__hidden this, void *, unsigned int, const char *, unsigned int, const char *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800012b0`
- `0x180001d30`
- `0x1800049fc`

## callees

- `0x1800024e0`
- `0x180003a14`

## pseudocode

```c
__int64 wil::details::in1diag3::Return_Win32Msg(
        wil::details::in1diag3 *this,
        void *a2,
        int a3,
        const char *a4,
        unsigned __int64 a5,
        const char *a6,
        ...)
{
  int v7; // [rsp+20h] [rbp-48h]
  wil::details *v8; // [rsp+30h] [rbp-38h]
  __int64 retaddr; // [rsp+68h] [rbp+0h]

  LODWORD(v8) = (_DWORD)a4;
  return wil::details::ReportFailure_Win32Msg<1>((int)this, (int)a2, a3, (int)a4, v7, retaddr, v8, a5, (char *)&a6);
}

```

## disassembly

```asm
0x180005db8  mov     r11, rsp
0x180005dbb  sub     rsp, 68h
0x180005dbf  mov     rax, cs:__security_cookie
0x180005dc6  xor     rax, rsp
0x180005dc9  mov     [rsp+68h+var_10], rax
0x180005dce  mov     qword ptr [r11-18h], 0
0x180005dd6  lea     rax, [r11+30h]
0x180005dda  mov     r10, [rsp+68h]
0x180005ddf  mov     [r11-28h], rax
0x180005de3  mov     rax, [r11+28h]
0x180005de7  mov     [r11-30h], rax
0x180005deb  mov     [r11-38h], r9d
0x180005def  mov     [r11-40h], r10
0x180005df3  call    ??$ReportFailure_Win32Msg@$00@details@wil@@YAJPEAXIPEBD110K1PEAD@Z; wil::details::ReportFailure_Win32Msg<1>(void *,uint,char const *,char const *,char const *,void *,ulong,char const *,char *)
0x180005df8  nop
0x180005df9  mov     rcx, [rsp+68h+var_10]
0x180005dfe  xor     rcx, rsp; StackCookie
0x180005e01  call    __security_check_cookie
0x180005e06  add     rsp, 68h
0x180005e0a  retn
```
