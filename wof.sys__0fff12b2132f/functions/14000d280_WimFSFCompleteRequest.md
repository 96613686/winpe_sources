# WimFSFCompleteRequest

- ea: `0x14000d280`
- end: `0x14000d2f4`
- name: `WimFSFCompleteRequest`
- size: `116`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009000`

## callees

- `0x14000d280`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14000d2c7`
- `ntoskrnl!KeSetEvent` at `0x14000d2c7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d2e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14000d2e1`

## pseudocode

```c
void __fastcall WimFSFCompleteRequest(PVOID Entry)
{
  int v1; // eax
  __int64 v3; // rcx

  v1 = *((_DWORD *)Entry + 27);
  if ( v1 < 0 )
  {
    v3 = *((_QWORD *)Entry + 15);
    if ( *(int *)(v3 + 32) >= 0 )
      *(_DWORD *)(v3 + 32) = v1;
  }
  else
  {
    _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)Entry + 15) + 36LL), *((_DWORD *)Entry + 28));
  }
  if ( _InterlockedExchangeAdd(*((volatile signed __int32 **)Entry + 15), 0xFFFFFFFF) == 1 )
    KeSetEvent((PRKEVENT)(*((_QWORD *)Entry + 15) + 8LL), 0, 0);
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*((_QWORD *)Entry + 4) + 640LL), Entry);
}

```

## disassembly

```asm
0x14000d280  push    rbx
0x14000d282  sub     rsp, 20h
0x14000d286  mov     eax, [rcx+6Ch]
0x14000d289  mov     rbx, rcx
0x14000d28c  test    eax, eax
0x14000d28e  js      short loc_14000D29D
0x14000d290  mov     rdx, [rcx+78h]
0x14000d294  mov     eax, [rcx+70h]
0x14000d297  lock add [rdx+24h], eax
0x14000d29b  jmp     short loc_14000D2AA
0x14000d29d  mov     rcx, [rcx+78h]
0x14000d2a1  cmp     dword ptr [rcx+20h], 0
0x14000d2a5  jl      short loc_14000D2AA
0x14000d2a7  mov     [rcx+20h], eax
0x14000d2aa  mov     rcx, [rbx+78h]
0x14000d2ae  or      eax, 0FFFFFFFFh
0x14000d2b1  lock xadd [rcx], eax
0x14000d2b5  cmp     eax, 1
0x14000d2b8  jnz     short loc_14000D2D3
0x14000d2ba  mov     rcx, [rbx+78h]
0x14000d2be  xor     r8d, r8d; Wait
0x14000d2c1  add     rcx, 8; Event
0x14000d2c5  xor     edx, edx; Increment
0x14000d2c7  call    cs:__imp_KeSetEvent
0x14000d2ce  nop     dword ptr [rax+rax+00h]
0x14000d2d3  mov     rcx, [rbx+20h]
0x14000d2d7  mov     rdx, rbx; Entry
0x14000d2da  add     rcx, 280h; Lookaside
0x14000d2e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x14000d2e8  nop     dword ptr [rax+rax+00h]
0x14000d2ed  add     rsp, 20h
0x14000d2f1  pop     rbx
0x14000d2f2  retn
```
