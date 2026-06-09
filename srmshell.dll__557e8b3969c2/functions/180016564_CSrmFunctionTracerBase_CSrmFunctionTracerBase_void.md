# CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)

- ea: `0x180016564`
- end: `0x18001666a`
- name: `??1CSrmFunctionTracerBase@@UEAA@XZ`
- size: `262`
- prototype: `void __fastcall(CSrmFunctionTracerBase *__hidden this)`
- caller_count: `61`
- callee_count: `2`
- tags: ``

## callers

- `0x180002658`
- `0x180002960`
- `0x180002b10`
- `0x1800051e0`
- `0x180005940`
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
- `0x180016a60`
- `0x180016f34`
- `0x180017158`
- `0x1800180a0`
- `0x1800188cc`
- `0x180018af0`
- `0x18001a384`
- `0x18001a540`
- `0x18001a9f8`
- `0x18001ae30`
- `0x18001b93b`
- `0x18001b95f`
- `0x18001bb0f`
- `0x18001c1c0`
- `0x18001c2c8`
- `0x18001c478`
- `0x18001c4ae`
- `0x18001c4d2`
- `0x18001c6ee`
- `0x18001c76c`

## callees

- `0x180001898`
- `0x1800195f0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001657f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001657f`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x18001663f`
- `SrmTrace!__imp_SrmSetTracingContextPerThread` at `0x18001663f`

## pseudocode

```c
void __fastcall CSrmFunctionTracerBase::~CSrmFunctionTracerBase(CSrmFunctionTracerBase *this)
{
  DWORD v2; // esi
  unsigned int v3; // r8d
  unsigned int v4; // [rsp+20h] [rbp-58h]
  unsigned int v5; // [rsp+28h] [rbp-50h]
  unsigned int v6; // [rsp+30h] [rbp-48h]
  unsigned int v7; // [rsp+38h] [rbp-40h]
  DWORD v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]

  *(_QWORD *)this = &CSrmFunctionTracerBase::`vftable';
  v2 = GetTickCount() - *((_DWORD *)this + 15);
  v3 = 160;
  if ( *((_DWORD *)this + 16) != 255 )
    v3 = *((_DWORD *)this + 16);
  v9 = *((_DWORD *)this + 2);
  v8 = v2;
  v7 = v2 % 0x3E8;
  v6 = v2 / 0x3E8 % 0x3C;
  v5 = v2 / 0xEA60 % 0x3C;
  v4 = v2 / 0x36EE80 % 0x3C;
  CSrmFunctionTracerBase::TraceInternalWithFormat(
    this,
    L"EXIT",
    v3,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    v4,
    v5,
    v6,
    v7,
    v8,
    v9);
  SrmSetTracingContextPerThread(*((_QWORD *)this + 21));
  `eh vector destructor iterator'(
    (char *)this + 72,
    0x20u,
    3u,
    (void (*)(void *))CSrmFunctionTracerBase::_ContextArray::~_ContextArray);
}

```

## disassembly

```asm
0x180016564  mov     [rsp+arg_0], rcx
0x180016569  push    rbx
0x18001656a  push    rsi
0x18001656b  push    rdi
0x18001656c  push    r14
0x18001656e  sub     rsp, 58h
0x180016572  mov     r14, rcx
0x180016575  lea     rax, ??_7CSrmFunctionTracerBase@@6B@; const CSrmFunctionTracerBase::`vftable'
0x18001657c  mov     [rcx], rax
0x18001657f  call    cs:__imp_GetTickCount
0x180016585  mov     esi, eax
0x180016587  sub     esi, [r14+3Ch]
0x18001658b  mov     eax, 10624DD3h
0x180016590  mul     esi
0x180016592  mov     edi, edx
0x180016594  shr     edi, 6
0x180016597  mov     r8d, 88888889h
0x18001659d  mov     eax, r8d
0x1800165a0  mul     edi
0x1800165a2  shr     edx, 5
0x1800165a5  imul    ecx, edx, 3Ch ; '<'
0x1800165a8  mov     ebx, edi
0x1800165aa  sub     ebx, ecx
0x1800165ac  mov     eax, 45E7B273h
0x1800165b1  mul     esi
0x1800165b3  mov     r11d, edx
0x1800165b6  shr     r11d, 0Eh
0x1800165ba  mov     eax, r8d
0x1800165bd  mul     r11d
0x1800165c0  shr     edx, 5
0x1800165c3  imul    ecx, edx, 3Ch ; '<'
0x1800165c6  sub     r11d, ecx
0x1800165c9  mov     eax, 95217CB1h
0x1800165ce  mul     esi
0x1800165d0  mov     r10d, edx
0x1800165d3  shr     r10d, 15h
0x1800165d7  mov     eax, r8d
0x1800165da  mul     r10d
0x1800165dd  shr     edx, 5
0x1800165e0  imul    eax, edx, 3Ch ; '<'
0x1800165e3  sub     r10d, eax
0x1800165e6  mov     r9d, [r14+8]
0x1800165ea  mov     r8d, 0A0h
0x1800165f0  cmp     dword ptr [r14+40h], 0FFh
0x1800165f8  cmovnz  r8d, [r14+40h]; unsigned int
0x1800165fd  imul    eax, edi, 3E8h
0x180016603  mov     ecx, esi
0x180016605  sub     ecx, eax
0x180016607  mov     [rsp+78h+var_30], r9d
0x18001660c  mov     [rsp+78h+var_38], esi
0x180016610  mov     [rsp+78h+var_40], ecx
0x180016614  mov     [rsp+78h+var_48], ebx
0x180016618  mov     [rsp+78h+var_50], r11d
0x18001661d  mov     [rsp+78h+var_58], r10d
0x180016622  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x180016629  lea     rdx, aExit; "EXIT"
0x180016630  mov     rcx, r14; this
0x180016633  call    ?TraceInternalWithFormat@CSrmFunctionTracerBase@@QEAAXPEBGK0ZZ; CSrmFunctionTracerBase::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180016638  mov     rcx, [r14+0A8h]
0x18001663f  call    cs:__imp_SrmSetTracingContextPerThread
0x180016645  nop
0x180016646  lea     rcx, [r14+48h]; void *
0x18001664a  lea     r9, ??1_ContextArray@CSrmFunctionTracerBase@@QEAA@XZ; void (*)(void *)
0x180016651  mov     edx, 20h ; ' '; unsigned __int64
0x180016656  lea     r8d, [rdx-1Dh]; unsigned __int64
0x18001665a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001665f  nop
0x180016660  add     rsp, 58h
0x180016664  pop     r14
0x180016666  pop     rdi
0x180016667  pop     rsi
0x180016668  pop     rbx
0x180016669  retn
```
