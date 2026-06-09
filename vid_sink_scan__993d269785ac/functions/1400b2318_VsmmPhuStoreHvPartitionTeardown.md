# VsmmPhuStoreHvPartitionTeardown

- ea: `0x1400b2318`
- end: `0x1400b2493`
- name: `VsmmPhuStoreHvPartitionTeardown`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x14009eb70`

## callees

- `0x140024754`
- `0x1400aa96c`
- `0x1400b2318`
- `0x1400b6730`
- `0x1400b8954`

## import_xrefs

- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b246f`
- `winhvr!WinHvUnlinkPreExistingPartition` at `0x1400b246f`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b2363`
- `winhvr!WinHvDeletePartitionRemote` at `0x1400b2363`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b244c`
- `winhvr!WinHvSetInterceptRoutine` at `0x1400b244c`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b2460`
- `winhvr!WinHvSetLowMemoryPolicyRoutine` at `0x1400b2460`

## pseudocode

```c
__int64 __fastcall VsmmPhuStoreHvPartitionTeardown(__int64 a1, __int64 a2)
{
  bool v4; // zf
  int v5; // eax
  __int64 result; // rax
  __int64 v7; // rbx
  char v8; // al
  char v9; // cl

  if ( *(_DWORD *)(a1 + 8632) == 2 )
  {
    v7 = *(_QWORD *)(a1 + 648);
    *(_QWORD *)(a1 + 648) = -1;
    v8 = *(_BYTE *)(a2 + 49);
    *(_QWORD *)(a2 + 56) = v7;
    *(_BYTE *)(a2 + 49) = v8 ^ (*(_BYTE *)(a1 + 8761) ^ v8) & 1;
    v9 = 2 * *(_BYTE *)(a1 + 8762);
    *(_BYTE *)(a1 + 8761) = 0;
    *(_BYTE *)(a2 + 49) ^= (*(_BYTE *)(a2 + 49) ^ v9) & 2;
    *(_BYTE *)(a1 + 8762) = 0;
    *(_BYTE *)(a2 + 49) ^= (*(_BYTE *)(a2 + 49) ^ (4 * *(_BYTE *)(a1 + 3221))) & 4;
    *(_QWORD *)(a2 + 104) = *(_QWORD *)(a1 + 8768);
    *(_QWORD *)(a1 + 8768) = 0;
    VsmmVsmGetPartitionConfig(a1, a2, a2 + 64);
    *(_BYTE *)(a2 + 48) = 1;
    WinHvSetInterceptRoutine(v7, 0, a2);
    WinHvSetLowMemoryPolicyRoutine(v7, 0, a2);
    result = WinHvUnlinkPreExistingPartition(v7);
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 8768) == 0;
    *(_WORD *)(a1 + 8761) = 0;
    if ( !v4 )
    {
      if ( (*(_DWORD *)(a1 + 8640) & 4) != 0 )
        VsmmPhuStorepHvPartitionMirrorTeardown();
      v5 = WinHvDeletePartitionRemote(*(_QWORD *)(a1 + 648));
      if ( v5 < 0 )
        VidTraceErrorStatusPartitionInternal0(
          (unsigned int)"VsmmPhuStoreHvPartitionTeardown",
          (unsigned int)"onecore\\vm\\vid\\sys\\vsmm\\vsmmphustore.c",
          3810,
          v5,
          a1 + 656);
      *(_QWORD *)(a1 + 8768) = 0;
    }
    result = VsmmPhuStorepSerializationChargeDecrease(*(_QWORD *)(a1 + 8648), 144);
  }
  *(_BYTE *)(a1 + 8760) = 0;
  return result;
}

