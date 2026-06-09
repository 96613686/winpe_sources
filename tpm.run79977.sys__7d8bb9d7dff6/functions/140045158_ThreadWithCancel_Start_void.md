# ThreadWithCancel::Start(void *)

- ea: `0x140045158`
- end: `0x14004518a`
- name: `?Start@ThreadWithCancel@@QEAAJPEAX@Z`
- size: `50`
- prototype: `__int64 __fastcall(ThreadWithCancel *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001e394`
- `0x14002ed30`

## callees

- `0x140044dcc`
- `0x140045070`
- `0x140045158`

## pseudocode

```c
int __fastcall ThreadWithCancel::Start(ThreadWithCancel *this, void *a2, unsigned __int8 a3)
{
  int result; // eax

  *((_QWORD *)this + 1) = a2;
  result = Event::Initialize((ThreadWithCancel *)((char *)this + 24), NotificationEvent, a3);
  if ( result >= 0 )
    return Thread::Initialize((ThreadWithCancel *)((char *)this + 16), *(void (**)(void *))this, this);
  return result;
}

```

## disassembly

```asm
0x140045158  push    rbx
0x14004515a  sub     rsp, 20h
0x14004515e  mov     [rcx+8], rdx
0x140045162  mov     rbx, rcx
0x140045165  add     rcx, 18h; this
0x140045169  xor     edx, edx; enum _EVENT_TYPE
0x14004516b  call    ?Initialize@Event@@QEAAJW4_EVENT_TYPE@@E@Z; Event::Initialize(_EVENT_TYPE,uchar)
0x140045170  test    eax, eax
0x140045172  js      short loc_140045183
0x140045174  mov     rdx, [rbx]; void (*)(void *)
0x140045177  lea     rcx, [rbx+10h]; this
0x14004517b  mov     r8, rbx; void *
0x14004517e  call    ?Initialize@Thread@@QEAAJP6AXPEAX@Z0@Z; Thread::Initialize(void (*)(void *),void *)
0x140045183  add     rsp, 20h
0x140045187  pop     rbx
0x140045188  retn
```
