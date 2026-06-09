# CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(void)

- ea: `0x180004cfc`
- end: `0x180004d3f`
- name: `?RemoveAll@?$CSPList@PEAVCAgreementElement@@PEAV1@@@QEAAXXZ`
- size: `67`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x1800091b8`
- `0x1800092d0`
- `0x180009344`
- `0x180009470`
- `0x18000a298`
- `0x18000a4aa`
- `0x18000a4b6`
- `0x18000aa9e`
- `0x18000aaaa`
- `0x18000ac31`
- `0x18000c0cc`
- `0x18000c465`
- `0x18000c77c`
- `0x18000c788`
- `0x18000d19b`
- `0x18000d8d4`
- `0x18000e06c`

## callees

- `0x180004cfc`
- `0x180004f5c`

## pseudocode

```c
void __fastcall CSPList<CAgreementElement *,CAgreementElement *>::RemoveAll(__int64 a1)
{
  CSPPlex *v2; // rcx

  *(_DWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)a1 = 0;
  v2 = *(CSPPlex **)(a1 + 32);
  if ( v2 )
  {
    CSPPlex::FreeDataChain(v2);
    *(_QWORD *)(a1 + 32) = 0;
  }
}

```

## disassembly

```asm
0x180004cfc  push    rbx
0x180004cfe  sub     rsp, 20h
0x180004d02  mov     rbx, rcx
0x180004d05  mov     dword ptr [rcx+10h], 0
0x180004d0c  mov     qword ptr [rcx+18h], 0
0x180004d14  mov     qword ptr [rcx+8], 0
0x180004d1c  mov     qword ptr [rcx], 0
0x180004d23  mov     rcx, [rcx+20h]; this
0x180004d27  test    rcx, rcx
0x180004d2a  jz      short loc_180004D39
0x180004d2c  call    ?FreeDataChain@CSPPlex@@QEAAXXZ; CSPPlex::FreeDataChain(void)
0x180004d31  mov     qword ptr [rbx+20h], 0
0x180004d39  add     rsp, 20h
0x180004d3d  pop     rbx
0x180004d3e  retn
```
