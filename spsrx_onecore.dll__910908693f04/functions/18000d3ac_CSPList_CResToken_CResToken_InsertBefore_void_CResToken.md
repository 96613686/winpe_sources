# CSPList<CResToken *,CResToken *>::InsertBefore(void *,CResToken *)

- ea: `0x18000d3ac`
- end: `0x18000d42b`
- name: `?InsertBefore@?$CSPList@PEAUCResToken@@PEAU1@@@QEAAPEAXPEAXPEAUCResToken@@@Z`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dd00`

## callees

- `0x18000d3ac`
- `0x18000db8c`

## pseudocode

```c
__int64 __fastcall CSPList<CResToken *,CResToken *>::InsertBefore(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 result; // rax
  __int64 *v7; // rcx

  if ( a2 )
  {
    result = CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(a1, *(_QWORD *)(a2 + 8), a2);
    if ( result )
    {
      *(_QWORD *)(result + 16) = a3;
      v7 = *(__int64 **)(a2 + 8);
      if ( v7 )
        *v7 = result;
      else
        *a1 = result;
      *(_QWORD *)(a2 + 8) = result;
    }
  }
  else
  {
    result = CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(a1, 0, *a1);
    if ( result )
    {
      *(_QWORD *)(result + 16) = a3;
      if ( *a1 )
        *(_QWORD *)(*a1 + 8) = result;
      else
        a1[1] = result;
      *a1 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d3ac  mov     [rsp+arg_0], rbx
0x18000d3b1  mov     [rsp+arg_8], rsi
0x18000d3b6  push    rdi
0x18000d3b7  sub     rsp, 20h
0x18000d3bb  mov     rsi, r8
0x18000d3be  mov     rdi, rdx
0x18000d3c1  mov     rbx, rcx
0x18000d3c4  test    rdx, rdx
0x18000d3c7  jnz     short loc_18000D3F1
0x18000d3c9  mov     r8, [rcx]
0x18000d3cc  call    ?NewNode@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z; CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *)
0x18000d3d1  test    rax, rax
0x18000d3d4  jz      short loc_18000D41B
0x18000d3d6  mov     [rax+10h], rsi
0x18000d3da  mov     rcx, [rbx]
0x18000d3dd  test    rcx, rcx
0x18000d3e0  jz      short loc_18000D3E8
0x18000d3e2  mov     [rcx+8], rax
0x18000d3e6  jmp     short loc_18000D3EC
0x18000d3e8  mov     [rbx+8], rax
0x18000d3ec  mov     [rbx], rax
0x18000d3ef  jmp     short loc_18000D41B
0x18000d3f1  mov     rdx, [rdx+8]
0x18000d3f5  mov     r8, rdi
0x18000d3f8  call    ?NewNode@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z; CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *)
0x18000d3fd  test    rax, rax
0x18000d400  jz      short loc_18000D41B
0x18000d402  mov     [rax+10h], rsi
0x18000d406  mov     rcx, [rdi+8]
0x18000d40a  test    rcx, rcx
0x18000d40d  jz      short loc_18000D414
0x18000d40f  mov     [rcx], rax
0x18000d412  jmp     short loc_18000D417
0x18000d414  mov     [rbx], rax
0x18000d417  mov     [rdi+8], rax
0x18000d41b  mov     rbx, [rsp+28h+arg_0]
0x18000d420  mov     rsi, [rsp+28h+arg_8]
0x18000d425  add     rsp, 20h
0x18000d429  pop     rdi
0x18000d42a  retn
```
