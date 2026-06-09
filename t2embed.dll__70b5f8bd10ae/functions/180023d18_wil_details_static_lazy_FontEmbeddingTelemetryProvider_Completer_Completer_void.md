# wil::details::static_lazy<FontEmbeddingTelemetryProvider>::Completer::~Completer(void)

- ea: `0x180023d18`
- end: `0x180023d72`
- name: `??1Completer@?$static_lazy@VFontEmbeddingTelemetryProvider@@@details@wil@@QEAA@XZ`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001bb28`

## callees

- `0x180001a68`
- `0x180023d18`
- `0x18002b010`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x180023d6b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<FontEmbeddingTelemetryProvider>::Completer::~Completer(_DWORD *a1)
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
0x180023d18  mov     [rsp+arg_0], rbx
0x180023d1d  push    rdi
0x180023d1e  sub     rsp, 20h
0x180023d22  cmp     dword ptr [rcx+8], 0
0x180023d26  mov     rdi, rcx
0x180023d29  jnz     short loc_180023D57
0x180023d2b  mov     rbx, [rcx]
0x180023d2e  mov     rcx, [rbx+20h]; CallbackContext
0x180023d32  mov     [rbx+10h], rcx
0x180023d36  mov     byte ptr [rbx+18h], 1
0x180023d3a  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180023d3f  mov     rax, [rbx+8]
0x180023d43  lea     rcx, [rbx+8]
0x180023d47  mov     dword ptr [rbx+1Ch], 1
0x180023d4e  mov     rax, [rax+8]
0x180023d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d57  mov     rcx, [rdi]
0x180023d5a  mov     edx, [rdi+8]
0x180023d5d  lea     r8, [rcx+8]
0x180023d61  mov     rbx, [rsp+28h+arg_0]
0x180023d66  add     rsp, 20h
0x180023d6a  pop     rdi
0x180023d6b  jmp     cs:__imp_InitOnceComplete
```
