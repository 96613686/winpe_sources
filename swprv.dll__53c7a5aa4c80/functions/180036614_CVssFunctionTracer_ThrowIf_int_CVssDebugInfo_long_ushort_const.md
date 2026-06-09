# CVssFunctionTracer::ThrowIf(int,CVssDebugInfo,long,ushort * const,...)

- ea: `0x180036614`
- end: `0x1800367b2`
- name: `?ThrowIf@CVssFunctionTracer@@QEAAXHUCVssDebugInfo@@JQEAGZZ`
- size: `414`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800057c0`
- `0x180007a54`
- `0x18000c770`

## callees

- `0x180001674`
- `0x180001af0`
- `0x1800339c0`
- `0x180033c2c`
- `0x180034e64`
- `0x180034f3c`
- `0x1800356ec`
- `0x1800363e0`
- `0x18003649c`
- `0x180036614`
- `0x1800369ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036772`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180036772`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void CVssFunctionTracer::ThrowIf(
        CVssFunctionTracer *a1,
        int a2,
        const struct CVssDebugInfo *a3,
        int a4,
        wchar_t *Format,
        ...)
{
  unsigned __int16 *v8; // rbx
  _WORD *v9; // rax
  CVssDebugInfo *v10; // rax
  const unsigned __int16 *CurrentContexts; // rax
  void *v12; // rdi
  CVssDebugInfo *v13; // rax
  const struct CVssDebugInfo *v14; // rax
  __int64 v15; // [rsp+20h] [rbp-E0h]
  LPVOID pv[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int64 v17[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[224]; // [rsp+60h] [rbp-A0h] BYREF
  va_list va; // [rsp+178h] [rbp+78h] BYREF

  va_start(va, Format);
  if ( a2 )
  {
    if ( (unsigned int)CVssFunctionTracer::IsTracingEnabled(a1) && Format )
    {
      v8 = (unsigned __int16 *)operator new[](0x3EAu, (const struct std::nothrow_t *)&std::nothrow);
      v17[1] = (unsigned __int64)v8;
      if ( v8 )
      {
        v17[0] = 0;
        pv[0] = 0;
        StringCchVPrintfExW(v8, 0x1F4u, (unsigned __int16 **)pv, v17, v15, Format, va);
        if ( v17[0] == 1 )
        {
          v9 = pv[0];
          *((_DWORD *)pv[0] - 1) = 3014702;
          *(v9 - 3) = 46;
        }
        v10 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v18, a3);
        CVssFunctionTracer::TraceInternal(a1, v10, L"THROW");
      }
      pv[0] = 0;
      CurrentContexts = CVssFunctionTracer::GetCurrentContexts(a1);
      CVssAutoCoString::CopyFrom(pv, CurrentContexts);
      v12 = pv[0];
      v13 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v18, a3);
      HIDWORD(v15) = HIDWORD(v12);
      CVssFunctionTracer::TraceInternal(a1, v13, L"THROW");
      CoTaskMemFree(v12);
      operator delete(v8);
    }
    *((_DWORD *)a1 + 2) = a4;
    v14 = CVssDebugInfo::CVssDebugInfo((CVssDebugInfo *)v18, a3);
    LODWORD(v15) = a4;
    CVssFunctionTracer::Throw(a1, v14, a4, L"re-throwing %#x", v15);
  }
  *((_DWORD *)a1 + 2) = 0;
  CVssDebugInfo::~CVssDebugInfo(a3);
}

