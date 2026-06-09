# TracePrintW(uchar,char const *,ulong,ushort const *,...)

- ea: `0x18000f4cc`
- end: `0x18000f58d`
- name: `?TracePrintW@@YAXEPEBDKPEBGZZ`
- size: `193`
- prototype: `void(PPTraceStatus *, MsaTracingInternal *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `13`
- callee_count: `7`
- tags: ``

## callers

- `0x180005d3c`
- `0x180007b00`
- `0x18000a3e8`
- `0x18000a998`
- `0x18000b4e8`
- `0x18000b5b4`
- `0x18000b820`
- `0x18000bbf8`
- `0x18000dc00`
- `0x18000de3c`
- `0x18000e1c0`
- `0x18000e500`
- `0x18000e8b8`

## callees

- `0x18000367c`
- `0x180006614`
- `0x180008d4c`
- `0x18000f030`
- `0x18000f230`
- `0x18000f4cc`
- `0x18000f658`

## pseudocode

```c
void TracePrintW(PPTraceStatus *a1, MsaTracingInternal *a2, unsigned int a3, const unsigned __int16 *a4, ...)
{
  char v6; // di
  __int64 v7; // r9
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rbx
  const char *v10; // rdx
  const char *BaseFileName; // rax
  __int64 v12; // rdx
  unsigned __int16 *v13; // [rsp+38h] [rbp-40h] BYREF
  int v14; // [rsp+40h] [rbp-38h]
  __int64 v15; // [rsp+48h] [rbp-30h]
  va_list va; // [rsp+A0h] [rbp+28h] BYREF

  va_start(va, a4);
  v6 = (char)a1;
  if ( PPTraceStatus::TraceOnFlag(a1, (unsigned __int8)a2) )
  {
    v13 = 0;
    v15 = 0;
    v14 = 0;
    if ( v7 )
    {
      AutoArray<unsigned short *,CPPArrayFunctor<unsigned short>,DummyContext>::Clear(&v13);
      v8 = (unsigned __int16 *)operator new[](0x800u, (const struct std::nothrow_t *)&std::nothrow);
      v13 = v8;
      v9 = v8;
      if ( v8 )
      {
        v14 = 1024;
        StringCchVPrintfW(v8, 0x400u, a4, va);
        if ( *v9 )
        {
          BaseFileName = MsaTracingInternal::GetBaseFileName(a2, v10);
          LOBYTE(v12) = v6;
          TraceStringW((unsigned int)dword_180020A0C, v12, BaseFileName, a3, v9);
        }
      }
    }
    AutoArray<unsigned short *,CPPArrayFunctor<unsigned short>,DummyContext>::Clear(&v13);
  }
}

```

## disassembly

```asm
0x18000f4cc  mov     [rsp+arg_18], r9
0x18000f4d1  push    rbx
0x18000f4d2  push    rbp
0x18000f4d3  push    rsi
0x18000f4d4  push    rdi
0x18000f4d5  push    r14
0x18000f4d7  sub     rsp, 50h
0x18000f4db  mov     esi, r8d
0x18000f4de  mov     rbp, rdx
0x18000f4e1  mov     dil, cl
0x18000f4e4  call    ?TraceOnFlag@PPTraceStatus@@YA_NE@Z; PPTraceStatus::TraceOnFlag(uchar)
0x18000f4e9  xor     r14d, r14d
0x18000f4ec  test    al, al
0x18000f4ee  jz      loc_18000F582
0x18000f4f4  mov     [rsp+78h+var_40], r14
0x18000f4f9  mov     [rsp+78h+var_30], r14
0x18000f4fe  mov     [rsp+78h+var_38], r14d
0x18000f503  test    r9, r9
0x18000f506  jz      short loc_18000F578
0x18000f508  lea     rcx, [rsp+78h+var_40]
0x18000f50d  call    ?Clear@?$AutoArray@PEAGU?$CPPArrayFunctor@G@@VDummyContext@@@@QEAAXXZ; AutoArray<ushort *,CPPArrayFunctor<ushort>,DummyContext>::Clear(void)
0x18000f512  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f519  mov     ecx, 800h; unsigned __int64
0x18000f51e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000f523  mov     [rsp+78h+var_40], rax
0x18000f528  mov     rbx, rax
0x18000f52b  test    rax, rax
0x18000f52e  jz      short loc_18000F578
0x18000f530  mov     edx, 400h; unsigned __int64
0x18000f535  mov     [rsp+78h+var_38], edx
0x18000f539  mov     r8, [rsp+78h+arg_18]; unsigned __int16 *
0x18000f541  lea     r9, [rsp+78h+arg_20]; char *
0x18000f549  mov     rcx, rax; unsigned __int16 *
0x18000f54c  call    ?StringCchVPrintfW@@YAJPEAG_KPEBGPEAD@Z; StringCchVPrintfW(ushort *,unsigned __int64,ushort const *,char *)
0x18000f551  cmp     [rbx], r14w
0x18000f555  jz      short loc_18000F578
0x18000f557  mov     rcx, rbp; this
0x18000f55a  call    ?GetBaseFileName@MsaTracingInternal@@YAPEBDPEBD@Z; MsaTracingInternal::GetBaseFileName(char const *)
0x18000f55f  mov     ecx, cs:dword_180020A0C
0x18000f565  mov     r9d, esi
0x18000f568  mov     r8, rax
0x18000f56b  mov     [rsp+78h+var_58], rbx
0x18000f570  mov     dl, dil
0x18000f573  call    ?TraceStringW@@YAXW4MSATRACE_MODULE@@EPEBDKPEBG@Z; TraceStringW(MSATRACE_MODULE,uchar,char const *,ulong,ushort const *)
0x18000f578  lea     rcx, [rsp+78h+var_40]
0x18000f57d  call    ?Clear@?$AutoArray@PEAGU?$CPPArrayFunctor@G@@VDummyContext@@@@QEAAXXZ; AutoArray<ushort *,CPPArrayFunctor<ushort>,DummyContext>::Clear(void)
0x18000f582  add     rsp, 50h
0x18000f586  pop     r14
0x18000f588  pop     rdi
0x18000f589  pop     rsi
0x18000f58a  pop     rbp
0x18000f58b  pop     rbx
0x18000f58c  retn
```
