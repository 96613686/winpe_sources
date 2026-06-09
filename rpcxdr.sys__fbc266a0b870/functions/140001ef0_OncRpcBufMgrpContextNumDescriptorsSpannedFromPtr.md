# OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr

- ea: `0x140001ef0`
- end: `0x140001f6f`
- name: `OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr`
- size: `127`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, char)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140009540`
- `0x14000a814`
- `0x14000aac4`
- `0x14000cb78`

## callees

- `0x140001340`
- `0x140001d60`
- `0x140001ef0`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrpContextNumDescriptorsSpannedFromPtr(__int64 a1, __int64 a2, __int64 a3, char a4)
{
  unsigned int v4; // ebx
  unsigned int v5; // edi
  char v6; // bp
  int v8; // r14d
  _DWORD *i; // rax
  int v11; // ecx
  unsigned int v12; // ecx

  v4 = a3;
  v5 = 1;
  LOBYTE(a3) = a4;
  v6 = 1;
  v8 = a2;
  for ( i = (_DWORD *)OncRpcBufMgrpContextGetDescriptorFromPtr(a1, a2, a3);
        v4;
        i = (_DWORD *)OncRpcBufMgrGetNextBufferDescriptor(a1, i) )
  {
    if ( v6 )
    {
      v11 = a4 ? i[14] + i[19] : i[16];
      v12 = v11 - v8;
      v6 = 0;
    }
    else
    {
      v12 = a4 ? i[19] : i[16] - i[14];
    }
    if ( v4 <= v12 )
      break;
    v4 -= v12;
    ++v5;
  }
  return v5;
}

```

## disassembly

```asm
0x140001ef0  push    rbx
0x140001ef2  push    rbp
0x140001ef3  push    rsi
0x140001ef4  push    rdi
0x140001ef5  push    r14
0x140001ef7  push    r15
0x140001ef9  sub     rsp, 28h
0x140001efd  mov     ebx, r8d
0x140001f00  mov     edi, 1
0x140001f05  mov     r8b, r9b
0x140001f08  mov     bpl, dil
0x140001f0b  mov     sil, r9b
0x140001f0e  mov     r14, rdx
0x140001f11  mov     r15, rcx
0x140001f14  call    OncRpcBufMgrpContextGetDescriptorFromPtr
0x140001f19  jmp     short loc_140001F58
0x140001f1b  test    bpl, bpl
0x140001f1e  jz      short loc_140001F38
0x140001f20  test    sil, sil
0x140001f23  jz      short loc_140001F2D
0x140001f25  mov     ecx, [rdx+4Ch]
0x140001f28  add     ecx, [rdx+38h]
0x140001f2b  jmp     short loc_140001F30
0x140001f2d  mov     ecx, [rdx+40h]
0x140001f30  sub     ecx, r14d
0x140001f33  xor     bpl, bpl
0x140001f36  jmp     short loc_140001F48
0x140001f38  test    sil, sil
0x140001f3b  jz      short loc_140001F42
0x140001f3d  mov     ecx, [rdx+4Ch]
0x140001f40  jmp     short loc_140001F48
0x140001f42  mov     ecx, [rdx+40h]
0x140001f45  sub     ecx, [rdx+38h]
0x140001f48  cmp     ebx, ecx
0x140001f4a  jbe     short loc_140001F5F
0x140001f4c  sub     ebx, ecx
0x140001f4e  inc     edi
0x140001f50  mov     rcx, r15
0x140001f53  call    OncRpcBufMgrGetNextBufferDescriptor
0x140001f58  mov     rdx, rax
0x140001f5b  test    ebx, ebx
0x140001f5d  jnz     short loc_140001F1B
0x140001f5f  mov     eax, edi
0x140001f61  add     rsp, 28h
0x140001f65  pop     r15
0x140001f67  pop     r14
0x140001f69  pop     rdi
0x140001f6a  pop     rsi
0x140001f6b  pop     rbp
0x140001f6c  pop     rbx
0x140001f6d  retn
```