```

## disassembly

```asm
0x180036614  mov     [rsp-8+arg_10], r8
0x180036619  push    rbp
0x18003661a  push    rbx
0x18003661b  push    rsi
0x18003661c  push    rdi
0x18003661d  push    r14
0x18003661f  push    r15
0x180036621  lea     rbp, [rsp-18h]
0x180036626  sub     rsp, 118h
0x18003662d  mov     r15d, r9d
0x180036630  mov     r14, r8
0x180036633  mov     rsi, rcx
0x180036636  xor     edi, edi
0x180036638  test    edx, edx
0x18003663a  jnz     short loc_180036657
0x18003663c  mov     [rcx+8], edi
0x18003663f  mov     rcx, r8; this
0x180036642  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180036647  add     rsp, 118h
0x18003664e  pop     r15
0x180036650  pop     r14
0x180036652  pop     rdi
0x180036653  pop     rsi
0x180036654  pop     rbx
0x180036655  pop     rbp
0x180036656  retn
0x180036657  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHXZ; CVssFunctionTracer::IsTracingEnabled(void)
0x18003665c  nop
0x18003665d  test    eax, eax
0x18003665f  jz      loc_180036786
0x180036665  cmp     [rbp+40h+arg_20], rdi
0x180036669  jz      loc_180036786
0x18003666f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036676  mov     ecx, 3EAh; unsigned __int64
0x18003667b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180036680  mov     rbx, rax
0x180036683  mov     [rsp+140h+var_E8], rax
0x180036688  test    rax, rax
0x18003668b  jz      loc_180036718
0x180036691  mov     [rsp+140h+var_F0], rdi
0x180036696  mov     [rsp+140h+pv], rdi
0x18003669b  lea     rax, [rbp+40h+arg_28]
0x18003669f  mov     [rsp+140h+Args], rax; Args
0x1800366a4  mov     rax, [rbp+40h+arg_20]
0x1800366a8  mov     [rsp+140h+Format], rax; Format
0x1800366ad  lea     r9, [rsp+140h+var_F0]; unsigned __int64 *
0x1800366b2  lea     r8, [rsp+140h+pv]; unsigned __int16 **
0x1800366b7  mov     edx, 1F4h; unsigned __int64
0x1800366bc  mov     rcx, rbx; unsigned __int16 *
0x1800366bf  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x1800366c4  cmp     [rsp+140h+var_F0], 1
0x1800366ca  jnz     short loc_1800366E1
0x1800366cc  mov     ecx, 2Eh ; '.'
0x1800366d1  mov     rax, [rsp+140h+pv]
0x1800366d6  mov     dword ptr [rax-4], 2E002Eh
0x1800366dd  mov     [rax-6], cx
0x1800366e1  mov     r9d, 50h ; 'P'
0x1800366e7  cmp     dword ptr [r14+20h], 0FFh
0x1800366ef  cmovnz  r9d, [r14+20h]
0x1800366f4  mov     rdx, r14; struct CVssDebugInfo *
0x1800366f7  lea     rcx, [rsp+140h+var_E0]; this
0x1800366fc  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180036701  mov     [rsp+140h+var_120], rbx
0x180036706  lea     r8, aThrow; "THROW"
0x18003670d  mov     rdx, rax
0x180036710  mov     rcx, rsi
0x180036713  call    ?TraceInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1@Z; CVssFunctionTracer::TraceInternal(CVssDebugInfo,ushort const *,ulong,ushort const *)
0x180036718  mov     [rsp+140h+pv], rdi
0x18003671d  mov     rcx, rsi; this
0x180036720  call    ?GetCurrentContexts@CVssFunctionTracer@@QEAAPEAGXZ; CVssFunctionTracer::GetCurrentContexts(void)
0x180036725  mov     rdx, rax; unsigned __int16 *
0x180036728  lea     rcx, [rsp+140h+pv]; this
0x18003672d  call    ?CopyFrom@CVssAutoCoString@@QEAA_NPEBG@Z; CVssAutoCoString::CopyFrom(ushort const *)
0x180036732  mov     rdi, [rsp+140h+pv]
0x180036737  mov     r9d, 0C8h
0x18003673d  cmp     dword ptr [r14+20h], 0FFh
0x180036745  cmovnz  r9d, [r14+20h]
0x18003674a  mov     rdx, r14; struct CVssDebugInfo *
0x18003674d  lea     rcx, [rsp+140h+var_E0]; this
0x180036752  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180036757  mov     [rsp+140h+var_120], rdi
0x18003675c  lea     r8, aThrow; "THROW"
0x180036763  mov     rdx, rax
0x180036766  mov     rcx, rsi
0x180036769  call    ?TraceInternal@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@PEBGK1@Z; CVssFunctionTracer::TraceInternal(CVssDebugInfo,ushort const *,ulong,ushort const *)
0x18003676e  nop
0x18003676f  mov     rcx, rdi; pv
0x180036772  call    cs:__imp_CoTaskMemFree
0x180036778  nop
0x180036779  mov     edx, 2
0x18003677e  mov     rcx, rbx; Block
0x180036781  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036786  mov     [rsi+8], r15d
0x18003678a  mov     rdx, r14; struct CVssDebugInfo *
0x18003678d  lea     rcx, [rsp+140h+var_E0]; this
0x180036792  call    ??0CVssDebugInfo@@QEAA@AEBU0@@Z; CVssDebugInfo::CVssDebugInfo(CVssDebugInfo const &)
0x180036797  mov     dword ptr [rsp+140h+var_120], r15d
0x18003679c  lea     r9, aReThrowingX; "re-throwing %#x"
0x1800367a3  mov     r8d, r15d
0x1800367a6  mov     rdx, rax
0x1800367a9  mov     rcx, rsi
0x1800367ac  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
```
