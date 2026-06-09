# wil::details::static_lazy<ProfileAPILogging>::Completer::~Completer(void)

- ea: `0x180013630`
- end: `0x18001368f`
- name: `??1Completer@?$static_lazy@VProfileAPILogging@@@details@wil@@QEAA@XZ`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d90c`

## callees

- `0x180001c7c`
- `0x180013630`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013683`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<ProfileAPILogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v2; // rbx
  __int64 v3; // rax

  if ( !a1[2] )
  {
    v2 = *(_QWORD *)a1;
    *(_QWORD *)(v2 + 16) = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
    *(_BYTE *)(v2 + 24) = 1;
    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation();
    v3 = *(_QWORD *)(v2 + 8);
    *(_DWORD *)(v2 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v3 + 8))(v2 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180013630  mov     [rsp+arg_0], rbx
0x180013635  push    rdi
0x180013636  sub     rsp, 20h
0x18001363a  cmp     dword ptr [rcx+8], 0
0x18001363e  mov     rdi, rcx
0x180013641  jnz     short loc_18001366F
0x180013643  mov     rbx, [rcx]
0x180013646  mov     rcx, [rbx+20h]
0x18001364a  mov     [rbx+10h], rcx
0x18001364e  mov     byte ptr [rbx+18h], 1
0x180013652  call    TraceLoggingRegisterEx_EtwEventRegister_EtwEventSetInformation
0x180013657  mov     rax, [rbx+8]
0x18001365b  lea     rcx, [rbx+8]
0x18001365f  mov     dword ptr [rbx+1Ch], 1
0x180013666  mov     rax, [rax+8]
0x18001366a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001366f  mov     rcx, [rdi]
0x180013672  mov     edx, [rdi+8]
0x180013675  lea     r8, [rcx+8]
0x180013679  mov     rbx, [rsp+28h+arg_0]
0x18001367e  add     rsp, 20h
0x180013682  pop     rdi
0x180013683  jmp     cs:__imp_InitOnceComplete
```