```

## disassembly

```asm
0x1400b2318  mov     [rsp+arg_0], rbx
0x1400b231d  mov     [rsp+arg_8], rbp
0x1400b2322  push    rdi
0x1400b2323  sub     rsp, 30h
0x1400b2327  cmp     dword ptr [rcx+21B8h], 2
0x1400b232e  mov     rbp, rdx
0x1400b2331  mov     rdi, rcx
0x1400b2334  jz      loc_1400B23BC
0x1400b233a  cmp     qword ptr [rcx+2240h], 0
0x1400b2342  mov     word ptr [rcx+2239h], 0
0x1400b234b  jz      short loc_1400B23A6
0x1400b234d  mov     eax, [rcx+21C0h]
0x1400b2353  test    al, 4
0x1400b2355  jz      short loc_1400B235C
0x1400b2357  call    VsmmPhuStorepHvPartitionMirrorTeardown
0x1400b235c  mov     rcx, [rdi+288h]
0x1400b2363  call    cs:__imp_WinHvDeletePartitionRemote
0x1400b236a  nop     dword ptr [rax+rax+00h]
0x1400b236f  test    eax, eax
0x1400b2371  jns     short loc_1400B239B
0x1400b2373  lea     rcx, [rdi+290h]
0x1400b237a  mov     r9d, eax
0x1400b237d  mov     [rsp+38h+var_18], rcx
0x1400b2382  lea     rdx, aOnecoreVmVidSy_55; "onecore\\vm\\vid\\sys\\vsmm\\vsmmphusto"...
0x1400b2389  lea     rcx, aVsmmphustorehv_1; "VsmmPhuStoreHvPartitionTeardown"
0x1400b2390  mov     r8d, 0EE2h
0x1400b2396  call    VidTraceErrorStatusPartitionInternal0
0x1400b239b  mov     qword ptr [rdi+2240h], 0
0x1400b23a6  mov     rcx, [rdi+21C8h]
0x1400b23ad  mov     edx, 90h
0x1400b23b2  call    VsmmPhuStorepSerializationChargeDecrease
0x1400b23b7  jmp     loc_1400B247B
0x1400b23bc  mov     rbx, [rcx+288h]
0x1400b23c3  lea     r8, [rdx+40h]
0x1400b23c7  mov     qword ptr [rcx+288h], 0FFFFFFFFFFFFFFFFh
0x1400b23d2  mov     al, [rdx+31h]
0x1400b23d5  mov     [rdx+38h], rbx
0x1400b23d9  mov     cl, al
0x1400b23db  xor     cl, [rdi+2239h]
0x1400b23e1  and     cl, 1
0x1400b23e4  xor     cl, al
0x1400b23e6  mov     [rdx+31h], cl
0x1400b23e9  mov     cl, [rdi+223Ah]
0x1400b23ef  add     cl, cl
0x1400b23f1  mov     byte ptr [rdi+2239h], 0
0x1400b23f8  mov     al, [rdx+31h]
0x1400b23fb  xor     cl, al
0x1400b23fd  and     cl, 2
0x1400b2400  xor     cl, al
0x1400b2402  mov     [rdx+31h], cl
0x1400b2405  mov     byte ptr [rdi+223Ah], 0
0x1400b240c  mov     cl, [rdi+0C95h]
0x1400b2412  mov     al, [rdx+31h]
0x1400b2415  shl     cl, 2
0x1400b2418  xor     cl, al
0x1400b241a  and     cl, 4
0x1400b241d  xor     cl, al
0x1400b241f  mov     [rdx+31h], cl
0x1400b2422  mov     rcx, rdi
0x1400b2425  mov     rax, [rdi+2240h]
0x1400b242c  mov     [rdx+68h], rax
0x1400b2430  mov     qword ptr [rdi+2240h], 0
0x1400b243b  call    VsmmVsmGetPartitionConfig
0x1400b2440  mov     r8, rbp
0x1400b2443  mov     byte ptr [rbp+30h], 1
0x1400b2447  xor     edx, edx
0x1400b2449  mov     rcx, rbx
0x1400b244c  call    cs:__imp_WinHvSetInterceptRoutine
0x1400b2453  nop     dword ptr [rax+rax+00h]
0x1400b2458  mov     r8, rbp
0x1400b245b  xor     edx, edx
0x1400b245d  mov     rcx, rbx
0x1400b2460  call    cs:__imp_WinHvSetLowMemoryPolicyRoutine
0x1400b2467  nop     dword ptr [rax+rax+00h]
0x1400b246c  mov     rcx, rbx
0x1400b246f  call    cs:__imp_WinHvUnlinkPreExistingPartition
0x1400b2476  nop     dword ptr [rax+rax+00h]
0x1400b247b  mov     byte ptr [rdi+2238h], 0
0x1400b2482  mov     rbx, [rsp+38h+arg_0]
0x1400b2487  mov     rbp, [rsp+38h+arg_8]
0x1400b248c  add     rsp, 30h
0x1400b2490  pop     rdi
0x1400b2491  retn
```
