# CLogFile::UnregisterOplockFromThreadPool(void)

- ea: `0x18000ed70`
- end: `0x18000eda8`
- name: `?UnregisterOplockFromThreadPool@CLogFile@@QEAAXXZ`
- size: `56`
- prototype: `void __fastcall(CLogFile *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001494`
- `0x180002b50`

## callees

- `0x18000ed38`
- `0x18000ed70`

## pseudocode

```c
void __fastcall CLogFile::UnregisterOplockFromThreadPool(CLogFile *this)
{
  signed __int64 v1; // r8
  void *v2; // rax

  if ( *((_QWORD *)this + 22) )
  {
    v1 = *((_QWORD *)this + 22);
    v2 = (void *)_InterlockedCompareExchange64((volatile signed __int64 *)this + 22, 0, v1);
    if ( (void *)v1 == v2 )
      TrkUnregisterWait(v2, (void *)0xFFFFFFFFFFFFFFFFLL);
  }
}

```

## disassembly

```asm
0x18000ed70  sub     rsp, 28h
0x18000ed74  xor     edx, edx
0x18000ed76  cmp     [rcx+0B0h], rdx
0x18000ed7d  jz      short loc_18000EDA3
0x18000ed7f  mov     r8, [rcx+0B0h]
0x18000ed86  mov     rax, r8
0x18000ed89  lock cmpxchg [rcx+0B0h], rdx
0x18000ed92  cmp     r8, rax
0x18000ed95  jnz     short loc_18000EDA3
0x18000ed97  or      rdx, 0FFFFFFFFFFFFFFFFh; void *
0x18000ed9b  mov     rcx, rax; void *
0x18000ed9e  call    ?TrkUnregisterWait@@YAHPEAX0@Z; TrkUnregisterWait(void *,void *)
0x18000eda3  add     rsp, 28h
0x18000eda7  retn
```
