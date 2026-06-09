# CSmHashTable<CMcCoClients::Client,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)

- ea: `0x18000c230`
- end: `0x18000c28e`
- name: `?EnumRemoveAt@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CMcCoClients@@AEAU_SMHTPOS@@@Z`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b430`
- `0x18000bdd4`

## callees

- `0x18000c230`
- `0x18000c2f0`
- `0x18000c394`

## pseudocode

```c
__int64 __fastcall CSmHashTable<CMcCoClients::Client,CNoLock,113>::EnumRemoveAt(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi

  v4 = CList<CMcCoClients::Client,CNoLock>::DeleteAt(
         a1 + 8 * (*(unsigned int *)(a2 + 4) + 2LL * *(unsigned int *)(a2 + 4) + 1),
         a2 + 8);
  if ( !*(_QWORD *)(a2 + 8) )
    CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(a1, a2);
  --*(_DWORD *)(a1 + 2720);
  return v4;
}

```

## disassembly

```asm
0x18000c230  mov     [rsp+arg_0], rbx
0x18000c235  mov     [rsp+arg_8], rsi
0x18000c23a  push    rdi
0x18000c23b  sub     rsp, 20h
0x18000c23f  mov     eax, [rdx+4]
0x18000c242  mov     rdi, rdx
0x18000c245  mov     rbx, rcx
0x18000c248  add     rdx, 8
0x18000c24c  lea     r8, ds:1[rax*2]
0x18000c254  add     r8, rax
0x18000c257  lea     rcx, [rcx+r8*8]
0x18000c25b  call    ?DeleteAt@?$CList@UClient@CMcCoClients@@VCNoLock@@@@QEAAPEAUClient@CMcCoClients@@AEAPEAX@Z; CList<CMcCoClients::Client,CNoLock>::DeleteAt(void * &)
0x18000c260  cmp     qword ptr [rdi+8], 0
0x18000c265  mov     rsi, rax
0x18000c268  jnz     short loc_18000C275
0x18000c26a  mov     rdx, rdi
0x18000c26d  mov     rcx, rbx
0x18000c270  call    ?MoveNext@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x18000c275  dec     dword ptr [rbx+0AA0h]
0x18000c27b  mov     rax, rsi
0x18000c27e  mov     rbx, [rsp+28h+arg_0]
0x18000c283  mov     rsi, [rsp+28h+arg_8]
0x18000c288  add     rsp, 20h
0x18000c28c  pop     rdi
0x18000c28d  retn
```
