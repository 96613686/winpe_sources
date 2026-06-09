# OncRpcBufMgrGetNextBufferDescriptor

- ea: `0x140001340`
- end: `0x140001363`
- name: `OncRpcBufMgrGetNextBufferDescriptor`
- size: `35`
- prototype: ``
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140001458`
- `0x140001bf0`
- `0x140001cac`
- `0x140001de4`
- `0x140001e90`
- `0x140001ef0`
- `0x140004558`
- `0x1400059f8`
- `0x1400085c0`
- `0x14000df80`
- `0x14001530c`
- `0x140015408`

## callees

- `0x140001340`

## pseudocode

```c
__int64 __fastcall OncRpcBufMgrGetNextBufferDescriptor(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rdx

  if ( !a2 )
    return 0;
  v2 = a2 + 24;
  v3 = *(_QWORD *)(a2 + 24);
  if ( v3 == v2 || v3 == a1 + 24 )
    return 0;
  else
    return v3 - 24;
}

```

## disassembly

```asm
0x140001340  test    rdx, rdx
0x140001343  jz      short loc_140001360
0x140001345  lea     rax, [rdx+18h]
0x140001349  mov     rdx, [rax]
0x14000134c  cmp     rdx, rax
0x14000134f  jz      short loc_140001360
0x140001351  lea     rax, [rcx+18h]
0x140001355  cmp     rdx, rax
0x140001358  jz      short loc_140001360
0x14000135a  lea     rax, [rdx-18h]
0x14000135e  retn
0x140001360  xor     eax, eax
0x140001362  retn
```
