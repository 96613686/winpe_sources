# UpdateProgress(void)

- ea: `0x14001920c`
- end: `0x1400192ac`
- name: `?UpdateProgress@@YAXXZ`
- size: `160`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140017260`
- `0x14001a644`

## callees

- `0x14001920c`
- `0x140041010`

## pseudocode

```c
void UpdateProgress(void)
{
  __int64 v0; // rdx

  if ( *((_QWORD *)g_TraceContext + 803) )
  {
    v0 = *((_QWORD *)g_TraceContext + 1086);
    if ( !v0 || *(_DWORD *)(v0 + 24) )
      (*((void (__fastcall **)(__int64))g_TraceContext + 803))(1);
  }
}

```

## disassembly

```asm
0x14001920c  sub     rsp, 28h
0x140019210  mov     r8, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140019217  mov     r9, [r8+1918h]
0x14001921e  test    r9, r9
0x140019221  jz      loc_1400192A7
0x140019227  mov     rdx, [r8+21F0h]
0x14001922e  test    rdx, rdx
0x140019231  jz      short loc_140019244
0x140019233  cmp     dword ptr [rdx+18h], 0
0x140019237  jz      short loc_1400192A7
0x140019239  test    rdx, rdx
0x14001923c  jz      short loc_140019244
0x14001923e  mov     r10d, [rdx+18h]
0x140019242  jmp     short loc_140019247
0x140019244  xor     r10d, r10d
0x140019247  mov     ecx, cs:?TotalBuffersExpected@@3KA; ulong TotalBuffersExpected
0x14001924d  inc     ecx
0x14001924f  xorps   xmm2, xmm2
0x140019252  cvtsi2sd xmm2, rcx
0x140019257  mov     eax, r10d
0x14001925a  xorps   xmm0, xmm0
0x14001925d  cvtsi2sd xmm0, rax
0x140019262  addsd   xmm2, xmm0
0x140019266  xorps   xmm1, xmm1
0x140019269  comisd  xmm2, xmm1
0x14001926d  jbe     short loc_140019286
0x14001926f  test    rdx, rdx
0x140019272  jz      short loc_140019279
0x140019274  movsd   xmm1, qword ptr [rdx+10h]
0x140019279  addsd   xmm1, qword ptr [r8+2130h]
0x140019282  divsd   xmm1, xmm2
0x140019286  mov     ecx, 1
0x14001928b  mov     rax, r9
0x14001928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140019293  jmp     short loc_1400192A7
0x140019295  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14001929c  mov     qword ptr [rax+1918h], 0
0x1400192a7  add     rsp, 28h
0x1400192ab  retn
```
