# SqospSetVolumeStatsTimer

- ea: `0x140007824`
- end: `0x1400078a0`
- name: `SqospSetVolumeStatsTimer`
- size: `124`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140001ab0`
- `0x140003f00`
- `0x1400077b0`

## callees

- `0x140007824`

## import_xrefs

- `ntoskrnl!KeSetTimerEx` at `0x140007888`
- `ntoskrnl!KeSetTimerEx` at `0x140007888`
- `FLTMGR!FltReferenceContext` at `0x140007868`
- `FLTMGR!FltReferenceContext` at `0x140007868`

## pseudocode

```c
void __fastcall SqospSetVolumeStatsTimer(__int64 a1)
{
  unsigned __int64 v2; // rax
  __int64 v3; // rbx

  if ( !_interlockedbittestandset((volatile signed __int32 *)(a1 + 4160), 0) )
  {
    v2 = *(_QWORD *)(a1 + 4296);
    if ( MEMORY[0xFFFFF78000000008] >= v2 )
      v3 = -10000000;
    else
      v3 = MEMORY[0xFFFFF78000000008] - v2 - 200000;
    FltReferenceContext((PFLT_CONTEXT)a1);
    KeSetTimerEx((PKTIMER)(a1 + 4168), (LARGE_INTEGER)v3, 0, (PKDPC)(a1 + 4232));
  }
}

```

## disassembly

```asm
0x140007824  mov     [rsp+arg_0], rbx
0x140007829  push    rdi
0x14000782a  sub     rsp, 20h
0x14000782e  lock bts dword ptr [rcx+1040h], 0
0x140007837  mov     rdi, rcx
0x14000783a  jb      short loc_140007894
0x14000783c  mov     rbx, 0FFFFF78000000008h
0x140007846  mov     rbx, [rbx]
0x140007849  mov     rax, [rcx+10C8h]
0x140007850  cmp     rbx, rax
0x140007853  jnb     short loc_140007861
0x140007855  sub     rbx, rax
0x140007858  sub     rbx, 30D40h
0x14000785f  jmp     short loc_140007868
0x140007861  mov     rbx, 0FFFFFFFFFF676980h
0x140007868  call    cs:__imp_FltReferenceContext
0x14000786f  nop     dword ptr [rax+rax+00h]
0x140007874  lea     r9, [rdi+1088h]; Dpc
0x14000787b  xor     r8d, r8d; Period
0x14000787e  lea     rcx, [rdi+1048h]; Timer
0x140007885  mov     rdx, rbx; DueTime
0x140007888  call    cs:__imp_KeSetTimerEx
0x14000788f  nop     dword ptr [rax+rax+00h]
0x140007894  mov     rbx, [rsp+28h+arg_0]
0x140007899  add     rsp, 20h
0x14000789d  pop     rdi
0x14000789e  retn
```
