# CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(CTnMultiResStringPackage::SStrCost *)

- ea: `0x180009c04`
- end: `0x180009c49`
- name: `?AddTail@?$CSPList@PEAUSStrCost@CTnMultiResStringPackage@@PEAU12@@@QEAAPEAXPEAUSStrCost@CTnMultiResStringPackage@@@Z`
- size: `69`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180009848`
- `0x180009930`
- `0x180009a44`
- `0x18000a14c`
- `0x18000a298`
- `0x18000a4c8`
- `0x18000a614`
- `0x18000aad0`
- `0x18000b208`
- `0x18000d1c0`
- `0x18000d348`
- `0x18000dc24`
- `0x18000dd00`

## callees

- `0x180009c04`
- `0x18000db8c`

## pseudocode

```c
__int64 __fastcall CSPList<CTnMultiResStringPackage::SStrCost *,CTnMultiResStringPackage::SStrCost *>::AddTail(
        __int64 *a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 *v5; // rcx

  result = CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(a1, a1[1], 0);
  if ( result )
  {
    *(_QWORD *)(result + 16) = a2;
    v5 = (__int64 *)a1[1];
    if ( v5 )
      *v5 = result;
    else
      *a1 = result;
    a1[1] = result;
  }
  return result;
}

```

## disassembly

```asm
0x180009c04  mov     [rsp+arg_0], rbx
0x180009c09  push    rdi
0x180009c0a  sub     rsp, 20h
0x180009c0e  mov     rdi, rdx
0x180009c11  xor     r8d, r8d
0x180009c14  mov     rdx, [rcx+8]
0x180009c18  mov     rbx, rcx
0x180009c1b  call    ?NewNode@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z; CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *)
0x180009c20  test    rax, rax
0x180009c23  jz      short loc_180009C3E
0x180009c25  mov     [rax+10h], rdi
0x180009c29  mov     rcx, [rbx+8]
0x180009c2d  test    rcx, rcx
0x180009c30  jz      short loc_180009C37
0x180009c32  mov     [rcx], rax
0x180009c35  jmp     short loc_180009C3A
0x180009c37  mov     [rbx], rax
0x180009c3a  mov     [rbx+8], rax
0x180009c3e  mov     rbx, [rsp+28h+arg_0]
0x180009c43  add     rsp, 20h
0x180009c47  pop     rdi
0x180009c48  retn
```
