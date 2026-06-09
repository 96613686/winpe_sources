# OncRpcConnMgrpWskCompletionContextAlloc

- ea: `0x14000d828`
- end: `0x14000d88e`
- name: `OncRpcConnMgrpWskCompletionContextAlloc`
- size: `102`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400077ac`
- `0x1400079b4`
- `0x140007d58`
- `0x14000df80`

## callees

- `0x14000d828`

## import_xrefs

- `ntoskrnl!IoAllocateIrp` at `0x14000d857`
- `ntoskrnl!IoAllocateIrp` at `0x14000d857`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d871`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d871`
- `ntoskrnl!ExAllocatePool2` at `0x14000d83b`
- `ntoskrnl!ExAllocatePool2` at `0x14000d83b`

## pseudocode

```c
_QWORD *OncRpcConnMgrpWskCompletionContextAlloc()
{
  _QWORD *Pool2; // rbx
  PIRP Irp; // rax

  Pool2 = (_QWORD *)ExAllocatePool2(64, 64, 1128486738);
  if ( Pool2 )
  {
    Irp = IoAllocateIrp(StackSize, 0);
    Pool2[5] = Irp;
    if ( Irp )
    {
      *(_DWORD *)Pool2 |= 1u;
    }
    else
    {
      ExFreePoolWithTag(Pool2, 0);
      return 0;
    }
  }
  return Pool2;
}

```

## disassembly

```asm
0x14000d828  push    rbx
0x14000d82a  sub     rsp, 20h
0x14000d82e  mov     ecx, 40h ; '@'
0x14000d833  mov     r8d, 43435752h
0x14000d839  mov     edx, ecx
0x14000d83b  call    cs:__imp_ExAllocatePool2
0x14000d842  nop     dword ptr [rax+rax+00h]
0x14000d847  mov     rbx, rax
0x14000d84a  test    rax, rax
0x14000d84d  jz      short loc_14000D884
0x14000d84f  mov     cl, cs:StackSize; StackSize
0x14000d855  xor     edx, edx; ChargeQuota
0x14000d857  call    cs:__imp_IoAllocateIrp
0x14000d85e  nop     dword ptr [rax+rax+00h]
0x14000d863  mov     [rbx+28h], rax
0x14000d867  test    rax, rax
0x14000d86a  jnz     short loc_14000D881
0x14000d86c  xor     edx, edx; Tag
0x14000d86e  mov     rcx, rbx; P
0x14000d871  call    cs:__imp_ExFreePoolWithTag
0x14000d878  nop     dword ptr [rax+rax+00h]
0x14000d87d  xor     ebx, ebx
0x14000d87f  jmp     short loc_14000D884
0x14000d881  or      dword ptr [rbx], 1
0x14000d884  mov     rax, rbx
0x14000d887  add     rsp, 20h
0x14000d88b  pop     rbx
0x14000d88c  retn
```
