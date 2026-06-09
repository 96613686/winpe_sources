# THREAD_POOL::~THREAD_POOL(void)

- ea: `0x180003730`
- end: `0x180003761`
- name: `??1THREAD_POOL@@AEAA@XZ`
- size: `49`
- prototype: `void __fastcall(THREAD_POOL *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180003768`

## callees

- `0x180001f8c`
- `0x180003730`

## pseudocode

```c
void __fastcall THREAD_POOL::~THREAD_POOL(void **this)
{
  _QWORD *v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    *(_DWORD *)v2 = 2017742932;
    v2[5] = 0;
    operator delete(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180003730  push    rbx
0x180003732  sub     rsp, 20h
0x180003736  mov     rbx, rcx
0x180003739  mov     rcx, [rcx]; Block
0x18000373c  test    rcx, rcx
0x18000373f  jz      short loc_18000375B
0x180003741  mov     dword ptr [rcx], 78445054h
0x180003747  mov     qword ptr [rcx+28h], 0
0x18000374f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003754  mov     qword ptr [rbx], 0
0x18000375b  add     rsp, 20h
0x18000375f  pop     rbx
0x180003760  retn
```
