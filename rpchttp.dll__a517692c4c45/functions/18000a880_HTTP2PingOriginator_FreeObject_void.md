# HTTP2PingOriginator::FreeObject(void)

- ea: `0x18000a880`
- end: `0x18000a8c4`
- name: `?FreeObject@HTTP2PingOriginator@@UEAAXXZ`
- size: `68`
- prototype: `void __fastcall(HTTP2PingOriginator *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800036cc`
- `0x18000a880`
- `0x180025010`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000a8bd`

## pseudocode

```c
void __fastcall HTTP2PingOriginator::FreeObject(HTTP2PingOriginator *this)
{
  PTP_TIMER *v2; // rcx
  __int64 v3; // rcx

  v2 = (PTP_TIMER *)*((_QWORD *)this + 5);
  if ( v2 )
  {
    RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 1);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 56LL))(v3);
  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 64));
}

```

## disassembly

```asm
0x18000a880  push    rbx
0x18000a882  sub     rsp, 20h
0x18000a886  mov     rbx, rcx
0x18000a889  mov     rcx, [rcx+28h]; this
0x18000a88d  test    rcx, rcx
0x18000a890  jz      short loc_18000A89F
0x18000a892  call    ??_GRPC_THREAD_POOL_TIMER@@QEAAPEAXI@Z; RPC_THREAD_POOL_TIMER::`scalar deleting destructor'(uint)
0x18000a897  mov     qword ptr [rbx+28h], 0
0x18000a89f  mov     rcx, [rbx+8]
0x18000a8a3  test    rcx, rcx
0x18000a8a6  jz      short loc_18000A8B4
0x18000a8a8  mov     rax, [rcx]
0x18000a8ab  mov     rax, [rax+38h]
0x18000a8af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b4  lea     rcx, [rbx+40h]
0x18000a8b8  add     rsp, 20h
0x18000a8bc  pop     rbx
0x18000a8bd  jmp     cs:__imp_RtlDeleteCriticalSection
```
