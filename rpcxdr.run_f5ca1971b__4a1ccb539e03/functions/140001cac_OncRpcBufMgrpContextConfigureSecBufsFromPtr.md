# OncRpcBufMgrpContextConfigureSecBufsFromPtr

- ea: `0x140001cac`
- end: `0x140001d58`
- name: `OncRpcBufMgrpContextConfigureSecBufsFromPtr`
- size: `172`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140009540`
- `0x14000aac4`
- `0x14000cb78`

## callees

- `0x140001340`
- `0x140001cac`
- `0x140001d60`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrpContextConfigureSecBufsFromPtr(
        __int64 a1,
        unsigned __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        char a6)
{
  unsigned int v7; // r15d
  char v11; // r14
  __int64 result; // rax
  __int64 v13; // rdx
  int v14; // ecx
  unsigned int v15; // ecx
  unsigned __int64 v16; // r8

  v7 = 0;
  v11 = 1;
  for ( result = (__int64)OncRpcBufMgrpContextGetDescriptorFromPtr(a1, a2, a6);
        ;
        result = OncRpcBufMgrGetNextBufferDescriptor(a1, v13) )
  {
    v13 = result;
    if ( !a3 )
      break;
    if ( v11 )
    {
      if ( a6 )
        v14 = *(_DWORD *)(result + 56) + *(_DWORD *)(result + 76);
      else
        v14 = *(_DWORD *)(result + 64);
      v15 = v14 - a2;
      v16 = a2;
      v11 = 0;
    }
    else
    {
      if ( a6 )
        v15 = *(_DWORD *)(result + 76);
      else
        v15 = *(_DWORD *)(result + 64) - *(_DWORD *)(result + 56);
      v16 = *(_QWORD *)(result + 56);
    }
    result = 2LL * v7;
    *(_DWORD *)(a4 + 8 * result + 4) = 1;
    *(_QWORD *)(a4 + 8 * result + 8) = v16;
    if ( a3 <= v15 )
    {
      *(_DWORD *)(a4 + 16LL * v7) = a3;
      return result;
    }
    *(_DWORD *)(a4 + 16LL * v7) = v15;
    a3 -= v15;
    ++v7;
  }
  return result;
}

```

## disassembly

```asm
0x140001cac  push    rbx
0x140001cae  push    rsi
0x140001caf  push    rdi
0x140001cb0  push    r12
0x140001cb2  push    r14
0x140001cb4  push    r15
0x140001cb6  sub     rsp, 28h
0x140001cba  mov     ebx, r8d
0x140001cbd  xor     r15d, r15d
0x140001cc0  mov     r8b, [rsp+58h+arg_28]
0x140001cc8  mov     rdi, r9
0x140001ccb  mov     rsi, rdx
0x140001cce  mov     r12, rcx
0x140001cd1  mov     r14b, 1
0x140001cd4  call    OncRpcBufMgrpContextGetDescriptorFromPtr
0x140001cd9  mov     rdx, rax
0x140001cdc  test    ebx, ebx
0x140001cde  jz      short loc_140001D49
0x140001ce0  test    r14b, r14b
0x140001ce3  jz      short loc_140001D04
0x140001ce5  cmp     [rsp+58h+arg_28], 0
0x140001ced  jz      short loc_140001CF7
0x140001cef  mov     ecx, [rax+4Ch]
0x140001cf2  add     ecx, [rax+38h]
0x140001cf5  jmp     short loc_140001CFA
0x140001cf7  mov     ecx, [rdx+40h]
0x140001cfa  sub     ecx, esi
0x140001cfc  mov     r8, rsi
0x140001cff  xor     r14b, r14b
0x140001d02  jmp     short loc_140001D1D
0x140001d04  cmp     [rsp+58h+arg_28], 0
0x140001d0c  jz      short loc_140001D13
0x140001d0e  mov     ecx, [rdx+4Ch]
0x140001d11  jmp     short loc_140001D19
0x140001d13  mov     ecx, [rdx+40h]
0x140001d16  sub     ecx, [rdx+38h]
0x140001d19  mov     r8, [rdx+38h]
0x140001d1d  mov     eax, r15d
0x140001d20  add     rax, rax
0x140001d23  mov     dword ptr [rdi+rax*8+4], 1
0x140001d2b  mov     [rdi+rax*8+8], r8
0x140001d30  cmp     ebx, ecx
0x140001d32  jbe     short loc_140001D46
0x140001d34  mov     [rdi+rax*8], ecx
0x140001d37  sub     ebx, ecx
0x140001d39  mov     rcx, r12
0x140001d3c  inc     r15d
0x140001d3f  call    OncRpcBufMgrGetNextBufferDescriptor
0x140001d44  jmp     short loc_140001CD9
0x140001d46  mov     [rdi+rax*8], ebx
0x140001d49  add     rsp, 28h
0x140001d4d  pop     r15
0x140001d4f  pop     r14
0x140001d51  pop     r12
0x140001d53  pop     rdi
0x140001d54  pop     rsi
0x140001d55  pop     rbx
0x140001d56  retn
```
