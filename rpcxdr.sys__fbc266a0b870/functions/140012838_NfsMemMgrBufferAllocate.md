# NfsMemMgrBufferAllocate

- ea: `0x140012838`
- end: `0x1400128a3`
- name: `NfsMemMgrBufferAllocate`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `2`
- tags: ``

## callers

- `0x140002e4c`
- `0x140003dbc`
- `0x140006610`
- `0x140008d78`
- `0x1400090f4`
- `0x140009540`
- `0x14000993c`
- `0x14000a2d0`
- `0x14000a814`
- `0x14000aac4`
- `0x14000b624`
- `0x14000bf88`
- `0x14000c56c`
- `0x14000c7f4`
- `0x14000cb78`
- `0x140011010`
- `0x140011a4c`

## callees

- `0x140012838`
- `0x140012bbc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001287b`
- `ntoskrnl!ExAllocatePool2` at `0x14001287b`

## pseudocode

```c
__int64 __fastcall NfsMemMgrBufferAllocate(__int64 a1, __int64 a2, int a3, __int64 *a4)
{
  __int64 Pool2; // rax
  unsigned int v6; // ecx
  unsigned int v7; // r9d
  __int64 v8; // r10
  __int64 v10; // [rsp+48h] [rbp+20h] BYREF

  if ( a3 )
  {
    v10 = 0;
    if ( (int)NfsMemMgrpMapPoolTypeWithPoolFlag(a1, &v10) < 0 )
    {
      Pool2 = 0;
    }
    else
    {
      Pool2 = ExAllocatePool2(v10 | 2, v8, v7);
      if ( Pool2 )
      {
        v6 = 0;
        goto LABEL_8;
      }
    }
    v6 = -1073741670;
    goto LABEL_8;
  }
  Pool2 = 0;
  v6 = -1073741811;
LABEL_8:
  *a4 = Pool2;
  return v6;
}

```

## disassembly

```asm
0x140012838  push    rbx
0x14001283a  sub     rsp, 20h
0x14001283e  mov     r10d, r8d
0x140012841  mov     rbx, r9
0x140012844  mov     r9d, edx
0x140012847  test    r8d, r8d
0x14001284a  jnz     short loc_140012855
0x14001284c  xor     eax, eax
0x14001284e  mov     ecx, 0C000000Dh
0x140012853  jmp     short loc_140012897
0x140012855  lea     rdx, [rsp+28h+arg_18]
0x14001285a  mov     [rsp+28h+arg_18], 0
0x140012863  call    NfsMemMgrpMapPoolTypeWithPoolFlag
0x140012868  test    eax, eax
0x14001286a  js      short loc_140012890
0x14001286c  mov     rcx, [rsp+28h+arg_18]
0x140012871  mov     rdx, r10
0x140012874  or      rcx, 2
0x140012878  mov     r8d, r9d
0x14001287b  call    cs:__imp_ExAllocatePool2
0x140012882  nop     dword ptr [rax+rax+00h]
0x140012887  test    rax, rax
0x14001288a  jz      short loc_140012892
0x14001288c  xor     ecx, ecx
0x14001288e  jmp     short loc_140012897
0x140012890  xor     eax, eax
0x140012892  mov     ecx, 0C000009Ah
0x140012897  mov     [rbx], rax
0x14001289a  mov     eax, ecx
0x14001289c  add     rsp, 20h
0x1400128a0  pop     rbx
0x1400128a1  retn
```
