# VmpReadWriteCompletionRoutine

- ea: `0x140002b30`
- end: `0x140002b91`
- name: `VmpReadWriteCompletionRoutine`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002b30`
- `0x140005090`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002b7c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140002b7c`

## pseudocode

```c
__int64 __fastcall VmpReadWriteCompletionRoutine(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  __int64 v3; // r9

  v2 = *(_QWORD *)(a1 + 64);
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  v3 = *(_QWORD *)(a2 + 184);
  if ( *(_QWORD *)(v3 + 24) )
    (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64))(*(_QWORD *)(v2 + 8) + 328LL))(
      *(_QWORD *)(v2 + 224),
      a2,
      v3 + 24,
      v3 + 16);
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(v2 + 112));
  return 0;
}

```

## disassembly

```asm
0x140002b30  push    rbx
0x140002b32  sub     rsp, 30h
0x140002b36  cmp     byte ptr [rdx+41h], 0
0x140002b3a  mov     rbx, [rcx+40h]
0x140002b3e  jz      short loc_140002B4B
0x140002b40  mov     rcx, [rdx+0B8h]
0x140002b47  or      byte ptr [rcx+3], 1
0x140002b4b  mov     r9, [rdx+0B8h]
0x140002b52  cmp     qword ptr [r9+18h], 0
0x140002b57  lea     r8, [r9+18h]
0x140002b5b  jz      short loc_140002B78
0x140002b5d  mov     rax, [rbx+8]
0x140002b61  add     r9, 10h
0x140002b65  mov     rcx, [rbx+0E0h]
0x140002b6c  mov     rax, [rax+148h]
0x140002b73  call    _guard_dispatch_icall
0x140002b78  mov     rcx, [rbx+70h]; RunRefCacheAware
0x140002b7c  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x140002b83  nop     dword ptr [rax+rax+00h]
0x140002b88  xor     eax, eax
0x140002b8a  add     rsp, 30h
0x140002b8e  pop     rbx
0x140002b8f  retn
```
