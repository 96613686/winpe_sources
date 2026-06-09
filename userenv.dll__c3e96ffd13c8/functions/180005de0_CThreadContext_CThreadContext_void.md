# CThreadContext::~CThreadContext(void)

- ea: `0x180005de0`
- end: `0x180005e18`
- name: `??1CThreadContext@@QEAA@XZ`
- size: `56`
- prototype: `void __fastcall(CThreadContext *__hidden this)`
- caller_count: `12`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x1800059a4`
- `0x1800067b0`
- `0x180006904`
- `0x18001274c`
- `0x1800128cc`
- `0x180012998`
- `0x180017ee0`
- `0x18001995c`
- `0x18001adfc`
- `0x18001af32`
- `0x18001af44`
- `0x18001af56`

## callees

- `0x180005320`
- `0x1800053c4`
- `0x180005de0`
- `0x180005e20`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x180005e09`
- `RPCRT4!RpcRevertToSelf` at `0x180005e09`

## pseudocode

```c
void __fastcall CThreadContext::~CThreadContext(CThreadContext *this)
{
  CThreadContext::RevertPrivileges(this);
  CThreadContext::RevertToPreviousToken(this);
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
0x180005de0  push    rbx
0x180005de2  sub     rsp, 20h
0x180005de6  mov     rbx, rcx
0x180005de9  call    ?RevertPrivileges@CThreadContext@@QEAAJXZ; CThreadContext::RevertPrivileges(void)
0x180005dee  mov     rcx, rbx; this
0x180005df1  call    ?RevertToPreviousToken@CThreadContext@@QEAAXXZ; CThreadContext::RevertToPreviousToken(void)
0x180005df6  cmp     dword ptr [rbx+14h], 0
0x180005dfa  jnz     short loc_180005E09
0x180005dfc  mov     rcx, rbx; this
0x180005dff  add     rsp, 20h
0x180005e03  pop     rbx
0x180005e04  jmp     ?RevertToSelf@CThreadContext@@QEAAXXZ; CThreadContext::RevertToSelf(void)
0x180005e09  call    cs:__imp_RpcRevertToSelf
0x180005e0f  mov     dword ptr [rbx+14h], 0
0x180005e16  jmp     short loc_180005DFC
```
