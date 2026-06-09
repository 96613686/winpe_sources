# Cache::Proxy::~Proxy(void)

- ea: `0x18000cfec`
- end: `0x18000d041`
- name: `??1Proxy@Cache@@QEAA@XZ`
- size: `85`
- prototype: `void __fastcall(Cache::Proxy *__hidden this)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x180010784`
- `0x180010afc`
- `0x18001126c`
- `0x180011ff0`
- `0x180012178`
- `0x1800123b8`
- `0x180012628`
- `0x180012d38`
- `0x180012e80`
- `0x18001307c`
- `0x1800131dc`
- `0x180015750`
- `0x18001c0a0`
- `0x18001c0b2`

## callees

- `0x18000cfec`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d02d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d02d`

## pseudocode

```c
void __fastcall Cache::Proxy::~Proxy(Cache::Proxy *this)
{
  __int64 v2; // rcx
  RTL_SRWLOCK *v3; // rcx

  if ( *((_QWORD *)this + 1) )
  {
    if ( *(_BYTE *)(*(_QWORD *)this + 120LL) )
    {
      v2 = *(_QWORD *)(*(_QWORD *)this + 32LL);
      if ( v2 )
      {
        (*(void (__fastcall **)(__int64, Cache::Proxy *))(*(_QWORD *)v2 + 16LL))(v2, this);
        *(_BYTE *)(*(_QWORD *)this + 120LL) = 0;
      }
    }
  }
  v3 = (RTL_SRWLOCK *)*((_QWORD *)this + 1);
  if ( v3 )
  {
    ReleaseSRWLockExclusive(v3);
    *((_QWORD *)this + 1) = 0;
  }
}

```

## disassembly

```asm
0x18000cfec  push    rbx
0x18000cfee  sub     rsp, 20h
0x18000cff2  mov     rbx, rcx
0x18000cff5  cmp     qword ptr [rcx+8], 0
0x18000cffa  jz      short loc_18000D024
0x18000cffc  mov     rax, [rcx]
0x18000cfff  cmp     byte ptr [rax+78h], 0
0x18000d003  jz      short loc_18000D024
0x18000d005  mov     rcx, [rax+20h]
0x18000d009  test    rcx, rcx
0x18000d00c  jz      short loc_18000D024
0x18000d00e  mov     rax, [rcx]
0x18000d011  mov     rdx, rbx
0x18000d014  mov     rax, [rax+10h]
0x18000d018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d01d  mov     rax, [rbx]
0x18000d020  mov     byte ptr [rax+78h], 0
0x18000d024  mov     rcx, [rbx+8]; SRWLock
0x18000d028  test    rcx, rcx
0x18000d02b  jz      short loc_18000D03B
0x18000d02d  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d033  mov     qword ptr [rbx+8], 0
0x18000d03b  add     rsp, 20h
0x18000d03f  pop     rbx
0x18000d040  retn
```
