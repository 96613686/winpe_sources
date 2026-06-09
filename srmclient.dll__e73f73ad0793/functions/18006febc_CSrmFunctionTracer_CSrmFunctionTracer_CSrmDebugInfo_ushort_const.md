# CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)

- ea: `0x18006febc`
- end: `0x180070016`
- name: `??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64, const struct CSrmDebugInfo *, __int64)`
- caller_count: `712`
- callee_count: `5`
- tags: ``

## callers

- `0x180007bd4`
- `0x18000ad14`
- `0x18000af40`
- `0x18000b0e8`
- `0x18000b3a0`
- `0x18000b5e0`
- `0x18000b820`
- `0x18000ba70`
- `0x18000bd50`
- `0x18000c030`
- `0x18000c35c`
- `0x18000c86c`
- `0x18000d114`
- `0x18000d1e0`
- `0x18000d560`
- `0x18000d8ec`
- `0x18000e290`
- `0x18000e750`
- `0x18000f488`
- `0x18000f98c`
- `0x18000fb7c`
- `0x18000fd74`
- `0x18000ff90`
- `0x1800101e8`
- `0x1800106e0`
- `0x180010930`
- `0x180010e60`
- `0x180011280`
- `0x180011cdc`
- `0x180011ef4`
- `0x180012484`
- `0x1800125c0`
- `0x180014c40`
- `0x180014ed4`
- `0x180015334`
- `0x180016408`
- `0x180016540`
- `0x180016648`
- `0x18001671c`
- `0x180016d28`
- `0x180016ee0`
- `0x180017210`
- `0x1800176f4`
- `0x18001791c`
- `0x180017adc`
- `0x180017e90`
- `0x180018064`
- `0x1800189fc`
- `0x180018b04`
- `0x18001a440`

## callees

- `0x180002018`
- `0x18006fdf0`
- `0x18006febc`
- `0x18007006c`
- `0x18007416c`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18006ff4e`
- `KERNEL32!GetTickCount` at `0x18006ff4e`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x18006ff90`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x18006ff90`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x18006ff83`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x18006ff83`

## pseudocode

```c
__int64 __fastcall CSrmFunctionTracer::CSrmFunctionTracer(__int64 a1, const struct CSrmDebugInfo *a2, __int64 a3)
{
  CSrmDebugInfo *v6; // rdi
  __int64 v7; // rax
  unsigned int v8; // r8d
  _BYTE v10[184]; // [rsp+30h] [rbp-B8h] BYREF
  __int64 v11; // [rsp+100h] [rbp+18h] BYREF
  CSrmDebugInfo *v12; // [rsp+108h] [rbp+20h]

  v6 = CSrmDebugInfo::CSrmDebugInfo((CSrmDebugInfo *)v10, a2);
  v12 = v6;
  *(_QWORD *)a1 = &CSrmFunctionTracerBase::`vftable';
  `eh vector constructor iterator'(
    (void *)(a1 + 72),
    0x20u,
    3u,
    (void (*)(void *))CSrmFunctionTracerBase::_ContextArray::_ContextArray,
    (void (*)(void *))CSrmFunctionTracerBase::_ContextArray::~_ContextArray);
  *(_DWORD *)(a1 + 8) = 0;
  if ( !a3 )
    a3 = *((_QWORD *)v6 + 1);
  *(_QWORD *)(a1 + 48) = a3;
  *(_QWORD *)(a1 + 24) = *(_QWORD *)v6;
  *(_QWORD *)(a1 + 32) = *((_QWORD *)v6 + 2);
  *(_DWORD *)(a1 + 40) = *((_DWORD *)v6 + 6);
  *(_DWORD *)(a1 + 44) = *((_DWORD *)v6 + 7);
  *(_DWORD *)(a1 + 60) = GetTickCount();
  *(_DWORD *)(a1 + 16) = -1;
  *(_DWORD *)(a1 + 64) = *((_DWORD *)v6 + 8);
  *(_QWORD *)(a1 + 168) = 0;
  v11 = 0;
  if ( (int)SrmGetTracingContextPerThread(&v11) >= 0 && (int)SrmSetTracingContextPerThread(a1) >= 0 )
    *(_QWORD *)(a1 + 168) = v11;
  v7 = *(_QWORD *)(a1 + 168);
  if ( v7 )
    LODWORD(v7) = *(_DWORD *)(v7 + 56) + 1;
  *(_DWORD *)(a1 + 56) = v7;
  v8 = 160;
  if ( *(_DWORD *)(a1 + 64) != 255 )
    v8 = *(_DWORD *)(a1 + 64);
  CSrmFunctionTracerBase::TraceInternal((CSrmFunctionTracerBase *)a1, L"ENTER", v8, *(_DWORD *)(a1 + 40), 0);
  CSrmDebugInfo::~CSrmDebugInfo(v6);
  *(_QWORD *)a1 = &CSrmFunctionTracer::`vftable';
  CSrmDebugInfo::~CSrmDebugInfo(a2);
  return a1;
}

```

