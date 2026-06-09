# CSPList<CTnMultiResNode *,CTnMultiResNode *>::AddHead(CTnMultiResNode *)

- ea: `0x1800098e0`
- end: `0x180009923`
- name: `?AddHead@?$CSPList@PEAVCTnMultiResNode@@PEAV1@@@QEAAPEAXPEAVCTnMultiResNode@@@Z`
- size: `67`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009d0c`
- `0x18000a614`
- `0x18000bf40`
- `0x18000d434`

## callees

- `0x1800098e0`
- `0x18000db8c`

## pseudocode

```c
_QWORD *__fastcall CSPList<CTnMultiResNode *,CTnMultiResNode *>::AddHead(__int64 *a1, __int64 a2)
{
  _QWORD *result; // rax

  result = CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode((__int64)a1, 0, *a1);
  if ( result )
  {
    result[2] = a2;
    if ( *a1 )
      *(_QWORD *)(*a1 + 8) = result;
    else
      a1[1] = (__int64)result;
    *a1 = (__int64)result;
  }
  return result;
}

```

## disassembly

```asm
0x1800098e0  mov     [rsp+arg_0], rbx
0x1800098e5  push    rdi
0x1800098e6  sub     rsp, 20h
0x1800098ea  mov     r8, [rcx]
0x1800098ed  mov     rdi, rdx
0x1800098f0  xor     edx, edx
0x1800098f2  mov     rbx, rcx
0x1800098f5  call    ?NewNode@?$CSPList@PEAVCTnMultiResCursor@@PEAV1@@@IEAAPEAUCNode@1@PEAU21@0@Z; CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::NewNode(CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *,CSPList<CTnMultiResCursor *,CTnMultiResCursor *>::CNode *)
0x1800098fa  test    rax, rax
0x1800098fd  jz      short loc_180009918
0x1800098ff  mov     [rax+10h], rdi
0x180009903  mov     rcx, [rbx]
0x180009906  test    rcx, rcx
0x180009909  jz      short loc_180009911
0x18000990b  mov     [rcx+8], rax
0x18000990f  jmp     short loc_180009915
0x180009911  mov     [rbx+8], rax
0x180009915  mov     [rbx], rax
0x180009918  mov     rbx, [rsp+28h+arg_0]
0x18000991d  add     rsp, 20h
0x180009921  pop     rdi
0x180009922  retn
```
