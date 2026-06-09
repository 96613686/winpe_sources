# OncRpcAllocateIndependentDescriptor

- ea: `0x140006880`
- end: `0x1400068bd`
- name: `OncRpcAllocateIndependentDescriptor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1400015ec`
- `0x140006880`

## pseudocode

```c
__int64 __fastcall OncRpcAllocateIndependentDescriptor(
        __int64 *a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5)
{
  __int64 result; // rax
  __int64 v7; // [rsp+20h] [rbp-18h]

  result = OncRpcBufMgrpAllocate(0, a1, a2, a3, v7, a5);
  if ( (int)result >= 0 )
  {
    *(_DWORD *)(*a1 + 80) |= 0x80u;
    *(_DWORD *)(*a1 + 80) |= 0x40u;
  }
  return result;
}

```

## disassembly

```asm
0x140006880  push    rbx
0x140006882  sub     rsp, 30h
0x140006886  mov     rax, [rsp+38h+arg_20]
0x14000688b  mov     r9d, r8d
0x14000688e  mov     r8d, edx
0x140006891  mov     [rsp+38h+var_10], rax
0x140006896  mov     rdx, rcx
0x140006899  mov     rbx, rcx
0x14000689c  xor     ecx, ecx
0x14000689e  call    OncRpcBufMgrpAllocate
0x1400068a3  test    eax, eax
0x1400068a5  js      short loc_1400068B6
0x1400068a7  mov     rdx, [rbx]
0x1400068aa  bts     dword ptr [rdx+50h], 7
0x1400068af  mov     rcx, [rbx]
0x1400068b2  or      dword ptr [rcx+50h], 40h
0x1400068b6  add     rsp, 30h
0x1400068ba  pop     rbx
0x1400068bb  retn
```
