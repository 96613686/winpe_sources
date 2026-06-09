# CSrmFunctionTracerBase::StaticTrace(CSrmDebugInfo,ulong,ushort const *,ushort const *,...)

- ea: `0x180018cbc`
- end: `0x180018e21`
- name: `?StaticTrace@CSrmFunctionTracerBase@@SAXUCSrmDebugInfo@@KPEBG1ZZ`
- size: `357`
- prototype: `void(CSrmDebugInfo *, int, __int64, wchar_t *, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180017e90`

## callees

- `0x1800019e4`
- `0x180001e44`
- `0x180016518`
- `0x180017e38`
- `0x180018cbc`
- `0x180018ea8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180018ded`
- `msvcrt!??3@YAXPEAX@Z` at `0x180018ded`
- `SrmTrace!__imp_SrmTraceMessage` at `0x180018de3`
- `SrmTrace!__imp_SrmTraceMessage` at `0x180018de3`
- `SrmTrace!__imp_SrmIsTracingEnabled` at `0x180018cde`
- `SrmTrace!__imp_SrmIsTracingEnabled` at `0x180018cde`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x180018cf8`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x180018cf8`

## pseudocode

```c
void CSrmFunctionTracerBase::StaticTrace(CSrmDebugInfo *a1, int a2, __int64 a3, wchar_t *a4, ...)
{
  unsigned int v7; // esi
  unsigned __int16 *v8; // rdi
  unsigned __int16 *v9; // rcx
  unsigned int v10; // [rsp+20h] [rbp-58h]
  unsigned __int64 pExceptionObject; // [rsp+50h] [rbp-28h] BYREF
  CSrmFunctionTracerBase *v12; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v13[3]; // [rsp+60h] [rbp-18h] BYREF
  va_list va; // [rsp+D0h] [rbp+58h] BYREF

  va_start(va, a4);
  if ( (unsigned int)SrmIsTracingEnabled() )
  {
    v12 = 0;
    if ( (int)SrmGetTracingContextPerThread(&v12) >= 0 )
    {
      v7 = 0;
      if ( v12 )
      {
        if ( !(unsigned int)CSrmFunctionTracerBase::IsTracingEnabled(v12, *((_DWORD *)a1 + 7)) )
          goto LABEL_11;
        v7 = *((_DWORD *)v12 + 14);
      }
      v8 = (unsigned __int16 *)operator new[](0x3EAu, (const struct std::nothrow_t *)&std::nothrow);
      v13[1] = v8;
      if ( !v8 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      pExceptionObject = 0;
      v13[0] = 0;
      StringCchVPrintfExW(v8, 0x1F4u, v13, &pExceptionObject, v10, a4, va);
      if ( pExceptionObject == 1 )
      {
        v9 = v13[0];
        if ( (__int64)(((char *)v13[0] - (char *)v8) & 0xFFFFFFFFFFFFFFFEuLL) > 6 )
        {
          *((_DWORD *)v13[0] - 1) = 3014702;
          *(v9 - 3) = 46;
        }
      }
      SrmTraceMessage(
        *(_QWORD *)a1,
        *((_QWORD *)a1 + 2),
        *((unsigned int *)a1 + 6),
        v7,
        *((_DWORD *)a1 + 7),
        a3,
        L"STATIC",
        a2,
        v8);
      operator delete(v8);
    }
  }
LABEL_11:
  CSrmDebugInfo::~CSrmDebugInfo(a1);
}

```

## disassembly

