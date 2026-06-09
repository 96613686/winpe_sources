# TmpTxActionDoPrePrepareComplete

- ea: `0x14000c320`
- end: `0x14000c3bb`
- name: `TmpTxActionDoPrePrepareComplete`
- size: `155`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14001eb30`

## callees

- `0x14000c320`
- `0x14000c3c4`
- `0x140011300`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14000c378`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000c378`

## pseudocode

```c
__int64 __fastcall TmpTxActionDoPrePrepareComplete(__int64 a1)
{
  __int64 v1; // rbx

  v1 = a1;
  *(_DWORD *)(a1 + 192) = 11;
  if ( (*(_DWORD *)(a1 + 196) & 4) != 0 )
  {
    *(_DWORD *)(a1 + 192) = 11;
    return TmpTxActionDoPrepare(a1);
  }
  else
  {
    if ( (*(_DWORD *)(a1 + 196) & 0x400) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 196) & 0x100) == 0 )
        a1 = *(_QWORD *)(a1 + 272);
      KeWaitForSingleObject((PVOID)(a1 + 704), Executive, 0, 0, 0);
    }
    return TmpNotifyEnlistment(*(PVOID *)(v1 + 240), 273);
  }
}

```

## disassembly

```asm
0x14000c320  push    rbx
0x14000c322  sub     rsp, 40h
0x14000c326  mov     rbx, rcx
0x14000c329  mov     ecx, 0Bh
0x14000c32e  mov     [rbx+0C0h], ecx
0x14000c334  mov     eax, [rbx+0C4h]
0x14000c33a  test    al, 4
0x14000c33c  jnz     short loc_14000C3A6
0x14000c33e  mov     eax, [rbx+0C4h]
0x14000c344  bt      eax, 0Ah
0x14000c348  jnb     short loc_14000C384
0x14000c34a  mov     eax, [rbx+0C4h]
0x14000c350  mov     rcx, rbx
0x14000c353  bt      eax, 8
0x14000c357  jb      short loc_14000C360
0x14000c359  mov     rcx, [rbx+110h]
0x14000c360  add     rcx, 2C0h; Object
0x14000c367  mov     [rsp+48h+Timeout], 0; Timeout
0x14000c370  xor     r9d, r9d; Alertable
0x14000c373  xor     r8d, r8d; WaitMode
0x14000c376  xor     edx, edx; WaitReason
0x14000c378  call    cs:__imp_KeWaitForSingleObject
0x14000c37f  nop     dword ptr [rax+rax+00h]
0x14000c384  mov     rcx, [rbx+0F0h]; Object
0x14000c38b  mov     r9b, 1
0x14000c38e  mov     dl, r9b
0x14000c391  mov     dword ptr [rsp+48h+Timeout], 111h; int
0x14000c399  mov     r8d, 10h
0x14000c39f  call    TmpNotifyEnlistment
0x14000c3a4  jmp     short loc_14000C3B4
0x14000c3a6  mov     [rbx+0C0h], ecx
0x14000c3ac  mov     rcx, rbx; int
0x14000c3af  call    TmpTxActionDoPrepare
0x14000c3b4  add     rsp, 40h
0x14000c3b8  pop     rbx
0x14000c3b9  retn
```
