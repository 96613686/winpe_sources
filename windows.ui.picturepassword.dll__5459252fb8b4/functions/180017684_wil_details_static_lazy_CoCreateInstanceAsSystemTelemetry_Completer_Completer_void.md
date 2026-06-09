# wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::Completer::~Completer(void)

- ea: `0x180017684`
- end: `0x1800176da`
- name: `??1Completer@?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800182ac`

## callees

- `0x180017684`
- `0x180017bd8`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800176d3`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = CoCreateInstanceAsSystemLogging::Provider();
    v3.Ptr = v2[1].Ptr;
    LOBYTE(v2[3].Ptr) = 0;
    HIDWORD(v2[3].Ptr) = 1;
    (*((void (__fastcall **)(LPINIT_ONCE))v3.Ptr + 1))(v2 + 1);
  }
  return InitOnceComplete(*(LPINIT_ONCE *)a1, *(_DWORD *)(a1 + 8), (LPVOID)(*(_QWORD *)a1 + 8LL));
}

```

## disassembly

```asm
0x180017684  mov     [rsp+arg_0], rbx
0x180017689  push    rdi
0x18001768a  sub     rsp, 20h
0x18001768e  cmp     dword ptr [rcx+8], 0
0x180017692  mov     rdi, rcx
0x180017695  jnz     short loc_1800176BF
0x180017697  mov     rbx, [rcx]
0x18001769a  call    ?Provider@CoCreateInstanceAsSystemLogging@@SAPEBU_tlgProvider_t@@XZ; CoCreateInstanceAsSystemLogging::Provider(void)
0x18001769f  mov     [rbx+10h], rax
0x1800176a3  lea     rcx, [rbx+8]
0x1800176a7  mov     rax, [rbx+8]
0x1800176ab  mov     byte ptr [rbx+18h], 0
0x1800176af  mov     dword ptr [rbx+1Ch], 1
0x1800176b6  mov     rax, [rax+8]
0x1800176ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176bf  mov     rcx, [rdi]
0x1800176c2  mov     edx, [rdi+8]
0x1800176c5  lea     r8, [rcx+8]
0x1800176c9  mov     rbx, [rsp+28h+arg_0]
0x1800176ce  add     rsp, 20h
0x1800176d2  pop     rdi
0x1800176d3  jmp     cs:__imp_InitOnceComplete
```
