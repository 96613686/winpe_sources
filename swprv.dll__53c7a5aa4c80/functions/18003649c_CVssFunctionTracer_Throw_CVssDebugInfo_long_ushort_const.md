# CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)

- ea: `0x18003649c`
- end: `0x18003660c`
- name: `?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ`
- size: `368`
- prototype: `void __noreturn(_QWORD, _QWORD, _QWORD, _QWORD, ...)`
- caller_count: `113`
- callee_count: `10`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180002af0`
- `0x180002cfc`
- `0x180002f1c`
- `0x18000313c`
- `0x180003be0`
- `0x180003de8`
- `0x180004c74`
- `0x180004fbc`
- `0x180005450`
- `0x180005f18`
- `0x18000610c`
- `0x1800066fc`
- `0x180006cb0`
- `0x180007824`
- `0x180007b80`
- `0x18000aa5c`
- `0x18000d6bc`
- `0x18000de70`
- `0x18000e900`
- `0x18000f910`
- `0x18000ffe0`
- `0x180010a20`
- `0x180011178`
- `0x1800122a0`
- `0x180012740`
- `0x180012bd0`
- `0x180012e50`
- `0x180013080`
- `0x1800138c0`
- `0x180013de0`
- `0x1800144a0`
- `0x180014a00`
- `0x180015890`
- `0x180015ff0`
- `0x180016550`
- `0x180016ff0`
- `0x1800171dc`
- `0x180017284`
- `0x180017410`
- `0x180017b30`
- `0x18001822c`
- `0x180018334`
- `0x18001843c`
- `0x180018bf8`
- `0x18001a0d0`
- `0x18001ae14`
- `0x18001c294`
- `0x18001c5dc`
- `0x18001d23c`
- `0x18001d988`

## callees

- `0x180001674`
- `0x180001af0`
- `0x180002138`
- `0x1800339c0`
- `0x180034e64`
- `0x180034f3c`
- `0x1800356ec`
- `0x1800363e0`
- `0x18003649c`
- `0x1800369ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800365dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __noreturn CVssFunctionTracer::Throw(
        CVssFunctionTracer *a1,
        const struct CVssDebugInfo *a2,
        int a3,
        wchar_t *a4,
        ...)
{
  unsigned __int16 *v7; // rbx
  _WORD *v8; // rax
  CVssDebugInfo *v9; // rax
  const unsigned __int16 *CurrentContexts; // rax
  void *v11; // rdi
  CVssDebugInfo *v12; // rax
  unsigned int v13; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 pExceptionObject[3]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[224]; // [rsp+60h] [rbp-A0h] BYREF
  va_list va; // [rsp+170h] [rbp+70h] BYREF

  va_start(va, a4);
  if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled(a1) && a4 )
  {
    v7 = (unsigned __int16 *)operator new[](0x3EAu, (const struct std::nothrow_t *)&std::nothrow);
    pExceptionObject[2] = (unsigned __int64)v7;
    if ( v7 )
    {
      pExceptionObject[0] = 0;
      pv = 0;
      StringCchVPrintfExW(v7, 0x1F4u, (unsigned __int16 **)&pv, pExceptionObject, v13, a4, va);
      if ( pExceptionObject[0] == 1 )
      {
        v8 = pv;
        *((_DWORD *)pv - 1) = 3014702;
        *(v8 - 3) = 46;
      }
      v9 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v16, a2);
      CVssFunctionTracer::TraceInternal(a1, v9, L"THROW");
    }
    pv = 0;
    CurrentContexts = CVssFunctionTracer::GetCurrentContexts(a1);
    CVssAutoCoString::CopyFrom(&pv, CurrentContexts);
    v11 = pv;
    v12 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v16, a2);
    CVssFunctionTracer::TraceInternal(a1, v12, L"THROW");
    CoTaskMemFree(v11);
    operator delete(v7);
  }
  *((_DWORD *)a1 + 2) = a3;
  LODWORD(pExceptionObject[0]) = a3;
  throw (long *)pExceptionObject;
}

