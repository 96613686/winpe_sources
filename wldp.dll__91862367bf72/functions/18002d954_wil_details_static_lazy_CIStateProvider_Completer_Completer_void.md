# wil::details::static_lazy<CIStateProvider>::Completer::~Completer(void)

- ea: `0x18002d954`
- end: `0x18002d9b4`
- name: `??1Completer@?$static_lazy@VCIStateProvider@@@details@wil@@QEAA@XZ`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002ddc4`
- `0x1800405c2`

## callees

- `0x180013310`
- `0x18002d954`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d9a2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002d9a2`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CIStateProvider>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  void *v3; // rcx

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    v3 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v2 + 16) = v3;
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v3);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v2 + 8) + 8LL))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x18002d954  mov     [rsp+arg_0], rbx
0x18002d959  push    rdi
0x18002d95a  sub     rsp, 20h
0x18002d95e  mov     rdi, rcx
0x18002d961  cmp     dword ptr [rcx+8], 0
0x18002d965  jnz     short loc_18002D998
0x18002d967  mov     rbx, [rcx]
0x18002d96a  mov     rcx, [rbx+20h]; CallbackContext
0x18002d96e  mov     [rbx+10h], rcx
0x18002d972  mov     byte ptr [rbx+18h], 1
0x18002d976  xor     r8d, r8d
0x18002d979  xor     edx, edx
0x18002d97b  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18002d980  mov     dword ptr [rbx+1Ch], 1
0x18002d987  mov     rax, [rbx+8]
0x18002d98b  lea     rcx, [rbx+8]
0x18002d98f  mov     rax, [rax+8]
0x18002d993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d998  mov     rcx, [rdi]; lpInitOnce
0x18002d99b  lea     r8, [rcx+8]; lpContext
0x18002d99f  mov     edx, [rdi+8]; dwFlags
0x18002d9a2  call    cs:__imp_InitOnceComplete
0x18002d9a8  nop
0x18002d9a9  mov     rbx, [rsp+28h+arg_0]
0x18002d9ae  add     rsp, 20h
0x18002d9b2  pop     rdi
0x18002d9b3  retn
```
