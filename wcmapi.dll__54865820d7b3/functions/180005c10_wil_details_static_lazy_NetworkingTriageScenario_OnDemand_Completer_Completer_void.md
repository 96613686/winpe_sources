# wil::details::static_lazy<NetworkingTriageScenario::OnDemand>::Completer::~Completer(void)

- ea: `0x180005c10`
- end: `0x180005c6f`
- name: `??1Completer@?$static_lazy@VOnDemand@NetworkingTriageScenario@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005b34`

## callees

- `0x180005340`
- `0x180005c10`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180005c63`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<NetworkingTriageScenario::OnDemand>::Completer::~Completer(_DWORD *a1)
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
0x180005c10  mov     [rsp+arg_0], rbx
0x180005c15  push    rdi
0x180005c16  sub     rsp, 20h
0x180005c1a  cmp     dword ptr [rcx+8], 0
0x180005c1e  mov     rdi, rcx
0x180005c21  jnz     short loc_180005C4F
0x180005c23  mov     rbx, [rcx]
0x180005c26  mov     rcx, [rbx+20h]; CallbackContext
0x180005c2a  mov     [rbx+10h], rcx
0x180005c2e  mov     byte ptr [rbx+18h], 1
0x180005c32  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180005c37  mov     rax, [rbx+8]
0x180005c3b  lea     rcx, [rbx+8]
0x180005c3f  mov     dword ptr [rbx+1Ch], 1
0x180005c46  mov     rax, [rax+8]
0x180005c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4f  mov     rcx, [rdi]
0x180005c52  mov     edx, [rdi+8]
0x180005c55  lea     r8, [rcx+8]
0x180005c59  mov     rbx, [rsp+28h+arg_0]
0x180005c5e  add     rsp, 20h
0x180005c62  pop     rdi
0x180005c63  jmp     cs:__imp_InitOnceComplete
```
