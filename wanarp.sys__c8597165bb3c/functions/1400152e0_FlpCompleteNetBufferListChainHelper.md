# FlpCompleteNetBufferListChainHelper

- ea: `0x1400152e0`
- end: `0x14001532e`
- name: `FlpCompleteNetBufferListChainHelper`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140015100`

## callees

- `0x14000f728`
- `0x1400152e0`
- `0x140015340`

## pseudocode

```c
void __fastcall FlpCompleteNetBufferListChainHelper(__int64 a1, struct _NET_BUFFER_LIST *a2, int a3)
{
  PVOID v3; // rdi

  v3 = a2->ProtocolReserved[3];
  FlpCompleteNdisNetBufferListChain(a2);
  while ( a3 )
  {
    --a3;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3 + 24, 0xFFFFFFFF) == 1 )
      WanpDeleteConnEntry((char *)v3);
  }
}

```

## disassembly

```asm
0x1400152e0  mov     [rsp+arg_0], rbx
0x1400152e5  push    rdi
0x1400152e6  sub     rsp, 20h
0x1400152ea  mov     rdi, [rdx+58h]
0x1400152ee  mov     ebx, r8d
0x1400152f1  mov     rcx, rdx; NetBufferLists
0x1400152f4  movzx   r8d, r9b
0x1400152f8  mov     edx, ebx
0x1400152fa  call    FlpCompleteNdisNetBufferListChain
0x1400152ff  test    ebx, ebx
0x140015301  jz      short loc_140015318
0x140015303  dec     ebx
0x140015305  mov     eax, 0FFFFFFFFh
0x14001530a  lock xadd [rdi+60h], eax
0x14001530f  cmp     eax, 1
0x140015312  jz      short loc_140015324
0x140015314  test    ebx, ebx
0x140015316  jnz     short loc_140015303
0x140015318  mov     rbx, [rsp+28h+arg_0]
0x14001531d  add     rsp, 20h
0x140015321  pop     rdi
0x140015322  retn
0x140015324  mov     rcx, rdi; Entry
0x140015327  call    WanpDeleteConnEntry
0x14001532c  jmp     short loc_140015314
```
