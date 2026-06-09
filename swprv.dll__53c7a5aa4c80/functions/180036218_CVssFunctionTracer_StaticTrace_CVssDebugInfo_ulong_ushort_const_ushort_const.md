# CVssFunctionTracer::StaticTrace(CVssDebugInfo,ulong,ushort const *,ushort const *,...)

- ea: `0x180036218`
- end: `0x180036358`
- name: `?StaticTrace@CVssFunctionTracer@@SAXUCVssDebugInfo@@KPEBG1ZZ`
- size: `320`
- prototype: `__int64(_QWORD, _QWORD, _QWORD, _QWORD, ...)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800356fc`

## callees

- `0x180001674`
- `0x180001af0`
- `0x180033c2c`
- `0x1800356a8`
- `0x180036218`
- `0x1800363e0`

## import_xrefs

- `VssTrace!__imp_VssTraceMessage` at `0x180036330`
- `VssTrace!__imp_VssTraceMessage` at `0x180036330`
- `VssTrace!__imp_VssIsTracingEnabled` at `0x180036235`
- `VssTrace!__imp_VssIsTracingEnabled` at `0x180036235`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x18003624f`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x18003624f`

## pseudocode

```c
void CVssFunctionTracer::StaticTrace(CVssDebugInfo *a1, int a2, __int64 a3, wchar_t *a4, ...)
{
  unsigned int v7; // esi
  unsigned __int16 *v8; // rbx
  unsigned __int16 *v9; // rax
  unsigned int v10; // [rsp+20h] [rbp-58h]
  CVssFunctionTracer *v11; // [rsp+50h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+58h] [rbp-20h] BYREF
  unsigned __int16 *v13[3]; // [rsp+60h] [rbp-18h] BYREF
  va_list va; // [rsp+D0h] [rbp+58h] BYREF

  va_start(va, a4);
  if ( (unsigned int)VssIsTracingEnabled() )
  {
    v11 = 0;
    if ( (int)VssGetTracingContextPerThread(&v11) >= 0 )
    {
      v7 = 0;
      if ( v11 )
      {
        if ( !(unsigned int)CVssFunctionTracer::IsTracingEnabled(v11, *((_DWORD *)a1 + 7)) )
          goto LABEL_12;
        v7 = *((_DWORD *)v11 + 12);
      }
      v8 = (unsigned __int16 *)operator new[](0x3EAu, (const struct std::nothrow_t *)&std::nothrow);
      if ( v8 )
      {
        v12 = 0;
        v13[0] = 0;
        v13[1] = 0;
        StringCchVPrintfExW(v8, 0x1F4u, v13, &v12, v10, a4, va);
        if ( v12 == 1 )
        {
          v9 = v13[0];
          *((_DWORD *)v13[0] - 1) = 3014702;
          *(v9 - 3) = 46;
        }
        VssTraceMessage(
          *(_QWORD *)a1,
          *((_QWORD *)a1 + 2),
          *((unsigned int *)a1 + 6),
          v7,
          *((_DWORD *)a1 + 7),
          a3,
          L"STATIC",
          a2,
          v8);
      }
      else
      {
        VssTraceMessage(
          *(_QWORD *)a1,
          *((_QWORD *)a1 + 2),
          *((unsigned int *)a1 + 6),
          v7,
          *((_DWORD *)a1 + 7),
          a3,
          L"STATIC",
          a2,
          L"StaticTrace failed due to out of memory condition");
      }
      operator delete(v8);
    }
  }
LABEL_12:
  CVssDebugInfo::~CVssDebugInfo(a1);
}

```

## disassembly

