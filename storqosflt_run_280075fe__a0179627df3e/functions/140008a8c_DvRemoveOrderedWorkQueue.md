# DvRemoveOrderedWorkQueue

- ea: `0x140008a8c`
- end: `0x140008ae4`
- name: `DvRemoveOrderedWorkQueue`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001940`

## callees

- `0x140008a8c`
- `0x140008aec`

## pseudocode

```c
_QWORD *__fastcall DvRemoveOrderedWorkQueue(signed __int64 *a1)
{
  signed __int64 v1; // rax
  _QWORD *v2; // r8
  signed __int64 v3; // rdx
  _QWORD *result; // rax
  _QWORD *v5; // rcx

  _m_prefetchw(a1);
  v1 = *a1;
  while ( (v1 & 2) == 0 )
  {
    v2 = (_QWORD *)(v1 & 0xFFFFFFFFFFFFFFFEuLL);
    v3 = v1;
    v1 = _InterlockedCompareExchange64(a1, (v1 & 0xFFFFFFFFFFFFFFFEuLL) != 0, v1);
    if ( v1 == v3 )
      goto LABEL_6;
  }
  v2 = (_QWORD *)DvpRemoveWorkQueueRunningDown(a1);
LABEL_6:
  result = 0;
  if ( v2 )
  {
    do
    {
      v5 = (_QWORD *)*v2;
      *v2 = result;
      result = v2;
      v2 = v5;
    }
    while ( v5 );
  }
  return result;
}

```

## disassembly

```asm
0x140008a8c  sub     rsp, 28h
0x140008a90  mov     r9, rcx
0x140008a93  prefetchw byte ptr [rcx]
0x140008a96  mov     rax, [rcx]
0x140008a99  test    al, 2
0x140008a9b  jnz     short loc_140008ABB
0x140008a9d  mov     r8, rax
0x140008aa0  mov     ecx, 0
0x140008aa5  and     r8, 0FFFFFFFFFFFFFFFEh
0x140008aa9  mov     rdx, rax
0x140008aac  setnz   cl
0x140008aaf  lock cmpxchg [r9], rcx
0x140008ab4  cmp     rax, rdx
0x140008ab7  jnz     short loc_140008A99
0x140008ab9  jmp     short loc_140008AC6
0x140008abb  mov     rcx, r9
0x140008abe  call    DvpRemoveWorkQueueRunningDown
0x140008ac3  mov     r8, rax
0x140008ac6  xor     eax, eax
0x140008ac8  test    r8, r8
0x140008acb  jz      short loc_140008ADE
0x140008acd  mov     rcx, [r8]
0x140008ad0  mov     [r8], rax
0x140008ad3  mov     rax, r8
0x140008ad6  mov     r8, rcx
0x140008ad9  test    rcx, rcx
0x140008adc  jnz     short loc_140008ACD
0x140008ade  add     rsp, 28h
0x140008ae2  retn
```
