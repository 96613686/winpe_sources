# CSmHashTable<CTpSrvClients::Client,CNoLock,113>::EnumRemoveAt(_SMHTPOS &)

- ea: `0x180010884`
- end: `0x1800108e2`
- name: `?EnumRemoveAt@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@QEAAPEAUClient@CTpSrvClients@@AEAU_SMHTPOS@@@Z`
- size: `94`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000f5cc`
- `0x18001038c`
- `0x18001050c`

## callees

- `0x180010884`
- `0x180010948`
- `0x180010ac8`

## pseudocode

```c
__int64 __fastcall CSmHashTable<CTpSrvClients::Client,CNoLock,113>::EnumRemoveAt(__int64 a1, __int64 a2)
{
  __int64 v4; // rsi

  v4 = CList<CTpSrvClients::Client,CNoLock>::DeleteAt(
         a1 + 8 * (*(unsigned int *)(a2 + 4) + 2LL * *(unsigned int *)(a2 + 4) + 1),
         a2 + 8);
  if ( !*(_QWORD *)(a2 + 8) )
    CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(a1, a2);
  --*(_DWORD *)(a1 + 2720);
  return v4;
}

```

## disassembly

```asm
0x180010884  mov     [rsp+arg_0], rbx
0x180010889  mov     [rsp+arg_8], rsi
0x18001088e  push    rdi
0x18001088f  sub     rsp, 20h
0x180010893  mov     eax, [rdx+4]
0x180010896  mov     rdi, rdx
0x180010899  mov     rbx, rcx
0x18001089c  add     rdx, 8
0x1800108a0  lea     r8, ds:1[rax*2]
0x1800108a8  add     r8, rax
0x1800108ab  lea     rcx, [rcx+r8*8]
0x1800108af  call    ?DeleteAt@?$CList@UClient@CTpSrvClients@@VCNoLock@@@@QEAAPEAUClient@CTpSrvClients@@AEAPEAX@Z; CList<CTpSrvClients::Client,CNoLock>::DeleteAt(void * &)
0x1800108b4  cmp     qword ptr [rdi+8], 0
0x1800108b9  mov     rsi, rax
0x1800108bc  jnz     short loc_1800108C9
0x1800108be  mov     rdx, rdi
0x1800108c1  mov     rcx, rbx
0x1800108c4  call    ?MoveNext@?$CSmHashTable@UClient@CTpSrvClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z; CSmHashTable<CTpSrvClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)
0x1800108c9  dec     dword ptr [rbx+0AA0h]
0x1800108cf  mov     rax, rsi
0x1800108d2  mov     rbx, [rsp+28h+arg_0]
0x1800108d7  mov     rsi, [rsp+28h+arg_8]
0x1800108dc  add     rsp, 20h
0x1800108e0  pop     rdi
0x1800108e1  retn
```
