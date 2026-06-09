# USBC_PnpComplete

- ea: `0x1400052c0`
- end: `0x14000533f`
- name: `USBC_PnpComplete`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400052c0`
- `0x1400054a0`
- `0x14000e210`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400052fe`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400052fe`

## pseudocode

```c
__int64 __fastcall USBC_PnpComplete(__int64 a1, __int64 a2, __int64 a3)
{
  if ( *(_BYTE *)(*(_QWORD *)(a2 + 184) + 1LL) == 4 && *(_DWORD *)(a3 + 12) == 5 )
  {
    FreeInterfaceList(a3, 0);
    *(_DWORD *)(a3 + 12) = 6;
  }
  if ( *(_BYTE *)(a2 + 65) )
    *(_BYTE *)(*(_QWORD *)(a2 + 184) + 3LL) |= 1u;
  UsbcReleaseRemoveLock(a3, a2);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a3 + 200), (PVOID)a2, 0x20u);
  return 0;
}

```

## disassembly

```asm
0x1400052c0  mov     [rsp+arg_0], rbx
0x1400052c5  push    rdi
0x1400052c6  sub     rsp, 20h
0x1400052ca  mov     rax, [rdx+0B8h]
0x1400052d1  mov     rdi, r8
0x1400052d4  mov     rbx, rdx
0x1400052d7  cmp     byte ptr [rax+1], 4
0x1400052db  jz      short loc_140005325
0x1400052dd  cmp     byte ptr [rbx+41h], 0
0x1400052e1  jnz     short loc_140005318
0x1400052e3  mov     rdx, rbx
0x1400052e6  mov     rcx, rdi
0x1400052e9  call    UsbcReleaseRemoveLock
0x1400052ee  lea     rcx, [rdi+0C8h]; RemoveLock
0x1400052f5  mov     r8d, 20h ; ' '; RemlockSize
0x1400052fb  mov     rdx, rbx; Tag
0x1400052fe  call    cs:__imp_IoReleaseRemoveLockEx
0x140005305  nop     dword ptr [rax+rax+00h]
0x14000530a  mov     rbx, [rsp+28h+arg_0]
0x14000530f  xor     eax, eax
0x140005311  add     rsp, 20h
0x140005315  pop     rdi
0x140005316  retn
0x140005318  mov     rax, [rbx+0B8h]
0x14000531f  or      byte ptr [rax+3], 1
0x140005323  jmp     short loc_1400052E3
0x140005325  cmp     dword ptr [r8+0Ch], 5
0x14000532a  jnz     short loc_1400052DD
0x14000532c  xor     edx, edx
0x14000532e  mov     rcx, rdi
0x140005331  call    FreeInterfaceList
0x140005336  mov     dword ptr [rdi+0Ch], 6
0x14000533d  jmp     short loc_1400052DD
```
