# Tpm20Scheduler::~Tpm20Scheduler(void)

- ea: `0x14001b974`
- end: `0x14001ba1d`
- name: `??1Tpm20Scheduler@@AEAA@XZ`
- size: `169`
- prototype: `void __fastcall(Tpm20Scheduler *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14001ba24`

## callees

- `0x140008aac`
- `0x14001b974`
- `0x14001ba4c`
- `0x140039780`

## import_xrefs

- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001b9ab`
- `ntoskrnl!ExInterlockedRemoveHeadList` at `0x14001b9ab`

## pseudocode

```c
void __fastcall Tpm20Scheduler::~Tpm20Scheduler(Tpm20ResourceMgr **this)
{
  KSPIN_LOCK *v2; // rdx
  struct _LIST_ENTRY *i; // rcx
  PLIST_ENTRY v4; // rax
  unsigned int v5; // edx
  TpmSWAntiHammeringMgr *v6; // rcx

  v2 = (KSPIN_LOCK *)(this + 14);
  for ( i = (struct _LIST_ENTRY *)(this + 15); ; i = (struct _LIST_ENTRY *)(this + 15) )
  {
    v4 = ExInterlockedRemoveHeadList(i, v2);
    if ( !v4 )
      break;
    Tpm20ResourceMgr::DeleteTpm20Context(this[17], (struct Tpm20Context *)&v4[-2].Blink, 0);
    v2 = (KSPIN_LOCK *)(this + 14);
  }
  v6 = this[20];
  if ( v6 )
    TpmSWAntiHammeringMgr::`scalar deleting destructor'(v6, v5);
  (*((void (__fastcall **)(PKDPC, Tpm20ResourceMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 208))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    this[19]);
  (*((void (__fastcall **)(PKDPC, Tpm20ResourceMgr *))WPP_MAIN_CB.Queue.Wcb.CurrentIrp + 208))(
    WPP_MAIN_CB.Queue.Wcb.BufferChainingDpc,
    this[7]);
}

```

## disassembly

```asm
0x14001b974  mov     [rsp+arg_0], rbx
0x14001b979  mov     [rsp+arg_8], rsi
0x14001b97e  push    rdi
0x14001b97f  sub     rsp, 20h
0x14001b983  mov     rbx, rcx
0x14001b986  lea     rdx, [rcx+70h]
0x14001b98a  add     rcx, 78h ; 'x'
0x14001b98e  jmp     short loc_14001B9AB
0x14001b990  mov     rcx, [rbx+88h]; this
0x14001b997  lea     rdx, [rax-18h]; struct Tpm20Context *
0x14001b99b  xor     r8d, r8d; bool
0x14001b99e  call    ?DeleteTpm20Context@Tpm20ResourceMgr@@QEAAXPEAVTpm20Context@@_N@Z; Tpm20ResourceMgr::DeleteTpm20Context(Tpm20Context *,bool)
0x14001b9a3  lea     rdx, [rbx+70h]; Lock
0x14001b9a7  lea     rcx, [rbx+78h]; ListHead
0x14001b9ab  call    cs:__imp_ExInterlockedRemoveHeadList
0x14001b9b2  nop     dword ptr [rax+rax+00h]
0x14001b9b7  test    rax, rax
0x14001b9ba  jnz     short loc_14001B990
0x14001b9bc  mov     rcx, [rbx+0A0h]; this
0x14001b9c3  test    rcx, rcx
0x14001b9c6  jz      short loc_14001B9CD
0x14001b9c8  call    ??_GTpmSWAntiHammeringMgr@@QEAAPEAXI@Z; TpmSWAntiHammeringMgr::`scalar deleting destructor'(uint)
0x14001b9cd  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001b9d4  mov     rdx, [rbx+98h]
0x14001b9db  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001b9e2  mov     rax, [rax+680h]
0x14001b9e9  call    _guard_dispatch_icall
0x14001b9ee  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14001b9f5  mov     rdx, [rbx+38h]
0x14001b9f9  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+40h
0x14001ba00  mov     rax, [rax+680h]
0x14001ba07  call    _guard_dispatch_icall
0x14001ba0c  mov     rbx, [rsp+28h+arg_0]
0x14001ba11  mov     rsi, [rsp+28h+arg_8]
0x14001ba16  add     rsp, 20h
0x14001ba1a  pop     rdi
0x14001ba1b  retn
```
