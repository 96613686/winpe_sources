# CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(_SMHTPOS &)

- ea: `0x18000c394`
- end: `0x18000c3fb`
- name: `?MoveNext@?$CSmHashTable@UClient@CMcCoClients@@VCNoLock@@$0HB@@@AEAAXAEAU_SMHTPOS@@@Z`
- size: `103`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b430`
- `0x18000bdd4`
- `0x18000c024`
- `0x18000c230`

## callees

- `0x18000c394`

## pseudocode

```c
void __fastcall CSmHashTable<CMcCoClients::Client,CNoLock,113>::MoveNext(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  unsigned int v5; // edx
  bool v6; // zf
  unsigned int i; // r9d
  __int64 v8; // rax

  if ( !*(_DWORD *)a2 )
  {
    v3 = *(_QWORD *)(a2 + 8);
    if ( !v3 || (v4 = *(_QWORD *)(v3 + 2152), (*(_QWORD *)(a2 + 8) = v4) == 0) )
    {
      v5 = *(_DWORD *)(a2 + 4) + 1;
      *(_DWORD *)(a2 + 4) = v5;
      v6 = v5 == 113;
      if ( v5 < 0x71 )
      {
        for ( i = v5; i < 0x71; v5 = i )
        {
          v8 = *(_QWORD *)(a1 + 24LL * i + 8);
          *(_QWORD *)(a2 + 8) = v8;
          if ( v8 )
            break;
          *(_DWORD *)(a2 + 4) = ++i;
        }
        v6 = v5 == 113;
      }
      if ( v6 )
        *(_DWORD *)a2 = 1;
    }
  }
}

```

## disassembly

```asm
0x18000c394  cmp     dword ptr [rdx], 0
0x18000c397  mov     r8, rdx
0x18000c39a  mov     r10, rcx
0x18000c39d  jnz     short locret_18000C3FA
0x18000c39f  mov     rax, [rdx+8]
0x18000c3a3  test    rax, rax
0x18000c3a6  jz      short loc_18000C3B8
0x18000c3a8  mov     rax, [rax+868h]
0x18000c3af  mov     [rdx+8], rax
0x18000c3b3  test    rax, rax
0x18000c3b6  jnz     short locret_18000C3FA
0x18000c3b8  mov     edx, [rdx+4]
0x18000c3bb  inc     edx
0x18000c3bd  mov     [r8+4], edx
0x18000c3c1  cmp     edx, 71h ; 'q'
0x18000c3c4  jnb     short loc_18000C3F1
0x18000c3c6  mov     r9d, edx
0x18000c3c9  mov     eax, r9d
0x18000c3cc  lea     rcx, [rax+rax*2]
0x18000c3d0  mov     rax, [r10+rcx*8+8]
0x18000c3d5  mov     [r8+8], rax
0x18000c3d9  test    rax, rax
0x18000c3dc  jnz     short loc_18000C3EE
0x18000c3de  lea     edx, [r9+1]
0x18000c3e2  mov     [r8+4], edx
0x18000c3e6  mov     r9d, edx
0x18000c3e9  cmp     edx, 71h ; 'q'
0x18000c3ec  jb      short loc_18000C3C9
0x18000c3ee  cmp     edx, 71h ; 'q'
0x18000c3f1  jnz     short locret_18000C3FA
0x18000c3f3  mov     dword ptr [r8], 1
0x18000c3fa  retn
```
