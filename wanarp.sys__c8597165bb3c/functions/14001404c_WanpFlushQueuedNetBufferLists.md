# WanpFlushQueuedNetBufferLists

- ea: `0x14001404c`
- end: `0x1400140de`
- name: `WanpFlushQueuedNetBufferLists`
- size: `146`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140010448`
- `0x1400110bc`
- `0x1400129e4`
- `0x140013df4`

## callees

- `0x14001404c`

## import_xrefs

- `NETIO!NetioAdvanceNetBufferList` at `0x140014091`
- `NETIO!NetioAdvanceNetBufferList` at `0x140014091`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400140b5`
- `NETIO!NetioDereferenceNetBufferListChain` at `0x1400140b5`
- `NDIS!NdisFreeNetBufferListContext` at `0x14001407d`
- `NDIS!NdisFreeNetBufferListContext` at `0x14001407d`

## pseudocode

```c
__int64 __fastcall WanpFlushQueuedNetBufferLists(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  _QWORD *v3; // rbx
  struct _NET_BUFFER_LIST *Alignment; // rdi

  v2 = *(_QWORD *)((-(__int64)((_BYTE)a2 != 0) & 0xFFFFFFFFFFFFFFF8uLL) + a1 + 176);
  v3 = (_QWORD *)(v2 + 120);
  Alignment = *(struct _NET_BUFFER_LIST **)(v2 + 120);
  while ( Alignment )
  {
    NdisFreeNetBufferListContext(Alignment, 8u);
    NetioAdvanceNetBufferList(Alignment, 14);
    Alignment = (struct _NET_BUFFER_LIST *)Alignment->Link.Alignment;
    --*(_DWORD *)(v2 + 136);
  }
  if ( *v3 )
  {
    LOBYTE(a2) = 1;
    NetioDereferenceNetBufferListChain(*v3, a2);
    *v3 = 0;
    *(_QWORD *)(v2 + 128) = v3;
  }
  return 0;
}

```

## disassembly

```asm
0x14001404c  mov     [rsp+arg_0], rbx
0x140014051  mov     [rsp+arg_8], rsi
0x140014056  push    rdi
0x140014057  sub     rsp, 20h
0x14001405b  neg     dl
0x14001405d  sbb     rax, rax
0x140014060  and     rax, 0FFFFFFFFFFFFFFF8h
0x140014064  mov     rsi, [rax+rcx+0B0h]
0x14001406c  lea     rbx, [rsi+78h]
0x140014070  mov     rdi, [rbx]
0x140014073  jmp     short loc_1400140A6
0x140014075  mov     edx, 8; ContextSize
0x14001407a  mov     rcx, rdi; NetBufferList
0x14001407d  call    cs:__imp_NdisFreeNetBufferListContext
0x140014084  nop     dword ptr [rax+rax+00h]
0x140014089  mov     edx, 0Eh
0x14001408e  mov     rcx, rdi
0x140014091  call    cs:__imp_NetioAdvanceNetBufferList
0x140014098  nop     dword ptr [rax+rax+00h]
0x14001409d  mov     rdi, [rdi]
0x1400140a0  dec     dword ptr [rsi+88h]
0x1400140a6  test    rdi, rdi
0x1400140a9  jnz     short loc_140014075
0x1400140ab  mov     rcx, [rbx]
0x1400140ae  test    rcx, rcx
0x1400140b1  jz      short loc_1400140CB
0x1400140b3  mov     dl, 1
0x1400140b5  call    cs:__imp_NetioDereferenceNetBufferListChain
0x1400140bc  nop     dword ptr [rax+rax+00h]
0x1400140c1  mov     [rbx], rdi
0x1400140c4  mov     [rsi+80h], rbx
0x1400140cb  mov     rbx, [rsp+28h+arg_0]
0x1400140d0  xor     eax, eax
0x1400140d2  mov     rsi, [rsp+28h+arg_8]
0x1400140d7  add     rsp, 20h
0x1400140db  pop     rdi
0x1400140dc  retn
```
