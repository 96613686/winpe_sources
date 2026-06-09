# PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x180012e5c`
- end: `0x180012efe`
- name: `?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ`
- size: `162`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180003900`
- `0x180003950`
- `0x180012c70`
- `0x180012cd0`

## callees

- `0x180005320`
- `0x18000ae94`
- `0x180012808`
- `0x18001285c`
- `0x180012e5c`
- `0x180012fc4`
- `0x180014fd0`

## pseudocode

```c
void PerfLibTelemetry::WriteDbgTraceInfo(char *a1, unsigned __int16 *a2, ...)
{
  unsigned __int64 v3; // rdx
  unsigned __int8 v4; // cl
  __int64 v5; // rcx
  PerfLibTelemetry *v6; // rcx
  unsigned __int16 v7[4096]; // [rsp+30h] [rbp-2018h] BYREF
  va_list va; // [rsp+2060h] [rbp+18h] BYREF

  va_start(va, a2);
  if ( PerfLibTelemetry::IsEnabled((unsigned __int8)a1, (unsigned __int64)a2)
    && (int)StringCchVPrintfW(v7, 0x1000u, a2, va) >= 0
    && PerfLibTelemetry::IsEnabled(v4, v3) )
  {
    wil::details::static_lazy<PerfLibTelemetry>::get(
      v5,
      _lambda_afb3aedd42a937a6b0239593c828df1f_::_lambda_invoker_cdecl_);
    PerfLibTelemetry::LogDbgTraceInfo_(v6, a1, v7);
  }
}

```

## disassembly

```asm
0x180012e5c  mov     [rsp+arg_8], rdx
0x180012e61  mov     qword ptr [rsp+arg_10], r8
0x180012e66  mov     [rsp+arg_18], r9
0x180012e6b  push    rbx
0x180012e6c  mov     eax, 2040h
0x180012e71  call    _alloca_probe
0x180012e76  sub     rsp, rax
0x180012e79  mov     rax, cs:__security_cookie
0x180012e80  xor     rax, rsp
0x180012e83  mov     [rsp+2048h+var_18], rax
0x180012e8b  mov     rbx, rcx
0x180012e8e  call    ?IsEnabled@PerfLibTelemetry@@SA_NE_K@Z; PerfLibTelemetry::IsEnabled(uchar,unsigned __int64)
0x180012e93  test    al, al
0x180012e95  jz      short loc_180012EE5
0x180012e97  mov     r8, [rsp+2048h+arg_8]; unsigned __int16 *
0x180012e9f  lea     r9, [rsp+2048h+arg_10]; char *
0x180012ea7  mov     edx, 1000h; unsigned __int64
0x180012eac  mov     [rsp+2048h+var_2028], 0
0x180012eb5  lea     rcx, [rsp+2048h+var_2018]; unsigned __int16 *
0x180012eba  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180012ebf  test    eax, eax
0x180012ec1  js      short loc_180012EE5
0x180012ec3  call    ?IsEnabled@PerfLibTelemetry@@SA_NE_K@Z; PerfLibTelemetry::IsEnabled(uchar,unsigned __int64)
0x180012ec8  test    al, al
0x180012eca  jz      short loc_180012EE5
0x180012ecc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_afb3aedd42a937a6b0239593c828df1f_@@CA@XZ; _lambda_afb3aedd42a937a6b0239593c828df1f_::_lambda_invoker_cdecl_(void)
0x180012ed3  call    ?get@?$static_lazy@VPerfLibTelemetry@@@details@wil@@QEAAPEAVPerfLibTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PerfLibTelemetry>::get(void (*)(void))
0x180012ed8  lea     r8, [rsp+2048h+var_2018]; unsigned __int16 *
0x180012edd  mov     rdx, rbx; char *
0x180012ee0  call    ?LogDbgTraceInfo_@PerfLibTelemetry@@QEAAXPEBDPEBG@Z; PerfLibTelemetry::LogDbgTraceInfo_(char const *,ushort const *)
0x180012ee5  mov     rcx, [rsp+2048h+var_18]
0x180012eed  xor     rcx, rsp; StackCookie
0x180012ef0  call    __security_check_cookie
0x180012ef5  add     rsp, 2040h
0x180012efc  pop     rbx
0x180012efd  retn
```