```

## disassembly

```asm
0x18003649c  mov     [rsp-8+arg_18], r9
0x1800364a1  mov     [rsp-8+arg_8], rdx
0x1800364a6  push    rbp
0x1800364a7  push    rbx
0x1800364a8  push    rsi
0x1800364a9  push    rdi
0x1800364aa  push    r14
0x1800364ac  push    r15
0x1800364ae  lea     rbp, [rsp-18h]
0x1800364b3  sub     rsp, 118h
0x1800364ba  mov     r15d, r8d
0x1800364bd  mov     r14, rdx
0x1800364c0  mov     rsi, rcx
0x1800364c3  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x1800364c8  xor     edi, edi
0x1800364ca  test    eax, eax
0x1800364cc  jz      loc_1800365F1
0x1800364d2  cmp     [rbp+40h+arg_18], rdi
0x1800364d6  jz      loc_1800365F1
0x1800364dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800364e3  mov     ecx, 3EAh; unsigned __int64
0x1800364e8  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800364ed  mov     rbx, rax
0x1800364f0  mov     [rsp+140h+var_E8], rax
0x1800364f5  test    rax, rax
0x1800364f8  jz      loc_180036583
0x1800364fe  mov     [rsp+140h+pExceptionObject], rdi
0x180036503  mov     [rsp+140h+pv], rdi
0x180036508  lea     rax, [rbp+40h+arg_20]
0x18003650c  mov     [rsp+140h+Args], rax; Args
0x180036511  mov     rax, [rbp+40h+arg_18]
0x180036515  mov     [rsp+140h+Format], rax; Format
0x18003651a  lea     r9, [rsp+140h+pExceptionObject]; unsigned __int64 *
0x18003651f  lea     r8, [rsp+140h+pv]; unsigned __int16 **
0x180036524  mov     edx, 1F4h; unsigned __int64
0x180036529  mov     rcx, rbx; unsigned __int16 *
0x18003652c  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x180036531  cmp     [rsp+140h+pExceptionObject], 1
0x180036537  jnz     short loc_18003654C
0x180036539  lea     ecx, [rdi+2Eh]
0x18003653c  mov     rax, [rsp+140h+pv]
0x180036541  mov     dword ptr [rax-4], 2E002Eh
0x180036548  mov     [rax-6], cx
0x18003654c  mov     r9d, 50h ; 'P'
0x180036552  cmp     dword ptr [r14+20h], 0FFh
0x18003655a  cmovnz  r9d, [r14+20h]
0x18003655f  mov     rdx, r14; struct CVssDebugInfo *
0x180036562  lea     rcx, [rsp+140h+var_E0]; this
0x180036567  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x18003656c  mov     [rsp+140h+var_120], rbx
0x180036571  lea     r8, aThrow; "THROW"
0x180036578  mov     rdx, rax
0x18003657b  mov     rcx, rsi
0x18003657e  call    ?TraceInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1@Z; CVssFunctionTracer::TraceInternal(CVssDebugInfo,ushort const *,ulong,ushort const *)
0x180036583  mov     [rsp+140h+pv], rdi
0x180036588  mov     rcx, rsi; this
0x18003658b  call    ?GetCurrentContexts@CVssFunctionTracer@@QEAAPEAGXZ; CVssFunctionTracer::GetCurrentContexts(void)
0x180036590  mov     rdx, rax; unsigned __int16 *
0x180036593  lea     rcx, [rsp+140h+pv]; this
0x180036598  call    ?CopyFrom@CVssAutoCoString@@QEAA_NPEBG@Z; CVssAutoCoString::CopyFrom(ushort const *)
0x18003659d  mov     rdi, [rsp+140h+pv]
0x1800365a2  mov     r9d, 0C8h
0x1800365a8  cmp     dword ptr [r14+20h], 0FFh
0x1800365b0  cmovnz  r9d, [r14+20h]
0x1800365b5  mov     rdx, r14; struct CVssDebugInfo *
0x1800365b8  lea     rcx, [rsp+140h+var_E0]; this
0x1800365bd  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x1800365c2  mov     [rsp+140h+var_120], rdi
0x1800365c7  lea     r8, aThrow; "THROW"
0x1800365ce  mov     rdx, rax
0x1800365d1  mov     rcx, rsi
0x1800365d4  call    ?TraceInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1@Z; CVssFunctionTracer::TraceInternal(CVssDebugInfo,ushort const *,ulong,ushort const *)
0x1800365d9  nop
0x1800365da  mov     rcx, rdi; pv
0x1800365dd  call    cs:__imp_CoTaskMemFree
0x1800365e3  nop
0x1800365e4  mov     edx, 2
0x1800365e9  mov     rcx, rbx; Block
0x1800365ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800365f1  mov     [rsi+8], r15d
0x1800365f5  mov     dword ptr [rsp+140h+pExceptionObject], r15d
0x1800365fa  lea     rdx, _TI1J; pThrowInfo
0x180036601  lea     rcx, [rsp+140h+pExceptionObject]; pExceptionObject
0x180036606  call    _CxxThrowException_0
```
