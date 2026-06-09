# GetSstpConfigFlag

- ea: `0x180006f00`
- end: `0x180006f53`
- name: `GetSstpConfigFlag`
- size: `83`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800056e0`
- `0x18000afb0`
- `0x180014900`
- `0x1800151e0`
- `0x180015500`
- `0x1800158c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006f16`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006f16`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006f3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006f3e`

## pseudocode

```c
_BOOL8 __fastcall GetSstpConfigFlag(int a1)
{
  BOOL v2; // ebx

  AcquireSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  v2 = (a1 & *((_DWORD *)SstpSvcGlobals + 194)) != 0;
  ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  return v2;
}

```

## disassembly

```asm
0x180006f00  push    rbx
0x180006f02  sub     rsp, 20h
0x180006f06  mov     ebx, ecx
0x180006f08  mov     rcx, cs:SstpSvcGlobals
0x180006f0f  add     rcx, 300h; SRWLock
0x180006f16  call    cs:__imp_AcquireSRWLockShared
0x180006f1d  nop     dword ptr [rax+rax+00h]
0x180006f22  mov     rcx, cs:SstpSvcGlobals
0x180006f29  test    [rcx+308h], ebx
0x180006f2f  mov     ebx, 0
0x180006f34  setnz   bl
0x180006f37  add     rcx, 300h; SRWLock
0x180006f3e  call    cs:__imp_ReleaseSRWLockShared
0x180006f45  nop     dword ptr [rax+rax+00h]
0x180006f4a  mov     eax, ebx
0x180006f4c  add     rsp, 20h
0x180006f50  pop     rbx
0x180006f51  retn
```
