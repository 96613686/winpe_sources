# WanpDeleteAdapter

- ea: `0x14000e280`
- end: `0x14000e307`
- name: `WanpDeleteAdapter`
- size: `135`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400019c0`
- `0x140002510`
- `0x14000e310`
- `0x14000e6f8`
- `0x14000e89c`
- `0x14000f094`
- `0x14000f9c8`
- `0x14000fdc4`
- `0x140010448`
- `0x1400120fc`
- `0x1400124bc`
- `0x140012e3c`
- `0x140013df4`
- `0x140015f60`
- `0x140017550`

## callees

- `0x14000e280`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2f4`
- `NDIS!NdisIfDeregisterInterface` at `0x14000e2a5`
- `NDIS!NdisIfDeregisterInterface` at `0x14000e2a5`

## pseudocode

```c
void __fastcall WanpDeleteAdapter(PVOID P)
{
  NET_IFINDEX v2; // ecx

  if ( !_InterlockedCompareExchange((volatile signed __int32 *)P + 86, 1, 0) )
  {
    v2 = *((_DWORD *)P + 90);
    if ( v2 != -1 )
    {
      NdisIfDeregisterInterface(v2);
      *((_DWORD *)P + 90) = -1;
    }
    if ( *((_QWORD *)P + 21) )
      _InterlockedDecrement(&g_ModuleV4);
    if ( *((_QWORD *)P + 22) )
      _InterlockedDecrement(&g_ModuleV6);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 33, 0xFFFFFFFF) == 1 )
      ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14000e280  push    rbx
0x14000e282  sub     rsp, 20h
0x14000e286  mov     rbx, rcx
0x14000e289  xor     eax, eax
0x14000e28b  mov     ecx, 1
0x14000e290  lock cmpxchg [rbx+158h], ecx
0x14000e298  jnz     short loc_14000E300
0x14000e29a  mov     ecx, [rbx+168h]; ifIndex
0x14000e2a0  cmp     ecx, 0FFFFFFFFh
0x14000e2a3  jz      short loc_14000E2BB
0x14000e2a5  call    cs:__imp_NdisIfDeregisterInterface
0x14000e2ac  nop     dword ptr [rax+rax+00h]
0x14000e2b1  mov     dword ptr [rbx+168h], 0FFFFFFFFh
0x14000e2bb  cmp     qword ptr [rbx+0A8h], 0
0x14000e2c3  jz      short loc_14000E2CC
0x14000e2c5  lock dec cs:g_ModuleV4
0x14000e2cc  cmp     qword ptr [rbx+0B0h], 0
0x14000e2d4  jz      short loc_14000E2DD
0x14000e2d6  lock dec cs:g_ModuleV6
0x14000e2dd  mov     eax, 0FFFFFFFFh
0x14000e2e2  lock xadd [rbx+84h], eax
0x14000e2ea  cmp     eax, 1
0x14000e2ed  jnz     short loc_14000E300
0x14000e2ef  xor     edx, edx; Tag
0x14000e2f1  mov     rcx, rbx; P
0x14000e2f4  call    cs:__imp_ExFreePoolWithTag
0x14000e2fb  nop     dword ptr [rax+rax+00h]
0x14000e300  add     rsp, 20h
0x14000e304  pop     rbx
0x14000e305  retn
```
