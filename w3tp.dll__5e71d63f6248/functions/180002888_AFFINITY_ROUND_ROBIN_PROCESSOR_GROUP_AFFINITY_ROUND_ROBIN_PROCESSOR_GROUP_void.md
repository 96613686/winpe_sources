# AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::~AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP(void)

- ea: `0x180002888`
- end: `0x180002900`
- name: `??1AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@UEAA@XZ`
- size: `120`
- prototype: `void __fastcall(AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002a30`

## callees

- `0x180001f8c`
- `0x180002888`
- `0x180002a68`

## pseudocode

```c
void __fastcall AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::~AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP(
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP *this)
{
  bool v1; // zf
  unsigned __int16 i; // di
  __int64 v4; // rsi
  struct _PROC_THREAD_ATTRIBUTE_LIST **v5; // rcx

  v1 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable';
  if ( !v1 )
  {
    for ( i = 0; i < *((_WORD *)this + 4); *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v4) = 0 )
    {
      v4 = i;
      v5 = *(struct _PROC_THREAD_ATTRIBUTE_LIST ***)(*((_QWORD *)this + 2) + 8LL * i);
      if ( v5 )
        AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(v5);
      ++i;
    }
    operator delete(*((void **)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x180002888  mov     [rsp+arg_0], rbx
0x18000288d  mov     [rsp+arg_8], rsi
0x180002892  push    rdi
0x180002893  sub     rsp, 20h
0x180002897  cmp     qword ptr [rcx+10h], 0
0x18000289c  lea     rax, ??_7AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@6B@; const AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::`vftable'
0x1800028a3  mov     [rcx], rax
0x1800028a6  mov     rbx, rcx
0x1800028a9  jz      short loc_1800028F0
0x1800028ab  xor     edi, edi
0x1800028ad  xor     eax, eax
0x1800028af  cmp     ax, [rcx+8]
0x1800028b3  jnb     short loc_1800028DF
0x1800028b5  mov     rax, [rbx+10h]
0x1800028b9  movzx   esi, di
0x1800028bc  mov     rcx, [rax+rsi*8]; this
0x1800028c0  test    rcx, rcx
0x1800028c3  jz      short loc_1800028CA
0x1800028c5  call    ??_GTHREAD_AFFINITY_CONTEXT@AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP@@QEAAPEAXI@Z; AFFINITY_ROUND_ROBIN_PROCESSOR_GROUP::THREAD_AFFINITY_CONTEXT::`scalar deleting destructor'(uint)
0x1800028ca  mov     rax, [rbx+10h]
0x1800028ce  inc     di
0x1800028d1  mov     qword ptr [rax+rsi*8], 0
0x1800028d9  cmp     di, [rbx+8]
0x1800028dd  jb      short loc_1800028B5
0x1800028df  mov     rcx, [rbx+10h]; Block
0x1800028e3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800028e8  mov     qword ptr [rbx+10h], 0
0x1800028f0  mov     rbx, [rsp+28h+arg_0]
0x1800028f5  mov     rsi, [rsp+28h+arg_8]
0x1800028fa  add     rsp, 20h
0x1800028fe  pop     rdi
0x1800028ff  retn
```
