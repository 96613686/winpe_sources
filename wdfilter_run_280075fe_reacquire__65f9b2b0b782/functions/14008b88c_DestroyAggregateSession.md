# DestroyAggregateSession

- ea: `0x14008b88c`
- end: `0x14008b8ec`
- name: `DestroyAggregateSession`
- size: `96`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14008b720`
- `0x14008bacc`
- `0x14008bc34`

## callees

- `0x14008b5ec`
- `0x14008b88c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14008b8c8`
- `ntoskrnl!ExDeleteResourceLite` at `0x14008b8c8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b8ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b8d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b8ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008b8d9`

## pseudocode

```c
void __fastcall DestroyAggregateSession(char *P)
{
  void *v2; // rcx

  if ( P )
  {
    CancelTimerCallbacksAndDeleteTimer();
    v2 = (void *)*((_QWORD *)P + 33);
    if ( v2 )
      ExFreePoolWithTag(v2, 0);
    if ( !byte_140026739 )
      ExDeleteResourceLite((PERESOURCE)(P + 272));
    ExFreePoolWithTag(P, 0);
  }
}

```

## disassembly

```asm
0x14008b88c  test    rcx, rcx
0x14008b88f  jz      short locret_14008B8EA
0x14008b891  push    rbx
0x14008b892  sub     rsp, 20h
0x14008b896  mov     rbx, rcx
0x14008b899  call    CancelTimerCallbacksAndDeleteTimer
0x14008b89e  mov     rcx, [rbx+108h]; P
0x14008b8a5  test    rcx, rcx
0x14008b8a8  jz      short loc_14008B8B8
0x14008b8aa  xor     edx, edx; Tag
0x14008b8ac  call    cs:__imp_ExFreePoolWithTag
0x14008b8b3  nop     dword ptr [rax+rax+00h]
0x14008b8b8  cmp     cs:byte_140026739, 0
0x14008b8bf  jnz     short loc_14008B8D4
0x14008b8c1  lea     rcx, [rbx+110h]; Resource
0x14008b8c8  call    cs:__imp_ExDeleteResourceLite
0x14008b8cf  nop     dword ptr [rax+rax+00h]
0x14008b8d4  xor     edx, edx; Tag
0x14008b8d6  mov     rcx, rbx; P
0x14008b8d9  call    cs:__imp_ExFreePoolWithTag
0x14008b8e0  nop     dword ptr [rax+rax+00h]
0x14008b8e5  add     rsp, 20h
0x14008b8e9  pop     rbx
0x14008b8ea  retn
```
