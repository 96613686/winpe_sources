# wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(void)

- ea: `0x1800096a0`
- end: `0x1800096fc`
- name: `??1Completer@?$static_lazy@VFeatureLogging@details@wil@@@details@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800095e0`

## callees

- `0x1800096a0`
- `0x180009704`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800096c7`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<wil::details::FeatureLogging>::Completer::~Completer(_DWORD *a1)
{
  __int64 v3; // rbx
  void *v4; // rcx
  __int64 v5; // rax

  if ( !a1[2] )
  {
    v3 = *(_QWORD *)a1;
    v4 = *(void **)(*(_QWORD *)a1 + 32LL);
    *(_QWORD *)(v3 + 16) = v4;
    *(_BYTE *)(v3 + 24) = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(v4);
    v5 = *(_QWORD *)(v3 + 8);
    *(_DWORD *)(v3 + 28) = 1;
    (*(void (__fastcall **)(__int64))(v5 + 8))(v3 + 8);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, a1[2], (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x1800096a0  mov     [rsp+arg_0], rbx
0x1800096a5  push    rdi
0x1800096a6  sub     rsp, 20h
0x1800096aa  cmp     dword ptr [rcx+8], 0
0x1800096ae  mov     rdi, rcx
0x1800096b1  jz      short loc_1800096CE
0x1800096b3  mov     rcx, [rdi]
0x1800096b6  mov     edx, [rdi+8]
0x1800096b9  lea     r8, [rcx+8]
0x1800096bd  mov     rbx, [rsp+28h+arg_0]
0x1800096c2  add     rsp, 20h
0x1800096c6  pop     rdi
0x1800096c7  jmp     cs:__imp_InitOnceComplete
0x1800096ce  mov     rbx, [rcx]
0x1800096d1  mov     rcx, [rbx+20h]; CallbackContext
0x1800096d5  mov     [rbx+10h], rcx
0x1800096d9  mov     byte ptr [rbx+18h], 1
0x1800096dd  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800096e2  mov     rax, [rbx+8]
0x1800096e6  lea     rcx, [rbx+8]
0x1800096ea  mov     dword ptr [rbx+1Ch], 1
0x1800096f1  mov     rax, [rax+8]
0x1800096f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096fa  jmp     short loc_1800096B3
```
