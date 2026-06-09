# OncRpcBufMgrChainUserSuppliedBuffer

- ea: `0x140001100`
- end: `0x140001194`
- name: `OncRpcBufMgrChainUserSuppliedBuffer`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140006a20`
- `0x14000993c`
- `0x14000a814`
- `0x14000aac4`

## callees

- `0x140001100`
- `0x140001804`
- `0x1400020c0`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrChainUserSuppliedBuffer(__int64 a1, __int64 a2)
{
  __int64 DescriptorFromLLForUserSuppliedBuffer; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rax
  _QWORD *v6; // rdx
  _QWORD *v7; // rcx

  DescriptorFromLLForUserSuppliedBuffer = OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedBuffer(a1, a2);
  if ( DescriptorFromLLForUserSuppliedBuffer )
  {
    v5 = a1 + 24;
    v6 = *(_QWORD **)(a1 + 32);
    if ( *v6 != a1 + 24 )
      __fastfail(3u);
    *(_QWORD *)(DescriptorFromLLForUserSuppliedBuffer + 32) = v6;
    v4 = 0;
    v7 = (_QWORD *)(DescriptorFromLLForUserSuppliedBuffer + 24);
    *v7 = v5;
    *v6 = v7;
    *(_QWORD *)(v5 + 8) = v7;
  }
  else
  {
    v4 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids, 3221225626LL);
  }
  return v4;
}

```

## disassembly

```asm
0x140001100  push    rbx
0x140001102  sub     rsp, 30h
0x140001106  mov     rax, [rsp+38h+arg_28]
0x14000110b  mov     rbx, rcx
0x14000110e  mov     [rsp+38h+var_10], rax
0x140001113  mov     rax, [rsp+38h+arg_20]
0x140001118  mov     [rsp+38h+var_18], rax
0x14000111d  call    OncRpcBufMgrpAllocateDescriptorFromLLForUserSuppliedBuffer
0x140001122  mov     rcx, rax
0x140001125  test    rax, rax
0x140001128  jnz     short loc_140001163
0x14000112a  mov     ebx, 0C000009Ah
0x14000112f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001136  lea     rax, WPP_GLOBAL_Control
0x14000113d  cmp     rcx, rax
0x140001140  jz      short loc_14000118B
0x140001142  mov     eax, [rcx+2Ch]
0x140001145  test    al, 2
0x140001147  jz      short loc_14000118B
0x140001149  mov     rcx, [rcx+18h]
0x14000114d  lea     r8, WPP_bc787cf5db083b51efc6e85b805038bb_Traceguids
0x140001154  mov     edx, 0Ch
0x140001159  mov     r9d, ebx
0x14000115c  call    WPP_SF_d
0x140001161  jmp     short loc_14000118B
0x140001163  lea     rax, [rbx+18h]
0x140001167  mov     rdx, [rax+8]
0x14000116b  cmp     [rdx], rax
0x14000116e  jz      short loc_140001177
0x140001170  mov     ecx, 3
0x140001175  int     29h; Win8: RtlFailFast(ecx)
0x140001177  mov     [rcx+20h], rdx
0x14000117b  xor     ebx, ebx
0x14000117d  add     rcx, 18h
0x140001181  mov     [rcx], rax
0x140001184  mov     [rdx], rcx
0x140001187  mov     [rax+8], rcx
0x14000118b  mov     eax, ebx
0x14000118d  add     rsp, 30h
0x140001191  pop     rbx
0x140001192  retn
```
