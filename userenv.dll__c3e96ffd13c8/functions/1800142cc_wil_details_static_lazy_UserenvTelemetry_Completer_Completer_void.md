# wil::details::static_lazy<UserenvTelemetry>::Completer::~Completer(void)

- ea: `0x1800142cc`
- end: `0x180014322`
- name: `??1Completer@?$static_lazy@VUserenvTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008d74`

## callees

- `0x18000cc14`
- `0x1800142cc`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001431b`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<UserenvTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = ProfileAPILogging::Provider();
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
0x1800142cc  mov     [rsp+arg_0], rbx
0x1800142d1  push    rdi
0x1800142d2  sub     rsp, 20h
0x1800142d6  cmp     dword ptr [rcx+8], 0
0x1800142da  mov     rdi, rcx
0x1800142dd  jnz     short loc_180014307
0x1800142df  mov     rbx, [rcx]
0x1800142e2  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x1800142e7  mov     [rbx+10h], rax
0x1800142eb  lea     rcx, [rbx+8]
0x1800142ef  mov     rax, [rbx+8]
0x1800142f3  mov     byte ptr [rbx+18h], 0
0x1800142f7  mov     dword ptr [rbx+1Ch], 1
0x1800142fe  mov     rax, [rax+8]
0x180014302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014307  mov     rcx, [rdi]
0x18001430a  mov     edx, [rdi+8]
0x18001430d  lea     r8, [rcx+8]
0x180014311  mov     rbx, [rsp+28h+arg_0]
0x180014316  add     rsp, 20h
0x18001431a  pop     rdi
0x18001431b  jmp     cs:__imp_InitOnceComplete
```
