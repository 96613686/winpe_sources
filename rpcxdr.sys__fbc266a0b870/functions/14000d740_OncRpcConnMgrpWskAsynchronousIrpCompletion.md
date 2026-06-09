# OncRpcConnMgrpWskAsynchronousIrpCompletion

- ea: `0x14000d740`
- end: `0x14000d79c`
- name: `OncRpcConnMgrpWskAsynchronousIrpCompletion`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d740`
- `0x140015680`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14000d76e`
- `ntoskrnl!IoFreeIrp` at `0x14000d76e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d77f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d77f`

## pseudocode

```c
__int64 __fastcall OncRpcConnMgrpWskAsynchronousIrpCompletion(__int64 a1, __int64 a2, void *a3)
{
  void (__fastcall *v4)(void *); // rax
  char v5; // di

  v4 = (void (__fastcall *)(void *))*((_QWORD *)a3 + 6);
  v5 = *(_BYTE *)a3 & 1;
  if ( v4 )
    v4(a3);
  if ( v5 )
  {
    IoFreeIrp(*((PIRP *)a3 + 5));
    ExFreePoolWithTag(a3, 0);
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14000d740  mov     [rsp+arg_0], rbx
0x14000d745  push    rdi
0x14000d746  sub     rsp, 20h
0x14000d74a  mov     dil, [r8]
0x14000d74d  mov     rbx, r8
0x14000d750  mov     rax, [r8+30h]
0x14000d754  and     dil, 1
0x14000d758  test    rax, rax
0x14000d75b  jz      short loc_14000D765
0x14000d75d  mov     rcx, rbx
0x14000d760  call    _guard_dispatch_icall
0x14000d765  test    dil, dil
0x14000d768  jz      short loc_14000D78B
0x14000d76a  mov     rcx, [rbx+28h]; Irp
0x14000d76e  call    cs:__imp_IoFreeIrp
0x14000d775  nop     dword ptr [rax+rax+00h]
0x14000d77a  xor     edx, edx; Tag
0x14000d77c  mov     rcx, rbx; P
0x14000d77f  call    cs:__imp_ExFreePoolWithTag
0x14000d786  nop     dword ptr [rax+rax+00h]
0x14000d78b  mov     rbx, [rsp+28h+arg_0]
0x14000d790  mov     eax, 0C0000016h
0x14000d795  add     rsp, 20h
0x14000d799  pop     rdi
0x14000d79a  retn
```
