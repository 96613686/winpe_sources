# wil::details::static_lazy<ShdocvwTelemetry>::Completer::~Completer(void)

- ea: `0x180014dd0`
- end: `0x180014e2a`
- name: `??1Completer@?$static_lazy@VShdocvwTelemetry@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001b76c`

## callees

- `0x1800043e0`
- `0x180014dd0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180014e23`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ShdocvwTelemetry>::Completer::~Completer(_DWORD *a1)
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
0x180014dd0  mov     [rsp+arg_0], rbx
0x180014dd5  push    rdi
0x180014dd6  sub     rsp, 20h
0x180014dda  cmp     dword ptr [rcx+8], 0
0x180014dde  mov     rdi, rcx
0x180014de1  jnz     short loc_180014E0F
0x180014de3  mov     rbx, [rcx]
0x180014de6  mov     rcx, [rbx+20h]; CallbackContext
0x180014dea  mov     [rbx+10h], rcx
0x180014dee  mov     byte ptr [rbx+18h], 1
0x180014df2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180014df7  mov     rax, [rbx+8]
0x180014dfb  lea     rcx, [rbx+8]
0x180014dff  mov     dword ptr [rbx+1Ch], 1
0x180014e06  mov     rax, [rax+8]
0x180014e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0f  mov     rcx, [rdi]
0x180014e12  mov     edx, [rdi+8]
0x180014e15  lea     r8, [rcx+8]
0x180014e19  mov     rbx, [rsp+28h+arg_0]
0x180014e1e  add     rsp, 20h
0x180014e22  pop     rdi
0x180014e23  jmp     cs:__imp_InitOnceComplete
```
