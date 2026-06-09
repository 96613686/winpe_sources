# DvRemoveWorkQueue

- ea: `0x140016e8c`
- end: `0x140016ecc`
- name: `DvRemoveWorkQueue`
- size: `64`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000ff34`
- `0x14002ea90`

## callees

- `0x140016e8c`
- `0x140016ed4`

## pseudocode

```c
__int64 __fastcall DvRemoveWorkQueue(signed __int64 *a1)
{
  signed __int64 v1; // rax
  unsigned __int64 v2; // r9
  signed __int64 v3; // rdx

  _m_prefetchw(a1);
  v1 = *a1;
  while ( (v1 & 2) == 0 )
  {
    v2 = v1 & 0xFFFFFFFFFFFFFFFEuLL;
    v3 = v1;
    v1 = _InterlockedCompareExchange64(a1, (v1 & 0xFFFFFFFFFFFFFFFEuLL) != 0, v1);
    if ( v1 == v3 )
      return v2;
  }
  return DvpRemoveWorkQueueRunningDown(a1);
}

```

## disassembly

```asm
0x140016e8c  sub     rsp, 28h
0x140016e90  mov     r8, rcx
0x140016e93  prefetchw byte ptr [rcx]
0x140016e96  mov     rax, [rcx]
0x140016e99  test    al, 2
0x140016e9b  jnz     short loc_140016EBE
0x140016e9d  mov     r9, rax
0x140016ea0  mov     ecx, 0
0x140016ea5  and     r9, 0FFFFFFFFFFFFFFFEh
0x140016ea9  mov     rdx, rax
0x140016eac  setnz   cl
0x140016eaf  lock cmpxchg [r8], rcx
0x140016eb4  cmp     rax, rdx
0x140016eb7  jnz     short loc_140016E99
0x140016eb9  mov     rax, r9
0x140016ebc  jmp     short loc_140016EC6
0x140016ebe  mov     rcx, r8
0x140016ec1  call    DvpRemoveWorkQueueRunningDown
0x140016ec6  add     rsp, 28h
0x140016eca  retn
```
