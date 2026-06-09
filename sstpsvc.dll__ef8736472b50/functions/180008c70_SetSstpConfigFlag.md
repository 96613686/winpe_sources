# SetSstpConfigFlag

- ea: `0x180008c70`
- end: `0x180008cd0`
- name: `SetSstpConfigFlag`
- size: `96`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000bd24`
- `0x18000d444`
- `0x1800158c0`

## callees

- `0x180008c70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c8c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180008c8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180008cc4`

## pseudocode

```c
void __fastcall SetSstpConfigFlag(int a1, int a2)
{
  RTL_SRWLOCK *v4; // rcx

  AcquireSRWLockExclusive((PSRWLOCK)SstpSvcGlobals + 96);
  v4 = (RTL_SRWLOCK *)SstpSvcGlobals;
  if ( a2 )
    *((_DWORD *)SstpSvcGlobals + 194) |= a1;
  else
    *((_DWORD *)SstpSvcGlobals + 194) &= ~a1;
  ReleaseSRWLockExclusive(v4 + 96);
}

```

## disassembly

```asm
0x180008c70  mov     [rsp+arg_0], rbx
0x180008c75  push    rdi
0x180008c76  sub     rsp, 20h
0x180008c7a  mov     edi, ecx
0x180008c7c  mov     ebx, edx
0x180008c7e  mov     rcx, cs:SstpSvcGlobals
0x180008c85  add     rcx, 300h; SRWLock
0x180008c8c  call    cs:__imp_AcquireSRWLockExclusive
0x180008c93  nop     dword ptr [rax+rax+00h]
0x180008c98  mov     rcx, cs:SstpSvcGlobals
0x180008c9f  test    ebx, ebx
0x180008ca1  jz      short loc_180008CAB
0x180008ca3  or      [rcx+308h], edi
0x180008ca9  jmp     short loc_180008CB3
0x180008cab  not     edi
0x180008cad  and     [rcx+308h], edi
0x180008cb3  add     rcx, 300h
0x180008cba  mov     rbx, [rsp+28h+arg_0]
0x180008cbf  add     rsp, 20h
0x180008cc3  pop     rdi
0x180008cc4  jmp     cs:__imp_ReleaseSRWLockExclusive
```
