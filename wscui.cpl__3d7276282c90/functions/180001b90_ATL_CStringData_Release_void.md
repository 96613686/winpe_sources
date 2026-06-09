# ATL::CStringData::Release(void)

- ea: `0x180001b90`
- end: `0x180001bb5`
- name: `?Release@CStringData@ATL@@QEAAXXZ`
- size: `37`
- prototype: `void __fastcall(ATL::CStringData *__hidden this)`
- caller_count: `25`
- callee_count: `2`
- tags: ``

## callers

- `0x180001890`
- `0x180001b70`
- `0x180004930`
- `0x18000498c`
- `0x1800052cc`
- `0x1800058b0`
- `0x18000592c`
- `0x180005cf4`
- `0x18000750c`
- `0x180007938`
- `0x180007b08`
- `0x180009300`
- `0x180009590`
- `0x18000b190`
- `0x18000b1b0`
- `0x18000b1d0`
- `0x18000b1f0`
- `0x18000b210`
- `0x18000b230`
- `0x18000b250`
- `0x18000b270`
- `0x18000b290`
- `0x18000b2b0`
- `0x18000b2d0`
- `0x18000b2f0`

## callees

- `0x180001b90`
- `0x18000c010`

## pseudocode

```c
void __fastcall ATL::CStringData::Release(ATL::CStringData *this)
{
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD, ATL::CStringData *))(**(_QWORD **)this + 8LL))(*(_QWORD *)this, this);
}

```

## disassembly

```asm
0x180001b90  mov     eax, 0FFFFFFFFh
0x180001b95  lock xadd [rcx+10h], eax
0x180001b9a  sub     eax, 1
0x180001b9d  jg      short locret_180001BB4
0x180001b9f  mov     r8, [rcx]
0x180001ba2  mov     rdx, rcx
0x180001ba5  mov     rcx, r8
0x180001ba8  mov     rax, [r8]
0x180001bab  mov     rax, [rax+8]
0x180001baf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x180001bb4  retn
```
