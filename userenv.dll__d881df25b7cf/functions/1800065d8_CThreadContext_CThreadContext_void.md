# CThreadContext::~CThreadContext(void)

- ea: `0x1800065d8`
- end: `0x180006616`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `62`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180006160`
- `0x180006ce0`
- `0x180006e18`
- `0x180013748`
- `0x180013984`
- `0x180013a54`
- `0x1800197f0`
- `0x18001b3e8`
- `0x18001c95e`
- `0x18001caa0`
- `0x18001cab2`
- `0x18001cac4`

## callees

- `0x180005a48`
- `0x180005af4`
- `0x1800062ac`
- `0x1800065d8`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180006601`
- `RPCRT4!RpcRevertToSelf` at `0x180006601`

## pseudocode

```c
void __fastcall CThreadContext::~CThreadContext(CThreadContext *this)
{
  CThreadContext::RevertPrivileges(this);
  CThreadContext::RevertToPreviousToken((HANDLE *)this);
  if ( *((_DWORD *)this + 5) )
  {
    RpcRevertToSelf();
    *((_DWORD *)this + 5) = 0;
  }
  CThreadContext::RevertToSelf(this);
}

```

## disassembly

```asm
0x1800065d8  push    rbx
0x1800065da  sub     rsp, 20h
0x1800065de  mov     rbx, rcx
0x1800065e1  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x1800065e6  mov     rcx, rbx; this
0x1800065e9  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x1800065ee  cmp     dword ptr [rbx+14h], 0
0x1800065f2  jnz     short loc_180006601
0x1800065f4  mov     rcx, rbx; this
0x1800065f7  add     rsp, 20h
0x1800065fb  pop     rbx
0x1800065fc  jmp     ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x180006601  call    cs:__imp_RpcRevertToSelf
0x180006608  nop     dword ptr [rax+rax+00h]
0x18000660d  mov     dword ptr [rbx+14h], 0
0x180006614  jmp     short loc_1800065F4
```