```asm
0x180036218  mov     [rsp-30h+arg_18], r9
0x18003621d  push    rbp
0x18003621e  push    rbx
0x18003621f  push    rsi
0x180036220  push    rdi
0x180036221  push    r14
0x180036223  push    r15
0x180036225  mov     rbp, rsp
0x180036228  sub     rsp, 78h
0x18003622c  mov     r14, r8
0x18003622f  mov     r15d, edx
0x180036232  mov     rdi, rcx
0x180036235  call    cs:__imp_VssIsTracingEnabled
0x18003623b  test    eax, eax
0x18003623d  jz      loc_180036343
0x180036243  lea     rcx, [rbp+var_28]
0x180036247  mov     [rbp+var_28], 0
0x18003624f  call    cs:__imp_VssGetTracingContextPerThread
0x180036255  test    eax, eax
0x180036257  js      loc_180036343
0x18003625d  mov     rcx, [rbp+var_28]; this
0x180036261  xor     esi, esi
0x180036263  test    rcx, rcx
0x180036266  jz      short loc_18003627F
0x180036268  mov     edx, [rdi+1Ch]; unsigned int
0x18003626b  call    ?IsTracingEnabled@CVssFunctionTracer@@QEAAHK@Z; CVssFunctionTracer::IsTracingEnabled(ulong)
0x180036270  test    eax, eax
0x180036272  jz      loc_180036343
0x180036278  mov     rax, [rbp+var_28]
0x18003627c  mov     esi, [rax+30h]
0x18003627f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180036286  mov     ecx, 3EAh; unsigned __int64
0x18003628b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180036290  mov     rbx, rax
0x180036293  test    rax, rax
0x180036296  jnz     short loc_1800362A6
0x180036298  lea     rax, aStatictraceFai; "StaticTrace failed due to out of memory"...
0x18003629f  mov     [rsp+78h+var_38], rax
0x1800362a4  jmp     short loc_180036305
0x1800362a6  lea     rax, [rbp+arg_20]
0x1800362aa  mov     [rbp+var_20], 0
0x1800362b2  mov     [rsp+78h+Args], rax; Args
0x1800362b7  lea     r9, [rbp+var_20]; unsigned __int64 *
0x1800362bb  mov     rax, [rbp+arg_18]
0x1800362bf  lea     r8, [rbp+var_18]; unsigned __int16 **
0x1800362c3  mov     edx, 1F4h; unsigned __int64
0x1800362c8  mov     [rsp+78h+Format], rax; Format
0x1800362cd  mov     rcx, rbx; unsigned __int16 *
0x1800362d0  mov     [rbp+var_18], 0
0x1800362d8  mov     [rbp+var_10], 0
0x1800362e0  call    ?StringCchVPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGPEAD@Z; StringCchVPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,char *)
0x1800362e5  cmp     [rbp+var_20], 1
0x1800362ea  jnz     short loc_180036300
0x1800362ec  mov     rax, [rbp+var_18]
0x1800362f0  mov     ecx, 2Eh ; '.'
0x1800362f5  mov     dword ptr [rax-4], 2E002Eh
0x1800362fc  mov     [rax-6], cx
0x180036300  mov     [rsp+78h+var_38], rbx
0x180036305  mov     r8d, [rdi+18h]
0x180036309  lea     rax, aStatic; "STATIC"
0x180036310  mov     rdx, [rdi+10h]
0x180036314  mov     r9d, esi
0x180036317  mov     rcx, [rdi]
0x18003631a  mov     [rsp+78h+var_40], r15d
0x18003631f  mov     [rsp+78h+Args], rax
0x180036324  mov     eax, [rdi+1Ch]
0x180036327  mov     [rsp+78h+Format], r14
0x18003632c  mov     [rsp+78h+var_58], eax
0x180036330  call    cs:__imp_VssTraceMessage
0x180036336  mov     edx, 2
0x18003633b  mov     rcx, rbx; Block
0x18003633e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180036343  mov     rcx, rdi; this
0x180036346  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x18003634b  add     rsp, 78h
0x18003634f  pop     r15
0x180036351  pop     r14
0x180036353  pop     rdi
0x180036354  pop     rsi
0x180036355  pop     rbx
0x180036356  pop     rbp
0x180036357  retn
```
