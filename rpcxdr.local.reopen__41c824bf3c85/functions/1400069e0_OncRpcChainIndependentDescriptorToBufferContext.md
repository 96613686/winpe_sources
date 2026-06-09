# OncRpcChainIndependentDescriptorToBufferContext

- ea: `0x1400069e0`
- end: `0x140006a13`
- name: `OncRpcChainIndependentDescriptorToBufferContext`
- size: `51`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400069e0`

## pseudocode

```c
__int64 __fastcall OncRpcChainIndependentDescriptorToBufferContext(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  _QWORD *v3; // r8
  __int64 result; // rax

  *(_QWORD *)(a2 + 16) = a1;
  *(_QWORD *)(a1 + 40) = a2;
  v2 = a1 + 24;
  v3 = *(_QWORD **)(v2 + 8);
  if ( *v3 != v2 )
    __fastfail(3u);
  result = a2 + 24;
  *(_QWORD *)(a2 + 24) = v2;
  *(_QWORD *)(a2 + 32) = v3;
  *v3 = a2 + 24;
  *(_QWORD *)(v2 + 8) = a2 + 24;
  *(_DWORD *)(a2 + 80) &= ~0x40u;
  return result;
}

```

## disassembly

```asm
0x1400069e0  mov     [rdx+10h], rcx
0x1400069e4  mov     [rcx+28h], rdx
0x1400069e8  add     rcx, 18h
0x1400069ec  mov     r8, [rcx+8]
0x1400069f0  cmp     [r8], rcx
0x1400069f3  jz      short loc_1400069FC
0x1400069f5  mov     ecx, 3
0x1400069fa  int     29h; Win8: RtlFailFast(ecx)
0x1400069fc  lea     rax, [rdx+18h]
0x140006a00  mov     [rax], rcx
0x140006a03  mov     [rax+8], r8
0x140006a07  mov     [r8], rax
0x140006a0a  mov     [rcx+8], rax
0x140006a0e  and     dword ptr [rdx+50h], 0FFFFFFBFh
0x140006a12  retn
```
