# CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)

- ea: `0x180033a8c`
- end: `0x180033b73`
- name: `??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z`
- size: `231`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `237`
- callee_count: `3`
- tags: ``

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

- `0x180033a8c`
- `0x180033c2c`
- `0x180036948`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033acb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033acb`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x180033b15`
- `VssTrace!__imp_VssSetTracingContextPerThread` at `0x180033b15`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x180033b08`
- `VssTrace!__imp_VssGetTracingContextPerThread` at `0x180033b08`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssFunctionTracer::CVssFunctionTracer(__int64 a1, __int64 a2, __int64 a3)
{
  DWORD TickCount; // eax
  __int64 v6; // rax
  unsigned int v7; // r8d
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF

  *(_DWORD *)(a1 + 8) = 0;
  if ( !a3 )
    a3 = *(_QWORD *)(a2 + 8);
  *(_QWORD *)(a1 + 40) = a3;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)a2;
  *(_QWORD *)(a1 + 24) = *(_QWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 32) = *(_DWORD *)(a2 + 24);
  *(_DWORD *)(a1 + 36) = *(_DWORD *)(a2 + 28);
  TickCount = GetTickCount();
  *(_DWORD *)(a1 + 4) = -1;
  *(_DWORD *)(a1 + 52) = TickCount;
  *(_DWORD *)(a1 + 56) = *(_DWORD *)(a2 + 32);
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 96) = 0;
  *(_OWORD *)(a1 + 64) = 0;
  v9 = 0;
  *(_OWORD *)(a1 + 80) = 0;
  if ( (int)VssGetTracingContextPerThread(&v9) >= 0 && (int)VssSetTracingContextPerThread(a1) >= 0 )
    *(_QWORD *)(a1 + 96) = v9;
  v6 = *(_QWORD *)(a1 + 96);
  if ( v6 )
    LODWORD(v6) = *(_DWORD *)(v6 + 48) + 1;
  *(_DWORD *)(a1 + 48) = v6;
  v7 = 160;
  if ( *(_DWORD *)(a1 + 56) != 255 )
    v7 = *(_DWORD *)(a1 + 56);
  CVssFunctionTracer::TraceInternal((CVssFunctionTracer *)a1, L"ENTER", v7, 0);
  CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)a2);
  return a1;
}

```

## disassembly

```asm
0x180033a8c  mov     [rsp+arg_8], rbx
0x180033a91  push    rdi
0x180033a92  sub     rsp, 20h
0x180033a96  mov     dword ptr [rcx+8], 0
0x180033a9d  mov     rdi, rdx
0x180033aa0  mov     rbx, rcx
0x180033aa3  test    r8, r8
0x180033aa6  jnz     short loc_180033AAC
0x180033aa8  mov     r8, [rdx+8]
0x180033aac  mov     [rcx+28h], r8
0x180033ab0  mov     rax, [rdx]
0x180033ab3  mov     [rcx+10h], rax
0x180033ab7  mov     rax, [rdx+10h]
0x180033abb  mov     [rcx+18h], rax
0x180033abf  mov     eax, [rdx+18h]
0x180033ac2  mov     [rcx+20h], eax
0x180033ac5  mov     eax, [rdx+1Ch]
0x180033ac8  mov     [rcx+24h], eax
0x180033acb  call    cs:__imp_GetTickCount
0x180033ad1  mov     dword ptr [rbx+4], 0FFFFFFFFh
0x180033ad8  lea     rcx, [rsp+28h+arg_0]
0x180033add  mov     [rbx+34h], eax
0x180033ae0  xorps   xmm0, xmm0
0x180033ae3  mov     eax, [rdi+20h]
0x180033ae6  mov     [rbx+38h], eax
0x180033ae9  mov     dword ptr [rbx], 0
0x180033aef  mov     qword ptr [rbx+60h], 0
0x180033af7  movups  xmmword ptr [rbx+40h], xmm0
0x180033afb  mov     [rsp+28h+arg_0], 0
0x180033b04  movups  xmmword ptr [rbx+50h], xmm0
0x180033b08  call    cs:__imp_VssGetTracingContextPerThread
0x180033b0e  test    eax, eax
0x180033b10  js      short loc_180033B28
0x180033b12  mov     rcx, rbx
0x180033b15  call    cs:__imp_VssSetTracingContextPerThread
0x180033b1b  test    eax, eax
0x180033b1d  js      short loc_180033B28
0x180033b1f  mov     rax, [rsp+28h+arg_0]
0x180033b24  mov     [rbx+60h], rax
0x180033b28  mov     rax, [rbx+60h]
0x180033b2c  test    rax, rax
0x180033b2f  jz      short loc_180033B36
0x180033b31  mov     eax, [rax+30h]
0x180033b34  inc     eax
0x180033b36  mov     [rbx+30h], eax
0x180033b39  lea     rdx, aEnter; "ENTER"
0x180033b40  cmp     dword ptr [rbx+38h], 0FFh
0x180033b47  mov     r8d, 0A0h
0x180033b4d  mov     rcx, rbx; this
0x180033b50  cmovnz  r8d, [rbx+38h]; unsigned int
0x180033b55  xor     r9d, r9d; unsigned __int16 *
0x180033b58  call    ?TraceInternal@CVssFunctionTracer@@QEAAXPEBGK0@Z; CVssFunctionTracer::TraceInternal(ushort const *,ulong,ushort const *)
0x180033b5d  mov     rcx, rdi; this
0x180033b60  call    ??1CVssDebugInfo@@QEAA@XZ; CVssDebugInfo::~CVssDebugInfo(void)
0x180033b65  mov     rax, rbx
0x180033b68  mov     rbx, [rsp+28h+arg_8]
0x180033b6d  add     rsp, 20h
0x180033b71  pop     rdi
0x180033b72  retn
```
