# RtlInitializeScalableMrswLock

- ea: `0x14000d634`
- end: `0x14000d671`
- name: `RtlInitializeScalableMrswLock`
- size: `61`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x14000d4e4`
- `0x14000f130`
- `0x14001a078`
- `0x14001b1fc`
- `0x1400333cc`

## callees

- `0x14000d634`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000d63d`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000d63d`

## pseudocode

```c
__int64 __fastcall RtlInitializeScalableMrswLock(__int64 a1)
{
  __int64 v2; // rdx
  __int64 result; // rax

  KeInitializeSpinLock((PKSPIN_LOCK)a1);
  v2 = 0;
  *(_DWORD *)(a1 + 8) = 3;
  do
  {
    result = ++v2 << 6;
    *(_DWORD *)((v2 << 6) + a1) = 0;
  }
  while ( v2 != 4 );
  return result;
}

```

## disassembly

```asm
0x14000d634  push    rbx
0x14000d636  sub     rsp, 20h
0x14000d63a  mov     rbx, rcx
0x14000d63d  call    cs:__imp_KeInitializeSpinLock
0x14000d644  nop     dword ptr [rax+rax+00h]
0x14000d649  xor     edx, edx
0x14000d64b  mov     dword ptr [rbx+8], 3
0x14000d652  lea     rax, [rdx+1]
0x14000d656  inc     rdx
0x14000d659  shl     rax, 6
0x14000d65d  mov     dword ptr [rax+rbx], 0
0x14000d664  cmp     rdx, 4
0x14000d668  jnz     short loc_14000D652
0x14000d66a  add     rsp, 20h
0x14000d66e  pop     rbx
0x14000d66f  retn
```
