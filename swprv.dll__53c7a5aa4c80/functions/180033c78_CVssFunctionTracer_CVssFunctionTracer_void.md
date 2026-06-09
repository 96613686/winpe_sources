# CVssFunctionTracer::~CVssFunctionTracer(void)

- ea: `0x180033c78`
- end: `0x180033d6d`
- name: `??1CVssFunctionTracer@@QEAA@XZ`
- size: `245`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `264`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000335c`
- `0x1800034cc`
- `0x18000357c`
- `0x1800037b0`
- `0x180003888`
- `0x180003930`
- `0x180004860`
- `0x180004c74`
- `0x180004fbc`
- `0x1800051a0`
- `0x1800057c0`
- `0x1800059a0`
- `0x180005a80`
- `0x180005b40`
- `0x180005f18`
- `0x180006080`
- `0x18000681c`
- `0x180006910`
- `0x180006cb0`
- `0x180007148`
- `0x180007374`
- `0x1800076b0`
- `0x180007758`
- `0x180007824`
- `0x180007a54`
- `0x180007b80`
- `0x180009a30`
- `0x180009db0`
- `0x180009f90`
- `0x18000a378`
- `0x18000a5a0`
- `0x18000a740`
- `0x18000aa5c`
- `0x18000af80`
- `0x18000b0d8`
- `0x18000b270`
- `0x18000b448`
- `0x18000c770`
- `0x18000cc10`
- `0x18000cd50`
- `0x18000d968`
- `0x18000dc7c`
- `0x18000de70`
- `0x18000e900`
- `0x18000f910`
- `0x18000ffe0`
- `0x1800108d4`
- `0x180010974`
- `0x180010a20`
- `0x180011178`

## callees

- `0x180033c78`
- `0x180036a1c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033ca3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033ca3`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x180033d66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c8b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033c8b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CVssFunctionTracer::~CVssFunctionTracer(LPVOID *this)
{
  __int64 i; // rbx
  DWORD TickCount; // eax
  unsigned int v4; // r8d

  for ( i = 0; i != 4; ++i )
  {
    CoTaskMemFree(this[i + 8]);
    this[i + 8] = 0;
  }
  TickCount = GetTickCount();
  v4 = 160;
  if ( *((_DWORD *)this + 14) != 255 )
    v4 = *((_DWORD *)this + 14);
  CVssFunctionTracer::TraceInternalWithFormat(
    (CVssFunctionTracer *)this,
    L"EXIT",
    v4,
    L"Time spent: %02ld:%02ld:%02ld-%04ld; total: %#x; HRESULT: %#x",
    (TickCount - *((_DWORD *)this + 13)) / 0x36EE80 % 0x3C,
    (TickCount - *((_DWORD *)this + 13)) / 0xEA60 % 0x3C,
    (TickCount - *((_DWORD *)this + 13)) / 0x3E8 % 0x3C,
    (TickCount - *((_DWORD *)this + 13)) % 0x3E8,
    TickCount - *((_DWORD *)this + 13),
    *((_DWORD *)this + 2));
  VssSetTracingContextPerThread(this[12]);
}

```

## disassembly

```asm
0x180033c78  push    rbx
0x180033c7a  push    rbp
0x180033c7b  push    rsi
0x180033c7c  push    rdi
0x180033c7d  sub     rsp, 58h
0x180033c81  mov     rbp, rcx
0x180033c84  xor     ebx, ebx
0x180033c86  mov     rcx, [rbp+rbx*8+40h]; pv
0x180033c8b  call    cs:__imp_CoTaskMemFree
0x180033c91  mov     qword ptr [rbp+rbx*8+40h], 0
0x180033c9a  inc     rbx
0x180033c9d  cmp     rbx, 4
0x180033ca1  jnz     short loc_180033C86
0x180033ca3  call    cs:__imp_GetTickCount
0x180033ca9  mov     r9d, [rbp+8]
0x180033cad  mov     r8d, 88888889h
0x180033cb3  mov     esi, eax
0x180033cb5  mov     [rsp+78h+var_30], r9d
0x180033cba  sub     esi, [rbp+34h]
0x180033cbd  lea     r9, aTimeSpent02ld0; "Time spent: %02ld:%02ld:%02ld-%04ld; to"...
0x180033cc4  mov     eax, 10624DD3h
0x180033cc9  mov     [rsp+78h+var_38], esi
0x180033ccd  mul     esi
0x180033ccf  mov     eax, r8d
0x180033cd2  mov     edi, edx
0x180033cd4  shr     edi, 6
0x180033cd7  mul     edi
0x180033cd9  mov     eax, 45E7B273h
0x180033cde  mov     ebx, edi
0x180033ce0  shr     edx, 5
0x180033ce3  imul    ecx, edx, 3Ch ; '<'
0x180033ce6  mul     esi
0x180033ce8  sub     ebx, ecx
0x180033cea  mov     eax, r8d
0x180033ced  mov     r11d, edx
0x180033cf0  shr     r11d, 0Eh
0x180033cf4  mul     r11d
0x180033cf7  mov     eax, 95217CB1h
0x180033cfc  shr     edx, 5
0x180033cff  imul    ecx, edx, 3Ch ; '<'
0x180033d02  mul     esi
0x180033d04  sub     r11d, ecx
0x180033d07  mov     eax, r8d
0x180033d0a  mov     r10d, edx
0x180033d0d  mov     r8d, 0A0h
0x180033d13  shr     r10d, 15h
0x180033d17  mov     ecx, esi
0x180033d19  mul     r10d
0x180033d1c  shr     edx, 5
0x180033d1f  imul    eax, edx, 3Ch ; '<'
0x180033d22  lea     rdx, aExit; "EXIT"
0x180033d29  sub     r10d, eax
0x180033d2c  cmp     dword ptr [rbp+38h], 0FFh
0x180033d33  cmovnz  r8d, [rbp+38h]; unsigned int
0x180033d38  imul    eax, edi, 3E8h
0x180033d3e  sub     ecx, eax
0x180033d40  mov     [rsp+78h+var_40], ecx
0x180033d44  mov     rcx, rbp; this
0x180033d47  mov     [rsp+78h+var_48], ebx
0x180033d4b  mov     [rsp+78h+var_50], r11d
0x180033d50  mov     [rsp+78h+var_58], r10d
0x180033d55  call    ?TraceInternalWithFormat@CVssFunctionTracer@@QEAAXPEBGK0ZZ; CVssFunctionTracer::TraceInternalWithFormat(ushort const *,ulong,ushort const *,...)
0x180033d5a  mov     rcx, [rbp+60h]
0x180033d5e  add     rsp, 58h
0x180033d62  pop     rdi
0x180033d63  pop     rsi
0x180033d64  pop     rbp
0x180033d65  pop     rbx
0x180033d66  jmp     cs:__imp_VssSetTracingContextPerThread
```
