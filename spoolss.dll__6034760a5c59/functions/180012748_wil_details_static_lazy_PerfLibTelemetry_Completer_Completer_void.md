# wil::details::static_lazy<PerfLibTelemetry>::Completer::~Completer(void)

- ea: `0x180012748`
- end: `0x18001279e`
- name: `??1Completer@?$static_lazy@VPerfLibTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012fc4`

## callees

- `0x180012748`
- `0x18001293c`
- `0x180016010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012797`

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
0x180012748  mov     [rsp+arg_0], rbx
0x18001274d  push    rdi
0x18001274e  sub     rsp, 20h
0x180012752  cmp     dword ptr [rcx+8], 0
0x180012756  mov     rdi, rcx
0x180012759  jnz     short loc_180012783
0x18001275b  mov     rbx, [rcx]
0x18001275e  call    ?Provider@PerfLibLogging@@SAPEBU_tlgProvider_t@@XZ; PerfLibLogging::Provider(void)
0x180012763  mov     [rbx+10h], rax
0x180012767  lea     rcx, [rbx+8]
0x18001276b  mov     rax, [rbx+8]
0x18001276f  mov     byte ptr [rbx+18h], 0
0x180012773  mov     dword ptr [rbx+1Ch], 1
0x18001277a  mov     rax, [rax+8]
0x18001277e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012783  mov     rcx, [rdi]
0x180012786  mov     edx, [rdi+8]
0x180012789  lea     r8, [rcx+8]
0x18001278d  mov     rbx, [rsp+28h+arg_0]
0x180012792  add     rsp, 20h
0x180012796  pop     rdi
0x180012797  jmp     cs:__imp_InitOnceComplete
```
