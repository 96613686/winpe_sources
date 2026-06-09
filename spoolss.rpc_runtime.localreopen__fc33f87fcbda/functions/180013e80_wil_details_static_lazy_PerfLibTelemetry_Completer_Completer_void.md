# wil::details::static_lazy<PerfLibTelemetry>::Completer::~Completer(void)

- ea: `0x180013e80`
- end: `0x180013edb`
- name: `??1Completer@?$static_lazy@VPerfLibTelemetry@@@details@wil@@QEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014724`

## callees

- `0x180013e80`
- `0x18001407c`
- `0x180017010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013ecf`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<PerfLibTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = PerfLibLogging::Provider();
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
0x180013e80  mov     [rsp+arg_0], rbx
0x180013e85  push    rdi
0x180013e86  sub     rsp, 20h
0x180013e8a  cmp     dword ptr [rcx+8], 0
0x180013e8e  mov     rdi, rcx
0x180013e91  jnz     short loc_180013EBB
0x180013e93  mov     rbx, [rcx]
0x180013e96  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x180013e9b  mov     [rbx+10h], rax
0x180013e9f  lea     rcx, [rbx+8]
0x180013ea3  mov     rax, [rbx+8]
0x180013ea7  mov     byte ptr [rbx+18h], 0
0x180013eab  mov     dword ptr [rbx+1Ch], 1
0x180013eb2  mov     rax, [rax+8]
0x180013eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ebb  mov     rcx, [rdi]
0x180013ebe  mov     edx, [rdi+8]
0x180013ec1  lea     r8, [rcx+8]
0x180013ec5  mov     rbx, [rsp+28h+arg_0]
0x180013eca  add     rsp, 20h
0x180013ece  pop     rdi
0x180013ecf  jmp     cs:__imp_InitOnceComplete
```