```asm
0x180018cbc  mov     [rsp-30h+arg_18], r9
0x180018cc1  mov     [rsp-30h+arg_0], rcx
0x180018cc6  push    rbp
0x180018cc7  push    rbx
0x180018cc8  push    rsi
0x180018cc9  push    rdi
0x180018cca  push    r14
0x180018ccc  push    r15
0x180018cce  mov     rbp, rsp
0x180018cd1  sub     rsp, 78h
0x180018cd5  mov     r14, r8
0x180018cd8  mov     r15d, edx
0x180018cdb  mov     rbx, rcx
0x180018cde  call    cs:__imp_SrmIsTracingEnabled
0x180018ce4  test    eax, eax
0x180018ce6  jz      loc_180018DF4
0x180018cec  mov     [rbp+var_20], 0
0x180018cf4  lea     rcx, [rbp+var_20]
0x180018cf8  call    cs:__imp_SrmGetTracingContextPerThread
0x180018cfe  test    eax, eax
0x180018d00  js      loc_180018DF4
0x180018d06  xor     esi, esi
0x180018d08  mov     rcx, [rbp+var_20]; this
0x180018d0c  test    rcx, rcx
0x180018d0f  jz      short loc_180018D28
0x180018d11  mov     edx, [rbx+1Ch]; unsigned int
0x180018d14  call    ?IsTracingEnabled@CSrmFunctionTracerBase@@QEAAHK@Z; CSrmFunctionTracerBase::IsTracingEnabled(ulong)
0x180018d19  test    eax, eax
0x180018d1b  jz      loc_180018DF4
0x180018d21  mov     rax, [rbp+var_20]
0x180018d25  mov     esi, [rax+38h]
0x180018d28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018d2f  mov     ecx, 3EAh; unsigned __int64
0x180018d34  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180018d39  mov     rdi, rax
0x180018d3c  mov     [rbp+var_10], rax
0x180018d40  test    rax, rax
0x180018d43  jz      loc_180018E09
0x180018d49  mov     [rbp+var_18], 0
0x180018d51  lea     rax, [rbp+arg_20]
0x180018d55  mov     [rbp+pExceptionObject], 0
0x180018d5d  mov     [rbp+var_18], 0
0x180018d65  mov     [rsp+78h+Args], rax; Args
0x180018d6a  mov     rax, [rbp+arg_18]
0x180018d6e  mov     [rsp+78h+Format], rax; Format
0x180018d73  lea     r9, [rbp+pExceptionObject]; unsigned __int64 *
0x180018d77  lea     r8, [rbp+var_18]; unsigned __int16 **
0x180018d7b  mov     edx, 1F4h; unsigned __int64
0x180018d80  mov     rcx, rdi; unsigned __int16 *
0x180018d83  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180018d88  cmp     [rbp+pExceptionObject], 1
0x180018d8d  jnz     short loc_180018DB3
0x180018d8f  mov     rcx, [rbp+var_18]
0x180018d93  mov     rax, rcx
0x180018d96  sub     rax, rdi
0x180018d99  and     rax, 0FFFFFFFFFFFFFFFEh
0x180018d9d  cmp     rax, 6
0x180018da1  jle     short loc_180018DB3
0x180018da3  mov     eax, 2Eh ; '.'
0x180018da8  mov     dword ptr [rcx-4], 2E002Eh
0x180018daf  mov     [rcx-6], ax
0x180018db3  mov     [rsp+78h+var_38], rdi
0x180018db8  mov     [rsp+78h+var_40], r15d
0x180018dbd  lea     rax, aStatic; "STATIC"
0x180018dc4  mov     [rsp+78h+Args], rax
0x180018dc9  mov     [rsp+78h+Format], r14
0x180018dce  mov     eax, [rbx+1Ch]
0x180018dd1  mov     [rsp+78h+var_58], eax
0x180018dd5  mov     r9d, esi
0x180018dd8  mov     r8d, [rbx+18h]
0x180018ddc  mov     rdx, [rbx+10h]
0x180018de0  mov     rcx, [rbx]
0x180018de3  call    cs:__imp_SrmTraceMessage
0x180018de9  nop
0x180018dea  mov     rcx, rdi
0x180018ded  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180018df3  nop
0x180018df4  mov     rcx, rbx; this
0x180018df7  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180018dfc  add     rsp, 78h
0x180018e00  pop     r15
0x180018e02  pop     r14
0x180018e04  pop     rdi
0x180018e05  pop     rsi
0x180018e06  pop     rbx
0x180018e07  pop     rbp
0x180018e08  retn
0x180018e09  mov     dword ptr [rbp+pExceptionObject], 8007000Eh
0x180018e10  lea     rdx, _TI1J; pThrowInfo
0x180018e17  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x180018e1b  call    _CxxThrowException_0
```
