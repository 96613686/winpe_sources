# CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(_SMHTPOS &)

- ea: `0x18000cbe8`
- end: `0x18000cc44`
- name: `?MoveNext@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z`
- size: `92`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c5dc`
- `0x18000cc4c`

## callees

- `0x18000cbe8`

## pseudocode

```c
void __fastcall CSmHashTable<PacketVariable,CNoLock,113>::MoveNext(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  __int64 v3; // rax
  __int64 i; // r8
  __int64 v5; // rax

  if ( !*(_DWORD *)a2 )
  {
    v2 = *(_QWORD *)(a2 + 8);
    if ( !v2 || (v3 = *(_QWORD *)(v2 + 96), (*(_QWORD *)(a2 + 8) = v3) == 0) )
    {
      for ( i = (unsigned int)(*(_DWORD *)(a2 + 4) + 1); ; i = (unsigned int)(i + 1) )
      {
        *(_DWORD *)(a2 + 4) = i;
        if ( (unsigned int)i >= 0x71 )
          break;
        v5 = *(_QWORD *)(a1 + 24 * i + 8);
        if ( v5 )
        {
          *(_QWORD *)(a2 + 8) = v5;
          break;
        }
        *(_QWORD *)(a2 + 8) = 0;
      }
      if ( (_DWORD)i == 113 )
        *(_DWORD *)a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x18000cbe8  cmp     dword ptr [rdx], 0
0x18000cbeb  mov     r10, rcx
0x18000cbee  jnz     short locret_18000CC43
0x18000cbf0  mov     rax, [rdx+8]
0x18000cbf4  test    rax, rax
0x18000cbf7  jz      short loc_18000CC06
0x18000cbf9  mov     rax, [rax+60h]
0x18000cbfd  mov     [rdx+8], rax
0x18000cc01  test    rax, rax
0x18000cc04  jnz     short locret_18000CC43
0x18000cc06  mov     r8d, [rdx+4]
0x18000cc0a  inc     r8d
0x18000cc0d  jmp     short loc_18000CC24
0x18000cc0f  lea     rcx, [r8+r8*2]
0x18000cc13  mov     rax, [r10+rcx*8+8]
0x18000cc18  test    rax, rax
0x18000cc1b  jnz     short loc_18000CC33
0x18000cc1d  and     [rdx+8], rax
0x18000cc21  inc     r8d
0x18000cc24  mov     [rdx+4], r8d
0x18000cc28  mov     r9d, r8d
0x18000cc2b  cmp     r8d, 71h ; 'q'
0x18000cc2f  jb      short loc_18000CC0F
0x18000cc31  jmp     short loc_18000CC37
0x18000cc33  mov     [rdx+8], rax
0x18000cc37  cmp     r9d, 71h ; 'q'
0x18000cc3b  jnz     short locret_18000CC43
0x18000cc3d  mov     dword ptr [rdx], 1
0x18000cc43  retn
```
