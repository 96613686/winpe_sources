# WEBHOST_PROTOCOL_MANAGER::CheckHealth(IHealthStatusCallback *)

- ea: `0x180001b10`
- end: `0x180001b7d`
- name: `?CheckHealth@WEBHOST_PROTOCOL_MANAGER@@UEAAJPEAVIHealthStatusCallback@@@Z`
- size: `109`
- prototype: `__int64 __fastcall(WEBHOST_PROTOCOL_MANAGER *__hidden this, struct IHealthStatusCallback *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001b10`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b35`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180001b35`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b5b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180001b5b`

## pseudocode

```c
__int64 __fastcall WEBHOST_PROTOCOL_MANAGER::CheckHealth(
        WEBHOST_PROTOCOL_MANAGER *this,
        struct IHealthStatusCallback *a2)
{
  __int64 v3; // rdi

  v3 = *((_QWORD *)this + 10);
  (**(void (__fastcall ***)(struct IHealthStatusCallback *))a2)(a2);
  EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
  if ( *(_QWORD *)(v3 + 16) )
    (*(void (__fastcall **)(struct IHealthStatusCallback *))(*(_QWORD *)a2 + 8LL))(a2);
  else
    *(_QWORD *)(v3 + 16) = a2;
  LeaveCriticalSection((LPCRITICAL_SECTION)(v3 + 32));
  return (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 9) + 32LL))(
           *((_QWORD *)this + 9),
           *((_QWORD *)this + 10));
}

```

## disassembly

```asm
0x180001b10  push    rbx
0x180001b12  push    rbp
0x180001b13  push    rsi
0x180001b14  push    rdi
0x180001b15  sub     rsp, 28h
0x180001b19  mov     rax, [rdx]
0x180001b1c  mov     rsi, rcx
0x180001b1f  mov     rdi, [rcx+50h]
0x180001b23  mov     rbx, rdx
0x180001b26  mov     rcx, rdx
0x180001b29  mov     rax, [rax]
0x180001b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b31  lea     rcx, [rdi+20h]; lpCriticalSection
0x180001b35  call    cs:__imp_EnterCriticalSection
0x180001b3b  cmp     qword ptr [rdi+10h], 0
0x180001b40  jz      short loc_180001B53
0x180001b42  mov     rax, [rbx]
0x180001b45  mov     rcx, rbx
0x180001b48  mov     rax, [rax+8]
0x180001b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b51  jmp     short loc_180001B57
0x180001b53  mov     [rdi+10h], rbx
0x180001b57  lea     rcx, [rdi+20h]; lpCriticalSection
0x180001b5b  call    cs:__imp_LeaveCriticalSection
0x180001b61  mov     rcx, [rsi+48h]
0x180001b65  mov     rdx, [rsi+50h]
0x180001b69  mov     rax, [rcx]
0x180001b6c  mov     rax, [rax+20h]
0x180001b70  add     rsp, 28h
0x180001b74  pop     rdi
0x180001b75  pop     rsi
0x180001b76  pop     rbp
0x180001b77  pop     rbx
0x180001b78  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
