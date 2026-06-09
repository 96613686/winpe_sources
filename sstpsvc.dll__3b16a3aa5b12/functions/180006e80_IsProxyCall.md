# IsProxyCall

- ea: `0x180006e80`
- end: `0x180006ee1`
- name: `IsProxyCall`
- size: `97`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180006b64`
- `0x18000a620`
- `0x18000afbc`
- `0x18000df30`

## callees

- `0x180006e80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006e9b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006e9b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006eb5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006eb5`

## pseudocode

```c
_BOOL8 __fastcall IsProxyCall(__int64 a1)
{
  int v2; // edi

  AcquireSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  v2 = *((_DWORD *)SstpSvcGlobals + 194);
  ReleaseSRWLockShared((PSRWLOCK)SstpSvcGlobals + 96);
  return (v2 & 1) != 0 && a1 && *(_QWORD *)(a1 + 624) != 0;
}

```

## disassembly

```asm
0x180006e80  mov     [rsp+arg_0], rbx
0x180006e85  push    rdi
0x180006e86  sub     rsp, 20h
0x180006e8a  mov     rbx, rcx
0x180006e8d  mov     rcx, cs:SstpSvcGlobals
0x180006e94  add     rcx, 300h; SRWLock
0x180006e9b  call    cs:__imp_AcquireSRWLockShared
0x180006ea1  mov     rcx, cs:SstpSvcGlobals
0x180006ea8  mov     edi, [rcx+308h]
0x180006eae  add     rcx, 300h; SRWLock
0x180006eb5  call    cs:__imp_ReleaseSRWLockShared
0x180006ebb  bt      edi, 0
0x180006ebf  jb      short loc_180006ECE
0x180006ec1  xor     eax, eax
0x180006ec3  mov     rbx, [rsp+28h+arg_0]
0x180006ec8  add     rsp, 20h
0x180006ecc  pop     rdi
0x180006ecd  retn
0x180006ece  test    rbx, rbx
0x180006ed1  jz      short loc_180006EC1
0x180006ed3  xor     eax, eax
0x180006ed5  cmp     [rbx+270h], rax
0x180006edc  setnz   al
0x180006edf  jmp     short loc_180006EC3
```
