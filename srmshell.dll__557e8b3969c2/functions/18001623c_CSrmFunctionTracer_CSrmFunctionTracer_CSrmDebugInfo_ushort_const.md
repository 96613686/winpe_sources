# CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)

- ea: `0x18001623c`
- end: `0x180016396`
- name: `??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z`
- size: `346`
- prototype: `__int64 __fastcall(__int64, const struct CSrmDebugInfo *, __int64)`
- caller_count: `37`
- callee_count: `5`
- tags: ``

## callers

- `0x180002658`
- `0x180002960`
- `0x180002b10`
- `0x1800059e0`
- `0x180005ce0`
- `0x180005e50`
- `0x180005fa0`
- `0x1800061d0`
- `0x180006688`
- `0x180006b50`
- `0x180007870`
- `0x1800079e0`
- `0x180007d44`
- `0x180008288`
- `0x180008408`
- `0x180009124`
- `0x1800096c0`
- `0x180009d18`
- `0x18000a460`
- `0x18000a704`
- `0x18000ace8`
- `0x18000b410`
- `0x18000dd70`
- `0x18000e224`
- `0x18000ecb8`
- `0x18000eeb4`
- `0x18000f4b0`
- `0x18000f7cc`
- `0x180016f34`
- `0x180017158`
- `0x1800180a0`
- `0x1800188cc`
- `0x180018af0`
- `0x18001a384`
- `0x18001a540`
- `0x18001a9f8`
- `0x18001ae30`

## callees

- `0x180002238`
- `0x180016170`
- `0x18001623c`
- `0x180016518`
- `0x180019510`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800162ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800162ce`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x180016310`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x180016310`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x180016303`
- `SrmTrace!__imp_SrmGetTracingContextPerThread` at `0x180016303`

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
0x18001623c  mov     [rsp+arg_8], rdx
0x180016241  mov     [rsp+arg_0], rcx
0x180016246  push    rbx
0x180016247  push    rbp
0x180016248  push    rsi
0x180016249  push    rdi
0x18001624a  sub     rsp, 0C8h
0x180016251  mov     rsi, r8
0x180016254  mov     rbp, rdx
0x180016257  mov     rbx, rcx
0x18001625a  lea     rcx, [rsp+0E8h+var_B8]; this
0x18001625f  call    ??0CSrmDebugInfo@@QEAA@AEBU0@@Z; CSrmDebugInfo::CSrmDebugInfo(CSrmDebugInfo const &)
0x180016264  mov     rdi, rax
0x180016267  mov     [rsp+0E8h+arg_18], rax
0x18001626f  lea     rax, ??_7CSrmFunctionTracerBase@@6B@; const CSrmFunctionTracerBase::`vftable'
0x180016276  mov     [rbx], rax
0x180016279  lea     rcx, [rbx+48h]; void *
0x18001627d  lea     rax, ??1_ContextArray@CSrmFunctionTracerBase@@QEAA@XZ; CSrmFunctionTracerBase::_ContextArray::~_ContextArray(void)
0x180016284  mov     [rsp+0E8h+var_C8], rax; void (*)(void *)
0x180016289  lea     r9, ??0_ContextArray@CSrmFunctionTracerBase@@QEAA@XZ; void (*)(void *)
0x180016290  mov     edx, 20h ; ' '; unsigned __int64
0x180016295  lea     r8d, [rdx-1Dh]; unsigned __int64
0x180016299  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18001629e  nop
0x18001629f  mov     dword ptr [rbx+8], 0
0x1800162a6  test    rsi, rsi
0x1800162a9  jnz     short loc_1800162AF
0x1800162ab  mov     rsi, [rdi+8]
0x1800162af  mov     [rbx+30h], rsi
0x1800162b3  mov     rax, [rdi]
0x1800162b6  mov     [rbx+18h], rax
0x1800162ba  mov     rax, [rdi+10h]
0x1800162be  mov     [rbx+20h], rax
0x1800162c2  mov     eax, [rdi+18h]
0x1800162c5  mov     [rbx+28h], eax
0x1800162c8  mov     eax, [rdi+1Ch]
0x1800162cb  mov     [rbx+2Ch], eax
0x1800162ce  call    cs:__imp_GetTickCount
0x1800162d4  mov     [rbx+3Ch], eax
0x1800162d7  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x1800162de  mov     eax, [rdi+20h]
0x1800162e1  mov     [rbx+40h], eax
0x1800162e4  mov     qword ptr [rbx+0A8h], 0
0x1800162ef  mov     [rsp+0E8h+arg_10], 0
0x1800162fb  lea     rcx, [rsp+0E8h+arg_10]
0x180016303  call    cs:__imp_SrmGetTracingContextPerThread
0x180016309  test    eax, eax
0x18001630b  js      short loc_180016329
0x18001630d  mov     rcx, rbx
0x180016310  call    cs:__imp_SrmSetTracingContextPerThread
0x180016316  test    eax, eax
0x180016318  js      short loc_180016329
0x18001631a  mov     rax, [rsp+0E8h+arg_10]
0x180016322  mov     [rbx+0A8h], rax
0x180016329  mov     rax, [rbx+0A8h]
0x180016330  test    rax, rax
0x180016333  jz      short loc_18001633A
0x180016335  mov     eax, [rax+38h]
0x180016338  inc     eax
0x18001633a  mov     [rbx+38h], eax
0x18001633d  mov     r8d, 0A0h
0x180016343  cmp     dword ptr [rbx+40h], 0FFh
0x18001634a  cmovnz  r8d, [rbx+40h]; unsigned int
0x18001634f  mov     [rsp+0E8h+var_C8], 0; unsigned __int16 *
0x180016358  mov     r9d, [rbx+28h]; unsigned int
0x18001635c  lea     rdx, aEnter; "ENTER"
0x180016363  mov     rcx, rbx; this
0x180016366  call    ?TraceInternal@CSrmFunctionTracerBase@@QEAAXPEBGKK0@Z; CSrmFunctionTracerBase::TraceInternal(ushort const *,ulong,ulong,ushort const *)
0x18001636b  nop
0x18001636c  mov     rcx, rdi; this
0x18001636f  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180016374  nop
0x180016375  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18001637c  mov     [rbx], rax
0x18001637f  mov     rcx, rbp; this
0x180016382  call    ??1CSrmDebugInfo@@QEAA@XZ; CSrmDebugInfo::~CSrmDebugInfo(void)
0x180016387  mov     rax, rbx
0x18001638a  add     rsp, 0C8h
0x180016391  pop     rdi
0x180016392  pop     rsi
0x180016393  pop     rbp
0x180016394  pop     rbx
0x180016395  retn
```
