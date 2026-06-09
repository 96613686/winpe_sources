# wil::details::static_lazy<UserenvTelemetry>::Completer::~Completer(void)

- ea: `0x180015440`
- end: `0x18001549b`
- name: `??1Completer@?$static_lazy@VUserenvTelemetry@@@details@wil@@QEAA@XZ`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009614`

## callees

- `0x18000d8ec`
- `0x180015440`
- `0x18001d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001548f`

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
0x180015440  mov     [rsp+arg_0], rbx
0x180015445  push    rdi
0x180015446  sub     rsp, 20h
0x18001544a  cmp     dword ptr [rcx+8], 0
0x18001544e  mov     rdi, rcx
0x180015451  jnz     short loc_18001547B
0x180015453  mov     rbx, [rcx]
0x180015456  call    ?Provider@ProfileAPILogging@@SAPEBU_tlgProvider_t@@XZ; ProfileAPILogging::Provider(void)
0x18001545b  mov     [rbx+10h], rax
0x18001545f  lea     rcx, [rbx+8]
0x180015463  mov     rax, [rbx+8]
0x180015467  mov     byte ptr [rbx+18h], 0
0x18001546b  mov     dword ptr [rbx+1Ch], 1
0x180015472  mov     rax, [rax+8]
0x180015476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001547b  mov     rcx, [rdi]
0x18001547e  mov     edx, [rdi+8]
0x180015481  lea     r8, [rcx+8]
0x180015485  mov     rbx, [rsp+28h+arg_0]
0x18001548a  add     rsp, 20h
0x18001548e  pop     rdi
0x18001548f  jmp     cs:__imp_InitOnceComplete
```
