# WanpFindInterfaceGivenIndex

- ea: `0x14000e4e4`
- end: `0x14000e529`
- name: `WanpFindInterfaceGivenIndex`
- size: `69`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140004124`
- `0x14000fdc4`
- `0x140011618`
- `0x1400129e4`
- `0x14001324c`

## callees

- `0x14000e4e4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e50b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000e50b`

## pseudocode

```c
__int64 __fastcall WanpFindInterfaceGivenIndex(int a1)
{
  __int64 i; // rbx

  for ( i = g_leIfList; (__int64 *)i != &g_leIfList; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 32) == a1 )
    {
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(i + 56));
      _InterlockedIncrement((volatile signed __int32 *)(i + 64));
      return i;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000e4e4  push    rbx
0x14000e4e6  sub     rsp, 20h
0x14000e4ea  mov     rbx, cs:g_leIfList
0x14000e4f1  lea     rax, g_leIfList
0x14000e4f8  cmp     rbx, rax
0x14000e4fb  jz      short loc_14000E520
0x14000e4fd  cmp     [rbx+20h], ecx
0x14000e500  jz      short loc_14000E507
0x14000e502  mov     rbx, [rbx]
0x14000e505  jmp     short loc_14000E4F1
0x14000e507  lea     rcx, [rbx+38h]; SpinLock
0x14000e50b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000e512  nop     dword ptr [rax+rax+00h]
0x14000e517  lock inc dword ptr [rbx+40h]
0x14000e51b  mov     rax, rbx
0x14000e51e  jmp     short loc_14000E522
0x14000e520  xor     eax, eax
0x14000e522  add     rsp, 20h
0x14000e526  pop     rbx
0x14000e527  retn
```
