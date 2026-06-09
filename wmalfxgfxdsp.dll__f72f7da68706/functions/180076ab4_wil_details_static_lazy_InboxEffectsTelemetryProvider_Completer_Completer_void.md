# wil::details::static_lazy<InboxEffectsTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180076ab4`
- end: `0x180076b0e`
- name: `??1Completer@?$static_lazy@VInboxEffectsTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180079a20`

## callees

- `0x180001650`
- `0x180076ab4`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180076b07`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<InboxEffectsTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180076ab4  mov     [rsp+arg_0], rbx
0x180076ab9  push    rdi
0x180076aba  sub     rsp, 20h
0x180076abe  cmp     dword ptr [rcx+8], 0
0x180076ac2  mov     rdi, rcx
0x180076ac5  jnz     short loc_180076AF3
0x180076ac7  mov     rbx, [rcx]
0x180076aca  mov     rcx, [rbx+20h]; CallbackContext
0x180076ace  mov     [rbx+10h], rcx
0x180076ad2  mov     byte ptr [rbx+18h], 1
0x180076ad6  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180076adb  mov     rax, [rbx+8]
0x180076adf  lea     rcx, [rbx+8]
0x180076ae3  mov     dword ptr [rbx+1Ch], 1
0x180076aea  mov     rax, [rax+8]
0x180076aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180076af3  mov     rcx, [rdi]
0x180076af6  mov     edx, [rdi+8]
0x180076af9  lea     r8, [rcx+8]
0x180076afd  mov     rbx, [rsp+28h+arg_0]
0x180076b02  add     rsp, 20h
0x180076b06  pop     rdi
0x180076b07  jmp     cs:__imp_InitOnceComplete
```