## disassembly

```asm
0x18006febc  mov     [rsp+arg_8], rdx
0x18006fec1  mov     [rsp+arg_0], rcx
0x18006fec6  push    rbx
0x18006fec7  push    rbp
0x18006fec8  push    rsi
0x18006fec9  push    rdi
0x18006feca  sub     rsp, 0C8h
0x18006fed1  mov     rsi, r8
0x18006fed4  mov     rbp, rdx
0x18006fed7  mov     rbx, rcx
0x18006feda  lea     rcx, [rsp+0E8h+var_B8]; this
0x18006fedf  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x18006fee4  mov     rdi, rax
0x18006fee7  mov     [rsp+0E8h+arg_18], rax
0x18006feef  lea     rax, ??_7CSrmFunctionTracerBase@@6B@; const CSrmFunctionTracerBase::`vftable'
0x18006fef6  mov     [rbx], rax
0x18006fef9  lea     rcx, [rbx+48h]; void *
0x18006fefd  lea     rax, ??1_ContextArray@CSrmFunctionTracerBase@@QEAA@XZ; CSrmFunctionTracerBase::_ContextArray::~_ContextArray(void)
0x18006ff04  mov     [rsp+0E8h+var_C8], rax; void (*)(void *)
0x18006ff09  lea     r9, ??0_ContextArray@CSrmFunctionTracerBase@@QEAA@XZ; void (*)(void *)
0x18006ff10  mov     edx, 20h ; ' '; unsigned __int64
0x18006ff15  lea     r8d, [rdx-1Dh]; unsigned __int64
0x18006ff19  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18006ff1e  nop
0x18006ff1f  mov     dword ptr [rbx+8], 0
0x18006ff26  test    rsi, rsi
0x18006ff29  jnz     short loc_18006FF2F
0x18006ff2b  mov     rsi, [rdi+8]
0x18006ff2f  mov     [rbx+30h], rsi
0x18006ff33  mov     rax, [rdi]
0x18006ff36  mov     [rbx+18h], rax
0x18006ff3a  mov     rax, [rdi+10h]
0x18006ff3e  mov     [rbx+20h], rax
0x18006ff42  mov     eax, [rdi+18h]
0x18006ff45  mov     [rbx+28h], eax
0x18006ff48  mov     eax, [rdi+1Ch]
0x18006ff4b  mov     [rbx+2Ch], eax
0x18006ff4e  call    cs:__imp_GetTickCount
0x18006ff54  mov     [rbx+3Ch], eax
0x18006ff57  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18006ff5e  mov     eax, [rdi+20h]
0x18006ff61  mov     [rbx+40h], eax
0x18006ff64  mov     qword ptr [rbx+0A8h], 0
0x18006ff6f  mov     [rsp+0E8h+arg_10], 0
0x18006ff7b  lea     rcx, [rsp+0E8h+arg_10]
0x18006ff83  call    cs:__imp_SrmGetTracingContextPerThread
0x18006ff89  test    eax, eax
0x18006ff8b  js      short loc_18006FFA9
0x18006ff8d  mov     rcx, rbx
0x18006ff90  call    cs:__imp_SrmSetTracingContextPerThread
0x18006ff96  test    eax, eax
0x18006ff98  js      short loc_18006FFA9
0x18006ff9a  mov     rax, [rsp+0E8h+arg_10]
0x18006ffa2  mov     [rbx+0A8h], rax
0x18006ffa9  mov     rax, [rbx+0A8h]
0x18006ffb0  test    rax, rax
0x18006ffb3  jz      short loc_18006FFBA
0x18006ffb5  mov     eax, [rax+38h]
0x18006ffb8  inc     eax
0x18006ffba  mov     [rbx+38h], eax
0x18006ffbd  mov     r8d, 0A0h
0x18006ffc3  cmp     dword ptr [rbx+40h], 0FFh
0x18006ffca  cmovnz  r8d, [rbx+40h]; unsigned int
0x18006ffcf  mov     [rsp+0E8h+var_C8], 0; unsigned __int16 *
0x18006ffd8  mov     r9d, [rbx+28h]; unsigned int
0x18006ffdc  lea     rdx, aEnter; "ENTER"
0x18006ffe3  mov     rcx, rbx; this
0x18006ffe6  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXPEBGKK0@Z; CSrmFunctionTracerBase::TraceInternal(ushort const *,ulong,ulong,ushort const *)
0x18006ffeb  nop
0x18006ffec  mov     rcx, rdi; this
0x18006ffef  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x18006fff4  nop
0x18006fff5  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18006fffc  mov     [rbx], rax
0x18006ffff  mov     rcx, rbp; this
0x180070002  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180070007  mov     rax, rbx
0x18007000a  add     rsp, 0C8h
0x180070011  pop     rdi
0x180070012  pop     rsi
0x180070013  pop     rbp
0x180070014  pop     rbx
0x180070015  retn
```
