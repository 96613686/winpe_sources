# ImpersonateSelfWithPrivilege::~ImpersonateSelfWithPrivilege(void)

- ea: `0x18000a384`
- end: `0x18000a3be`
- name: `??1ImpersonateSelfWithPrivilege@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(ImpersonateSelfWithPrivilege *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b218`
- `0x1800130c0`
- `0x18003127a`
- `0x180031869`
- `0x18003188d`

## callees

- `0x180005094`
- `0x18000a384`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a397`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000a397`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a3a5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000a3a5`

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
0x18000a384  push    rbx
0x18000a386  sub     rsp, 20h
0x18000a38a  mov     rdx, [rcx]; Token
0x18000a38d  mov     rbx, rcx
0x18000a390  test    rdx, rdx
0x18000a393  jz      short loc_18000A3A5
0x18000a395  xor     ecx, ecx; Thread
0x18000a397  call    cs:__imp_SetThreadToken
0x18000a39e  nop     dword ptr [rax+rax+00h]
0x18000a3a3  jmp     short loc_18000A3B1
0x18000a3a5  call    cs:__imp_RevertToSelf
0x18000a3ac  nop     dword ptr [rax+rax+00h]
0x18000a3b1  mov     rcx, rbx; this
0x18000a3b4  add     rsp, 20h
0x18000a3b8  pop     rbx
0x18000a3b9  jmp     ?Close@AutoHandle@wmi@@QEAAXXZ; wmi::AutoHandle::Close(void)
```
