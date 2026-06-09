# WanpAcquireResource

- ea: `0x140002b6c`
- end: `0x140002ba7`
- name: `WanpAcquireResource`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x1400028b0`
- `0x140002e60`
- `0x1400042f0`
- `0x14000f9c8`
- `0x140010448`
- `0x140011618`
- `0x1400120fc`
- `0x1400124bc`
- `0x140012e3c`
- `0x14001324c`
- `0x140013708`
- `0x140017130`
- `0x140017550`
- `0x140017738`
- `0x14001a078`

## callees

- `0x140002b6c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140002b95`
- `ntoskrnl!KeWaitForSingleObject` at `0x140002b95`

## pseudocode

```c
NTSTATUS __fastcall WanpAcquireResource(volatile signed __int32 *a1)
{
  NTSTATUS result; // eax

  result = _InterlockedIncrement(a1);
  if ( result != 1 )
    return KeWaitForSingleObject((PVOID)(a1 + 2), Executive, 0, 0, 0);
  return result;
}

```

## disassembly

```asm
0x140002b6c  sub     rsp, 38h
0x140002b70  mov     eax, 1
0x140002b75  lock xadd [rcx], eax
0x140002b79  inc     eax
0x140002b7b  cmp     eax, 1
0x140002b7e  jz      short loc_140002BA1
0x140002b80  add     rcx, 8; Object
0x140002b84  mov     [rsp+38h+Timeout], 0; Timeout
0x140002b8d  xor     r9d, r9d; Alertable
0x140002b90  xor     r8d, r8d; WaitMode
0x140002b93  xor     edx, edx; WaitReason
0x140002b95  call    cs:__imp_KeWaitForSingleObject
0x140002b9c  nop     dword ptr [rax+rax+00h]
0x140002ba1  add     rsp, 38h
0x140002ba5  retn
```
