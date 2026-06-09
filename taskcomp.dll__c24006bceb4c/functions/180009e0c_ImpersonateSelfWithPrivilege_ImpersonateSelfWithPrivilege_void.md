# ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)

- ea: `0x180009e0c`
- end: `0x180009e3a`
- name: `??1ImpersonateSelfWithPrivilege@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000ac28`
- `0x180012560`
- `0x18002f129`
- `0x18002f718`
- `0x18002f73c`

## callees

- `0x180004e1c`
- `0x180009e0c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009e1f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180009e1f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009e27`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009e27`

## pseudocode

```c
void __fastcall ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(HANDLE *this)
{
  if ( *this )
    SetThreadToken(0, *this);
  else
    RevertToSelf();
  wmi::AutoHandle::Close((wmi::AutoHandle *)this);
}

```

## disassembly

```asm
0x180009e0c  push    rbx
0x180009e0e  sub     rsp, 20h
0x180009e12  mov     rdx, [rcx]; Token
0x180009e15  mov     rbx, rcx
0x180009e18  test    rdx, rdx
0x180009e1b  jz      short loc_180009E27
0x180009e1d  xor     ecx, ecx; Thread
0x180009e1f  call    cs:__imp_SetThreadToken
0x180009e25  jmp     short loc_180009E2D
0x180009e27  call    cs:__imp_RevertToSelf
0x180009e2d  mov     rcx, rbx; this
0x180009e30  add     rsp, 20h
0x180009e34  pop     rbx
0x180009e35  jmp     ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
```
