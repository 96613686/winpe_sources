# PerfLibTelemetry::WriteDbgTraceInfo(char *,ushort *,...)

- ea: `0x1800145b0`
- end: `0x180014653`
- name: `?WriteDbgTraceInfo@PerfLibTelemetry@@SAXPEADPEAGZZ`
- size: `163`
- prototype: `void(char *, unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `7`
- tags: ``

## callers

- `0x180003bf8`
- `0x180003c4c`
- `0x1800143b0`
- `0x180014414`

## callees

- `0x180005680`
- `0x18000b794`
- `0x180013f48`
- `0x180013f9c`
- `0x1800145b0`
- `0x180014724`
- `0x1800169d0`

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
0x1800145b0  mov     [rsp+arg_8], rdx
0x1800145b5  mov     qword ptr [rsp+arg_10], r8
0x1800145ba  mov     [rsp+arg_18], r9
0x1800145bf  push    rbx
0x1800145c0  mov     eax, 2040h
0x1800145c5  call    _alloca_probe
0x1800145ca  sub     rsp, rax
0x1800145cd  mov     rax, cs:__security_cookie
0x1800145d4  xor     rax, rsp
0x1800145d7  mov     [rsp+2048h+var_18], rax
0x1800145df  mov     rbx, rcx
0x1800145e2  call    ?IsEnabled@PerfLibTelemetry@@SA_NE_K@Z; PerfLibTelemetry::IsEnabled(uchar,unsigned __int64)
0x1800145e7  test    al, al
0x1800145e9  jz      short loc_180014639
0x1800145eb  mov     r8, [rsp+2048h+arg_8]; unsigned __int16 *
0x1800145f3  lea     r9, [rsp+2048h+arg_10]; char *
0x1800145fb  mov     edx, 1000h; unsigned __int64
0x180014600  mov     [rsp+2048h+var_2028], 0
0x180014609  lea     rcx, [rsp+2048h+var_2018]; unsigned __int16 *
0x18001460e  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x180014613  test    eax, eax
0x180014615  js      short loc_180014639
0x180014617  call    ?IsEnabled@PerfLibTelemetry@@SA_NE_K@Z; PerfLibTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001461c  test    al, al
0x18001461e  jz      short loc_180014639
0x180014620  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_afb3aedd42a937a6b0239593c828df1f_@@CA@XZ; _lambda_afb3aedd42a937a6b0239593c828df1f_::_lambda_invoker_cdecl_(void)
0x180014627  call    ?get@?$static_lazy@VPerfLibTelemetry@@@details@wil@@QEAAPEAVPerfLibTelemetry@@P6AXXZ@Z; wil::details::static_lazy<PerfLibTelemetry>::get(void (*)(void))
0x18001462c  lea     r8, [rsp+2048h+var_2018]; unsigned __int16 *
0x180014631  mov     rdx, rbx; char *
0x180014634  call    ?LogDbgTraceInfo_@PerfLibTelemetry@@QEAAXPEBDPEBG@Z; PerfLibTelemetry::LogDbgTraceInfo_(char const *,ushort const *)
0x180014639  mov     rcx, [rsp+2048h+var_18]
0x180014641  xor     rcx, rsp; StackCookie
0x180014644  call    __security_check_cookie
0x180014649  add     rsp, 2040h
0x180014650  pop     rbx
0x180014651  retn
```
