# AutoTokenImpersonate::~AutoTokenImpersonate(void)

- ea: `0x180076998`
- end: `0x1800769f6`
- name: `??1AutoTokenImpersonate@@QEAA@XZ`
- size: `94`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800760f0`
- `0x1800768fc`
- `0x18009a970`
- `0x1800bd448`

## callees

- `0x180076998`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800769ee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800769ee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800769ca`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800769ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800769af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800769d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800769af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800769d8`

## pseudocode

```c
void __fastcall AutoTokenImpersonate::~AutoTokenImpersonate(HANDLE *this)
{
  HANDLE v2; // rcx

  if ( *((_DWORD *)this + 2) )
  {
    v2 = *this;
    if ( v2 )
      ImpersonateLoggedOnUser(v2);
    else
      RevertToSelf();
    if ( *this )
    {
      CloseHandle(*this);
      *this = 0;
    }
    *((_DWORD *)this + 2) = 0;
  }
  if ( *this )
  {
    CloseHandle(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x180076998  push    rbx
0x18007699a  sub     rsp, 20h
0x18007699e  cmp     dword ptr [rcx+8], 0
0x1800769a2  mov     rbx, rcx
0x1800769a5  jnz     short loc_1800769C2
0x1800769a7  mov     rcx, [rbx]; hObject
0x1800769aa  test    rcx, rcx
0x1800769ad  jz      short loc_1800769BC
0x1800769af  call    cs:__imp_CloseHandle
0x1800769b5  mov     qword ptr [rbx], 0
0x1800769bc  add     rsp, 20h
0x1800769c0  pop     rbx
0x1800769c1  retn
0x1800769c2  mov     rcx, [rcx]; hToken
0x1800769c5  test    rcx, rcx
0x1800769c8  jz      short loc_1800769EE
0x1800769ca  call    cs:__imp_ImpersonateLoggedOnUser
0x1800769d0  mov     rcx, [rbx]; hObject
0x1800769d3  test    rcx, rcx
0x1800769d6  jz      short loc_1800769E5
0x1800769d8  call    cs:__imp_CloseHandle
0x1800769de  mov     qword ptr [rbx], 0
0x1800769e5  mov     dword ptr [rbx+8], 0
0x1800769ec  jmp     short loc_1800769A7
0x1800769ee  call    cs:__imp_RevertToSelf
0x1800769f4  jmp     short loc_1800769D0
```
