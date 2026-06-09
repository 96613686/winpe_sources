# PkCompleteInsertion

- ea: `0x140015034`
- end: `0x140015097`
- name: `PkCompleteInsertion`
- size: `99`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002380`
- `0x140002f04`
- `0x1400030fc`
- `0x14000b0e0`
- `0x140014e78`
- `0x14001521c`
- `0x1400152dc`
- `0x14001661c`

## callees

- `0x140015034`
- `0x1400155c8`

## pseudocode

```c
__int64 __fastcall PkCompleteInsertion(__int64 a1, int a2)
{
  _DWORD *v2; // rax
  __int64 v4; // rcx
  int v5; // edx
  __int64 v6; // r8
  int v7; // r9d
  int v8; // r10d
  signed __int32 v10[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = *(_DWORD **)a1;
  v4 = *(unsigned int *)(a1 + 16);
  *(_DWORD *)(a1 + 128) = a2;
  *v2 = a2;
  _InterlockedOr(v10, 0);
  if ( !(unsigned __int8)PkpValidatePointer(v4, (unsigned int)v2[1]) )
    return 3221225730LL;
  *(_DWORD *)(v6 + 132) = v5;
  if ( v8 == v5 )
  {
    if ( !v7 )
      return 532;
    ++**(_QWORD **)(v6 + 152);
  }
  return 0;
}

```

## disassembly

```asm
0x140015034  sub     rsp, 28h
0x140015038  mov     rax, [rcx]
0x14001503b  mov     r8, rcx
0x14001503e  mov     ecx, [rcx+10h]
0x140015041  mov     r10d, [r8+80h]
0x140015048  mov     [r8+80h], edx
0x14001504f  mov     [rax], edx
0x140015051  lock or [rsp+28h+var_28], 0
0x140015056  mov     r9d, [rax+8]
0x14001505a  mov     edx, [rax+4]
0x14001505d  call    PkpValidatePointer
0x140015062  test    al, al
0x140015064  jnz     short loc_14001506D
0x140015066  mov     eax, 0C0000102h
0x14001506b  jmp     short loc_140015091
0x14001506d  mov     [r8+84h], edx
0x140015074  cmp     r10d, edx
0x140015077  jnz     short loc_14001508F
0x140015079  test    r9d, r9d
0x14001507c  jnz     short loc_140015085
0x14001507e  mov     eax, 214h
0x140015083  jmp     short loc_140015091
0x140015085  mov     rax, [r8+98h]
0x14001508c  inc     qword ptr [rax]
0x14001508f  xor     eax, eax
0x140015091  add     rsp, 28h
0x140015095  retn
```
