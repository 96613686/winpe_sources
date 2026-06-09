# wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(void)

- ea: `0x18000c868`
- end: `0x18000c8c2`
- name: `??1Completer@?$static_lazy@VMSAClientTraceTelemetry@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: `BOOL __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ec50`

## callees

- `0x180001e94`
- `0x18000c868`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000c8bb`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<MSAClientTraceTelemetry>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx
  __int64 v4; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    v4 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v4 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18000c868  mov     [rsp+arg_0], rbx
0x18000c86d  push    rdi
0x18000c86e  sub     rsp, 20h
0x18000c872  cmp     dword ptr [rcx+8], 0
0x18000c876  mov     rdi, rcx
0x18000c879  jnz     short loc_18000C8A7
0x18000c87b  mov     rbx, [rcx]
0x18000c87e  mov     rcx, [rbx+20h]; CallbackContext
0x18000c882  mov     [rbx+10h], rcx
0x18000c886  mov     byte ptr [rbx+18h], 1
0x18000c88a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000c88f  mov     rax, [rbx+8]
0x18000c893  lea     rcx, [rbx+8]
0x18000c897  mov     dword ptr [rbx+1Ch], 1
0x18000c89e  mov     rax, [rax+8]
0x18000c8a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8a7  mov     rcx, [rdi]
0x18000c8aa  mov     edx, [rdi+8]
0x18000c8ad  lea     r8, [rcx+8]
0x18000c8b1  mov     rbx, [rsp+28h+arg_0]
0x18000c8b6  add     rsp, 20h
0x18000c8ba  pop     rdi
0x18000c8bb  jmp     cs:__imp_InitOnceComplete
```
