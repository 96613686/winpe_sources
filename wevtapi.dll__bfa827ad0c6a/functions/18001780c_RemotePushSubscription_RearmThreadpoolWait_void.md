# RemotePushSubscription::RearmThreadpoolWait(void)

- ea: `0x18001780c`
- end: `0x18001785c`
- name: `?RearmThreadpoolWait@RemotePushSubscription@@AEAAXXZ`
- size: `80`
- prototype: `void __fastcall(RemotePushSubscription *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800176d0`

## callees

- `0x18001780c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017823`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180017823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017855`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017842`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180017842`

## pseudocode

```c
void __fastcall RemotePushSubscription::RearmThreadpoolWait(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v1; // rdi
  struct _TP_WAIT *Ptr; // rcx

  v1 = this + 28;
  AcquireSRWLockExclusive(this + 28);
  if ( !LOBYTE(this[43].Ptr) )
  {
    Ptr = (struct _TP_WAIT *)this[8].Ptr;
    if ( Ptr )
      SetThreadpoolWait(Ptr, this[7].Ptr, 0);
  }
  ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18001780c  mov     [rsp+arg_0], rbx
0x180017811  push    rdi
0x180017812  sub     rsp, 20h
0x180017816  lea     rdi, [rcx+0E0h]
0x18001781d  mov     rbx, rcx
0x180017820  mov     rcx, rdi; SRWLock
0x180017823  call    cs:__imp_AcquireSRWLockExclusive
0x180017829  cmp     byte ptr [rbx+158h], 0
0x180017830  jnz     short loc_180017848
0x180017832  mov     rcx, [rbx+40h]; pwa
0x180017836  test    rcx, rcx
0x180017839  jz      short loc_180017848
0x18001783b  mov     rdx, [rbx+38h]; h
0x18001783f  xor     r8d, r8d; pftTimeout
0x180017842  call    cs:__imp_SetThreadpoolWait
0x180017848  mov     rcx, rdi
0x18001784b  mov     rbx, [rsp+28h+arg_0]
0x180017850  add     rsp, 20h
0x180017854  pop     rdi
0x180017855  jmp     cs:__imp_ReleaseSRWLockExclusive
```
