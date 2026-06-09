# InpPrepareToQueueWorkerLocked

- ea: `0x140005cf0`
- end: `0x140005e30`
- name: `InpPrepareToQueueWorkerLocked`
- size: `320`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140001170`
- `0x140001370`
- `0x140001780`
- `0x140001ce0`
- `0x1400049a0`
- `0x140004cc0`
- `0x140005ca0`
- `0x1400081ec`
- `0x140008338`

## callees

- `0x140005cf0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140005d13`
- `ntoskrnl!KeSetEvent` at `0x140005d13`

## pseudocode

```c
char __fastcall InpPrepareToQueueWorkerLocked(__int64 a1, char a2, char a3)
{
  struct _KEVENT *v4; // rcx
  char result; // al
  int LockArray_high; // eax
  int v7; // ecx
  int v8; // r9d
  int v9; // r10d
  __int64 v10; // rax
  char v11; // cl

  if ( *(_DWORD *)(a1 + 1096) == 1 )
  {
    v4 = *(struct _KEVENT **)(a1 + 1216);
    if ( v4 )
    {
      KeSetEvent(v4, 0, 0);
      result = 0;
      *(_QWORD *)(a1 + 1216) = 0;
      *(_QWORD *)(a1 + 1128) = 0;
      return result;
    }
  }
  *(_DWORD *)(a1 + 1096) = 2;
  *(_QWORD *)(a1 + 1128) = 0;
  if ( !*(_QWORD *)(a1 + 1136) )
  {
    LockArray_high = HIDWORD(KeGetPcr()[1].LockArray);
    v7 = *(_DWORD *)(a1 + 1632);
    if ( v7 != LockArray_high )
    {
      v8 = *(_DWORD *)(a1 + 1636);
      if ( v8 != LockArray_high )
      {
        v9 = *(_DWORD *)(a1 + 1640);
        if ( v9 != LockArray_high )
        {
          if ( a2 || *(_BYTE *)(a1 + 1201) )
          {
            if ( v9 == -1 )
            {
              *(_BYTE *)(a1 + 1100) |= 2u;
              ++*(_QWORD *)(a1 + 1184);
              ++*(_DWORD *)(a1 + 1164);
              *(_DWORD *)(a1 + 1640) = LockArray_high;
              *(_QWORD *)(a1 + 1136) = *(_QWORD *)(a1 + 1624);
              return 1;
            }
          }
          else
          {
            if ( v7 == -1 )
            {
              *(_DWORD *)(a1 + 1632) = LockArray_high;
              v10 = 1496;
LABEL_14:
              ++*(_QWORD *)(a1 + 1192);
              *(_QWORD *)(a1 + 1136) = a1 + v10;
              v11 = *(_BYTE *)(a1 + 1100) & 0xFE | (a3 != 0);
              result = 1;
              ++*(_DWORD *)(a1 + 1164);
              *(_BYTE *)(a1 + 1100) = v11;
              return result;
            }
            if ( v8 == -1 )
            {
              *(_DWORD *)(a1 + 1636) = LockArray_high;
              v10 = 1560;
              goto LABEL_14;
            }
          }
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140005cf0  push    rbx
0x140005cf2  sub     rsp, 20h
0x140005cf6  cmp     dword ptr [rcx+448h], 1
0x140005cfd  mov     rbx, rcx
0x140005d00  jnz     short loc_140005D34
0x140005d02  mov     rcx, [rcx+4C0h]; Event
0x140005d09  test    rcx, rcx
0x140005d0c  jz      short loc_140005D34
0x140005d0e  xor     r8d, r8d; Wait
0x140005d11  xor     edx, edx; Increment
0x140005d13  call    cs:__imp_KeSetEvent
0x140005d1a  nop     dword ptr [rax+rax+00h]
0x140005d1f  xor     eax, eax
0x140005d21  mov     [rbx+4C0h], rax
0x140005d28  mov     [rbx+468h], rax
0x140005d2f  jmp     loc_140005E29
0x140005d34  xor     eax, eax
0x140005d36  mov     dword ptr [rbx+448h], 2
0x140005d40  mov     [rbx+468h], rax
0x140005d47  cmp     [rbx+470h], rax
0x140005d4e  jnz     loc_140005E27
0x140005d54  mov     eax, gs:1A4h
0x140005d5c  mov     ecx, [rbx+660h]
0x140005d62  cmp     ecx, eax
0x140005d64  jz      loc_140005E27
0x140005d6a  mov     r9d, [rbx+664h]
0x140005d71  cmp     r9d, eax
0x140005d74  jz      loc_140005E27
0x140005d7a  mov     r10d, [rbx+668h]
0x140005d81  cmp     r10d, eax
0x140005d84  jz      loc_140005E27
0x140005d8a  test    dl, dl
0x140005d8c  jnz     short loc_140005DF0
0x140005d8e  cmp     [rbx+4B1h], dl
0x140005d94  jnz     short loc_140005DF0
0x140005d96  cmp     ecx, 0FFFFFFFFh
0x140005d99  jnz     short loc_140005DA8
0x140005d9b  mov     [rbx+660h], eax
0x140005da1  mov     eax, 5D8h
0x140005da6  jmp     short loc_140005DB9
0x140005da8  cmp     r9d, 0FFFFFFFFh
0x140005dac  jnz     short loc_140005E27
0x140005dae  mov     [rbx+664h], eax
0x140005db4  mov     eax, 618h
0x140005db9  inc     qword ptr [rbx+4A8h]
0x140005dc0  add     rax, rbx
0x140005dc3  mov     [rbx+470h], rax
0x140005dca  test    r8b, r8b
0x140005dcd  movzx   eax, byte ptr [rbx+44Ch]
0x140005dd4  setnz   cl
0x140005dd7  and     al, 0FEh
0x140005dd9  or      cl, al
0x140005ddb  mov     al, 1
0x140005ddd  inc     dword ptr [rbx+48Ch]
0x140005de3  mov     [rbx+44Ch], cl
0x140005de9  add     rsp, 20h
0x140005ded  pop     rbx
0x140005dee  retn
0x140005df0  cmp     r10d, 0FFFFFFFFh
0x140005df4  jnz     short loc_140005E27
0x140005df6  or      byte ptr [rbx+44Ch], 2
0x140005dfd  inc     qword ptr [rbx+4A0h]
0x140005e04  inc     dword ptr [rbx+48Ch]
0x140005e0a  mov     [rbx+668h], eax
0x140005e10  mov     rax, [rbx+658h]
0x140005e17  mov     [rbx+470h], rax
0x140005e1e  mov     al, 1
0x140005e20  add     rsp, 20h
0x140005e24  pop     rbx
0x140005e25  retn
0x140005e27  xor     al, al
0x140005e29  add     rsp, 20h
0x140005e2d  pop     rbx
0x140005e2e  retn
```
