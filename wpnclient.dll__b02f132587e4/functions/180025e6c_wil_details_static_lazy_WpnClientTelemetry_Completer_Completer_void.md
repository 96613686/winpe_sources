# wil::details::static_lazy<WpnClientTelemetry>::Completer::~Completer(void)

- ea: `0x180025e6c`
- end: `0x180025ec2`
- name: `??1Completer@?$static_lazy@VWpnClientTelemetry@@@details@wil@@QEAA@XZ`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d8a0`

## callees

- `0x180025e6c`
- `0x18002621c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180025ebb`

## pseudocode

```c
BOOL __fastcall wil::details::static_lazy<WpnClientTelemetry>::Completer::~Completer(__int64 a1)
{
  LPINIT_ONCE v2; // rbx
  union _RTL_RUN_ONCE v3; // rax

  if ( !*(_DWORD *)(a1 + 8) )
  {
    v2 = *(LPINIT_ONCE *)a1;
    v2[2].Ptr = WpnClientTelemetryProvider::Provider();
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
0x180025e6c  mov     [rsp+arg_0], rbx
0x180025e71  push    rdi
0x180025e72  sub     rsp, 20h
0x180025e76  cmp     dword ptr [rcx+8], 0
0x180025e7a  mov     rdi, rcx
0x180025e7d  jnz     short loc_180025EA7
0x180025e7f  mov     rbx, [rcx]
0x180025e82  call    ?Provider@WpnClientTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; WpnClientTelemetryProvider::Provider(void)
0x180025e87  mov     [rbx+10h], rax
0x180025e8b  lea     rcx, [rbx+8]
0x180025e8f  mov     rax, [rbx+8]
0x180025e93  mov     byte ptr [rbx+18h], 0
0x180025e97  mov     dword ptr [rbx+1Ch], 1
0x180025e9e  mov     rax, [rax+8]
0x180025ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ea7  mov     rcx, [rdi]
0x180025eaa  mov     edx, [rdi+8]
0x180025ead  lea     r8, [rcx+8]
0x180025eb1  mov     rbx, [rsp+28h+arg_0]
0x180025eb6  add     rsp, 20h
0x180025eba  pop     rdi
0x180025ebb  jmp     cs:__imp_InitOnceComplete
```
